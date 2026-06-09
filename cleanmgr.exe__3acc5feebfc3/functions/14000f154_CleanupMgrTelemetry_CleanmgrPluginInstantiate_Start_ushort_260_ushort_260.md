# CleanupMgrTelemetry::CleanmgrPluginInstantiate::Start<ushort (&)[260]>(ushort (&)[260])

- ea: `0x14000f154`
- end: `0x14000f1ad`
- name: `??$Start@AEAY0BAE@G@CleanmgrPluginInstantiate@CleanupMgrTelemetry@@SA?AV01@AEAY0BAE@G@Z`
- size: `89`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140013530`

## callees

- `0x14000f154`
- `0x14000f254`
- `0x1400160b0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000f17a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000f17a`

## string_xrefs

- `0x14000f164`: `CleanmgrPluginInstantiate`

## pseudocode

```c
_QWORD *__fastcall CleanupMgrTelemetry::CleanmgrPluginInstantiate::Start<unsigned short (&)[260]>(
        _QWORD *a1,
        __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // r8

  wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    a1,
    "CleanmgrPluginInstantiate");
  *a1 = &CleanupMgrTelemetry::CleanmgrPluginInstantiate::`vftable';
  cleanmgrBeforePluginInstantiationTick = GetTickCount64();
  if ( (Microsoft_Windows_CleanmgrEnableBits & 1) != 0 )
    McTemplateU0qz_EventWriteTransfer(v4, CleanmgrPluginInstantiateStart, v5, a2);
  return a1;
}

```

## disassembly

```asm
0x14000f154  mov     [rsp+arg_0], rbx
0x14000f159  push    rdi
0x14000f15a  sub     rsp, 20h
0x14000f15e  mov     rdi, rdx
0x14000f161  mov     rbx, rcx
0x14000f164  lea     rdx, aCleanmgrplugin; "CleanmgrPluginInstantiate"
0x14000f16b  call    ??0?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14000f170  lea     rax, ??_7CleanmgrPluginInstantiate@CleanupMgrTelemetry@@6B@; const CleanupMgrTelemetry::CleanmgrPluginInstantiate::`vftable'
0x14000f177  mov     [rbx], rax
0x14000f17a  call    cs:__imp_GetTickCount64
0x14000f180  test    cs:Microsoft_Windows_CleanmgrEnableBits, 1
0x14000f187  mov     cs:?cleanmgrBeforePluginInstantiationTick@@3_KA, rax; unsigned __int64 cleanmgrBeforePluginInstantiationTick
0x14000f18e  jz      short loc_14000F19F
0x14000f190  mov     r9, rdi
0x14000f193  lea     rdx, CleanmgrPluginInstantiateStart
0x14000f19a  call    McTemplateU0qz_EventWriteTransfer
0x14000f19f  mov     rax, rbx
0x14000f1a2  mov     rbx, [rsp+28h+arg_0]
0x14000f1a7  add     rsp, 20h
0x14000f1ab  pop     rdi
0x14000f1ac  retn
```
