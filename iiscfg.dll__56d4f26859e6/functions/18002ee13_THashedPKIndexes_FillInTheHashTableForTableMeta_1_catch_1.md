# _THashedPKIndexes::FillInTheHashTableForTableMeta_::_1_::catch$1

- ea: `0x18002ee13`
- end: `0x18002ee56`
- name: `_THashedPKIndexes::FillInTheHashTableForTableMeta_::_1_::catch$1`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18002df9b`
- `0x18002ee13`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002ee2c`
- `ole32!CoTaskMemFree` at `0x18002ee2c`

## pseudocode

```c
void __fastcall __noreturn THashedPKIndexes::FillInTheHashTableForTableMeta_::_1_::catch_1(__int64 a1, __int64 a2)
{
  void *v3; // rcx
  _OWORD *v4; // rax

  v3 = *(void **)(a2 + 168);
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = *(_OWORD **)(a2 + 64);
  *(_OWORD *)(a2 + 96) = *v4;
  *(_OWORD *)(a2 + 112) = v4[1];
  throw (TException *)(a2 + 96);
}

```

## disassembly

```asm
0x18002ee13  mov     [rsp+arg_8], rdx
0x18002ee18  push    rbp
0x18002ee19  sub     rsp, 40h
0x18002ee1d  mov     rbp, rdx
0x18002ee20  mov     rcx, [rbp+0A8h]; pv
0x18002ee27  test    rcx, rcx
0x18002ee2a  jz      short loc_18002EE32
0x18002ee2c  call    cs:__imp_CoTaskMemFree
0x18002ee32  mov     rax, [rbp+40h]
0x18002ee36  movups  xmm0, xmmword ptr [rax]
0x18002ee39  movups  xmmword ptr [rbp+60h], xmm0
0x18002ee3d  movups  xmm1, xmmword ptr [rax+10h]
0x18002ee41  movups  xmmword ptr [rbp+70h], xmm1
0x18002ee45  lea     rdx, _TI1?AUTException@@; pThrowInfo
0x18002ee4c  lea     rcx, [rbp+60h]; pExceptionObject
0x18002ee50  call    _CxxThrowException_0
```
