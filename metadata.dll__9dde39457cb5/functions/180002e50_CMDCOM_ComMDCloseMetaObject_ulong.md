# CMDCOM::ComMDCloseMetaObject(ulong)

- ea: `0x180002e50`
- end: `0x1800030ab`
- name: `?ComMDCloseMetaObject@CMDCOM@@UEAAJK@Z`
- size: `603`
- prototype: `__int64 __fastcall(CMDCOM *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002e50`
- `0x1800034e0`
- `0x1800084cc`
- `0x1800142d4`
- `0x180014310`
- `0x1800143bc`

## import_xrefs

- `KERNEL32!PulseEvent` at `0x18000305d`
- `KERNEL32!PulseEvent` at `0x18000307b`
- `KERNEL32!PulseEvent` at `0x18000305d`
- `KERNEL32!PulseEvent` at `0x18000307b`
- `IisRTL!?ConvertExclusiveToShared@CReaderWriterLock3@@QEAAXXZ` at `0x180002f17`
- `IisRTL!?ConvertExclusiveToShared@CReaderWriterLock3@@QEAAXXZ` at `0x180002f17`
- `IisRTL!?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z` at `0x180002f35`
- `IisRTL!?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z` at `0x180002f8b`
- `IisRTL!?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z` at `0x180002f9e`
- `IisRTL!?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z` at `0x180002fb4`
- `IisRTL!?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z` at `0x180002f35`
- `IisRTL!?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z` at `0x180002f8b`
- `IisRTL!?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z` at `0x180002f9e`
- `IisRTL!?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z` at `0x180002fb4`
- `IisRTL!PuDbgPrint` at `0x18000304b`
- `IisRTL!PuDbgPrint` at `0x18000304b`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180002e64`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180002e64`
- `IisRTL!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x180002ed8`
- `IisRTL!?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z` at `0x180002ed8`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180002eb7`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180002eb7`

## string_xrefs

- `0x180003044`: `inetsrv\iis\mb\metadata\comobj.cxx`
- `0x180003032`: `CMDCOM::ComMDCloseMetaObject`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDCloseMetaObject(CMDCOM *this, unsigned int a2)
{
  CHandleTable *v4; // rbx
  unsigned int Key; // eax
  int v6; // ebp
  CMDHandle *v7; // rdi
  unsigned int v8; // eax
  CHANGE_NOTIFY *v9; // rbp
  BOOL v10; // r15d
  int v11; // r14d
  __int64 v13; // rax
  __int64 i; // rcx
  CMDHandle *v15; // [rsp+70h] [rbp+18h] BYREF

  CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockMasterResource);
  if ( !g_dwInitialized )
  {
    CReaderWriterLock3::ReadOrWriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource, 0);
    return 2148321280LL;
  }
  if ( !a2 )
  {
    CReaderWriterLock3::ReadOrWriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource, 0);
    return 2147942406LL;
  }
  v4 = g_pHandleTable;
  if ( !g_pHandleTable )
  {
    v6 = -2147418113;
LABEL_19:
    CReaderWriterLock3::ReadOrWriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource, 0);
    return (unsigned int)v6;
  }
  v15 = 0;
  Key = CLKRHashTable::FindKey(g_pHandleTable, a2, &v15);
  v6 = CHandleTable::_HRESULT_FROM_LK_RETCODE(Key);
  if ( v6 < 0 )
    goto LABEL_19;
  v7 = v15;
  v8 = CLKRHashTable::DeleteKey(v4, a2);
  v6 = CHandleTable::_HRESULT_FROM_LK_RETCODE(v8);
  if ( v6 < 0 )
    goto LABEL_19;
  if ( (*((_BYTE *)v7 + 12) & 2) != 0 )
  {
    RemovePermissions(*((struct CMDBaseObject **)v7 + 3), 2u);
    v9 = (CHANGE_NOTIFY *)*((_QWORD *)v7 + 5);
    v10 = 1;
    *((_QWORD *)v7 + 5) = 0;
  }
  else
  {
    v9 = 0;
    v10 = 0;
  }
  v11 = 0;
  if ( (*((_BYTE *)v7 + 12) & 1) != 0 )
  {
    v13 = *((_QWORD *)v7 + 3);
    --*(_DWORD *)(v13 + 192);
    for ( i = *(_QWORD *)(v13 + 184); i; i = *(_QWORD *)(i + 184) )
      --*(_DWORD *)(i + 196);
    v11 = 1;
  }
  CReaderWriterLock3::ConvertExclusiveToShared((CReaderWriterLock3 *)&g_LockMasterResource);
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\comobj.cxx",
      3046,
      "CMDCOM::ComMDCloseMetaObject",
      "Metabase handle %u closed\n",
      a2);
  CReaderWriterLock3::ReadOrWriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource, 1);
  if ( v10 )
    v10 = PulseEvent(*(&g_phEventHandles + 1));
  if ( v11 && !v10 )
    PulseEvent(g_phEventHandles);
  if ( v9 )
  {
    CHANGE_NOTIFY::SendNotifications(v9, this);
    CHANGE_NOTIFY::Destroy(v9);
  }
  if ( v7 )
    CMDHandle::Destroy(v7);
  return 0;
}

