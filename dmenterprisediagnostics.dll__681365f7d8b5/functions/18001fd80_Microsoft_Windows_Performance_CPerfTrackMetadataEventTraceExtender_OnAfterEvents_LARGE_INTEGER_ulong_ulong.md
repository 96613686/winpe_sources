# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18001fd80`
- end: `0x18001fe9e`
- name: `?OnAfterEvents@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z`
- size: `286`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001800`
- `0x1800023e0`
- `0x180006be0`
- `0x18000b750`
- `0x18001fd80`
- `0x180020508`
- `0x18002099c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18001fdd0`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18001fdd0`

## string_xrefs

- `0x18001fdfa`: `*.xml`
- `0x18001fe21`: `*.ptxml`
- `0x18001fde0`: `\system32\wdi\PerfTrack\`

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
0x18001fd80  push    rbx
0x18001fd82  push    rbp
0x18001fd83  push    rsi
0x18001fd84  push    rdi
0x18001fd85  sub     rsp, 258h
0x18001fd8c  mov     rax, cs:__security_cookie
0x18001fd93  xor     rax, rsp
0x18001fd96  mov     [rsp+278h+var_38], rax
0x18001fd9e  cmp     byte ptr [rcx+20h], 0
0x18001fda2  mov     ebp, r9d
0x18001fda5  mov     esi, r8d
0x18001fda8  mov     rbx, rdx
0x18001fdab  mov     rdi, rcx
0x18001fdae  jnz     loc_18001FE59
0x18001fdb4  xor     edx, edx; Val
0x18001fdb6  lea     rcx, [rsp+278h+Buffer]; void *
0x18001fdbb  mov     r8d, 208h; Size
0x18001fdc1  call    memset_0
0x18001fdc6  mov     edx, 104h; uSize
0x18001fdcb  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x18001fdd0  call    cs:__imp_GetWindowsDirectoryW
0x18001fdd7  nop     dword ptr [rax+rax+00h]
0x18001fddc  test    eax, eax
0x18001fdde  jz      short loc_18001FE48
0x18001fde0  lea     r8, aSystem32WdiPer; "\\system32\\wdi\\PerfTrack\\"
0x18001fde7  mov     edx, 104h; unsigned __int64
0x18001fdec  lea     rcx, [rsp+278h+Buffer]; unsigned __int16 *
0x18001fdf1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001fdf6  test    eax, eax
0x18001fdf8  js      short loc_18001FE48
0x18001fdfa  lea     rax, aXml; "*.xml"
0x18001fe01  mov     r9d, ebp; unsigned int
0x18001fe04  mov     [rsp+278h+var_250], rax; unsigned __int16 *
0x18001fe09  mov     r8d, esi; unsigned int
0x18001fe0c  lea     rax, [rsp+278h+Buffer]
0x18001fe11  mov     rdx, rbx; union _LARGE_INTEGER
0x18001fe14  mov     rcx, rdi; this
0x18001fe17  mov     [rsp+278h+var_258], rax; unsigned __int16 *
0x18001fe1c  call    ?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)
0x18001fe21  lea     rax, aPtxml; "*.ptxml"
0x18001fe28  mov     r9d, ebp; unsigned int
0x18001fe2b  mov     [rsp+278h+var_250], rax; unsigned __int16 *
0x18001fe30  mov     r8d, esi; unsigned int
0x18001fe33  lea     rax, [rsp+278h+Buffer]
0x18001fe38  mov     rdx, rbx; union _LARGE_INTEGER
0x18001fe3b  mov     rcx, rdi; this
0x18001fe3e  mov     [rsp+278h+var_258], rax; unsigned __int16 *
0x18001fe43  call    ?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)
0x18001fe48  mov     r9d, ebp; unsigned int
0x18001fe4b  mov     r8d, esi; unsigned int
0x18001fe4e  mov     rdx, rbx; union _LARGE_INTEGER
0x18001fe51  mov     rcx, rdi; this
0x18001fe54  call    ?ProcessPerfTrackRegistry@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackRegistry(_LARGE_INTEGER,ulong,ulong)
0x18001fe59  mov     r9d, ebp; unsigned int
0x18001fe5c  mov     r8d, esi; unsigned int
0x18001fe5f  mov     rdx, rbx; union _LARGE_INTEGER
0x18001fe62  mov     rcx, rdi; this
0x18001fe65  call    ?OnAfterEvents@CEventTraceExtenderBase@Performance@Windows@Microsoft@@UEAAJT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CEventTraceExtenderBase::OnAfterEvents(_LARGE_INTEGER,ulong,ulong)
0x18001fe6a  cmp     byte ptr [rdi+20h], 0
0x18001fe6e  mov     ecx, eax
0x18001fe70  jnz     short loc_18001FE7F
0x18001fe72  xor     eax, eax
0x18001fe74  cmp     ecx, 80004001h
0x18001fe7a  cmovnz  eax, ecx
0x18001fe7d  mov     ecx, eax
0x18001fe7f  mov     eax, ecx
0x18001fe81  mov     rcx, [rsp+278h+var_38]
0x18001fe89  xor     rcx, rsp; StackCookie
0x18001fe8c  call    __security_check_cookie
0x18001fe91  add     rsp, 258h
0x18001fe98  pop     rdi
0x18001fe99  pop     rsi
0x18001fe9a  pop     rbp
0x18001fe9b  pop     rbx
0x18001fe9c  retn
```
