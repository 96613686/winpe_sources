# CUSTOM_ERROR_HANDLER::NotificationToString(ulong)

- ea: `0x180003acc`
- end: `0x180003c45`
- name: `?NotificationToString@CUSTOM_ERROR_HANDLER@@AEAAPEBGK@Z`
- size: `377`
- prototype: `const unsigned __int16 *__fastcall(CUSTOM_ERROR_HANDLER *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x180005988`

## callees

- `0x180003acc`

## import_xrefs

- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180003beb`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x180003beb`

## string_xrefs

- `0x180003b50`: `ResolveRequestCache`
- `0x180003c39`: `UpdateRequestCache`
- `0x180003c0c`: `ReadEntity`
- `0x180003c03`: `MapPath`

## pseudocode

```c
const unsigned __int16 *__fastcall CUSTOM_ERROR_HANDLER::NotificationToString(const char **this, unsigned int a2)
{
  unsigned int v2; // edx
  unsigned int v3; // edx
  unsigned int v4; // edx
  unsigned int v5; // edx
  unsigned int v6; // edx
  unsigned int v7; // edx
  unsigned int v8; // edx
  const unsigned __int16 *result; // rax
  bool v10; // sf
  unsigned int v11; // [rsp+48h] [rbp+10h] BYREF
  const unsigned __int16 *v12; // [rsp+50h] [rbp+18h] BYREF

  v12 = 0;
  v11 = 0;
  if ( a2 > 0x100 )
  {
    switch ( a2 )
    {
      case 0x200u:
        return L"UpdateRequestCache";
      case 0x400u:
        return L"LogRequest";
      case 0x800u:
        return L"EndRequest";
      case 0x10000000u:
        return L"CustomNotification";
      case 0x20000000u:
        return L"SendResponse";
      case 0x40000000u:
        return L"ReadEntity";
      case 0x80000000:
        return L"MapPath";
    }
  }
  else
  {
    if ( a2 == 256 )
      return L"ReleaseRequestState";
    v2 = a2 - 1;
    if ( !v2 )
      return L"BeginRequest";
    v3 = v2 - 1;
    if ( !v3 )
      return L"AuthenticateRequest";
    v4 = v3 - 2;
    if ( !v4 )
      return L"AuthorizeRequest";
    v5 = v4 - 4;
    if ( !v5 )
      return L"ResolveRequestCache";
    v6 = v5 - 8;
    if ( !v6 )
      return L"MapRequestHandler";
    v7 = v6 - 16;
    if ( !v7 )
      return L"AcquireRequestState";
    v8 = v7 - 32;
    if ( !v8 )
      return L"PreExecuteRequestHandler";
    if ( v8 == 64 )
      return L"ExecuteRequestHandler";
  }
  v10 = (int)LANG_STRING::GetString((LANG_STRING *)CUSTOM_ERROR_HANDLER::sm_pLangString, 0x2F93u, this[4], &v12, &v11) < 0;
  result = L"Unknown";
  if ( !v10 )
    return v12;
  return result;
}

```

## disassembly

