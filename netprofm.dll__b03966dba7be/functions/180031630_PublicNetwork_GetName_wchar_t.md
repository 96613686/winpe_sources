# PublicNetwork::GetName(wchar_t * *)

- ea: `0x180031630`
- end: `0x18003178b`
- name: `?GetName@PublicNetwork@@UEAAJPEAPEA_W@Z`
- size: `347`
- prototype: `__int64 __fastcall(PublicNetwork *__hidden this, wchar_t **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800064a0`
- `0x180006770`
- `0x180006810`
- `0x1800086b0`
- `0x1800120d0`
- `0x180031630`
- `0x180031a18`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031728`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031728`
- `OLEAUT32!__imp_SysAllocString` at `0x18003170f`
- `OLEAUT32!__imp_SysAllocString` at `0x18003170f`

## pseudocode

```c
__int64 __fastcall PublicNetwork::GetName(PublicNetwork *this, const wchar_t **a2)
{
  PVOID *v4; // rcx
  int PrivateNetwork; // ebx
  int v6; // r8d
  wchar_t *v7; // rax
  const wchar_t *v8; // r9
  OLECHAR *psz; // [rsp+30h] [rbp-28h] BYREF
  struct INetworkPrivate *v11; // [rsp+38h] [rbp-20h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_165b7460307b3cab5819d4ce2d5dc00e_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    *a2 = 0;
    v11 = 0;
    PrivateNetwork = PublicNetwork::GetPrivateNetwork(this, &v11);
    if ( PrivateNetwork >= 0 )
    {
      psz = 0;
      PrivateNetwork = (*(__int64 (__fastcall **)(struct INetworkPrivate *, OLECHAR **))(*(_QWORD *)v11 + 24LL))(
                         v11,
                         &psz);
      if ( PrivateNetwork >= 0 )
      {
        v7 = SysAllocString(psz);
        *a2 = v7;
        if ( !v7 )
          PrivateNetwork = -2147024882;
        CoTaskMemFree(psz);
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v8 = L"nullptr";
      if ( *a2 )
        v8 = *a2;
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v6, (_DWORD)v8, PrivateNetwork);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v11);
  }
  else
  {
    PrivateNetwork = -2147467261;
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
      WPP_SF_d(v4[2], 16, &WPP_165b7460307b3cab5819d4ce2d5dc00e_Traceguids, 2147500035LL);
  }
  return (unsigned int)PrivateNetwork;
}

```

## disassembly

```asm
0x180031630  mov     [rsp+arg_10], rbx
0x180031635  mov     [rsp+arg_18], rdi
0x18003163a  push    r14
0x18003163c  sub     rsp, 50h
0x180031640  mov     rax, cs:__security_cookie
0x180031647  xor     rax, rsp
0x18003164a  mov     [rsp+58h+var_18], rax
0x18003164f  mov     rdi, rdx
0x180031652  mov     rbx, rcx
0x180031655  lea     r14, WPP_GLOBAL_Control
0x18003165c  mov     rcx, cs:WPP_GLOBAL_Control
0x180031663  cmp     rcx, r14
0x180031666  jz      short loc_18003168A
0x180031668  test    byte ptr [rcx+1Ch], 8
0x18003166c  jz      short loc_18003168A
0x18003166e  mov     edx, 0Fh
0x180031673  lea     r8, WPP_165b7460307b3cab5819d4ce2d5dc00e_Traceguids
0x18003167a  mov     rcx, [rcx+10h]
0x18003167e  call    WPP_SF_
0x180031683  mov     rcx, cs:WPP_GLOBAL_Control
0x18003168a  test    rdi, rdi
0x18003168d  jnz     short loc_1800316C2
0x18003168f  mov     ebx, 80004003h
0x180031694  cmp     rcx, r14
0x180031697  jz      loc_18003176B
0x18003169d  test    byte ptr [rcx+1Ch], 8
0x1800316a1  jz      loc_18003176B
0x1800316a7  lea     edx, [rdi+10h]
0x1800316aa  mov     r9d, ebx
0x1800316ad  lea     r8, WPP_165b7460307b3cab5819d4ce2d5dc00e_Traceguids
0x1800316b4  mov     rcx, [rcx+10h]
0x1800316b8  call    WPP_SF_d
0x1800316bd  jmp     loc_18003176B
0x1800316c2  mov     qword ptr [rdi], 0
0x1800316c9  mov     [rsp+58h+var_20], 0
0x1800316d2  lea     rdx, [rsp+58h+var_20]; struct INetworkPrivate **
0x1800316d7  mov     rcx, rbx; this
0x1800316da  call    ?GetPrivateNetwork@PublicNetwork@@AEBAJPEAPEAUINetworkPrivate@@@Z; PublicNetwork::GetPrivateNetwork(INetworkPrivate * *)
0x1800316df  mov     ebx, eax
0x1800316e1  test    eax, eax
0x1800316e3  js      short loc_18003172E
0x1800316e5  mov     [rsp+58h+psz], 0
0x1800316ee  mov     rcx, [rsp+58h+var_20]
0x1800316f3  mov     rax, [rcx]
0x1800316f6  lea     rdx, [rsp+58h+psz]
0x1800316fb  mov     rax, [rax+18h]
0x1800316ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031704  mov     ebx, eax
0x180031706  test    eax, eax
0x180031708  js      short loc_18003172E
0x18003170a  mov     rcx, [rsp+58h+psz]; psz
0x18003170f  call    cs:__imp_SysAllocString
0x180031715  mov     [rdi], rax
0x180031718  mov     ecx, 8007000Eh
0x18003171d  test    rax, rax
0x180031720  cmovz   ebx, ecx
0x180031723  mov     rcx, [rsp+58h+psz]; pv
0x180031728  call    cs:__imp_CoTaskMemFree
0x18003172e  mov     rcx, cs:WPP_GLOBAL_Control
0x180031735  cmp     rcx, r14
0x180031738  jz      short loc_180031761
0x18003173a  test    byte ptr [rcx+1Ch], 8
0x18003173e  jz      short loc_180031761
0x180031740  lea     r9, aNullptr; "nullptr"
0x180031747  cmp     qword ptr [rdi], 0
0x18003174b  cmovnz  r9, [rdi]
0x18003174f  mov     edx, 11h
0x180031754  mov     [rsp+58h+var_38], ebx
0x180031758  mov     rcx, [rcx+10h]
0x18003175c  call    WPP_SF_Sd
0x180031761  lea     rcx, [rsp+58h+var_20]
0x180031766  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003176b  mov     eax, ebx
0x18003176d  mov     rcx, [rsp+58h+var_18]
0x180031772  xor     rcx, rsp; StackCookie
0x180031775  call    __security_check_cookie
0x18003177a  mov     rbx, [rsp+58h+arg_10]
0x18003177f  mov     rdi, [rsp+58h+arg_18]
0x180031784  add     rsp, 50h
0x180031788  pop     r14
0x18003178a  retn
```
