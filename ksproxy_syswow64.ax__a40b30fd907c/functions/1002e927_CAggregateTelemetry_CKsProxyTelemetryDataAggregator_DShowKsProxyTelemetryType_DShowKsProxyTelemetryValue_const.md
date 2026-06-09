# CAggregateTelemetry<CKsProxyTelemetryDataAggregator,DShowKsProxyTelemetryType,DShowKsProxyTelemetryValue const &,1,0>::~CAggregateTelemetry<CKsProxyTelemetryDataAggregator,DShowKsProxyTelemetryType,DShowKsProxyTelemetryValue const &,1,0>(void)

- ea: `0x1002e927`
- end: `0x1002e984`
- name: `??1?$CAggregateTelemetry@VCKsProxyTelemetryDataAggregator@@W4DShowKsProxyTelemetryType@@ABUDShowKsProxyTelemetryValue@@$00$0A@@@UAE@XZ`
- size: `93`
- prototype: `void __thiscall(void *this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1002ec80`
- `0x1002ecb0`

## callees

- `0x1002d510`
- `0x1002e927`
- `0x1002e9f0`
- `0x1003af9d`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1002e942`
- `KERNEL32!DeleteCriticalSection` at `0x1002e942`

## pseudocode

```c
void __thiscall CAggregateTelemetry<CKsProxyTelemetryDataAggregator,enum DShowKsProxyTelemetryType,DShowKsProxyTelemetryValue const &,1,0>::~CAggregateTelemetry<CKsProxyTelemetryDataAggregator,enum DShowKsProxyTelemetryType,DShowKsProxyTelemetryValue const &,1,0>(
        void *this)
{
  void *v2; // esi
  void (__thiscall ***v3)(_DWORD, int); // ebx

  *(_DWORD *)this = &CAggregateTelemetry<CKsProxyTelemetryDataAggregator,enum DShowKsProxyTelemetryType,DShowKsProxyTelemetryValue const &,1,0>::`vftable';
  CAggregateTelemetry<CKsProxyTelemetryDataAggregator,enum DShowKsProxyTelemetryType,DShowKsProxyTelemetryValue const &,1,0>::Flush(1);
  v2 = (void *)*((_DWORD *)this + 3);
  if ( v2 )
  {
    DeleteCriticalSection(*((LPCRITICAL_SECTION *)this + 3));
    operator delete(v2, 0x18u);
    *((_DWORD *)this + 3) = 0;
  }
  if ( *((_BYTE *)this + 9) )
  {
    v3 = (void (__thiscall ***)(_DWORD, int))*((_DWORD *)this + 1);
    if ( v3 )
    {
      (**v3)(v3, 1);
      *((_DWORD *)this + 1) = 0;
    }
  }
}

```

## disassembly

```asm
0x1002e927  mov     edi, edi
0x1002e929  push    esi
0x1002e92a  push    edi
0x1002e92b  mov     edi, ecx
0x1002e92d  push    1
0x1002e92f  mov     dword ptr [edi], offset ??_7?$CAggregateTelemetry@VCKsProxyTelemetryDataAggregator@@W4DShowKsProxyTelemetryType@@ABUDShowKsProxyTelemetryValue@@$00$0A@@@6B@; const CAggregateTelemetry<CKsProxyTelemetryDataAggregator,DShowKsProxyTelemetryType,DShowKsProxyTelemetryValue const &,1,0>::`vftable'
0x1002e935  call    ?Flush@?$CAggregateTelemetry@VCKsProxyTelemetryDataAggregator@@W4DShowKsProxyTelemetryType@@ABUDShowKsProxyTelemetryValue@@$00$0A@@@UAEX_N@Z; CAggregateTelemetry<CKsProxyTelemetryDataAggregator,DShowKsProxyTelemetryType,DShowKsProxyTelemetryValue const &,1,0>::Flush(bool)
0x1002e93a  mov     esi, [edi+0Ch]
0x1002e93d  test    esi, esi
0x1002e93f  jz      short loc_1002E959
0x1002e941  push    esi; lpCriticalSection
0x1002e942  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x1002e948  push    18h; unsigned int
0x1002e94a  push    esi; Block
0x1002e94b  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1002e950  pop     ecx
0x1002e951  pop     ecx
0x1002e952  mov     dword ptr [edi+0Ch], 0
0x1002e959  cmp     byte ptr [edi+9], 0
0x1002e95d  jz      short loc_1002E981
0x1002e95f  push    ebx
0x1002e960  mov     ebx, [edi+4]
0x1002e963  test    ebx, ebx
0x1002e965  jz      short loc_1002E980
0x1002e967  mov     eax, [ebx]
0x1002e969  push    1
0x1002e96b  mov     esi, [eax]
0x1002e96d  mov     ecx, esi; this
0x1002e96f  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002e975  mov     ecx, ebx
0x1002e977  call    esi
0x1002e979  mov     dword ptr [edi+4], 0
0x1002e980  pop     ebx
0x1002e981  pop     edi
0x1002e982  pop     esi
0x1002e983  retn
```
