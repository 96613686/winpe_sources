# CAccServerDocMgr::NewDocument(_GUID const &,IUnknown *)

- ea: `0x18000cca0`
- end: `0x18000cfe7`
- name: `?NewDocument@CAccServerDocMgr@@UEAAJAEBU_GUID@@PEAUIUnknown@@@Z`
- size: `839`
- prototype: `__int64 __fastcall(CAccServerDocMgr *this, const struct _GUID *, struct ITextStoreAnchor *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001370`
- `0x1800026d0`
- `0x18000cb30`
- `0x18000cca0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000cd73`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000cd73`

## string_xrefs

- `0x18000cd83`: `CoCreate(AccStore)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAccServerDocMgr::NewDocument(
        CAccServerDocMgr *this,
        const struct _GUID *a2,
        struct ITextStoreAnchor *a3)
{
  __int64 *v6; // rbx
  __int64 v7; // rcx
  unsigned int Instance; // ebp
  struct ITextStoreAnchor *v9; // rbx
  unsigned int v10; // edi
  _QWORD *v11; // rax
  _QWORD *v12; // rdi
  _QWORD *v13; // rax
  int ppv; // [rsp+20h] [rbp-48h]
  _QWORD v15[5]; // [rsp+40h] [rbp-28h] BYREF
  struct ITextStoreAnchor *v16; // [rsp+88h] [rbp+20h] BYREF

