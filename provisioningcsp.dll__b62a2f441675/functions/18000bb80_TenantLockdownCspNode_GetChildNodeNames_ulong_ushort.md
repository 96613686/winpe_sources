# TenantLockdownCspNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x18000bb80`
- end: `0x18000bd65`
- name: `?GetChildNodeNames@TenantLockdownCspNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `485`
- prototype: `__int64 __fastcall(TenantLockdownCspNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006974`
- `0x18000b3ac`
- `0x18000b470`
- `0x18000b578`
- `0x18000ba60`
- `0x18000bb80`
- `0x18000c8f4`
- `0x18000cd2c`
- `0x1800358a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bc28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bc28`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bc88`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bc88`

## pseudocode

```c
__int64 __fastcall TenantLockdownCspNode::GetChildNodeNames(
        TenantLockdownCspNode *this,
        unsigned int *a2,
        unsigned __int16 ***a3)
{
  unsigned int v6; // ebx
  unsigned __int16 **v7; // rax
  __int64 v8; // rdi
  BSTR v9; // rax
  unsigned int v10; // eax
  int v12; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 **v13; // [rsp+28h] [rbp-D8h] BYREF
  OLECHAR *psz; // [rsp+30h] [rbp-D0h]
  _QWORD v15[2]; // [rsp+38h] [rbp-C8h] BYREF
  char v16; // [rsp+48h] [rbp-B8h]
  _QWORD v17[42]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  *a2 = 0;
  *a3 = 0;
  wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v17,
    "CspGetChildNodeNames");
  v17[0] = &ForcedEnrollmentTelemetryProvider::CspGetChildNodeNames::`vftable';
  ForcedEnrollmentTelemetryProvider::CspGetChildNodeNames::StartActivity((ForcedEnrollmentTelemetryProvider::CspGetChildNodeNames *)v17);
  if ( *((_DWORD *)this + 11) )
  {
    *a2 = 0;
    *a3 = 0;
    v6 = -2046820335;
  }
  else
  {
    v12 = 0;
    psz = L"RequireNetworkInOOBE";
    v7 = (unsigned __int16 **)CoTaskMemAlloc(8u);
    v13 = v7;
    if ( v7 )
    {
      v16 = 1;
      *v7 = 0;
      v8 = 0;
      v15[0] = &v13;
      v15[1] = &v12;
      while ( 1 )
      {
        v9 = SysAllocString((const OLECHAR *)v15[v8 - 1]);
        v13[v8] = v9;
        if ( !v13[v8] )
          break;
        v8 = (unsigned int)(v8 + 1);
        v10 = ++v12;
        if ( (_DWORD)v8 )
        {
          *a3 = v13;
          v13 = 0;
          *a2 = v10;
          wil::details::ScopeExitFn__lambda_2fc6b439b24d94e47d4f65647024a2b7___::_ScopeExitFn__lambda_2fc6b439b24d94e47d4f65647024a2b7___(v15);
          wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v17);
          v17[0] = &ForcedEnrollmentTelemetryProvider::CspGetChildNodeNames::`vftable';
          wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v17);
          wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(v17);
          return 0;
        }
      }
      v6 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAF,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\tenantlockdowncspnode.cpp",
        (const char *)0x8007000ELL,
        v12);
      wil::details::ScopeExitFn__lambda_2fc6b439b24d94e47d4f65647024a2b7___::_ScopeExitFn__lambda_2fc6b439b24d94e47d4f65647024a2b7___(v15);
    }
    else
    {
      v6 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9D,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\tenantlockdowncspnode.cpp",
        (const char *)0x8007000ELL,
        v12);
    }
  }
  v17[0] = &ForcedEnrollmentTelemetryProvider::CspGetChildNodeNames::`vftable';
  wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v17);
  wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(v17);
  return v6;
}

```

## disassembly

