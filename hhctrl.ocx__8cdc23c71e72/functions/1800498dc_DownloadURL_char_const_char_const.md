# DownloadURL(char const *,char const *)

- ea: `0x1800498dc`
- end: `0x180049bc3`
- name: `?DownloadURL@@YAJPEBD0@Z`
- size: `743`
- prototype: `__int64 __fastcall(const char *Source, LPCSTR lpFileName)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18004af3c`
- `0x18004c040`

## callees

- `0x1800498dc`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `msvcrt!mbstowcs` at `0x180049967`
- `msvcrt!mbstowcs` at `0x180049967`
- `KERNEL32!CloseHandle` at `0x180049b21`
- `KERNEL32!CloseHandle` at `0x180049b49`
- `KERNEL32!CloseHandle` at `0x180049b21`
- `KERNEL32!CloseHandle` at `0x180049b49`
- `KERNEL32!CreateFileA` at `0x180049a9d`
- `KERNEL32!CreateFileA` at `0x180049a9d`
- `KERNEL32!WriteFile` at `0x180049b06`
- `KERNEL32!WriteFile` at `0x180049b06`
- `ole32!CoCreateInstance` at `0x180049990`
- `ole32!CoCreateInstance` at `0x180049990`
- `ole32!CreateBindCtx` at `0x180049924`
- `ole32!CreateBindCtx` at `0x180049924`

## pseudocode

