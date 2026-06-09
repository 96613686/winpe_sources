# GetTemporaryFilePath

- ea: `0x18000a148`
- end: `0x18000a289`
- name: `GetTemporaryFilePath`
- size: `321`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000bc10`

## callees

- `0x180009cd4`
- `0x180009db8`
- `0x18000a148`
- `0x18000a518`
- `0x180018b30`
- `0x18002b530`
- `0x180035b88`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000a173`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000a173`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000a1aa`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000a1aa`

## pseudocode

```c
__int64 __fastcall GetTemporaryFilePath(unsigned __int16 *a1)
{
  HRESULT v2; // eax
  const char *v3; // r9
  int v4; // eax
  unsigned __int64 v5; // rdx
  int v6; // eax
  unsigned __int64 v7; // rdx
  __int64 result; // rax
  GUID pguid; // [rsp+20h] [rbp-288h] BYREF
  OLECHAR sz[40]; // [rsp+30h] [rbp-278h] BYREF
  WCHAR PathName[264]; // [rsp+80h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  pguid = 0;
  v2 = CoCreateGuid(&pguid);
  if ( v2 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x3EE,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)(unsigned int)v2,
      pguid.Data1);
  if ( StringFromGUID2(&pguid, sz, 39) != 39 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x3F5,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      v3);
  GetTemporaryDirectoryPath(PathName);
  v4 = StringCchCopyW(a1, 0x104u, PathName);
  if ( v4 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x3FD,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)(unsigned int)v4,
      pguid.Data1);
  v6 = StringCchCatW(a1, v5, sz);
  if ( v6 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x3FE,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)(unsigned int)v6,
      pguid.Data1);
  result = StringCchCatW(a1, v7, L".htm");
  if ( (int)result < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x3FF,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      (const char *)(unsigned int)result,
      pguid.Data1);
  return result;
}

```

## disassembly

```asm
0x18000a148  push    rbx
0x18000a14a  sub     rsp, 2A0h
0x18000a151  mov     rax, cs:__security_cookie
0x18000a158  xor     rax, rsp
0x18000a15b  mov     [rsp+2A8h+var_18], rax
0x18000a163  mov     rbx, rcx
0x18000a166  xorps   xmm0, xmm0
0x18000a169  lea     rcx, [rsp+2A8h+pguid]; pguid
0x18000a16e  movups  xmmword ptr [rsp+2A8h+pguid.Data1], xmm0; int
0x18000a173  call    cs:__imp_CoCreateGuid
0x18000a179  test    eax, eax
0x18000a17b  jns     short loc_18000A19A
0x18000a17d  mov     rcx, [rsp+2A8h]; this
0x18000a185  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18000a18c  mov     r9d, eax; char *
0x18000a18f  mov     edx, 3EEh; void *
0x18000a194  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000a19a  mov     r8d, 27h ; '''; cchMax
0x18000a1a0  lea     rdx, [rsp+2A8h+sz]; lpsz
0x18000a1a5  lea     rcx, [rsp+2A8h+pguid]; rguid
0x18000a1aa  call    cs:__imp_StringFromGUID2
0x18000a1b0  cmp     eax, 27h ; '''
0x18000a1b3  jz      short loc_18000A1CF
0x18000a1b5  mov     rcx, [rsp+2A8h]; this
0x18000a1bd  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18000a1c4  mov     edx, 3F5h; void *
0x18000a1c9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000a1cf  lea     rcx, [rsp+2A8h+PathName]; lpPathName
0x18000a1d7  call    GetTemporaryDirectoryPath
0x18000a1dc  lea     r8, [rsp+2A8h+PathName]; unsigned __int16 *
0x18000a1e4  mov     edx, 104h; unsigned __int64
0x18000a1e9  mov     rcx, rbx; unsigned __int16 *
0x18000a1ec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a1f1  test    eax, eax
0x18000a1f3  jns     short loc_18000A212
0x18000a1f5  mov     rcx, [rsp+2A8h]; this
0x18000a1fd  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18000a204  mov     r9d, eax; char *
0x18000a207  mov     edx, 3FDh; void *
0x18000a20c  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000a212  lea     r8, [rsp+2A8h+sz]; unsigned __int16 *
0x18000a217  mov     rcx, rbx; unsigned __int16 *
0x18000a21a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a21f  test    eax, eax
0x18000a221  jns     short loc_18000A240
0x18000a223  mov     rcx, [rsp+2A8h]; this
0x18000a22b  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18000a232  mov     r9d, eax; char *
0x18000a235  mov     edx, 3FEh; void *
0x18000a23a  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000a240  lea     r8, aHtm; ".htm"
0x18000a247  mov     rcx, rbx; unsigned __int16 *
0x18000a24a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a24f  test    eax, eax
0x18000a251  jns     short loc_18000A270
0x18000a253  mov     rcx, [rsp+2A8h]; this
0x18000a25b  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18000a262  mov     r9d, eax; char *
0x18000a265  mov     edx, 3FFh; void *
0x18000a26a  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18000a270  mov     rcx, [rsp+2A8h+var_18]
0x18000a278  xor     rcx, rsp; StackCookie
0x18000a27b  call    __security_check_cookie
0x18000a280  add     rsp, 2A0h
0x18000a287  pop     rbx
0x18000a288  retn
```
