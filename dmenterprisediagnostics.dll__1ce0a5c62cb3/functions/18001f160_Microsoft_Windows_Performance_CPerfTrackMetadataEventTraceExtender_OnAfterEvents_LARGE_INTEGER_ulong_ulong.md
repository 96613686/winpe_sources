# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18001f160`
- end: `0x18001f277`
- name: `?OnAfterEvents@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `279`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800017e0`
- `0x1800023c0`
- `0x180006960`
- `0x18000b1e0`
- `0x18001f160`
- `0x18001f888`
- `0x18001fce4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18001f1b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18001f1b0`

## string_xrefs

- `0x18001f1d4`: `*.xml`
- `0x18001f1fb`: `*.ptxml`
- `0x18001f1ba`: `\system32\wdi\PerfTrack\`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::OnAfterEvents(
        Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned int v8; // ecx
  unsigned int v9; // eax
  WCHAR Buffer[264]; // [rsp+30h] [rbp-248h] BYREF

  if ( !*((_BYTE *)this + 32) )
  {
    memset_0(Buffer, 0, 0x208u);
    if ( GetWindowsDirectoryW(Buffer, 0x104u) && StringCchCatW(Buffer, 0x104u, L"\\system32\\wdi\\PerfTrack\\") >= 0 )
    {
      Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(
        this,
        a2,
        a3,
        a4,
        Buffer,
        L"*.xml");
      Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(
        this,
        a2,
        a3,
        a4,
        Buffer,
        L"*.ptxml");
    }
    Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackRegistry(this, a2, a3, a4);
  }
  v8 = Microsoft::Windows::Performance::CEventTraceExtenderBase::OnAfterEvents(this, a2, a3, a4);
  if ( !*((_BYTE *)this + 32) )
  {
    v9 = 0;
    if ( v8 != -2147467263 )
      return v8;
    return v9;
  }
  return v8;
}

```

## disassembly

```asm
0x18001f160  push    rbx
0x18001f162  push    rbp
0x18001f163  push    rsi
0x18001f164  push    rdi
0x18001f165  sub     rsp, 258h
0x18001f16c  mov     rax, cs:__security_cookie
0x18001f173  xor     rax, rsp
0x18001f176  mov     [rsp+278h+var_38], rax
0x18001f17e  cmp     byte ptr [rcx+20h], 0
0x18001f182  mov     ebp, r9d
0x18001f185  mov     esi, r8d
0x18001f188  mov     rbx, rdx
0x18001f18b  mov     rdi, rcx
0x18001f18e  jnz     loc_18001F233
0x18001f194  xor     edx, edx; Val
0x18001f196  lea     rcx, [rsp+278h+Buffer]; void *
0x18001f19b  mov     r8d, 208h; Size
0x18001f1a1  call    memset_0
0x18001f1a6  mov     edx, 104h; uSize
0x18001f1ab  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x18001f1b0  call    cs:__imp_GetWindowsDirectoryW
0x18001f1b6  test    eax, eax
0x18001f1b8  jz      short loc_18001F222
0x18001f1ba  lea     r8, aSystem32WdiPer; "\\system32\\wdi\\PerfTrack\\"
0x18001f1c1  mov     edx, 104h; unsigned __int64
0x18001f1c6  lea     rcx, [rsp+278h+Buffer]; unsigned __int16 *
0x18001f1cb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001f1d0  test    eax, eax
0x18001f1d2  js      short loc_18001F222
0x18001f1d4  lea     rax, aXml; "*.xml"
0x18001f1db  mov     r9d, ebp; unsigned int
0x18001f1de  mov     [rsp+278h+var_250], rax; unsigned __int16 *
0x18001f1e3  mov     r8d, esi; unsigned int
0x18001f1e6  lea     rax, [rsp+278h+Buffer]
0x18001f1eb  mov     rdx, rbx; union _LARGE_INTEGER
0x18001f1ee  mov     rcx, rdi; this
0x18001f1f1  mov     [rsp+278h+var_258], rax; unsigned __int16 *
0x18001f1f6  call    ?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)
0x18001f1fb  lea     rax, aPtxml; "*.ptxml"
0x18001f202  mov     r9d, ebp; unsigned int
0x18001f205  mov     [rsp+278h+var_250], rax; unsigned __int16 *
0x18001f20a  mov     r8d, esi; unsigned int
0x18001f20d  lea     rax, [rsp+278h+Buffer]
0x18001f212  mov     rdx, rbx; union _LARGE_INTEGER
0x18001f215  mov     rcx, rdi; this
0x18001f218  mov     [rsp+278h+var_258], rax; unsigned __int16 *
0x18001f21d  call    ?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)
0x18001f222  mov     r9d, ebp; unsigned int
0x18001f225  mov     r8d, esi; unsigned int
0x18001f228  mov     rdx, rbx; union _LARGE_INTEGER
0x18001f22b  mov     rcx, rdi; this
0x18001f22e  call    ?ProcessPerfTrackRegistry@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackRegistry(_LARGE_INTEGER,ulong,ulong)
0x18001f233  mov     r9d, ebp; unsigned int
0x18001f236  mov     r8d, esi; unsigned int
0x18001f239  mov     rdx, rbx; union _LARGE_INTEGER
0x18001f23c  mov     rcx, rdi; this
0x18001f23f  call    ?OnAfterEvents@CEventTraceExtenderBase@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CEventTraceExtenderBase::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)
0x18001f244  cmp     byte ptr [rdi+20h], 0
0x18001f248  mov     ecx, eax
0x18001f24a  jnz     short loc_18001F259
0x18001f24c  xor     eax, eax
0x18001f24e  cmp     ecx, 80004001h
0x18001f254  cmovnz  eax, ecx
0x18001f257  mov     ecx, eax
0x18001f259  mov     eax, ecx
0x18001f25b  mov     rcx, [rsp+278h+var_38]
0x18001f263  xor     rcx, rsp; StackCookie
0x18001f266  call    __security_check_cookie
0x18001f26b  add     rsp, 258h
0x18001f272  pop     rdi
0x18001f273  pop     rsi
0x18001f274  pop     rbp
0x18001f275  pop     rbx
0x18001f276  retn
```
