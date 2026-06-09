# MsoFOpenCreateFileMappingEx(void * *,void *,ulong,ulong,ulong,char const *,char *,int,int *,_SECURITY_ATTRIBUTES *,ulong)

- ea: `0x180121d78`
- end: `0x180121ee7`
- name: `?MsoFOpenCreateFileMappingEx@@YAHPEAPEAXPEAXKKKPEBDPEADHPEAHPEAU_SECURITY_ATTRIBUTES@@K@Z`
- size: `367`
- prototype: `__int64 __fastcall(void **, void *, unsigned int, unsigned int, DWORD, const char *, char *, int, int *, struct _SECURITY_ATTRIBUTES *, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x18010f3d4`
- `0x180112708`
- `0x180112a28`

## callees

- `0x180004198`
- `0x18003e690`
- `0x180121d78`
- `0x180123210`
- `0x1801234bc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180121e61`
- `KERNEL32!GetLastError` at `0x180121e61`
- `KERNEL32!OpenFileMappingA` at `0x180121e15`
- `KERNEL32!OpenFileMappingA` at `0x180121e15`
- `KERNEL32!CreateFileMappingA` at `0x180121e58`
- `KERNEL32!CreateFileMappingA` at `0x180121e58`

## pseudocode

```c
_BOOL8 __fastcall MsoFOpenCreateFileMappingEx(
        void **a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        DWORD dwMaximumSizeLow,
        char *a6,
        char *a7,
        int a8,
        int *a9,
        struct _SECURITY_ATTRIBUTES *a10,
        unsigned int a11)
{
  int v13; // edi
  char v14; // r12
  const CHAR *lpName; // r15
  __int64 v16; // rax
  DWORD LastError; // ebp
  int v18; // r8d
  int v19; // ecx
  LPSECURITY_ATTRIBUTES lpFileMappingAttributes[2]; // [rsp+30h] [rbp-448h] BYREF
  char Destination[1024]; // [rsp+40h] [rbp-438h] BYREF

  lpFileMappingAttributes[0] = 0;
  if ( !a1 )
    return 0;
  v13 = 0;
  v14 = 0;
  *a1 = 0;
  lpName = MsoSzCreateNamedObjectNameSz(Destination, (unsigned int)a2, a6, a11, 4);
  while ( 1 )
  {
    if ( lpName )
      *a1 = OpenFileMappingA(0x2001Fu, (a11 >> 23) & 1, lpName);
    v16 = (__int64)*a1;
    if ( *a1 )
      break;
    LastError = 0;
    if ( !(unsigned int)MsoFMNOResolveSecurity(a11, lpFileMappingAttributes, 4u)
      || (*a1 = CreateFileMappingA(
                  (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                  lpFileMappingAttributes[0],
                  0x8000004u,
                  0,
                  dwMaximumSizeLow,
                  lpName),
          LastError = GetLastError(),
          MsoMNOReleaseSecurity(a11, lpFileMappingAttributes, v18),
          LastError != 5)
      || v14 )
    {
      v16 = (__int64)*a1;
      if ( *a1 && LastError != 183 )
        v13 = 1;
      break;
    }
    v14 = 1;
  }
  v19 = 0;
  if ( v16 )
    v19 = v13;
  if ( a9 )
    *a9 = v19;
  return v16 != 0;
}

```

## disassembly

