# Microsoft::Windows::MDM::OmadmClient::ConfigManagerInvoker::GetNodeData(ushort const *,ushort * *)

- ea: `0x14004c4f0`
- end: `0x14004c7ce`
- name: `?GetNodeData@ConfigManagerInvoker@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEBGPEAPEAG@Z`
- size: `734`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::ConfigManagerInvoker *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003450`
- `0x14000b0f4`
- `0x14000d71c`
- `0x14000d778`
- `0x14000e610`
- `0x140013404`
- `0x14004c4f0`
- `0x140069010`

## import_xrefs

- `DMCmnUtils!CopyString` at `0x14004c711`
- `DMCmnUtils!CopyString` at `0x14004c711`
- `OLEAUT32!__imp_SysAllocString` at `0x14004c5dd`
- `OLEAUT32!__imp_SysAllocString` at `0x14004c5dd`
- `OLEAUT32!__imp_SysFreeString` at `0x14004c76a`
- `OLEAUT32!__imp_SysFreeString` at `0x14004c76a`
- `OLEAUT32!__imp_VariantInit` at `0x14004c5ba`
- `OLEAUT32!__imp_VariantInit` at `0x14004c5ba`
- `OLEAUT32!__imp_VariantClear` at `0x14004c77b`
- `OLEAUT32!__imp_VariantClear` at `0x14004c77b`
- `OLEAUT32!__imp_VariantChangeType` at `0x14004c6cc`
- `OLEAUT32!__imp_VariantChangeType` at `0x14004c6cc`

## string_xrefs

- `0x14004c604`: `onecoreuap\admin\dm\omadm\omadmclient\lib\src\configmanagerinvoker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::ConfigManagerInvoker::GetNodeData(
        Microsoft::Windows::MDM::OmadmClient::ConfigManagerInvoker *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  __int64 v6; // r8
  unsigned int v7; // edi
  BSTR v8; // rax
  OLECHAR *v9; // rbx
  int v10; // eax
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  HRESULT v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int *v20; // [rsp+20h] [rbp-69h]
  unsigned int v21; // [rsp+30h] [rbp-59h] BYREF
  __int64 v22; // [rsp+38h] [rbp-51h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-49h] BYREF
  _QWORD v24[3]; // [rsp+58h] [rbp-31h] BYREF
  int v25; // [rsp+70h] [rbp-19h]
  unsigned int *v26; // [rsp+78h] [rbp-11h]
  BSTR v27; // [rsp+80h] [rbp-9h] BYREF
  int v28[2]; // [rsp+88h] [rbp-1h] BYREF
  VARIANTARG *p_pvarg; // [rsp+90h] [rbp+7h]
  BSTR *v30; // [rsp+98h] [rbp+Fh]
  __int64 v31; // [rsp+A0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v21 = 0;
  v24[0] = 0;
  v24[1] = "GetNodeData";
  v24[2] = COmaDmLogger::GetLogger();
  v25 = 2;
  v26 = &v21;
  if ( *((_QWORD *)this + 1) )
  {
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
    {
      LODWORD(v27) = 16;
      v30 = &v27;
      v31 = 4;
      v20 = v28;
      McGenEventWrite_EventWriteTransfer(WP_OMADM_CLIENT_PROVIDER_Context, OmaDmClientFunctionEntryPointEvent, v6, 2);
    }
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    *(_QWORD *)v28 = &v21;
    p_pvarg = &pvarg;
    LOBYTE(v30) = 1;
    v8 = SysAllocString(a2);
    v9 = v8;
    v27 = v8;
    if ( v8 )
    {
      v21 = 0;
      v22 = 0;
      v10 = (*(__int64 (__fastcall **)(_QWORD, BSTR, __int64 *))(**((_QWORD **)this + 1) + 80LL))(
              *((_QWORD *)this + 1),
              v8,
              &v22);
      v7 = v10;
      v21 = v10;
      if ( v10 >= 0 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v22 + 104LL))(v22, &pvarg);
        v7 = v12;
        v21 = v12;
        if ( v12 >= 0 )
        {
          if ( pvarg.vt < 2u )
          {
            v24[0] = 0x8000FFFF00002338uLL;
            v7 = -2147418113;
            v17 = v22;
            if ( v22 )
            {
              v22 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            }
          }
          else
          {
            v14 = VariantChangeType(&pvarg, &pvarg, 0, 8u);
            v7 = v14;
            v21 = v14;
            if ( v14 >= 0 )
            {
              v7 = CopyString(pvarg.bstrVal, 0xFFFFFFFF, a3);
              v21 = v7;
              v16 = v22;
              if ( v22 )
              {
                v22 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
              }
            }
            else
            {
              LODWORD(v24[0]) = 9011;
              HIDWORD(v24[0]) = v14;
              v15 = v22;
              if ( v22 )
              {
                v22 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
              }
            }
          }
        }
        else
        {
          LODWORD(v24[0]) = 9013;
          HIDWORD(v24[0]) = v12;
          v13 = v22;
          if ( v22 )
          {
            v22 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          }
        }
      }
      else
      {
        LODWORD(v24[0]) = 9012;
        HIDWORD(v24[0]) = v10;
        v11 = v22;
        if ( v22 )
        {
          v22 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        }
      }
      SysFreeString(v9);
    }
    else
    {
      v7 = -2147024882;
      v21 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\configmanagerinvoker.cpp",
        (const char *)0x8007000ELL,
        (int)v20);
    }
    VariantClear(&pvarg);
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
      McTemplateU0qq_EventWriteTransfer(v18, OmaDmClientFunctionReturnValueEvent, 16, v21);
  }
  else
  {
    v24[0] = 0x8000400500002336uLL;
    v7 = -2147467259;
  }
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v24);
  return v7;
}

