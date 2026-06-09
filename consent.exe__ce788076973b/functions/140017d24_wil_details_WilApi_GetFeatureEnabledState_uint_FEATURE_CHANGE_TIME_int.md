# wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)

- ea: `0x140017d24`
- end: `0x140017d47`
- name: `?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z`
- size: `35`
- prototype: `__int64 (__fastcall *__fastcall(wil::details *this, __int64, __int64, int *))(wil::details *, __int64, __int64, int *)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x140015fc8`
- `0x140016090`
- `0x140016174`
- `0x1400161e8`
- `0x14001625c`
- `0x1400162d0`
- `0x140016344`
- `0x140016428`
- `0x14001650c`
- `0x1400165d4`
- `0x1400166a8`

## callees

- `0x140017d24`
- `0x14001f010`

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
0x140017d24  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140017d2b  test    rax, rax
0x140017d2e  jz      short loc_140017D3A
0x140017d30  mov     edx, 3
0x140017d35  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x140017d3a  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140017d41  test    rax, rax
0x140017d44  jnz     short loc_140017D30
0x140017d46  retn
```
