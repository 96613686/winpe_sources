# _dynamic_initializer_for__g_TraceOuputSettings__

- ea: `0x1400011e0`
- end: `0x140001232`
- name: `_dynamic_initializer_for__g_TraceOuputSettings__`
- size: `82`
- prototype: `int __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400011e0`
- `0x140001a78`
- `0x140002980`
- `0x140006010`

## string_xrefs

- `0x1400011ff`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`

## pseudocode

```c
int __fastcall dynamic_initializer_for__g_TraceOuputSettings__(void *a1)
{
  int v1; // eax

  v1 = TraceOutputSettings::Initialize(a1);
  if ( v1 )
    TraceStringInline(
      2,
      1u,
      (__int64)L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
      82,
      (__int64)L"TraceOutputSettings::TraceOutputSettings",
      v1,
      L"Error from Initialize");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_TraceOuputSettings__);
}

```

## disassembly

```asm
0x1400011e0  sub     rsp, 48h
0x1400011e4  call    ?Initialize@TraceOutputSettings@@SAKPEAX@Z; TraceOutputSettings::Initialize(void *)
0x1400011e9  test    eax, eax
0x1400011eb  jz      short loc_140001222
0x1400011ed  lea     rcx, aErrorFromIniti; "Error from Initialize"
0x1400011f4  mov     r9d, 52h ; 'R'
0x1400011fa  mov     [rsp+48h+var_18], rcx
0x1400011ff  lea     r8, aComComplusDtcS_0; "com\\complus\\dtc\\shared\\trace\\src\\"...
0x140001206  mov     [rsp+48h+var_20], eax
0x14000120a  lea     rax, aTraceoutputset; "TraceOutputSettings::TraceOutputSetting"...
0x140001211  mov     [rsp+48h+var_28], rax
0x140001216  lea     edx, [r9-51h]
0x14000121a  lea     ecx, [rdx+1]
0x14000121d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x140001222  lea     rcx, _dynamic_atexit_destructor_for__g_TraceOuputSettings__
0x140001229  add     rsp, 48h
0x14000122d  jmp     atexit
```
