# LpCreateProfileSchemaCollection

- ea: `0x180032778`
- end: `0x1800328f0`
- name: `LpCreateProfileSchemaCollection`
- size: `376`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cbc0`
- `0x1800328f8`

## callees

- `0x1800025f0`
- `0x180003114`
- `0x180008bac`
- `0x18000a9c0`
- `0x18000c230`
- `0x1800326fc`
- `0x180032778`
- `0x18003b034`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032811`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180032803`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180032803`
- `OLEAUT32!__imp_VariantInit` at `0x1800327ad`
- `OLEAUT32!__imp_VariantInit` at `0x1800327ad`
- `OLEAUT32!__imp_VariantClear` at `0x1800328a7`
- `OLEAUT32!__imp_VariantClear` at `0x1800328a7`

## pseudocode

```c
__int64 __fastcall LpCreateProfileSchemaCollection(struct IXMLDOMSchemaCollection **a1)
{
  UINT SystemWindowsDirectoryW; // eax
  unsigned int LastError; // ebx
  int v4; // eax
  __int64 v5; // rdx
  const struct _XC_SCHEMA_LOCATION *v6; // rcx
  struct IXMLDOMSchemaCollection *v8; // [rsp+20h] [rbp-248h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-240h] BYREF
  size_t Buffer[66]; // [rsp+40h] [rbp-228h] BYREF

  v8 = 0;
  VariantInit(&pvarg);
  memset_0(Buffer, 0, 0x208u);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 46, WPP_25f5f272669b3cc70b9a4d690e9b67ad_Traceguids);
  }
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW((LPWSTR)Buffer, 0x104u);
  if ( SystemWindowsDirectoryW )
  {
    if ( SystemWindowsDirectoryW > 0x104 )
    {
      LastError = 122;
      goto LABEL_13;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_13;
  }
  v4 = StringCchCatW((unsigned __int16 *)Buffer, 0x104u, L"\\L2Schemas\\");
  LastError = v4;
  if ( v4 >= 0 )
    goto LABEL_11;
  if ( (v4 & 0x1FFF0000) == 0x70000 )
    LastError = (unsigned __int16)v4;
  if ( !LastError )
  {
LABEL_11:
    LastError = XcCreateSchemaCollection(v6, v5, Buffer, (LPVOID *)&v8);
    if ( !LastError )
    {
      *a1 = v8;
      v8 = 0;
    }
  }
LABEL_13:
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 47, WPP_25f5f272669b3cc70b9a4d690e9b67ad_Traceguids, LastError);
  }
  VariantClear(&pvarg);
  ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>((__int64 *)&v8);
  return LastError;
}

```

## disassembly

