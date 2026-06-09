# MakeUniqueTempDirectory(char const *,char *,ulong)

- ea: `0x14000a798`
- end: `0x14000a9ca`
- name: `?MakeUniqueTempDirectory@@YAJPEBDPEADK@Z`
- size: `562`
- prototype: `__int64 __fastcall(LPCSTR lpTemplateDirectory, char *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400096b4`

## callees

- `0x14000a798`
- `0x14000b3c0`
- `0x14000ba00`
- `0x1400109c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000a932`
- `KERNEL32!CloseHandle` at `0x14000a932`
- `KERNEL32!CreateDirectoryExA` at `0x14000a8a1`
- `KERNEL32!CreateDirectoryExA` at `0x14000a8a1`
- `KERNEL32!GetFileAttributesA` at `0x14000a821`
- `KERNEL32!GetFileAttributesA` at `0x14000a821`
- `KERNEL32!CreateFileA` at `0x14000a8fe`
- `KERNEL32!CreateFileA` at `0x14000a8fe`
- `KERNEL32!LocalFree` at `0x14000a962`
- `KERNEL32!LocalFree` at `0x14000a978`
- `KERNEL32!LocalFree` at `0x14000a962`
- `KERNEL32!LocalFree` at `0x14000a978`
- `KERNEL32!LeaveCriticalSection` at `0x14000a994`
- `KERNEL32!LeaveCriticalSection` at `0x14000a994`
- `KERNEL32!EnterCriticalSection` at `0x14000a7e1`
- `KERNEL32!EnterCriticalSection` at `0x14000a7e1`
- `KERNEL32!GetLastError` at `0x14000a8b7`
- `KERNEL32!GetLastError` at `0x14000a940`
- `KERNEL32!GetLastError` at `0x14000a8b7`
- `KERNEL32!GetLastError` at `0x14000a940`
- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x14000a921`
- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x14000a921`

## pseudocode

