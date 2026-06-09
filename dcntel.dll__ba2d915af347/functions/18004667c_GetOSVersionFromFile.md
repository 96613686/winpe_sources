# GetOSVersionFromFile

- ea: `0x18004667c`
- end: `0x180046868`
- name: `GetOSVersionFromFile`
- size: `492`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x18004c380`

## callees

- `0x180008dc0`
- `0x180012734`
- `0x18004667c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180046789`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180046789`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004676c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004676c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046836`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046836`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18004675b`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18004675b`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x1800467ae`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x1800467ae`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800467d3`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800467d3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180046715`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180046715`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800466e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180046727`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800466e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180046727`

## string_xrefs

- `0x1800466f3`: `\kernel32.dll`
- `0x180046737`: `\ntdll.dll`

## pseudocode

```c
__int64 __fastcall GetOSVersionFromFile(_DWORD *a1, _DWORD *a2, unsigned int *a3, _DWORD *a4, unsigned int *a5)
{
  int v8; // ebx
  DWORD FileVersionInfoSizeW; // r14d
  HANDLE ProcessHeap; // rax
  void *v11; // rsi
  void *v12; // rax
  void *v13; // rdi
  unsigned __int16 *v14; // rcx
  _DWORD *v15; // rdx
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int puLen; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID lpBuffer; // [rsp+28h] [rbp-D8h] BYREF
  _DWORD *v21; // [rsp+30h] [rbp-D0h]
  unsigned int *v22; // [rsp+38h] [rbp-C8h]
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF

  v21 = a2;
  v22 = a5;
  lpBuffer = 0;
  puLen = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
    return (unsigned int)-2147418113;
  v8 = StringCchCatW(Buffer, 0x104u, L"\\kernel32.dll");
  if ( v8 < 0 )
    return (unsigned int)v8;
  if ( GetFileAttributesW(Buffer) == -1 )
  {
    if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
      return (unsigned int)-2147418113;
    v8 = StringCchCatW(Buffer, 0x104u, L"\\ntdll.dll");
    if ( v8 < 0 )
      return (unsigned int)v8;
  }
  FileVersionInfoSizeW = GetFileVersionInfoSizeW(Buffer, 0);
  if ( !FileVersionInfoSizeW )
    return (unsigned int)-2147418113;
  ProcessHeap = GetProcessHeap();
  v11 = ProcessHeap;
  if ( !ProcessHeap )
    return (unsigned int)-2147418113;
  v12 = HeapAlloc(ProcessHeap, 8u, FileVersionInfoSizeW);
  v13 = v12;
  if ( v12 )
  {
    if ( GetFileVersionInfoW(Buffer, 0, FileVersionInfoSizeW, v12) && VerQueryValueW(v13, L"\\", &lpBuffer, &puLen) )
    {
      v14 = (unsigned __int16 *)lpBuffer;
      v15 = v21;
      *a1 = *((unsigned __int16 *)lpBuffer + 5);
      *v15 = v14[4];
      v16 = v14[7];
      *v22 = v16;
      if ( v16 >= 0x23F0 )
        v17 = 0;
      else
        v17 = v16 % 0xA;
      *a3 = v17;
      *a4 = 0;
    }
    else
    {
      v8 = -2147418113;
    }
    HeapFree(v11, 0, v13);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004667c  push    rbp
0x18004667e  push    rbx
0x18004667f  push    rsi
0x180046680  push    rdi
0x180046681  push    r12
0x180046683  push    r13
0x180046685  push    r14
0x180046687  push    r15
0x180046689  lea     rbp, [rsp-168h]
0x180046691  sub     rsp, 268h
0x180046698  mov     rax, cs:__security_cookie
0x18004669f  xor     rax, rsp
0x1800466a2  mov     [rbp+1A0h+var_50], rax
0x1800466a9  mov     rax, [rbp+1A0h+arg_20]
0x1800466b0  mov     r13, rcx
0x1800466b3  mov     [rsp+2A0h+var_270], rdx
0x1800466b8  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x1800466bd  mov     edi, 104h
0x1800466c2  mov     [rsp+2A0h+var_268], rax
0x1800466c7  mov     edx, edi; uSize
0x1800466c9  mov     [rsp+2A0h+lpBuffer], 0
0x1800466d2  mov     r12, r9
0x1800466d5  mov     [rsp+2A0h+puLen], 0
0x1800466dd  mov     r15, r8
0x1800466e0  call    cs:__imp_GetSystemDirectoryW
0x1800466e6  dec     eax
0x1800466e8  lea     esi, [rdi-2]
0x1800466eb  cmp     eax, esi
0x1800466ed  ja      loc_18004683E
0x1800466f3  lea     r8, aKernel32Dll; "\\kernel32.dll"
0x1800466fa  mov     edx, edi; unsigned __int64
0x1800466fc  lea     rcx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x180046701  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180046706  mov     ebx, eax
0x180046708  test    eax, eax
0x18004670a  js      loc_180046843
0x180046710  lea     rcx, [rsp+2A0h+Buffer]; lpFileName
0x180046715  call    cs:__imp_GetFileAttributesW
0x18004671b  cmp     eax, 0FFFFFFFFh
0x18004671e  jnz     short loc_180046754
0x180046720  mov     edx, edi; uSize
0x180046722  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x180046727  call    cs:__imp_GetSystemDirectoryW
0x18004672d  dec     eax
0x18004672f  cmp     eax, esi
0x180046731  ja      loc_18004683E
0x180046737  lea     r8, aNtdllDll_0; "\\ntdll.dll"
0x18004673e  mov     edx, edi; unsigned __int64
0x180046740  lea     rcx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x180046745  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004674a  mov     ebx, eax
0x18004674c  test    eax, eax
0x18004674e  js      loc_180046843
0x180046754  xor     edx, edx; lpdwHandle
0x180046756  lea     rcx, [rsp+2A0h+Buffer]; lptstrFilename
0x18004675b  call    cs:__imp_GetFileVersionInfoSizeW
0x180046761  mov     r14d, eax
0x180046764  test    eax, eax
0x180046766  jz      loc_18004683E
0x18004676c  call    cs:__imp_GetProcessHeap
0x180046772  mov     rsi, rax
0x180046775  test    rax, rax
0x180046778  jz      loc_18004683E
0x18004677e  mov     r8d, r14d; dwBytes
0x180046781  mov     edx, 8; dwFlags
0x180046786  mov     rcx, rax; hHeap
0x180046789  call    cs:__imp_HeapAlloc
0x18004678f  mov     rdi, rax
0x180046792  test    rax, rax
0x180046795  jnz     short loc_1800467A1
0x180046797  mov     ebx, 8007000Eh
0x18004679c  jmp     loc_180046843
0x1800467a1  mov     r9, rdi; lpData
0x1800467a4  lea     rcx, [rsp+2A0h+Buffer]; lptstrFilename
0x1800467a9  mov     r8d, r14d; dwLen
0x1800467ac  xor     edx, edx; dwHandle
0x1800467ae  call    cs:__imp_GetFileVersionInfoW
0x1800467b4  test    eax, eax
0x1800467b6  jnz     short loc_1800467BF
0x1800467b8  mov     ebx, 8000FFFFh
0x1800467bd  jmp     short loc_18004682E
0x1800467bf  lea     r9, [rsp+2A0h+puLen]; puLen
0x1800467c4  mov     rcx, rdi; pBlock
0x1800467c7  lea     r8, [rsp+2A0h+lpBuffer]; lplpBuffer
0x1800467cc  lea     rdx, Source; "\\"
0x1800467d3  call    cs:__imp_VerQueryValueW
0x1800467d9  test    eax, eax
0x1800467db  jz      short loc_1800467B8
0x1800467dd  mov     rcx, [rsp+2A0h+lpBuffer]
0x1800467e2  mov     rdx, [rsp+2A0h+var_270]
0x1800467e7  movzx   eax, word ptr [rcx+0Ah]
0x1800467eb  mov     [r13+0], eax
0x1800467ef  movzx   eax, word ptr [rcx+8]
0x1800467f3  mov     [rdx], eax
0x1800467f5  movzx   r8d, word ptr [rcx+0Eh]
0x1800467fa  mov     rax, [rsp+2A0h+var_268]
0x1800467ff  mov     [rax], r8d
0x180046802  cmp     r8d, 23F0h
0x180046809  jnb     short loc_180046820
0x18004680b  mov     eax, 0CCCCCCCDh
0x180046810  mul     r8d
0x180046813  shr     edx, 3
0x180046816  lea     eax, [rdx+rdx*4]
0x180046819  add     eax, eax
0x18004681b  sub     r8d, eax
0x18004681e  jmp     short loc_180046823
0x180046820  xor     r8d, r8d
0x180046823  mov     [r15], r8d
0x180046826  mov     dword ptr [r12], 0
0x18004682e  mov     r8, rdi; lpMem
0x180046831  xor     edx, edx; dwFlags
0x180046833  mov     rcx, rsi; hHeap
0x180046836  call    cs:__imp_HeapFree
0x18004683c  jmp     short loc_180046843
0x18004683e  mov     ebx, 8000FFFFh
0x180046843  mov     eax, ebx
0x180046845  mov     rcx, [rbp+1A0h+var_50]
0x18004684c  xor     rcx, rsp; StackCookie
0x18004684f  call    __security_check_cookie
0x180046854  add     rsp, 268h
0x18004685b  pop     r15
0x18004685d  pop     r14
0x18004685f  pop     r13
0x180046861  pop     r12
0x180046863  pop     rdi
0x180046864  pop     rsi
0x180046865  pop     rbx
0x180046866  pop     rbp
0x180046867  retn
```