```asm
0x180121d78  mov     [rsp+arg_8], rbx
0x180121d7d  mov     [rsp+arg_10], rbp
0x180121d82  mov     [rsp+arg_18], rsi
0x180121d87  push    rdi
0x180121d88  push    r12
0x180121d8a  push    r13
0x180121d8c  push    r14
0x180121d8e  push    r15
0x180121d90  sub     rsp, 450h
0x180121d97  mov     rax, cs:__security_cookie
0x180121d9e  xor     rax, rsp
0x180121da1  mov     [rsp+478h+var_38], rax
0x180121da9  mov     rbx, rcx
0x180121dac  mov     r13d, [rsp+478h+arg_20]
0x180121db4  mov     r8, [rsp+478h+arg_28]; char *
0x180121dbc  mov     r14, [rsp+478h+arg_40]
0x180121dc4  mov     esi, [rsp+478h+arg_50]
0x180121dcb  mov     [rsp+478h+lpFileMappingAttributes], 0
0x180121dd4  test    rcx, rcx
0x180121dd7  jnz     short loc_180121DE0
0x180121dd9  xor     eax, eax
0x180121ddb  jmp     loc_180121EB6
0x180121de0  xor     edi, edi
0x180121de2  xor     r12b, r12b
0x180121de5  mov     [rcx], rdi
0x180121de8  mov     [rsp+478h+dwMaximumSizeLow], 4; int
0x180121df0  mov     r9d, esi; unsigned int
0x180121df3  lea     rcx, [rsp+478h+Destination]; Destination
0x180121df8  call    ?MsoSzCreateNamedObjectNameSz@@YAPEADPEADKPEBDKH@Z; MsoSzCreateNamedObjectNameSz(char *,ulong,char const *,ulong,int)
0x180121dfd  mov     r15, rax
0x180121e00  test    r15, r15
0x180121e03  jz      short loc_180121E1E
0x180121e05  mov     edx, esi
0x180121e07  shr     edx, 17h
0x180121e0a  and     edx, 1; bInheritHandle
0x180121e0d  mov     r8, r15; lpName
0x180121e10  mov     ecx, 2001Fh; dwDesiredAccess
0x180121e15  call    cs:__imp_OpenFileMappingA
0x180121e1b  mov     [rbx], rax
0x180121e1e  mov     rax, [rbx]
0x180121e21  test    rax, rax
0x180121e24  jnz     short loc_180121E9C
0x180121e26  xor     ebp, ebp
0x180121e28  lea     r8d, [rax+4]; int
0x180121e2c  lea     rdx, [rsp+478h+lpFileMappingAttributes]; struct _SECURITY_ATTRIBUTES **
0x180121e31  mov     ecx, esi; unsigned int
0x180121e33  call    ?MsoFMNOResolveSecurity@@YAHKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z; MsoFMNOResolveSecurity(ulong,_SECURITY_ATTRIBUTES * *,int)
0x180121e38  test    eax, eax
0x180121e3a  jz      short loc_180121E87
0x180121e3c  mov     [rsp+478h+lpName], r15; lpName
0x180121e41  mov     [rsp+478h+dwMaximumSizeLow], r13d; dwMaximumSizeLow
0x180121e46  xor     r9d, r9d; dwMaximumSizeHigh
0x180121e49  mov     r8d, 8000004h; flProtect
0x180121e4f  mov     rdx, [rsp+478h+lpFileMappingAttributes]; lpFileMappingAttributes
0x180121e54  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180121e58  call    cs:__imp_CreateFileMappingA
0x180121e5e  mov     [rbx], rax
0x180121e61  call    cs:__imp_GetLastError
0x180121e67  mov     ebp, eax
0x180121e69  lea     rdx, [rsp+478h+lpFileMappingAttributes]; struct _SECURITY_ATTRIBUTES **
0x180121e6e  mov     ecx, esi; unsigned int
0x180121e70  call    ?MsoMNOReleaseSecurity@@YAXKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z; MsoMNOReleaseSecurity(ulong,_SECURITY_ATTRIBUTES * *,int)
0x180121e75  cmp     ebp, 5
0x180121e78  jnz     short loc_180121E87
0x180121e7a  test    r12b, r12b
0x180121e7d  jnz     short loc_180121E87
0x180121e7f  mov     r12b, 1
0x180121e82  jmp     loc_180121E00
0x180121e87  mov     rax, [rbx]
0x180121e8a  test    rax, rax
0x180121e8d  jz      short loc_180121E9C
0x180121e8f  cmp     ebp, 0B7h
0x180121e95  jz      short loc_180121E9C
0x180121e97  mov     edi, 1
0x180121e9c  xor     edx, edx
0x180121e9e  test    rax, rax
0x180121ea1  setnz   dl
0x180121ea4  xor     ecx, ecx
0x180121ea6  test    rax, rax
0x180121ea9  cmovnz  ecx, edi
0x180121eac  test    r14, r14
0x180121eaf  jz      short loc_180121EB4
0x180121eb1  mov     [r14], ecx
0x180121eb4  mov     eax, edx
0x180121eb6  mov     rcx, [rsp+478h+var_38]
0x180121ebe  xor     rcx, rsp; StackCookie
0x180121ec1  call    __security_check_cookie
0x180121ec6  lea     r11, [rsp+478h+var_28]
0x180121ece  mov     rbx, [r11+38h]
0x180121ed2  mov     rbp, [r11+40h]
0x180121ed6  mov     rsi, [r11+48h]
0x180121eda  mov     rsp, r11
0x180121edd  pop     r15
0x180121edf  pop     r14
0x180121ee1  pop     r13
0x180121ee3  pop     r12
0x180121ee5  pop     rdi
0x180121ee6  retn
```
