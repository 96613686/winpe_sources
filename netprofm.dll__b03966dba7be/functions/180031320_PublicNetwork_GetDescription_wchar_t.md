# PublicNetwork::GetDescription(wchar_t * *)

- ea: `0x180031320`
- end: `0x18003147b`
- name: `?GetDescription@PublicNetwork@@UEAAJPEAPEA_W@Z`
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
- `0x180031320`
- `0x180031a18`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031418`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031418`
- `OLEAUT32!__imp_SysAllocString` at `0x1800313ff`
- `OLEAUT32!__imp_SysAllocString` at `0x1800313ff`

## pseudocode

```c
__int64 __fastcall PublicNetwork::GetDescription(PublicNetwork *this, const wchar_t **a2)
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_165b7460307b3cab5819d4ce2d5dc00e_Traceguids);
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
      PrivateNetwork = (*(__int64 (__fastcall **)(struct INetworkPrivate *, OLECHAR **))(*(_QWORD *)v11 + 32LL))(
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
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, v6, (_DWORD)v8, PrivateNetwork);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v11);
  }
  else
  {
    PrivateNetwork = -2147467261;
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
      WPP_SF_d(v4[2], 21, &WPP_165b7460307b3cab5819d4ce2d5dc00e_Traceguids, 2147500035LL);
  }
  return (unsigned int)PrivateNetwork;
}

```

## disassembly

```asm
0x180031320  mov     [rsp+arg_10], rbx
0x180031325  mov     [rsp+arg_18], rdi
0x18003132a  push    r14
0x18003132c  sub     rsp, 50h
0x180031330  mov     rax, cs:__security_cookie
0x180031337  xor     rax, rsp
0x18003133a  mov     [rsp+58h+var_18], rax
0x18003133f  mov     rdi, rdx
0x180031342  mov     rbx, rcx
0x180031345  lea     r14, WPP_GLOBAL_Control
0x18003134c  mov     rcx, cs:WPP_GLOBAL_Control
0x180031353  cmp     rcx, r14
0x180031356  jz      short loc_18003137A
0x180031358  test    byte ptr [rcx+1Ch], 8
0x18003135c  jz      short loc_18003137A
0x18003135e  mov     edx, 14h
0x180031363  lea     r8, WPP_165b7460307b3cab5819d4ce2d5dc00e_Traceguids
0x18003136a  mov     rcx, [rcx+10h]
0x18003136e  call    WPP_SF_
0x180031373  mov     rcx, cs:WPP_GLOBAL_Control
0x18003137a  test    rdi, rdi
0x18003137d  jnz     short loc_1800313B2
0x18003137f  mov     ebx, 80004003h
0x180031384  cmp     rcx, r14
0x180031387  jz      loc_18003145B
0x18003138d  test    byte ptr [rcx+1Ch], 8
0x180031391  jz      loc_18003145B
0x180031397  lea     edx, [rdi+15h]
0x18003139a  mov     r9d, ebx
0x18003139d  lea     r8, WPP_165b7460307b3cab5819d4ce2d5dc00e_Traceguids
0x1800313a4  mov     rcx, [rcx+10h]
0x1800313a8  call    WPP_SF_d
0x1800313ad  jmp     loc_18003145B
0x1800313b2  mov     qword ptr [rdi], 0
0x1800313b9  mov     [rsp+58h+var_20], 0
0x1800313c2  lea     rdx, [rsp+58h+var_20]; struct INetworkPrivate **
0x1800313c7  mov     rcx, rbx; this
0x1800313ca  call    ?GetPrivateNetwork@PublicNetwork@@AEBAJPEAPEAUINetworkPrivate@@@Z; PublicNetwork::GetPrivateNetwork(INetworkPrivate * *)
0x1800313cf  mov     ebx, eax
0x1800313d1  test    eax, eax
0x1800313d3  js      short loc_18003141E
0x1800313d5  mov     [rsp+58h+psz], 0
0x1800313de  mov     rcx, [rsp+58h+var_20]
0x1800313e3  mov     rax, [rcx]
0x1800313e6  lea     rdx, [rsp+58h+psz]
0x1800313eb  mov     rax, [rax+20h]
0x1800313ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800313f4  mov     ebx, eax
0x1800313f6  test    eax, eax
0x1800313f8  js      short loc_18003141E
0x1800313fa  mov     rcx, [rsp+58h+psz]; psz
0x1800313ff  call    cs:__imp_SysAllocString
0x180031405  mov     [rdi], rax
0x180031408  mov     ecx, 8007000Eh
0x18003140d  test    rax, rax
0x180031410  cmovz   ebx, ecx
0x180031413  mov     rcx, [rsp+58h+psz]; pv
0x180031418  call    cs:__imp_CoTaskMemFree
0x18003141e  mov     rcx, cs:WPP_GLOBAL_Control
0x180031425  cmp     rcx, r14
0x180031428  jz      short loc_180031451
0x18003142a  test    byte ptr [rcx+1Ch], 8
0x18003142e  jz      short loc_180031451
0x180031430  lea     r9, aNullptr; "nullptr"
0x180031437  cmp     qword ptr [rdi], 0
0x18003143b  cmovnz  r9, [rdi]
0x18003143f  mov     edx, 16h
0x180031444  mov     [rsp+58h+var_38], ebx
0x180031448  mov     rcx, [rcx+10h]
0x18003144c  call    WPP_SF_Sd
0x180031451  lea     rcx, [rsp+58h+var_20]
0x180031456  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003145b  mov     eax, ebx
0x18003145d  mov     rcx, [rsp+58h+var_18]
0x180031462  xor     rcx, rsp; StackCookie
0x180031465  call    __security_check_cookie
0x18003146a  mov     rbx, [rsp+58h+arg_10]
0x18003146f  mov     rdi, [rsp+58h+arg_18]
0x180031474  add     rsp, 50h
0x180031478  pop     r14
0x18003147a  retn
```
