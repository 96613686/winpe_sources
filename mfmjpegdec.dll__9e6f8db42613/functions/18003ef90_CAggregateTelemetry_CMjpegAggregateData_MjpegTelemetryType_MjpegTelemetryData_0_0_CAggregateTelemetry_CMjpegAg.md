# CAggregateTelemetry<CMjpegAggregateData,MjpegTelemetryType,MjpegTelemetryData *,0,0>::~CAggregateTelemetry<CMjpegAggregateData,MjpegTelemetryType,MjpegTelemetryData *,0,0>(void)

- ea: `0x18003ef90`
- end: `0x18003f00d`
- name: `??1?$CAggregateTelemetry@VCMjpegAggregateData@@W4MjpegTelemetryType@@PEATMjpegTelemetryData@@$0A@$0A@@@UEAA@XZ`
- size: `125`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18003f408`
- `0x18003fa30`
- `0x18003fa70`

## callees

- `0x1800245f0`
- `0x18003ef90`
- `0x1800416f0`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003efc0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003efc0`

## pseudocode

```c
void __fastcall CAggregateTelemetry<CMjpegAggregateData,enum MjpegTelemetryType,MjpegTelemetryData *,0,0>::~CAggregateTelemetry<CMjpegAggregateData,enum MjpegTelemetryType,MjpegTelemetryData *,0,0>(
        __int64 a1,
        __int64 a2)
{
  bool v2; // zf
  void *v4; // rdi
  void (__fastcall ***v5)(_QWORD, __int64); // rcx

  v2 = *(_BYTE *)(a1 + 16) == 0;
  *(_QWORD *)a1 = &CAggregateTelemetry<CMjpegAggregateData,enum MjpegTelemetryType,MjpegTelemetryData *,0,0>::`vftable';
  if ( !v2 )
  {
    LOBYTE(a2) = 1;
    CAggregateTelemetry<CMjpegAggregateData,enum MjpegTelemetryType,MjpegTelemetryData *,0,0>::Log(a1, a2);
  }
  v4 = *(void **)(a1 + 24);
  if ( v4 )
  {
    DeleteCriticalSection(*(LPCRITICAL_SECTION *)(a1 + 24));
    operator delete(v4, (const struct std::nothrow_t *)0x28);
    *(_QWORD *)(a1 + 24) = 0;
  }
  if ( *(_BYTE *)(a1 + 17) )
  {
    v5 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 8);
    if ( v5 )
    {
      (**v5)(v5, 1);
      *(_QWORD *)(a1 + 8) = 0;
    }
  }
}

```

## disassembly

```asm
0x18003ef90  mov     [rsp+arg_0], rbx
0x18003ef95  push    rdi
0x18003ef96  sub     rsp, 20h
0x18003ef9a  cmp     byte ptr [rcx+10h], 0
0x18003ef9e  lea     rax, ??_7?$CAggregateTelemetry@VCMjpegAggregateData@@W4MjpegTelemetryType@@PEATMjpegTelemetryData@@$0A@$0A@@@6B@; const CAggregateTelemetry<CMjpegAggregateData,MjpegTelemetryType,MjpegTelemetryData *,0,0>::`vftable'
0x18003efa5  mov     [rcx], rax
0x18003efa8  mov     rbx, rcx
0x18003efab  jz      short loc_18003EFB4
0x18003efad  mov     dl, 1
0x18003efaf  call    ?Log@?$CAggregateTelemetry@VCMjpegAggregateData@@W4MjpegTelemetryType@@PEATMjpegTelemetryData@@$0A@$0A@@@UEAAX_N@Z; CAggregateTelemetry<CMjpegAggregateData,MjpegTelemetryType,MjpegTelemetryData *,0,0>::Log(bool)
0x18003efb4  mov     rdi, [rbx+18h]
0x18003efb8  test    rdi, rdi
0x18003efbb  jz      short loc_18003EFDB
0x18003efbd  mov     rcx, rdi; lpCriticalSection
0x18003efc0  call    cs:__imp_DeleteCriticalSection
0x18003efc6  mov     edx, 28h ; '('; struct std::nothrow_t *
0x18003efcb  mov     rcx, rdi; void *
0x18003efce  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003efd3  mov     qword ptr [rbx+18h], 0
0x18003efdb  cmp     byte ptr [rbx+11h], 0
0x18003efdf  jz      short loc_18003F002
0x18003efe1  mov     rcx, [rbx+8]
0x18003efe5  test    rcx, rcx
0x18003efe8  jz      short loc_18003F002
0x18003efea  mov     rax, [rcx]
0x18003efed  mov     edx, 1
0x18003eff2  mov     rax, [rax]
0x18003eff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003effa  mov     qword ptr [rbx+8], 0
0x18003f002  mov     rbx, [rsp+28h+arg_0]
0x18003f007  add     rsp, 20h
0x18003f00b  pop     rdi
0x18003f00c  retn
```