```

## disassembly

```asm
0x14004c4f0  push    rbp
0x14004c4f2  push    rbx
0x14004c4f3  push    rsi
0x14004c4f4  push    rdi
0x14004c4f5  push    r12
0x14004c4f7  push    r13
0x14004c4f9  push    r14
0x14004c4fb  lea     rbp, [rsp-27h]
0x14004c500  sub     rsp, 0B0h
0x14004c507  mov     rax, cs:__security_cookie
0x14004c50e  xor     rax, rsp
0x14004c511  mov     [rbp+57h+var_38], rax
0x14004c515  mov     rsi, r8
0x14004c518  mov     rbx, rdx
0x14004c51b  mov     rdi, rcx
0x14004c51e  xor     r14d, r14d
0x14004c521  mov     [rbp+57h+var_B0], r14d
0x14004c525  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14004c52a  mov     [rbp+57h+var_88], r14
0x14004c52e  lea     rcx, aGetnodedata; "GetNodeData"
0x14004c535  mov     [rbp+57h+var_80], rcx
0x14004c539  mov     [rbp+57h+var_78], rax
0x14004c53d  lea     r13d, [r14+2]
0x14004c541  mov     [rbp+57h+var_70], r13d
0x14004c545  lea     rax, [rbp+57h+var_B0]
0x14004c549  mov     [rbp+57h+var_68], rax
0x14004c54d  cmp     [rdi+8], r14
0x14004c551  jnz     short loc_14004C567
0x14004c553  mov     dword ptr [rbp+57h+var_88], 2336h
0x14004c55a  mov     edi, 80004005h
0x14004c55f  mov     dword ptr [rbp+57h+var_88+4], edi
0x14004c562  jmp     loc_14004C7A4
0x14004c567  mov     r12d, 10h
0x14004c56d  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x14004c574  jz      short loc_14004C5A9
0x14004c576  mov     dword ptr [rbp+57h+var_60], r12d
0x14004c57a  lea     rax, [rbp+57h+var_60]
0x14004c57e  mov     [rbp+57h+var_48], rax
0x14004c582  mov     [rbp+57h+var_40], 4
0x14004c58a  lea     rax, [rbp+57h+var_58]
0x14004c58e  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x14004c593  mov     r9d, r13d
0x14004c596  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x14004c59d  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x14004c5a4  call    McGenEventWrite_EventWriteTransfer
0x14004c5a9  xorps   xmm0, xmm0
0x14004c5ac  xor     eax, eax
0x14004c5ae  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x14004c5b2  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x14004c5b6  lea     rcx, [rbp+57h+pvarg]; pvarg
0x14004c5ba  call    cs:__imp_VariantInit
0x14004c5c1  nop     dword ptr [rax+rax+00h]
0x14004c5c6  lea     rax, [rbp+57h+var_B0]
0x14004c5ca  mov     qword ptr [rbp+57h+var_58], rax
0x14004c5ce  lea     rax, [rbp+57h+pvarg]
0x14004c5d2  mov     [rbp+57h+var_50], rax
0x14004c5d6  mov     byte ptr [rbp+57h+var_48], 1
0x14004c5da  mov     rcx, rbx; psz
0x14004c5dd  call    cs:__imp_SysAllocString
0x14004c5e4  nop     dword ptr [rax+rax+00h]
0x14004c5e9  mov     rbx, rax
0x14004c5ec  mov     [rbp+57h+var_60], rax
0x14004c5f0  test    rax, rax
0x14004c5f3  jnz     short loc_14004C619
0x14004c5f5  mov     edi, 8007000Eh
0x14004c5fa  mov     [rbp+57h+var_B0], edi
0x14004c5fd  mov     rcx, [rbp+5Fh]; this
0x14004c601  mov     r9d, edi; char *
0x14004c604  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14004c60b  lea     edx, [rax+3Bh]; void *
0x14004c60e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004c613  nop
0x14004c614  jmp     loc_14004C777
0x14004c619  mov     [rbp+57h+var_B0], r14d
0x14004c61d  mov     [rbp+57h+var_A8], r14
0x14004c621  mov     rcx, [rdi+8]
0x14004c625  mov     rax, [rcx]
0x14004c628  lea     r8, [rbp+57h+var_A8]
0x14004c62c  mov     rdx, rbx
0x14004c62f  mov     rax, [rax+50h]
0x14004c633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c638  mov     edi, eax
0x14004c63a  mov     [rbp+57h+var_B0], eax
0x14004c63d  test    eax, eax
0x14004c63f  jns     short loc_14004C66A
0x14004c641  mov     dword ptr [rbp+57h+var_88], 2334h
0x14004c648  mov     dword ptr [rbp+57h+var_88+4], eax
0x14004c64b  mov     rcx, [rbp+57h+var_A8]
0x14004c64f  test    rcx, rcx
0x14004c652  jz      short loc_14004C665
0x14004c654  mov     [rbp+57h+var_A8], r14
0x14004c658  mov     rax, [rcx]
0x14004c65b  mov     rax, [rax+10h]
0x14004c65f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c664  nop
0x14004c665  jmp     loc_14004C767
0x14004c66a  mov     rcx, [rbp+57h+var_A8]
0x14004c66e  mov     rax, [rcx]
0x14004c671  lea     rdx, [rbp+57h+pvarg]
0x14004c675  mov     rax, [rax+68h]
0x14004c679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c67e  mov     edi, eax
0x14004c680  mov     [rbp+57h+var_B0], eax
0x14004c683  test    eax, eax
0x14004c685  jns     short loc_14004C6B0
0x14004c687  mov     dword ptr [rbp+57h+var_88], 2335h
0x14004c68e  mov     dword ptr [rbp+57h+var_88+4], eax
0x14004c691  mov     rcx, [rbp+57h+var_A8]
0x14004c695  test    rcx, rcx
0x14004c698  jz      short loc_14004C6AB
0x14004c69a  mov     [rbp+57h+var_A8], r14
0x14004c69e  mov     rax, [rcx]
0x14004c6a1  mov     rax, [rax+10h]
0x14004c6a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c6aa  nop
0x14004c6ab  jmp     loc_14004C767
0x14004c6b0  cmp     word ptr [rbp+57h+pvarg], r13w
0x14004c6b5  jb      loc_14004C73E
0x14004c6bb  mov     r9d, 8; vt
0x14004c6c1  xor     r8d, r8d; wFlags
0x14004c6c4  lea     rdx, [rbp+57h+pvarg]; pvarSrc
0x14004c6c8  lea     rcx, [rbp+57h+pvarg]; pvargDest
0x14004c6cc  call    cs:__imp_VariantChangeType
0x14004c6d3  nop     dword ptr [rax+rax+00h]
0x14004c6d8  mov     edi, eax
0x14004c6da  mov     [rbp+57h+var_B0], eax
0x14004c6dd  test    eax, eax
0x14004c6df  jns     short loc_14004C707
0x14004c6e1  mov     dword ptr [rbp+57h+var_88], 2333h
0x14004c6e8  mov     dword ptr [rbp+57h+var_88+4], eax
0x14004c6eb  mov     rcx, [rbp+57h+var_A8]
0x14004c6ef  test    rcx, rcx
0x14004c6f2  jz      short loc_14004C705
0x14004c6f4  mov     [rbp+57h+var_A8], r14
0x14004c6f8  mov     rax, [rcx]
0x14004c6fb  mov     rax, [rax+10h]
0x14004c6ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c704  nop
0x14004c705  jmp     short loc_14004C767
0x14004c707  mov     r8, rsi
0x14004c70a  or      edx, 0FFFFFFFFh
0x14004c70d  mov     rcx, qword ptr [rbp+57h+pvarg+8]
0x14004c711  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x14004c718  nop     dword ptr [rax+rax+00h]
0x14004c71d  mov     edi, eax
0x14004c71f  mov     [rbp+57h+var_B0], eax
0x14004c722  mov     rcx, [rbp+57h+var_A8]
0x14004c726  test    rcx, rcx
0x14004c729  jz      short loc_14004C73C
0x14004c72b  mov     [rbp+57h+var_A8], r14
0x14004c72f  mov     rdx, [rcx]
0x14004c732  mov     rax, [rdx+10h]
0x14004c736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c73b  nop
0x14004c73c  jmp     short loc_14004C767
0x14004c73e  mov     dword ptr [rbp+57h+var_88], 2338h
0x14004c745  mov     edi, 8000FFFFh
0x14004c74a  mov     dword ptr [rbp+57h+var_88+4], edi
0x14004c74d  mov     rcx, [rbp+57h+var_A8]
0x14004c751  test    rcx, rcx
0x14004c754  jz      short loc_14004C767
0x14004c756  mov     [rbp+57h+var_A8], r14
0x14004c75a  mov     rax, [rcx]
0x14004c75d  mov     rax, [rax+10h]
0x14004c761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004c766  nop
0x14004c767  mov     rcx, rbx; bstrString
0x14004c76a  call    cs:__imp_SysFreeString
0x14004c771  nop     dword ptr [rax+rax+00h]
0x14004c776  nop
0x14004c777  lea     rcx, [rbp+57h+pvarg]; pvarg
0x14004c77b  call    cs:__imp_VariantClear
0x14004c782  nop     dword ptr [rax+rax+00h]
0x14004c787  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x14004c78e  jz      short loc_14004C7A4
0x14004c790  mov     r9d, [rbp+57h+var_B0]
0x14004c794  mov     r8d, r12d
0x14004c797  lea     rdx, OmaDmClientFunctionReturnValueEvent
0x14004c79e  call    McTemplateU0qq_EventWriteTransfer
0x14004c7a3  nop
0x14004c7a4  lea     rcx, [rbp+57h+var_88]; this
0x14004c7a8  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14004c7ad  mov     eax, edi
0x14004c7af  mov     rcx, [rbp+57h+var_38]
0x14004c7b3  xor     rcx, rsp; StackCookie
0x14004c7b6  call    __security_check_cookie
0x14004c7bb  add     rsp, 0B0h
0x14004c7c2  pop     r14
0x14004c7c4  pop     r13
0x14004c7c6  pop     r12
0x14004c7c8  pop     rdi
0x14004c7c9  pop     rsi
0x14004c7ca  pop     rbx
0x14004c7cb  pop     rbp
0x14004c7cc  retn
```
