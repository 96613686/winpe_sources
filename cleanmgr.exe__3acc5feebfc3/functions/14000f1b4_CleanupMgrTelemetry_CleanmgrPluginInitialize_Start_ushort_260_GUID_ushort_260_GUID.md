# CleanupMgrTelemetry::CleanmgrPluginInitialize::Start<ushort (&)[260],_GUID &>(ushort (&)[260],_GUID &)

- ea: `0x14000f1b4`
- end: `0x14000f20d`
- name: `??$Start@AEAY0BAE@GAEAU_GUID@@@CleanmgrPluginInitialize@CleanupMgrTelemetry@@SA?AV01@AEAY0BAE@GAEAU_GUID@@@Z`
- size: `89`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140013530`

## callees

- `0x14000f1b4`
- `0x14000f254`
- `0x1400160b0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000f1da`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14000f1da`

## string_xrefs

- `0x14000f1c4`: `CleanmgrPluginInitialize`

## pseudocode

```c
_QWORD *__fastcall CleanupMgrTelemetry::CleanmgrPluginInitialize::Start<unsigned short (&)[260],_GUID &>(
        _QWORD *a1,
        __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // r8

  wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    a1,
    "CleanmgrPluginInitialize");
  *a1 = &CleanupMgrTelemetry::CleanmgrPluginInitialize::`vftable';
  cleanmgrBeforePluginInitializationTick = GetTickCount64();
  if ( (Microsoft_Windows_CleanmgrEnableBits & 1) != 0 )
    McTemplateU0qz_EventWriteTransfer(v4, CleanmgrPluginInitStart, v5, a2);
  return a1;
}

```

## disassembly

```asm
0x14000f1b4  mov     [rsp+arg_0], rbx
0x14000f1b9  push    rdi
0x14000f1ba  sub     rsp, 20h
0x14000f1be  mov     rdi, rdx
0x14000f1c1  mov     rbx, rcx
0x14000f1c4  lea     rdx, aCleanmgrplugin_0; "CleanmgrPluginInitialize"
0x14000f1cb  call    ??0?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14000f1d0  lea     rax, ??_7CleanmgrPluginInitialize@CleanupMgrTelemetry@@6B@; const CleanupMgrTelemetry::CleanmgrPluginInitialize::`vftable'
0x14000f1d7  mov     [rbx], rax
0x14000f1da  call    cs:__imp_GetTickCount64
0x14000f1e0  test    cs:Microsoft_Windows_CleanmgrEnableBits, 1
0x14000f1e7  mov     cs:?cleanmgrBeforePluginInitializationTick@@3_KA, rax; unsigned __int64 cleanmgrBeforePluginInitializationTick
0x14000f1ee  jz      short loc_14000F1FF
0x14000f1f0  mov     r9, rdi
0x14000f1f3  lea     rdx, CleanmgrPluginInitStart
0x14000f1fa  call    McTemplateU0qz_EventWriteTransfer
0x14000f1ff  mov     rax, rbx
0x14000f202  mov     rbx, [rsp+28h+arg_0]
0x14000f207  add     rsp, 20h
0x14000f20b  pop     rdi
0x14000f20c  retn
```
