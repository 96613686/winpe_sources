# CPackage::_DrawIconToDC(HDC__ *,_IC *,bool)

- ea: `0x18000a474`
- end: `0x18000a61c`
- name: `?_DrawIconToDC@CPackage@@IEAAXPEAUHDC__@@PEAU_IC@@_N@Z`
- size: `424`
- prototype: `void __fastcall(CPackage *this, HDC, struct _IC *, char)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000874c`
- `0x180008b94`

## callees

- `0x18000a474`
- `0x18000afb4`
- `0x18000b94c`
- `0x18000c5e8`
- `0x18000cbf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a5f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a5f9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000a54a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000a54a`
- `KERNEL32!lstrlenW` at `0x18000a5b0`
- `KERNEL32!lstrlenW` at `0x18000a5b0`
- `USER32!DrawIcon` at `0x18000a589`
- `USER32!DrawIcon` at `0x18000a589`
- `USER32!SetRect` at `0x18000a53d`
- `USER32!SetRect` at `0x18000a53d`
- `GDI32!TextOutW` at `0x18000a5db`
- `GDI32!TextOutW` at `0x18000a5db`
- `GDI32!SetTextAlign` at `0x18000a5a5`
- `GDI32!SetTextAlign` at `0x18000a5a5`
- `GDI32!SetBkMode` at `0x18000a597`
- `GDI32!SetBkMode` at `0x18000a597`
- `GDI32!SelectObject` at `0x18000a55a`
- `GDI32!SelectObject` at `0x18000a5ec`
- `GDI32!SelectObject` at `0x18000a55a`
- `GDI32!SelectObject` at `0x18000a5ec`
- `GDI32!SetWindowExtEx` at `0x18000a51c`
- `GDI32!SetWindowExtEx` at `0x18000a51c`
- `GDI32!SetWindowOrgEx` at `0x18000a4fe`
- `GDI32!SetWindowOrgEx` at `0x18000a4fe`

## pseudocode

```c
void __fastcall CPackage::_DrawIconToDC(CPackage *this, HDC a2, struct _IC *a3, char a4)
{
  LONG v6; // edx
  struct tagRECT *v7; // r9
  LONG v9; // eax
  CPackage *v10; // rcx
  HGDIOBJ v11; // rdi
  int v12; // edx
  int v13; // eax
  struct tagRECT v14; // [rsp+30h] [rbp-D0h] BYREF
  struct tagRECT rc; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR String[264]; // [rsp+50h] [rbp-B0h] BYREF

  v6 = *((_DWORD *)this + 64);
  v7 = 0;
  rc = 0;
  v14 = 0;
  if ( v6 )
  {
    v9 = *((_DWORD *)this + 63);
    if ( v9 )
    {
      v14.right = v6;
      v7 = &v14;
      v14.bottom = v9;
    }
  }
  CPackage::_CreateSaferIconTitle(this, (CPackage *)String, (const WCHAR *)a3, v7);
  CPackage::_IconCalcSize(v10, (struct tagRECT *)((char *)a3 + 1052), String);
  SetWindowOrgEx(a2, 0, 0, 0);
  SetWindowExtEx(a2, *((_DWORD *)a3 + 265) - 1, *((_DWORD *)a3 + 266) - 1, 0);
  SetRect(&rc, 0, 0, *((_DWORD *)a3 + 265), *((_DWORD *)a3 + 266));
  AcquireSRWLockShared(&PackagerFontLock);
  v11 = SelectObject(a2, g_hfontTitle);
  v12 = (rc.right - g_cxIcon) / 2;
  if ( a4 )
    AlphaStripRenderIcon(a2, v12);
  else
    DrawIcon(a2, v12, 0, *(HICON *)a3);
  SetBkMode(a2, 1);
  SetTextAlign(a2, 6u);
  v13 = lstrlenW(String);
  TextOutW(a2, rc.right / 2, g_cxIcon + 1, String, v13);
  if ( v11 )
    SelectObject(a2, v11);
  ReleaseSRWLockShared(&PackagerFontLock);
}

```

## disassembly

