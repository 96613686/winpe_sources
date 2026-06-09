# CRdpWindowTracker::STATIC_EnumMonitorsProc(HMONITOR__ *,HDC__ *,tagRECT *,__int64)

- ea: `0x14005e750`
- end: `0x14005e908`
- name: `?STATIC_EnumMonitorsProc@CRdpWindowTracker@@CAHPEAUHMONITOR__@@PEAUHDC__@@PEAUtagRECT@@_J@Z`
- size: `440`
- prototype: `BOOL __stdcall(HMONITOR, HDC, LPRECT, LPARAM)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x1400056c4`
- `0x140005750`
- `0x14005e750`
- `0x14006a120`

## import_xrefs

- `USER32!GetMonitorInfoW` at `0x14005e795`
- `USER32!GetMonitorInfoW` at `0x14005e795`
- `GDI32!CreateRectRgnIndirect` at `0x14005e7f8`
- `GDI32!CreateRectRgnIndirect` at `0x14005e7f8`
- `GDI32!CombineRgn` at `0x14005e878`
- `GDI32!CombineRgn` at `0x14005e878`
- `GDI32!DeleteObject` at `0x14005e8dc`
- `GDI32!DeleteObject` at `0x14005e8dc`

## string_xrefs

- `0x14005e836`: `CreateRectRgn() failed`
- `0x14005e8a6`: `CombineRgn() failed`

## pseudocode

```c
__int64 __fastcall CRdpWindowTracker::STATIC_EnumMonitorsProc(HMONITOR a1, HDC a2, LPRECT a3, HRGN a4)
{
  unsigned int v6; // eax
  HRGN RectRgnIndirect; // rax
  HRGN v8; // rbx
  unsigned int v9; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  tagMONITORINFO mi; // [rsp+30h] [rbp-88h] BYREF

  memset_0(&mi.rcMonitor, 0, 0x64u);
  mi.cbSize = 104;
  if ( GetMonitorInfoW(a1, &mi) )
  {
    RectRgnIndirect = CreateRectRgnIndirect(&mi.rcMonitor);
    v8 = RectRgnIndirect;
    if ( RectRgnIndirect )
    {
      if ( !CombineRgn(a4, a4, RectRgnIndirect, 2)
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          64,
          (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"CombineRgn() failed",
          -2147467259);
      }
      DeleteObject(v8);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
        v9,
        (__int64)"CreateRectRgn() failed",
        -2147467259);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids, v6);
  }
  return 1;
}

```

## disassembly

```asm
0x14005e750  mov     [rsp+arg_8], rbx
0x14005e755  push    rdi
0x14005e756  sub     rsp, 0B0h
0x14005e75d  mov     rax, cs:__security_cookie
0x14005e764  xor     rax, rsp
0x14005e767  mov     [rsp+0B8h+var_18], rax
0x14005e76f  xor     edx, edx; Val
0x14005e771  mov     rbx, rcx
0x14005e774  lea     rcx, [rsp+0B8h+mi.rcMonitor]; void *
0x14005e779  mov     rdi, r9
0x14005e77c  lea     r8d, [rdx+64h]; Size
0x14005e780  call    memset_0
0x14005e785  lea     rdx, [rsp+0B8h+mi]; lpmi
0x14005e78a  mov     [rsp+0B8h+mi.cbSize], 68h ; 'h'
0x14005e792  mov     rcx, rbx; hMonitor
0x14005e795  call    cs:__imp_GetMonitorInfoW
0x14005e79b  test    eax, eax
0x14005e79d  jnz     short loc_14005E7F3
0x14005e79f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e7a6  lea     rax, WPP_GLOBAL_Control
0x14005e7ad  cmp     rcx, rax
0x14005e7b0  jz      loc_14005E8E2
0x14005e7b6  test    byte ptr [rcx+1Ch], 8
0x14005e7ba  jz      loc_14005E8E2
0x14005e7c0  cmp     byte ptr [rcx+19h], 3
0x14005e7c4  jb      loc_14005E8E2
0x14005e7ca  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005e7cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e7d6  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005e7dd  mov     edx, 3Eh ; '>'
0x14005e7e2  mov     r9d, eax
0x14005e7e5  mov     rcx, [rcx+10h]
0x14005e7e9  call    WPP_SF_d
0x14005e7ee  jmp     loc_14005E8E2
0x14005e7f3  lea     rcx, [rsp+0B8h+mi.rcMonitor]; lprect
0x14005e7f8  call    cs:__imp_CreateRectRgnIndirect
0x14005e7fe  mov     rbx, rax
0x14005e801  test    rax, rax
0x14005e804  jnz     short loc_14005E869
0x14005e806  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e80d  lea     rax, WPP_GLOBAL_Control
0x14005e814  cmp     rcx, rax
0x14005e817  jz      loc_14005E8E2
0x14005e81d  test    byte ptr [rcx+1Ch], 8
0x14005e821  jz      loc_14005E8E2
0x14005e827  cmp     byte ptr [rcx+19h], 2
0x14005e82b  jb      loc_14005E8E2
0x14005e831  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005e836  lea     rcx, aCreaterectrgnF; "CreateRectRgn() failed"
0x14005e83d  mov     [rsp+0B8h+var_90], 80004005h
0x14005e845  mov     [rsp+0B8h+var_98], rcx
0x14005e84a  lea     edx, [rbx+3Fh]
0x14005e84d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e854  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005e85b  mov     r9d, eax
0x14005e85e  mov     rcx, [rcx+10h]
0x14005e862  call    WPP_SF_DsD
0x14005e867  jmp     short loc_14005E8E2
0x14005e869  mov     r9d, 2; iMode
0x14005e86f  mov     r8, rbx; hrgnSrc2
0x14005e872  mov     rdx, rdi; hrgnSrc1
0x14005e875  mov     rcx, rdi; hrgnDst
0x14005e878  call    cs:__imp_CombineRgn
0x14005e87e  test    eax, eax
0x14005e880  jnz     short loc_14005E8D9
0x14005e882  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e889  lea     rax, WPP_GLOBAL_Control
0x14005e890  cmp     rcx, rax
0x14005e893  jz      short loc_14005E8D9
0x14005e895  test    byte ptr [rcx+1Ch], 8
0x14005e899  jz      short loc_14005E8D9
0x14005e89b  cmp     byte ptr [rcx+19h], 2
0x14005e89f  jb      short loc_14005E8D9
0x14005e8a1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005e8a6  lea     rcx, aCombinergnFail; "CombineRgn() failed"
0x14005e8ad  mov     [rsp+0B8h+var_90], 80004005h
0x14005e8b5  mov     [rsp+0B8h+var_98], rcx
0x14005e8ba  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005e8c1  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e8c8  mov     edx, 40h ; '@'
0x14005e8cd  mov     r9d, eax
0x14005e8d0  mov     rcx, [rcx+10h]
0x14005e8d4  call    WPP_SF_DsD
0x14005e8d9  mov     rcx, rbx; ho
0x14005e8dc  call    cs:__imp_DeleteObject
0x14005e8e2  mov     eax, 1
0x14005e8e7  mov     rcx, [rsp+0B8h+var_18]
0x14005e8ef  xor     rcx, rsp; StackCookie
0x14005e8f2  call    __security_check_cookie
0x14005e8f7  mov     rbx, [rsp+0B8h+arg_8]
0x14005e8ff  add     rsp, 0B0h
0x14005e906  pop     rdi
0x14005e907  retn
```
