# MESSAGES_CONFIG_ELEMENT::Initialize(IAppHostElement *)

- ea: `0x180046180`
- end: `0x180046433`
- name: `?Initialize@MESSAGES_CONFIG_ELEMENT@@UEAAJPEAUIAppHostElement@@@Z`
- size: `691`
- prototype: `int(MESSAGES_CONFIG_ELEMENT *__hidden this, struct IAppHostElement *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18002afc4`
- `0x18002b5bc`
- `0x18002b65c`
- `0x180046180`
- `0x180049010`

## import_xrefs

- `msvcrt!strstr` at `0x180046398`
- `msvcrt!strstr` at `0x180046398`
- `OLEAUT32!__imp_SysFreeString` at `0x180046220`
- `OLEAUT32!__imp_SysFreeString` at `0x180046283`
- `OLEAUT32!__imp_SysFreeString` at `0x1800462cb`
- `OLEAUT32!__imp_SysFreeString` at `0x180046316`
- `OLEAUT32!__imp_SysFreeString` at `0x1800463b8`
- `OLEAUT32!__imp_SysFreeString` at `0x180046220`
- `OLEAUT32!__imp_SysFreeString` at `0x180046283`
- `OLEAUT32!__imp_SysFreeString` at `0x1800462cb`
- `OLEAUT32!__imp_SysFreeString` at `0x180046316`
- `OLEAUT32!__imp_SysFreeString` at `0x1800463b8`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x1800461f4`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180046257`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x1800461f4`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180046257`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18004620c`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18004626f`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800462b7`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180046302`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18004620c`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18004626f`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800462b7`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180046302`
- `iisutil!PuDbgPrintError` at `0x180046403`
- `iisutil!PuDbgPrintError` at `0x180046403`

## string_xrefs

- `0x180046391`: `%AvailableBytesInHomeDirectory%`
- `0x1800463da`: `Failed to read element %S\n`
- `0x1800463f2`: `inetsrv\iis\iisrearc\ftp\server\ftp_config\ftp_site_config.cxx`
- `0x1800463e6`: `MESSAGES_CONFIG_ELEMENT::Initialize`

## pseudocode

```c
__int64 __fastcall MESSAGES_CONFIG_ELEMENT::Initialize(MESSAGES_CONFIG_ELEMENT *this, struct IAppHostElement *a2)
{
  int SubElement; // ebx
  bool v4; // zf
  BSTR bstrString; // [rsp+70h] [rbp+30h] BYREF
  struct IAppHostElement *v7; // [rsp+78h] [rbp+38h] BYREF

  v7 = 0;
  bstrString = 0;
  SubElement = Config_GetSubElement(a2, L"messages", &v7);
  if ( SubElement >= 0 )
  {
    SubElement = Config_GetStringProperty(v7, L"exitMessage", &bstrString);
    if ( SubElement >= 0 )
    {
      SubElement = STRA::CopyWToUTF8Unescaped((MESSAGES_CONFIG_ELEMENT *)((char *)this + 232), bstrString);
      if ( SubElement >= 0 )
      {
        SubElement = STRA::CopyW((MESSAGES_CONFIG_ELEMENT *)((char *)this + 8), bstrString);
        if ( SubElement >= 0 )
        {
          SysFreeString(bstrString);
          bstrString = 0;
          SubElement = Config_GetStringProperty(v7, L"greetingMessage", &bstrString);
          if ( SubElement >= 0 )
          {
            SubElement = STRA::CopyWToUTF8Unescaped((MESSAGES_CONFIG_ELEMENT *)((char *)this + 288), bstrString);
            if ( SubElement >= 0 )
            {
              SubElement = STRA::CopyW((MESSAGES_CONFIG_ELEMENT *)((char *)this + 64), bstrString);
              if ( SubElement >= 0 )
              {
                SysFreeString(bstrString);
                bstrString = 0;
                SubElement = Config_GetStringProperty(v7, L"bannerMessage", &bstrString);
                if ( SubElement >= 0 )
                {
                  SubElement = STRA::CopyW((MESSAGES_CONFIG_ELEMENT *)((char *)this + 120), bstrString);
                  if ( SubElement >= 0 )
                  {
                    SysFreeString(bstrString);
                    bstrString = 0;
                    SubElement = Config_GetStringProperty(v7, L"maxClientsMessage", &bstrString);
                    if ( SubElement >= 0 )
                    {
                      SubElement = STRA::CopyW((MESSAGES_CONFIG_ELEMENT *)((char *)this + 176), bstrString);
                      if ( SubElement >= 0 )
                      {
                        SysFreeString(bstrString);
                        bstrString = 0;
                        SubElement = Config_GetBoolProperty(v7, L"suppressDefaultBanner", (int *)this + 86);
                        if ( SubElement >= 0 )
                        {
                          SubElement = Config_GetBoolProperty(v7, L"expandVariables", (int *)this + 87);
                          if ( SubElement >= 0 )
                          {
                            SubElement = Config_GetBoolProperty(v7, L"allowLocalDetailedErrors", (int *)this + 89);
                            if ( SubElement >= 0 )
                            {
                              v4 = *((_DWORD *)this + 87) == 0;
                              *((_DWORD *)this + 88) = 0;
                              if ( !v4 && strstr(*((const char **)this + 12), "%AvailableBytesInHomeDirectory%") )
                                *((_DWORD *)this + 88) = 1;
                              SubElement = 0;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( SubElement < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_config\\ftp_site_config.cxx",
      1340,
      "MESSAGES_CONFIG_ELEMENT::Initialize",
      SubElement,
      "Failed to read element %S\n",
      L"messages");
  if ( v7 )
    ((void (__fastcall *)(struct IAppHostElement *))v7->lpVtbl->Release)(v7);
  return (unsigned int)SubElement;
}

```

