# debugOpenLogFile

- ea: `0x140071d04`
- end: `0x140071ec0`
- name: `debugOpenLogFile`
- size: `444`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1400236a0`
- `0x140027708`

## callees

- `0x140002c43`
- `0x140004aa4`
- `0x14006a3a4`
- `0x140071d04`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetTempPath2W` at `0x140071da5`
- `KERNEL32!GetTempPath2W` at `0x140071da5`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x140071d75`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x140071d75`
- `KERNEL32!CloseHandle` at `0x140071e9a`
- `KERNEL32!CloseHandle` at `0x140071e9a`
- `KERNEL32!SetFilePointer` at `0x140071e88`
- `KERNEL32!SetFilePointer` at `0x140071e88`
- `msvcrt!wcschr` at `0x140071d8e`
- `msvcrt!wcschr` at `0x140071d8e`

## pseudocode

```c
__int64 debugOpenLogFile()
{
  __int64 v1; // rbx
  __int64 v2; // r9
  __int64 v3; // rcx
  WCHAR *v4; // rdx
  WCHAR *v5; // rax
  WCHAR *v6; // rdx
  void *File; // rax
  WCHAR Dst[264]; // [rsp+40h] [rbp-438h] BYREF
  _BYTE v9[528]; // [rsp+250h] [rbp-228h] BYREF

  memset_0(Dst, 0, 0x208u);
  memset_0(v9, 0, 0x208u);
  if ( g_hLogFile != (HANDLE)-1LL )
  {
    _InterlockedIncrement(&g_iLogFileRefCount);
    return 1;
  }
  v1 = 260;
  if ( ExpandEnvironmentStringsW(L"FXSSVCDebugLogFile.txt", Dst, 0x104u) - 1 <= 0x103 )
  {
    if ( wcschr(Dst, 0x5Cu) )
    {
      v3 = 2147483646;
      v4 = Dst;
      v5 = &g_szPathToFile;
      do
      {
        if ( !v3 )
          break;
        if ( !*v4 )
          break;
        *v5++ = *v4++;
        --v3;
        --v1;
      }
      while ( v1 );
      v6 = v5 - 1;
      if ( v1 )
        v6 = v5;
      *v6 = 0;
      if ( !v1 )
        return 0;
    }
    else if ( !(unsigned int)GetTempPath2W(260, v9)
           || (int)StringCchPrintfW(&g_szPathToFile, 0x104u, L"%s%s", v9, Dst) < 0 )
    {
      return 0;
    }
    File = (void *)InternalSafeCreateFile(&g_szPathToFile, 0x40000000u, 3u, v2, 4u, 128);
    g_hLogFile = File;
    if ( File != (void *)-1LL )
    {
      if ( SetFilePointer(File, 0, 0, 2u) != -1 )
      {
        _InterlockedExchange(&g_iLogFileRefCount, 1);
        return 1;
      }
      CloseHandle(g_hLogFile);
      g_hLogFile = (HANDLE)-1LL;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140071d04  mov     [rsp+arg_0], rbx
0x140071d09  push    rdi
0x140071d0a  sub     rsp, 470h
0x140071d11  mov     rax, cs:__security_cookie
0x140071d18  xor     rax, rsp
0x140071d1b  mov     [rsp+478h+var_18], rax
0x140071d23  mov     ebx, 208h
0x140071d28  lea     rcx, [rsp+478h+Dst]; void *
0x140071d2d  mov     r8d, ebx; Size
0x140071d30  xor     edx, edx; Val
0x140071d32  call    memset_0
0x140071d37  mov     r8d, ebx; Size
0x140071d3a  lea     rcx, [rsp+478h+var_228]; void *
0x140071d42  xor     edx, edx; Val
0x140071d44  call    memset_0
0x140071d49  cmp     cs:?g_hLogFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * g_hLogFile
0x140071d51  jz      short loc_140071D61
0x140071d53  lock inc cs:?g_iLogFileRefCount@@3JA; long g_iLogFileRefCount
0x140071d5a  mov     eax, 1
0x140071d5f  jmp     short loc_140071DDC
0x140071d61  mov     ebx, 104h
0x140071d66  lea     rdx, [rsp+478h+Dst]; lpDst
0x140071d6b  mov     r8d, ebx; nSize
0x140071d6e  lea     rcx, Src; "FXSSVCDebugLogFile.txt"
0x140071d75  call    cs:__imp_ExpandEnvironmentStringsW
0x140071d7b  dec     eax
0x140071d7d  cmp     eax, 103h
0x140071d82  ja      short loc_140071DDA
0x140071d84  mov     edx, 5Ch ; '\'; Ch
0x140071d89  lea     rcx, [rsp+478h+Dst]; Str
0x140071d8e  call    cs:__imp_wcschr
0x140071d94  xor     edi, edi
0x140071d96  test    rax, rax
0x140071d99  jnz     short loc_140071DFD
0x140071d9b  lea     rdx, [rsp+478h+var_228]
0x140071da3  mov     ecx, ebx
0x140071da5  call    cs:__imp_GetTempPath2W
0x140071dab  test    eax, eax
0x140071dad  jz      short loc_140071DDA
0x140071daf  lea     rax, [rsp+478h+Dst]
0x140071db4  mov     edx, ebx; unsigned __int64
0x140071db6  lea     r9, [rsp+478h+var_228]
0x140071dbe  mov     qword ptr [rsp+478h+var_458], rax
0x140071dc3  lea     r8, aSS_1; "%s%s"
0x140071dca  lea     rcx, ?g_szPathToFile@@3PAGA; unsigned __int16 *
0x140071dd1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140071dd6  test    eax, eax
0x140071dd8  jns     short loc_140071E42
0x140071dda  xor     eax, eax
0x140071ddc  mov     rcx, [rsp+478h+var_18]
0x140071de4  xor     rcx, rsp; StackCookie
0x140071de7  call    __security_check_cookie
0x140071dec  mov     rbx, [rsp+478h+arg_0]
0x140071df4  add     rsp, 470h
0x140071dfb  pop     rdi
0x140071dfc  retn
0x140071dfd  mov     ecx, 7FFFFFFEh
0x140071e02  lea     rdx, [rsp+478h+Dst]
0x140071e07  lea     rax, ?g_szPathToFile@@3PAGA; ushort near * g_szPathToFile
0x140071e0e  test    rcx, rcx
0x140071e11  jz      short loc_140071E32
0x140071e13  movzx   r8d, word ptr [rdx]
0x140071e17  test    r8w, r8w
0x140071e1b  jz      short loc_140071E32
0x140071e1d  mov     [rax], r8w
0x140071e21  add     rdx, 2
0x140071e25  add     rax, 2
0x140071e29  dec     rcx
0x140071e2c  sub     rbx, 1
0x140071e30  jnz     short loc_140071E0E
0x140071e32  test    rbx, rbx
0x140071e35  lea     rdx, [rax-2]
0x140071e39  cmovnz  rdx, rax
0x140071e3d  mov     [rdx], di
0x140071e40  jz      short loc_140071DDA
0x140071e42  mov     [rsp+478h+var_450], 80h; int
0x140071e4a  lea     rcx, ?g_szPathToFile@@3PAGA; lpFileName
0x140071e51  mov     edx, 40000000h; dwDesiredAccess
0x140071e56  mov     [rsp+478h+var_458], 4; DWORD
0x140071e5e  mov     r8d, 3; dwShareMode
0x140071e64  call    InternalSafeCreateFile
0x140071e69  mov     cs:?g_hLogFile@@3PEAXEA, rax; void * g_hLogFile
0x140071e70  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140071e74  jz      loc_140071DDA
0x140071e7a  mov     r9d, 2; dwMoveMethod
0x140071e80  xor     r8d, r8d; lpDistanceToMoveHigh
0x140071e83  xor     edx, edx; lDistanceToMove
0x140071e85  mov     rcx, rax; hFile
0x140071e88  call    cs:__imp_SetFilePointer
0x140071e8e  cmp     eax, 0FFFFFFFFh
0x140071e91  jnz     short loc_140071EB0
0x140071e93  mov     rcx, cs:?g_hLogFile@@3PEAXEA; hObject
0x140071e9a  call    cs:__imp_CloseHandle
0x140071ea0  mov     cs:?g_hLogFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * g_hLogFile
0x140071eab  jmp     loc_140071DDA
0x140071eb0  mov     eax, 1
0x140071eb5  xchg    eax, cs:?g_iLogFileRefCount@@3JA; long g_iLogFileRefCount
0x140071ebb  jmp     loc_140071D5A
```
