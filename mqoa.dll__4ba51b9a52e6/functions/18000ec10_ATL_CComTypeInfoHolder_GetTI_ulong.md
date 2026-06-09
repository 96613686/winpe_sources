# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x18000ec10`
- end: `0x18000edb7`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `423`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000eb24`
- `0x18000efb4`
- `0x18000fa18`

## callees

- `0x18000173c`
- `0x1800033ec`
- `0x1800095d4`
- `0x18000ec10`
- `0x18000fae0`
- `0x180029010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000ec42`
- `KERNEL32!EnterCriticalSection` at `0x18000ed2e`
- `KERNEL32!EnterCriticalSection` at `0x18000ec42`
- `KERNEL32!EnterCriticalSection` at `0x18000ed2e`
- `KERNEL32!LeaveCriticalSection` at `0x18000ed4d`
- `KERNEL32!LeaveCriticalSection` at `0x18000eda2`
- `KERNEL32!LeaveCriticalSection` at `0x18000ed4d`
- `KERNEL32!LeaveCriticalSection` at `0x18000eda2`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18000ec6f`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18000ec6f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID lcid)
{
  HRESULT NameCache; // edi
  struct IUnknown *v6; // rcx
  struct IUnknown *v7; // rsi
  _QWORD *v8; // rsi
  struct ITypeInfo *v9; // rdx
  ITypeLib *pptlib; // [rsp+30h] [rbp-10h] BYREF
  struct IUnknown *v11; // [rsp+60h] [rbp+20h] BYREF
  struct IUnknown *v12; // [rsp+70h] [rbp+30h] BYREF
  struct IUnknown *v13; // [rsp+78h] [rbp+38h] BYREF

  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    return 0;
  NameCache = 0;
  EnterCriticalSection(&Buf1);
  if ( !*((_QWORD *)this + 3) )
  {
    pptlib = 0;
    NameCache = LoadRegTypeLib(
                  *((const GUID *const *)this + 1),
                  *((_WORD *)this + 8),
                  *((_WORD *)this + 9),
                  lcid,
                  &pptlib);
    if ( NameCache >= 0 )
    {
      v12 = 0;
      NameCache = ((__int64 (__fastcall *)(ITypeLib *, _QWORD, struct IUnknown **))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                    pptlib,
                    *(_QWORD *)this,
                    &v12);
      if ( NameCache >= 0 )
      {
        v6 = v12;
        v7 = v12;
        v11 = v12;
        if ( v12 )
        {
          ((void (__fastcall *)(struct IUnknown *))v12->lpVtbl->AddRef)(v12);
          v6 = v12;
        }
        v13 = 0;
        if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v6->lpVtbl->QueryInterface)(
               v6,
               &GUID_00020412_0000_0000_c000_000000000046,
               &v13) >= 0 )
        {
          ATL::AtlComPtrAssign(&v11, v13);
          v7 = v11;
        }
        v11 = 0;
        *((_QWORD *)this + 3) = v7;
        v8 = operator new(0x18u);
        if ( v8 )
        {
          *v8 = ATL::CComTypeInfoHolder::Cleanup;
          v8[1] = this;
          EnterCriticalSection(&Buf1);
          v8[2] = Block;
          Block = v8;
          LeaveCriticalSection(&Buf1);
        }
        R<IADs>::~R<IADs>(&v13);
        R<IADs>::~R<IADs>(&v11);
      }
      ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
      R<IADs>::~R<IADs>(&v12);
    }
  }
  v9 = (struct ITypeInfo *)*((_QWORD *)this + 3);
  if ( v9 )
  {
    if ( !*((_QWORD *)this + 5) )
      NameCache = ATL::CComTypeInfoHolder::LoadNameCache(this, v9);
  }
  LeaveCriticalSection(&Buf1);
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x18000ec10  mov     [rsp-18h+arg_8], rbx
0x18000ec15  push    rbp
0x18000ec16  push    rsi
0x18000ec17  push    rdi
0x18000ec18  mov     rbp, rsp
0x18000ec1b  sub     rsp, 40h
0x18000ec1f  mov     esi, edx
0x18000ec21  mov     rbx, rcx
0x18000ec24  cmp     qword ptr [rcx+18h], 0
0x18000ec29  jz      short loc_18000EC39
0x18000ec2b  cmp     qword ptr [rcx+28h], 0
0x18000ec30  jz      short loc_18000EC39
0x18000ec32  xor     eax, eax
0x18000ec34  jmp     loc_18000EDAA
0x18000ec39  xor     edi, edi
0x18000ec3b  lea     rcx, Buf1; lpCriticalSection
0x18000ec42  call    cs:__imp_EnterCriticalSection
0x18000ec48  cmp     [rbx+18h], rdi
0x18000ec4c  jnz     loc_18000ED81
0x18000ec52  mov     [rbp+var_10], rdi
0x18000ec56  lea     rax, [rbp+var_10]
0x18000ec5a  mov     [rsp+40h+pptlib], rax; pptlib
0x18000ec5f  mov     r9d, esi; lcid
0x18000ec62  movzx   r8d, word ptr [rbx+12h]; wVerMinor
0x18000ec67  movzx   edx, word ptr [rbx+10h]; wVerMajor
0x18000ec6b  mov     rcx, [rbx+8]; rguid
0x18000ec6f  call    cs:__imp_LoadRegTypeLib
0x18000ec75  mov     edi, eax
0x18000ec77  test    eax, eax
0x18000ec79  js      loc_18000ED81
0x18000ec7f  mov     [rbp+arg_10], 0
0x18000ec87  mov     rcx, [rbp+var_10]
0x18000ec8b  mov     rax, [rcx]
0x18000ec8e  lea     r8, [rbp+arg_10]
0x18000ec92  mov     rdx, [rbx]
0x18000ec95  mov     rax, [rax+30h]
0x18000ec99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec9e  mov     edi, eax
0x18000eca0  test    eax, eax
0x18000eca2  js      loc_18000ED67
0x18000eca8  mov     rcx, [rbp+arg_10]
0x18000ecac  mov     rsi, rcx
0x18000ecaf  mov     [rbp+arg_0], rcx
0x18000ecb3  test    rcx, rcx
0x18000ecb6  jz      short loc_18000ECC8
0x18000ecb8  mov     rax, [rcx]
0x18000ecbb  mov     rax, [rax+8]
0x18000ecbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecc4  mov     rcx, [rbp+arg_10]
0x18000ecc8  mov     [rbp+arg_18], 0
0x18000ecd0  mov     rax, [rcx]
0x18000ecd3  lea     r8, [rbp+arg_18]
0x18000ecd7  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x18000ecde  mov     rax, [rax]
0x18000ece1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ece6  test    eax, eax
0x18000ece8  js      short loc_18000ECFB
0x18000ecea  mov     rdx, [rbp+arg_18]; struct IUnknown *
0x18000ecee  lea     rcx, [rbp+arg_0]; struct IUnknown **
0x18000ecf2  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000ecf7  mov     rsi, [rbp+arg_0]
0x18000ecfb  mov     [rbp+arg_0], 0
0x18000ed03  mov     [rbx+18h], rsi
0x18000ed07  mov     ecx, 18h; Size
0x18000ed0c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ed11  mov     rsi, rax
0x18000ed14  test    rax, rax
0x18000ed17  jz      short loc_18000ED54
0x18000ed19  lea     rax, ?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z; ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)
0x18000ed20  mov     [rsi], rax
0x18000ed23  mov     [rsi+8], rbx
0x18000ed27  lea     rcx, Buf1; lpCriticalSection
0x18000ed2e  call    cs:__imp_EnterCriticalSection
0x18000ed34  mov     rcx, cs:Block
0x18000ed3b  mov     [rsi+10h], rcx
0x18000ed3f  mov     cs:Block, rsi
0x18000ed46  lea     rcx, Buf1; lpCriticalSection
0x18000ed4d  call    cs:__imp_LeaveCriticalSection
0x18000ed53  nop
0x18000ed54  lea     rcx, [rbp+arg_18]
0x18000ed58  call    ??1?$R@UIADs@@@@QEAA@XZ; R<IADs>::~R<IADs>(void)
0x18000ed5d  nop
0x18000ed5e  lea     rcx, [rbp+arg_0]
0x18000ed62  call    ??1?$R@UIADs@@@@QEAA@XZ; R<IADs>::~R<IADs>(void)
0x18000ed67  mov     rcx, [rbp+var_10]
0x18000ed6b  mov     rax, [rcx]
0x18000ed6e  mov     rax, [rax+10h]
0x18000ed72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed77  nop
0x18000ed78  lea     rcx, [rbp+arg_10]
0x18000ed7c  call    ??1?$R@UIADs@@@@QEAA@XZ; R<IADs>::~R<IADs>(void)
0x18000ed81  mov     rdx, [rbx+18h]; struct ITypeInfo *
0x18000ed85  test    rdx, rdx
0x18000ed88  jz      short loc_18000ED9B
0x18000ed8a  cmp     qword ptr [rbx+28h], 0
0x18000ed8f  jnz     short loc_18000ED9B
0x18000ed91  mov     rcx, rbx; this
0x18000ed94  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x18000ed99  mov     edi, eax
0x18000ed9b  lea     rcx, Buf1; lpCriticalSection
0x18000eda2  call    cs:__imp_LeaveCriticalSection
0x18000eda8  mov     eax, edi
0x18000edaa  mov     rbx, [rsp+40h+arg_8]
0x18000edaf  add     rsp, 40h
0x18000edb3  pop     rdi
0x18000edb4  pop     rsi
0x18000edb5  pop     rbp
0x18000edb6  retn
```
