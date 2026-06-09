# CWapDPUHelper::DeleteV2Node(IConfigManager2 *,ushort const *,IResultTracker *)

- ea: `0x180026a20`
- end: `0x180026c71`
- name: `?DeleteV2Node@CWapDPUHelper@@UEAAJPEAUIConfigManager2@@PEBGPEAUIResultTracker@@@Z`
- size: `593`
- prototype: `__int64 __fastcall(CWapDPUHelper *__hidden this, struct IConfigManager2 *, wchar_t *Str, struct IResultTracker *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001488`
- `0x1800110bc`
- `0x180026854`
- `0x180026a20`
- `0x1800271a8`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180026bc3`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180026bc3`
- `OLEAUT32!__imp_VariantInit` at `0x180026a82`
- `OLEAUT32!__imp_VariantInit` at `0x180026a82`
- `OLEAUT32!__imp_VariantClear` at `0x180026c34`
- `OLEAUT32!__imp_VariantClear` at `0x180026c34`

## string_xrefs

- `0x180026b04`: `DeleteV2Node`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWapDPUHelper::DeleteV2Node(
        CWapDPUHelper *this,
        struct IConfigManager2 *a2,
        wchar_t *Str,
        struct IResultTracker *a4)
{
  int IsCSPRootNode; // ebx
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // rcx
  int v12; // eax
  wchar_t *v13; // rax
  wchar_t *v14; // rdx
  __int64 v16; // [rsp+40h] [rbp-29h] BYREF
  struct IConfigNode *v17; // [rsp+48h] [rbp-21h] BYREF
  int v18; // [rsp+50h] [rbp-19h] BYREF
  unsigned int v19; // [rsp+54h] [rbp-15h] BYREF
  unsigned int v20; // [rsp+58h] [rbp-11h] BYREF
  int v21; // [rsp+5Ch] [rbp-Dh] BYREF
  const wchar_t *v22; // [rsp+60h] [rbp-9h] BYREF
  wchar_t *v23; // [rsp+68h] [rbp-1h] BYREF
  __int64 v24; // [rsp+70h] [rbp+7h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp+Fh] BYREF
  int v26; // [rsp+D8h] [rbp+6Fh] BYREF

  v17 = 0;
  v16 = 0;
  v24 = 0;
  v20 = 0;
  v19 = 0;
  v26 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v18 = 0;
  VariantInit(&pvarg);
  if ( a2 && Str && a4 )
  {
    IsCSPRootNode = (*(__int64 (__fastcall **)(struct IConfigManager2 *, wchar_t *, struct IConfigNode **))(*(_QWORD *)a2 + 80LL))(
                      a2,
                      Str,
                      &v17);
    if ( IsCSPRootNode >= 0 )
    {
      IsCSPRootNode = (*(__int64 (__fastcall **)(struct IConfigNode *, int *))(*(_QWORD *)v17 + 224LL))(v17, &v26);
      v11 = 0x80000000LL;
      if ( (int)(IsCSPRootNode + 0x80000000) < 0 || IsCSPRootNode == -2147023728 )
      {
        IsCSPRootNode = 0;
        if ( (unsigned int)dword_18003E080 > 5 )
        {
          v22 = L"DeleteV2Node";
          v23 = Str;
          v21 = v26;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            0x80000000,
            (unsigned int)byte_18003783B,
            v9,
            v10,
            (__int64)&v21,
            (__int64)&v23,
            (__int64)&v22);
        }
        if ( v26 )
        {
          IsCSPRootNode = CWapDPUHelper::IsCSPRootNode((CWapDPUHelper *)v11, v17, &v18);
          if ( IsCSPRootNode >= 0 )
          {
            if ( v18 )
            {
              v12 = CWapDPUHelper::DeleteChildNodes(this, a2, v17, a4);
LABEL_22:
              IsCSPRootNode = v12;
              goto LABEL_23;
            }
            IsCSPRootNode = (*(__int64 (__fastcall **)(struct IConfigNode *, __int64 *))(*(_QWORD *)v17 + 200LL))(
                              v17,
                              &v16);
            if ( IsCSPRootNode >= 0 )
            {
              IsCSPRootNode = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v16 + 144LL))(v16, &v20);
              if ( IsCSPRootNode >= 0 )
              {
                v13 = wcsrchr(Str, 0x2Fu);
                v14 = v13 ? v13 + 1 : Str;
                IsCSPRootNode = (*(__int64 (__fastcall **)(__int64, wchar_t *))(*(_QWORD *)v16 + 72LL))(v16, v14);
                if ( IsCSPRootNode >= 0 )
                {
                  IsCSPRootNode = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v16 + 144LL))(
                                    v16,
                                    &v19);
                  if ( IsCSPRootNode >= 0 )
                  {
                    v12 = (*(__int64 (__fastcall **)(struct IResultTracker *, __int64, _QWORD, _QWORD))(*(_QWORD *)a4 + 48LL))(
                            a4,
                            v16,
                            v20,
                            v19);
                    goto LABEL_22;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    IsCSPRootNode = -2147024809;
  }
LABEL_23:
  VariantClear(&pvarg);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v24);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v16);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v17);
  return (unsigned int)IsCSPRootNode;
}

