# GetInternalClassPtr<IDiscRecorder,CMSDiscRecorderObj>(_com_ptr_t<_com_IIID<IDiscRecorder,&__s_GUID const _GUID_85ac9776_ca88_4cf2_894e_09598c078a41>>)

- ea: `0x18000b0b4`
- end: `0x18000b106`
- name: `??$GetInternalClassPtr@UIDiscRecorder@@VCMSDiscRecorderObj@@@@YAPEAVCMSDiscRecorderObj@@V?$_com_ptr_t@V?$_com_IIID@UIDiscRecorder@@$1?_GUID_85ac9776_ca88_4cf2_894e_09598c078a41@@3U__s_GUID@@B@@@@@Z`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d830`
- `0x18000e3f0`

## callees

- `0x18000b0b4`
- `0x1800184a1`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall GetInternalClassPtr<IDiscRecorder,CMSDiscRecorderObj>(_QWORD *a1)
{
  __int64 v2; // rdi

  v2 = _RTDynamicCast_0(*a1, 0, &IDiscRecorder `RTTI Type Descriptor', &CMSDiscRecorderObj `RTTI Type Descriptor', 0);
  if ( *a1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
  return v2;
}

```

## disassembly

```asm
0x18000b0b4  mov     [rsp+arg_0], rbx
0x18000b0b9  push    rdi
0x18000b0ba  sub     rsp, 30h
0x18000b0be  mov     rbx, rcx
0x18000b0c1  mov     [rsp+38h+var_18], 0
0x18000b0c9  mov     rcx, [rcx]
0x18000b0cc  lea     r9, ??_R0?AVCMSDiscRecorderObj@@@8; CMSDiscRecorderObj `RTTI Type Descriptor'
0x18000b0d3  lea     r8, ??_R0?AUIDiscRecorder@@@8; IDiscRecorder `RTTI Type Descriptor'
0x18000b0da  xor     edx, edx
0x18000b0dc  call    __RTDynamicCast_0
0x18000b0e1  mov     rcx, [rbx]
0x18000b0e4  mov     rdi, rax
0x18000b0e7  test    rcx, rcx
0x18000b0ea  jz      short loc_18000B0F8
0x18000b0ec  mov     rdx, [rcx]
0x18000b0ef  mov     rax, [rdx+10h]
0x18000b0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0f8  mov     rbx, [rsp+38h+arg_0]
0x18000b0fd  mov     rax, rdi
0x18000b100  add     rsp, 30h
0x18000b104  pop     rdi
0x18000b105  retn
```