```asm
0x180032778  mov     [rsp+arg_8], rbx
0x18003277d  mov     [rsp+arg_10], rbp
0x180032782  push    rdi
0x180032783  sub     rsp, 260h
0x18003278a  mov     rax, cs:__security_cookie
0x180032791  xor     rax, rsp
0x180032794  mov     [rsp+268h+var_18], rax
0x18003279c  mov     rdi, rcx
0x18003279f  mov     [rsp+268h+var_248], 0
0x1800327a8  lea     rcx, [rsp+268h+pvarg]; pvarg
0x1800327ad  call    cs:__imp_VariantInit
0x1800327b3  xor     edx, edx; Val
0x1800327b5  lea     rcx, [rsp+268h+Buffer]; void *
0x1800327ba  mov     r8d, 208h; Size
0x1800327c0  call    memset_0
0x1800327c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800327cc  lea     rbp, WPP_GLOBAL_Control
0x1800327d3  cmp     rcx, rbp
0x1800327d6  jz      short loc_1800327F9
0x1800327d8  cmp     byte ptr [rcx+19h], 4
0x1800327dc  jb      short loc_1800327F9
0x1800327de  test    byte ptr [rcx+1Ch], 1
0x1800327e2  jz      short loc_1800327F9
0x1800327e4  mov     rcx, [rcx+10h]
0x1800327e8  lea     r8, WPP_25f5f272669b3cc70b9a4d690e9b67ad_Traceguids
0x1800327ef  mov     edx, 2Eh ; '.'
0x1800327f4  call    WPP_SF_
0x1800327f9  mov     edx, 104h; uSize
0x1800327fe  lea     rcx, [rsp+268h+Buffer]; lpBuffer
0x180032803  call    cs:__imp_GetSystemWindowsDirectoryW
0x180032809  test    eax, eax
0x18003280b  jnz     loc_1800328DE
0x180032811  call    cs:__imp_GetLastError
0x180032817  mov     ebx, eax
0x180032819  test    eax, eax
0x18003281b  jnz     short loc_180032872
0x18003281d  lea     r8, aL2schemas; "\\L2Schemas\\"
0x180032824  mov     edx, 104h; unsigned __int64
0x180032829  lea     rcx, [rsp+268h+Buffer]; unsigned __int16 *
0x18003282e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180032833  mov     ebx, eax
0x180032835  test    eax, eax
0x180032837  jns     short loc_18003284C
0x180032839  and     eax, 1FFF0000h
0x18003283e  cmp     eax, 70000h
0x180032843  jnz     short loc_180032848
0x180032845  movzx   ebx, bx
0x180032848  test    ebx, ebx
0x18003284a  jnz     short loc_180032872
0x18003284c  lea     r9, [rsp+268h+var_248]; struct IXMLDOMSchemaCollection **
0x180032851  lea     r8, [rsp+268h+Buffer]; unsigned __int16 *
0x180032856  call    ?XcCreateSchemaCollection@@YAKPEBU_XC_SCHEMA_LOCATION@@KPEBGPEAPEAUIXMLDOMSchemaCollection@@@Z; XcCreateSchemaCollection(_XC_SCHEMA_LOCATION const *,ulong,ushort const *,IXMLDOMSchemaCollection * *)
0x18003285b  mov     ebx, eax
0x18003285d  test    eax, eax
0x18003285f  jnz     short loc_180032872
0x180032861  mov     rax, [rsp+268h+var_248]
0x180032866  mov     [rdi], rax
0x180032869  mov     [rsp+268h+var_248], 0
0x180032872  mov     rcx, cs:WPP_GLOBAL_Control
0x180032879  cmp     rcx, rbp
0x18003287c  jz      short loc_1800328A2
0x18003287e  cmp     byte ptr [rcx+19h], 4
0x180032882  jb      short loc_1800328A2
0x180032884  test    byte ptr [rcx+1Ch], 1
0x180032888  jz      short loc_1800328A2
0x18003288a  mov     rcx, [rcx+10h]
0x18003288e  lea     r8, WPP_25f5f272669b3cc70b9a4d690e9b67ad_Traceguids
0x180032895  mov     edx, 2Fh ; '/'
0x18003289a  mov     r9d, ebx
0x18003289d  call    WPP_SF_d
0x1800328a2  lea     rcx, [rsp+268h+pvarg]; pvarg
0x1800328a7  call    cs:__imp_VariantClear
0x1800328ad  lea     rcx, [rsp+268h+var_248]
0x1800328b2  call    ??1?$CComPtrBase@UIXMLDOMParseError@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>(void)
0x1800328b7  mov     eax, ebx
0x1800328b9  mov     rcx, [rsp+268h+var_18]
0x1800328c1  xor     rcx, rsp; StackCookie
0x1800328c4  call    __security_check_cookie
0x1800328c9  lea     r11, [rsp+268h+var_8]
0x1800328d1  mov     rbx, [r11+18h]
0x1800328d5  mov     rbp, [r11+20h]
0x1800328d9  mov     rsp, r11
0x1800328dc  pop     rdi
0x1800328dd  retn
0x1800328de  cmp     eax, 104h
0x1800328e3  jbe     loc_18003281D
0x1800328e9  mov     ebx, 7Ah ; 'z'
0x1800328ee  jmp     short loc_180032872
```
