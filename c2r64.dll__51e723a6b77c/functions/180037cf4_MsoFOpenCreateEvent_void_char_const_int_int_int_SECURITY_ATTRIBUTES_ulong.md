# MsoFOpenCreateEvent(void * *,char const *,int,int,int *,_SECURITY_ATTRIBUTES *,ulong)

- ea: `0x180037cf4`
- end: `0x180037e44`
- name: `?MsoFOpenCreateEvent@@YAHPEAPEAXPEBDHHPEAHPEAU_SECURITY_ATTRIBUTES@@K@Z`
- size: `336`
- prototype: `int(void **, const char *, int, int, int *, struct _SECURITY_ATTRIBUTES *, unsigned int)`
- caller_count: `5`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180026364`
- `0x180111868`
- `0x180111c0c`
- `0x180111fa0`
- `0x1801123f0`

## callees

- `0x180004198`
- `0x180037cf4`
- `0x18003e690`
- `0x180123210`
- `0x1801234bc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180037dca`
- `KERNEL32!GetLastError` at `0x180037dca`
- `KERNEL32!OpenEventA` at `0x180037d8b`
- `KERNEL32!OpenEventA` at `0x180037d8b`
- `KERNEL32!CreateEventA` at `0x180037dc1`
- `KERNEL32!CreateEventA` at `0x180037dc1`

## pseudocode

```c
_BOOL8 __fastcall MsoFOpenCreateEvent(
        void **a1,
        const char *a2,
        BOOL a3,
        BOOL a4,
        int *a5,
        struct _SECURITY_ATTRIBUTES *a6,
        unsigned int a7)
{
  BOOL v7; // r15d
  int v9; // ebx
  _BOOL8 result; // rax
  int v11; // esi
  const CHAR *NamedObjectNameSz; // r13
  DWORD LastError; // r15d
  int v14; // r8d
  char v15; // [rsp+30h] [rbp-478h]
  LPSECURITY_ATTRIBUTES lpEventAttributes[2]; // [rsp+40h] [rbp-468h] BYREF
  char Destination[1024]; // [rsp+50h] [rbp-458h] BYREF

  v7 = a3;
  v9 = 0;
  lpEventAttributes[0] = 0;
  v15 = 0;
  if ( !a1 )
    return 0;
  v11 = 0;
  *a1 = 0;
  NamedObjectNameSz = MsoSzCreateNamedObjectNameSz(Destination, (unsigned int)a2, a2, a7, 0);
  while ( 1 )
  {
    if ( NamedObjectNameSz )
      *a1 = OpenEventA(0x120003u, (a7 >> 23) & 1, NamedObjectNameSz);
    if ( *a1 || (a7 & 0x4000000) != 0 || !(unsigned int)MsoFMNOResolveSecurity(a7, lpEventAttributes, 0) )
      break;
    *a1 = CreateEventA(lpEventAttributes[0], v7, a4, NamedObjectNameSz);
    LastError = GetLastError();
    MsoMNOReleaseSecurity(a7, lpEventAttributes, v14);
    if ( LastError != 5 || v15 )
    {
      if ( *a1 )
        LOBYTE(v11) = LastError != 183;
      break;
    }
    v15 = 1;
    v7 = a3;
  }
  result = *a1 != 0;
  if ( a5 )
  {
    if ( *a1 )
      v9 = v11;
    *a5 = v9;
  }
  return result;
}

