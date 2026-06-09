# NfsUpCallpPasswdGroupRefreshGroup

- ea: `0x1400114ac`
- end: `0x14001160c`
- name: `NfsUpCallpPasswdGroupRefreshGroup`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x140011614`

## callees

- `0x140010da4`
- `0x1400114ac`
- `0x140011b54`
- `0x1400120d4`
- `0x140018350`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x1400115c1`
- `ADVAPI32!EventWrite` at `0x1400115c1`
- `ADVAPI32!EventEnabled` at `0x14001159e`
- `ADVAPI32!EventEnabled` at `0x14001159e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140011554`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140011554`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001153f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001153f`
- `msvcrt!qsort` at `0x14001150a`
- `msvcrt!qsort` at `0x140011521`
- `msvcrt!qsort` at `0x14001150a`
- `msvcrt!qsort` at `0x140011521`
- `ntdll!RtlFreeHeap` at `0x1400115e8`
- `ntdll!RtlFreeHeap` at `0x1400115e8`

## pseudocode

```c
__int64 __fastcall NfsUpCallpPasswdGroupRefreshGroup(__int64 a1, RTL_SRWLOCK *a2, const WCHAR *a3, void *a4)
{
  unsigned int v7; // eax
  void **v8; // rsi
  unsigned int v9; // edi
  __int64 v10; // rcx
  void **Ptr; // r15
  __int64 v12; // rax
  void **v13; // r8
  PVOID P; // [rsp+20h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+28h] [rbp-50h] BYREF

  P = 0;
  v7 = NfsUpCallpPasswdGroupLoadPasswdGroupFile(&P, (__int64)a2, a3, 0);
  v8 = (void **)P;
  v9 = v7;
  if ( v7
    || (qsort(*(void **)P, *((unsigned int *)P + 6), 8u, NfsUpCallpPasswdGroupEntrySortByName),
        qsort(v8[1], *((unsigned int *)v8 + 6), 8u, NfsUpCallpPasswdGroupGroupEntrySortById),
        (v9 = NfsUpCallpPasswdGroupValidateGroupInfoForDuplicates(v10, (__int64 *)v8, (__int64)a3)) != 0) )
  {
    if ( v8 )
    {
      v13 = v8;
      goto LABEL_14;
    }
  }
  else
  {
    AcquireSRWLockExclusive(a2);
    Ptr = (void **)a2[2].Ptr;
    a2[2].Ptr = v8;
    a2[4].Ptr = a4;
    ReleaseSRWLockExclusive(a2);
    if ( a2[5].Ptr )
      SendMapCacheRefreshIoctlToDriver();
    UserData.Ptr = (ULONGLONG)a3;
    v12 = -1;
    do
      ++v12;
    while ( a3[v12] );
    UserData.Size = 2 * v12 + 2;
    UserData.Reserved = 0;
    if ( RegHandle && EventEnabled(RegHandle, &EVENT_NFS_SERVICE_PASSWDGROUP_LOAD_SUCCESS) )
      EventWrite(RegHandle, &EVENT_NFS_SERVICE_PASSWDGROUP_LOAD_SUCCESS, 1u, &UserData);
    if ( Ptr )
    {
      v13 = Ptr;
LABEL_14:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1400114ac  push    rbx
0x1400114ae  push    rbp
0x1400114af  push    rsi
0x1400114b0  push    rdi
0x1400114b1  push    r12
0x1400114b3  push    r14
0x1400114b5  push    r15
0x1400114b7  sub     rsp, 40h
0x1400114bb  mov     rax, cs:__security_cookie
0x1400114c2  xor     rax, rsp
0x1400114c5  mov     [rsp+78h+var_40], rax
0x1400114ca  mov     rbx, r9
0x1400114cd  lea     rcx, [rsp+78h+P]
0x1400114d2  xor     r12d, r12d
0x1400114d5  xor     r9d, r9d
0x1400114d8  mov     [rsp+78h+P], r12
0x1400114dd  mov     r14, r8
0x1400114e0  mov     rbp, rdx
0x1400114e3  call    NfsUpCallpPasswdGroupLoadPasswdGroupFile
0x1400114e8  mov     rsi, [rsp+78h+P]
0x1400114ed  mov     edi, eax
0x1400114ef  test    eax, eax
0x1400114f1  jnz     loc_1400115D1
0x1400114f7  mov     edx, [rsi+18h]; NumOfElements
0x1400114fa  lea     edi, [rax+8]
0x1400114fd  mov     rcx, [rsi]; Base
0x140011500  lea     r9, NfsUpCallpPasswdGroupEntrySortByName; CompareFunction
0x140011507  mov     r8d, edi; SizeOfElements
0x14001150a  call    cs:__imp_qsort
0x140011510  mov     edx, [rsi+18h]; NumOfElements
0x140011513  lea     r9, NfsUpCallpPasswdGroupGroupEntrySortById; CompareFunction
0x14001151a  mov     rcx, [rsi+8]; Base
0x14001151e  mov     r8d, edi; SizeOfElements
0x140011521  call    cs:__imp_qsort
0x140011527  mov     r8, r14
0x14001152a  mov     rdx, rsi
0x14001152d  call    NfsUpCallpPasswdGroupValidateGroupInfoForDuplicates
0x140011532  mov     edi, eax
0x140011534  test    eax, eax
0x140011536  jnz     loc_1400115D1
0x14001153c  mov     rcx, rbp; SRWLock
0x14001153f  call    cs:__imp_AcquireSRWLockExclusive
0x140011545  mov     r15, [rbp+10h]
0x140011549  mov     rcx, rbp; SRWLock
0x14001154c  mov     [rbp+10h], rsi
0x140011550  mov     [rbp+20h], rbx
0x140011554  call    cs:__imp_ReleaseSRWLockExclusive
0x14001155a  mov     rcx, [rbp+28h]
0x14001155e  test    rcx, rcx
0x140011561  jz      short loc_140011568
0x140011563  call    SendMapCacheRefreshIoctlToDriver
0x140011568  mov     [rsp+78h+UserData.Ptr], r14
0x14001156d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140011571  inc     rax
0x140011574  cmp     [r14+rax*2], r12w
0x140011579  jnz     short loc_140011571
0x14001157b  mov     rcx, cs:RegHandle; RegHandle
0x140011582  lea     eax, ds:2[rax*2]
0x140011589  mov     [rsp+78h+UserData.Size], eax
0x14001158d  mov     dword ptr [rsp+78h+UserData.0Ch], r12d
0x140011592  test    rcx, rcx
0x140011595  jz      short loc_1400115C7
0x140011597  lea     rdx, EVENT_NFS_SERVICE_PASSWDGROUP_LOAD_SUCCESS; EventDescriptor
0x14001159e  call    cs:__imp_EventEnabled
0x1400115a4  test    al, al
0x1400115a6  jz      short loc_1400115C7
0x1400115a8  mov     rcx, cs:RegHandle; RegHandle
0x1400115af  lea     r9, [rsp+78h+UserData]; UserData
0x1400115b4  mov     r8d, 1; UserDataCount
0x1400115ba  lea     rdx, EVENT_NFS_SERVICE_PASSWDGROUP_LOAD_SUCCESS; EventDescriptor
0x1400115c1  call    cs:__imp_EventWrite
0x1400115c7  test    r15, r15
0x1400115ca  jz      short loc_1400115EE
0x1400115cc  mov     r8, r15
0x1400115cf  jmp     short loc_1400115D9
0x1400115d1  test    rsi, rsi
0x1400115d4  jz      short loc_1400115EE
0x1400115d6  mov     r8, rsi; P
0x1400115d9  mov     rcx, gs:60h
0x1400115e2  xor     edx, edx; Flags
0x1400115e4  mov     rcx, [rcx+30h]; HeapHandle
0x1400115e8  call    cs:__imp_RtlFreeHeap
0x1400115ee  mov     eax, edi
0x1400115f0  mov     rcx, [rsp+78h+var_40]
0x1400115f5  xor     rcx, rsp; StackCookie
0x1400115f8  call    __security_check_cookie
0x1400115fd  add     rsp, 40h
0x140011601  pop     r15
0x140011603  pop     r14
0x140011605  pop     r12
0x140011607  pop     rdi
0x140011608  pop     rsi
0x140011609  pop     rbp
0x14001160a  pop     rbx
0x14001160b  retn
```
