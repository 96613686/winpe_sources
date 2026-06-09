# MsoFOpenCreateMutexEx(void * *,char const *,char *,int,int *,_SECURITY_ATTRIBUTES *,ulong)

- ea: `0x180121ee8`
- end: `0x18012202e`
- name: `?MsoFOpenCreateMutexEx@@YAHPEAPEAXPEBDPEADHPEAHPEAU_SECURITY_ATTRIBUTES@@K@Z`
- size: `326`
- prototype: `int(void **, const char *, char *, int, int *, struct _SECURITY_ATTRIBUTES *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180112914`

## callees

- `0x180004198`
- `0x1800264b4`
- `0x18003e690`
- `0x180121ee8`
- `0x180123210`
- `0x1801234bc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180121fb7`
- `KERNEL32!GetLastError` at `0x180121fb7`
- `KERNEL32!OpenMutexA` at `0x180121f76`
- `KERNEL32!OpenMutexA` at `0x180121f76`
- `KERNEL32!CreateMutexA` at `0x180121fae`
- `KERNEL32!CreateMutexA` at `0x180121fae`

## pseudocode

```c
__int64 __fastcall MsoFOpenCreateMutexEx(
        void **a1,
        const char *a2,
        char *a3,
        __int64 a4,
        int *a5,
        struct _SECURITY_ATTRIBUTES *a6,
        unsigned int a7)
{
  unsigned int v9; // edi
  const CHAR *NamedObjectNameSz; // r15
  char v11; // r12
  unsigned int v12; // r14d
  __int64 v13; // rax
  DWORD LastError; // ebx
  int v15; // r8d
  LPSECURITY_ATTRIBUTES lpMutexAttributes[4]; // [rsp+30h] [rbp-458h] BYREF
  char Destination[1024]; // [rsp+50h] [rbp-438h] BYREF

  lpMutexAttributes[0] = 0;
  if ( !a1 )
    return 0;
  *a1 = 0;
  v9 = 1;
  NamedObjectNameSz = MsoSzCreateNamedObjectNameSz(Destination, (unsigned int)a2, a2, a7, 1);
  v11 = 0;
  v12 = a7 & 0x4000000;
  while ( 1 )
  {
    if ( NamedObjectNameSz )
      *a1 = OpenMutexA(0x120001u, (a7 >> 23) & 1, NamedObjectNameSz);
    v13 = (__int64)*a1;
    if ( *a1 )
      break;
    if ( v12 )
      goto LABEL_13;
    if ( !(unsigned int)MsoFMNOResolveSecurity(a7, lpMutexAttributes, 1u)
      || (*a1 = CreateMutexA(lpMutexAttributes[0], (a7 >> 25) & 1, NamedObjectNameSz),
          LastError = GetLastError(),
          MsoMNOReleaseSecurity(a7, lpMutexAttributes, v15),
          LastError != 5)
      || v11 )
    {
      v13 = (__int64)*a1;
LABEL_13:
      if ( !v13 )
        goto LABEL_15;
      break;
    }
    v11 = 1;
  }
  if ( v13 != -1 )
    return v9;
LABEL_15:
  if ( !v12 )
    MsoShipAssertTagProc(1454561);
  *a1 = 0;
  return 0;
}

```

## disassembly

