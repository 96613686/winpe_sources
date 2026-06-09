# MsoFOpenCreateSemaphoreEx(void * *,char const *,char *,int,ulong,ulong,int *,_SECURITY_ATTRIBUTES *,ulong)

- ea: `0x180122030`
- end: `0x180122178`
- name: `?MsoFOpenCreateSemaphoreEx@@YAHPEAPEAXPEBDPEADHKKPEAHPEAU_SECURITY_ATTRIBUTES@@K@Z`
- size: `328`
- prototype: `int(void **, const char *, char *, int, unsigned int, unsigned int, int *, struct _SECURITY_ATTRIBUTES *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18010fad0`
- `0x18010fec8`

## callees

- `0x180004198`
- `0x18003e690`
- `0x180122030`
- `0x180123210`
- `0x1801234bc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801220fa`
- `KERNEL32!GetLastError` at `0x1801220fa`
- `KERNEL32!OpenSemaphoreA` at `0x1801220ba`
- `KERNEL32!OpenSemaphoreA` at `0x1801220ba`
- `KERNEL32!CreateSemaphoreA` at `0x1801220f1`
- `KERNEL32!CreateSemaphoreA` at `0x1801220f1`

## pseudocode

```c
_BOOL8 __fastcall MsoFOpenCreateSemaphoreEx(
        void **a1,
        const char *a2,
        char *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        int *a7,
        struct _SECURITY_ATTRIBUTES *a8,
        unsigned int a9)
{
  int v11; // edi
  char v12; // r12
  const CHAR *NamedObjectNameSz; // r15
  __int64 v14; // rax
  DWORD LastError; // ebp
  int v16; // r8d
  int v17; // ecx
  LPSECURITY_ATTRIBUTES lpSemaphoreAttributes[2]; // [rsp+30h] [rbp-448h] BYREF
  char Destination[1024]; // [rsp+40h] [rbp-438h] BYREF

  lpSemaphoreAttributes[0] = 0;
  if ( !a1 )
    return 0;
  v11 = 0;
  v12 = 0;
  *a1 = 0;
  NamedObjectNameSz = MsoSzCreateNamedObjectNameSz(Destination, (unsigned int)a2, a2, a9, 2);
  while ( 1 )
  {
    if ( NamedObjectNameSz )
      *a1 = OpenSemaphoreA(0x120003u, (a9 >> 23) & 1, NamedObjectNameSz);
    v14 = (__int64)*a1;
    if ( *a1 )
      break;
    LastError = 0;
    if ( !(unsigned int)MsoFMNOResolveSecurity(a9, lpSemaphoreAttributes, 2u)
      || (*a1 = CreateSemaphoreA(lpSemaphoreAttributes[0], 0, 0x7FFFFFFF, NamedObjectNameSz),
          LastError = GetLastError(),
          MsoMNOReleaseSecurity(a9, lpSemaphoreAttributes, v16),
          LastError != 5)
      || v12 )
    {
      v14 = (__int64)*a1;
      if ( *a1 && LastError != 183 )
        v11 = 1;
      break;
    }
    v12 = 1;
  }
  v17 = 0;
  if ( v14 )
    v17 = v11;
  if ( a7 )
    *a7 = v17;
  return v14 != 0;
}

```

## disassembly

