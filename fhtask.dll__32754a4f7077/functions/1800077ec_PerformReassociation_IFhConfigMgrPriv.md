# PerformReassociation(IFhConfigMgrPriv *)

- ea: `0x1800077ec`
- end: `0x180007b9a`
- name: `?PerformReassociation@@YAJPEAUIFhConfigMgrPriv@@@Z`
- size: `942`
- prototype: `__int64 __fastcall(struct IFhConfigMgrPriv *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007ba0`

## callees

- `0x1800011d8`
- `0x1800067a0`
- `0x180006988`
- `0x180006a10`
- `0x180006b24`
- `0x1800077ec`
- `0x1800097b0`
- `0x180009a00`
- `0x18000b010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000797e`
- `msvcrt!wcsrchr` at `0x18000797e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007af6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007af6`
- `OLEAUT32!__imp_SysAllocString` at `0x180007a7d`
- `OLEAUT32!__imp_SysAllocString` at `0x180007a7d`
- `OLEAUT32!__imp_SysFreeString` at `0x180007b16`
- `OLEAUT32!__imp_SysFreeString` at `0x180007b20`
- `OLEAUT32!__imp_SysFreeString` at `0x180007b16`
- `OLEAUT32!__imp_SysFreeString` at `0x180007b20`
- `ole32!CoCreateInstance` at `0x1800079c0`
- `ole32!CoCreateInstance` at `0x1800079c0`

## pseudocode

