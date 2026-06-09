# COMMAND_FILTERING_CONFIG_ELEMENT::Initialize(IAppHostElement *)

- ea: `0x1800445b0`
- end: `0x1800448f5`
- name: `?Initialize@COMMAND_FILTERING_CONFIG_ELEMENT@@UEAAJPEAUIAppHostElement@@@Z`
- size: `837`
- prototype: `int(COMMAND_FILTERING_CONFIG_ELEMENT *__hidden this, struct IAppHostElement *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18002afc4`
- `0x18002b0c4`
- `0x18002b5bc`
- `0x18002b65c`
- `0x1800445b0`
- `0x180049010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18004478b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800448d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18004478b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800448d1`
- `OLEAUT32!__imp_VariantInit` at `0x180044600`
- `OLEAUT32!__imp_VariantInit` at `0x180044600`
- `OLEAUT32!__imp_VariantClear` at `0x18004485e`
- `OLEAUT32!__imp_VariantClear` at `0x18004485e`
- `iisutil!PuDbgPrint` at `0x18004467d`
- `iisutil!PuDbgPrint` at `0x18004467d`
- `iisutil!PuDbgPrintError` at `0x180044854`
- `iisutil!PuDbgPrintError` at `0x180044854`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800447d7`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800447ed`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800447d7`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800447ed`

## string_xrefs

- `0x18004460d`: `security`
- `0x18004482b`: `Failed to read element %S\n`
- `0x180044671`: `inetsrv\iis\iisrearc\ftp\server\ftp_config\ftp_site_config.cxx`
- `0x180044843`: `inetsrv\iis\iisrearc\ftp\server\ftp_config\ftp_site_config.cxx`
- `0x180044619`: `commandFiltering`
- `0x18004466a`: `COMMAND_FILTERING_CONFIG_ELEMENT::Initialize`
- `0x180044837`: `COMMAND_FILTERING_CONFIG_ELEMENT::Initialize`
- `0x180044690`: `maxCommandLine`
- `0x18004479d`: `command`

## pseudocode

```c
__int64 __fastcall COMMAND_FILTERING_CONFIG_ELEMENT::Initialize(
        COMMAND_FILTERING_CONFIG_ELEMENT *this,
        struct IAppHostElement *a2)
{
  int SubElement; // ebx
  int v5; // eax
  int DWORDProperty; // eax
  unsigned int v7; // esi
  __int64 v8; // rax
  __int64 (__fastcall *v9)(__int64 *, __int128 *, struct IAppHostElement **); // rax
  struct IAppHostElement *v11; // [rsp+40h] [rbp-29h] BYREF
  struct IAppHostElement *v12; // [rsp+48h] [rbp-21h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-19h] BYREF
  __int64 *v14; // [rsp+58h] [rbp-11h] BYREF
  struct IAppHostElement *v15; // [rsp+60h] [rbp-9h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-1h] BYREF
  __int128 v17; // [rsp+80h] [rbp+17h] BYREF
  IRecordInfo *pRecInfo; // [rsp+90h] [rbp+27h]
  unsigned int v19; // [rsp+E0h] [rbp+77h] BYREF
  int v20; // [rsp+E8h] [rbp+7Fh] BYREF

  v12 = 0;
  v15 = 0;
  v14 = 0;
  v11 = 0;
  v19 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  bstrString = 0;
  VariantInit(&pvarg);
  SubElement = Config_GetSubElement(a2, L"security", &v15);
  if ( SubElement >= 0 )
  {
    v5 = Config_GetSubElement(v15, L"commandFiltering", &v12);
    SubElement = v5;
    if ( v5 >= 0 )
    {
      DWORDProperty = Config_GetDWORDProperty(v12, L"maxCommandLine", (unsigned int *)this + 31);
      SubElement = DWORDProperty;
      if ( DWORDProperty >= 0 )
      {
        SubElement = Config_GetBoolProperty(v12, L"allowUnlisted", (int *)this + 30);
        if ( SubElement >= 0 )
        {
          SubElement = ((__int64 (__fastcall *)(struct IAppHostElement *, __int64 **))v12->lpVtbl->get_Collection)(
                         v12,
                         &v14);
          if ( SubElement >= 0 )
          {
            SubElement = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v14 + 24))(v14, &v19);
            if ( SubElement >= 0 )
            {
              v7 = 0;
              if ( !v19 )
                goto LABEL_28;
              while ( 1 )
              {
                pvarg.lVal = v7;
                pvarg.vt = 19;
                v8 = *v14;
                v20 = 1;
                pRecInfo = pvarg.pRecInfo;
                v9 = *(__int64 (__fastcall **)(__int64 *, __int128 *, struct IAppHostElement **))(v8 + 32);
                v17 = *(_OWORD *)&pvarg.vt;
                SubElement = v9(v14, &v17, &v11);
                if ( SubElement < 0 )
                  break;
                if ( bstrString )
                {
                  SysFreeString(bstrString);
                  bstrString = 0;
                }
                SubElement = Config_GetStringProperty(v11, L"command", &bstrString);
                if ( SubElement < 0 )
                  break;
                SubElement = Config_GetBoolProperty(v11, L"allowed", &v20);
                if ( SubElement < 0 )
                  break;
                if ( v20 )
                {
                  if ( !MULTISZ::Append((COMMAND_FILTERING_CONFIG_ELEMENT *)((char *)this + 8), bstrString) )
                    SubElement = -2147024888;
                  if ( SubElement < 0 )
                    break;
                }
                else if ( !MULTISZ::Append((COMMAND_FILTERING_CONFIG_ELEMENT *)((char *)this + 64), bstrString) )
                {
                  SubElement = -2147024888;
                  break;
                }
                ((void (__fastcall *)(struct IAppHostElement *))v11->lpVtbl->Release)(v11);
                ++v7;
                v11 = 0;
                if ( v7 >= v19 )
                  goto LABEL_28;
              }
            }
          }
        }
      }
      else if ( (g_dwDebugFlags & 3) != 0 )
      {
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_config\\ftp_site_config.cxx",
          1882,
          "COMMAND_FILTERING_CONFIG_ELEMENT::Initialize",
          "GetBooleanProperty failed on %S - 0x%08x\r\n",
          L"allowUnlisted",
          DWORDProperty);
      }
    }
    else if ( (g_dwDebugFlags & 3) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_config\\ftp_site_config.cxx",
        1869,
        "COMMAND_FILTERING_CONFIG_ELEMENT::Initialize",
        "GetElement failed on %S - 0x%08x\r\n",
        L"commandFiltering",
        v5);
    }
  }
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_config\\ftp_site_config.cxx",
      1978,
      "COMMAND_FILTERING_CONFIG_ELEMENT::Initialize",
      SubElement,
      "Failed to read element %S\n",
      L"commandFiltering");
LABEL_28:
  VariantClear(&pvarg);
  if ( v11 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v11->lpVtbl->Release)(v11);
    v11 = 0;
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
    v14 = 0;
  }
  if ( v12 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v12->lpVtbl->Release)(v12);
    v12 = 0;
  }
  if ( v15 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v15->lpVtbl->Release)(v15);
    v15 = 0;
  }
  if ( bstrString )
    SysFreeString(bstrString);
  return (unsigned int)SubElement;
}

```

