# wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)

- ea: `0x140009c64`
- end: `0x140009c82`
- name: `?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z`
- size: `30`
- prototype: `__int64 (__fastcall *__fastcall(wil::details *this, __int64, __int64, int *))(wil::details *, __int64, __int64, int *)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d5a4`
- `0x14000d670`
- `0x14000d6ec`
- `0x14000d768`
- `0x14000d7e4`
- `0x14000d860`
- `0x14000d8dc`
- `0x14000d9c8`
- `0x14000dab4`
- `0x14000dba0`
- `0x14000dc8c`
- `0x14000dd68`

## callees

- `0x140009c64`
- `0x140018010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil::details::WilApi_GetFeatureEnabledState(
        wil::details *this,
        __int64 a2,
        __int64 a3,
        int *a4))(wil::details *, __int64, __int64, int *)
{
  __int64 (__fastcall *result)(wil::details *, __int64, __int64, int *); // rax

  result = (__int64 (__fastcall *)(wil::details *, __int64, __int64, int *))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState )
    return (__int64 (__fastcall *)(wil::details *, __int64, __int64, int *))result(this, a2, a3, a4);
  result = (__int64 (__fastcall *)(wil::details *, __int64, __int64, int *))g_wil_details_apiGetFeatureEnabledState;
  if ( g_wil_details_apiGetFeatureEnabledState )
    return (__int64 (__fastcall *)(wil::details *, __int64, __int64, int *))result(this, a2, a3, a4);
  return result;
}

```

## disassembly

```asm
0x140009c64  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140009c6b  test    rax, rax
0x140009c6e  jz      short loc_140009C75
0x140009c70  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x140009c75  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140009c7c  test    rax, rax
0x140009c7f  jnz     short loc_140009C70
0x140009c81  retn
```