```c
__int64 __fastcall DownloadURL(const char *Source, LPCSTR lpFileName)
{
  HRESULT v4; // ebx
  LPBC v5; // rcx
  __int64 v6; // rax
  HANDLE v7; // rdi
  LPBC ppbc; // [rsp+40h] [rbp-C0h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+48h] [rbp-B8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+4Ch] [rbp-B4h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v13; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v14; // [rsp+60h] [rbp-A0h] BYREF
  int v15; // [rsp+68h] [rbp-98h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+70h] [rbp-90h] BYREF
  wchar_t Dest[264]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE Buffer[1024]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v13 = 0;
  ppbc = 0;
  v4 = CreateBindCtx(0, &ppbc);
  if ( v4 < 0 )
    goto LABEL_26;
  v5 = ppbc;
  if ( !ppbc )
    goto LABEL_26;
  v6 = -1;
  do
    ++v6;
  while ( Source[v6] );
  if ( (unsigned __int64)(v6 + 1) > 0x104 )
  {
LABEL_25:
    ((void (__fastcall *)(LPBC))v5->lpVtbl->Release)(v5);
    goto LABEL_26;
  }
  mbstowcs(Dest, Source, v6 + 1);
  ppv = 0;
  v4 = CoCreateInstance(&CLSID_PARSE_URL, 0, 1u, &IID_IParseDisplayName, &ppv);
  if ( v4 < 0 || !ppv )
  {
LABEL_24:
    v5 = ppbc;
    goto LABEL_25;
  }
  v15 = 0;
  v14 = 0;
  v4 = (*(__int64 (__fastcall **)(LPVOID, LPBC, wchar_t *, int *, __int64 *))(*(_QWORD *)ppv + 24LL))(
         ppv,
         ppbc,
         Dest,
         &v15,
         &v14);
  if ( v4 < 0 || !v14 )
  {
LABEL_23:
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    goto LABEL_24;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, LPBC, _QWORD, GUID *, __int64 *))(*(_QWORD *)v14 + 72LL))(
         v14,
         ppbc,
         0,
         &IID_IStream,
         &v13);
  if ( v4 < 0 || !v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    goto LABEL_23;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  SecurityAttributes.lpSecurityDescriptor = 0;
  nNumberOfBytesToWrite = 0;
  v7 = CreateFileA(lpFileName, 0x40000000u, 0, &SecurityAttributes, 2u, 0x80u, 0);
  if ( v7 == (HANDLE)-1LL )
  {
    v4 = -2147467259;
LABEL_21:
    CloseHandle(v7);
    goto LABEL_26;
  }
  while ( 1 )
  {
    NumberOfBytesWritten = 0;
    Buffer[0] = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64, DWORD *))(*(_QWORD *)v13 + 24LL))(
           v13,
           Buffer,
           1024,
           &nNumberOfBytesToWrite);
    if ( v4 < 0 )
      break;
    if ( !WriteFile(v7, Buffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0)
      || nNumberOfBytesToWrite != NumberOfBytesWritten )
    {
      v4 = -2147467259;
      break;
    }
    if ( nNumberOfBytesToWrite != 1024 )
    {
      CloseHandle(v7);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      return 0;
    }
  }
  if ( v7 )
    goto LABEL_21;
LABEL_26:
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800498dc  mov     [rsp-8+arg_10], rbx
0x1800498e1  mov     [rsp-8+arg_18], rsi
0x1800498e6  push    rbp
0x1800498e7  push    rdi
0x1800498e8  push    r14
0x1800498ea  lea     rbp, [rsp-5B0h]
0x1800498f2  sub     rsp, 6B0h
0x1800498f9  mov     rax, cs:__security_cookie
0x180049900  xor     rax, rsp
0x180049903  mov     [rbp+5C0h+var_20], rax
0x18004990a  mov     rsi, rdx
0x18004990d  mov     rdi, rcx
0x180049910  xor     r14d, r14d
0x180049913  lea     rdx, [rsp+6C0h+ppbc]; ppbc
0x180049918  xor     ecx, ecx; reserved
0x18004991a  mov     [rsp+6C0h+var_668], r14
0x18004991f  mov     [rsp+6C0h+ppbc], r14
0x180049924  call    cs:__imp_CreateBindCtx
0x18004992a  mov     ebx, eax
0x18004992c  test    eax, eax
0x18004992e  js      loc_180049B84
0x180049934  mov     rcx, [rsp+6C0h+ppbc]
0x180049939  test    rcx, rcx
0x18004993c  jz      loc_180049B84
0x180049942  or      rax, 0FFFFFFFFFFFFFFFFh
0x180049946  inc     rax
0x180049949  cmp     [rdi+rax], r14b
0x18004994d  jnz     short loc_180049946
0x18004994f  lea     r8, [rax+1]; MaxCount
0x180049953  cmp     r8, 104h
0x18004995a  ja      loc_180049B78
0x180049960  mov     rdx, rdi; Source
0x180049963  lea     rcx, [rbp+5C0h+Dest]; Dest
0x180049967  call    cs:__imp_mbstowcs
0x18004996d  xor     edx, edx; pUnkOuter
0x18004996f  mov     [rsp+6C0h+var_670], r14
0x180049974  lea     rax, [rsp+6C0h+var_670]
0x180049979  lea     r9, IID_IParseDisplayName; riid
0x180049980  mov     [rsp+6C0h+ppv], rax; ppv
0x180049985  lea     rcx, CLSID_PARSE_URL; rclsid
0x18004998c  lea     r8d, [rdx+1]; dwClsContext
0x180049990  call    cs:__imp_CoCreateInstance
0x180049996  mov     ebx, eax
0x180049998  test    eax, eax
0x18004999a  js      loc_180049B73
0x1800499a0  mov     rcx, [rsp+6C0h+var_670]
0x1800499a5  test    rcx, rcx
0x1800499a8  jz      loc_180049B73
0x1800499ae  mov     [rsp+6C0h+var_658], r14d
0x1800499b3  lea     rdx, [rsp+6C0h+var_660]
0x1800499b8  mov     [rsp+6C0h+var_660], r14
0x1800499bd  lea     r9, [rsp+6C0h+var_658]
0x1800499c2  mov     rax, [rcx]
0x1800499c5  lea     r8, [rbp+5C0h+Dest]
0x1800499c9  mov     [rsp+6C0h+ppv], rdx
0x1800499ce  mov     rdx, [rsp+6C0h+ppbc]
0x1800499d3  mov     rax, [rax+18h]
0x1800499d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800499dc  mov     ebx, eax
0x1800499de  test    eax, eax
0x1800499e0  js      loc_180049B62
0x1800499e6  mov     rcx, [rsp+6C0h+var_660]
0x1800499eb  test    rcx, rcx
0x1800499ee  jz      loc_180049B62
0x1800499f4  mov     rax, [rcx]
0x1800499f7  lea     rdx, [rsp+6C0h+var_668]
0x1800499fc  mov     [rsp+6C0h+ppv], rdx
0x180049a01  lea     r9, IID_IStream
0x180049a08  mov     rdx, [rsp+6C0h+ppbc]
0x180049a0d  xor     r8d, r8d
0x180049a10  mov     rax, [rax+48h]
0x180049a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a19  mov     ebx, eax
0x180049a1b  test    eax, eax
0x180049a1d  js      loc_180049B51
0x180049a23  cmp     [rsp+6C0h+var_668], r14
0x180049a28  jz      loc_180049B51
0x180049a2e  mov     rcx, [rsp+6C0h+var_660]
0x180049a33  mov     rax, [rcx]
0x180049a36  mov     rax, [rax+10h]
0x180049a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a3f  mov     rcx, [rsp+6C0h+var_670]
0x180049a44  mov     rax, [rcx]
0x180049a47  mov     rax, [rax+10h]
0x180049a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a50  mov     rcx, [rsp+6C0h+ppbc]
0x180049a55  mov     rax, [rcx]
0x180049a58  mov     rax, [rax+10h]
0x180049a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a61  mov     [rsp+6C0h+hTemplateFile], r14; hTemplateFile
0x180049a66  lea     r9, [rsp+6C0h+SecurityAttributes]; lpSecurityAttributes
0x180049a6b  mov     [rsp+6C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180049a73  xor     r8d, r8d; dwShareMode
0x180049a76  mov     edx, 40000000h; dwDesiredAccess
0x180049a7b  mov     dword ptr [rsp+6C0h+ppv], 2; dwCreationDisposition
0x180049a83  mov     rcx, rsi; lpFileName
0x180049a86  mov     qword ptr [rsp+6C0h+SecurityAttributes.nLength], 18h
0x180049a8f  mov     qword ptr [rbp+5C0h+SecurityAttributes.bInheritHandle], r14
0x180049a93  mov     [rsp+6C0h+SecurityAttributes.lpSecurityDescriptor], r14
0x180049a98  mov     [rsp+6C0h+nNumberOfBytesToWrite], r14d
0x180049a9d  call    cs:__imp_CreateFileA
0x180049aa3  mov     rdi, rax
0x180049aa6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180049aaa  jnz     short loc_180049AB6
0x180049aac  mov     ebx, 80004005h
0x180049ab1  jmp     loc_180049B46
0x180049ab6  mov     esi, 400h
0x180049abb  mov     rcx, [rsp+6C0h+var_668]
0x180049ac0  lea     r9, [rsp+6C0h+nNumberOfBytesToWrite]
0x180049ac5  mov     [rsp+6C0h+NumberOfBytesWritten], r14d
0x180049aca  lea     rdx, [rbp+5C0h+Buffer]
0x180049ad1  mov     [rbp+5C0h+Buffer], r14b
0x180049ad8  mov     r8d, esi
0x180049adb  mov     rax, [rcx]
0x180049ade  mov     rax, [rax+18h]
0x180049ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ae7  mov     ebx, eax
0x180049ae9  test    eax, eax
0x180049aeb  js      short loc_180049B41
0x180049aed  mov     r8d, [rsp+6C0h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180049af2  lea     r9, [rsp+6C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180049af7  lea     rdx, [rbp+5C0h+Buffer]; lpBuffer
0x180049afe  mov     [rsp+6C0h+ppv], r14; lpOverlapped
0x180049b03  mov     rcx, rdi; hFile
0x180049b06  call    cs:__imp_WriteFile
0x180049b0c  test    eax, eax
0x180049b0e  jz      short loc_180049B3C
0x180049b10  mov     eax, [rsp+6C0h+nNumberOfBytesToWrite]
0x180049b14  cmp     eax, [rsp+6C0h+NumberOfBytesWritten]
0x180049b18  jnz     short loc_180049B3C
0x180049b1a  cmp     eax, esi
0x180049b1c  jz      short loc_180049ABB
0x180049b1e  mov     rcx, rdi; hObject
0x180049b21  call    cs:__imp_CloseHandle
0x180049b27  mov     rcx, [rsp+6C0h+var_668]
0x180049b2c  mov     rax, [rcx]
0x180049b2f  mov     rax, [rax+10h]
0x180049b33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b38  xor     eax, eax
0x180049b3a  jmp     short loc_180049B9C
0x180049b3c  mov     ebx, 80004005h
0x180049b41  test    rdi, rdi
0x180049b44  jz      short loc_180049B84
0x180049b46  mov     rcx, rdi; hObject
0x180049b49  call    cs:__imp_CloseHandle
0x180049b4f  jmp     short loc_180049B84
0x180049b51  mov     rcx, [rsp+6C0h+var_660]
0x180049b56  mov     rax, [rcx]
0x180049b59  mov     rax, [rax+10h]
0x180049b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b62  mov     rcx, [rsp+6C0h+var_670]
0x180049b67  mov     rax, [rcx]
0x180049b6a  mov     rax, [rax+10h]
0x180049b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b73  mov     rcx, [rsp+6C0h+ppbc]
0x180049b78  mov     rax, [rcx]
0x180049b7b  mov     rax, [rax+10h]
0x180049b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b84  mov     rcx, [rsp+6C0h+var_668]
0x180049b89  test    rcx, rcx
0x180049b8c  jz      short loc_180049B9A
0x180049b8e  mov     rax, [rcx]
0x180049b91  mov     rax, [rax+10h]
0x180049b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b9a  mov     eax, ebx
0x180049b9c  mov     rcx, [rbp+5C0h+var_20]
0x180049ba3  xor     rcx, rsp; StackCookie
0x180049ba6  call    __security_check_cookie
0x180049bab  lea     r11, [rsp+6C0h+var_10]
0x180049bb3  mov     rbx, [r11+30h]
0x180049bb7  mov     rsi, [r11+38h]
0x180049bbb  mov     rsp, r11
0x180049bbe  pop     r14
0x180049bc0  pop     rdi
0x180049bc1  pop     rbp
0x180049bc2  retn
```
