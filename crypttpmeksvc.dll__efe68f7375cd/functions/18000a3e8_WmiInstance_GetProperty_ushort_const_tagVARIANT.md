# WmiInstance::GetProperty(ushort const *,tagVARIANT *)

- ea: `0x18000a3e8`
- end: `0x18000a47d`
- name: `?GetProperty@WmiInstance@@QEAAJPEBGPEAUtagVARIANT@@@Z`
- size: `149`
- prototype: `__int64 __fastcall(WmiInstance *this, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a628`

## callees

- `0x18000a3e8`
- `0x18000b010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000a40c`
- `OLEAUT32!__imp_VariantInit` at `0x18000a40c`
- `OLEAUT32!__imp_VariantClear` at `0x18000a46a`
- `OLEAUT32!__imp_VariantClear` at `0x18000a46a`
- `OLEAUT32!__imp_VariantCopy` at `0x18000a456`
- `OLEAUT32!__imp_VariantCopy` at `0x18000a456`

## string_xrefs

- `0x18000a429`: `__Path`

## pseudocode

```c
__int64 __fastcall WmiInstance::GetProperty(WmiInstance *this, const unsigned __int16 *a2, struct tagVARIANT *a3)
{
  HRESULT v5; // ebx
  VARIANTARG pvarg; // [rsp+40h] [rbp-28h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( a3 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(**((_QWORD **)this + 2)
                                                                                                  + 32LL))(
           *((_QWORD *)this + 2),
           L"__Path",
           0,
           &pvarg,
           0,
           0);
    if ( v5 >= 0 )
      v5 = VariantCopy(a3, &pvarg);
  }
  else
  {
    v5 = -2147024809;
  }
  VariantClear(&pvarg);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000a3e8  mov     [rsp+arg_0], rbx
0x18000a3ed  push    rdi
0x18000a3ee  sub     rsp, 60h
0x18000a3f2  mov     rbx, rcx
0x18000a3f5  xorps   xmm0, xmm0
0x18000a3f8  xor     eax, eax
0x18000a3fa  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18000a3ff  movups  xmmword ptr [rsp+68h+pvarg], xmm0
0x18000a404  mov     qword ptr [rsp+68h+pvarg+10h], rax
0x18000a409  mov     rdi, r8
0x18000a40c  call    cs:__imp_VariantInit
0x18000a412  test    rdi, rdi
0x18000a415  jz      short loc_18000A460
0x18000a417  mov     rcx, [rbx+10h]
0x18000a41b  lea     r9, [rsp+68h+pvarg]
0x18000a420  mov     [rsp+68h+var_40], 0
0x18000a429  lea     rdx, aPath; "__Path"
0x18000a430  xor     r8d, r8d
0x18000a433  mov     [rsp+68h+var_48], 0
0x18000a43c  mov     rax, [rcx]
0x18000a43f  mov     rax, [rax+20h]
0x18000a443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a448  mov     ebx, eax
0x18000a44a  test    eax, eax
0x18000a44c  js      short loc_18000A465
0x18000a44e  lea     rdx, [rsp+68h+pvarg]; pvargSrc
0x18000a453  mov     rcx, rdi; pvargDest
0x18000a456  call    cs:__imp_VariantCopy
0x18000a45c  mov     ebx, eax
0x18000a45e  jmp     short loc_18000A465
0x18000a460  mov     ebx, 80070057h
0x18000a465  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18000a46a  call    cs:__imp_VariantClear
0x18000a470  mov     eax, ebx
0x18000a472  mov     rbx, [rsp+68h+arg_0]
0x18000a477  add     rsp, 60h
0x18000a47b  pop     rdi
0x18000a47c  retn
```
