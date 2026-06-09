# GlobalDoWork(ulong,IHttpEventProvider *)

- ea: `0x180001e7c`
- end: `0x180001f26`
- name: `?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800024f0`

## callees

- `0x180001d8c`
- `0x180001e7c`
- `0x180013010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180001ea2`
- `msvcrt!_wcsicmp` at `0x180001ea2`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001edc`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001edc`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x180001f19`
- `iisutil!?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z` at `0x180001f19`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180001eb3`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180001eb3`

## pseudocode

```c
__int64 __fastcall GlobalDoWork(int a1, __int64 a2)
{
  const wchar_t *v2; // rax
  unsigned int v3; // edx
  _QWORD v5[5]; // [rsp+20h] [rbp-28h] BYREF

  if ( a1 == 64 )
  {
    v2 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    if ( !_wcsicmp(v2, L"MACHINE/WEBROOT/APPHOST") )
    {
      CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)W3_RESTRICTION_LIST::sm_pRestrictionLock);
      if ( W3_RESTRICTION_LIST::sm_pRestrictionList )
      {
        W3_RESTRICTION_LIST::`scalar deleting destructor'(W3_RESTRICTION_LIST::sm_pRestrictionList, v3);
        W3_RESTRICTION_LIST::sm_pRestrictionList = 0;
      }
      CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)W3_RESTRICTION_LIST::sm_pRestrictionLock);
      v5[1] = &ISAPI_DLL_MANAGER::InvalidateEntry;
      v5[0] = 0;
      v5[2] = 0;
      ((void (__fastcall *)(W3_RESTRICTION_LIST *, __int64 (__fastcall *)(), _QWORD *, __int64))CLKRHashTable::Apply)(
        g_pDllManager,
        CTypedHashTable<ISAPI_DLL_HASH,ISAPI_DLL,unsigned short const *,CLKRHashTable>::_Action,
        v5,
        1);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180001e7c  sub     rsp, 48h
0x180001e80  cmp     ecx, 40h ; '@'
0x180001e83  jnz     loc_180001F1F
0x180001e89  mov     rax, [rdx]
0x180001e8c  mov     rcx, rdx
0x180001e8f  mov     rax, [rax+8]
0x180001e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e98  mov     rcx, rax; String1
0x180001e9b  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180001ea2  call    cs:__imp__wcsicmp
0x180001ea8  test    eax, eax
0x180001eaa  jnz     short loc_180001F1F
0x180001eac  mov     rcx, cs:?sm_pRestrictionLock@W3_RESTRICTION_LIST@@0PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * W3_RESTRICTION_LIST::sm_pRestrictionLock
0x180001eb3  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180001eb9  mov     rcx, cs:?sm_pRestrictionList@W3_RESTRICTION_LIST@@0PEAV1@EA; this
0x180001ec0  test    rcx, rcx
0x180001ec3  jz      short loc_180001ED5
0x180001ec5  call    ??_GW3_RESTRICTION_LIST@@QEAAPEAXI@Z; W3_RESTRICTION_LIST::`scalar deleting destructor'(uint)
0x180001eca  mov     cs:?sm_pRestrictionList@W3_RESTRICTION_LIST@@0PEAV1@EA, 0; W3_RESTRICTION_LIST * W3_RESTRICTION_LIST::sm_pRestrictionList
0x180001ed5  mov     rcx, cs:?sm_pRestrictionLock@W3_RESTRICTION_LIST@@0PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * W3_RESTRICTION_LIST::sm_pRestrictionLock
0x180001edc  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180001ee2  mov     rcx, cs:?g_pDllManager@@3PEAVISAPI_DLL_MANAGER@@EA; ISAPI_DLL_MANAGER * g_pDllManager
0x180001ee9  lea     rax, ?InvalidateEntry@ISAPI_DLL_MANAGER@@CA?AW4LK_ACTION@@PEAVISAPI_DLL@@PEAX@Z; ISAPI_DLL_MANAGER::InvalidateEntry(ISAPI_DLL *,void *)
0x180001ef0  mov     r9d, 1
0x180001ef6  mov     [rsp+48h+var_20], rax
0x180001efb  lea     r8, [rsp+48h+var_28]
0x180001f00  mov     [rsp+48h+var_28], 0
0x180001f09  lea     rdx, ?_Action@?$CTypedHashTable@VISAPI_DLL_HASH@@VISAPI_DLL@@PEBGVCLKRHashTable@@@@CA?AW4LK_ACTION@@PEBXPEAX@Z; CTypedHashTable<ISAPI_DLL_HASH,ISAPI_DLL,ushort const *,CLKRHashTable>::_Action(void const *,void *)
0x180001f10  mov     [rsp+48h+var_18], 0
0x180001f19  call    cs:__imp_?Apply@CLKRHashTable@@QEAAKP6A?AW4LK_ACTION@@PEBXPEAX@Z1W4LK_LOCKTYPE@@@Z; CLKRHashTable::Apply(LK_ACTION (*)(void const *,void *),void *,LK_LOCKTYPE)
0x180001f1f  xor     eax, eax
0x180001f21  add     rsp, 48h
0x180001f25  retn
```
