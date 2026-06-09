# CMachineEnroller::HandleBackCompatForBlueDesktop(IXMLDOMDocument2 *,ushort *,ushort const *,HKEY__ *,int *)

- ea: `0x18004f648`
- end: `0x18004f932`
- name: `?HandleBackCompatForBlueDesktop@CMachineEnroller@@CAJPEAUIXMLDOMDocument2@@PEAGPEBGPEAUHKEY__@@PEAH@Z`
- size: `746`
- prototype: `__int64 __usercall@<rax>(struct IXMLDOMDocument2 *@<rcx>, OLECHAR *@<rdx>, OLECHAR *psz@<r8>, HKEY@<r9>, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004ff88`

## callees

- `0x18000de50`
- `0x18004e488`
- `0x18004ef34`
- `0x18004f648`
- `0x18005138c`
- `0x180051760`
- `0x18005e2e0`
- `0x18005e638`
- `0x18005e740`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18004f789`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18004f789`
- `OLEAUT32!__imp_VariantInit` at `0x18004f77f`
- `OLEAUT32!__imp_VariantInit` at `0x18004f7c6`
- `OLEAUT32!__imp_VariantInit` at `0x18004f89b`
- `OLEAUT32!__imp_VariantInit` at `0x18004f77f`
- `OLEAUT32!__imp_VariantInit` at `0x18004f7c6`
- `OLEAUT32!__imp_VariantInit` at `0x18004f89b`
- `OLEAUT32!__imp_VariantClear` at `0x18004f7d0`
- `OLEAUT32!__imp_VariantClear` at `0x18004f8a5`
- `OLEAUT32!__imp_VariantClear` at `0x18004f7d0`
- `OLEAUT32!__imp_VariantClear` at `0x18004f8a5`
- `DMCmnUtils!OmaDmRegistrySetString` at `0x18004f8e4`
- `DMCmnUtils!OmaDmRegistrySetString` at `0x18004f8e4`

## string_xrefs