## disassembly

```asm
0x1800445b0  mov     [rsp-8+arg_0], rbx
0x1800445b5  mov     [rsp-8+arg_8], rsi
0x1800445ba  push    rbp
0x1800445bb  push    rdi
0x1800445bc  push    r12
0x1800445be  push    r14
0x1800445c0  push    r15
0x1800445c2  lea     rbp, [rsp-37h]
0x1800445c7  sub     rsp, 0A0h
0x1800445ce  xor     r14d, r14d
0x1800445d1  mov     rdi, rcx
0x1800445d4  xorps   xmm0, xmm0
0x1800445d7  mov     [rbp+57h+var_78], r14
0x1800445db  xor     eax, eax
0x1800445dd  mov     [rbp+57h+var_60], r14
0x1800445e1  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800445e5  mov     [rbp+57h+var_68], r14
0x1800445e9  mov     [rbp+57h+var_80], r14
0x1800445ed  mov     rbx, rdx
0x1800445f0  mov     [rbp+57h+arg_10], r14d
0x1800445f4  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800445f8  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800445fc  mov     [rbp+57h+bstrString], r14
0x180044600  call    cs:__imp_VariantInit
0x180044606  lea     r8, [rbp+57h+var_60]; struct IAppHostElement **
0x18004460a  mov     rcx, rbx; struct IAppHostElement *
0x18004460d  lea     rdx, aSecurity; "security"
0x180044614  call    ?Config_GetSubElement@@YAJPEAUIAppHostElement@@PEBGPEAPEAU1@@Z; Config_GetSubElement(IAppHostElement *,ushort const *,IAppHostElement * *)
0x180044619  lea     r12, aCommandfilteri; "commandFiltering"
0x180044620  mov     ebx, eax
0x180044622  test    eax, eax
0x180044624  js      loc_18004481B
0x18004462a  mov     rcx, [rbp+57h+var_60]; struct IAppHostElement *
0x18004462e  lea     r8, [rbp+57h+var_78]; struct IAppHostElement **
0x180044632  mov     rdx, r12; unsigned __int16 *
0x180044635  call    ?Config_GetSubElement@@YAJPEAUIAppHostElement@@PEBGPEAPEAU1@@Z; Config_GetSubElement(IAppHostElement *,ushort const *,IAppHostElement * *)
0x18004463a  mov     ebx, eax
0x18004463c  test    eax, eax
0x18004463e  jns     short loc_180044688
0x180044640  test    byte ptr cs:g_dwDebugFlags, 3
0x180044647  jz      loc_18004481B
0x18004464d  mov     dword ptr [rsp+0C0h+var_90], eax
0x180044651  mov     r8d, 74Dh
0x180044657  mov     [rsp+0C0h+var_98], r12
0x18004465c  lea     rax, aGetelementFail; "GetElement failed on %S - 0x%08x\r\n"
0x180044663  mov     rcx, cs:g_pDebug
0x18004466a  lea     r9, aCommandFilteri_0; "COMMAND_FILTERING_CONFIG_ELEMENT::Initi"...
0x180044671  lea     rdx, aInetsrvIisIisr_28; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x180044678  mov     [rsp+0C0h+var_A0], rax
0x18004467d  call    cs:__imp_PuDbgPrint
0x180044683  jmp     loc_18004481B
0x180044688  mov     rcx, [rbp+57h+var_78]; struct IAppHostElement *
0x18004468c  lea     r8, [rdi+7Ch]; unsigned int *
0x180044690  lea     rdx, aMaxcommandline; "maxCommandLine"
0x180044697  call    ?Config_GetDWORDProperty@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; Config_GetDWORDProperty(IAppHostElement *,ushort const *,ulong *)
0x18004469c  mov     ebx, eax
0x18004469e  test    eax, eax
0x1800446a0  jns     short loc_1800446CE
0x1800446a2  test    byte ptr cs:g_dwDebugFlags, 3
0x1800446a9  jz      loc_18004481B
0x1800446af  mov     dword ptr [rsp+0C0h+var_90], eax
0x1800446b3  lea     rdx, aAllowunlisted; "allowUnlisted"
0x1800446ba  mov     [rsp+0C0h+var_98], rdx
0x1800446bf  lea     rax, aGetbooleanprop_0; "GetBooleanProperty failed on %S - 0x%08"...
0x1800446c6  mov     r8d, 75Ah
0x1800446cc  jmp     short loc_180044663
0x1800446ce  mov     rcx, [rbp+57h+var_78]; struct IAppHostElement *
0x1800446d2  lea     r8, [rdi+78h]; int *
0x1800446d6  lea     rdx, aAllowunlisted; "allowUnlisted"
0x1800446dd  call    ?Config_GetBoolProperty@@YAJPEAUIAppHostElement@@PEBGPEAH@Z; Config_GetBoolProperty(IAppHostElement *,ushort const *,int *)
0x1800446e2  mov     ebx, eax
0x1800446e4  test    eax, eax
0x1800446e6  js      loc_18004481B
0x1800446ec  mov     rcx, [rbp+57h+var_78]
0x1800446f0  lea     rdx, [rbp+57h+var_68]
0x1800446f4  mov     rax, [rcx]
0x1800446f7  mov     rax, [rax+20h]
0x1800446fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044700  mov     ebx, eax
0x180044702  test    eax, eax
0x180044704  js      loc_18004481B
0x18004470a  mov     rcx, [rbp+57h+var_68]
0x18004470e  lea     rdx, [rbp+57h+arg_10]
0x180044712  mov     rax, [rcx]
0x180044715  mov     rax, [rax+18h]
0x180044719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004471e  mov     ebx, eax
0x180044720  test    eax, eax
0x180044722  js      loc_18004481B
0x180044728  mov     esi, r14d
0x18004472b  cmp     [rbp+57h+arg_10], r14d
0x18004472f  jbe     loc_18004485A
0x180044735  mov     r15d, 80070008h
0x18004473b  mov     rcx, [rbp+57h+var_68]
0x18004473f  lea     r8, [rbp+57h+var_80]
0x180044743  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180044748  lea     rdx, [rbp+57h+var_40]
0x18004474c  mov     dword ptr [rbp+57h+pvarg+8], esi
0x18004474f  mov     eax, 13h
0x180044754  mov     word ptr [rbp+57h+pvarg], ax
0x180044758  mov     rax, [rcx]
0x18004475b  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18004475f  mov     [rbp+57h+arg_18], 1
0x180044766  movsd   [rbp+57h+var_30], xmm1
0x18004476b  mov     rax, [rax+20h]
0x18004476f  movaps  [rbp+57h+var_40], xmm0
0x180044773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044778  mov     ebx, eax
0x18004477a  test    eax, eax
0x18004477c  js      loc_18004481B
0x180044782  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180044786  test    rcx, rcx
0x180044789  jz      short loc_180044795
0x18004478b  call    cs:__imp_SysFreeString
0x180044791  mov     [rbp+57h+bstrString], r14
0x180044795  mov     rcx, [rbp+57h+var_80]; struct IAppHostElement *
0x180044799  lea     r8, [rbp+57h+bstrString]; unsigned __int16 **
0x18004479d  lea     rdx, aCommand; "command"
0x1800447a4  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x1800447a9  mov     ebx, eax
0x1800447ab  test    eax, eax
0x1800447ad  js      short loc_18004481B
0x1800447af  mov     rcx, [rbp+57h+var_80]; struct IAppHostElement *
0x1800447b3  lea     r8, [rbp+57h+arg_18]; int *
0x1800447b7  lea     rdx, aAllowed; "allowed"
0x1800447be  call    ?Config_GetBoolProperty@@YAJPEAUIAppHostElement@@PEBGPEAH@Z; Config_GetBoolProperty(IAppHostElement *,ushort const *,int *)
0x1800447c3  mov     ebx, eax
0x1800447c5  test    eax, eax
0x1800447c7  js      short loc_18004481B
0x1800447c9  mov     rdx, [rbp+57h+bstrString]
0x1800447cd  cmp     [rbp+57h+arg_18], r14d
0x1800447d1  jz      short loc_1800447E9
0x1800447d3  lea     rcx, [rdi+8]
0x1800447d7  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x1800447dd  test    eax, eax
0x1800447df  cmovz   ebx, r15d
0x1800447e3  test    ebx, ebx
0x1800447e5  js      short loc_18004481B
0x1800447e7  jmp     short loc_1800447F7
0x1800447e9  lea     rcx, [rdi+40h]
0x1800447ed  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x1800447f3  test    eax, eax
0x1800447f5  jz      short loc_180044818
0x1800447f7  mov     rcx, [rbp+57h+var_80]
0x1800447fb  mov     rax, [rcx]
0x1800447fe  mov     rax, [rax+10h]
0x180044802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044807  inc     esi
0x180044809  mov     [rbp+57h+var_80], r14
0x18004480d  cmp     esi, [rbp+57h+arg_10]
0x180044810  jb      loc_18004473B
0x180044816  jmp     short loc_18004485A
0x180044818  mov     ebx, r15d
0x18004481b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180044822  jz      short loc_18004485A
0x180044824  mov     rcx, cs:g_pDebug
0x18004482b  lea     rax, aFailedToReadEl; "Failed to read element %S\n"
0x180044832  mov     [rsp+0C0h+var_90], r12
0x180044837  lea     r9, aCommandFilteri_0; "COMMAND_FILTERING_CONFIG_ELEMENT::Initi"...
0x18004483e  mov     [rsp+0C0h+var_98], rax
0x180044843  lea     rdx, aInetsrvIisIisr_28; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x18004484a  mov     r8d, 7BAh
0x180044850  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x180044854  call    cs:__imp_PuDbgPrintError
0x18004485a  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18004485e  call    cs:__imp_VariantClear
0x180044864  mov     rcx, [rbp+57h+var_80]
0x180044868  test    rcx, rcx
0x18004486b  jz      short loc_18004487D
0x18004486d  mov     rax, [rcx]
0x180044870  mov     rax, [rax+10h]
0x180044874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044879  mov     [rbp+57h+var_80], r14
0x18004487d  mov     rcx, [rbp+57h+var_68]
0x180044881  test    rcx, rcx
0x180044884  jz      short loc_180044896
0x180044886  mov     rax, [rcx]
0x180044889  mov     rax, [rax+10h]
0x18004488d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044892  mov     [rbp+57h+var_68], r14
0x180044896  mov     rcx, [rbp+57h+var_78]
0x18004489a  test    rcx, rcx
0x18004489d  jz      short loc_1800448AF
0x18004489f  mov     rax, [rcx]
0x1800448a2  mov     rax, [rax+10h]
0x1800448a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448ab  mov     [rbp+57h+var_78], r14
0x1800448af  mov     rcx, [rbp+57h+var_60]
0x1800448b3  test    rcx, rcx
0x1800448b6  jz      short loc_1800448C8
0x1800448b8  mov     rax, [rcx]
0x1800448bb  mov     rax, [rax+10h]
0x1800448bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448c4  mov     [rbp+57h+var_60], r14
0x1800448c8  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800448cc  test    rcx, rcx
0x1800448cf  jz      short loc_1800448D7
0x1800448d1  call    cs:__imp_SysFreeString
0x1800448d7  lea     r11, [rsp+0C0h+var_20]
0x1800448df  mov     eax, ebx
0x1800448e1  mov     rbx, [r11+30h]
0x1800448e5  mov     rsi, [r11+38h]
0x1800448e9  mov     rsp, r11
0x1800448ec  pop     r15
0x1800448ee  pop     r14
0x1800448f0  pop     r12
0x1800448f2  pop     rdi
0x1800448f3  pop     rbp
0x1800448f4  retn
```