```

## disassembly

```asm
0x180026a20  push    rbp
0x180026a22  push    rbx
0x180026a23  push    rsi
0x180026a24  push    rdi
0x180026a25  push    r14
0x180026a27  push    r15
0x180026a29  lea     rbp, [rsp-2Fh]
0x180026a2e  sub     rsp, 98h
0x180026a35  mov     r14, r9
0x180026a38  mov     rdi, r8
0x180026a3b  mov     rsi, rdx
0x180026a3e  mov     r15, rcx
0x180026a41  mov     [rbp+57h+var_78], 0
0x180026a49  mov     [rbp+57h+var_80], 0
0x180026a51  mov     [rbp+57h+var_50], 0
0x180026a59  mov     [rbp+57h+var_68], 0
0x180026a60  mov     [rbp+57h+var_6C], 0
0x180026a67  mov     [rbp+57h+arg_8], 0
0x180026a6e  xorps   xmm0, xmm0
0x180026a71  xor     eax, eax
0x180026a73  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180026a77  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180026a7b  mov     [rbp+57h+var_70], eax
0x180026a7e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180026a82  call    cs:__imp_VariantInit
0x180026a89  nop     dword ptr [rax+rax+00h]
0x180026a8e  test    rsi, rsi
0x180026a91  jnz     short loc_180026A9D
0x180026a93  mov     ebx, 80070057h
0x180026a98  jmp     loc_180026C30
0x180026a9d  test    rdi, rdi
0x180026aa0  jz      short loc_180026A93
0x180026aa2  test    r14, r14
0x180026aa5  jz      short loc_180026A93
0x180026aa7  mov     rax, [rsi]
0x180026aaa  lea     r8, [rbp+57h+var_78]
0x180026aae  mov     rdx, rdi
0x180026ab1  mov     rcx, rsi
0x180026ab4  mov     rax, [rax+50h]
0x180026ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026abd  mov     ebx, eax
0x180026abf  test    eax, eax
0x180026ac1  js      loc_180026C30
0x180026ac7  mov     rcx, [rbp+57h+var_78]
0x180026acb  mov     rax, [rcx]
0x180026ace  lea     rdx, [rbp+57h+arg_8]
0x180026ad2  mov     rax, [rax+0E0h]
0x180026ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ade  mov     ebx, eax
0x180026ae0  mov     ecx, 80000000h
0x180026ae5  add     eax, ecx
0x180026ae7  test    ecx, eax
0x180026ae9  jnz     short loc_180026AF7
0x180026aeb  cmp     ebx, 80070490h
0x180026af1  jnz     loc_180026C30
0x180026af7  xor     ebx, ebx
0x180026af9  mov     eax, cs:dword_18003E080
0x180026aff  cmp     eax, 5
0x180026b02  jbe     short loc_180026B40
0x180026b04  lea     rax, aDeletev2node; "DeleteV2Node"
0x180026b0b  mov     [rbp+57h+var_60], rax
0x180026b0f  mov     [rbp+57h+var_58], rdi
0x180026b13  mov     eax, [rbp+57h+arg_8]
0x180026b16  mov     [rbp+57h+var_64], eax
0x180026b19  lea     rax, [rbp+57h+var_60]
0x180026b1d  mov     [rsp+0C0h+var_90], rax
0x180026b22  lea     rax, [rbp+57h+var_58]
0x180026b26  mov     [rsp+0C0h+var_98], rax
0x180026b2b  lea     rax, [rbp+57h+var_64]
0x180026b2f  mov     [rsp+0C0h+var_A0], rax
0x180026b34  lea     rdx, byte_18003783B
0x180026b3b  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180026b40  cmp     [rbp+57h+arg_8], ebx
0x180026b43  jz      loc_180026C30
0x180026b49  lea     r8, [rbp+57h+var_70]; int *
0x180026b4d  mov     rdx, [rbp+57h+var_78]; struct IConfigNode *
0x180026b51  call    ?IsCSPRootNode@CWapDPUHelper@@AEAAJPEAUIConfigNode@@PEAH@Z; CWapDPUHelper::IsCSPRootNode(IConfigNode *,int *)
0x180026b56  mov     ebx, eax
0x180026b58  test    eax, eax
0x180026b5a  js      loc_180026C30
0x180026b60  cmp     [rbp+57h+var_70], 0
0x180026b64  jz      short loc_180026B7D
0x180026b66  mov     r9, r14; struct IResultTracker *
0x180026b69  mov     r8, [rbp+57h+var_78]; struct IConfigNode *
0x180026b6d  mov     rdx, rsi; struct IConfigManager2 *
0x180026b70  mov     rcx, r15; this
0x180026b73  call    ?DeleteChildNodes@CWapDPUHelper@@AEAAJPEAUIConfigManager2@@PEAUIConfigNode@@PEAUIResultTracker@@@Z; CWapDPUHelper::DeleteChildNodes(IConfigManager2 *,IConfigNode *,IResultTracker *)
0x180026b78  jmp     loc_180026C2E
0x180026b7d  mov     rcx, [rbp+57h+var_78]
0x180026b81  mov     rax, [rcx]
0x180026b84  lea     rdx, [rbp+57h+var_80]
0x180026b88  mov     rax, [rax+0C8h]
0x180026b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b94  mov     ebx, eax
0x180026b96  test    eax, eax
0x180026b98  js      loc_180026C30
0x180026b9e  mov     rcx, [rbp+57h+var_80]
0x180026ba2  mov     rax, [rcx]
0x180026ba5  lea     rdx, [rbp+57h+var_68]
0x180026ba9  mov     rax, [rax+90h]
0x180026bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bb5  mov     ebx, eax
0x180026bb7  test    eax, eax
0x180026bb9  js      short loc_180026C30
0x180026bbb  mov     edx, 2Fh ; '/'; Ch
0x180026bc0  mov     rcx, rdi; Str
0x180026bc3  call    cs:__imp_wcsrchr
0x180026bca  nop     dword ptr [rax+rax+00h]
0x180026bcf  mov     rdx, rax
0x180026bd2  test    rax, rax
0x180026bd5  jnz     short loc_180026BDC
0x180026bd7  mov     rdx, rdi
0x180026bda  jmp     short loc_180026BE0
0x180026bdc  add     rdx, 2
0x180026be0  mov     rcx, [rbp+57h+var_80]
0x180026be4  mov     rax, [rcx]
0x180026be7  mov     rax, [rax+48h]
0x180026beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bf0  mov     ebx, eax
0x180026bf2  test    eax, eax
0x180026bf4  js      short loc_180026C30
0x180026bf6  mov     rcx, [rbp+57h+var_80]
0x180026bfa  mov     rax, [rcx]
0x180026bfd  lea     rdx, [rbp+57h+var_6C]
0x180026c01  mov     rax, [rax+90h]
0x180026c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c0d  mov     ebx, eax
0x180026c0f  test    eax, eax
0x180026c11  js      short loc_180026C30
0x180026c13  mov     rax, [r14]
0x180026c16  mov     r9d, [rbp+57h+var_6C]
0x180026c1a  mov     r8d, [rbp+57h+var_68]
0x180026c1e  mov     rdx, [rbp+57h+var_80]
0x180026c22  mov     rcx, r14
0x180026c25  mov     rax, [rax+30h]
0x180026c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c2e  mov     ebx, eax
0x180026c30  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180026c34  call    cs:__imp_VariantClear
0x180026c3b  nop     dword ptr [rax+rax+00h]
0x180026c40  nop
0x180026c41  lea     rcx, [rbp+57h+var_50]
0x180026c45  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180026c4a  nop
0x180026c4b  lea     rcx, [rbp+57h+var_80]
0x180026c4f  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180026c54  nop
0x180026c55  lea     rcx, [rbp+57h+var_78]
0x180026c59  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180026c5e  mov     eax, ebx
0x180026c60  add     rsp, 98h
0x180026c67  pop     r15
0x180026c69  pop     r14
0x180026c6b  pop     rdi
0x180026c6c  pop     rsi
0x180026c6d  pop     rbx
0x180026c6e  pop     rbp
0x180026c6f  retn
```
