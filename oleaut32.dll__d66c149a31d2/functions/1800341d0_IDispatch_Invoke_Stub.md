# IDispatch_Invoke_Stub

- ea: `0x1800341d0`
- end: `0x1800342e0`
- name: `IDispatch_Invoke_Stub`
- size: `272`
- prototype: `HRESULT __stdcall(IDispatch *This, DISPID dispIdMember, const IID *const riid, LCID lcid, DWORD dwFlags, DISPPARAMS *pDispParams, VARIANT *pVarResult, EXCEPINFO *pExcepInfo, UINT *pArgErr, UINT cVarRef, UINT *rgVarRefIdx, VARIANTARG *rgVarRef)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180034160`

## callees

- `0x1800341d0`
- `0x1800342e8`
- `0x180034434`
- `0x18009c010`

## import_xrefs

- `combase!DcomChannelSetHResult` at `0x1800342c7`
- `combase!DcomChannelSetHResult` at `0x1800342c7`

## pseudocode

```c
HRESULT __stdcall IDispatch_Invoke_Stub(
        IDispatch *This,
        DISPID dispIdMember,
        const IID *const riid,
        LCID lcid,
        DWORD dwFlags,
        DISPPARAMS *pDispParams,
        VARIANT *pVarResult,
        EXCEPINFO *pExcepInfo,
        UINT *pArgErr,
        UINT cVarRef,
        UINT *rgVarRefIdx,
        VARIANTARG *rgVarRef)
{
  unsigned int *v12; // rsi
  UINT v14; // ebp
  HRESULT v17; // ebx
  EXCEPINFO *v18; // rbx
  int v19; // eax
  int v21; // [rsp+20h] [rbp-88h]
  VARIANT *v22; // [rsp+30h] [rbp-78h]
  unsigned __int16 *v23; // [rsp+50h] [rbp-58h] BYREF

  v12 = rgVarRefIdx;
  v14 = cVarRef;
  v23 = 0;
  v17 = InvokeStubPreCheck(
          pDispParams,
          &v23,
          dwFlags,
          &pVarResult,
          &pExcepInfo,
          &pArgErr,
          cVarRef,
          rgVarRefIdx,
          rgVarRef);
  if ( v17 >= 0 )
  {
    v18 = pExcepInfo;
    v22 = pVarResult;
    LOWORD(v21) = dwFlags;
    v19 = ((__int64 (__fastcall *)(IDispatch *, _QWORD, const IID *const, _QWORD, int, DISPPARAMS *))This->lpVtbl->Invoke)(
            This,
            (unsigned int)dispIdMember,
            riid,
            lcid,
            v21,
            pDispParams);
    v17 = InvokeStubPostCheck(v19, pDispParams, v18, v23, v14, v12, v22);
  }
  DcomChannelSetHResult(0, 0, v17);
  return v17;
}

```

## disassembly

```asm
0x1800341d0  mov     [rsp+arg_8], edx
0x1800341d4  mov     r11, rsp
0x1800341d7  push    rbx
0x1800341d8  push    rbp
0x1800341d9  push    rsi
0x1800341da  push    rdi
0x1800341db  push    r12
0x1800341dd  push    r13
0x1800341df  push    r14
0x1800341e1  push    r15
0x1800341e3  sub     rsp, 68h
0x1800341e7  mov     rax, [rsp+0A8h+rgVarRef]
0x1800341ef  lea     rdx, [r11-58h]; unsigned __int16 **
0x1800341f3  mov     rsi, [rsp+0A8h+rgVarRefIdx]
0x1800341fb  mov     r12d, r9d
0x1800341fe  mov     ebp, [rsp+0A8h+cVarRef]
0x180034205  lea     r9, [r11+38h]; struct tagVARIANT **
0x180034209  mov     rdi, [rsp+0A8h+pDispParams]
0x180034211  mov     r13, r8
0x180034214  mov     r14d, [rsp+0A8h+dwFlags]
0x18003421c  mov     r15, rcx
0x18003421f  mov     [r11-68h], rax
0x180034223  mov     r8d, r14d; unsigned int
0x180034226  mov     [r11-70h], rsi
0x18003422a  lea     rax, [r11+48h]
0x18003422e  mov     dword ptr [rsp+0A8h+var_78], ebp; unsigned int
0x180034232  mov     rcx, rdi; struct tagDISPPARAMS *
0x180034235  mov     [r11-80h], rax
0x180034239  lea     rax, [r11+40h]
0x18003423d  mov     [rsp+0A8h+var_88], rax; struct tagEXCEPINFO **
0x180034242  mov     qword ptr [r11-58h], 0
0x18003424a  call    ?InvokeStubPreCheck@@YAJPEAUtagDISPPARAMS@@PEAPEAGKPEAPEAUtagVARIANT@@PEAPEAUtagEXCEPINFO@@PEAPEAIIPEAIPEAU2@@Z; InvokeStubPreCheck(tagDISPPARAMS *,ushort * *,ulong,tagVARIANT * *,tagEXCEPINFO * *,uint * *,uint,uint *,tagVARIANT *)
0x18003424f  mov     ebx, eax
0x180034251  test    eax, eax
0x180034253  js      short loc_1800342C0
0x180034255  mov     rcx, [rsp+0A8h+pArgErr]
0x18003425d  mov     r9d, r12d
0x180034260  mov     rax, [r15]
0x180034263  mov     r8, r13
0x180034266  mov     rbx, [rsp+0A8h+pExcepInfo]
0x18003426e  mov     edx, [rsp+0A8h+arg_8]
0x180034275  mov     [rsp+0A8h+var_68], rcx
0x18003427a  mov     rcx, [rsp+0A8h+pVarResult]
0x180034282  mov     rax, [rax+30h]
0x180034286  mov     [rsp+0A8h+var_70], rbx
0x18003428b  mov     [rsp+0A8h+var_78], rcx; struct tagVARIANT *
0x180034290  mov     rcx, r15
0x180034293  mov     [rsp+0A8h+var_80], rdi
0x180034298  mov     word ptr [rsp+0A8h+var_88], r14w
0x18003429e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800342a3  mov     r9, [rsp+0A8h+var_58]; unsigned __int16 *
0x1800342a8  mov     r8, rbx; struct tagEXCEPINFO *
0x1800342ab  mov     rdx, rdi; struct tagDISPPARAMS *
0x1800342ae  mov     [rsp+0A8h+var_80], rsi; unsigned int *
0x1800342b3  mov     ecx, eax; int
0x1800342b5  mov     dword ptr [rsp+0A8h+var_88], ebp; unsigned int
0x1800342b9  call    ?InvokeStubPostCheck@@YAJJPEAUtagDISPPARAMS@@PEAUtagEXCEPINFO@@PEAGIPEAIPEAUtagVARIANT@@@Z; InvokeStubPostCheck(long,tagDISPPARAMS *,tagEXCEPINFO *,ushort *,uint,uint *,tagVARIANT *)
0x1800342be  mov     ebx, eax
0x1800342c0  mov     r8d, ebx; appsHR
0x1800342c3  xor     edx, edx; pulReserved
0x1800342c5  xor     ecx, ecx; pvReserved
0x1800342c7  call    cs:__imp_DcomChannelSetHResult
0x1800342cd  mov     eax, ebx
0x1800342cf  add     rsp, 68h
0x1800342d3  pop     r15
0x1800342d5  pop     r14
0x1800342d7  pop     r13
0x1800342d9  pop     r12
0x1800342db  pop     rdi
0x1800342dc  pop     rsi
0x1800342dd  pop     rbp
0x1800342de  pop     rbx
0x1800342df  retn
```
