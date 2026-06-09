# wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180008784`
- end: `0x1800087ad`
- name: `?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `41`
- prototype: `void __fastcall(wil::details *this, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180006f10`
- `0x180007160`
- `0x1800087b4`

## callees

- `0x180008784`
- `0x18000a010`

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
0x180008784  sub     rsp, 38h
0x180008788  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000878f  test    rax, rax
0x180008792  jnz     short loc_1800087A0
0x180008794  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000879b  test    rax, rax
0x18000879e  jz      short loc_1800087A8
0x1800087a0  xor     r9d, r9d
0x1800087a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087a8  add     rsp, 38h
0x1800087ac  retn
```