  v16 = 0;
  if ( *(_OWORD *)a2 == *(_OWORD *)&IID_ITextStoreAnchor
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ITfTextStoreAnchor.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ITfTextStoreAnchor.Data4 )
  {
    if ( a3 )
      ((void (__fastcall *)(struct ITextStoreAnchor *))a3->lpVtbl->AddRef)(a3);
    v16 = a3;
    if ( !(unsigned int)CheckForWrapper(&v16) )
    {
      if ( v16 )
        ((void (__fastcall *)(struct ITextStoreAnchor *))v16->lpVtbl->Release)(v16);
      return 2147500037LL;
    }
    v6 = (__int64 *)((char *)this + 32);
    v7 = *((_QWORD *)this + 4);
    if ( !v7 )
    {
      *v6 = 0;
      Instance = CoCreateInstance(&CLSID_AccStore, 0, 4u, &IID_IAccStore, (LPVOID *)this + 4);
      v7 = *v6;
      if ( !*v6 )
      {
        InternalTrace(
          L"windows\\oleacc\\msaatext\\msaaadapter.cpp",
          0x8Bu,
          ppv,
          Instance,
          (__int64)L"CoCreate(AccStore)");
        if ( v16 )
          ((void (__fastcall *)(struct ITextStoreAnchor *))v16->lpVtbl->Release)(v16);
        return Instance;
      }
    }
    v9 = v16;
    Instance = (*(__int64 (__fastcall **)(__int64, GUID *, struct ITextStoreAnchor *))(*(_QWORD *)v7 + 24LL))(
                 v7,
                 &IID_ITextStoreAnchor,
                 v16);
    if ( Instance )
    {
      InternalTrace(
        L"windows\\oleacc\\msaatext\\msaaadapter.cpp",
        0x95u,
        ppv,
        Instance,
        (__int64)L"m_pAccStore->Register()");
      if ( v9 )
        ((void (__fastcall *)(struct ITextStoreAnchor *))v9->lpVtbl->Release)(v9);
      return Instance;
    }
    v15[0] = 0;
    v10 = ((__int64 (__fastcall *)(struct ITextStoreAnchor *, GUID *, _QWORD *))a3->lpVtbl->QueryInterface)(
            a3,
            &IID_IUnknown,
            v15);
    if ( v10 || !v15[0] )
    {
      InternalTrace(L"windows\\oleacc\\msaatext\\msaaadapter.cpp", 0xAAu, ppv, 0, (__int64)L"QI(IUnknown) failed");
      if ( v9 )
        ((void (__fastcall *)(struct ITextStoreAnchor *))v9->lpVtbl->Release)(v9);
      return v10;
    }
    else
    {
      v11 = operator new(0x20u);
      v12 = v11;
      v15[1] = v11;
      if ( v11 )
      {
        *v11 = 0;
        v11[1] = 0;
        v11[3] = v9;
        v11[2] = v15[0];
        *v11 = 0;
        v11[1] = *((_QWORD *)this + 2);
        v13 = (_QWORD *)*((_QWORD *)this + 2);
        if ( v13 )
          *v13 = v12;
        else
          *((_QWORD *)this + 3) = v12;
        *((_QWORD *)this + 2) = v12;
        ((void (__fastcall *)(struct ITextStoreAnchor *))v9->lpVtbl->AddRef)(v9);
        ((void (__fastcall *)(struct ITextStoreAnchor *))v9->lpVtbl->Release)(v9);
        return 0;
      }
      else
      {
        if ( v9 )
          ((void (__fastcall *)(struct ITextStoreAnchor *))v9->lpVtbl->Release)(v9);
        return 2147942414LL;
      }
    }
  }
  else if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ITextStoreACP.Data1
         && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ITextStoreACP.Data4
         || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ITfTextStoreACP.Data1
         && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ITfTextStoreACP.Data4 )
  {
    InternalTrace(
      L"windows\\oleacc\\msaatext\\msaaadapter.cpp",
      0x6Du,
      ppv,
      0,
      (__int64)L"Got ACP doc, but ACP->Anchor wrapping not currently supported");
    return 2147500033LL;
  }
  else
  {
    InternalTrace(
      L"windows\\oleacc\\msaatext\\msaaadapter.cpp",
      0x79u,
      ppv,
      0,
      (__int64)L"Got unknown interface - wasn't ITextStoreAnchor/ITfTextStoreAnchor");
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x18000cca0  mov     rax, rsp
0x18000cca3  mov     [rax+8], rbx
0x18000cca7  mov     [rax+10h], rbp
0x18000ccab  push    rsi
0x18000ccac  push    rdi
0x18000ccad  push    r14
0x18000ccaf  sub     rsp, 50h
0x18000ccb3  mov     rdi, r8
0x18000ccb6  mov     rsi, rcx
0x18000ccb9  xor     r14d, r14d
0x18000ccbc  mov     [rax+20h], r14
0x18000ccc0  mov     rax, [rdx]
0x18000ccc3  cmp     rax, qword ptr cs:IID_ITextStoreAnchor.Data1
0x18000ccca  jnz     short loc_18000CCD9
0x18000cccc  mov     rax, [rdx+8]
0x18000ccd0  cmp     rax, qword ptr cs:IID_ITextStoreAnchor.Data4
0x18000ccd7  jz      short loc_18000CCFA
0x18000ccd9  mov     rax, [rdx]
0x18000ccdc  cmp     rax, qword ptr cs:IID_ITfTextStoreAnchor.Data1
0x18000cce3  jnz     loc_18000CF44
0x18000cce9  mov     rax, [rdx+8]
0x18000cced  cmp     rax, qword ptr cs:IID_ITfTextStoreAnchor.Data4
0x18000ccf4  jnz     loc_18000CF44
0x18000ccfa  test    rdi, rdi
0x18000ccfd  jz      short loc_18000CD0E
0x18000ccff  mov     rax, [r8]
0x18000cd02  mov     rcx, rdi
0x18000cd05  mov     rax, [rax+8]
0x18000cd09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd0e  mov     [rsp+68h+arg_18], rdi
0x18000cd16  lea     rcx, [rsp+68h+arg_18]; struct ITextStoreAnchor **
0x18000cd1e  call    ?CheckForWrapper@@YAHPEAPEAUITextStoreAnchor@@@Z; CheckForWrapper(ITextStoreAnchor * *)
0x18000cd23  test    eax, eax
0x18000cd25  jnz     short loc_18000CD4B
0x18000cd27  mov     rcx, [rsp+68h+arg_18]
0x18000cd2f  test    rcx, rcx
0x18000cd32  jz      short loc_18000CD41
0x18000cd34  mov     rax, [rcx]
0x18000cd37  mov     rax, [rax+10h]
0x18000cd3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd40  nop
0x18000cd41  mov     eax, 80004005h
0x18000cd46  jmp     loc_18000CFD4
0x18000cd4b  lea     rbx, [rsi+20h]
0x18000cd4f  mov     rcx, [rbx]
0x18000cd52  test    rcx, rcx
0x18000cd55  jnz     short loc_18000CDCE
0x18000cd57  mov     [rbx], r14
0x18000cd5a  mov     [rsp+68h+ppv], rbx; int
0x18000cd5f  lea     r9, IID_IAccStore; riid
0x18000cd66  xor     edx, edx; pUnkOuter
0x18000cd68  lea     r8d, [rcx+4]; dwClsContext
0x18000cd6c  lea     rcx, CLSID_AccStore; rclsid
0x18000cd73  call    cs:__imp_CoCreateInstance
0x18000cd79  mov     ebp, eax
0x18000cd7b  mov     rcx, [rbx]
0x18000cd7e  test    rcx, rcx
0x18000cd81  jnz     short loc_18000CDCE
0x18000cd83  lea     rax, aCocreateAccsto; "CoCreate(AccStore)"
0x18000cd8a  mov     [rsp+68h+var_38], rax; __int64
0x18000cd8f  mov     [rsp+68h+var_40], ebp; int
0x18000cd93  mov     edx, 8Bh; Value
0x18000cd98  lea     r9d, [rcx+1]
0x18000cd9c  lea     r8d, [rcx+3]
0x18000cda0  lea     rcx, aWindowsOleaccM_2; "windows\\oleacc\\msaatext\\msaaadapter."...
0x18000cda7  call    InternalTrace
0x18000cdac  nop
0x18000cdad  mov     rcx, [rsp+68h+arg_18]
0x18000cdb5  test    rcx, rcx
0x18000cdb8  jz      short loc_18000CDC7
0x18000cdba  mov     rax, [rcx]
0x18000cdbd  mov     rax, [rax+10h]
0x18000cdc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdc6  nop
0x18000cdc7  mov     eax, ebp
0x18000cdc9  jmp     loc_18000CFD4
0x18000cdce  mov     rax, [rcx]
0x18000cdd1  mov     rbx, [rsp+68h+arg_18]
0x18000cdd9  mov     r8, rbx
0x18000cddc  lea     rdx, IID_ITextStoreAnchor
0x18000cde3  mov     rax, [rax+18h]
0x18000cde7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdec  mov     ebp, eax
0x18000cdee  test    eax, eax
0x18000cdf0  jz      short loc_18000CE35
0x18000cdf2  lea     rax, aMPaccstoreRegi; "m_pAccStore->Register()"
0x18000cdf9  mov     [rsp+68h+var_38], rax; __int64
0x18000cdfe  mov     [rsp+68h+var_40], ebp; int
0x18000ce02  mov     edx, 95h; Value
0x18000ce07  mov     r9d, 1
0x18000ce0d  lea     r8d, [r9+2]
0x18000ce11  lea     rcx, aWindowsOleaccM_2; "windows\\oleacc\\msaatext\\msaaadapter."...
0x18000ce18  call    InternalTrace
0x18000ce1d  nop
0x18000ce1e  test    rbx, rbx
0x18000ce21  jz      short loc_18000CE33
0x18000ce23  mov     rax, [rbx]
0x18000ce26  mov     rcx, rbx
0x18000ce29  mov     rax, [rax+10h]
0x18000ce2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce32  nop
0x18000ce33  jmp     short loc_18000CDC7
0x18000ce35  mov     [rsp+68h+var_28], r14
0x18000ce3a  mov     rax, [rdi]
0x18000ce3d  lea     r8, [rsp+68h+var_28]
0x18000ce42  lea     rdx, IID_IUnknown
0x18000ce49  mov     rcx, rdi
0x18000ce4c  mov     rax, [rax]
0x18000ce4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce54  mov     edi, eax
0x18000ce56  test    eax, eax
0x18000ce58  jnz     loc_18000CEFE
0x18000ce5e  cmp     [rsp+68h+var_28], r14
0x18000ce63  jz      loc_18000CEFE
0x18000ce69  lea     ecx, [rax+20h]; Size
0x18000ce6c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ce71  mov     rdi, rax
0x18000ce74  mov     [rsp+68h+var_20], rax
0x18000ce79  test    rax, rax
0x18000ce7c  jz      short loc_18000CEDF
0x18000ce7e  mov     [rax], r14
0x18000ce81  mov     [rax+8], r14
0x18000ce85  test    rax, rax
0x18000ce88  jz      short loc_18000CEDF
0x18000ce8a  mov     [rax+18h], rbx
0x18000ce8e  mov     rcx, [rsp+68h+var_28]
0x18000ce93  mov     [rax+10h], rcx
0x18000ce97  mov     [rax], r14
0x18000ce9a  mov     rax, [rsi+10h]
0x18000ce9e  mov     [rdi+8], rax
0x18000cea2  mov     rax, [rsi+10h]
0x18000cea6  test    rax, rax
0x18000cea9  jz      short loc_18000CEB0
0x18000ceab  mov     [rax], rdi
0x18000ceae  jmp     short loc_18000CEB4
0x18000ceb0  mov     [rsi+18h], rdi
0x18000ceb4  mov     [rsi+10h], rdi
0x18000ceb8  mov     rax, [rbx]
0x18000cebb  mov     rcx, rbx
0x18000cebe  mov     rax, [rax+8]
0x18000cec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cec7  nop
0x18000cec8  mov     rax, [rbx]
0x18000cecb  mov     rcx, rbx
0x18000cece  mov     rax, [rax+10h]
0x18000ced2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ced7  nop
0x18000ced8  xor     eax, eax
0x18000ceda  jmp     loc_18000CFD4
0x18000cedf  test    rbx, rbx
0x18000cee2  jz      short loc_18000CEF4
0x18000cee4  mov     rax, [rbx]
0x18000cee7  mov     rcx, rbx
0x18000ceea  mov     rax, [rax+10h]
0x18000ceee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cef3  nop
0x18000cef4  mov     eax, 8007000Eh
0x18000cef9  jmp     loc_18000CFD4
0x18000cefe  lea     rax, aQiIunknownFail; "QI(IUnknown) failed"
0x18000cf05  mov     [rsp+68h+var_38], rax; __int64
0x18000cf0a  mov     [rsp+68h+var_40], r14d; int
0x18000cf0f  xor     r9d, r9d
0x18000cf12  mov     edx, 0AAh; Value
0x18000cf17  lea     r8d, [r9+8]
0x18000cf1b  lea     rcx, aWindowsOleaccM_2; "windows\\oleacc\\msaatext\\msaaadapter."...
0x18000cf22  call    InternalTrace
0x18000cf27  nop
0x18000cf28  test    rbx, rbx
0x18000cf2b  jz      short loc_18000CF3D
0x18000cf2d  mov     rax, [rbx]
0x18000cf30  mov     rcx, rbx
0x18000cf33  mov     rax, [rax+10h]
0x18000cf37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf3c  nop
0x18000cf3d  mov     eax, edi
0x18000cf3f  jmp     loc_18000CFD4
0x18000cf44  mov     rax, [rdx]
0x18000cf47  cmp     rax, qword ptr cs:IID_ITextStoreACP.Data1
0x18000cf4e  jnz     short loc_18000CF5D
0x18000cf50  mov     rax, [rdx+8]
0x18000cf54  cmp     rax, qword ptr cs:IID_ITextStoreACP.Data4
0x18000cf5b  jz      short loc_18000CF76
0x18000cf5d  mov     rax, [rdx]
0x18000cf60  cmp     rax, qword ptr cs:IID_ITfTextStoreACP.Data1
0x18000cf67  jnz     short loc_18000CFA6
0x18000cf69  mov     rax, [rdx+8]
0x18000cf6d  cmp     rax, qword ptr cs:IID_ITfTextStoreACP.Data4
0x18000cf74  jnz     short loc_18000CFA6
0x18000cf76  lea     rax, aGotAcpDocButAc; "Got ACP doc, but ACP->Anchor wrapping n"...
0x18000cf7d  mov     [rsp+68h+var_38], rax; __int64
0x18000cf82  mov     [rsp+68h+var_40], r14d; int
0x18000cf87  xor     r9d, r9d
0x18000cf8a  lea     edx, [r9+6Dh]; Value
0x18000cf8e  lea     r8d, [r9+4]
0x18000cf92  lea     rcx, aWindowsOleaccM_2; "windows\\oleacc\\msaatext\\msaaadapter."...
0x18000cf99  call    InternalTrace
0x18000cf9e  nop
0x18000cf9f  mov     eax, 80004001h
0x18000cfa4  jmp     short loc_18000CFD4
0x18000cfa6  lea     rax, aGotUnknownInte; "Got unknown interface - wasn't ITextSto"...
0x18000cfad  mov     [rsp+68h+var_38], rax; __int64
0x18000cfb2  mov     [rsp+68h+var_40], r14d; int
0x18000cfb7  xor     r9d, r9d
0x18000cfba  lea     edx, [r9+79h]; Value
0x18000cfbe  lea     r8d, [r9+4]
0x18000cfc2  lea     rcx, aWindowsOleaccM_2; "windows\\oleacc\\msaatext\\msaaadapter."...
0x18000cfc9  call    InternalTrace
0x18000cfce  nop
0x18000cfcf  mov     eax, 80004002h
0x18000cfd4  mov     rbx, [rsp+68h+arg_0]
0x18000cfd9  mov     rbp, [rsp+68h+arg_8]
0x18000cfde  add     rsp, 50h
0x18000cfe2  pop     r14
0x18000cfe4  pop     rdi
0x18000cfe5  pop     rsi
0x18000cfe6  retn
```