```asm
0x18000bb80  mov     [rsp-8+arg_0], rbx
0x18000bb85  push    rbp
0x18000bb86  push    rsi
0x18000bb87  push    rdi
0x18000bb88  push    r12
0x18000bb8a  push    r14
0x18000bb8c  lea     rbp, [rsp-0B0h]
0x18000bb94  sub     rsp, 1B0h
0x18000bb9b  mov     rax, cs:__security_cookie
0x18000bba2  xor     rax, rsp
0x18000bba5  mov     [rbp+0D0h+var_30], rax
0x18000bbac  mov     dword ptr [rdx], 0
0x18000bbb2  mov     rsi, rdx
0x18000bbb5  mov     rbx, rcx
0x18000bbb8  mov     qword ptr [r8], 0
0x18000bbbf  lea     rdx, aCspgetchildnod; "CspGetChildNodeNames"
0x18000bbc6  mov     r14, r8
0x18000bbc9  lea     rcx, [rsp+1D0h+var_180]
0x18000bbce  call    ??0?$ActivityBase@VForcedEnrollmentTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000bbd3  lea     r12, ??_7CspGetChildNodeNames@ForcedEnrollmentTelemetryProvider@@6B@; const ForcedEnrollmentTelemetryProvider::CspGetChildNodeNames::`vftable'
0x18000bbda  lea     rcx, [rsp+1D0h+var_180]; this
0x18000bbdf  mov     [rsp+1D0h+var_180], r12
0x18000bbe4  call    ?StartActivity@CspGetChildNodeNames@ForcedEnrollmentTelemetryProvider@@QEAAXXZ; ForcedEnrollmentTelemetryProvider::CspGetChildNodeNames::StartActivity(void)
0x18000bbe9  cmp     dword ptr [rbx+2Ch], 0
0x18000bbed  jz      short loc_18000BC06
0x18000bbef  mov     dword ptr [rsi], 0
0x18000bbf5  mov     qword ptr [r14], 0
0x18000bbfc  mov     ebx, 86000011h
0x18000bc01  jmp     loc_18000BD23
0x18000bc06  lea     rax, aRequirenetwork; "RequireNetworkInOOBE"
0x18000bc0d  mov     [rsp+1D0h+var_1B0], 0; int
0x18000bc15  mov     ecx, 8; cb
0x18000bc1a  mov     [rsp+1D0h+psz], rax
0x18000bc1f  mov     [rsp+1D0h+var_1A8], 0
0x18000bc28  call    cs:__imp_CoTaskMemAlloc
0x18000bc2f  nop     dword ptr [rax+rax+00h]
0x18000bc34  mov     [rsp+1D0h+var_1A8], rax
0x18000bc39  test    rax, rax
0x18000bc3c  jnz     short loc_18000BC63
0x18000bc3e  mov     rcx, [rbp+0D8h]; this
0x18000bc45  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\provcsp\\tenan"...
0x18000bc4c  mov     ebx, 8007000Eh
0x18000bc51  mov     edx, 9Dh; void *
0x18000bc56  mov     r9d, ebx; char *
0x18000bc59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bc5e  jmp     loc_18000BD23
0x18000bc63  xor     ecx, ecx
0x18000bc65  mov     [rsp+1D0h+var_188], 1
0x18000bc6a  mov     [rax], rcx
0x18000bc6d  xor     edi, edi
0x18000bc6f  lea     rax, [rsp+1D0h+var_1A8]
0x18000bc74  mov     [rsp+1D0h+var_198], rax
0x18000bc79  lea     rax, [rsp+1D0h+var_1B0]
0x18000bc7e  mov     [rsp+1D0h+var_190], rax
0x18000bc83  mov     rcx, [rsp+rdi*8+1D0h+psz]; psz
0x18000bc88  call    cs:__imp_SysAllocString
0x18000bc8f  nop     dword ptr [rax+rax+00h]
0x18000bc94  mov     rcx, [rsp+1D0h+var_1A8]
0x18000bc99  mov     [rcx+rdi*8], rax
0x18000bc9d  mov     rcx, [rsp+1D0h+var_1A8]
0x18000bca2  cmp     qword ptr [rcx+rdi*8], 0
0x18000bca7  jz      short loc_18000BCF9
0x18000bca9  mov     eax, [rsp+1D0h+var_1B0]
0x18000bcad  inc     edi
0x18000bcaf  inc     eax
0x18000bcb1  mov     [rsp+1D0h+var_1B0], eax
0x18000bcb5  cmp     edi, 1
0x18000bcb8  jb      short loc_18000BC83
0x18000bcba  mov     [r14], rcx
0x18000bcbd  lea     rcx, [rsp+1D0h+var_198]
0x18000bcc2  mov     [rsp+1D0h+var_1A8], 0
0x18000bccb  mov     [rsi], eax
0x18000bccd  call    wil__details__ScopeExitFn__lambda_2fc6b439b24d94e47d4f65647024a2b7______ScopeExitFn__lambda_2fc6b439b24d94e47d4f65647024a2b7___
0x18000bcd2  lea     rcx, [rsp+1D0h+var_180]
0x18000bcd7  call    ?Stop@?$ActivityBase@VForcedEnrollmentTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000bcdc  lea     rcx, [rsp+1D0h+var_180]
0x18000bce1  mov     [rsp+1D0h+var_180], r12
0x18000bce6  call    ?Destroy@?$ActivityBase@VForcedEnrollmentTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000bceb  lea     rcx, [rsp+1D0h+var_180]
0x18000bcf0  call    ??1?$ActivityBase@VForcedEnrollmentTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000bcf5  xor     eax, eax
0x18000bcf7  jmp     short loc_18000BD3E
0x18000bcf9  mov     rcx, [rbp+0D8h]; this
0x18000bd00  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\provcsp\\tenan"...
0x18000bd07  mov     ebx, 8007000Eh
0x18000bd0c  mov     edx, 0AFh; void *
0x18000bd11  mov     r9d, ebx; char *
0x18000bd14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bd19  lea     rcx, [rsp+1D0h+var_198]
0x18000bd1e  call    wil__details__ScopeExitFn__lambda_2fc6b439b24d94e47d4f65647024a2b7______ScopeExitFn__lambda_2fc6b439b24d94e47d4f65647024a2b7___
0x18000bd23  lea     rcx, [rsp+1D0h+var_180]
0x18000bd28  mov     [rsp+1D0h+var_180], r12
0x18000bd2d  call    ?Destroy@?$ActivityBase@VForcedEnrollmentTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000bd32  lea     rcx, [rsp+1D0h+var_180]
0x18000bd37  call    ??1?$ActivityBase@VForcedEnrollmentTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ForcedEnrollmentTelemetryProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000bd3c  mov     eax, ebx
0x18000bd3e  mov     rcx, [rbp+0D0h+var_30]
0x18000bd45  xor     rcx, rsp; StackCookie
0x18000bd48  call    __security_check_cookie
0x18000bd4d  mov     rbx, [rsp+1D0h+arg_0]
0x18000bd55  add     rsp, 1B0h
0x18000bd5c  pop     r14
0x18000bd5e  pop     r12
0x18000bd60  pop     rdi
0x18000bd61  pop     rsi
0x18000bd62  pop     rbp
0x18000bd63  retn
```
