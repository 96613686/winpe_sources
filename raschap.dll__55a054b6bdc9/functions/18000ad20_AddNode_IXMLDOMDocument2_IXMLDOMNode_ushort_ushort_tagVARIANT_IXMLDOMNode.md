# AddNode(IXMLDOMDocument2 *,IXMLDOMNode *,ushort *,ushort *,tagVARIANT,IXMLDOMNode * *)

- ea: `0x18000ad20`
- end: `0x18000ae53`
- name: `?AddNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAG2UtagVARIANT@@PEAPEAU2@@Z`
- size: `307`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, unsigned __int16 *, unsigned __int16 *, struct tagVARIANT *, struct IXMLDOMNode **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005430`

## callees

- `0x18000ad20`
- `0x180027010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000ad56`
- `OLEAUT32!__imp_VariantInit` at `0x18000ad56`
- `OLEAUT32!__imp_VariantClear` at `0x18000adb5`
- `OLEAUT32!__imp_VariantClear` at `0x18000adb5`

## pseudocode

```c
__int64 __fastcall AddNode(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct tagVARIANT *a5,
        struct IXMLDOMNode **a6)
{
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  HRESULT (__stdcall *createNode)(IXMLDOMDocument2 *, VARIANT, BSTR, BSTR, IXMLDOMNode **); // rax
  unsigned int v12; // ebx
  __int128 v13; // xmm0
  IRecordInfo *pRecInfo; // xmm1_8
  __int64 v15; // rax
  VARIANTARG pvarg; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v18[72]; // [rsp+50h] [rbp-48h] BYREF
  __int64 *v19; // [rsp+A0h] [rbp+8h] BYREF

  v19 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.lVal = 1;
  pvarg.vt = 3;
  lpVtbl = a1->lpVtbl;
  *(_QWORD *)&v18[16] = pvarg.pRecInfo;
  createNode = lpVtbl->createNode;
  *(_OWORD *)v18 = *(_OWORD *)&pvarg.vt;
  v12 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, _BYTE *, unsigned __int16 *, unsigned __int16 *, __int64 **))createNode)(
          a1,
          v18,
          a4,
          a3,
          &v19);
  VariantClear(&pvarg);
  if ( !v12 )
  {
    if ( !a5->vt
      || (v13 = *(_OWORD *)&a5->decVal.scale,
          pRecInfo = a5->pRecInfo,
          *(_WORD *)v18 = a5->vt,
          *(_OWORD *)&v18[2] = v13,
          v15 = *v19,
          *(_QWORD *)&v18[16] = pRecInfo,
          (v12 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(v15 + 248))(v19, v18)) == 0) )
    {
      v12 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *, struct IXMLDOMNode **))a2->lpVtbl->appendChild)(
              a2,
              v19,
              a6);
    }
  }
  if ( v19 )
    (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
  return v12;
}

```

## disassembly

```asm
0x18000ad20  push    rbx
0x18000ad22  push    rsi
0x18000ad23  push    rdi
0x18000ad24  push    r14
0x18000ad26  sub     rsp, 78h
0x18000ad2a  mov     rdi, rcx
0x18000ad2d  mov     [rsp+98h+arg_0], 0
0x18000ad39  xorps   xmm0, xmm0
0x18000ad3c  lea     rcx, [rsp+98h+pvarg]; pvarg
0x18000ad41  xor     eax, eax
0x18000ad43  mov     rsi, r9
0x18000ad46  movups  xmmword ptr [rsp+98h+pvarg], xmm0
0x18000ad4b  mov     qword ptr [rsp+98h+pvarg+10h], rax
0x18000ad50  mov     rbx, r8
0x18000ad53  mov     r14, rdx
0x18000ad56  call    cs:__imp_VariantInit
0x18000ad5c  movsd   xmm1, qword ptr [rsp+98h+pvarg+10h]
0x18000ad62  lea     rcx, [rsp+98h+arg_0]
0x18000ad6a  mov     eax, 3
0x18000ad6f  mov     dword ptr [rsp+98h+pvarg+8], 1
0x18000ad77  mov     word ptr [rsp+98h+pvarg], ax
0x18000ad7c  lea     rdx, [rsp+98h+var_48]
0x18000ad81  mov     rax, [rdi]
0x18000ad84  mov     r9, rbx
0x18000ad87  movups  xmm0, xmmword ptr [rsp+98h+pvarg]
0x18000ad8c  mov     [rsp+98h+var_78], rcx
0x18000ad91  mov     r8, rsi
0x18000ad94  mov     rcx, rdi
0x18000ad97  movsd   [rsp+98h+var_38], xmm1
0x18000ad9d  mov     rax, [rax+1C0h]
0x18000ada4  movaps  [rsp+98h+var_48], xmm0
0x18000ada9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adae  lea     rcx, [rsp+98h+pvarg]; pvarg
0x18000adb3  mov     ebx, eax
0x18000adb5  call    cs:__imp_VariantClear
0x18000adbb  test    ebx, ebx
0x18000adbd  jnz     short loc_18000AE2E
0x18000adbf  mov     rax, [rsp+98h+arg_20]
0x18000adc7  movzx   edx, word ptr [rax]
0x18000adca  test    dx, dx
0x18000adcd  jz      short loc_18000AE0A
0x18000adcf  movups  xmm0, xmmword ptr [rax+2]
0x18000add3  mov     rcx, [rsp+98h+arg_0]
0x18000addb  movsd   xmm1, qword ptr [rax+10h]
0x18000ade0  mov     word ptr [rsp+98h+var_48], dx
0x18000ade5  lea     rdx, [rsp+98h+var_48]
0x18000adea  movups  [rsp+98h+var_48+2], xmm0
0x18000adef  mov     rax, [rcx]
0x18000adf2  movsd   [rsp+98h+var_38], xmm1
0x18000adf8  mov     rax, [rax+0F8h]
0x18000adff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae04  mov     ebx, eax
0x18000ae06  test    eax, eax
0x18000ae08  jnz     short loc_18000AE2E
0x18000ae0a  mov     rax, [r14]
0x18000ae0d  mov     rcx, r14
0x18000ae10  mov     r8, [rsp+98h+arg_28]
0x18000ae18  mov     rdx, [rsp+98h+arg_0]
0x18000ae20  mov     rax, [rax+0A8h]
0x18000ae27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae2c  mov     ebx, eax
0x18000ae2e  mov     rcx, [rsp+98h+arg_0]
0x18000ae36  test    rcx, rcx
0x18000ae39  jz      short loc_18000AE47
0x18000ae3b  mov     rax, [rcx]
0x18000ae3e  mov     rax, [rax+10h]
0x18000ae42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae47  mov     eax, ebx
0x18000ae49  add     rsp, 78h
0x18000ae4d  pop     r14
0x18000ae4f  pop     rdi
0x18000ae50  pop     rsi
0x18000ae51  pop     rbx
0x18000ae52  retn
```
