# JsonHelper::GetJsonStringAsByteArray(uchar * *,ulong *)

- ea: `0x180090860`
- end: `0x180090a01`
- name: `?GetJsonStringAsByteArray@JsonHelper@@UEAAJPEAPEAEPEAK@Z`
- size: `417`
- prototype: `int(JsonHelper *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800711c8`
- `0x180071a60`
- `0x18008fcdc`
- `0x180090860`
- `0x180091270`
- `0x1800921a8`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800908f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800909d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800908f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800909d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009095e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009095e`

## string_xrefs

- `0x1800908da`: `spJsonObj.As(&spJsonValue)  failed!`
- `0x18009094d`: `spJsonValue->Stringify  failed!`

## pseudocode

```c
__int64 __fastcall JsonHelper::GetJsonStringAsByteArray(JsonHelper *this, unsigned __int8 **a2, unsigned int *a3)
{
  __int64 v5; // rdx
  int v6; // ebx
  __int64 v7; // r8
  int ActivityIdPrefix; // eax
  int v9; // edx
  const char *v10; // rcx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  __int64 v13; // rdx
  __int64 v14; // r8
  const unsigned __int16 *StringRawBuffer; // rax
  JsonHelper *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r8
  _QWORD v20[2]; // [rsp+30h] [rbp-10h] BYREF
  UINT32 length; // [rsp+60h] [rbp+20h] BYREF
  HSTRING string; // [rsp+78h] [rbp+38h] BYREF

  v20[0] = 0;
  string = 0;
  length = 0;
  v6 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(
         (char *)this + 56,
         v20);
  if ( v6 >= 0 )
  {
    v11 = v20[0];
    v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v20[0] + 56LL);
    WindowsDeleteString(string);
    string = 0;
    v6 = v12(v11, &string);
    if ( v6 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
      v6 = JsonHelper::WideCharToUTF8AsByteArray(v16, StringRawBuffer, length, a2, a3);
      if ( v6 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v17, v18);
        v9 = 29;
        v10 = "WideCharToUTF8AsByteArray  failed!";
        goto LABEL_16;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v13, v14);
      v9 = 28;
      v10 = "spJsonValue->Stringify  failed!";
      goto LABEL_16;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v5, v7);
    v9 = 27;
    v10 = "spJsonObj.As(&spJsonValue)  failed!";