```

## disassembly

```asm
0x180037cf4  push    rbx
0x180037cf6  push    rbp
0x180037cf7  push    rsi
0x180037cf8  push    rdi
0x180037cf9  push    r12
0x180037cfb  push    r13
0x180037cfd  push    r14
0x180037cff  push    r15
0x180037d01  sub     rsp, 468h
0x180037d08  mov     rax, cs:__security_cookie
0x180037d0f  xor     rax, rsp
0x180037d12  mov     [rsp+4A8h+var_58], rax
0x180037d1a  mov     [rsp+4A8h+bInitialState], r9d
0x180037d1f  mov     r15d, r8d
0x180037d22  mov     [rsp+4A8h+var_470], r8d
0x180037d27  mov     rdi, rcx
0x180037d2a  mov     r14, [rsp+4A8h+arg_20]
0x180037d32  mov     ebp, [rsp+4A8h+arg_30]
0x180037d39  xor     ebx, ebx
0x180037d3b  mov     [rsp+4A8h+lpEventAttributes], rbx
0x180037d40  mov     [rsp+4A8h+var_478], bl
0x180037d44  test    rcx, rcx
0x180037d47  jnz     short loc_180037D50
0x180037d49  xor     eax, eax
0x180037d4b  jmp     loc_180037E20
0x180037d50  mov     esi, ebx
0x180037d52  mov     [rcx], rbx
0x180037d55  mov     [rsp+4A8h+var_488], ebx; int
0x180037d59  mov     r9d, ebp; unsigned int
0x180037d5c  mov     r8, rdx; char *
0x180037d5f  lea     rcx, [rsp+4A8h+Destination]; Destination
0x180037d64  call    ?MsoSzCreateNamedObjectNameSz@@YAPEADPEADKPEBDKH@Z; MsoSzCreateNamedObjectNameSz(char *,ulong,char const *,ulong,int)
0x180037d69  mov     r13, rax
0x180037d6c  mov     r12d, ebp
0x180037d6f  and     r12d, 4000000h
0x180037d76  test    r13, r13
0x180037d79  jz      short loc_180037D94
0x180037d7b  mov     edx, ebp
0x180037d7d  shr     edx, 17h
0x180037d80  and     edx, 1; bInheritHandle
0x180037d83  mov     r8, r13; lpName
0x180037d86  mov     ecx, 120003h; dwDesiredAccess
0x180037d8b  call    cs:__imp_OpenEventA
0x180037d91  mov     [rdi], rax
0x180037d94  cmp     [rdi], rbx
0x180037d97  jnz     short loc_180037E0A
0x180037d99  test    r12d, r12d
0x180037d9c  jnz     short loc_180037E0A
0x180037d9e  xor     r8d, r8d; int
0x180037da1  lea     rdx, [rsp+4A8h+lpEventAttributes]; struct _SECURITY_ATTRIBUTES **
0x180037da6  mov     ecx, ebp; unsigned int
0x180037da8  call    ?MsoFMNOResolveSecurity@@YAHKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z; MsoFMNOResolveSecurity(ulong,_SECURITY_ATTRIBUTES * *,int)
0x180037dad  test    eax, eax
0x180037daf  jz      short loc_180037E0A
0x180037db1  mov     r9, r13; lpName
0x180037db4  mov     r8d, [rsp+4A8h+bInitialState]; bInitialState
0x180037db9  mov     edx, r15d; bManualReset
0x180037dbc  mov     rcx, [rsp+4A8h+lpEventAttributes]; lpEventAttributes
0x180037dc1  call    cs:__imp_CreateEventA
0x180037dc7  mov     [rdi], rax
0x180037dca  call    cs:__imp_GetLastError
0x180037dd0  mov     r15d, eax
0x180037dd3  lea     rdx, [rsp+4A8h+lpEventAttributes]; struct _SECURITY_ATTRIBUTES **
0x180037dd8  mov     ecx, ebp; unsigned int
0x180037dda  call    ?MsoMNOReleaseSecurity@@YAXKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z; MsoMNOReleaseSecurity(ulong,_SECURITY_ATTRIBUTES * *,int)
0x180037ddf  cmp     r15d, 5
0x180037de3  jnz     short loc_180037DFA
0x180037de5  cmp     [rsp+4A8h+var_478], bl
0x180037de9  jnz     short loc_180037DFA
0x180037deb  mov     [rsp+4A8h+var_478], 1
0x180037df0  mov     r15d, [rsp+4A8h+var_470]
0x180037df5  jmp     loc_180037D76
0x180037dfa  cmp     [rdi], rbx
0x180037dfd  jz      short loc_180037E0A
0x180037dff  cmp     r15d, 0B7h
0x180037e06  setnz   sil
0x180037e0a  mov     eax, ebx
0x180037e0c  cmp     [rdi], rbx
0x180037e0f  setnz   al
0x180037e12  test    r14, r14
0x180037e15  jz      short loc_180037E20
0x180037e17  cmp     [rdi], rbx
0x180037e1a  cmovnz  ebx, esi
0x180037e1d  mov     [r14], ebx
0x180037e20  mov     rcx, [rsp+4A8h+var_58]
0x180037e28  xor     rcx, rsp; StackCookie
0x180037e2b  call    __security_check_cookie
0x180037e30  add     rsp, 468h
0x180037e37  pop     r15
0x180037e39  pop     r14
0x180037e3b  pop     r13
0x180037e3d  pop     r12
0x180037e3f  pop     rdi
0x180037e40  pop     rsi
0x180037e41  pop     rbp
0x180037e42  pop     rbx
0x180037e43  retn
```
