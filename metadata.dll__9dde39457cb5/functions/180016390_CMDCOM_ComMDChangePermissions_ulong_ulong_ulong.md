# CMDCOM::ComMDChangePermissions(ulong,ulong,ulong)

- ea: `0x180016390`
- end: `0x18001664c`
- name: `?ComMDChangePermissions@CMDCOM@@UEAAJKKK@Z`
- size: `700`
- prototype: `__int64 __fastcall(CMDCOM *__hidden this, unsigned int, DWORD dwMilliseconds, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002d60`
- `0x180007870`
- `0x1800082d0`
- `0x1800084cc`
- `0x1800142d4`
- `0x1800143bc`
- `0x180016390`

## import_xrefs

- `KERNEL32!PulseEvent` at `0x180016604`
- `KERNEL32!PulseEvent` at `0x180016623`
- `KERNEL32!PulseEvent` at `0x180016604`
- `KERNEL32!PulseEvent` at `0x180016623`
- `KERNEL32!WaitForMultipleObjects` at `0x18001652f`
- `KERNEL32!WaitForMultipleObjects` at `0x18001652f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800164b3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001653a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800164b3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001653a`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001641f`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001650e`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001641f`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001650e`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800163c0`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001657a`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800163c0`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001657a`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDChangePermissions(CMDCOM *this, unsigned int a2, DWORD dwMilliseconds, int a4)
{
  struct CMDCOM *v4; // rbx
  __int64 v5; // rdi
  CHANGE_NOTIFY *v6; // r14
  unsigned int v9; // edi
  struct CMDHandle *HandleObject; // rax
  struct CMDHandle *v11; // rbx
  int v13; // eax
  unsigned int v14; // r10d
  int v15; // ecx
  int v16; // eax
  BOOL v17; // edx
  BOOL v18; // r12d
  __int64 v19; // r13
  unsigned __int64 v20; // rdi
  int v21; // esi
  DWORD v22; // r9d
  struct CMDHandle *v23; // rax
  struct CMDBaseObject **v24; // rsi
  int v25; // [rsp+20h] [rbp-58h]
  int v26; // [rsp+24h] [rbp-54h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+28h] [rbp-50h] BYREF

  v4 = this;
  v5 = dwMilliseconds;
  v6 = 0;
  SystemTimeAsFileTime = 0;
  CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockMasterResource);
  if ( !g_dwInitialized )
  {
    v9 = -2146646016;
    goto LABEL_9;
  }
  if ( a2 && GetHandleObject(a2) && (a4 & 3) != 0 )
  {
    HandleObject = GetHandleObject(a2);
    v11 = HandleObject;
    if ( !HandleObject )
    {
LABEL_7:
      v9 = -2147024890;
LABEL_8:
      v4 = this;
      goto LABEL_9;
    }
    v13 = *((_DWORD *)HandleObject + 3);
    v14 = 1;
    v15 = v13 & 1;
    if ( (v13 & 1) != 0 || (v25 = 1, (a4 & 1) == 0) )
      v25 = 0;
    v16 = v13 & 2;
    v17 = !v16 && (a4 & 2) != 0;
    if ( !v15 || (v26 = 1, (a4 & 1) != 0) )
      v26 = 0;
    v18 = v16 && (a4 & 2) == 0;
    if ( v17 )
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v19 = v5;
      v20 = SystemTimeAsFileTime.dwLowDateTime
          + 10000 * v5
          + ((unsigned __int64)SystemTimeAsFileTime.dwHighDateTime << 32);
      v21 = PermissionsAvailable(*((struct CMDBaseObject **)v11 + 3), 2u, 1u);
      if ( !v21 )
      {
        do
        {
          if ( v19 <= 0 )
            break;
          if ( !v11 )
            goto LABEL_7;
          CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
          v22 = 10;
          if ( (unsigned int)v19 < 0xA )
            v22 = v19;
          WaitForMultipleObjects(2u, &g_phEventHandles, 0, v22);
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          v19 = (__int64)(v20
                        - ((unsigned __int64)SystemTimeAsFileTime.dwHighDateTime << 32)
                        - SystemTimeAsFileTime.dwLowDateTime)
              / 10000;
          CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockMasterResource);
          v23 = GetHandleObject(a2);
          v11 = v23;
          if ( v23 )
            v21 = PermissionsAvailable(*((struct CMDBaseObject **)v23 + 3), 2u, 1u);
        }
        while ( !v21 );
        if ( !v11 )
          goto LABEL_7;
      }
      if ( !v21 )
      {
        v9 = -2147024748;
        goto LABEL_8;
      }
      AddPermissions(*((struct CMDBaseObject **)v11 + 3), 2);
    }
    v9 = 0;
    v24 = (struct CMDBaseObject **)((char *)v11 + 24);
    if ( v25 )
      AddPermissions(*v24, v14);
    if ( v26 )
    {
      RemovePermissions(*v24, v14);
      PulseEvent(g_phEventHandles);
    }
    if ( v18 )
    {
      RemovePermissions(*v24, 2u);
      PulseEvent(*(&g_phEventHandles + 1));
    }
    *((_DWORD *)v11 + 3) = a4;
    if ( v18 )
    {
      v6 = (CHANGE_NOTIFY *)*((_QWORD *)v11 + 5);
      *((_QWORD *)v11 + 5) = 0;
    }
    goto LABEL_8;
  }
  v9 = -2147024809;