```asm
0x180121ee8  mov     [rsp+arg_10], rbx
0x180121eed  mov     [rsp+arg_18], rbp
0x180121ef2  push    rsi
0x180121ef3  push    rdi
0x180121ef4  push    r12
0x180121ef6  push    r14
0x180121ef8  push    r15
0x180121efa  sub     rsp, 460h
0x180121f01  mov     rax, cs:__security_cookie
0x180121f08  xor     rax, rsp
0x180121f0b  mov     [rsp+488h+var_38], rax
0x180121f13  mov     rsi, rcx
0x180121f16  mov     ebp, [rsp+488h+arg_30]
0x180121f1d  mov     [rsp+488h+lpMutexAttributes], 0
0x180121f26  test    rcx, rcx
0x180121f29  jnz     short loc_180121F32
0x180121f2b  xor     eax, eax
0x180121f2d  jmp     loc_180122002
0x180121f32  mov     qword ptr [rcx], 0
0x180121f39  mov     edi, 1
0x180121f3e  mov     [rsp+488h+var_468], edi; int
0x180121f42  mov     r9d, ebp; unsigned int
0x180121f45  mov     r8, rdx; char *
0x180121f48  lea     rcx, [rsp+488h+Destination]; Destination
0x180121f4d  call    ?MsoSzCreateNamedObjectNameSz@@YAPEADPEADKPEBDKH@Z; MsoSzCreateNamedObjectNameSz(char *,ulong,char const *,ulong,int)
0x180121f52  mov     r15, rax
0x180121f55  xor     r12b, r12b
0x180121f58  mov     r14d, ebp
0x180121f5b  and     r14d, 4000000h
0x180121f62  test    r15, r15
0x180121f65  jz      short loc_180121F7F
0x180121f67  mov     edx, ebp
0x180121f69  shr     edx, 17h
0x180121f6c  and     edx, edi; bInheritHandle
0x180121f6e  mov     r8, r15; lpName
0x180121f71  mov     ecx, 120001h; dwDesiredAccess
0x180121f76  call    cs:__imp_OpenMutexA
0x180121f7c  mov     [rsi], rax
0x180121f7f  mov     rax, [rsi]
0x180121f82  test    rax, rax
0x180121f85  jnz     short loc_180121FE2
0x180121f87  test    r14d, r14d
0x180121f8a  jnz     short loc_180121FDD
0x180121f8c  mov     r8d, edi; int
0x180121f8f  lea     rdx, [rsp+488h+lpMutexAttributes]; struct _SECURITY_ATTRIBUTES **
0x180121f94  mov     ecx, ebp; unsigned int
0x180121f96  call    ?MsoFMNOResolveSecurity@@YAHKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z; MsoFMNOResolveSecurity(ulong,_SECURITY_ATTRIBUTES * *,int)
0x180121f9b  test    eax, eax
0x180121f9d  jz      short loc_180121FDA
0x180121f9f  mov     edx, ebp
0x180121fa1  shr     edx, 19h
0x180121fa4  and     edx, edi; bInitialOwner
0x180121fa6  mov     r8, r15; lpName
0x180121fa9  mov     rcx, [rsp+488h+lpMutexAttributes]; lpMutexAttributes
0x180121fae  call    cs:__imp_CreateMutexA
0x180121fb4  mov     [rsi], rax
0x180121fb7  call    cs:__imp_GetLastError
0x180121fbd  mov     ebx, eax
0x180121fbf  lea     rdx, [rsp+488h+lpMutexAttributes]; struct _SECURITY_ATTRIBUTES **
0x180121fc4  mov     ecx, ebp; unsigned int
0x180121fc6  call    ?MsoMNOReleaseSecurity@@YAXKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z; MsoMNOReleaseSecurity(ulong,_SECURITY_ATTRIBUTES * *,int)
0x180121fcb  cmp     ebx, 5
0x180121fce  jnz     short loc_180121FDA
0x180121fd0  test    r12b, r12b
0x180121fd3  jnz     short loc_180121FDA
0x180121fd5  mov     r12b, dil
0x180121fd8  jmp     short loc_180121F62
0x180121fda  mov     rax, [rsi]
0x180121fdd  test    rax, rax
0x180121fe0  jz      short loc_180121FE8
0x180121fe2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180121fe6  jnz     short loc_180122000
0x180121fe8  test    r14d, r14d
0x180121feb  jnz     short loc_180121FF7
0x180121fed  mov     ecx, 1631E1h
0x180121ff2  call    MsoShipAssertTagProc
0x180121ff7  mov     qword ptr [rsi], 0
0x180121ffe  xor     edi, edi
0x180122000  mov     eax, edi
0x180122002  mov     rcx, [rsp+488h+var_38]
0x18012200a  xor     rcx, rsp; StackCookie
0x18012200d  call    __security_check_cookie
0x180122012  lea     r11, [rsp+488h+var_28]
0x18012201a  mov     rbx, [r11+40h]
0x18012201e  mov     rbp, [r11+48h]
0x180122022  mov     rsp, r11
0x180122025  pop     r15
0x180122027  pop     r14
0x180122029  pop     r12
0x18012202b  pop     rdi
0x18012202c  pop     rsi
0x18012202d  retn
```
