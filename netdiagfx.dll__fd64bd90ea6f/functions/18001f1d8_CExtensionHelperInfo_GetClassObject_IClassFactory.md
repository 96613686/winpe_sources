# CExtensionHelperInfo::GetClassObject(IClassFactory * *)

- ea: `0x18001f1d8`
- end: `0x18001f2f1`
- name: `?GetClassObject@CExtensionHelperInfo@@QEAAJPEAPEAUIClassFactory@@@Z`
- size: `281`
- prototype: `HRESULT __fastcall(CExtensionHelperInfo *this, LPVOID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001dfa4`

## callees

- `0x180008c84`
- `0x180011208`
- `0x180011298`
- `0x18001f1d8`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18001f221`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18001f221`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall CExtensionHelperInfo::GetClassObject(CExtensionHelperInfo *this, LPVOID *a2)
{
  HRESULT result; // eax
  unsigned int v5; // eax
  struct _GUID v6; // [rsp+30h] [rbp-20h] BYREF
  struct _GUID v7; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v8; // [rsp+78h] [rbp+28h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp+30h] BYREF
  struct INetDiagHelperInfo *v10; // [rsp+88h] [rbp+38h] BYREF

  if ( !a2 )
    return -2147024809;
  ppv = 0;
  if ( *((_DWORD *)this + 17) )
  {
    result = CoGetClassObject((const IID *const)((char *)this + 8), 1u, 0, &IID_IClassFactory, &ppv);
  }
  else
  {
    v6 = IID_IClassFactory;
    v7 = *(struct _GUID *)((char *)this + 8);
    result = ProtectedOutOfProcGetClassObject(&v7, &v6, &ppv);
  }
  if ( result >= 0 )
  {
    if ( *((_QWORD *)this + 7) )
    {
      *a2 = ppv;
    }
    else
    {
      v10 = 0;
      if ( (*(int (__fastcall **)(LPVOID, _QWORD, GUID *, struct INetDiagHelperInfo **))(*(_QWORD *)ppv + 24LL))(
             ppv,
             0,
             &IID_INetDiagHelperInfo,
             &v10) >= 0 )
      {
        v8 = 0;
        *(_QWORD *)&v6.Data1 = 0;
        if ( (int)ProtectedGetAttributeInfo(v10, &v8, (struct tagHelperAttributeInfo **)&v6, *((_DWORD *)this + 17)) >= 0 )
        {
          v5 = v8;
          if ( v8 )
          {
            if ( *(_QWORD *)&v6.Data1 )
            {
              *((_QWORD *)this + 7) = *(_QWORD *)&v6.Data1;
              *((_DWORD *)this + 16) = v5;
            }
          }
        }
      }
      *a2 = ppv;
      ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>((__int64 *)&v10);
    }
    return 0;
  }
  else
  {
    *a2 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001f1d8  push    rbp
0x18001f1da  push    rbx
0x18001f1db  push    rdi
0x18001f1dc  mov     rbp, rsp
0x18001f1df  sub     rsp, 50h
0x18001f1e3  mov     rdi, rdx
0x18001f1e6  mov     rbx, rcx
0x18001f1e9  test    rdx, rdx
0x18001f1ec  jnz     short loc_18001F1F8
0x18001f1ee  mov     eax, 80070057h
0x18001f1f3  jmp     loc_18001F2E9
0x18001f1f8  mov     [rbp+arg_10], 0
0x18001f200  cmp     dword ptr [rcx+44h], 0
0x18001f204  jz      short loc_18001F229
0x18001f206  lea     rcx, [rbp+arg_10]
0x18001f20a  mov     [rsp+50h+ppv], rcx; ppv
0x18001f20f  lea     r9, IID_IClassFactory; riid
0x18001f216  xor     r8d, r8d; pvReserved
0x18001f219  lea     edx, [r8+1]; dwClsContext
0x18001f21d  lea     rcx, [rbx+8]; rclsid
0x18001f221  call    cs:__imp_CoGetClassObject
0x18001f227  jmp     short loc_18001F24F
0x18001f229  movups  xmm0, xmmword ptr cs:IID_IClassFactory.Data1
0x18001f230  movdqu  xmmword ptr [rbp+var_20.Data1], xmm0
0x18001f235  movups  xmm0, xmmword ptr [rcx+8]
0x18001f239  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x18001f23e  lea     r8, [rbp+arg_10]; void **
0x18001f242  lea     rdx, [rbp+var_20]; struct _GUID
0x18001f246  lea     rcx, [rbp+var_10]; struct _GUID
0x18001f24a  call    ?ProtectedOutOfProcGetClassObject@@YAJU_GUID@@0PEAPEAX@Z; ProtectedOutOfProcGetClassObject(_GUID,_GUID,void * *)
0x18001f24f  test    eax, eax
0x18001f251  jns     short loc_18001F25F
0x18001f253  mov     qword ptr [rdi], 0
0x18001f25a  jmp     loc_18001F2E9
0x18001f25f  cmp     qword ptr [rbx+38h], 0
0x18001f264  jz      short loc_18001F26F
0x18001f266  mov     rax, [rbp+arg_10]
0x18001f26a  mov     [rdi], rax
0x18001f26d  jmp     short loc_18001F2E7
0x18001f26f  mov     [rbp+arg_18], 0
0x18001f277  mov     rcx, [rbp+arg_10]
0x18001f27b  mov     rax, [rcx]
0x18001f27e  lea     r9, [rbp+arg_18]
0x18001f282  lea     r8, IID_INetDiagHelperInfo
0x18001f289  xor     edx, edx
0x18001f28b  mov     rax, [rax+18h]
0x18001f28f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f294  test    eax, eax
0x18001f296  js      short loc_18001F2D7
0x18001f298  mov     [rbp+arg_8], 0
0x18001f29f  mov     qword ptr [rbp+var_20.Data1], 0
0x18001f2a7  mov     r9d, [rbx+44h]; int
0x18001f2ab  lea     r8, [rbp+var_20]; struct tagHelperAttributeInfo **
0x18001f2af  lea     rdx, [rbp+arg_8]; unsigned int *
0x18001f2b3  mov     rcx, [rbp+arg_18]; struct INetDiagHelperInfo *
0x18001f2b7  call    ?ProtectedGetAttributeInfo@@YAJPEAUINetDiagHelperInfo@@PEAKPEAPEAUtagHelperAttributeInfo@@H@Z; ProtectedGetAttributeInfo(INetDiagHelperInfo *,ulong *,tagHelperAttributeInfo * *,int)
0x18001f2bc  test    eax, eax
0x18001f2be  js      short loc_18001F2D7
0x18001f2c0  mov     eax, [rbp+arg_8]
0x18001f2c3  test    eax, eax
0x18001f2c5  jz      short loc_18001F2D7
0x18001f2c7  mov     rcx, qword ptr [rbp+var_20.Data1]
0x18001f2cb  test    rcx, rcx
0x18001f2ce  jz      short loc_18001F2D7
0x18001f2d0  mov     [rbx+38h], rcx
0x18001f2d4  mov     [rbx+40h], eax
0x18001f2d7  mov     rax, [rbp+arg_10]
0x18001f2db  mov     [rdi], rax
0x18001f2de  lea     rcx, [rbp+arg_18]
0x18001f2e2  call    ??1?$CComPtrBase@UINDFHelperClass@@@ATL@@QEAA@XZ; ATL::CComPtrBase<INDFHelperClass>::~CComPtrBase<INDFHelperClass>(void)
0x18001f2e7  xor     eax, eax
0x18001f2e9  add     rsp, 50h
0x18001f2ed  pop     rdi
0x18001f2ee  pop     rbx
0x18001f2ef  pop     rbp
0x18001f2f0  retn
```
