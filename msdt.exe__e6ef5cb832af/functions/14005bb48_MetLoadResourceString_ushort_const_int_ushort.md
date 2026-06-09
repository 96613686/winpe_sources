# MetLoadResourceString(ushort const *,int,ushort * *)

- ea: `0x14005bb48`
- end: `0x14005bca3`
- name: `?MetLoadResourceString@@YAJPEBGHPEAPEAG@Z`
- size: `347`
- prototype: `__int64 __fastcall(const unsigned __int16 *, UINT, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14005befc`
- `0x14005ca60`

## callees

- `0x140020420`
- `0x14005bb48`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14005bc20`
- `KERNEL32!GetLastError` at `0x14005bc20`
- `KERNEL32!HeapAlloc` at `0x14005bb90`
- `KERNEL32!HeapAlloc` at `0x14005bb90`
- `KERNEL32!HeapFree` at `0x14005bc8b`
- `KERNEL32!HeapFree` at `0x14005bc8b`
- `KERNEL32!GetProcessHeap` at `0x14005bb79`
- `KERNEL32!GetProcessHeap` at `0x14005bc77`
- `KERNEL32!GetProcessHeap` at `0x14005bb79`
- `KERNEL32!GetProcessHeap` at `0x14005bc77`
- `KERNEL32!FreeLibrary` at `0x14005bc66`
- `KERNEL32!FreeLibrary` at `0x14005bc66`
- `KERNEL32!LoadLibraryExW` at `0x14005bb5c`
- `KERNEL32!LoadLibraryExW` at `0x14005bb5c`
- `USER32!LoadStringW` at `0x14005bbde`
- `USER32!LoadStringW` at `0x14005bbde`
- `OLEAUT32!__imp_SysAllocString` at `0x14005bc02`
- `OLEAUT32!__imp_SysAllocString` at `0x14005bc02`

## pseudocode

```c
__int64 __fastcall MetLoadResourceString(const unsigned __int16 *a1, UINT a2, unsigned __int16 **a3)
{
  HMODULE Library; // rsi
  HANDLE ProcessHeap; // rax
  WCHAR *v7; // rax
  OLECHAR *v8; // rdi
  int v9; // r9d
  unsigned int v10; // ebx
  unsigned __int16 *v11; // rax
  signed int LastError; // eax
  HANDLE v13; // rax

  Library = LoadLibraryExW(a1, 0, 2u);
  if ( (unsigned __int64)Library - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    ProcessHeap = GetProcessHeap();
    v7 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x800u);
    v8 = v7;
    if ( v7 )
    {
      if ( LoadStringW(Library, a2, v7, 1024) <= 0 )
      {
        v10 = -2143551222;
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetLoadResourceString", 112, -2143551222);
        goto LABEL_14;
      }
      v11 = SysAllocString(v8);
      *a3 = v11;
      if ( v11 )
      {
        v10 = 0;
        goto LABEL_14;
      }
      v9 = 116;
    }
    else
    {
      v9 = 108;
    }
    v10 = -2147024882;
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetLoadResourceString", v9, -2147024882);
LABEL_14:
    FreeLibrary(Library);
    if ( v8 )
    {
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v8);
    }
    return v10;
  }
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
  SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetLoadResourceString", 106, v10);
  v8 = 0;
  if ( Library )
    goto LABEL_14;
  return v10;
}

