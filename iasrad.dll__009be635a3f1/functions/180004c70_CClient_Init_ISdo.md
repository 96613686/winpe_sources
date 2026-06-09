# CClient::Init(ISdo *)

- ea: `0x180004c70`
- end: `0x180005013`
- name: `?Init@CClient@@UEAAJPEAUISdo@@@Z`
- size: `931`
- prototype: `__int64 __fastcall(CClient *__hidden this, struct ISdo *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004c70`
- `0x1800075bc`
- `0x1800077c0`
- `0x1800094e4`
- `0x18001d31c`
- `0x18001eaf4`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180004c8a`
- `OLEAUT32!__imp_VariantInit` at `0x180004c8a`
- `OLEAUT32!__imp_VariantClear` at `0x180004d45`
- `OLEAUT32!__imp_VariantClear` at `0x180004df7`
- `OLEAUT32!__imp_VariantClear` at `0x180004e71`
- `OLEAUT32!__imp_VariantClear` at `0x180004ee3`
- `OLEAUT32!__imp_VariantClear` at `0x180004f76`
- `OLEAUT32!__imp_VariantClear` at `0x180004fe3`
- `OLEAUT32!__imp_VariantClear` at `0x180004ffe`
- `OLEAUT32!__imp_VariantClear` at `0x180004d45`
- `OLEAUT32!__imp_VariantClear` at `0x180004df7`
- `OLEAUT32!__imp_VariantClear` at `0x180004e71`
- `OLEAUT32!__imp_VariantClear` at `0x180004ee3`
- `OLEAUT32!__imp_VariantClear` at `0x180004f76`
- `OLEAUT32!__imp_VariantClear` at `0x180004fe3`
- `OLEAUT32!__imp_VariantClear` at `0x180004ffe`

## string_xrefs

- `0x180004cdb`: `Unable to obtain Client Address Property during Client object initialization`
- `0x180004d93`: `Unable to obtain Client shared secret Property during Client object initialization`
- `0x180004e45`: `Unable to obtain Client Signature Property during Client object initialization`
- `0x180004ebf`: `Unable to obtain Client NAS Manufacturer Property during Client object initialization`
- `0x180004f31`: `Unable to obtain SDO Name Property during Client object initialization`
- `0x180004fb8`: `Unable to obtain Client IsClientEnabled Property during Client object initialization`

## pseudocode

```c
__int64 __fastcall CClient::Init(CClient *this, struct ISdo *a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  VARIANTARG pvarg; // [rsp+20h] [rbp-48h] BYREF
  struct tagVARIANT v8; // [rsp+40h] [rbp-28h] BYREF

  VariantInit(&pvarg);
  if ( ((int (__fastcall *)(struct ISdo *, __int64, VARIANTARG *))a2->lpVtbl->GetProperty)(a2, 1028, &pvarg) < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Unable to obtain Client Address Property during Client object initialization");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_1d3eb203fb0232ec74f11b7ccc17ee04_Traceguids, "NPSRAD");
    }
    goto LABEL_16;
  }
  if ( pvarg.vt != 8 )
    goto LABEL_7;
  v4 = StringCchCopyW((unsigned __int16 *)this + 436, 0x100u, pvarg.bstrVal);
  if ( v4 < 0 )
    goto LABEL_40;
  VariantClear(&pvarg);
  v4 = ((__int64 (__fastcall *)(struct ISdo *, __int64, VARIANTARG *))a2->lpVtbl->GetProperty)(a2, 1026, &pvarg);
  if ( v4 >= 0 )
  {
    v8 = pvarg;
    if ( !(unsigned int)CClient::SetSecret(this, &v8) )
    {
LABEL_16:
      v4 = -2147467259;
      goto LABEL_40;
    }
    VariantClear(&pvarg);
    v4 = ((__int64 (__fastcall *)(struct ISdo *, __int64, VARIANTARG *))a2->lpVtbl->GetProperty)(a2, 1024, &pvarg);
    if ( v4 >= 0 )
    {
      *((_DWORD *)this + 347) = pvarg.iVal != 0;
      VariantClear(&pvarg);
      v4 = ((__int64 (__fastcall *)(struct ISdo *, __int64, VARIANTARG *))a2->lpVtbl->GetProperty)(a2, 1027, &pvarg);
      if ( v4 >= 0 )
      {
        *((_DWORD *)this + 348) = pvarg.lVal;
        VariantClear(&pvarg);
        v4 = ((__int64 (__fastcall *)(struct ISdo *, __int64, VARIANTARG *))a2->lpVtbl->GetProperty)(a2, 2, &pvarg);
        if ( v4 >= 0 )
        {
          if ( pvarg.vt != 8 )
          {
LABEL_7:
            v4 = -2147024809;
            goto LABEL_40;
          }
          v4 = StringCchCopyW((unsigned __int16 *)this + 180, 0x100u, pvarg.bstrVal);
          if ( v4 >= 0 )
          {
            VariantClear(&pvarg);
            v4 = ((__int64 (__fastcall *)(struct ISdo *, __int64, VARIANTARG *))a2->lpVtbl->GetProperty)(
                   a2,
                   1030,
                   &pvarg);
            if ( v4 >= 0 )
            {
              *((_DWORD *)this + 349) = pvarg.iVal == -1;
              VariantClear(&pvarg);
              *((_DWORD *)this + 350) = RegistryUtil::isConfigEnabled((const WCHAR *)this + 180, 0);
              goto LABEL_40;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
            {
              WppDbgPrint("Unable to obtain Client IsClientEnabled Property during Client object initialization");
              v5 = 15;
              goto LABEL_14;
            }
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
               && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WppDbgPrint("Unable to obtain SDO Name Property during Client object initialization");
          v5 = 14;
          goto LABEL_14;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("Unable to obtain Client NAS Manufacturer Property during Client object initialization");
        v5 = 13;
        goto LABEL_14;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Unable to obtain Client Signature Property during Client object initialization");
      v5 = 12;
      goto LABEL_14;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Unable to obtain Client shared secret Property during Client object initialization");
    v5 = 11;
LABEL_14:
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, WPP_1d3eb203fb0232ec74f11b7ccc17ee04_Traceguids, "NPSRAD");
  }
LABEL_40:
  VariantClear(&pvarg);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180004c70  push    rbp
0x180004c72  push    rbx
0x180004c73  push    rsi
0x180004c74  push    rdi
0x180004c75  push    r14
0x180004c77  push    r15
0x180004c79  mov     rbp, rsp
0x180004c7c  sub     rsp, 68h
0x180004c80  mov     r14, rcx
0x180004c83  mov     rsi, rdx
0x180004c86  lea     rcx, [rbp+pvarg]; pvarg
0x180004c8a  call    cs:__imp_VariantInit
0x180004c90  mov     rax, [rsi]
0x180004c93  lea     r8, [rbp+pvarg]
0x180004c97  mov     edx, 404h
0x180004c9c  mov     rcx, rsi
0x180004c9f  mov     rax, [rax+40h]
0x180004ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ca8  test    eax, eax
0x180004caa  jns     short loc_180004D0F
0x180004cac  mov     rcx, cs:WPP_GLOBAL_Control
0x180004cb3  lea     rax, WPP_GLOBAL_Control
0x180004cba  cmp     rcx, rax
0x180004cbd  jz      loc_180004DE9
0x180004cc3  cmp     byte ptr [rcx+19h], 2
0x180004cc7  jb      loc_180004DE9
0x180004ccd  mov     edi, 100h
0x180004cd2  test    [rcx+1Ch], edi
0x180004cd5  jz      loc_180004DE9
0x180004cdb  lea     rcx, aUnableToObtain_7; "Unable to obtain Client Address Propert"...
0x180004ce2  call    WppDbgPrint
0x180004ce7  mov     rcx, cs:WPP_GLOBAL_Control
0x180004cee  lea     r9, aNpsrad; "NPSRAD"
0x180004cf5  mov     edx, 0Ah
0x180004cfa  lea     r8, WPP_1d3eb203fb0232ec74f11b7ccc17ee04_Traceguids
0x180004d01  mov     rcx, [rcx+10h]
0x180004d05  call    WPP_SF_s
0x180004d0a  jmp     loc_180004DE9
0x180004d0f  cmp     word ptr [rbp+pvarg], 8
0x180004d14  jz      short loc_180004D20
0x180004d16  mov     ebx, 80070057h
0x180004d1b  jmp     loc_180004FFA
0x180004d20  mov     r8, qword ptr [rbp+pvarg+8]; unsigned __int16 *
0x180004d24  lea     rcx, [r14+368h]; unsigned __int16 *
0x180004d2b  mov     edi, 100h
0x180004d30  mov     edx, edi; unsigned __int64
0x180004d32  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004d37  mov     ebx, eax
0x180004d39  test    eax, eax
0x180004d3b  js      loc_180004FFA
0x180004d41  lea     rcx, [rbp+pvarg]; pvarg
0x180004d45  call    cs:__imp_VariantClear
0x180004d4b  mov     rax, [rsi]
0x180004d4e  lea     r8, [rbp+pvarg]
0x180004d52  mov     edx, 402h
0x180004d57  mov     rcx, rsi
0x180004d5a  mov     rax, [rax+40h]
0x180004d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d63  mov     ebx, eax
0x180004d65  test    eax, eax
0x180004d67  jns     short loc_180004DC7
0x180004d69  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d70  lea     rax, WPP_GLOBAL_Control
0x180004d77  cmp     rcx, rax
0x180004d7a  jz      loc_180004FFA
0x180004d80  cmp     byte ptr [rcx+19h], 2
0x180004d84  jb      loc_180004FFA
0x180004d8a  test    [rcx+1Ch], edi
0x180004d8d  jz      loc_180004FFA
0x180004d93  lea     rcx, aUnableToObtain_2; "Unable to obtain Client shared secret P"...
0x180004d9a  call    WppDbgPrint
0x180004d9f  mov     edx, 0Bh
0x180004da4  mov     rcx, cs:WPP_GLOBAL_Control
0x180004dab  lea     r9, aNpsrad; "NPSRAD"
0x180004db2  lea     r8, WPP_1d3eb203fb0232ec74f11b7ccc17ee04_Traceguids
0x180004db9  mov     rcx, [rcx+10h]
0x180004dbd  call    WPP_SF_s
0x180004dc2  jmp     loc_180004FFA
0x180004dc7  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180004dcb  lea     rdx, [rbp+var_28]; struct tagVARIANT
0x180004dcf  mov     rcx, r14; this
0x180004dd2  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180004dd7  movaps  xmmword ptr [rbp+var_28], xmm0
0x180004ddb  movsd   qword ptr [rbp+var_28+10h], xmm1
0x180004de0  call    ?SetSecret@CClient@@AEAAHUtagVARIANT@@@Z; CClient::SetSecret(tagVARIANT)
0x180004de5  test    eax, eax
0x180004de7  jnz     short loc_180004DF3
0x180004de9  mov     ebx, 80004005h
0x180004dee  jmp     loc_180004FFA
0x180004df3  lea     rcx, [rbp+pvarg]; pvarg
0x180004df7  call    cs:__imp_VariantClear
0x180004dfd  mov     rax, [rsi]
0x180004e00  lea     r8, [rbp+pvarg]
0x180004e04  mov     edx, 400h
0x180004e09  mov     rcx, rsi
0x180004e0c  mov     rax, [rax+40h]
0x180004e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e15  mov     ebx, eax
0x180004e17  test    eax, eax
0x180004e19  jns     short loc_180004E5B
0x180004e1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e22  lea     rax, WPP_GLOBAL_Control
0x180004e29  cmp     rcx, rax
0x180004e2c  jz      loc_180004FFA
0x180004e32  cmp     byte ptr [rcx+19h], 2
0x180004e36  jb      loc_180004FFA
0x180004e3c  test    [rcx+1Ch], edi
0x180004e3f  jz      loc_180004FFA
0x180004e45  lea     rcx, aUnableToObtain_0; "Unable to obtain Client Signature Prope"...
0x180004e4c  call    WppDbgPrint
0x180004e51  mov     edx, 0Ch
0x180004e56  jmp     loc_180004DA4
0x180004e5b  xor     eax, eax
0x180004e5d  xor     ecx, ecx
0x180004e5f  cmp     cx, word ptr [rbp+pvarg+8]
0x180004e63  lea     rcx, [rbp+pvarg]; pvarg
0x180004e67  setnz   al
0x180004e6a  mov     [r14+56Ch], eax
0x180004e71  call    cs:__imp_VariantClear
0x180004e77  mov     rax, [rsi]
0x180004e7a  lea     r8, [rbp+pvarg]
0x180004e7e  mov     edx, 403h
0x180004e83  mov     rcx, rsi
0x180004e86  mov     rax, [rax+40h]
0x180004e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e8f  mov     ebx, eax
0x180004e91  test    eax, eax
0x180004e93  jns     short loc_180004ED5
0x180004e95  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e9c  lea     rax, WPP_GLOBAL_Control
0x180004ea3  cmp     rcx, rax
0x180004ea6  jz      loc_180004FFA
0x180004eac  cmp     byte ptr [rcx+19h], 2
0x180004eb0  jb      loc_180004FFA
0x180004eb6  test    [rcx+1Ch], edi
0x180004eb9  jz      loc_180004FFA
0x180004ebf  lea     rcx, aUnableToObtain_3; "Unable to obtain Client NAS Manufacture"...
0x180004ec6  call    WppDbgPrint
0x180004ecb  mov     edx, 0Dh
0x180004ed0  jmp     loc_180004DA4
0x180004ed5  mov     eax, dword ptr [rbp+pvarg+8]
0x180004ed8  lea     rcx, [rbp+pvarg]; pvarg
0x180004edc  mov     [r14+570h], eax
0x180004ee3  call    cs:__imp_VariantClear
0x180004ee9  mov     rax, [rsi]
0x180004eec  lea     r8, [rbp+pvarg]
0x180004ef0  mov     edx, 2
0x180004ef5  mov     rcx, rsi
0x180004ef8  mov     rax, [rax+40h]
0x180004efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f01  mov     ebx, eax
0x180004f03  test    eax, eax
0x180004f05  jns     short loc_180004F47
0x180004f07  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f0e  lea     rax, WPP_GLOBAL_Control
0x180004f15  cmp     rcx, rax
0x180004f18  jz      loc_180004FFA
0x180004f1e  cmp     byte ptr [rcx+19h], 2
0x180004f22  jb      loc_180004FFA
0x180004f28  test    [rcx+1Ch], edi
0x180004f2b  jz      loc_180004FFA
0x180004f31  lea     rcx, aUnableToObtain_10; "Unable to obtain SDO Name Property duri"...
0x180004f38  call    WppDbgPrint
0x180004f3d  mov     edx, 0Eh
0x180004f42  jmp     loc_180004DA4
0x180004f47  cmp     word ptr [rbp+pvarg], 8
0x180004f4c  jnz     loc_180004D16
0x180004f52  mov     r8, qword ptr [rbp+pvarg+8]; unsigned __int16 *
0x180004f56  lea     r15, [r14+168h]
0x180004f5d  mov     rcx, r15; unsigned __int16 *
0x180004f60  mov     rdx, rdi; unsigned __int64
0x180004f63  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004f68  mov     ebx, eax
0x180004f6a  test    eax, eax
0x180004f6c  js      loc_180004FFA
0x180004f72  lea     rcx, [rbp+pvarg]; pvarg
0x180004f76  call    cs:__imp_VariantClear
0x180004f7c  mov     rax, [rsi]
0x180004f7f  lea     r8, [rbp+pvarg]
0x180004f83  mov     edx, 406h
0x180004f88  mov     rcx, rsi
0x180004f8b  mov     rax, [rax+40h]
0x180004f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f94  mov     ebx, eax
0x180004f96  test    eax, eax
0x180004f98  jns     short loc_180004FCE
0x180004f9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004fa1  lea     rax, WPP_GLOBAL_Control
0x180004fa8  cmp     rcx, rax
0x180004fab  jz      short loc_180004FFA
0x180004fad  cmp     byte ptr [rcx+19h], 2
0x180004fb1  jb      short loc_180004FFA
0x180004fb3  test    [rcx+1Ch], edi
0x180004fb6  jz      short loc_180004FFA
0x180004fb8  lea     rcx, aUnableToObtain_9; "Unable to obtain Client IsClientEnabled"...
0x180004fbf  call    WppDbgPrint
0x180004fc4  mov     edx, 0Fh
0x180004fc9  jmp     loc_180004DA4
0x180004fce  xor     eax, eax
0x180004fd0  lea     rcx, [rbp+pvarg]; pvarg
0x180004fd4  cmp     word ptr [rbp+pvarg+8], 0FFFFh
0x180004fd9  setz    al
0x180004fdc  mov     [r14+574h], eax
0x180004fe3  call    cs:__imp_VariantClear
0x180004fe9  xor     edx, edx
0x180004feb  mov     rcx, r15
0x180004fee  call    ?isConfigEnabled@RegistryUtil@@KA?AW4__MIDL___MIDL_itf_iasradius_0000_0000_0002@@PEAG_N@Z; RegistryUtil::isConfigEnabled(ushort *,bool)
0x180004ff3  mov     [r14+578h], eax
0x180004ffa  lea     rcx, [rbp+pvarg]; pvarg
0x180004ffe  call    cs:__imp_VariantClear
0x180005004  mov     eax, ebx
0x180005006  add     rsp, 68h
0x18000500a  pop     r15
0x18000500c  pop     r14
0x18000500e  pop     rdi
0x18000500f  pop     rsi
0x180005010  pop     rbx
0x180005011  pop     rbp
0x180005012  retn
```