```asm
0x180122030  mov     [rsp+arg_10], rbx
0x180122035  mov     [rsp+arg_18], rbp
0x18012203a  push    rsi
0x18012203b  push    rdi
0x18012203c  push    r12
0x18012203e  push    r14
0x180122040  push    r15
0x180122042  sub     rsp, 450h
0x180122049  mov     rax, cs:__security_cookie
0x180122050  xor     rax, rsp
0x180122053  mov     [rsp+478h+var_38], rax
0x18012205b  mov     rbx, rcx
0x18012205e  mov     r14, [rsp+478h+arg_30]
0x180122066  mov     esi, [rsp+478h+arg_40]
0x18012206d  mov     [rsp+478h+lpSemaphoreAttributes], 0
0x180122076  test    rcx, rcx
0x180122079  jnz     short loc_180122082
0x18012207b  xor     eax, eax
0x18012207d  jmp     loc_18012214C
0x180122082  xor     edi, edi
0x180122084  xor     r12b, r12b
0x180122087  mov     [rcx], rdi
0x18012208a  mov     [rsp+478h+var_458], 2; int
0x180122092  mov     r9d, esi; unsigned int
0x180122095  mov     r8, rdx; char *
0x180122098  lea     rcx, [rsp+478h+Destination]; Destination
0x18012209d  call    ?MsoSzCreateNamedObjectNameSz@@YAPEADPEADKPEBDKH@Z; MsoSzCreateNamedObjectNameSz(char *,ulong,char const *,ulong,int)
0x1801220a2  mov     r15, rax
0x1801220a5  test    r15, r15
0x1801220a8  jz      short loc_1801220C3
0x1801220aa  mov     edx, esi
0x1801220ac  shr     edx, 17h
0x1801220af  and     edx, 1; bInheritHandle
0x1801220b2  mov     r8, r15; lpName
0x1801220b5  mov     ecx, 120003h; dwDesiredAccess
0x1801220ba  call    cs:__imp_OpenSemaphoreA
0x1801220c0  mov     [rbx], rax
0x1801220c3  mov     rax, [rbx]
0x1801220c6  test    rax, rax
0x1801220c9  jnz     short loc_180122132
0x1801220cb  xor     ebp, ebp
0x1801220cd  lea     r8d, [rax+2]; int
0x1801220d1  lea     rdx, [rsp+478h+lpSemaphoreAttributes]; struct _SECURITY_ATTRIBUTES **
0x1801220d6  mov     ecx, esi; unsigned int
0x1801220d8  call    ?MsoFMNOResolveSecurity@@YAHKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z; MsoFMNOResolveSecurity(ulong,_SECURITY_ATTRIBUTES * *,int)
0x1801220dd  test    eax, eax
0x1801220df  jz      short loc_18012211D
0x1801220e1  mov     r9, r15; lpName
0x1801220e4  xor     edx, edx; lInitialCount
0x1801220e6  mov     r8d, 7FFFFFFFh; lMaximumCount
0x1801220ec  mov     rcx, [rsp+478h+lpSemaphoreAttributes]; lpSemaphoreAttributes
0x1801220f1  call    cs:__imp_CreateSemaphoreA
0x1801220f7  mov     [rbx], rax
0x1801220fa  call    cs:__imp_GetLastError
0x180122100  mov     ebp, eax
0x180122102  lea     rdx, [rsp+478h+lpSemaphoreAttributes]; struct _SECURITY_ATTRIBUTES **
0x180122107  mov     ecx, esi; unsigned int
0x180122109  call    ?MsoMNOReleaseSecurity@@YAXKPEAPEAU_SECURITY_ATTRIBUTES@@H@Z; MsoMNOReleaseSecurity(ulong,_SECURITY_ATTRIBUTES * *,int)
0x18012210e  cmp     ebp, 5
0x180122111  jnz     short loc_18012211D
0x180122113  test    r12b, r12b
0x180122116  jnz     short loc_18012211D
0x180122118  mov     r12b, 1
0x18012211b  jmp     short loc_1801220A5
0x18012211d  mov     rax, [rbx]
0x180122120  test    rax, rax
0x180122123  jz      short loc_180122132
0x180122125  cmp     ebp, 0B7h
0x18012212b  jz      short loc_180122132
0x18012212d  mov     edi, 1
0x180122132  xor     edx, edx
0x180122134  test    rax, rax
0x180122137  setnz   dl
0x18012213a  xor     ecx, ecx
0x18012213c  test    rax, rax
0x18012213f  cmovnz  ecx, edi
0x180122142  test    r14, r14
0x180122145  jz      short loc_18012214A
0x180122147  mov     [r14], ecx
0x18012214a  mov     eax, edx
0x18012214c  mov     rcx, [rsp+478h+var_38]
0x180122154  xor     rcx, rsp; StackCookie
0x180122157  call    __security_check_cookie
0x18012215c  lea     r11, [rsp+478h+var_28]
0x180122164  mov     rbx, [r11+40h]
0x180122168  mov     rbp, [r11+48h]
0x18012216c  mov     rsp, r11
0x18012216f  pop     r15
0x180122171  pop     r14
0x180122173  pop     r12
0x180122175  pop     rdi
0x180122176  pop     rsi
0x180122177  retn
```
