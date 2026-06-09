# CAggregateTelemetry<CKsProxyTelemetryDataAggregator,DShowKsProxyTelemetryType,DShowKsProxyTelemetryValue const &,1,0>::~CAggregateTelemetry<CKsProxyTelemetryDataAggregator,DShowKsProxyTelemetryType,DShowKsProxyTelemetryValue const &,1,0>(void)

- ea: `0x180012f58`
- end: `0x180012fde`
- name: `??1?$CAggregateTelemetry@VCKsProxyTelemetryDataAggregator@@W4DShowKsProxyTelemetryType@@AEBUDShowKsProxyTelemetryValue@@$00$0A@@@UEAA@XZ`
- size: `134`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180012f10`
- `0x18003d730`

## callees

- `0x180012f58`
- `0x180015e00`
- `0x18001f1c4`
- `0x180045010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180012f81`
- `KERNEL32!DeleteCriticalSection` at `0x180012f81`

## pseudocode

```c
void __fastcall CAggregateTelemetry<CKsProxyTelemetryDataAggregator,enum DShowKsProxyTelemetryType,DShowKsProxyTelemetryValue const &,1,0>::~CAggregateTelemetry<CKsProxyTelemetryDataAggregator,enum DShowKsProxyTelemetryType,DShowKsProxyTelemetryValue const &,1,0>(
        __int64 a1,
        __int64 a2)
{
  bool v2; // zf
  void *v4; // rdi
  void (__fastcall ***v5)(_QWORD, __int64); // rcx

  v2 = *(_BYTE *)(a1 + 16) == 0;
  *(_QWORD *)a1 = &CAggregateTelemetry<CKsProxyTelemetryDataAggregator,enum DShowKsProxyTelemetryType,DShowKsProxyTelemetryValue const &,1,0>::`vftable';
  if ( !v2 )
  {
    LOBYTE(a2) = 1;
    CAggregateTelemetry<CKsProxyTelemetryDataAggregator,enum DShowKsProxyTelemetryType,DShowKsProxyTelemetryValue const &,1,0>::Log(
      a1,
      a2);
  }
  v4 = *(void **)(a1 + 24);
  if ( v4 )
  {
    DeleteCriticalSection(*(LPCRITICAL_SECTION *)(a1 + 24));
    operator delete(v4, 0x28u);
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
0x180012f58  mov     [rsp+arg_0], rbx
0x180012f5d  push    rdi
0x180012f5e  sub     rsp, 20h
0x180012f62  cmp     byte ptr [rcx+10h], 0
0x180012f66  lea     rax, ??_7?$CAggregateTelemetry@VCKsProxyTelemetryDataAggregator@@W4DShowKsProxyTelemetryType@@AEBUDShowKsProxyTelemetryValue@@$00$0A@@@6B@; const CAggregateTelemetry<CKsProxyTelemetryDataAggregator,DShowKsProxyTelemetryType,DShowKsProxyTelemetryValue const &,1,0>::`vftable'
0x180012f6d  mov     [rcx], rax
0x180012f70  mov     rbx, rcx
0x180012f73  jnz     short loc_180012FD5
0x180012f75  mov     rdi, [rbx+18h]
0x180012f79  test    rdi, rdi
0x180012f7c  jz      short loc_180012FA2
0x180012f7e  mov     rcx, rdi; lpCriticalSection
0x180012f81  call    cs:__imp_DeleteCriticalSection
0x180012f88  nop     dword ptr [rax+rax+00h]
0x180012f8d  mov     edx, 28h ; '('; unsigned __int64
0x180012f92  mov     rcx, rdi; void *
0x180012f95  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012f9a  mov     qword ptr [rbx+18h], 0
0x180012fa2  cmp     byte ptr [rbx+11h], 0
0x180012fa6  jz      short loc_180012FC9
0x180012fa8  mov     rcx, [rbx+8]
0x180012fac  test    rcx, rcx
0x180012faf  jz      short loc_180012FC9
0x180012fb1  mov     rax, [rcx]
0x180012fb4  mov     edx, 1
0x180012fb9  mov     rax, [rax]
0x180012fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fc1  mov     qword ptr [rbx+8], 0
0x180012fc9  mov     rbx, [rsp+28h+arg_0]
0x180012fce  add     rsp, 20h
0x180012fd2  pop     rdi
0x180012fd3  retn
0x180012fd5  mov     dl, 1
0x180012fd7  call    ?Log@?$CAggregateTelemetry@VCKsProxyTelemetryDataAggregator@@W4DShowKsProxyTelemetryType@@AEBUDShowKsProxyTelemetryValue@@$00$0A@@@UEAAX_N@Z; CAggregateTelemetry<CKsProxyTelemetryDataAggregator,DShowKsProxyTelemetryType,DShowKsProxyTelemetryValue const &,1,0>::Log(bool)
0x180012fdc  jmp     short loc_180012F75
```
