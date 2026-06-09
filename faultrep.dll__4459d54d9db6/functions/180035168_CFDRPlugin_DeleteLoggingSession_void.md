# CFDRPlugin::DeleteLoggingSession(void)

- ea: `0x180035168`
- end: `0x18003521d`
- name: `?DeleteLoggingSession@CFDRPlugin@@AEAAJXZ`
- size: `181`
- prototype: `__int64 __fastcall(CFDRPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180035c50`

## callees

- `0x180009ed8`
- `0x180034df8`
- `0x180035168`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800351b3`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800351b3`

## string_xrefs

- `0x1800351a5`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\FDR\CurrentSession`

## pseudocode

```c
__int64 __fastcall CFDRPlugin::DeleteLoggingSession(CFDRPlugin *this)
{
  _QWORD *v1; // rcx

  if ( (int)CFDRPlugin::DeleteFDRLayer(this) < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
  }
  if ( (RegDeleteKeyW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins\\FDR\\CurrentSession")
      & 0xFFFFFFFD) == 0 )
    return 0;
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
      v1 = WPP_GLOBAL_Control;
    }
    if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 1) != 0 )
      WPP_SF_(v1[2], 58, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180035168  push    rbx
0x18003516a  sub     rsp, 20h
0x18003516e  call    ?DeleteFDRLayer@CFDRPlugin@@AEAAJXZ; CFDRPlugin::DeleteFDRLayer(void)
0x180035173  lea     rbx, WPP_GLOBAL_Control
0x18003517a  test    eax, eax
0x18003517c  jns     short loc_1800351A5
0x18003517e  mov     rcx, cs:WPP_GLOBAL_Control
0x180035185  cmp     rcx, rbx
0x180035188  jz      short loc_1800351A5
0x18003518a  test    byte ptr [rcx+1Ch], 4
0x18003518e  jz      short loc_1800351A5
0x180035190  mov     rcx, [rcx+10h]
0x180035194  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x18003519b  mov     edx, 39h ; '9'
0x1800351a0  call    WPP_SF_
0x1800351a5  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\Windows\\Windows E"...
0x1800351ac  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800351b3  call    cs:__imp_RegDeleteKeyW
0x1800351b9  test    eax, 0FFFFFFFDh
0x1800351be  jz      short loc_180035215
0x1800351c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800351c7  cmp     rcx, rbx
0x1800351ca  jz      short loc_18003520E
0x1800351cc  test    byte ptr [rcx+1Ch], 1
0x1800351d0  jz      short loc_1800351EE
0x1800351d2  mov     rcx, [rcx+10h]
0x1800351d6  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x1800351dd  mov     edx, 33h ; '3'
0x1800351e2  call    WPP_SF_
0x1800351e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800351ee  cmp     rcx, rbx
0x1800351f1  jz      short loc_18003520E
0x1800351f3  test    byte ptr [rcx+1Ch], 1
0x1800351f7  jz      short loc_18003520E
0x1800351f9  mov     rcx, [rcx+10h]
0x1800351fd  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x180035204  mov     edx, 3Ah ; ':'
0x180035209  call    WPP_SF_
0x18003520e  mov     eax, 80004005h
0x180035213  jmp     short loc_180035217
0x180035215  xor     eax, eax
0x180035217  add     rsp, 20h
0x18003521b  pop     rbx
0x18003521c  retn
```