```asm
0x18000a474  push    rbp
0x18000a476  push    rbx
0x18000a477  push    rsi
0x18000a478  push    rdi
0x18000a479  push    r14
0x18000a47b  lea     rbp, [rsp-170h]
0x18000a483  sub     rsp, 270h
0x18000a48a  mov     rax, cs:__security_cookie
0x18000a491  xor     rax, rsp
0x18000a494  mov     [rbp+190h+var_30], rax
0x18000a49b  mov     r14b, r9b
0x18000a49e  mov     rbx, rdx
0x18000a4a1  mov     edx, [rcx+100h]
0x18000a4a7  xor     r9d, r9d
0x18000a4aa  xorps   xmm0, xmm0
0x18000a4ad  xorps   xmm1, xmm1
0x18000a4b0  mov     rsi, r8
0x18000a4b3  movups  xmmword ptr [rsp+290h+rc.left], xmm0
0x18000a4b8  movups  xmmword ptr [rsp+290h+var_260.left], xmm1
0x18000a4bd  test    edx, edx
0x18000a4bf  jz      short loc_18000A4D8
0x18000a4c1  mov     eax, [rcx+0FCh]
0x18000a4c7  test    eax, eax
0x18000a4c9  jz      short loc_18000A4D8
0x18000a4cb  mov     [rsp+290h+var_260.right], edx
0x18000a4cf  lea     r9, [rsp+290h+var_260]; struct tagRECT *
0x18000a4d4  mov     [rsp+290h+var_260.bottom], eax
0x18000a4d8  lea     rdx, [rsp+290h+String]; unsigned __int16 *
0x18000a4dd  call    ?_CreateSaferIconTitle@CPackage@@IEAAXPEAGPEAU_IC@@PEBUtagRECT@@@Z; CPackage::_CreateSaferIconTitle(ushort *,_IC *,tagRECT const *)
0x18000a4e2  lea     rdx, [rsi+41Ch]; struct tagRECT *
0x18000a4e9  lea     r8, [rsp+290h+String]; unsigned __int16 *
0x18000a4ee  call    ?_IconCalcSize@CPackage@@IEAAHPEAUtagRECT@@PEBG@Z; CPackage::_IconCalcSize(tagRECT *,ushort const *)
0x18000a4f3  xor     r9d, r9d; lppt
0x18000a4f6  xor     r8d, r8d; y
0x18000a4f9  xor     edx, edx; x
0x18000a4fb  mov     rcx, rbx; hdc
0x18000a4fe  call    cs:__imp_SetWindowOrgEx
0x18000a504  mov     r8d, [rsi+428h]
0x18000a50b  xor     r9d, r9d; lpsz
0x18000a50e  mov     edx, [rsi+424h]
0x18000a514  dec     r8d; y
0x18000a517  dec     edx; x
0x18000a519  mov     rcx, rbx; hdc
0x18000a51c  call    cs:__imp_SetWindowExtEx
0x18000a522  mov     eax, [rsi+428h]
0x18000a528  lea     rcx, [rsp+290h+rc]; lprc
0x18000a52d  mov     r9d, [rsi+424h]; xRight
0x18000a534  xor     r8d, r8d; yTop
0x18000a537  xor     edx, edx; xLeft
0x18000a539  mov     [rsp+290h+yBottom], eax; yBottom
0x18000a53d  call    cs:__imp_SetRect
0x18000a543  lea     rcx, ?PackagerFontLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18000a54a  call    cs:__imp_AcquireSRWLockShared
0x18000a550  mov     rdx, cs:?g_hfontTitle@@3PEAUHFONT__@@EA; h
0x18000a557  mov     rcx, rbx; hdc
0x18000a55a  call    cs:__imp_SelectObject
0x18000a560  mov     r9, [rsi]; hIcon
0x18000a563  mov     rcx, rbx; hDC
0x18000a566  mov     rdi, rax
0x18000a569  mov     eax, [rsp+290h+rc.right]
0x18000a56d  sub     eax, cs:?g_cxIcon@@3HA; int g_cxIcon
0x18000a573  cdq
0x18000a574  sub     eax, edx
0x18000a576  sar     eax, 1
0x18000a578  mov     edx, eax; X
0x18000a57a  test    r14b, r14b
0x18000a57d  jz      short loc_18000A586
0x18000a57f  call    AlphaStripRenderIcon
0x18000a584  jmp     short loc_18000A58F
0x18000a586  xor     r8d, r8d; Y
0x18000a589  call    cs:__imp_DrawIcon
0x18000a58f  mov     edx, 1; mode
0x18000a594  mov     rcx, rbx; hdc
0x18000a597  call    cs:__imp_SetBkMode
0x18000a59d  mov     edx, 6; align
0x18000a5a2  mov     rcx, rbx; hdc
0x18000a5a5  call    cs:__imp_SetTextAlign
0x18000a5ab  lea     rcx, [rsp+290h+String]; lpString
0x18000a5b0  call    cs:__imp_lstrlenW
0x18000a5b6  mov     r8d, cs:?g_cxIcon@@3HA; int g_cxIcon
0x18000a5bd  mov     rcx, rbx; hdc
0x18000a5c0  mov     r9d, eax
0x18000a5c3  inc     r8d; y
0x18000a5c6  mov     eax, [rsp+290h+rc.right]
0x18000a5ca  cdq
0x18000a5cb  mov     [rsp+290h+yBottom], r9d; c
0x18000a5d0  sub     eax, edx
0x18000a5d2  lea     r9, [rsp+290h+String]; lpString
0x18000a5d7  sar     eax, 1
0x18000a5d9  mov     edx, eax; x
0x18000a5db  call    cs:__imp_TextOutW
0x18000a5e1  test    rdi, rdi
0x18000a5e4  jz      short loc_18000A5F2
0x18000a5e6  mov     rdx, rdi; h
0x18000a5e9  mov     rcx, rbx; hdc
0x18000a5ec  call    cs:__imp_SelectObject
0x18000a5f2  lea     rcx, ?PackagerFontLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18000a5f9  call    cs:__imp_ReleaseSRWLockShared
0x18000a5ff  mov     rcx, [rbp+190h+var_30]
0x18000a606  xor     rcx, rsp; StackCookie
0x18000a609  call    __security_check_cookie
0x18000a60e  add     rsp, 270h
0x18000a615  pop     r14
0x18000a617  pop     rdi
0x18000a618  pop     rsi
0x18000a619  pop     rbx
0x18000a61a  pop     rbp
0x18000a61b  retn
```