LABEL_16:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      ActivityIdPrefix,
      (__int64)v10,
      v6);
  }
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(v20);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180090860  mov     [rsp-18h+arg_8], rbx
0x180090865  mov     [rsp-18h+arg_10], rsi
0x18009086a  push    rbp
0x18009086b  push    rdi
0x18009086c  push    r14
0x18009086e  mov     rbp, rsp
0x180090871  sub     rsp, 40h
0x180090875  mov     r14, rdx
0x180090878  mov     [rbp+var_10], 0
0x180090880  lea     rdx, [rbp+var_10]
0x180090884  mov     [rbp+string], 0
0x18009088c  add     rcx, 38h ; '8'
0x180090890  mov     [rbp+length], 0
0x180090897  mov     rsi, r8
0x18009089a  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x18009089f  mov     ebx, eax
0x1800908a1  test    eax, eax
0x1800908a3  jns     short loc_1800908E6
0x1800908a5  mov     rax, cs:WPP_GLOBAL_Control
0x1800908ac  lea     rcx, WPP_GLOBAL_Control
0x1800908b3  cmp     rax, rcx
0x1800908b6  jz      loc_1800909D1
0x1800908bc  test    byte ptr [rax+1Ch], 8
0x1800908c0  jz      loc_1800909D1
0x1800908c6  cmp     byte ptr [rax+19h], 2
0x1800908ca  jb      loc_1800909D1
0x1800908d0  call    RdpX_GetActivityIdPrefix
0x1800908d5  mov     edx, 1Bh
0x1800908da  lea     rcx, aSpjsonobjAsSpj; "spJsonObj.As(&spJsonValue)  failed!"
0x1800908e1  jmp     loc_1800909AE
0x1800908e6  mov     rdi, [rbp+var_10]
0x1800908ea  mov     rcx, [rbp+string]; string
0x1800908ee  mov     rax, [rdi]
0x1800908f1  mov     rbx, [rax+38h]
0x1800908f5  call    cs:__imp_WindowsDeleteString
0x1800908fb  lea     rdx, [rbp+string]
0x1800908ff  mov     [rbp+string], 0
0x180090907  mov     rcx, rdi
0x18009090a  mov     rax, rbx
0x18009090d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090912  mov     ebx, eax
0x180090914  test    eax, eax
0x180090916  jns     short loc_180090956
0x180090918  mov     rax, cs:WPP_GLOBAL_Control
0x18009091f  lea     rcx, WPP_GLOBAL_Control
0x180090926  cmp     rax, rcx
0x180090929  jz      loc_1800909D1
0x18009092f  test    byte ptr [rax+1Ch], 8
0x180090933  jz      loc_1800909D1
0x180090939  cmp     byte ptr [rax+19h], 2
0x18009093d  jb      loc_1800909D1
0x180090943  call    RdpX_GetActivityIdPrefix
0x180090948  mov     edx, 1Ch
0x18009094d  lea     rcx, aSpjsonvalueStr; "spJsonValue->Stringify  failed!"
0x180090954  jmp     short loc_1800909AE
0x180090956  mov     rcx, [rbp+string]; string
0x18009095a  lea     rdx, [rbp+length]; length
0x18009095e  call    cs:__imp_WindowsGetStringRawBuffer
0x180090964  mov     r8d, [rbp+length]; int
0x180090968  mov     r9, r14; unsigned __int8 **
0x18009096b  mov     rdx, rax; unsigned __int16 *
0x18009096e  mov     [rsp+40h+var_20], rsi; unsigned int *
0x180090973  call    ?WideCharToUTF8AsByteArray@JsonHelper@@AEAAJPEBGHPEAPEAEPEAK@Z; JsonHelper::WideCharToUTF8AsByteArray(ushort const *,int,uchar * *,ulong *)
0x180090978  mov     ebx, eax
0x18009097a  test    eax, eax
0x18009097c  jns     short loc_1800909D1
0x18009097e  mov     rax, cs:WPP_GLOBAL_Control
0x180090985  lea     rcx, WPP_GLOBAL_Control
0x18009098c  cmp     rax, rcx
0x18009098f  jz      short loc_1800909D1
0x180090991  test    byte ptr [rax+1Ch], 8
0x180090995  jz      short loc_1800909D1
0x180090997  cmp     byte ptr [rax+19h], 2
0x18009099b  jb      short loc_1800909D1
0x18009099d  call    RdpX_GetActivityIdPrefix
0x1800909a2  mov     edx, 1Dh
0x1800909a7  lea     rcx, aWidechartoutf8; "WideCharToUTF8AsByteArray  failed!"
0x1800909ae  mov     [rsp+40h+var_18], ebx
0x1800909b2  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x1800909b9  mov     [rsp+40h+var_20], rcx
0x1800909be  mov     r9d, eax
0x1800909c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800909c8  mov     rcx, [rcx+10h]
0x1800909cc  call    WPP_SF_DsD
0x1800909d1  mov     rcx, [rbp+string]; string
0x1800909d5  call    cs:__imp_WindowsDeleteString
0x1800909db  lea     rcx, [rbp+var_10]
0x1800909df  mov     [rbp+string], 0
0x1800909e7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1800909ec  mov     rsi, [rsp+40h+arg_10]
0x1800909f1  mov     eax, ebx
0x1800909f3  mov     rbx, [rsp+40h+arg_8]
0x1800909f8  add     rsp, 40h
0x1800909fc  pop     r14
0x1800909fe  pop     rdi
0x1800909ff  pop     rbp
0x180090a00  retn
```