- `0x18004f8d8`: `SSPHyperLink`
- `0x18004f8bc`: `//characteristic[@type='APPLICATION']/parm[@name="SSPHyperlink"]/@value`
- `0x18004f68d`: `wap-provisioningdoc/characteristic[@type='Registry']/characteristic[@type='HKLM\System\ConfigurationManager']/parm[@name='DeviceName']/@value`
- `0x18004f744`: `wap-provisioningdoc/characteristic[@type='Registry']/characteristic[@type='HKLM\Security\MachineEnrollment']/parm[@name='RenewalPeriod']/@value`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CMachineEnroller::HandleBackCompatForBlueDesktop(
        struct IXMLDOMDocument2 *a1,
        OLECHAR *a2,
        OLECHAR *psz,
        HKEY a4,
        int *a5)
{
  OLECHAR *v9; // rbx
  int v10; // edi
  const unsigned __int16 *v11; // rdx
  unsigned __int16 *v12; // rbx
  VARIANTARG pvarg; // [rsp+30h] [rbp-61h] BYREF
  VARIANTARG v15; // [rsp+50h] [rbp-41h] BYREF
  unsigned __int16 *v16; // [rsp+70h] [rbp-21h] BYREF
  int v17; // [rsp+78h] [rbp-19h] BYREF
  __int64 v18; // [rsp+80h] [rbp-11h]
  char v19; // [rsp+88h] [rbp-9h]
  unsigned __int16 *v20; // [rsp+90h] [rbp-1h] BYREF
  unsigned __int16 *v21; // [rsp+98h] [rbp+7h] BYREF
  OLECHAR *v22[8]; // [rsp+A0h] [rbp+Fh] BYREF

  v22[0] = 0;
  v21 = 0;
  v20 = 0;
  if ( CMachineEnroller::ExtractNodeStringValue(
         a1,
         L"wap-provisioningdoc/characteristic[@type='Registry']/characteristic[@type='HKLM\\System\\ConfigurationManager']"
          "/parm[@name='DeviceName']/@value",
         v22,
         1) >= 0 )
  {
    v9 = v22[0];
    if ( v22[0] )
    {
      v17 = 0;
      v18 = 0;
      v19 = 0;
      v16 = 0;
      v10 = UrlEscapeWrapper(a2);
      if ( v10 < 0
        || (v10 = OmaDMConfigMgr::Init((OmaDMConfigMgr *)&v17, psz, a2), v10 < 0)
        || (v10 = OmaDMConfigMgr::Set((OmaDMConfigMgr *)&v17, v11, v16, L"EntDeviceName", v9), v10 < 0) )
      {
        CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v16);
        goto LABEL_5;
      }
      CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v16);
      OmaDMConfigMgr::~OmaDMConfigMgr((OmaDMConfigMgr *)&v17);
    }
  }
  if ( CMachineEnroller::ExtractNodeStringValue(
         a1,
         L"wap-provisioningdoc/characteristic[@type='Registry']/characteristic[@type='HKLM\\Security\\MachineEnrollment']/"
          "parm[@name='RenewalPeriod']/@value",
         &v21,
         1) >= 0 )
  {
    v12 = v21;
    if ( v21 )
    {
      v17 = 0;
      v18 = 0;
      v19 = 0;
      VariantInit(&pvarg);
      pvarg.lVal = _o__wtoi(v12);
      pvarg.vt = 3;
      v10 = OmaDMConfigMgr::Init((OmaDMConfigMgr *)&v17, psz, a2);
      if ( v10 < 0
        || (v15 = pvarg,
            v10 = OmaDMConfigMgr::Set(&v17, L"./Vendor/MSFT/CertificateStore/My/WSTEP/Renew/RenewPeriod", &v15, 0),
            v10 < 0)
        || (pvarg.lVal = 1,
            v15 = pvarg,
            v10 = OmaDMConfigMgr::Set(&v17, L"./Vendor/MSFT/CertificateStore/My/WSTEP/Renew/RetryInterval", &v15, 0),
            v10 < 0) )
      {
        v15 = pvarg;
      }
      else
      {
        pvarg.iVal = 1;
        pvarg.vt = 11;
        v15 = pvarg;
        v10 = OmaDMConfigMgr::Set(&v17, L"./Vendor/MSFT/CertificateStore/My/WSTEP/Renew/ROBOSupport", &v15, 5);
        v15 = pvarg;
        if ( v10 >= 0 )
        {
          VariantInit(&pvarg);
          VariantClear(&v15);
          OmaDMConfigMgr::~OmaDMConfigMgr((OmaDMConfigMgr *)&v17);
          goto LABEL_18;
        }
      }
      VariantInit(&pvarg);
      VariantClear(&v15);
LABEL_5:
      OmaDMConfigMgr::~OmaDMConfigMgr((OmaDMConfigMgr *)&v17);
      goto LABEL_22;
    }
  }
LABEL_18:
  if ( CMachineEnroller::ExtractNodeStringValue(
         a1,
         L"//characteristic[@type='APPLICATION']/parm[@name=\"SSPHyperlink\"]/@value",
         &v20,
         0) < 0
    || !v20
    || (v10 = OmaDmRegistrySetString(a4, 0, L"SSPHyperLink", v20), v10 >= 0) )
  {
    v10 = CMachineEnroller::SetDefaultInitialOmaDmSessionParams(a1, psz, a5);
  }
