# NfsUpCallpPasswdGroupRefreshPasswd

- ea: `0x140011800`
- end: `0x140011960`
- name: `NfsUpCallpPasswdGroupRefreshPasswd`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x140011968`

## callees

- `0x140010da4`
- `0x140011800`
- `0x140011cec`
- `0x1400120d4`
- `0x140018350`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x140011915`
- `ADVAPI32!EventWrite` at `0x140011915`
- `ADVAPI32!EventEnabled` at `0x1400118f2`
- `ADVAPI32!EventEnabled` at `0x1400118f2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400118a8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400118a8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140011893`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140011893`
- `msvcrt!qsort` at `0x14001185e`
- `msvcrt!qsort` at `0x140011875`
- `msvcrt!qsort` at `0x14001185e`
- `msvcrt!qsort` at `0x140011875`
- `ntdll!RtlFreeHeap` at `0x14001193c`
- `ntdll!RtlFreeHeap` at `0x14001193c`

## pseudocode

```c
__int64 __fastcall NfsUpCallpPasswdGroupRefreshPasswd(__int64 a1, RTL_SRWLOCK *a2, const WCHAR *a3, void *a4)
{
  unsigned int v7; // eax
  void **v8; // rsi
  unsigned int v9; // edi
  __int64 v10; // rcx
  void **Ptr; // r15
  PVOID v12; // rcx
  __int64 v13; // rax
  void **v14; // r8
  PVOID P; // [rsp+20h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+28h] [rbp-50h] BYREF

  P = 0;
  v7 = NfsUpCallpPasswdGroupLoadPasswdGroupFile(&P, (__int64)a2, a3, 1);
  v8 = (void **)P;
  v9 = v7;
  if ( v7
    || (qsort(*(void **)P, *((unsigned int *)P + 6), 8u, NfsUpCallpPasswdGroupEntrySortByName),
        qsort(v8[1], *((unsigned int *)v8 + 6), 8u, NfsUpCallpPasswdGroupPasswdEntrySortById),
        (v9 = NfsUpCallpPasswdGroupValidatePasswdInfoForDuplicates(v10, (__int64 *)v8, (__int64)a3)) != 0) )
  {
    if ( v8 )
    {
      v14 = v8;
      goto LABEL_14;
    }
  }
  else
  {
    AcquireSRWLockExclusive(a2);
    Ptr = (void **)a2[1].Ptr;
    a2[1].Ptr = v8;
    a2[3].Ptr = a4;
    ReleaseSRWLockExclusive(a2);
    v12 = a2[5].Ptr;
    if ( v12 )
      SendMapCacheRefreshIoctlToDriver(v12);
    UserData.Ptr = (ULONGLONG)a3;
    v13 = -1;
    do
      ++v13;
    while ( a3[v13] );
    UserData.Size = 2 * v13 + 2;
    UserData.Reserved = 0;
    if ( RegHandle && EventEnabled(RegHandle, &EVENT_NFS_SERVICE_PASSWDGROUP_LOAD_SUCCESS) )
      EventWrite(RegHandle, &EVENT_NFS_SERVICE_PASSWDGROUP_LOAD_SUCCESS, 1u, &UserData);
    if ( Ptr )
    {
      v14 = Ptr;
LABEL_14:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x140011800  push    rbx
0x140011802  push    rbp
0x140011803  push    rsi
0x140011804  push    rdi
0x140011805  push    r12
0x140011807  push    r14
0x140011809  push    r15
0x14001180b  sub     rsp, 40h
0x14001180f  mov     rax, cs:__security_cookie
0x140011816  xor     rax, rsp
0x140011819  mov     [rsp+78h+var_40], rax
0x14001181e  mov     rbx, r9
0x140011821  lea     rcx, [rsp+78h+P]
0x140011826  xor     r12d, r12d
0x140011829  mov     r9b, 1
0x14001182c  mov     [rsp+78h+P], r12
0x140011831  mov     r14, r8
0x140011834  mov     rbp, rdx
0x140011837  call    NfsUpCallpPasswdGroupLoadPasswdGroupFile
0x14001183c  mov     rsi, [rsp+78h+P]
0x140011841  mov     edi, eax
0x140011843  test    eax, eax
0x140011845  jnz     loc_140011925
0x14001184b  mov     edx, [rsi+18h]; NumOfElements
0x14001184e  lea     edi, [rax+8]
0x140011851  mov     rcx, [rsi]; Base
0x140011854  lea     r9, NfsUpCallpPasswdGroupEntrySortByName; CompareFunction
0x14001185b  mov     r8d, edi; SizeOfElements
0x14001185e  call    cs:__imp_qsort
0x140011864  mov     edx, [rsi+18h]; NumOfElements
0x140011867  lea     r9, NfsUpCallpPasswdGroupPasswdEntrySortById; CompareFunction
0x14001186e  mov     rcx, [rsi+8]; Base
0x140011872  mov     r8d, edi; SizeOfElements
0x140011875  call    cs:__imp_qsort
0x14001187b  mov     r8, r14
0x14001187e  mov     rdx, rsi
0x140011881  call    NfsUpCallpPasswdGroupValidatePasswdInfoForDuplicates
0x140011886  mov     edi, eax
0x140011888  test    eax, eax
0x14001188a  jnz     loc_140011925
0x140011890  mov     rcx, rbp; SRWLock
0x140011893  call    cs:__imp_AcquireSRWLockExclusive
0x140011899  mov     r15, [rbp+8]
0x14001189d  mov     rcx, rbp; SRWLock
0x1400118a0  mov     [rbp+8], rsi
0x1400118a4  mov     [rbp+18h], rbx
0x1400118a8  call    cs:__imp_ReleaseSRWLockExclusive
0x1400118ae  mov     rcx, [rbp+28h]
0x1400118b2  test    rcx, rcx
0x1400118b5  jz      short loc_1400118BC
0x1400118b7  call    SendMapCacheRefreshIoctlToDriver
0x1400118bc  mov     [rsp+78h+UserData.Ptr], r14
0x1400118c1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400118c5  inc     rax
0x1400118c8  cmp     [r14+rax*2], r12w
0x1400118cd  jnz     short loc_1400118C5
0x1400118cf  mov     rcx, cs:RegHandle; RegHandle
0x1400118d6  lea     eax, ds:2[rax*2]
0x1400118dd  mov     [rsp+78h+UserData.Size], eax
0x1400118e1  mov     dword ptr [rsp+78h+UserData.0Ch], r12d
0x1400118e6  test    rcx, rcx
0x1400118e9  jz      short loc_14001191B
0x1400118eb  lea     rdx, EVENT_NFS_SERVICE_PASSWDGROUP_LOAD_SUCCESS; EventDescriptor
0x1400118f2  call    cs:__imp_EventEnabled
0x1400118f8  test    al, al
0x1400118fa  jz      short loc_14001191B
0x1400118fc  mov     rcx, cs:RegHandle; RegHandle
0x140011903  lea     r9, [rsp+78h+UserData]; UserData
0x140011908  mov     r8d, 1; UserDataCount
0x14001190e  lea     rdx, EVENT_NFS_SERVICE_PASSWDGROUP_LOAD_SUCCESS; EventDescriptor
0x140011915  call    cs:__imp_EventWrite
0x14001191b  test    r15, r15
0x14001191e  jz      short loc_140011942
0x140011920  mov     r8, r15
0x140011923  jmp     short loc_14001192D
0x140011925  test    rsi, rsi
0x140011928  jz      short loc_140011942
0x14001192a  mov     r8, rsi; P
0x14001192d  mov     rcx, gs:60h
0x140011936  xor     edx, edx; Flags
0x140011938  mov     rcx, [rcx+30h]; HeapHandle
0x14001193c  call    cs:__imp_RtlFreeHeap
0x140011942  mov     eax, edi
0x140011944  mov     rcx, [rsp+78h+var_40]
0x140011949  xor     rcx, rsp; StackCookie
0x14001194c  call    __security_check_cookie
0x140011951  add     rsp, 40h
0x140011955  pop     r15
0x140011957  pop     r14
0x140011959  pop     r12
0x14001195b  pop     rdi
0x14001195c  pop     rsi
0x14001195d  pop     rbp
0x14001195e  pop     rbx
0x14001195f  retn
```
