# CSharedAccessStatEngine::InvokeVoidAction(IUPnPService *,ushort *,tagVARIANT *)

- ea: `0x180056b14`
- end: `0x180056c2d`
- name: `?InvokeVoidAction@CSharedAccessStatEngine@@CAJPEAUIUPnPService@@PEAGPEAUtagVARIANT@@@Z`
- size: `281`
- prototype: `static int(struct IUPnPService *, unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180056e54`

## callees

- `0x180056b14`
- `0x180065010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180056b35`
- `OLEAUT32!__imp_SysAllocString` at `0x180056b35`
- `OLEAUT32!__imp_SysFreeString` at `0x180056c06`
- `OLEAUT32!__imp_SysFreeString` at `0x180056c06`
- `OLEAUT32!__imp_VariantInit` at `0x180056b89`
- `OLEAUT32!__imp_VariantInit` at `0x180056b92`
- `OLEAUT32!__imp_VariantInit` at `0x180056b9c`
- `OLEAUT32!__imp_VariantInit` at `0x180056b89`
- `OLEAUT32!__imp_VariantInit` at `0x180056b92`
- `OLEAUT32!__imp_VariantInit` at `0x180056b9c`
- `OLEAUT32!__imp_VariantClear` at `0x180056bed`
- `OLEAUT32!__imp_VariantClear` at `0x180056bed`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180056b5b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180056b5b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180056bf6`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180056bf6`

## pseudocode

```c
__int64 __fastcall CSharedAccessStatEngine::InvokeVoidAction(
        struct IUPnPService *a1,
        unsigned __int16 *a2,
        struct tagVARIANT *a3)
{
  OLECHAR *v5; // rsi
  SAFEARRAY *v6; // rdi
  struct IUPnPServiceVtbl *lpVtbl; // rax
  HRESULT (__stdcall *InvokeAction)(IUPnPService *, BSTR, VARIANT, VARIANT *, VARIANT *); // rax
  int v9; // ebx
  VARIANTARG pvarg; // [rsp+30h] [rbp-50h] BYREF
  VARIANTARG v12; // [rsp+48h] [rbp-38h] BYREF
  __int128 v13; // [rsp+60h] [rbp-20h] BYREF
  IRecordInfo *pRecInfo; // [rsp+70h] [rbp-10h]
  SAFEARRAYBOUND rgsabound; // [rsp+B8h] [rbp+38h] BYREF

  v5 = SysAllocString(a2);
  if ( v5 )
  {
    rgsabound = 0;
    v6 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    if ( v6 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      memset(&v12, 0, sizeof(v12));
      VariantInit(&pvarg);
      VariantInit(a3);
      VariantInit(&v12);
      pvarg.llVal = (LONGLONG)v6;
      pvarg.vt = 8204;
      lpVtbl = a1->lpVtbl;
      pRecInfo = pvarg.pRecInfo;
      InvokeAction = lpVtbl->InvokeAction;
      v13 = *(_OWORD *)&pvarg.vt;
      v9 = ((__int64 (__fastcall *)(struct IUPnPService *, OLECHAR *, __int128 *, struct tagVARIANT *, VARIANTARG *))InvokeAction)(
             a1,
             v5,
             &v13,
             a3,
             &v12);
      if ( v9 >= 0 )
        VariantClear(&v12);
      SafeArrayDestroy(v6);
    }
    else
    {
      v9 = -2147024882;
    }
    SysFreeString(v5);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180056b14  mov     [rsp-18h+arg_0], rbx
0x180056b19  mov     [rsp-18h+arg_8], rsi
0x180056b1e  push    rbp
0x180056b1f  push    rdi
0x180056b20  push    r14
0x180056b22  mov     rbp, rsp
0x180056b25  sub     rsp, 80h
0x180056b2c  mov     r14, rcx
0x180056b2f  mov     rbx, r8
0x180056b32  mov     rcx, rdx; psz
0x180056b35  call    cs:__imp_SysAllocString
0x180056b3b  mov     rsi, rax
0x180056b3e  test    rax, rax
0x180056b41  jz      loc_180056C0E
0x180056b47  mov     ecx, 0Ch; vt
0x180056b4c  mov     qword ptr [rbp+rgsabound.cElements], 0
0x180056b54  lea     r8, [rbp+rgsabound]; rgsabound
0x180056b58  lea     edx, [rcx-0Bh]; cDims
0x180056b5b  call    cs:__imp_SafeArrayCreate
0x180056b61  mov     rdi, rax
0x180056b64  test    rax, rax
0x180056b67  jz      loc_180056BFE
0x180056b6d  xor     eax, eax
0x180056b6f  lea     rcx, [rbp+pvarg]; pvarg
0x180056b73  xorps   xmm0, xmm0
0x180056b76  mov     qword ptr [rbp+pvarg+10h], rax
0x180056b7a  xorps   xmm1, xmm1
0x180056b7d  mov     qword ptr [rbp+var_38+10h], rax
0x180056b81  movups  xmmword ptr [rbp+pvarg], xmm0
0x180056b85  movups  xmmword ptr [rbp+var_38], xmm1
0x180056b89  call    cs:__imp_VariantInit
0x180056b8f  mov     rcx, rbx; pvarg
0x180056b92  call    cs:__imp_VariantInit
0x180056b98  lea     rcx, [rbp+var_38]; pvarg
0x180056b9c  call    cs:__imp_VariantInit
0x180056ba2  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180056ba7  lea     rcx, [rbp+var_38]
0x180056bab  mov     eax, 200Ch
0x180056bb0  mov     qword ptr [rbp+pvarg+8], rdi
0x180056bb4  mov     word ptr [rbp+pvarg], ax
0x180056bb8  lea     r8, [rbp+var_20]
0x180056bbc  mov     rax, [r14]
0x180056bbf  mov     r9, rbx
0x180056bc2  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180056bc6  mov     [rsp+80h+var_60], rcx
0x180056bcb  mov     rdx, rsi
0x180056bce  mov     rcx, r14
0x180056bd1  movsd   [rbp+var_10], xmm1
0x180056bd6  mov     rax, [rax+40h]
0x180056bda  movaps  [rbp+var_20], xmm0
0x180056bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056be3  mov     ebx, eax
0x180056be5  test    eax, eax
0x180056be7  js      short loc_180056BF3
0x180056be9  lea     rcx, [rbp+var_38]; pvarg
0x180056bed  call    cs:__imp_VariantClear
0x180056bf3  mov     rcx, rdi; psa
0x180056bf6  call    cs:__imp_SafeArrayDestroy
0x180056bfc  jmp     short loc_180056C03
0x180056bfe  mov     ebx, 8007000Eh
0x180056c03  mov     rcx, rsi; bstrString
0x180056c06  call    cs:__imp_SysFreeString
0x180056c0c  jmp     short loc_180056C13
0x180056c0e  mov     ebx, 8007000Eh
0x180056c13  lea     r11, [rsp+80h+var_s0]
0x180056c1b  mov     eax, ebx
0x180056c1d  mov     rbx, [r11+20h]
0x180056c21  mov     rsi, [r11+28h]
0x180056c25  mov     rsp, r11
0x180056c28  pop     r14
0x180056c2a  pop     rdi
0x180056c2b  pop     rbp
0x180056c2c  retn
```