LABEL_22:
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v20);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v21);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)v22);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18004f648  push    rbp
0x18004f64a  push    rbx
0x18004f64b  push    rsi
0x18004f64c  push    rdi
0x18004f64d  push    r12
0x18004f64f  push    r14
0x18004f651  push    r15
0x18004f653  lea     rbp, [rsp-1Fh]
0x18004f658  sub     rsp, 0B0h
0x18004f65f  mov     r12, r9
0x18004f662  mov     r15, r8
0x18004f665  mov     r14, rdx
0x18004f668  mov     rsi, rcx
0x18004f66b  mov     [rbp+4Fh+var_40], 0
0x18004f673  mov     [rbp+4Fh+var_48], 0
0x18004f67b  mov     [rbp+4Fh+var_50], 0
0x18004f683  mov     r9d, 1; int
0x18004f689  lea     r8, [rbp+4Fh+var_40]; unsigned __int16 **
0x18004f68d  lea     rdx, aWapProvisionin; "wap-provisioningdoc/characteristic[@typ"...
0x18004f694  call    ?ExtractNodeStringValue@CMachineEnroller@@SAJPEAUIXMLDOMDocument2@@PEBGPEAPEAGH@Z; CMachineEnroller::ExtractNodeStringValue(IXMLDOMDocument2 *,ushort const *,ushort * *,int)
0x18004f699  test    eax, eax
0x18004f69b  js      loc_18004F73A
0x18004f6a1  mov     rbx, [rbp+4Fh+var_40]
0x18004f6a5  test    rbx, rbx
0x18004f6a8  jz      loc_18004F73A
0x18004f6ae  mov     [rbp+4Fh+var_68], 0
0x18004f6b5  mov     [rbp+4Fh+var_60], 0
0x18004f6bd  mov     [rbp+4Fh+var_58], 0
0x18004f6c1  mov     [rbp+4Fh+var_70], 0
0x18004f6c9  lea     rdx, [rbp+4Fh+var_70]
0x18004f6cd  mov     rcx, r14; pszUrl
0x18004f6d0  call    UrlEscapeWrapper
0x18004f6d5  mov     edi, eax
0x18004f6d7  test    eax, eax
0x18004f6d9  jns     short loc_18004F6F3
0x18004f6db  lea     rcx, [rbp+4Fh+var_70]
0x18004f6df  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18004f6e4  nop
0x18004f6e5  lea     rcx, [rbp+4Fh+var_68]; this
0x18004f6e9  call    ??1OmaDMConfigMgr@@QEAA@XZ; OmaDMConfigMgr::~OmaDMConfigMgr(void)
0x18004f6ee  jmp     loc_18004F901
0x18004f6f3  mov     r8, r14; OLECHAR *
0x18004f6f6  mov     rdx, r15; psz
0x18004f6f9  lea     rcx, [rbp+4Fh+var_68]; this
0x18004f6fd  call    ?Init@OmaDMConfigMgr@@QEAAJPEBG0@Z; OmaDMConfigMgr::Init(ushort const *,ushort const *)
0x18004f702  mov     edi, eax
0x18004f704  test    eax, eax
0x18004f706  js      short loc_18004F6DB
0x18004f708  mov     [rsp+0E0h+psz], rbx; psz
0x18004f70d  lea     r9, aEntdevicename; "EntDeviceName"
0x18004f714  mov     r8, [rbp+4Fh+var_70]; unsigned __int16 *
0x18004f718  lea     rcx, [rbp+4Fh+var_68]; this
0x18004f71c  call    ?Set@OmaDMConfigMgr@@QEAAJPEBG000@Z; OmaDMConfigMgr::Set(ushort const *,ushort const *,ushort const *,ushort const *)
0x18004f721  mov     edi, eax
0x18004f723  lea     rcx, [rbp+4Fh+var_70]
0x18004f727  test    eax, eax
0x18004f729  js      short loc_18004F6DF
0x18004f72b  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18004f730  nop
0x18004f731  lea     rcx, [rbp+4Fh+var_68]; this
0x18004f735  call    ??1OmaDMConfigMgr@@QEAA@XZ; OmaDMConfigMgr::~OmaDMConfigMgr(void)
0x18004f73a  mov     r9d, 1; int
0x18004f740  lea     r8, [rbp+4Fh+var_48]; unsigned __int16 **
0x18004f744  lea     rdx, aWapProvisionin_14; "wap-provisioningdoc/characteristic[@typ"...
0x18004f74b  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x18004f74e  call    ?ExtractNodeStringValue@CMachineEnroller@@SAJPEAUIXMLDOMDocument2@@PEBGPEAPEAGH@Z; CMachineEnroller::ExtractNodeStringValue(IXMLDOMDocument2 *,ushort const *,ushort * *,int)
0x18004f753  test    eax, eax
0x18004f755  js      loc_18004F8B5
0x18004f75b  mov     rbx, [rbp+4Fh+var_48]
0x18004f75f  test    rbx, rbx
0x18004f762  jz      loc_18004F8B5
0x18004f768  mov     [rbp+4Fh+var_68], 0
0x18004f76f  mov     [rbp+4Fh+var_60], 0
0x18004f777  mov     [rbp+4Fh+var_58], 0
0x18004f77b  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18004f77f  call    cs:__imp_VariantInit
0x18004f785  nop
0x18004f786  mov     rcx, rbx
0x18004f789  call    cs:__imp__o__wtoi
0x18004f78f  mov     dword ptr [rbp+4Fh+pvarg+8], eax
0x18004f792  mov     eax, 3
0x18004f797  mov     word ptr [rbp+4Fh+pvarg], ax
0x18004f79b  mov     r8, r14; OLECHAR *
0x18004f79e  mov     rdx, r15; psz
0x18004f7a1  lea     rcx, [rbp+4Fh+var_68]; this
0x18004f7a5  call    ?Init@OmaDMConfigMgr@@QEAAJPEBG0@Z; OmaDMConfigMgr::Init(ushort const *,ushort const *)
0x18004f7aa  mov     edi, eax
0x18004f7ac  test    eax, eax
0x18004f7ae  jns     short loc_18004F7DC
0x18004f7b0  movups  xmm0, xmmword ptr [rbp+4Fh+pvarg]
0x18004f7b4  movups  xmmword ptr [rbp+4Fh+var_90], xmm0
0x18004f7b8  movsd   xmm1, qword ptr [rbp+4Fh+pvarg+10h]
0x18004f7bd  movsd   qword ptr [rbp+4Fh+var_90+10h], xmm1
0x18004f7c2  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18004f7c6  call    cs:__imp_VariantInit
0x18004f7cc  lea     rcx, [rbp+4Fh+var_90]; pvarg
0x18004f7d0  call    cs:__imp_VariantClear
0x18004f7d6  nop
0x18004f7d7  jmp     loc_18004F6E5
0x18004f7dc  movups  xmm0, xmmword ptr [rbp+4Fh+pvarg]
0x18004f7e0  movaps  xmmword ptr [rbp+4Fh+var_90], xmm0
0x18004f7e4  movsd   xmm1, qword ptr [rbp+4Fh+pvarg+10h]
0x18004f7e9  movsd   qword ptr [rbp+4Fh+var_90+10h], xmm1
0x18004f7ee  xor     r9d, r9d
0x18004f7f1  lea     r8, [rbp+4Fh+var_90]
0x18004f7f5  lea     rdx, aVendorMsftCert_3; "./Vendor/MSFT/CertificateStore/My/WSTEP"...
0x18004f7fc  lea     rcx, [rbp+4Fh+var_68]
0x18004f800  call    ?Set@OmaDMConfigMgr@@QEAAJPEBGUtagVARIANT@@W4ConfigDataType@@@Z; OmaDMConfigMgr::Set(ushort const *,tagVARIANT,ConfigDataType)
0x18004f805  mov     edi, eax
0x18004f807  test    eax, eax
0x18004f809  js      short loc_18004F7B0
0x18004f80b  mov     ebx, 1
0x18004f810  mov     dword ptr [rbp+4Fh+pvarg+8], ebx
0x18004f813  movups  xmm0, xmmword ptr [rbp+4Fh+pvarg]
0x18004f817  movaps  xmmword ptr [rbp+4Fh+var_90], xmm0
0x18004f81b  movsd   xmm1, qword ptr [rbp+4Fh+pvarg+10h]
0x18004f820  movsd   qword ptr [rbp+4Fh+var_90+10h], xmm1
0x18004f825  xor     r9d, r9d
0x18004f828  lea     r8, [rbp+4Fh+var_90]
0x18004f82c  lea     rdx, aVendorMsftCert_1; "./Vendor/MSFT/CertificateStore/My/WSTEP"...
0x18004f833  lea     rcx, [rbp+4Fh+var_68]
0x18004f837  call    ?Set@OmaDMConfigMgr@@QEAAJPEBGUtagVARIANT@@W4ConfigDataType@@@Z; OmaDMConfigMgr::Set(ushort const *,tagVARIANT,ConfigDataType)
0x18004f83c  mov     edi, eax
0x18004f83e  test    eax, eax
0x18004f840  js      loc_18004F7B0
0x18004f846  mov     word ptr [rbp+4Fh+pvarg+8], bx
0x18004f84a  lea     eax, [rbx+0Ah]
0x18004f84d  mov     word ptr [rbp+4Fh+pvarg], ax
0x18004f851  movups  xmm0, xmmword ptr [rbp+4Fh+pvarg]
0x18004f855  movaps  xmmword ptr [rbp+4Fh+var_90], xmm0
0x18004f859  movsd   xmm1, qword ptr [rbp+4Fh+pvarg+10h]
0x18004f85e  movsd   qword ptr [rbp+4Fh+var_90+10h], xmm1
0x18004f863  lea     r9d, [rbx+4]
0x18004f867  lea     r8, [rbp+4Fh+var_90]
0x18004f86b  lea     rdx, aVendorMsftCert_0; "./Vendor/MSFT/CertificateStore/My/WSTEP"...
0x18004f872  lea     rcx, [rbp+4Fh+var_68]
0x18004f876  call    ?Set@OmaDMConfigMgr@@QEAAJPEBGUtagVARIANT@@W4ConfigDataType@@@Z; OmaDMConfigMgr::Set(ushort const *,tagVARIANT,ConfigDataType)
0x18004f87b  mov     edi, eax
0x18004f87d  movups  xmm0, xmmword ptr [rbp+4Fh+pvarg]
0x18004f881  movsd   xmm1, qword ptr [rbp+4Fh+pvarg+10h]
0x18004f886  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18004f88a  movups  xmmword ptr [rbp+4Fh+var_90], xmm0
0x18004f88e  movsd   qword ptr [rbp+4Fh+var_90+10h], xmm1
0x18004f893  test    eax, eax
0x18004f895  js      loc_18004F7C6
0x18004f89b  call    cs:__imp_VariantInit
0x18004f8a1  lea     rcx, [rbp+4Fh+var_90]; pvarg
0x18004f8a5  call    cs:__imp_VariantClear
0x18004f8ab  nop
0x18004f8ac  lea     rcx, [rbp+4Fh+var_68]; this
0x18004f8b0  call    ??1OmaDMConfigMgr@@QEAA@XZ; OmaDMConfigMgr::~OmaDMConfigMgr(void)
0x18004f8b5  xor     r9d, r9d; int
0x18004f8b8  lea     r8, [rbp+4Fh+var_50]; unsigned __int16 **
0x18004f8bc  lea     rdx, aCharacteristic_3; "//characteristic[@type='APPLICATION']/p"...
0x18004f8c3  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x18004f8c6  call    ?ExtractNodeStringValue@CMachineEnroller@@SAJPEAUIXMLDOMDocument2@@PEBGPEAPEAGH@Z; CMachineEnroller::ExtractNodeStringValue(IXMLDOMDocument2 *,ushort const *,ushort * *,int)
0x18004f8cb  test    eax, eax
0x18004f8cd  js      short loc_18004F8F0
0x18004f8cf  mov     r9, [rbp+4Fh+var_50]
0x18004f8d3  test    r9, r9
0x18004f8d6  jz      short loc_18004F8F0
0x18004f8d8  lea     r8, aSsphyperlink; "SSPHyperLink"
0x18004f8df  xor     edx, edx
0x18004f8e1  mov     rcx, r12
0x18004f8e4  call    cs:__imp_?OmaDmRegistrySetString@@YAJPEAUHKEY__@@PEBG11@Z; OmaDmRegistrySetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18004f8ea  mov     edi, eax
0x18004f8ec  test    eax, eax
0x18004f8ee  js      short loc_18004F901
0x18004f8f0  mov     r8, [rbp+4Fh+arg_20]; int *
0x18004f8f4  mov     rdx, r15; unsigned __int16 *
0x18004f8f7  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x18004f8fa  call    ?SetDefaultInitialOmaDmSessionParams@CMachineEnroller@@CAJPEAUIXMLDOMDocument2@@PEBGPEAH@Z; CMachineEnroller::SetDefaultInitialOmaDmSessionParams(IXMLDOMDocument2 *,ushort const *,int *)
0x18004f8ff  mov     edi, eax
0x18004f901  lea     rcx, [rbp+4Fh+var_50]
0x18004f905  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18004f90a  nop
0x18004f90b  lea     rcx, [rbp+4Fh+var_48]
0x18004f90f  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18004f914  nop
0x18004f915  lea     rcx, [rbp+4Fh+var_40]
0x18004f919  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18004f91e  mov     eax, edi
0x18004f920  add     rsp, 0B0h
0x18004f927  pop     r15
0x18004f929  pop     r14
0x18004f92b  pop     r12
0x18004f92d  pop     rdi
0x18004f92e  pop     rsi
0x18004f92f  pop     rbx
0x18004f930  pop     rbp
0x18004f931  retn
```