```

## disassembly

```asm
0x14005bb48  push    rbx
0x14005bb4a  push    rbp
0x14005bb4b  push    rsi
0x14005bb4c  push    rdi
0x14005bb4d  sub     rsp, 38h
0x14005bb51  mov     ebp, edx
0x14005bb53  mov     rbx, r8
0x14005bb56  xor     edx, edx; hFile
0x14005bb58  lea     r8d, [rdx+2]; dwFlags
0x14005bb5c  call    cs:__imp_LoadLibraryExW
0x14005bb63  nop     dword ptr [rax+rax+00h]
0x14005bb68  mov     rsi, rax
0x14005bb6b  lea     rcx, [rax-1]
0x14005bb6f  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14005bb73  ja      loc_14005BC20
0x14005bb79  call    cs:__imp_GetProcessHeap
0x14005bb80  nop     dword ptr [rax+rax+00h]
0x14005bb85  xor     edx, edx; dwFlags
0x14005bb87  mov     r8d, 800h; dwBytes
0x14005bb8d  mov     rcx, rax; hHeap
0x14005bb90  call    cs:__imp_HeapAlloc
0x14005bb97  nop     dword ptr [rax+rax+00h]
0x14005bb9c  mov     rdi, rax
0x14005bb9f  test    rax, rax
0x14005bba2  jnz     short loc_14005BBD0
0x14005bba4  lea     r9d, [rax+6Ch]
0x14005bba8  mov     eax, 8007000Eh
0x14005bbad  mov     [rsp+58h+var_38], eax
0x14005bbb1  mov     ebx, eax
0x14005bbb3  lea     r8, aMetloadresourc; "MetLoadResourceString"
0x14005bbba  mov     ecx, 1; Level
0x14005bbbf  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x14005bbc6  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14005bbcb  jmp     loc_14005BC63
0x14005bbd0  mov     r9d, 400h; cchBufferMax
0x14005bbd6  mov     r8, rdi; lpBuffer
0x14005bbd9  mov     edx, ebp; uID
0x14005bbdb  mov     rcx, rsi; hInstance
0x14005bbde  call    cs:__imp_LoadStringW
0x14005bbe5  nop     dword ptr [rax+rax+00h]
0x14005bbea  test    eax, eax
0x14005bbec  jg      short loc_14005BBFF
0x14005bbee  mov     ebx, 803C010Ah
0x14005bbf3  mov     r9d, 70h ; 'p'
0x14005bbf9  mov     [rsp+58h+var_38], ebx
0x14005bbfd  jmp     short loc_14005BBB3
0x14005bbff  mov     rcx, rdi; psz
0x14005bc02  call    cs:__imp_SysAllocString
0x14005bc09  nop     dword ptr [rax+rax+00h]
0x14005bc0e  mov     [rbx], rax
0x14005bc11  test    rax, rax
0x14005bc14  jnz     short loc_14005BC1C
0x14005bc16  lea     r9d, [rax+74h]
0x14005bc1a  jmp     short loc_14005BBA8
0x14005bc1c  xor     ebx, ebx
0x14005bc1e  jmp     short loc_14005BC63
0x14005bc20  call    cs:__imp_GetLastError
0x14005bc27  nop     dword ptr [rax+rax+00h]
0x14005bc2c  mov     ebx, eax
0x14005bc2e  test    eax, eax
0x14005bc30  jle     short loc_14005BC3B
0x14005bc32  movzx   ebx, ax
0x14005bc35  or      ebx, 80070000h
0x14005bc3b  mov     r9d, 6Ah ; 'j'
0x14005bc41  mov     [rsp+58h+var_38], ebx
0x14005bc45  lea     r8, aMetloadresourc; "MetLoadResourceString"
0x14005bc4c  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x14005bc53  lea     ecx, [r9-69h]; Level
0x14005bc57  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14005bc5c  xor     edi, edi
0x14005bc5e  test    rsi, rsi
0x14005bc61  jz      short loc_14005BC97
0x14005bc63  mov     rcx, rsi; hLibModule
0x14005bc66  call    cs:__imp_FreeLibrary
0x14005bc6d  nop     dword ptr [rax+rax+00h]
0x14005bc72  test    rdi, rdi
0x14005bc75  jz      short loc_14005BC97
0x14005bc77  call    cs:__imp_GetProcessHeap
0x14005bc7e  nop     dword ptr [rax+rax+00h]
0x14005bc83  mov     r8, rdi; lpMem
0x14005bc86  xor     edx, edx; dwFlags
0x14005bc88  mov     rcx, rax; hHeap
0x14005bc8b  call    cs:__imp_HeapFree
0x14005bc92  nop     dword ptr [rax+rax+00h]
0x14005bc97  mov     eax, ebx
0x14005bc99  add     rsp, 38h
0x14005bc9d  pop     rdi
0x14005bc9e  pop     rsi
0x14005bc9f  pop     rbp
0x14005bca0  pop     rbx
0x14005bca1  retn
```