```

## disassembly

```asm
0x180002e50  push    rsi
0x180002e52  push    r12
0x180002e54  sub     rsp, 48h
0x180002e58  mov     r12, rcx
0x180002e5b  mov     esi, edx
0x180002e5d  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180002e64  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180002e6a  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180002e70  test    eax, eax
0x180002e72  jz      loc_180002F95
0x180002e78  test    esi, esi
0x180002e7a  jz      loc_180002FAB
0x180002e80  mov     [rsp+58h+arg_0], rbx
0x180002e85  mov     rbx, cs:?g_pHandleTable@@3PEAVCHandleTable@@EA; CHandleTable * g_pHandleTable
0x180002e8c  mov     [rsp+58h+arg_8], rbp
0x180002e91  mov     [rsp+58h+var_18], rdi
0x180002e96  mov     [rsp+58h+var_20], r14
0x180002e9b  test    rbx, rbx
0x180002e9e  jz      loc_180002FC1
0x180002ea4  lea     r8, [rsp+58h+arg_10]
0x180002ea9  mov     [rsp+58h+arg_10], 0
0x180002eb2  mov     edx, esi
0x180002eb4  mov     rcx, rbx
0x180002eb7  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180002ebd  mov     ecx, eax
0x180002ebf  call    ?_HRESULT_FROM_LK_RETCODE@CHandleTable@@CAJW4LK_RETCODE@@@Z; CHandleTable::_HRESULT_FROM_LK_RETCODE(LK_RETCODE)
0x180002ec4  mov     ebp, eax
0x180002ec6  test    eax, eax
0x180002ec8  js      loc_180002F82
0x180002ece  mov     rdi, [rsp+58h+arg_10]
0x180002ed3  mov     edx, esi
0x180002ed5  mov     rcx, rbx
0x180002ed8  call    cs:__imp_?DeleteKey@CLKRHashTable@@QEAA?AW4LK_RETCODE@@_K@Z; CLKRHashTable::DeleteKey(unsigned __int64)
0x180002ede  mov     ecx, eax
0x180002ee0  call    ?_HRESULT_FROM_LK_RETCODE@CHandleTable@@CAJW4LK_RETCODE@@@Z; CHandleTable::_HRESULT_FROM_LK_RETCODE(LK_RETCODE)
0x180002ee5  mov     ebp, eax
0x180002ee7  test    eax, eax
0x180002ee9  js      loc_180002F82
0x180002eef  mov     [rsp+58h+var_28], r15
0x180002ef4  test    byte ptr [rdi+0Ch], 2
0x180002ef8  jnz     loc_180002FC8
0x180002efe  xor     ebp, ebp
0x180002f00  xor     r15d, r15d
0x180002f03  xor     r14d, r14d
0x180002f06  test    byte ptr [rdi+0Ch], 1
0x180002f0a  jnz     loc_180002FED
0x180002f10  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180002f17  call    cs:__imp_?ConvertExclusiveToShared@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ConvertExclusiveToShared(void)
0x180002f1d  xor     ebx, ebx
0x180002f1f  test    byte ptr cs:g_dwDebugFlags, 3
0x180002f26  jnz     loc_180003020
0x180002f2c  mov     dl, 1
0x180002f2e  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180002f35  call    cs:__imp_?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z; CReaderWriterLock3::ReadOrWriteUnlock(bool)
0x180002f3b  test    r15d, r15d
0x180002f3e  jnz     loc_180003056
0x180002f44  test    r14d, r14d
0x180002f47  jnz     loc_18000306B
0x180002f4d  mov     r15, [rsp+58h+var_28]
0x180002f52  test    rbp, rbp
0x180002f55  jnz     loc_180003086
0x180002f5b  test    rdi, rdi
0x180002f5e  jnz     loc_18000309E
0x180002f64  mov     eax, ebx
0x180002f66  mov     rdi, [rsp+58h+var_18]
0x180002f6b  mov     rbp, [rsp+58h+arg_8]
0x180002f70  mov     rbx, [rsp+58h+arg_0]
0x180002f75  mov     r14, [rsp+58h+var_20]
0x180002f7a  add     rsp, 48h
0x180002f7e  pop     r12
0x180002f80  pop     rsi
0x180002f81  retn
0x180002f82  xor     edx, edx
0x180002f84  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180002f8b  call    cs:__imp_?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z; CReaderWriterLock3::ReadOrWriteUnlock(bool)
0x180002f91  mov     eax, ebp
0x180002f93  jmp     short loc_180002F66
0x180002f95  xor     edx, edx
0x180002f97  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180002f9e  call    cs:__imp_?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z; CReaderWriterLock3::ReadOrWriteUnlock(bool)
0x180002fa4  mov     eax, 800CC800h
0x180002fa9  jmp     short loc_180002F7A
0x180002fab  xor     edx, edx
0x180002fad  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180002fb4  call    cs:__imp_?ReadOrWriteUnlock@CReaderWriterLock3@@QEAAX_N@Z; CReaderWriterLock3::ReadOrWriteUnlock(bool)
0x180002fba  mov     eax, 80070006h
0x180002fbf  jmp     short loc_180002F7A
0x180002fc1  mov     ebp, 8000FFFFh
0x180002fc6  jmp     short loc_180002F82
0x180002fc8  mov     rcx, [rdi+18h]; struct CMDBaseObject *
0x180002fcc  mov     edx, 2; unsigned int
0x180002fd1  call    ?RemovePermissions@@YAXPEAVCMDBaseObject@@K@Z; RemovePermissions(CMDBaseObject *,ulong)
0x180002fd6  mov     rbp, [rdi+28h]
0x180002fda  mov     r15d, 1
0x180002fe0  mov     qword ptr [rdi+28h], 0
0x180002fe8  jmp     loc_180002F03
0x180002fed  mov     rax, [rdi+18h]
0x180002ff1  dec     dword ptr [rax+0C0h]
0x180002ff7  mov     rcx, [rax+0B8h]
0x180002ffe  test    rcx, rcx
0x180003001  jz      short loc_180003015
0x180003003  dec     dword ptr [rcx+0C4h]
0x180003009  mov     rcx, [rcx+0B8h]
0x180003010  test    rcx, rcx
0x180003013  jnz     short loc_180003003
0x180003015  mov     r14d, 1
0x18000301b  jmp     loc_180002F10
0x180003020  mov     rcx, cs:g_pDebug
0x180003027  lea     rax, aMetabaseHandle; "Metabase handle %u closed\n"
0x18000302e  mov     [rsp+58h+var_30], esi
0x180003032  lea     r9, aCmdcomCommdclo; "CMDCOM::ComMDCloseMetaObject"
0x180003039  mov     r8d, 0BE6h
0x18000303f  mov     [rsp+58h+var_38], rax
0x180003044  lea     rdx, aInetsrvIisMbMe_2; "inetsrv\\iis\\mb\\metadata\\comobj.cxx"
0x18000304b  call    cs:__imp_PuDbgPrint
0x180003051  jmp     loc_180002F2C
0x180003056  mov     rcx, qword ptr cs:?g_phEventHandles@@3PAPEAXA+8; hEvent
0x18000305d  call    cs:__imp_PulseEvent
0x180003063  mov     r15d, eax
0x180003066  jmp     loc_180002F44
0x18000306b  test    r15d, r15d
0x18000306e  jnz     loc_180002F4D
0x180003074  mov     rcx, qword ptr cs:?g_phEventHandles@@3PAPEAXA; hEvent
0x18000307b  call    cs:__imp_PulseEvent
0x180003081  jmp     loc_180002F4D
0x180003086  mov     rdx, r12; struct CMDCOM *
0x180003089  mov     rcx, rbp; this
0x18000308c  call    ?SendNotifications@CHANGE_NOTIFY@@QEAAXPEAVCMDCOM@@@Z; CHANGE_NOTIFY::SendNotifications(CMDCOM *)
0x180003091  mov     rcx, rbp; this
0x180003094  call    ?Destroy@CHANGE_NOTIFY@@QEAAXXZ; CHANGE_NOTIFY::Destroy(void)
0x180003099  jmp     loc_180002F5B
0x18000309e  mov     rcx, rdi; this
0x1800030a1  call    ?Destroy@CMDHandle@@QEAAXXZ; CMDHandle::Destroy(void)
0x1800030a6  jmp     loc_180002F64
```
