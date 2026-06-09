# wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x140009c88`
- end: `0x140009cb1`
- name: `?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `41`
- prototype: `void __fastcall(wil::details *this, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140008a14`
- `0x140008bf0`
- `0x140009328`
- `0x140009cb8`

## callees

- `0x140009c88`
- `0x140018010`

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
0x140009c88  sub     rsp, 38h
0x140009c8c  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x140009c93  test    rax, rax
0x140009c96  jnz     short loc_140009CA4
0x140009c98  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x140009c9f  test    rax, rax
0x140009ca2  jz      short loc_140009CAC
0x140009ca4  xor     r9d, r9d
0x140009ca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009cac  add     rsp, 38h
0x140009cb0  retn
```
