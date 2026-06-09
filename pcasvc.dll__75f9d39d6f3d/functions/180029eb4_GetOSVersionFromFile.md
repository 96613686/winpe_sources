# GetOSVersionFromFile

- ea: `0x180029eb4`
- end: `0x18002a133`
- name: `GetOSVersionFromFile`
- size: `639`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180029a58`

## callees

- `0x180013334`
- `0x180029eb4`
- `0x1800f1f10`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a0c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a0c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a019`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a019`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a036`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a036`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180029f12`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002a0da`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180029f12`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002a0da`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180029ff2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180029ff2`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18002a055`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18002a055`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18002a008`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18002a008`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18002a073`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18002a073`

## string_xrefs

- `0x180029f6c`: `\kernel32.dll`
- `0x18002a0e7`: `\ntdll.dll`

## pseudocode

```c
__int64 __fastcall GetOSVersionFromFile(_DWORD *a1, _DWORD *a2, unsigned int *a3, _DWORD *a4, unsigned int *a5)
{
  __int64 v8; // rdx
  WCHAR *v9; // rax
  unsigned int v10; // ebx
  __int64 v11; // r8
  const wchar_t *v12; // r9
  __int64 v13; // rcx
  WCHAR *v14; // rax
  __int64 v15; // rdx
  WCHAR *v16; // rcx
  DWORD FileVersionInfoSizeW; // r14d
  HANDLE ProcessHeap; // rax
  void *v20; // rsi
  void *v21; // rax
  void *v22; // rdi
  unsigned __int16 *v23; // rcx
  _DWORD *v24; // rdx
  unsigned int v25; // r8d
  unsigned int v26; // r8d
  unsigned int puLen; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID lpBuffer; // [rsp+28h] [rbp-D8h] BYREF
  _DWORD *v29; // [rsp+30h] [rbp-D0h]
  unsigned int *v30; // [rsp+38h] [rbp-C8h]
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF

  v29 = a2;
  v30 = a5;
  lpBuffer = 0;
  puLen = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
    return (unsigned int)-2147418113;
  v8 = 260;
  v9 = Buffer;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v8;
  }
  while ( v8 );
  v10 = v8 == 0 ? 0x80070057 : 0;
  v11 = (260 - v8) & -(__int64)(v8 != 0);
  if ( v8 )
  {
    v12 = L"\\kernel32.dll";
    v13 = 2147483646;
    v14 = &Buffer[v11];
    v15 = 260 - v11;
    if ( v11 != 260 )
    {
      do
      {
        if ( !v13 )
          break;
        if ( !*v12 )
          break;
        *v14++ = *v12++;
        --v13;
        --v15;
      }
      while ( v15 );
    }
    v16 = v14 - 1;
    if ( v15 )
      v16 = v14;
    *v16 = 0;
    v10 = v15 == 0 ? 0x8007007A : 0;
    if ( v15 )
    {
      if ( GetFileAttributesW(Buffer) == -1 )
      {
        if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
          return (unsigned int)-2147418113;
        v10 = StringCchCatW(Buffer, 0x104u, L"\\ntdll.dll");
        if ( (v10 & 0x80000000) != 0 )
          return v10;
      }
      FileVersionInfoSizeW = GetFileVersionInfoSizeW(Buffer, 0);
      if ( FileVersionInfoSizeW )
      {
        ProcessHeap = GetProcessHeap();
        v20 = ProcessHeap;
        if ( ProcessHeap )
        {
          v21 = HeapAlloc(ProcessHeap, 8u, FileVersionInfoSizeW);
          v22 = v21;
          if ( v21 )
          {
            if ( GetFileVersionInfoW(Buffer, 0, FileVersionInfoSizeW, v21)
              && VerQueryValueW(v22, L"\\", &lpBuffer, &puLen) )
            {
              v23 = (unsigned __int16 *)lpBuffer;
              v24 = v29;
              *a1 = *((unsigned __int16 *)lpBuffer + 5);
              *v24 = v23[4];
              v25 = v23[7];
              *v30 = v25;
              if ( v25 < 0x23F0 )
                v26 = v25 % 0xA;
              else
                v26 = 0;
              *a3 = v26;
              *a4 = 0;
            }
            else
            {
              v10 = -2147418113;
            }
            HeapFree(v20, 0, v22);
          }
          else
          {
            return (unsigned int)-2147024882;
          }
          return v10;
        }
      }
      return (unsigned int)-2147418113;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180029eb4  push    rbp
0x180029eb6  push    rbx
0x180029eb7  push    rsi
0x180029eb8  push    rdi
0x180029eb9  push    r12
0x180029ebb  push    r13
0x180029ebd  push    r14
0x180029ebf  push    r15
0x180029ec1  lea     rbp, [rsp-168h]
0x180029ec9  sub     rsp, 268h
0x180029ed0  mov     rax, cs:__security_cookie
0x180029ed7  xor     rax, rsp
0x180029eda  mov     [rbp+1A0h+var_50], rax
0x180029ee1  mov     rax, [rbp+1A0h+arg_20]
0x180029ee8  mov     r13, rcx
0x180029eeb  mov     [rsp+2A0h+var_270], rdx
0x180029ef0  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x180029ef5  xor     edi, edi
0x180029ef7  mov     [rsp+2A0h+var_268], rax
0x180029efc  mov     esi, 104h
0x180029f01  mov     [rsp+2A0h+lpBuffer], rdi
0x180029f06  mov     edx, esi; uSize
0x180029f08  mov     [rsp+2A0h+puLen], edi
0x180029f0c  mov     r12, r9
0x180029f0f  mov     r15, r8
0x180029f12  call    cs:__imp_GetSystemDirectoryW
0x180029f18  dec     eax
0x180029f1a  lea     r14d, [rsi-2]
0x180029f1e  cmp     eax, r14d
0x180029f21  ja      loc_18002A129
0x180029f27  mov     edx, esi
0x180029f29  lea     rax, [rsp+2A0h+Buffer]
0x180029f2e  cmp     [rax], di
0x180029f31  jz      short loc_180029F3D
0x180029f33  add     rax, 2
0x180029f37  sub     rdx, 1
0x180029f3b  jnz     short loc_180029F2E
0x180029f3d  mov     rax, rdx
0x180029f40  mov     rcx, rsi
0x180029f43  neg     rax
0x180029f46  mov     rax, rdx
0x180029f49  sbb     ebx, ebx
0x180029f4b  sub     rcx, rdx
0x180029f4e  not     ebx
0x180029f50  and     ebx, 80070057h
0x180029f56  neg     rax
0x180029f59  sbb     r8, r8
0x180029f5c  and     r8, rcx
0x180029f5f  test    rdx, rdx
0x180029f62  jz      short loc_180029FC8
0x180029f64  mov     rdx, rsi
0x180029f67  lea     rax, [rsp+2A0h+Buffer]
0x180029f6c  lea     r9, aKernel32Dll; "\\kernel32.dll"
0x180029f73  mov     ecx, 7FFFFFFEh
0x180029f78  lea     rax, [rax+r8*2]
0x180029f7c  sub     rdx, r8
0x180029f7f  jz      short loc_180029FA5
0x180029f81  test    rcx, rcx
0x180029f84  jz      short loc_180029FA5
0x180029f86  movzx   r8d, word ptr [r9]
0x180029f8a  test    r8w, r8w
0x180029f8e  jz      short loc_180029FA5
0x180029f90  mov     [rax], r8w
0x180029f94  add     r9, 2
0x180029f98  add     rax, 2
0x180029f9c  dec     rcx
0x180029f9f  sub     rdx, 1
0x180029fa3  jnz     short loc_180029F81
0x180029fa5  test    rdx, rdx
0x180029fa8  lea     rcx, [rax-2]
0x180029fac  cmovnz  rcx, rax
0x180029fb0  mov     rax, rdx
0x180029fb3  neg     rax
0x180029fb6  sbb     ebx, ebx
0x180029fb8  not     ebx
0x180029fba  mov     [rcx], di
0x180029fbd  and     ebx, 8007007Ah
0x180029fc3  test    rdx, rdx
0x180029fc6  jnz     short loc_180029FED
0x180029fc8  mov     eax, ebx
0x180029fca  mov     rcx, [rbp+1A0h+var_50]
0x180029fd1  xor     rcx, rsp; StackCookie
0x180029fd4  call    __security_check_cookie
0x180029fd9  add     rsp, 268h
0x180029fe0  pop     r15
0x180029fe2  pop     r14
0x180029fe4  pop     r13
0x180029fe6  pop     r12
0x180029fe8  pop     rdi
0x180029fe9  pop     rsi
0x180029fea  pop     rbx
0x180029feb  pop     rbp
0x180029fec  retn
0x180029fed  lea     rcx, [rsp+2A0h+Buffer]; lpFileName
0x180029ff2  call    cs:__imp_GetFileAttributesW
0x180029ff8  cmp     eax, 0FFFFFFFFh
0x180029ffb  jz      loc_18002A0D3
0x18002a001  xor     edx, edx; lpdwHandle
0x18002a003  lea     rcx, [rsp+2A0h+Buffer]; lptstrFilename
0x18002a008  call    cs:__imp_GetFileVersionInfoSizeW
0x18002a00e  mov     r14d, eax
0x18002a011  test    eax, eax
0x18002a013  jz      loc_18002A129
0x18002a019  call    cs:__imp_GetProcessHeap
0x18002a01f  mov     rsi, rax
0x18002a022  test    rax, rax
0x18002a025  jz      loc_18002A129
0x18002a02b  mov     r8d, r14d; dwBytes
0x18002a02e  mov     edx, 8; dwFlags
0x18002a033  mov     rcx, rax; hHeap
0x18002a036  call    cs:__imp_HeapAlloc
0x18002a03c  mov     rdi, rax
0x18002a03f  test    rax, rax
0x18002a042  jz      loc_18002A10A
0x18002a048  mov     r9, rax; lpData
0x18002a04b  lea     rcx, [rsp+2A0h+Buffer]; lptstrFilename
0x18002a050  mov     r8d, r14d; dwLen
0x18002a053  xor     edx, edx; dwHandle
0x18002a055  call    cs:__imp_GetFileVersionInfoW
0x18002a05b  test    eax, eax
0x18002a05d  jz      short loc_18002A0CC
0x18002a05f  lea     r9, [rsp+2A0h+puLen]; puLen
0x18002a064  mov     rcx, rdi; pBlock
0x18002a067  lea     r8, [rsp+2A0h+lpBuffer]; lplpBuffer
0x18002a06c  lea     rdx, SubBlock; "\\"
0x18002a073  call    cs:__imp_VerQueryValueW
0x18002a079  test    eax, eax
0x18002a07b  jz      short loc_18002A0CC
0x18002a07d  mov     rcx, [rsp+2A0h+lpBuffer]
0x18002a082  mov     rdx, [rsp+2A0h+var_270]
0x18002a087  movzx   eax, word ptr [rcx+0Ah]
0x18002a08b  mov     [r13+0], eax
0x18002a08f  movzx   eax, word ptr [rcx+8]
0x18002a093  mov     [rdx], eax
0x18002a095  movzx   r8d, word ptr [rcx+0Eh]
0x18002a09a  mov     rax, [rsp+2A0h+var_268]
0x18002a09f  mov     [rax], r8d
0x18002a0a2  cmp     r8d, 23F0h
0x18002a0a9  jb      short loc_18002A114
0x18002a0ab  xor     r8d, r8d
0x18002a0ae  mov     [r15], r8d
0x18002a0b1  mov     dword ptr [r12], 0
0x18002a0b9  mov     r8, rdi; lpMem
0x18002a0bc  xor     edx, edx; dwFlags
0x18002a0be  mov     rcx, rsi; hHeap
0x18002a0c1  call    cs:__imp_HeapFree
0x18002a0c7  jmp     loc_180029FC8
0x18002a0cc  mov     ebx, 8000FFFFh
0x18002a0d1  jmp     short loc_18002A0B9
0x18002a0d3  mov     edx, esi; uSize
0x18002a0d5  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x18002a0da  call    cs:__imp_GetSystemDirectoryW
0x18002a0e0  dec     eax
0x18002a0e2  cmp     eax, r14d
0x18002a0e5  ja      short loc_18002A129
0x18002a0e7  lea     r8, aNtdllDll_0; "\\ntdll.dll"
0x18002a0ee  mov     rdx, rsi; unsigned __int64
0x18002a0f1  lea     rcx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x18002a0f6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002a0fb  mov     ebx, eax
0x18002a0fd  test    eax, eax
0x18002a0ff  js      loc_180029FC8
0x18002a105  jmp     loc_18002A001
0x18002a10a  mov     ebx, 8007000Eh
0x18002a10f  jmp     loc_180029FC8
0x18002a114  mov     eax, 0CCCCCCCDh
0x18002a119  mul     r8d
0x18002a11c  shr     edx, 3
0x18002a11f  lea     eax, [rdx+rdx*4]
0x18002a122  add     eax, eax
0x18002a124  sub     r8d, eax
0x18002a127  jmp     short loc_18002A0AE
0x18002a129  mov     ebx, 8000FFFFh
0x18002a12e  jmp     loc_180029FC8
```
