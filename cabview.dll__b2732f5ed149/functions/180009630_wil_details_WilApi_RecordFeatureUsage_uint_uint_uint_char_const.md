# wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180009630`
- end: `0x180009659`
- name: `?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `41`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007988`
- `0x180007b90`
- `0x1800082a8`
- `0x180009660`

## callees

- `0x180009630`
- `0x180013010`

## pseudocode

```c
void __fastcall wil::details::WilApi_RecordFeatureUsage(wil::details *this, __int64 a2, __int64 a3)
{
  void (__fastcall *v3)(wil::details *, __int64, __int64, _QWORD); // rax

  v3 = (void (__fastcall *)(wil::details *, __int64, __int64, _QWORD))g_wil_details_internalRecordFeatureUsage;
  if ( g_wil_details_internalRecordFeatureUsage
    || (v3 = (void (__fastcall *)(wil::details *, __int64, __int64, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
  {
    v3(this, a2, a3, 0);
  }
}

```

## disassembly

```asm
0x180009630  sub     rsp, 38h
0x180009634  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000963b  test    rax, rax
0x18000963e  jnz     short loc_18000964C
0x180009640  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180009647  test    rax, rax
0x18000964a  jz      short loc_180009654
0x18000964c  xor     r9d, r9d
0x18000964f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009654  add     rsp, 38h
0x180009658  retn
```