```c
__int64 __fastcall MakeUniqueTempDirectory(LPCSTR lpTemplateDirectory, char *a2)
{
  int v4; // edi
  int v5; // ebx
  signed int LastError; // eax
  HANDLE FileA; // rax
  void *v8; // rdi
  signed int v9; // eax
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL v12; // [rsp+48h] [rbp-B8h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+50h] [rbp-B0h] BYREF
  _EXPLICIT_ACCESS_W v14; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v15[40]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v16[80]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v17[80]; // [rsp+1A0h] [rbp+A0h] BYREF

  v4 = 1;
  if ( g_oLock )
    EnterCriticalSection(&CriticalSection);
  while ( 1 )
  {
    v5 = StringCchPrintfA(a2, 0x104u, "%s%s%d.tmp", lpTemplateDirectory, "IDC", v4);
    if ( v5 < 0 )
      break;
    if ( GetFileAttributesA(a2) != -1 && ++v4 <= 500 )
      continue;
    hMem = 0;
    v12 = 0;
    memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
    v5 = SetSecurityAttributes(&SecurityAttributes, &v14, v17, v16, v15, (struct _ACL **)&hMem, &v12);
    if ( v5 >= 0 )
    {
      if ( CreateDirectoryExA(lpTemplateDirectory, a2, &SecurityAttributes) )
        goto LABEL_11;
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
      {
LABEL_11:
        FileA = CreateFileA(a2, 0x1F0000u, 0, 0, 3u, 0x2000000u, 0);
        v8 = FileA;
        if ( FileA == (HANDLE)-1LL )
        {
          v9 = GetLastError();
          v5 = v9;
          if ( v9 > 0 )
            v5 = (unsigned __int16)v9 | 0x80070000;
        }
        else
        {
          v5 = SetWindowsHandleAccess(FileA, 0x1240u, 0x1200A9u);
          CloseHandle(v8);
        }
      }
      if ( hMem )
        LocalFree(hMem);
      if ( v12 )
        LocalFree(v12);
    }
    break;
  }
  if ( g_oLock )
    LeaveCriticalSection(&CriticalSection);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000a798  mov     [rsp-8+arg_10], rbx
0x14000a79d  mov     [rsp-8+arg_18], rsi
0x14000a7a2  push    rbp
0x14000a7a3  push    rdi
0x14000a7a4  push    r14
0x14000a7a6  lea     rbp, [rsp-100h]
0x14000a7ae  sub     rsp, 200h
0x14000a7b5  mov     rax, cs:__security_cookie
0x14000a7bc  xor     rax, rsp
0x14000a7bf  mov     [rbp+110h+var_20], rax
0x14000a7c6  cmp     cs:?g_oLock@@3VCLock@@A, 0; CLock g_oLock
0x14000a7cd  mov     rsi, rdx
0x14000a7d0  mov     r14, rcx
0x14000a7d3  mov     edi, 1
0x14000a7d8  jz      short loc_14000A7ED
0x14000a7da  lea     rcx, CriticalSection; lpCriticalSection
0x14000a7e1  call    cs:__imp_EnterCriticalSection
0x14000a7e8  nop     dword ptr [rax+rax+00h]
0x14000a7ed  lea     rax, aIdc_0; "IDC"
0x14000a7f4  mov     [rsp+210h+dwFlagsAndAttributes], edi
0x14000a7f8  mov     r9, r14
0x14000a7fb  mov     qword ptr [rsp+210h+dwCreationDisposition], rax
0x14000a800  lea     r8, aSSDTmp; "%s%s%d.tmp"
0x14000a807  mov     edx, 104h; unsigned __int64
0x14000a80c  mov     rcx, rsi; char *
0x14000a80f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x14000a814  mov     ebx, eax
0x14000a816  test    eax, eax
0x14000a818  js      loc_14000A984
0x14000a81e  mov     rcx, rsi; lpFileName
0x14000a821  call    cs:__imp_GetFileAttributesA
0x14000a828  nop     dword ptr [rax+rax+00h]
0x14000a82d  cmp     eax, 0FFFFFFFFh
0x14000a830  jz      short loc_14000A83C
0x14000a832  inc     edi
0x14000a834  cmp     edi, 1F4h
0x14000a83a  jle     short loc_14000A7ED
0x14000a83c  xor     eax, eax
0x14000a83e  lea     r9, [rbp+110h+var_C0]; void *
0x14000a842  mov     qword ptr [rsp+210h+SecurityAttributes.bInheritHandle], rax
0x14000a847  lea     r8, [rbp+110h+var_70]; void *
0x14000a84e  mov     [rsp+210h+hMem], rax
0x14000a853  lea     rdx, [rsp+210h+var_1A0]; struct _EXPLICIT_ACCESS_W *
0x14000a858  mov     [rsp+210h+var_1C8], rax
0x14000a85d  lea     rcx, [rsp+210h+SecurityAttributes]; struct _SECURITY_ATTRIBUTES *
0x14000a862  lea     rax, [rsp+210h+var_1C8]
0x14000a867  xorps   xmm0, xmm0
0x14000a86a  mov     [rsp+210h+hTemplateFile], rax; void **
0x14000a86f  lea     rax, [rsp+210h+hMem]
0x14000a874  mov     qword ptr [rsp+210h+dwFlagsAndAttributes], rax; struct _ACL **
0x14000a879  lea     rax, [rbp+110h+var_110]
0x14000a87d  mov     qword ptr [rsp+210h+dwCreationDisposition], rax; void *
0x14000a882  movups  xmmword ptr [rsp+210h+SecurityAttributes.nLength], xmm0
0x14000a887  call    ?SetSecurityAttributes@@YAJPEAU_SECURITY_ATTRIBUTES@@QEAU_EXPLICIT_ACCESS_W@@PEAX22PEAPEAU_ACL@@PEAPEAX@Z; SetSecurityAttributes(_SECURITY_ATTRIBUTES *,_EXPLICIT_ACCESS_W * const,void *,void *,void *,_ACL * *,void * *)
0x14000a88c  mov     ebx, eax
0x14000a88e  test    eax, eax
0x14000a890  js      loc_14000A984
0x14000a896  lea     r8, [rsp+210h+SecurityAttributes]; lpSecurityAttributes
0x14000a89b  mov     rdx, rsi; lpNewDirectory
0x14000a89e  mov     rcx, r14; lpTemplateDirectory
0x14000a8a1  call    cs:__imp_CreateDirectoryExA
0x14000a8a8  nop     dword ptr [rax+rax+00h]
0x14000a8ad  mov     r14d, 80070000h
0x14000a8b3  test    eax, eax
0x14000a8b5  jnz     short loc_14000A8D7
0x14000a8b7  call    cs:__imp_GetLastError
0x14000a8be  nop     dword ptr [rax+rax+00h]
0x14000a8c3  mov     ebx, eax
0x14000a8c5  test    eax, eax
0x14000a8c7  jle     short loc_14000A8CF
0x14000a8c9  movzx   ebx, ax
0x14000a8cc  or      ebx, r14d
0x14000a8cf  test    ebx, ebx
0x14000a8d1  js      loc_14000A958
0x14000a8d7  mov     [rsp+210h+hTemplateFile], 0; hTemplateFile
0x14000a8e0  xor     r9d, r9d; lpSecurityAttributes
0x14000a8e3  mov     [rsp+210h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x14000a8eb  xor     r8d, r8d; dwShareMode
0x14000a8ee  mov     edx, 1F0000h; dwDesiredAccess
0x14000a8f3  mov     [rsp+210h+dwCreationDisposition], 3; dwCreationDisposition
0x14000a8fb  mov     rcx, rsi; lpFileName
0x14000a8fe  call    cs:__imp_CreateFileA
0x14000a905  nop     dword ptr [rax+rax+00h]
0x14000a90a  mov     rdi, rax
0x14000a90d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000a911  jz      short loc_14000A940
0x14000a913  mov     edx, 1240h
0x14000a918  mov     r8d, 1200A9h
0x14000a91e  mov     rcx, rax
0x14000a921  call    cs:__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z; SetWindowsHandleAccess(void *,ulong,ulong)
0x14000a928  nop     dword ptr [rax+rax+00h]
0x14000a92d  mov     rcx, rdi; hObject
0x14000a930  mov     ebx, eax
0x14000a932  call    cs:__imp_CloseHandle
0x14000a939  nop     dword ptr [rax+rax+00h]
0x14000a93e  jmp     short loc_14000A958
0x14000a940  call    cs:__imp_GetLastError
0x14000a947  nop     dword ptr [rax+rax+00h]
0x14000a94c  mov     ebx, eax
0x14000a94e  test    eax, eax
0x14000a950  jle     short loc_14000A958
0x14000a952  movzx   ebx, ax
0x14000a955  or      ebx, r14d
0x14000a958  mov     rcx, [rsp+210h+hMem]; hMem
0x14000a95d  test    rcx, rcx
0x14000a960  jz      short loc_14000A96E
0x14000a962  call    cs:__imp_LocalFree
0x14000a969  nop     dword ptr [rax+rax+00h]
0x14000a96e  mov     rcx, [rsp+210h+var_1C8]; hMem
0x14000a973  test    rcx, rcx
0x14000a976  jz      short loc_14000A984
0x14000a978  call    cs:__imp_LocalFree
0x14000a97f  nop     dword ptr [rax+rax+00h]
0x14000a984  cmp     cs:?g_oLock@@3VCLock@@A, 0; CLock g_oLock
0x14000a98b  jz      short loc_14000A9A0
0x14000a98d  lea     rcx, CriticalSection; lpCriticalSection
0x14000a994  call    cs:__imp_LeaveCriticalSection
0x14000a99b  nop     dword ptr [rax+rax+00h]
0x14000a9a0  mov     eax, ebx
0x14000a9a2  mov     rcx, [rbp+110h+var_20]
0x14000a9a9  xor     rcx, rsp; StackCookie
0x14000a9ac  call    __security_check_cookie
0x14000a9b1  lea     r11, [rsp+210h+var_10]
0x14000a9b9  mov     rbx, [r11+30h]
0x14000a9bd  mov     rsi, [r11+38h]
0x14000a9c1  mov     rsp, r11
0x14000a9c4  pop     r14
0x14000a9c6  pop     rdi
0x14000a9c7  pop     rbp
0x14000a9c8  retn
```
