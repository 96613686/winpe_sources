# _PwrshPlugInMediator::ReadConfigXmlValue_::_1_::catch$1

- ea: `0x180009b45`
- end: `0x180009b6b`
- name: `_PwrshPlugInMediator::ReadConfigXmlValue_::_1_::catch$1`
- size: `38`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting`

## callees

- `0x180001dfc`
- `0x180009b45`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180009b5b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009b5b`

## pseudocode

```c
void __fastcall __noreturn PwrshPlugInMediator::ReadConfigXmlValue_::_1_::catch_1(__int64 a1, __int64 a2)
{
  void *v2; // rcx

  v2 = *(void **)(a2 + 40);
  if ( v2 )
    operator delete[](v2);
  throw;
}

```

## disassembly

```asm
0x180009b45  mov     [rsp+arg_8], rdx
0x180009b4a  push    rbp
0x180009b4b  sub     rsp, 20h
0x180009b4f  mov     rbp, rdx
0x180009b52  mov     rcx, [rbp+28h]
0x180009b56  test    rcx, rcx
0x180009b59  jz      short loc_180009B61
0x180009b5b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009b61  xor     edx, edx; pThrowInfo
0x180009b63  xor     ecx, ecx; pExceptionObject
0x180009b65  call    _CxxThrowException_0
```