```c
__int64 __fastcall PerformReassociation(struct IFhConfigMgrPriv *a1)
{
  HRESULT v1; // eax
  int v2; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r9
  LPVOID v6; // rsi
  __int64 v7; // r14
  const OLECHAR *v8; // rdi
  BSTR *v9; // rax
  BSTR *v10; // rbx
  BSTR v11; // rax
  BSTR bstrString; // [rsp+30h] [rbp-29h] BYREF
  wchar_t *Str; // [rsp+38h] [rbp-21h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-19h] BYREF
  __int64 v16; // [rsp+48h] [rbp-11h] BYREF
  int v17; // [rsp+50h] [rbp-9h] BYREF
  __int64 v18; // [rsp+58h] [rbp-1h] BYREF
  BSTR *v19; // [rsp+60h] [rbp+7h] BYREF
  OLECHAR *psz[2]; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v21; // [rsp+78h] [rbp+1Fh]
  unsigned __int64 v22; // [rsp+80h] [rbp+27h]

  v18 = 0;
  v16 = 0;
  ppv = 0;
  bstrString = 0;
  Str = 0;
  v22 = 7;
  v21 = 0;
  LOWORD(psz[0]) = 0;
  v17 = 0;
  v1 = (*(__int64 (__fastcall **)(struct IFhConfigMgrPriv *, __int64 *))(*(_QWORD *)a1 + 96LL))(a1, &v18);
  v2 = v1;
  if ( v1 >= 0 )
  {
    v1 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v18)(
           v18,
           &GUID_16d085cc_5bf2_11e0_8680_18a90531a85a,
           &v16);
    v2 = v1;
    if ( v1 >= 0 )
    {
      v1 = (*(__int64 (__fastcall **)(__int64, __int64, BSTR *))(*(_QWORD *)v16 + 24LL))(v16, 1, &bstrString);
      v2 = v1;
      if ( v1 >= 0 )
      {
        v1 = (*(__int64 (__fastcall **)(__int64, __int64, wchar_t **))(*(_QWORD *)v16 + 40LL))(v16, 4, &Str);
        v2 = v1;
        if ( v1 >= 0 )
        {
          *wcsrchr(Str, 0x5Cu) = 0;
          std::wstring::operator=(psz, bstrString);
          std::wstring::operator+=(psz, Str);
          v1 = CoCreateInstance(&CLSID_FhReassociation, 0, 0x17u, &GUID_16d085ce_5bf2_11e0_8680_18a90531a85a, &ppv);
          v2 = v1;
          if ( v1 >= 0 )
          {
            v1 = (*(__int64 (__fastcall **)(LPVOID, BSTR, int *))(*(_QWORD *)ppv + 24LL))(ppv, bstrString, &v17);
            v2 = v1;
            if ( v1 >= 0 )
            {
              v6 = ppv;
              v7 = *(_QWORD *)ppv;
              v8 = (const OLECHAR *)psz;
              if ( v22 >= 8 )
                v8 = psz[0];
              v9 = (BSTR *)operator new(0x18u);
              v10 = v9;
              if ( !v9 || (v9[1] = 0, *((_DWORD *)v9 + 4) = 1, v11 = SysAllocString(v8), (*v10 = v11) == 0) && v8 )
                _com_issue_error(-2147024882);
              v19 = v10;
              v2 = (*(__int64 (__fastcall **)(LPVOID, BSTR, BSTR))(v7 + 80))(v6, bstrString, v11);
              _bstr_t::~_bstr_t((_bstr_t *)&v19);
              if ( v2 < 0 )
              {
                v3 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v4 = 34;
                  v5 = (unsigned int)v2;
                  goto LABEL_35;
                }
              }
            }
            else
            {
              v3 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v4 = 33;
                goto LABEL_5;
              }
            }
          }
          else
          {
            v3 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v4 = 32;
              goto LABEL_5;
            }
          }
        }
        else
        {
          v3 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v4 = 31;
            goto LABEL_5;
          }
        }
      }
      else
      {
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v4 = 30;
          goto LABEL_5;
        }
      }
    }
    else
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v4 = 29;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 28;
LABEL_5:
      v5 = (unsigned int)v1;
LABEL_35:
      WPP_SF_d(v3[2], v4, &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids, v5);
    }
  }
  if ( v22 >= 8 )
    operator delete(psz[0]);
  v22 = 7;
  v21 = 0;
  LOWORD(psz[0]) = 0;
  SysFreeString(Str);
  SysFreeString(bstrString);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800077ec  mov     [rsp-8+arg_8], rbx
0x1800077f1  mov     [rsp-8+arg_10], rsi
0x1800077f6  push    rbp
0x1800077f7  push    rdi
0x1800077f8  push    r14
0x1800077fa  lea     rbp, [rsp-47h]
0x1800077ff  sub     rsp, 0A0h
0x180007806  mov     rax, cs:__security_cookie
0x18000780d  xor     rax, rsp
0x180007810  mov     [rbp+57h+var_20], rax
0x180007814  mov     [rbp+57h+var_58], 0
0x18000781c  mov     [rbp+57h+var_68], 0
0x180007824  mov     [rbp+57h+var_70], 0
0x18000782c  mov     [rbp+57h+bstrString], 0
0x180007834  mov     [rbp+57h+Str], 0
0x18000783c  mov     [rbp+57h+var_30], 7
0x180007844  mov     [rbp+57h+var_38], 0
0x18000784c  xor     eax, eax
0x18000784e  mov     word ptr [rbp+57h+psz], ax
0x180007852  mov     [rbp+57h+var_60], eax
0x180007855  mov     rax, [rcx]
0x180007858  lea     rdx, [rbp+57h+var_58]
0x18000785c  mov     rax, [rax+60h]
0x180007860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007865  mov     ebx, eax
0x180007867  test    eax, eax
0x180007869  jns     short loc_180007899
0x18000786b  lea     rdx, WPP_GLOBAL_Control
0x180007872  mov     rcx, cs:WPP_GLOBAL_Control
0x180007879  cmp     rcx, rdx
0x18000787c  jz      loc_180007AEB
0x180007882  test    byte ptr [rcx+1Ch], 1
0x180007886  jz      loc_180007AEB
0x18000788c  mov     edx, 1Ch
0x180007891  mov     r9d, eax
0x180007894  jmp     loc_180007ADB
0x180007899  mov     rcx, [rbp+57h+var_58]
0x18000789d  mov     rax, [rcx]
0x1800078a0  lea     r8, [rbp+57h+var_68]
0x1800078a4  lea     rdx, _GUID_16d085cc_5bf2_11e0_8680_18a90531a85a
0x1800078ab  mov     rax, [rax]
0x1800078ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078b3  mov     ebx, eax
0x1800078b5  test    eax, eax
0x1800078b7  jns     short loc_1800078E1
0x1800078b9  lea     rdx, WPP_GLOBAL_Control
0x1800078c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078c7  cmp     rcx, rdx
0x1800078ca  jz      loc_180007AEB
0x1800078d0  test    byte ptr [rcx+1Ch], 1
0x1800078d4  jz      loc_180007AEB
0x1800078da  mov     edx, 1Dh
0x1800078df  jmp     short loc_180007891
0x1800078e1  mov     rcx, [rbp+57h+var_68]
0x1800078e5  mov     rax, [rcx]
0x1800078e8  lea     r8, [rbp+57h+bstrString]
0x1800078ec  mov     edx, 1
0x1800078f1  mov     rax, [rax+18h]
0x1800078f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078fa  mov     ebx, eax
0x1800078fc  test    eax, eax
0x1800078fe  jns     short loc_18000792B
0x180007900  lea     rdx, WPP_GLOBAL_Control
0x180007907  mov     rcx, cs:WPP_GLOBAL_Control
0x18000790e  cmp     rcx, rdx
0x180007911  jz      loc_180007AEB
0x180007917  test    byte ptr [rcx+1Ch], 1
0x18000791b  jz      loc_180007AEB
0x180007921  mov     edx, 1Eh
0x180007926  jmp     loc_180007891
0x18000792b  mov     rcx, [rbp+57h+var_68]
0x18000792f  mov     rax, [rcx]
0x180007932  lea     r8, [rbp+57h+Str]
0x180007936  mov     edx, 4
0x18000793b  mov     rax, [rax+28h]
0x18000793f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007944  mov     ebx, eax
0x180007946  test    eax, eax
0x180007948  jns     short loc_180007975
0x18000794a  lea     rdx, WPP_GLOBAL_Control
0x180007951  mov     rcx, cs:WPP_GLOBAL_Control
0x180007958  cmp     rcx, rdx
0x18000795b  jz      loc_180007AEB
0x180007961  test    byte ptr [rcx+1Ch], 1
0x180007965  jz      loc_180007AEB
0x18000796b  mov     edx, 1Fh
0x180007970  jmp     loc_180007891
0x180007975  mov     edx, 5Ch ; '\'; Ch
0x18000797a  mov     rcx, [rbp+57h+Str]; Str
0x18000797e  call    cs:__imp_wcsrchr
0x180007984  xor     ecx, ecx
0x180007986  mov     [rax], cx
0x180007989  mov     rdx, [rbp+57h+bstrString]; void *
0x18000798d  lea     rcx, [rbp+57h+psz]; Src
0x180007991  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator=(ushort const *)
0x180007996  mov     rdx, [rbp+57h+Str]; void *
0x18000799a  lea     rcx, [rbp+57h+psz]; Src
0x18000799e  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x1800079a3  lea     rax, [rbp+57h+var_70]
0x1800079a7  mov     [rsp+0B0h+ppv], rax; ppv
0x1800079ac  lea     r9, _GUID_16d085ce_5bf2_11e0_8680_18a90531a85a; riid
0x1800079b3  xor     edx, edx; pUnkOuter
0x1800079b5  lea     r8d, [rdx+17h]; dwClsContext
0x1800079b9  lea     rcx, CLSID_FhReassociation; rclsid
0x1800079c0  call    cs:__imp_CoCreateInstance
0x1800079c6  mov     ebx, eax
0x1800079c8  test    eax, eax
0x1800079ca  jns     short loc_1800079F7
0x1800079cc  lea     rdx, WPP_GLOBAL_Control
0x1800079d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800079da  cmp     rcx, rdx
0x1800079dd  jz      loc_180007AEB
0x1800079e3  test    byte ptr [rcx+1Ch], 1
0x1800079e7  jz      loc_180007AEB
0x1800079ed  mov     edx, 20h ; ' '
0x1800079f2  jmp     loc_180007891
0x1800079f7  mov     rcx, [rbp+57h+var_70]
0x1800079fb  mov     rax, [rcx]
0x1800079fe  lea     r8, [rbp+57h+var_60]
0x180007a02  mov     rdx, [rbp+57h+bstrString]
0x180007a06  mov     rax, [rax+18h]
0x180007a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a0f  mov     ebx, eax
0x180007a11  test    eax, eax
0x180007a13  jns     short loc_180007A40
0x180007a15  lea     rdx, WPP_GLOBAL_Control
0x180007a1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a23  cmp     rcx, rdx
0x180007a26  jz      loc_180007AEB
0x180007a2c  test    byte ptr [rcx+1Ch], 1
0x180007a30  jz      loc_180007AEB
0x180007a36  mov     edx, 21h ; '!'
0x180007a3b  jmp     loc_180007891
0x180007a40  mov     rsi, [rbp+57h+var_70]
0x180007a44  mov     r14, [rsi]
0x180007a47  lea     rdi, [rbp+57h+psz]
0x180007a4b  cmp     [rbp+57h+var_30], 8
0x180007a50  cmovnb  rdi, [rbp+57h+psz]
0x180007a55  mov     ecx, 18h; Size
0x180007a5a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007a5f  mov     rbx, rax
0x180007a62  test    rax, rax
0x180007a65  jz      loc_180007B8F
0x180007a6b  mov     qword ptr [rax+8], 0
0x180007a73  mov     dword ptr [rax+10h], 1
0x180007a7a  mov     rcx, rdi; psz
0x180007a7d  call    cs:__imp_SysAllocString
0x180007a83  mov     [rbx], rax
0x180007a86  test    rax, rax
0x180007a89  jnz     short loc_180007A94
0x180007a8b  test    rdi, rdi
0x180007a8e  jnz     loc_180007B8F
0x180007a94  mov     [rbp+57h+var_50], rbx
0x180007a98  mov     r8, rax
0x180007a9b  mov     rdx, [rbp+57h+bstrString]
0x180007a9f  mov     rcx, rsi
0x180007aa2  mov     rax, [r14+50h]
0x180007aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aab  mov     ebx, eax
0x180007aad  lea     rcx, [rbp+57h+var_50]; this
0x180007ab1  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180007ab6  test    ebx, ebx
0x180007ab8  jns     short loc_180007AEB
0x180007aba  lea     rdx, WPP_GLOBAL_Control
0x180007ac1  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ac8  cmp     rcx, rdx
0x180007acb  jz      short loc_180007AEB
0x180007acd  test    byte ptr [rcx+1Ch], 1
0x180007ad1  jz      short loc_180007AEB
0x180007ad3  mov     edx, 22h ; '"'
0x180007ad8  mov     r9d, ebx
0x180007adb  lea     r8, WPP_8158daeccbd13eff1bb477c819869c69_Traceguids
0x180007ae2  mov     rcx, [rcx+10h]
0x180007ae6  call    WPP_SF_d
0x180007aeb  cmp     [rbp+57h+var_30], 8
0x180007af0  jb      short loc_180007AFC
0x180007af2  mov     rcx, [rbp+57h+psz]
0x180007af6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007afc  mov     [rbp+57h+var_30], 7
0x180007b04  mov     [rbp+57h+var_38], 0
0x180007b0c  xor     eax, eax
0x180007b0e  mov     word ptr [rbp+57h+psz], ax
0x180007b12  mov     rcx, [rbp+57h+Str]; bstrString
0x180007b16  call    cs:__imp_SysFreeString
0x180007b1c  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180007b20  call    cs:__imp_SysFreeString
0x180007b26  nop
0x180007b27  mov     rcx, [rbp+57h+var_70]
0x180007b2b  test    rcx, rcx
0x180007b2e  jz      short loc_180007B3D
0x180007b30  mov     rax, [rcx]
0x180007b33  mov     rax, [rax+10h]
0x180007b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b3c  nop
0x180007b3d  mov     rcx, [rbp+57h+var_68]
0x180007b41  test    rcx, rcx
0x180007b44  jz      short loc_180007B53
0x180007b46  mov     rax, [rcx]
0x180007b49  mov     rax, [rax+10h]
0x180007b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b52  nop
0x180007b53  mov     rcx, [rbp+57h+var_58]
0x180007b57  test    rcx, rcx
0x180007b5a  jz      short loc_180007B69
0x180007b5c  mov     rax, [rcx]
0x180007b5f  mov     rax, [rax+10h]
0x180007b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b68  nop
0x180007b69  mov     eax, ebx
0x180007b6b  mov     rcx, [rbp+57h+var_20]
0x180007b6f  xor     rcx, rsp; StackCookie
0x180007b72  call    __security_check_cookie
0x180007b77  lea     r11, [rsp+0B0h+var_10]
0x180007b7f  mov     rbx, [r11+28h]
0x180007b83  mov     rsi, [r11+30h]
0x180007b87  mov     rsp, r11
0x180007b8a  pop     r14
0x180007b8c  pop     rdi
0x180007b8d  pop     rbp
0x180007b8e  retn
0x180007b8f  mov     ecx, 8007000Eh; int
0x180007b94  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
