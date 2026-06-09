# NdfCreatePnrpIncident

- ea: `0x18000adc0`
- end: `0x18000af9b`
- name: `NdfCreatePnrpIncident`
- size: `475`
- prototype: `HRESULT __stdcall(LPCWSTR cloudname, LPCWSTR peername, BOOL diagnosePublish, LPCWSTR appId, NDFHANDLE *handle)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000721c`
- `0x1800098b0`
- `0x18000a9e0`
- `0x18000adc0`
- `0x18001f652`
- `0x18001f690`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000af74`
- `KERNEL32!GetLastError` at `0x18000af74`
- `KERNEL32!GetModuleFileNameW` at `0x18000af07`
- `KERNEL32!GetModuleFileNameW` at `0x18000af07`
- `wdi!WdiCancel` at `0x18000ae36`
- `wdi!WdiCancel` at `0x18000ae36`

## string_xrefs

- `0x18000ae19`: `NdfCreatePnrpIncident`

## pseudocode

```c
HRESULT __stdcall NdfCreatePnrpIncident(
        LPCWSTR cloudname,
        LPCWSTR peername,
        BOOL diagnosePublish,
        LPCWSTR appId,
        NDFHANDLE *handle)
{
  HRESULT result; // eax
  LPCWSTR v10; // rax
  unsigned __int16 v11; // bx
  __int64 v12; // r8
  LPCWSTR i; // rax
  __int64 v14; // rax
  size_t v15[4]; // [rsp+20h] [rbp-E0h] BYREF
  HELPER_ATTRIBUTE attributes; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v17; // [rsp+D0h] [rbp-30h]
  int v18; // [rsp+D8h] [rbp-28h]
  BOOL v19; // [rsp+E0h] [rbp-20h]
  const wchar_t *v20; // [rsp+160h] [rbp+60h]
  int v21; // [rsp+168h] [rbp+68h]
  LPCWSTR v22; // [rsp+170h] [rbp+70h]
  WCHAR Filename[264]; // [rsp+280h] [rbp+180h] BYREF

  v15[3] = 15;
  v15[2] = 0;
  LOBYTE(v15[0]) = 0;
  std::string::assign(v15, "NdfCreatePnrpIncident", 0x15u);
  TelemeterAPICall(v15);
  if ( (unsigned int)WdiCancel(0) == -2147023611 )
    return -2147467260;
  if ( !handle )
    return -2146895611;
  v19 = diagnosePublish;
  attributes.type = AT_STRING;
  attributes.pwszName = L"cloudname";
  v10 = (LPCWSTR)&dword_1800269CC;
  v18 = 1;
  if ( cloudname )
    v10 = cloudname;
  v11 = 2;
  attributes.Int64 = (LONGLONG)v10;
  v17 = L"publishmode";
  if ( peername )
  {
    v21 = 10;
    v20 = L"peername";
    v11 = 3;
    v22 = peername;
  }
  memset_0(Filename, 0, 0x208u);
  v12 = 260;
  if ( appId )
  {
    for ( i = appId; *i; ++i )
    {
      if ( !--v12 )
        return -2147024809;
    }
  }
  else
  {
    if ( !GetModuleFileNameW(0, Filename, 0x104u) )
      return GetLastError();
    appId = Filename;
  }
  v14 = 144LL * v11;
  *(LPWSTR *)((char *)&attributes.pwszName + v14) = L"appid";
  *(ATTRIBUTE_TYPE *)((char *)&attributes.type + v14) = AT_STRING;
  *(_QWORD *)((char *)&attributes.Boolean + v14) = appId;
  result = NdfCreateIncident(L"PnrpHelperClass", (unsigned __int16)(v11 + 1), &attributes, handle);
  if ( result >= 0 )
  {
    if ( *handle )
      *((_DWORD *)*handle + 4) = 7;
  }
  return result;
}

