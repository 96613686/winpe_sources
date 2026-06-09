# CRdpClipMainWnd::RefreshWallpaper(int)

- ea: `0x140004bc4`
- end: `0x140004c82`
- name: `?RefreshWallpaper@CRdpClipMainWnd@@IEAAXH@Z`
- size: `190`
- prototype: `void __fastcall(CRdpClipMainWnd *__hidden this, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000429c`

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x140004bc4`
- `0x1400056c4`
- `0x14006a120`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x140004c06`
- `USER32!SystemParametersInfoW` at `0x140004c1d`
- `USER32!SystemParametersInfoW` at `0x140004c06`
- `USER32!SystemParametersInfoW` at `0x140004c1d`

## pseudocode

```c
void __fastcall CRdpClipMainWnd::RefreshWallpaper(CRdpClipMainWnd *this, int a2)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  _BYTE pvParam[528]; // [rsp+20h] [rbp-228h] BYREF

  if ( !a2 )
  {
    memset_0(pvParam, 0, 0x208u);
    if ( SystemParametersInfoW(0x73u, 0x104u, pvParam, 0) )
    {
      if ( !SystemParametersInfoW(0x14u, 0, pvParam, 0)
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          WPP_4c38a7a72efb3f7c531805000cd98558_Traceguids,
          CurrentThreadActivityIdPrefix);
      }
    }
  }
}

```

## disassembly

```asm
0x140004bc4  test    edx, edx
0x140004bc6  jnz     locret_140004C81
0x140004bcc  sub     rsp, 248h
0x140004bd3  mov     rax, cs:__security_cookie
0x140004bda  xor     rax, rsp
0x140004bdd  mov     [rsp+248h+var_18], rax
0x140004be5  mov     r8d, 208h; Size
0x140004beb  lea     rcx, [rsp+248h+pvParam]; void *
0x140004bf0  call    memset_0
0x140004bf5  xor     r9d, r9d; fWinIni
0x140004bf8  lea     r8, [rsp+248h+pvParam]; pvParam
0x140004bfd  mov     edx, 104h; uiParam
0x140004c02  lea     ecx, [r9+73h]; uiAction
0x140004c06  call    cs:__imp_SystemParametersInfoW
0x140004c0c  test    eax, eax
0x140004c0e  jz      short loc_140004C6A
0x140004c10  xor     edx, edx; uiParam
0x140004c12  lea     r8, [rsp+248h+pvParam]; pvParam
0x140004c17  xor     r9d, r9d; fWinIni
0x140004c1a  lea     ecx, [rdx+14h]; uiAction
0x140004c1d  call    cs:__imp_SystemParametersInfoW
0x140004c23  test    eax, eax
0x140004c25  jnz     short loc_140004C6A
0x140004c27  mov     rax, cs:WPP_GLOBAL_Control
0x140004c2e  lea     rcx, WPP_GLOBAL_Control
0x140004c35  cmp     rax, rcx
0x140004c38  jz      short loc_140004C6A
0x140004c3a  test    byte ptr [rax+1Ch], 1
0x140004c3e  jz      short loc_140004C6A
0x140004c40  cmp     byte ptr [rax+19h], 2
0x140004c44  jb      short loc_140004C6A
0x140004c46  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140004c4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140004c52  lea     r8, WPP_4c38a7a72efb3f7c531805000cd98558_Traceguids
0x140004c59  mov     edx, 26h ; '&'
0x140004c5e  mov     r9d, eax
0x140004c61  mov     rcx, [rcx+10h]
0x140004c65  call    WPP_SF_d
0x140004c6a  mov     rcx, [rsp+248h+var_18]
0x140004c72  xor     rcx, rsp; StackCookie
0x140004c75  call    __security_check_cookie
0x140004c7a  add     rsp, 248h
0x140004c81  retn
```
