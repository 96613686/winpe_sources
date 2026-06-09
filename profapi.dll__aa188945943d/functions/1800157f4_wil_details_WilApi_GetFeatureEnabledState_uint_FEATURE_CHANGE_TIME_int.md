# wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)

- ea: `0x1800157f4`
- end: `0x180015817`
- name: `?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z`
- size: `35`
- prototype: `__int64 (__fastcall *__fastcall(wil::details *this, __int64, __int64, int *))(wil::details *, __int64, __int64, int *)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x180013d68`
- `0x180013e28`
- `0x180013e9c`
- `0x180013f10`
- `0x180013f84`
- `0x180013ff8`
- `0x18001406c`
- `0x18001415c`
- `0x18001424c`
- `0x18001433c`
- `0x18001442c`
- `0x180014520`

## callees

- `0x1800157f4`
- `0x180018010`

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
    return (__int64 (__fastcall *)(wil::details *, __int64, __int64, int *))result(this, 3, a3, a4);
  result = (__int64 (__fastcall *)(wil::details *, __int64, __int64, int *))g_wil_details_apiGetFeatureEnabledState;
  if ( g_wil_details_apiGetFeatureEnabledState )
    return (__int64 (__fastcall *)(wil::details *, __int64, __int64, int *))result(this, 3, a3, a4);
  return result;
}

```

## disassembly

```asm
0x1800157f4  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800157fb  test    rax, rax
0x1800157fe  jz      short loc_18001580A
0x180015800  mov     edx, 3
0x180015805  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18001580a  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180015811  test    rax, rax
0x180015814  jnz     short loc_180015800
0x180015816  retn
```