```

## disassembly

```asm
0x18000adc0  push    rbp
0x18000adc2  push    rbx
0x18000adc3  push    rsi
0x18000adc4  push    rdi
0x18000adc5  push    r12
0x18000adc7  push    r14
0x18000adc9  push    r15
0x18000adcb  lea     rbp, [rsp-3A0h]
0x18000add3  sub     rsp, 4A0h
0x18000adda  mov     rax, cs:__security_cookie
0x18000ade1  xor     rax, rsp
0x18000ade4  mov     [rbp+3D0h+var_40], rax
0x18000adeb  mov     rsi, [rbp+3D0h+handle]
0x18000adf2  xor     r12d, r12d
0x18000adf5  mov     r15d, r8d
0x18000adf8  mov     [rsp+4D0h+var_498], 0Fh
0x18000ae01  mov     r14, rdx
0x18000ae04  mov     [rsp+4D0h+var_4A0], r12
0x18000ae09  mov     rbx, rcx
0x18000ae0c  mov     [rsp+4D0h+var_4B0], r12b
0x18000ae11  lea     r8d, [r12+15h]; Size
0x18000ae16  mov     rdi, r9
0x18000ae19  lea     rdx, aNdfcreatepnrpi_0; "NdfCreatePnrpIncident"
0x18000ae20  lea     rcx, [rsp+4D0h+var_4B0]; void *
0x18000ae25  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z; std::string::assign(char const *,unsigned __int64)
0x18000ae2a  lea     rcx, [rsp+4D0h+var_4B0]
0x18000ae2f  call    ?TelemeterAPICall@@YAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; TelemeterAPICall(std::string)
0x18000ae34  xor     ecx, ecx
0x18000ae36  call    cs:__imp_WdiCancel
0x18000ae3c  cmp     eax, 80070505h
0x18000ae41  jnz     short loc_18000AE4D
0x18000ae43  mov     eax, 80004004h
0x18000ae48  jmp     loc_18000AF7A
0x18000ae4d  test    rsi, rsi
0x18000ae50  jnz     short loc_18000AE5C
0x18000ae52  mov     eax, 8008F905h
0x18000ae57  jmp     loc_18000AF7A
0x18000ae5c  test    rbx, rbx
0x18000ae5f  mov     [rbp+3D0h+var_3F0], r15d
0x18000ae63  lea     rax, aCloudname; "cloudname"
0x18000ae6a  mov     [rsp+4D0h+attributes.type], 0Ah
0x18000ae72  mov     [rsp+4D0h+attributes.pwszName], rax
0x18000ae77  mov     r15d, 2
0x18000ae7d  lea     rax, dword_1800269CC
0x18000ae84  mov     [rbp+3D0h+var_3F8], 1
0x18000ae8b  cmovnz  rax, rbx
0x18000ae8f  movzx   ebx, r15w
0x18000ae93  mov     qword ptr [rsp+4D0h+attributes.10h], rax
0x18000ae98  lea     rax, aPublishmode; "publishmode"
0x18000ae9f  mov     [rbp+3D0h+var_400], rax
0x18000aea3  test    r14, r14
0x18000aea6  jz      short loc_18000AEC2
0x18000aea8  lea     rax, aPeername; "peername"
0x18000aeaf  mov     [rbp+3D0h+var_368], 0Ah
0x18000aeb6  mov     [rbp+3D0h+var_370], rax
0x18000aeba  lea     ebx, [r15+1]
0x18000aebe  mov     [rbp+3D0h+var_360], r14
0x18000aec2  xor     edx, edx; Val
0x18000aec4  lea     rcx, [rbp+3D0h+Filename]; void *
0x18000aecb  mov     r8d, 208h; Size
0x18000aed1  call    memset_0
0x18000aed6  mov     r8d, 104h; nSize
0x18000aedc  test    rdi, rdi
0x18000aedf  jz      short loc_18000AEFE
0x18000aee1  mov     rax, rdi
0x18000aee4  mov     edx, 1
0x18000aee9  cmp     [rax], r12w
0x18000aeed  jz      short loc_18000AF1D
0x18000aeef  add     rax, r15
0x18000aef2  sub     r8, rdx
0x18000aef5  jnz     short loc_18000AEE9
0x18000aef7  mov     eax, 80070057h
0x18000aefc  jmp     short loc_18000AF7A
0x18000aefe  lea     rdx, [rbp+3D0h+Filename]; lpFilename
0x18000af05  xor     ecx, ecx; hModule
0x18000af07  call    cs:__imp_GetModuleFileNameW
0x18000af0d  test    eax, eax
0x18000af0f  jz      short loc_18000AF74
0x18000af11  lea     rdi, [rbp+3D0h+Filename]
0x18000af18  mov     edx, 1
0x18000af1d  movzx   eax, bx
0x18000af20  lea     r8, [rsp+4D0h+attributes]; attributes
0x18000af25  movzx   eax, bx
0x18000af28  mov     ecx, 90h
0x18000af2d  imul    rax, rcx
0x18000af31  lea     rcx, aAppid; "appid"
0x18000af38  add     bx, dx
0x18000af3b  movzx   edx, bx; celt
0x18000af3e  mov     r9, rsi; handle
0x18000af41  mov     [rsp+rax+4D0h+attributes.pwszName], rcx
0x18000af46  lea     rcx, aPnrphelperclas; "PnrpHelperClass"
0x18000af4d  mov     [rsp+rax+4D0h+attributes.type], 0Ah
0x18000af55  mov     qword ptr [rsp+rax+4D0h+attributes.10h], rdi
0x18000af5a  call    NdfCreateIncident
0x18000af5f  test    eax, eax
0x18000af61  js      short loc_18000AF7A
0x18000af63  mov     rcx, [rsi]
0x18000af66  test    rcx, rcx
0x18000af69  jz      short loc_18000AF7A
0x18000af6b  mov     dword ptr [rcx+10h], 7
0x18000af72  jmp     short loc_18000AF7A
0x18000af74  call    cs:__imp_GetLastError
0x18000af7a  mov     rcx, [rbp+3D0h+var_40]
0x18000af81  xor     rcx, rsp; StackCookie
0x18000af84  call    __security_check_cookie
0x18000af89  add     rsp, 4A0h
0x18000af90  pop     r15
0x18000af92  pop     r14
0x18000af94  pop     r12
0x18000af96  pop     rdi
0x18000af97  pop     rsi
0x18000af98  pop     rbx
0x18000af99  pop     rbp
0x18000af9a  retn
```
