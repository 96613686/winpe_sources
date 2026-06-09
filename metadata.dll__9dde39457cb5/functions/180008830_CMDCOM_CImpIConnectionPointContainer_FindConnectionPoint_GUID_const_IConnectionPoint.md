# CMDCOM::CImpIConnectionPointContainer::FindConnectionPoint(_GUID const &,IConnectionPoint * *)

- ea: `0x180008830`
- end: `0x1800088db`
- name: `?FindConnectionPoint@CImpIConnectionPointContainer@CMDCOM@@UEAAJAEBU_GUID@@PEAPEAUIConnectionPoint@@@Z`
- size: `171`
- prototype: `__int64 __fastcall(CMDCOM::CImpIConnectionPointContainer *__hidden this, const struct _GUID *, struct IConnectionPoint **)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180008830`
- `0x180031010`

## import_xrefs

- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800088c9`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800088c9`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000884f`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000884f`

## pseudocode

```c
__int64 __fastcall CMDCOM::CImpIConnectionPointContainer::FindConnectionPoint(
        CMDCOM::CImpIConnectionPointContainer *this,
        const struct _GUID *a2,
        struct IConnectionPoint **a3)
{
  unsigned int v6; // edi
  __int64 v7; // rax
  __int64 (__fastcall ***v8)(_QWORD, GUID *, struct IConnectionPoint **); // rcx
  __int64 v9; // rax

  v6 = -2147220992;
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockSinkResource);
  *a3 = 0;
  v7 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IMDCOMSINK_A.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IMDCOMSINK_A.Data1 )
    v7 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IMDCOMSINK_A.Data4;
  if ( !v7 )
  {
    v8 = *(__int64 (__fastcall ****)(_QWORD, GUID *, struct IConnectionPoint **))(*((_QWORD *)this + 1) + 32LL);
    goto LABEL_9;
  }
  v9 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IMDCOMSINK_W.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IMDCOMSINK_W.Data1 )
    v9 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IMDCOMSINK_W.Data4;
  if ( !v9 )
  {
    v8 = *(__int64 (__fastcall ****)(_QWORD, GUID *, struct IConnectionPoint **))(*((_QWORD *)this + 1) + 40LL);
LABEL_9:
    if ( v8 )
      v6 = (**v8)(v8, &IID_IConnectionPoint, a3);
  }
  CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&g_LockSinkResource);
  return v6;
}

```

## disassembly

```asm
0x180008830  push    rbx
0x180008832  push    rsi
0x180008833  push    rdi
0x180008834  push    r14
0x180008836  sub     rsp, 28h
0x18000883a  mov     rsi, rcx
0x18000883d  mov     r14, r8
0x180008840  lea     rcx, ?g_LockSinkResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockSinkResource
0x180008847  mov     rbx, rdx
0x18000884a  mov     edi, 80040200h
0x18000884f  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180008855  mov     qword ptr [r14], 0
0x18000885c  mov     rax, [rbx]
0x18000885f  sub     rax, qword ptr cs:IID_IMDCOMSINK_A.Data1
0x180008866  jnz     short loc_180008873
0x180008868  mov     rax, [rbx+8]
0x18000886c  sub     rax, qword ptr cs:IID_IMDCOMSINK_A.Data4
0x180008873  test    rax, rax
0x180008876  jnz     short loc_180008882
0x180008878  mov     rax, [rsi+8]
0x18000887c  mov     rcx, [rax+20h]
0x180008880  jmp     short loc_1800088A6
0x180008882  mov     rax, [rbx]
0x180008885  sub     rax, qword ptr cs:IID_IMDCOMSINK_W.Data1
0x18000888c  jnz     short loc_180008899
0x18000888e  mov     rax, [rbx+8]
0x180008892  sub     rax, qword ptr cs:IID_IMDCOMSINK_W.Data4
0x180008899  test    rax, rax
0x18000889c  jnz     short loc_1800088C2
0x18000889e  mov     rax, [rsi+8]
0x1800088a2  mov     rcx, [rax+28h]
0x1800088a6  test    rcx, rcx
0x1800088a9  jz      short loc_1800088C2
0x1800088ab  mov     rax, [rcx]
0x1800088ae  lea     rdx, IID_IConnectionPoint
0x1800088b5  mov     r8, r14
0x1800088b8  mov     rax, [rax]
0x1800088bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088c0  mov     edi, eax
0x1800088c2  lea     rcx, ?g_LockSinkResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockSinkResource
0x1800088c9  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800088cf  mov     eax, edi
0x1800088d1  add     rsp, 28h
0x1800088d5  pop     r14
0x1800088d7  pop     rdi
0x1800088d8  pop     rsi
0x1800088d9  pop     rbx
0x1800088da  retn
```