```asm
0x180003acc  sub     rsp, 38h
0x180003ad0  mov     eax, 100h
0x180003ad5  mov     [rsp+38h+arg_10], 0
0x180003ade  mov     [rsp+38h+arg_8], 0
0x180003ae6  cmp     edx, eax
0x180003ae8  ja      loc_180003B8C
0x180003aee  jz      loc_180003B80
0x180003af4  sub     edx, 1
0x180003af7  jz      short loc_180003B74
0x180003af9  sub     edx, 1
0x180003afc  jz      short loc_180003B68
0x180003afe  sub     edx, 2
0x180003b01  jz      short loc_180003B5C
0x180003b03  sub     edx, 4
0x180003b06  jz      short loc_180003B50
0x180003b08  sub     edx, 8
0x180003b0b  jz      short loc_180003B44
0x180003b0d  sub     edx, 10h
0x180003b10  jz      short loc_180003B38
0x180003b12  sub     edx, 20h ; ' '
0x180003b15  jz      short loc_180003B2C
0x180003b17  cmp     edx, 40h ; '@'
0x180003b1a  jnz     loc_180003BCC
0x180003b20  lea     rax, aExecuterequest; "ExecuteRequestHandler"
0x180003b27  jmp     loc_180003C40
0x180003b2c  lea     rax, aPreexecuterequ; "PreExecuteRequestHandler"
0x180003b33  jmp     loc_180003C40
0x180003b38  lea     rax, aAcquirerequest; "AcquireRequestState"
0x180003b3f  jmp     loc_180003C40
0x180003b44  lea     rax, aMaprequesthand; "MapRequestHandler"
0x180003b4b  jmp     loc_180003C40
0x180003b50  lea     rax, aResolverequest; "ResolveRequestCache"
0x180003b57  jmp     loc_180003C40
0x180003b5c  lea     rax, aAuthorizereque; "AuthorizeRequest"
0x180003b63  jmp     loc_180003C40
0x180003b68  lea     rax, aAuthenticatere; "AuthenticateRequest"
0x180003b6f  jmp     loc_180003C40
0x180003b74  lea     rax, aBeginrequest; "BeginRequest"
0x180003b7b  jmp     loc_180003C40
0x180003b80  lea     rax, aReleaserequest; "ReleaseRequestState"
0x180003b87  jmp     loc_180003C40
0x180003b8c  cmp     edx, 200h
0x180003b92  jz      loc_180003C39
0x180003b98  cmp     edx, 400h
0x180003b9e  jz      loc_180003C30
0x180003ba4  cmp     edx, 800h
0x180003baa  jz      short loc_180003C27
0x180003bac  cmp     edx, 10000000h
0x180003bb2  jz      short loc_180003C1E
0x180003bb4  cmp     edx, 20000000h
0x180003bba  jz      short loc_180003C15
0x180003bbc  cmp     edx, 40000000h
0x180003bc2  jz      short loc_180003C0C
0x180003bc4  cmp     edx, 80000000h
0x180003bca  jz      short loc_180003C03
0x180003bcc  mov     r8, [rcx+20h]
0x180003bd0  lea     rax, [rsp+38h+arg_8]
0x180003bd5  mov     rcx, cs:?sm_pLangString@CUSTOM_ERROR_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * CUSTOM_ERROR_HANDLER::sm_pLangString
0x180003bdc  lea     r9, [rsp+38h+arg_10]
0x180003be1  mov     edx, 2F93h
0x180003be6  mov     [rsp+38h+var_18], rax
0x180003beb  call    cs:__imp_?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z; LANG_STRING::GetString(uint,char const *,ushort const * *,ulong *)
0x180003bf1  test    eax, eax
0x180003bf3  lea     rax, aUnknown; "Unknown"
0x180003bfa  js      short loc_180003C40
0x180003bfc  mov     rax, [rsp+38h+arg_10]
0x180003c01  jmp     short loc_180003C40
0x180003c03  lea     rax, aMappath; "MapPath"
0x180003c0a  jmp     short loc_180003C40
0x180003c0c  lea     rax, aReadentity; "ReadEntity"
0x180003c13  jmp     short loc_180003C40
0x180003c15  lea     rax, aSendresponse; "SendResponse"
0x180003c1c  jmp     short loc_180003C40
0x180003c1e  lea     rax, aCustomnotifica; "CustomNotification"
0x180003c25  jmp     short loc_180003C40
0x180003c27  lea     rax, aEndrequest; "EndRequest"
0x180003c2e  jmp     short loc_180003C40
0x180003c30  lea     rax, aLogrequest; "LogRequest"
0x180003c37  jmp     short loc_180003C40
0x180003c39  lea     rax, aUpdaterequestc; "UpdateRequestCache"
0x180003c40  add     rsp, 38h
0x180003c44  retn
```