## disassembly

```asm
0x180046180  mov     [rsp-18h+arg_0], rbx
0x180046185  mov     [rsp-18h+arg_8], rsi
0x18004618a  push    rbp
0x18004618b  push    rdi
0x18004618c  push    r15
0x18004618e  mov     rbp, rsp
0x180046191  sub     rsp, 40h
0x180046195  mov     rax, rdx
0x180046198  mov     [rbp+arg_18], 0
0x1800461a0  mov     rdi, rcx
0x1800461a3  mov     [rbp+bstrString], 0
0x1800461ab  lea     r15, aMessages; "messages"
0x1800461b2  mov     rcx, rax; struct IAppHostElement *
0x1800461b5  mov     rdx, r15; unsigned __int16 *
0x1800461b8  lea     r8, [rbp+arg_18]; struct IAppHostElement **
0x1800461bc  call    ?Config_GetSubElement@@YAJPEAUIAppHostElement@@PEBGPEAPEAU1@@Z; Config_GetSubElement(IAppHostElement *,ushort const *,IAppHostElement * *)
0x1800461c1  mov     ebx, eax
0x1800461c3  test    eax, eax
0x1800461c5  js      loc_1800463AF
0x1800461cb  mov     rcx, [rbp+arg_18]; struct IAppHostElement *
0x1800461cf  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x1800461d3  lea     rdx, aExitmessage; "exitMessage"
0x1800461da  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x1800461df  mov     ebx, eax
0x1800461e1  test    eax, eax
0x1800461e3  js      loc_1800463AF
0x1800461e9  mov     rdx, [rbp+bstrString]
0x1800461ed  lea     rcx, [rdi+0E8h]
0x1800461f4  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z; STRA::CopyWToUTF8Unescaped(ushort const *)
0x1800461fa  mov     ebx, eax
0x1800461fc  test    eax, eax
0x1800461fe  js      loc_1800463AF
0x180046204  mov     rdx, [rbp+bstrString]
0x180046208  lea     rcx, [rdi+8]
0x18004620c  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x180046212  mov     ebx, eax
0x180046214  test    eax, eax
0x180046216  js      loc_1800463AF
0x18004621c  mov     rcx, [rbp+bstrString]; bstrString
0x180046220  call    cs:__imp_SysFreeString
0x180046226  mov     rcx, [rbp+arg_18]; struct IAppHostElement *
0x18004622a  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x18004622e  lea     rdx, aGreetingmessag; "greetingMessage"
0x180046235  mov     [rbp+bstrString], 0
0x18004623d  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x180046242  mov     ebx, eax
0x180046244  test    eax, eax
0x180046246  js      loc_1800463AF
0x18004624c  mov     rdx, [rbp+bstrString]
0x180046250  lea     rcx, [rdi+120h]
0x180046257  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z; STRA::CopyWToUTF8Unescaped(ushort const *)
0x18004625d  mov     ebx, eax
0x18004625f  test    eax, eax
0x180046261  js      loc_1800463AF
0x180046267  mov     rdx, [rbp+bstrString]
0x18004626b  lea     rcx, [rdi+40h]
0x18004626f  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x180046275  mov     ebx, eax
0x180046277  test    eax, eax
0x180046279  js      loc_1800463AF
0x18004627f  mov     rcx, [rbp+bstrString]; bstrString
0x180046283  call    cs:__imp_SysFreeString
0x180046289  mov     rcx, [rbp+arg_18]; struct IAppHostElement *
0x18004628d  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x180046291  lea     rdx, aBannermessage; "bannerMessage"
0x180046298  mov     [rbp+bstrString], 0
0x1800462a0  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x1800462a5  mov     ebx, eax
0x1800462a7  test    eax, eax
0x1800462a9  js      loc_1800463AF
0x1800462af  mov     rdx, [rbp+bstrString]
0x1800462b3  lea     rcx, [rdi+78h]
0x1800462b7  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x1800462bd  mov     ebx, eax
0x1800462bf  test    eax, eax
0x1800462c1  js      loc_1800463AF
0x1800462c7  mov     rcx, [rbp+bstrString]; bstrString
0x1800462cb  call    cs:__imp_SysFreeString
0x1800462d1  mov     rcx, [rbp+arg_18]; struct IAppHostElement *
0x1800462d5  lea     r8, [rbp+bstrString]; unsigned __int16 **
0x1800462d9  lea     rdx, aMaxclientsmess; "maxClientsMessage"
0x1800462e0  mov     [rbp+bstrString], 0
0x1800462e8  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x1800462ed  mov     ebx, eax
0x1800462ef  test    eax, eax
0x1800462f1  js      loc_1800463AF
0x1800462f7  mov     rdx, [rbp+bstrString]
0x1800462fb  lea     rcx, [rdi+0B0h]
0x180046302  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x180046308  mov     ebx, eax
0x18004630a  test    eax, eax
0x18004630c  js      loc_1800463AF
0x180046312  mov     rcx, [rbp+bstrString]; bstrString
0x180046316  call    cs:__imp_SysFreeString
0x18004631c  mov     rcx, [rbp+arg_18]; struct IAppHostElement *
0x180046320  lea     r8, [rdi+158h]; int *
0x180046327  lea     rdx, aSuppressdefaul; "suppressDefaultBanner"
0x18004632e  mov     [rbp+bstrString], 0
0x180046336  call    ?Config_GetBoolProperty@@YAJPEAUIAppHostElement@@PEBGPEAH@Z; Config_GetBoolProperty(IAppHostElement *,ushort const *,int *)
0x18004633b  mov     ebx, eax
0x18004633d  test    eax, eax
0x18004633f  js      short loc_1800463AF
0x180046341  mov     rcx, [rbp+arg_18]; struct IAppHostElement *
0x180046345  lea     rsi, [rdi+15Ch]
0x18004634c  mov     r8, rsi; int *
0x18004634f  lea     rdx, aExpandvariable; "expandVariables"
0x180046356  call    ?Config_GetBoolProperty@@YAJPEAUIAppHostElement@@PEBGPEAH@Z; Config_GetBoolProperty(IAppHostElement *,ushort const *,int *)
0x18004635b  mov     ebx, eax
0x18004635d  test    eax, eax
0x18004635f  js      short loc_1800463AF
0x180046361  mov     rcx, [rbp+arg_18]; struct IAppHostElement *
0x180046365  lea     r8, [rdi+164h]; int *
0x18004636c  lea     rdx, aAllowlocaldeta; "allowLocalDetailedErrors"
0x180046373  call    ?Config_GetBoolProperty@@YAJPEAUIAppHostElement@@PEBGPEAH@Z; Config_GetBoolProperty(IAppHostElement *,ushort const *,int *)
0x180046378  mov     ebx, eax
0x18004637a  test    eax, eax
0x18004637c  js      short loc_1800463AF
0x18004637e  cmp     dword ptr [rsi], 0
0x180046381  mov     dword ptr [rdi+160h], 0
0x18004638b  jz      short loc_1800463AD
0x18004638d  mov     rcx, [rdi+60h]; Str
0x180046391  lea     rdx, aAvailablebytes; "%AvailableBytesInHomeDirectory%"
0x180046398  call    cs:__imp_strstr
0x18004639e  test    rax, rax
0x1800463a1  jz      short loc_1800463AD
0x1800463a3  mov     dword ptr [rdi+160h], 1
0x1800463ad  xor     ebx, ebx
0x1800463af  mov     rcx, [rbp+bstrString]; bstrString
0x1800463b3  test    rcx, rcx
0x1800463b6  jz      short loc_1800463C6
0x1800463b8  call    cs:__imp_SysFreeString
0x1800463be  mov     [rbp+bstrString], 0
0x1800463c6  test    ebx, ebx
0x1800463c8  jns     short loc_180046409
0x1800463ca  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800463d1  jz      short loc_180046409
0x1800463d3  mov     rcx, cs:g_pDebug
0x1800463da  lea     rax, aFailedToReadEl; "Failed to read element %S\n"
0x1800463e1  mov     [rsp+40h+var_10], r15
0x1800463e6  lea     r9, aMessagesConfig; "MESSAGES_CONFIG_ELEMENT::Initialize"
0x1800463ed  mov     [rsp+40h+var_18], rax
0x1800463f2  lea     rdx, aInetsrvIisIisr_28; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x1800463f9  mov     r8d, 53Ch
0x1800463ff  mov     [rsp+40h+var_20], ebx
0x180046403  call    cs:__imp_PuDbgPrintError
0x180046409  mov     rcx, [rbp+arg_18]
0x18004640d  test    rcx, rcx
0x180046410  jz      short loc_18004641E
0x180046412  mov     rax, [rcx]
0x180046415  mov     rax, [rax+10h]
0x180046419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004641e  mov     rsi, [rsp+40h+arg_8]
0x180046423  mov     eax, ebx
0x180046425  mov     rbx, [rsp+40h+arg_0]
0x18004642a  add     rsp, 40h
0x18004642e  pop     r15
0x180046430  pop     rdi
0x180046431  pop     rbp
0x180046432  retn
```
