# CPersistStreamInit::WriteVARIANTColumnDataToStream(tagVARIANT *,uchar,uchar)

- ea: `0x18001fec8`
- end: `0x18001fff0`
- name: `?WriteVARIANTColumnDataToStream@CPersistStreamInit@@AEAAJPEAUtagVARIANT@@EE@Z`
- size: `296`
- prototype: `__int64 __fastcall(CPersistStreamInit *__hidden this, VARIANTARG *pvarg, unsigned __int8, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001d350`

## callees

- `0x18001b558`
- `0x18001d2e4`
- `0x18001fec8`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001ff91`
- `OLEAUT32!__imp_VariantInit` at `0x18001ff91`
- `OLEAUT32!__imp_VariantClear` at `0x18001ffc5`
- `OLEAUT32!__imp_VariantClear` at `0x18001ffc5`

## pseudocode

```c
__int64 __fastcall CPersistStreamInit::WriteVARIANTColumnDataToStream(CPersistStreamInit *this, VARIANTARG *pvarg)
{
  VARTYPE vt; // r10
  int v5; // edx
  __int64 result; // rax
  unsigned int v7; // edi
  unsigned __int16 *bstrVal; // [rsp+98h] [rbp+10h] BYREF

  vt = pvarg->vt;
  v5 = pvarg->vt - 1;
  if ( !v5 )
    return 2147500037LL;
  if ( v5 == 8208 )
  {
    v7 = CPersistStreamInit::BinaryOut(this, *(unsigned __int8 **)(pvarg->llVal + 16), *(_DWORD *)(pvarg->llVal + 24));
    goto LABEL_9;
  }
  bstrVal = 0;
  if ( vt == 8 )
  {
    v7 = 0;
    bstrVal = pvarg->bstrVal;
    VariantInit(pvarg);
    goto LABEL_7;
  }
  result = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 24LL))(*((_QWORD *)this + 5), 12);
  v7 = result;
  if ( (int)result >= 0 )
  {
LABEL_7:
    CPersistStreamInit::WriteBSTRColumnDataToStream(this, &bstrVal);
LABEL_9:
    VariantClear(pvarg);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x18001fec8  mov     rax, rsp
0x18001fecb  mov     [rax+8], rbx
0x18001fecf  mov     [rax+18h], rsi
0x18001fed3  push    rdi
0x18001fed4  sub     rsp, 80h
0x18001fedb  movzx   r10d, word ptr [rdx]
0x18001fedf  mov     rbx, rdx
0x18001fee2  mov     edx, r10d
0x18001fee5  mov     qword ptr [rax-18h], 0
0x18001feed  mov     r11b, r8b
0x18001fef0  mov     rsi, rcx
0x18001fef3  sub     edx, 1
0x18001fef6  jz      loc_18001FFD5
0x18001fefc  cmp     edx, 2010h
0x18001ff02  jz      loc_18001FFAF
0x18001ff08  mov     r8d, 8
0x18001ff0e  mov     qword ptr [rax+10h], 0
0x18001ff16  cmp     r10w, r8w
0x18001ff1a  jz      short loc_18001FF80
0x18001ff1c  mov     rcx, [rcx+28h]
0x18001ff20  lea     r10, [rsp+88h+arg_8]
0x18001ff28  mov     [rsp+88h+var_28], 0
0x18001ff30  lea     edx, [r8+4]
0x18001ff34  mov     [rsp+88h+var_30], r9b
0x18001ff39  lea     r9d, [r8+10h]
0x18001ff3d  mov     [rsp+88h+var_38], r11b
0x18001ff42  mov     rax, [rcx]
0x18001ff45  mov     [rsp+88h+var_40], 0
0x18001ff4e  mov     [rsp+88h+var_48], 0
0x18001ff56  mov     [rsp+88h+var_50], r9
0x18001ff5b  mov     rax, [rax+18h]
0x18001ff5f  mov     [rsp+88h+var_58], r10
0x18001ff64  lea     r10, [rsp+88h+var_18]
0x18001ff69  mov     [rsp+88h+var_60], rbx
0x18001ff6e  mov     [rsp+88h+var_68], r10
0x18001ff73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff78  mov     edi, eax
0x18001ff7a  test    eax, eax
0x18001ff7c  jns     short loc_18001FF9D
0x18001ff7e  jmp     short loc_18001FFDA
0x18001ff80  mov     rax, [rbx+8]
0x18001ff84  xor     edi, edi
0x18001ff86  mov     rcx, rbx; pvarg
0x18001ff89  mov     [rsp+88h+arg_8], rax
0x18001ff91  call    cs:__imp_VariantInit
0x18001ff98  nop     dword ptr [rax+rax+00h]
0x18001ff9d  lea     rdx, [rsp+88h+arg_8]; unsigned __int16 **
0x18001ffa5  mov     rcx, rsi; this
0x18001ffa8  call    ?WriteBSTRColumnDataToStream@CPersistStreamInit@@AEAAJPEAPEAG@Z; CPersistStreamInit::WriteBSTRColumnDataToStream(ushort * *)
0x18001ffad  jmp     short loc_18001FFC2
0x18001ffaf  mov     rdx, [rbx+8]
0x18001ffb3  mov     r8d, [rdx+18h]; unsigned int
0x18001ffb7  mov     rdx, [rdx+10h]; unsigned __int8 *
0x18001ffbb  call    ?BinaryOut@CPersistStreamInit@@AEAAJPEAEK@Z; CPersistStreamInit::BinaryOut(uchar *,ulong)
0x18001ffc0  mov     edi, eax
0x18001ffc2  mov     rcx, rbx; pvarg
0x18001ffc5  call    cs:__imp_VariantClear
0x18001ffcc  nop     dword ptr [rax+rax+00h]
0x18001ffd1  mov     eax, edi
0x18001ffd3  jmp     short loc_18001FFDA
0x18001ffd5  mov     eax, 80004005h
0x18001ffda  lea     r11, [rsp+88h+var_8]
0x18001ffe2  mov     rbx, [r11+10h]
0x18001ffe6  mov     rsi, [r11+20h]
0x18001ffea  mov     rsp, r11
0x18001ffed  pop     rdi
0x18001ffee  retn
```