LABEL_9:
  CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
  if ( v6 )
  {
    CHANGE_NOTIFY::SendNotifications(v6, v4);
    CHANGE_NOTIFY::Destroy(v6);
  }
  return v9;
}

```

## disassembly

```asm
0x180016390  mov     [rsp+arg_0], rcx
0x180016395  push    rbx
0x180016396  push    rbp
0x180016397  push    rsi
0x180016398  push    rdi
0x180016399  push    r12
0x18001639b  push    r13
0x18001639d  push    r14
0x18001639f  push    r15
0x1800163a1  sub     rsp, 38h
0x1800163a5  mov     rbx, rcx
0x1800163a8  mov     edi, r8d
0x1800163ab  xor     r14d, r14d
0x1800163ae  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x1800163b5  mov     qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime], r14
0x1800163ba  mov     ebp, r9d
0x1800163bd  mov     r15d, edx
0x1800163c0  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800163c6  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x1800163cc  test    eax, eax
0x1800163ce  jnz     short loc_1800163D7
0x1800163d0  mov     edi, 800CC800h
0x1800163d5  jmp     short loc_180016418
0x1800163d7  test    r15d, r15d
0x1800163da  jz      loc_180016642
0x1800163e0  mov     ecx, r15d; unsigned int
0x1800163e3  call    ?GetHandleObject@@YAPEAVCMDHandle@@K@Z; GetHandleObject(ulong)
0x1800163e8  test    rax, rax
0x1800163eb  jz      loc_180016642
0x1800163f1  test    bpl, 3
0x1800163f5  jz      loc_180016642
0x1800163fb  mov     ecx, r15d; unsigned int
0x1800163fe  call    ?GetHandleObject@@YAPEAVCMDHandle@@K@Z; GetHandleObject(ulong)
0x180016403  mov     rbx, rax
0x180016406  test    rax, rax
0x180016409  jnz     short loc_180016450
0x18001640b  mov     edi, 80070006h
0x180016410  mov     rbx, [rsp+78h+arg_0]
0x180016418  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18001641f  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180016425  test    r14, r14
0x180016428  jz      short loc_18001643D
0x18001642a  mov     rdx, rbx; struct CMDCOM *
0x18001642d  mov     rcx, r14; this
0x180016430  call    ?SendNotifications@CHANGE_NOTIFY@@QEAAXPEAVCMDCOM@@@Z; CHANGE_NOTIFY::SendNotifications(CMDCOM *)
0x180016435  mov     rcx, r14; this
0x180016438  call    ?Destroy@CHANGE_NOTIFY@@QEAAXXZ; CHANGE_NOTIFY::Destroy(void)
0x18001643d  mov     eax, edi
0x18001643f  add     rsp, 38h
0x180016443  pop     r15
0x180016445  pop     r14
0x180016447  pop     r13
0x180016449  pop     r12
0x18001644b  pop     rdi
0x18001644c  pop     rsi
0x18001644d  pop     rbp
0x18001644e  pop     rbx
0x18001644f  retn
0x180016450  mov     eax, [rax+0Ch]
0x180016453  mov     r10d, 1
0x180016459  mov     ecx, eax
0x18001645b  and     ecx, r10d
0x18001645e  jnz     short loc_18001646A
0x180016460  mov     [rsp+78h+var_58], r10d
0x180016465  test    r10b, bpl
0x180016468  jnz     short loc_18001646F
0x18001646a  mov     [rsp+78h+var_58], r14d
0x18001646f  and     eax, 2
0x180016472  jnz     short loc_18001647F
0x180016474  test    bpl, 2
0x180016478  jz      short loc_18001647F
0x18001647a  mov     edx, r10d
0x18001647d  jmp     short loc_180016481
0x18001647f  xor     edx, edx
0x180016481  test    ecx, ecx
0x180016483  jz      short loc_18001648F
0x180016485  mov     [rsp+78h+var_54], r10d
0x18001648a  test    r10b, bpl
0x18001648d  jz      short loc_180016494
0x18001648f  mov     [rsp+78h+var_54], r14d
0x180016494  test    eax, eax
0x180016496  jz      short loc_1800164A3
0x180016498  test    bpl, 2
0x18001649c  jnz     short loc_1800164A3
0x18001649e  mov     r12d, r10d
0x1800164a1  jmp     short loc_1800164A6
0x1800164a3  xor     r12d, r12d
0x1800164a6  test    edx, edx
0x1800164a8  jz      loc_1800165D5
0x1800164ae  lea     rcx, [rsp+78h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800164b3  call    cs:__imp_GetSystemTimeAsFileTime
0x1800164b9  mov     rcx, [rbx+18h]; struct CMDBaseObject *
0x1800164bd  mov     r13, rdi
0x1800164c0  mov     edi, [rsp+78h+SystemTimeAsFileTime.dwHighDateTime]
0x1800164c4  mov     r10d, 1
0x1800164ca  imul    rax, r13, 2710h
0x1800164d1  shl     rdi, 20h
0x1800164d5  mov     r8d, r10d; unsigned int
0x1800164d8  add     rdi, rax
0x1800164db  lea     edx, [r10+1]; unsigned int
0x1800164df  mov     eax, [rsp+78h+SystemTimeAsFileTime.dwLowDateTime]
0x1800164e3  add     rdi, rax
0x1800164e6  call    ?PermissionsAvailable@@YAHPEAVCMDBaseObject@@KK@Z; PermissionsAvailable(CMDBaseObject *,ulong,ulong)
0x1800164eb  mov     esi, eax
0x1800164ed  test    eax, eax
0x1800164ef  jnz     loc_1800165B9
0x1800164f5  test    r13, r13
0x1800164f8  jle     loc_1800165B0
0x1800164fe  test    rbx, rbx
0x180016501  jz      loc_18001640B
0x180016507  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x18001650e  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180016514  mov     r9d, 0Ah
0x18001651a  lea     rdx, ?g_phEventHandles@@3PAPEAXA; lpHandles
0x180016521  cmp     r13d, r9d
0x180016524  cmovb   r9d, r13d; dwMilliseconds
0x180016528  xor     r8d, r8d; bWaitAll
0x18001652b  lea     ecx, [r8+2]; nCount
0x18001652f  call    cs:__imp_WaitForMultipleObjects
0x180016535  lea     rcx, [rsp+78h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001653a  call    cs:__imp_GetSystemTimeAsFileTime
0x180016540  mov     eax, [rsp+78h+SystemTimeAsFileTime.dwHighDateTime]
0x180016544  mov     rcx, rdi
0x180016547  shl     rax, 20h
0x18001654b  sub     rcx, rax
0x18001654e  mov     eax, [rsp+78h+SystemTimeAsFileTime.dwLowDateTime]
0x180016552  sub     rcx, rax
0x180016555  mov     rax, 346DC5D63886594Bh
0x18001655f  imul    rcx
0x180016562  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180016569  mov     r13, rdx
0x18001656c  sar     r13, 0Bh
0x180016570  mov     rax, r13
0x180016573  shr     rax, 3Fh
0x180016577  add     r13, rax
0x18001657a  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180016580  mov     ecx, r15d; unsigned int
0x180016583  call    ?GetHandleObject@@YAPEAVCMDHandle@@K@Z; GetHandleObject(ulong)
0x180016588  mov     rbx, rax
0x18001658b  mov     r10d, 1
0x180016591  test    rax, rax
0x180016594  jz      short loc_1800165A8
0x180016596  mov     rcx, [rax+18h]; struct CMDBaseObject *
0x18001659a  lea     edx, [r10+1]; unsigned int
0x18001659e  mov     r8d, r10d; unsigned int
0x1800165a1  call    ?PermissionsAvailable@@YAHPEAVCMDBaseObject@@KK@Z; PermissionsAvailable(CMDBaseObject *,ulong,ulong)
0x1800165a6  mov     esi, eax
0x1800165a8  test    esi, esi
0x1800165aa  jz      loc_1800164F5
0x1800165b0  test    rbx, rbx
0x1800165b3  jz      loc_18001640B
0x1800165b9  test    esi, esi
0x1800165bb  jnz     short loc_1800165C7
0x1800165bd  mov     edi, 80070094h
0x1800165c2  jmp     loc_180016410
0x1800165c7  mov     rcx, [rbx+18h]; struct CMDBaseObject *
0x1800165cb  mov     edx, 2; unsigned int
0x1800165d0  call    ?AddPermissions@@YAXPEAVCMDBaseObject@@K@Z; AddPermissions(CMDBaseObject *,ulong)
0x1800165d5  xor     edi, edi
0x1800165d7  lea     rsi, [rbx+18h]
0x1800165db  cmp     [rsp+78h+var_58], edi
0x1800165df  jz      short loc_1800165EC
0x1800165e1  mov     rcx, [rsi]; struct CMDBaseObject *
0x1800165e4  mov     edx, r10d; unsigned int
0x1800165e7  call    ?AddPermissions@@YAXPEAVCMDBaseObject@@K@Z; AddPermissions(CMDBaseObject *,ulong)
0x1800165ec  cmp     [rsp+78h+var_54], edi
0x1800165f0  jz      short loc_18001660A
0x1800165f2  mov     rcx, [rsi]; struct CMDBaseObject *
0x1800165f5  mov     edx, r10d; unsigned int
0x1800165f8  call    ?RemovePermissions@@YAXPEAVCMDBaseObject@@K@Z; RemovePermissions(CMDBaseObject *,ulong)
0x1800165fd  mov     rcx, qword ptr cs:?g_phEventHandles@@3PAPEAXA; hEvent
0x180016604  call    cs:__imp_PulseEvent
0x18001660a  test    r12d, r12d
0x18001660d  jz      short loc_180016629
0x18001660f  mov     rcx, [rsi]; struct CMDBaseObject *
0x180016612  mov     edx, 2; unsigned int
0x180016617  call    ?RemovePermissions@@YAXPEAVCMDBaseObject@@K@Z; RemovePermissions(CMDBaseObject *,ulong)
0x18001661c  mov     rcx, qword ptr cs:?g_phEventHandles@@3PAPEAXA+8; hEvent
0x180016623  call    cs:__imp_PulseEvent
0x180016629  mov     [rbx+0Ch], ebp
0x18001662c  test    r12d, r12d
0x18001662f  jz      loc_180016410
0x180016635  mov     r14, [rbx+28h]
0x180016639  mov     [rbx+28h], rdi
0x18001663d  jmp     loc_180016410
0x180016642  mov     edi, 80070057h
0x180016647  jmp     loc_180016418
```
