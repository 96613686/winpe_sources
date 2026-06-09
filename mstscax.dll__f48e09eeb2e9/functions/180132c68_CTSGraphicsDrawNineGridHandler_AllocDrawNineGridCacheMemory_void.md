# CTSGraphicsDrawNineGridHandler::AllocDrawNineGridCacheMemory(void)

- ea: `0x180132c68`
- end: `0x180132ed1`
- name: `?AllocDrawNineGridCacheMemory@CTSGraphicsDrawNineGridHandler@@IEAAJXZ`
- size: `617`
- prototype: `__int64 __fastcall(CTSGraphicsDrawNineGridHandler *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180133690`

## callees

- `0x180039c98`
- `0x180039ce4`
- `0x18009f2f8`
- `0x180132c68`
- `0x180133834`
- `0x180688f3e`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180132dba`
- `KERNEL32!LocalAlloc` at `0x180132dba`
- `KERNEL32!LocalFree` at `0x180132e5f`
- `KERNEL32!LocalFree` at `0x180132e5f`
- `GDI32!CreateRectRgn` at `0x180132d8f`
- `GDI32!CreateRectRgn` at `0x180132d8f`
- `GDI32!DeleteObject` at `0x180132e46`
- `GDI32!DeleteObject` at `0x180132e46`
- `GDI32!DeleteDC` at `0x180132e30`
- `GDI32!DeleteDC` at `0x180132e30`
- `GDI32!CreateCompatibleDC` at `0x180132d50`
- `GDI32!CreateCompatibleDC` at `0x180132d50`
- `GDI32!SelectPalette` at `0x180132d75`
- `GDI32!SelectPalette` at `0x180132d75`
- `GDI32!RealizePalette` at `0x180132d7f`
- `GDI32!RealizePalette` at `0x180132d7f`
- `USER32!GetWindowDC` at `0x180132d3b`
- `USER32!GetWindowDC` at `0x180132d3b`
- `USER32!ReleaseDC` at `0x180132eb6`
- `USER32!ReleaseDC` at `0x180132eb6`

## string_xrefs

- `0x180132cb9`: `DrawNineGridCacheSize`
- `0x180132cdd`: `DrawNineGridCacheEntries`

## pseudocode

```c
__int64 __fastcall CTSGraphicsDrawNineGridHandler::AllocDrawNineGridCacheMemory(CTSGraphicsDrawNineGridHandler *this)
{
  HDC v2; // rdi
  unsigned int v3; // ebp
  int RegistryInt; // esi
  int v5; // eax
  HDC WindowDC; // rax
  HDC CompatibleDC; // rax
  HPALETTE CurrentPalette; // rax
  HRGN RectRgn; // rax
  unsigned int v10; // ebp
  HLOCAL v11; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HDC v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  unsigned int v16; // eax

  v2 = 0;
  v3 = -2147467259;
  RegistryInt = CUT::UT_ReadRegistryInt(&sourceString, L"DrawNineGridSupportLevel", 2, 2);
  CUT::UT_ReadRegistryInt(&sourceString, L"DrawNineGridEmulate", 0, 2);
  *((_DWORD *)this + 35) = CUT::UT_ReadRegistryInt(&sourceString, L"DrawNineGridCacheSize", 2560, 2);
  v5 = CUT::UT_ReadRegistryInt(&sourceString, L"DrawNineGridCacheEntries", 256, 2);
  *((_DWORD *)this + 36) = v5;
  if ( RegistryInt < 0 )
    RegistryInt = 2;
  if ( (unsigned int)(*((_DWORD *)this + 35) - 512) > 0x1C00 )
    *((_DWORD *)this + 35) = 2560;
  if ( (unsigned int)(v5 - 50) > 0x1C2 )
    *((_DWORD *)this + 36) = 256;
  if ( RegistryInt )
  {
    WindowDC = GetWindowDC(0);
    v2 = WindowDC;
    if ( WindowDC )
    {
      CompatibleDC = CreateCompatibleDC(WindowDC);
      *((_QWORD *)this + 14) = CompatibleDC;
      if ( CompatibleDC )
      {
        CurrentPalette = CTSGraphicsDrawNineGridHandler::GetCurrentPalette(this);
        SelectPalette(*((HDC *)this + 14), CurrentPalette, 0);
        RealizePalette(*((HDC *)this + 14));
        RectRgn = CreateRectRgn(0, 0, 0, 0);
        *((_QWORD *)this + 16) = RectRgn;
        if ( RectRgn )
        {
          v10 = 40 * *((_DWORD *)this + 36);
          v11 = LocalAlloc(0x40u, v10);
          *((_QWORD *)this + 19) = v11;
          if ( v11 )
          {
            memset_0(v11, 0, v10);
            v3 = 0;
            goto LABEL_24;
          }
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              31,
              WPP_70def9178a39339a9397f44e2a5c8663_Traceguids,
              CurrentThreadActivityIdPrefix,
              v10);
          }
          v3 = -2147024882;
        }
      }
    }
  }
  v13 = (HDC)*((_QWORD *)this + 14);
  RegistryInt = 0;
  if ( v13 )
  {
    DeleteDC(v13);
    *((_QWORD *)this + 14) = 0;
  }
  v14 = (void *)*((_QWORD *)this + 16);
  if ( v14 )
  {
    DeleteObject(v14);
    *((_QWORD *)this + 16) = 0;
  }
  v15 = (void *)*((_QWORD *)this + 19);
  if ( v15 )
  {
    LocalFree(v15);
    *((_QWORD *)this + 19) = 0;
  }
