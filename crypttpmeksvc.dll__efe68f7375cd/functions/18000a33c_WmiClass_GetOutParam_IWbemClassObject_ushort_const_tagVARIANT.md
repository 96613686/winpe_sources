# WmiClass::GetOutParam(IWbemClassObject *,ushort const *,tagVARIANT *)

- ea: `0x18000a33c`
- end: `0x18000a3e2`
- name: `?GetOutParam@WmiClass@@QEAAJPEAUIWbemClassObject@@PEBGPEAUtagVARIANT@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(WmiClass *this, struct IWbemClassObject *, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009f34`

## callees

- `0x18000a33c`
- `0x18000b010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000a367`
- `OLEAUT32!__imp_VariantInit` at `0x18000a367`
- `OLEAUT32!__imp_VariantClear` at `0x18000a3ca`
- `OLEAUT32!__imp_VariantClear` at `0x18000a3ca`
- `OLEAUT32!__imp_VariantCopy` at `0x18000a3b6`
- `OLEAUT32!__imp_VariantCopy` at `0x18000a3b6`

## pseudocode

```c
__int64 __fastcall WmiClass::GetOutParam(
        WmiClass *this,
        struct IWbemClassObject *a2,
        const unsigned __int16 *a3,
        struct tagVARIANT *a4)
{
  HRESULT v7; // ebx
  VARIANTARG pvargSrc; // [rsp+40h] [rbp-28h] BYREF

  memset(&pvargSrc, 0, sizeof(pvargSrc));
  VariantInit(&pvargSrc);
  if ( a2 && a3 && a4 )
  {
    v7 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a2->lpVtbl->Get)(
           a2,
           a3,
           0,
           &pvargSrc,
           0,
           0);
    if ( v7 >= 0 )
      v7 = VariantCopy(a4, &pvargSrc);
  }
  else
  {
    v7 = -2147024809;
  }
  VariantClear(&pvargSrc);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000a33c  mov     r11, rsp
0x18000a33f  mov     [r11+8], rbx
0x18000a343  mov     [r11+10h], rsi
0x18000a347  push    rdi
0x18000a348  sub     rsp, 60h
0x18000a34c  xorps   xmm0, xmm0
0x18000a34f  lea     rcx, [r11-28h]; pvarg
0x18000a353  xor     eax, eax
0x18000a355  mov     rdi, r9
0x18000a358  movups  xmmword ptr [rsp+68h+pvargSrc], xmm0
0x18000a35d  mov     [r11-18h], rax
0x18000a361  mov     rbx, r8
0x18000a364  mov     rsi, rdx
0x18000a367  call    cs:__imp_VariantInit
0x18000a36d  test    rsi, rsi
0x18000a370  jz      short loc_18000A3C0
0x18000a372  test    rbx, rbx
0x18000a375  jz      short loc_18000A3C0
0x18000a377  test    rdi, rdi
0x18000a37a  jz      short loc_18000A3C0
0x18000a37c  mov     rax, [rsi]
0x18000a37f  lea     r9, [rsp+68h+pvargSrc]
0x18000a384  mov     [rsp+68h+var_40], 0
0x18000a38d  xor     r8d, r8d
0x18000a390  mov     rdx, rbx
0x18000a393  mov     [rsp+68h+var_48], 0
0x18000a39c  mov     rcx, rsi
0x18000a39f  mov     rax, [rax+20h]
0x18000a3a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3a8  mov     ebx, eax
0x18000a3aa  test    eax, eax
0x18000a3ac  js      short loc_18000A3C5
0x18000a3ae  lea     rdx, [rsp+68h+pvargSrc]; pvargSrc
0x18000a3b3  mov     rcx, rdi; pvargDest
0x18000a3b6  call    cs:__imp_VariantCopy
0x18000a3bc  mov     ebx, eax
0x18000a3be  jmp     short loc_18000A3C5
0x18000a3c0  mov     ebx, 80070057h
0x18000a3c5  lea     rcx, [rsp+68h+pvargSrc]; pvarg
0x18000a3ca  call    cs:__imp_VariantClear
0x18000a3d0  mov     rsi, [rsp+68h+arg_8]
0x18000a3d5  mov     eax, ebx
0x18000a3d7  mov     rbx, [rsp+68h+arg_0]
0x18000a3dc  add     rsp, 60h
0x18000a3e0  pop     rdi
0x18000a3e1  retn
```
