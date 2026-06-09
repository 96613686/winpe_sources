# wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000bfd0`
- end: `0x18000bff9`
- name: `?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `41`
- prototype: `void __fastcall(wil::details *this, __int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a3d4`
- `0x18000a5cc`
- `0x18000a6f0`
- `0x18000ae24`
- `0x18000c000`

## callees

- `0x18000bfd0`
- `0x180012010`

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
0x18000bfd0  sub     rsp, 38h
0x18000bfd4  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000bfdb  test    rax, rax
0x18000bfde  jnz     short loc_18000BFEC
0x18000bfe0  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000bfe7  test    rax, rax
0x18000bfea  jz      short loc_18000BFF4
0x18000bfec  xor     r9d, r9d
0x18000bfef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bff4  add     rsp, 38h
0x18000bff8  retn
```