LABEL_24:
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      WPP_70def9178a39339a9397f44e2a5c8663_Traceguids,
      v16,
      RegistryInt);
  }
  if ( v2 )
    ReleaseDC(0, v2);
  *((_DWORD *)this + 34) = RegistryInt;
  return v3;
}

```

## disassembly

```asm
0x180132c68  push    rbx
0x180132c6a  push    rbp
0x180132c6b  push    rsi
0x180132c6c  push    rdi
0x180132c6d  push    r12
0x180132c6f  push    r14
0x180132c71  sub     rsp, 38h
0x180132c75  mov     rbx, rcx
0x180132c78  lea     r14, sourceString
0x180132c7f  xor     edi, edi
0x180132c81  lea     rdx, aDrawninegridsu; "DrawNineGridSupportLevel"
0x180132c88  mov     rcx, r14
0x180132c8b  mov     ebp, 80004005h
0x180132c90  lea     r12d, [rdi+2]
0x180132c94  mov     r9d, r12d
0x180132c97  mov     r8d, r12d
0x180132c9a  call    ?UT_ReadRegistryInt@CUT@@SAHPEBG0HW4UT_REGREAD_LOCATION@@@Z; CUT::UT_ReadRegistryInt(ushort const *,ushort const *,int,UT_REGREAD_LOCATION)
0x180132c9f  mov     r9d, r12d
0x180132ca2  lea     rdx, aDrawninegridem; "DrawNineGridEmulate"
0x180132ca9  xor     r8d, r8d
0x180132cac  mov     rcx, r14
0x180132caf  mov     esi, eax
0x180132cb1  call    ?UT_ReadRegistryInt@CUT@@SAHPEBG0HW4UT_REGREAD_LOCATION@@@Z; CUT::UT_ReadRegistryInt(ushort const *,ushort const *,int,UT_REGREAD_LOCATION)
0x180132cb6  mov     r9d, r12d
0x180132cb9  lea     rdx, aDrawninegridca; "DrawNineGridCacheSize"
0x180132cc0  mov     r8d, 0A00h
0x180132cc6  mov     rcx, r14
0x180132cc9  call    ?UT_ReadRegistryInt@CUT@@SAHPEBG0HW4UT_REGREAD_LOCATION@@@Z; CUT::UT_ReadRegistryInt(ushort const *,ushort const *,int,UT_REGREAD_LOCATION)
0x180132cce  mov     r9d, r12d
0x180132cd1  mov     [rbx+8Ch], eax
0x180132cd7  mov     r8d, 100h
0x180132cdd  lea     rdx, aDrawninegridca_0; "DrawNineGridCacheEntries"
0x180132ce4  mov     rcx, r14
0x180132ce7  call    ?UT_ReadRegistryInt@CUT@@SAHPEBG0HW4UT_REGREAD_LOCATION@@@Z; CUT::UT_ReadRegistryInt(ushort const *,ushort const *,int,UT_REGREAD_LOCATION)
0x180132cec  test    esi, esi
0x180132cee  mov     [rbx+90h], eax
0x180132cf4  mov     ecx, eax
0x180132cf6  mov     eax, [rbx+8Ch]
0x180132cfc  cmovs   esi, r12d
0x180132d00  sub     eax, 200h
0x180132d05  cmp     eax, 1C00h
0x180132d0a  jbe     short loc_180132D16
0x180132d0c  mov     dword ptr [rbx+8Ch], 0A00h
0x180132d16  lea     eax, [rcx-32h]
0x180132d19  cmp     eax, 1C2h
0x180132d1e  jbe     short loc_180132D2A
0x180132d20  mov     dword ptr [rbx+90h], 100h
0x180132d2a  lea     r14, WPP_GLOBAL_Control
0x180132d31  test    esi, esi
0x180132d33  jz      loc_180132E25
0x180132d39  xor     ecx, ecx; hWnd
0x180132d3b  call    cs:__imp_GetWindowDC
0x180132d41  mov     rdi, rax
0x180132d44  test    rax, rax
0x180132d47  jz      loc_180132E25
0x180132d4d  mov     rcx, rax; hdc
0x180132d50  call    cs:__imp_CreateCompatibleDC
0x180132d56  mov     [rbx+70h], rax
0x180132d5a  test    rax, rax
0x180132d5d  jz      loc_180132E25
0x180132d63  mov     rcx, rbx; this
0x180132d66  call    ?GetCurrentPalette@CTSGraphicsDrawNineGridHandler@@IEAAPEAUHPALETTE__@@XZ; CTSGraphicsDrawNineGridHandler::GetCurrentPalette(void)
0x180132d6b  mov     rcx, [rbx+70h]; hdc
0x180132d6f  xor     r8d, r8d; bForceBkgd
0x180132d72  mov     rdx, rax; hPal
0x180132d75  call    cs:__imp_SelectPalette
0x180132d7b  mov     rcx, [rbx+70h]; hdc
0x180132d7f  call    cs:__imp_RealizePalette
0x180132d85  xor     r9d, r9d; y2
0x180132d88  xor     r8d, r8d; x2
0x180132d8b  xor     edx, edx; y1
0x180132d8d  xor     ecx, ecx; x1
0x180132d8f  call    cs:__imp_CreateRectRgn
0x180132d95  mov     [rbx+80h], rax
0x180132d9c  test    rax, rax
0x180132d9f  jz      loc_180132E25
0x180132da5  mov     eax, [rbx+90h]
0x180132dab  lea     ecx, [rax+rax*4]
0x180132dae  shl     ecx, 3
0x180132db1  mov     ebp, ecx
0x180132db3  mov     edx, ecx; uBytes
0x180132db5  mov     ecx, 40h ; '@'; uFlags
0x180132dba  call    cs:__imp_LocalAlloc
0x180132dc0  mov     [rbx+98h], rax
0x180132dc7  test    rax, rax
0x180132dca  jz      short loc_180132DE0
0x180132dcc  mov     r8d, ebp; Size
0x180132dcf  xor     edx, edx; Val
0x180132dd1  mov     rcx, rax; void *
0x180132dd4  call    memset_0
0x180132dd9  xor     ebp, ebp
0x180132ddb  jmp     loc_180132E6C
0x180132de0  mov     rax, cs:WPP_GLOBAL_Control
0x180132de7  cmp     rax, r14
0x180132dea  jz      short loc_180132E20
0x180132dec  test    byte ptr [rax+1Ch], 1
0x180132df0  jz      short loc_180132E20
0x180132df2  cmp     [rax+19h], r12b
0x180132df6  jb      short loc_180132E20
0x180132df8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180132dfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180132e04  lea     r8, WPP_70def9178a39339a9397f44e2a5c8663_Traceguids
0x180132e0b  mov     edx, 1Fh
0x180132e10  mov     [rsp+68h+var_48], ebp
0x180132e14  mov     r9d, eax
0x180132e17  mov     rcx, [rcx+10h]
0x180132e1b  call    WPP_SF_Dd
0x180132e20  mov     ebp, 8007000Eh
0x180132e25  mov     rcx, [rbx+70h]; hdc
0x180132e29  xor     esi, esi
0x180132e2b  test    rcx, rcx
0x180132e2e  jz      short loc_180132E3A
0x180132e30  call    cs:__imp_DeleteDC
0x180132e36  mov     [rbx+70h], rsi
0x180132e3a  mov     rcx, [rbx+80h]; ho
0x180132e41  test    rcx, rcx
0x180132e44  jz      short loc_180132E53
0x180132e46  call    cs:__imp_DeleteObject
0x180132e4c  mov     [rbx+80h], rsi
0x180132e53  mov     rcx, [rbx+98h]; hMem
0x180132e5a  test    rcx, rcx
0x180132e5d  jz      short loc_180132E6C
0x180132e5f  call    cs:__imp_LocalFree
0x180132e65  mov     [rbx+98h], rsi
0x180132e6c  mov     rax, cs:WPP_GLOBAL_Control
0x180132e73  cmp     rax, r14
0x180132e76  jz      short loc_180132EAC
0x180132e78  test    byte ptr [rax+1Ch], 1
0x180132e7c  jz      short loc_180132EAC
0x180132e7e  cmp     byte ptr [rax+19h], 4
0x180132e82  jb      short loc_180132EAC
0x180132e84  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180132e89  mov     rcx, cs:WPP_GLOBAL_Control
0x180132e90  lea     r8, WPP_70def9178a39339a9397f44e2a5c8663_Traceguids
0x180132e97  mov     edx, 20h ; ' '
0x180132e9c  mov     [rsp+68h+var_48], esi
0x180132ea0  mov     r9d, eax
0x180132ea3  mov     rcx, [rcx+10h]
0x180132ea7  call    WPP_SF_Dd
0x180132eac  test    rdi, rdi
0x180132eaf  jz      short loc_180132EBC
0x180132eb1  mov     rdx, rdi; hDC
0x180132eb4  xor     ecx, ecx; hWnd
0x180132eb6  call    cs:__imp_ReleaseDC
0x180132ebc  mov     [rbx+88h], esi
0x180132ec2  mov     eax, ebp
0x180132ec4  add     rsp, 38h
0x180132ec8  pop     r14
0x180132eca  pop     r12
0x180132ecc  pop     rdi
0x180132ecd  pop     rsi
0x180132ece  pop     rbp
0x180132ecf  pop     rbx
0x180132ed0  retn
```
