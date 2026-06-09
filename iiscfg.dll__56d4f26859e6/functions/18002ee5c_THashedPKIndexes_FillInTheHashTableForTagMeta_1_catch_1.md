# _THashedPKIndexes::FillInTheHashTableForTagMeta_::_1_::catch$1

- ea: `0x18002ee5c`
- end: `0x18002ee9f`
- name: `_THashedPKIndexes::FillInTheHashTableForTagMeta_::_1_::catch$1`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18002df9b`
- `0x18002ee5c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002ee75`
- `ole32!CoTaskMemFree` at `0x18002ee75`

## pseudocode

```c
void __fastcall __noreturn THashedPKIndexes::FillInTheHashTableForTagMeta_::_1_::catch_1(__int64 a1, __int64 a2)
{
  void *v3; // rcx
  _OWORD *v4; // rax

  v3 = *(void **)(a2 + 184);
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
0x18002ee5c  mov     [rsp+arg_8], rdx
0x18002ee61  push    rbp
0x18002ee62  sub     rsp, 40h
0x18002ee66  mov     rbp, rdx
0x18002ee69  mov     rcx, [rbp+0B8h]; pv
0x18002ee70  test    rcx, rcx
0x18002ee73  jz      short loc_18002EE7B
0x18002ee75  call    cs:__imp_CoTaskMemFree
0x18002ee7b  mov     rax, [rbp+40h]
0x18002ee7f  movups  xmm0, xmmword ptr [rax]
0x18002ee82  movups  xmmword ptr [rbp+60h], xmm0
0x18002ee86  movups  xmm1, xmmword ptr [rax+10h]
0x18002ee8a  movups  xmmword ptr [rbp+70h], xmm1
0x18002ee8e  lea     rdx, _TI1?AUTException@@; pThrowInfo
0x18002ee95  lea     rcx, [rbp+60h]; pExceptionObject
0x18002ee99  call    _CxxThrowException_0
```
