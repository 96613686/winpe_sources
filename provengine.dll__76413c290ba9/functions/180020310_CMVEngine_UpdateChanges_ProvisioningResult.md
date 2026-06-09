# CMVEngine::UpdateChanges(ProvisioningResult)

- ea: `0x180020310`
- end: `0x180020392`
- name: `?UpdateChanges@CMVEngine@@AEAAXW4ProvisioningResult@@@Z`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001240c`
- `0x180018f74`

## callees

- `0x18001cfcc`
- `0x180020310`
- `0x180021cf4`
- `0x180047010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180020324`
- `OLEAUT32!__imp_VariantInit` at `0x180020324`
- `OLEAUT32!__imp_VariantClear` at `0x18002036c`
- `OLEAUT32!__imp_VariantClear` at `0x18002036c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall CMVEngine::UpdateChanges(__int64 a1, int a2)
{
  int v4; // eax
  VARIANTARG pvarg; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  VariantInit(&pvarg);
  pvarg.vt = 19;
  pvarg.lVal = a2 | CMVEngine::RetrieveChanges(a1);
  v4 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, VARIANTARG *))(*(_QWORD *)a1 + 64LL))(
         a1,
         L"ChangesMade",
         &pvarg);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB59,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
      (const char *)(unsigned int)v4,
      *(int *)&pvarg.vt);
  return VariantClear(&pvarg);
}

```

## disassembly

```asm
0x180020310  mov     [rsp+arg_0], rbx
0x180020315  push    rdi
0x180020316  sub     rsp, 40h
0x18002031a  mov     ebx, edx
0x18002031c  mov     rdi, rcx
0x18002031f  lea     rcx, [rsp+48h+pvarg]; pvarg
0x180020324  call    cs:__imp_VariantInit
0x18002032a  nop
0x18002032b  mov     eax, 13h
0x180020330  mov     word ptr [rsp+48h+pvarg], ax; int
0x180020335  mov     rcx, rdi
0x180020338  call    ?RetrieveChanges@CMVEngine@@AEAA?AW4ProvisioningResult@@XZ; CMVEngine::RetrieveChanges(void)
0x18002033d  or      eax, ebx
0x18002033f  mov     dword ptr [rsp+48h+pvarg+8], eax
0x180020343  mov     rax, [rdi]
0x180020346  lea     r8, [rsp+48h+pvarg]
0x18002034b  lea     rdx, ?gc_wszChangesMade@@3QBGB; "ChangesMade"
0x180020352  mov     rcx, rdi
0x180020355  mov     rax, [rax+40h]
0x180020359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002035e  mov     rcx, [rsp+48h]; this
0x180020363  test    eax, eax
0x180020365  js      short loc_18002037D
0x180020367  lea     rcx, [rsp+48h+pvarg]; pvarg
0x18002036c  call    cs:__imp_VariantClear
0x180020372  mov     rbx, [rsp+48h+arg_0]
0x180020377  add     rsp, 40h
0x18002037b  pop     rdi
0x18002037c  retn
0x18002037d  mov     r9d, eax; char *
0x180020380  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180020387  mov     edx, 0B59h; void *
0x18002038c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
