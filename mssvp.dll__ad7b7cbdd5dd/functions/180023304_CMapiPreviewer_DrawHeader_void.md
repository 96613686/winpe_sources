# CMapiPreviewer::DrawHeader(void)

- ea: `0x180023304`
- end: `0x1800239bf`
- name: `?DrawHeader@CMapiPreviewer@@AEAAJXZ`
- size: `1723`
- prototype: `__int64 __fastcall(CMapiPreviewer *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180023020`

## callees

- `0x1800031c0`
- `0x180023304`
- `0x1800239c8`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x18002393d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x18002393d`
- `USER32!GetSysColor` at `0x180023326`
- `USER32!GetSysColor` at `0x180023332`
- `USER32!GetSysColor` at `0x180023326`
- `USER32!GetSysColor` at `0x180023332`
- `GDI32!DeleteObject` at `0x180023958`
- `GDI32!DeleteObject` at `0x180023973`
- `GDI32!DeleteObject` at `0x180023958`
- `GDI32!DeleteObject` at `0x180023973`

## pseudocode

```c
__int64 __fastcall CMapiPreviewer::DrawHeader(CMapiPreviewer *this)
{
  DWORD SysColor; // ebp
  DWORD v3; // r14d
  int v4; // eax
  int v5; // edi
  unsigned int v6; // edi
  unsigned int v7; // edx
  unsigned int v8; // r8d
  unsigned int v9; // r11d
  unsigned int v10; // r15d
  unsigned int v11; // r12d
  int v12; // eax
  unsigned int i; // ebp
  __int64 v14; // rsi
  HWND v15; // rcx
  void *v16; // rcx
  void *v17; // rcx

  *((_QWORD *)this + 149) = 0;
  SysColor = GetSysColor(8);
  v3 = GetSysColor(17);
  v4 = *((_DWORD *)this + 56);
  if ( v4 )
  {
    if ( v4 == 2 )
    {
      v5 = CMapiPreviewer::DrawItemOnHeader(
             this,
             0,
             0x37001Fu,
             0,
             0,
             0,
             0xFAu,
             0x105u,
             SysColor,
             0x107u,
             0x106u,
             0,
             0x108u,
             0);
      if ( v5 < 0 )
        goto LABEL_26;
      v5 = CMapiPreviewer::DrawItemOnHeader(
             this,
             0,
             0xC1A001Fu,
             0,
             0,
             0,
             0xFAu,
             0x10Fu,
             SysColor,
             0x111u,
             0x110u,
             0,
             0x112u,
             0);
      if ( v5 < 0 )
        goto LABEL_26;
      v5 = CMapiPreviewer::DrawItemOnHeader(
             this,
             0xC9u,
             0xE04001Fu,
             0,
             0,
             0,
             0xFAu,
             0x119u,
             SysColor,
             0x11Bu,
             0x11Au,
             v3,
             0x11Cu,
             0);
      if ( v5 < 0 )
        goto LABEL_26;
      v5 = CMapiPreviewer::DrawItemOnHeader(
             this,
             0xCAu,
             0xE03001Fu,
             0,
             0,
             1,
             0xFAu,
             0x123u,
             SysColor,
             0x125u,
             0x124u,
             v3,
             0x126u,
             0);
      if ( v5 < 0 )
        goto LABEL_26;
      v5 = CMapiPreviewer::DrawItemOnHeader(
             this,
             0xD5u,
             0,
             0,
             0,
             1,
             0xFAu,
             0x12Du,
             SysColor,
             0x12Fu,
             0x12Eu,
             v3,
             0x130u,
             1);
      if ( v5 < 0 )
        goto LABEL_26;
      v7 = 205;
      v10 = 312;
      v8 = 235274304;
      v6 = 313;
      v9 = 311;
      v11 = 314;
      goto LABEL_23;
    }
    if ( v4 == 5 )
    {
      v5 = CMapiPreviewer::DrawItemOnHeader(
             this,
             0,
             0x3001001Fu,
             0,
             0,
             0,
             0xFAu,
             0x17Du,
             SysColor,
             0x17Fu,
             0x17Eu,
             0,
             0x180u,
             0);
      if ( v5 < 0 )
        goto LABEL_26;
      v5 = CMapiPreviewer::DrawItemOnHeader(
             this,
             0,
             0,
             L"{00062004-0000-0000-C000-000000000046}",
             0x8084001F,
             0,
             0xFAu,
             0x187u,
             SysColor,
             0x189u,
             0x188u,
             0,
             0x18Au,
             0);
      if ( v5 < 0 )
        goto LABEL_26;
      v5 = CMapiPreviewer::DrawItemOnHeader(
             this,
             0xD2u,
             0x3A09001Fu,
             0,
             0,
             1,
             0xFAu,
             0x191u,
             SysColor,
             0x193u,
             0x192u,
             v3,
             0x194u,
             0);
      if ( v5 < 0 )
        goto LABEL_26;
      v5 = CMapiPreviewer::DrawItemOnHeader(
             this,
             0xD3u,
             0x3A08001Fu,
             0,
             0,
             1,
             0xFAu,
             0x19Bu,
             SysColor,
             0x19Du,
             0x19Cu,
             v3,
             0x19Eu,
             0);
      if ( v5 < 0 )
        goto LABEL_26;
      v6 = 423;
      v7 = 212;
      v8 = 974913567;
      v9 = 421;
      v10 = 422;
      v11 = 424;
      goto LABEL_23;
    }
    if ( v4 != 7 )
    {
      v5 = -2147418113;
LABEL_26:
      for ( i = 0; i < *((_DWORD *)this + 298); ++i )
      {
        v14 = 56LL * i;
        v15 = *(HWND *)((char *)this + v14 + 296);
        if ( v15 )
        {
          DestroyWindow(v15);
          *(_QWORD *)((char *)this + v14 + 296) = 0;
        }
        v16 = *(void **)((char *)this + v14 + 304);
        if ( v16 )
        {
          DeleteObject(v16);
          *(_QWORD *)((char *)this + v14 + 304) = 0;
        }
        v17 = *(void **)((char *)this + v14 + 320);
        if ( v17 )
        {
          DeleteObject(v17);
          *(_QWORD *)((char *)this + v14 + 320) = 0;
        }
        ATL::CSimpleStringT<wchar_t,0>::SetString((char *)this + v14 + 312, &lParam, 0);
      }
      *((_QWORD *)this + 149) = 0;
      return (unsigned int)v5;
    }
  }
  v5 = CMapiPreviewer::DrawItemOnHeader(
         this,
         0,
         0x37001Fu,
         0,
         0,
         0,
         0xFAu,
         0x141u,
         SysColor,
         0x143u,
         0x142u,
         0,
         0x144u,
         0);
  if ( v5 < 0 )
    goto LABEL_26;
  v5 = CMapiPreviewer::DrawItemOnHeader(
         this,
         0xCEu,
         0xC1A001Fu,
         0,
         0,
         0,
         0xFAu,
         0x14Bu,
         SysColor,
         0x14Du,
         0x14Cu,
         v3,
         0x14Eu,
         0);
  if ( v5 < 0 )
    goto LABEL_26;
  v5 = CMapiPreviewer::DrawItemOnHeader(
         this,
         0xCFu,
         0xE04001Fu,
         0,
         0,
         1,
         0xFAu,
         0x155u,
         SysColor,
         0x157u,
         0x156u,
         v3,
         0x158u,
         0);
  if ( v5 < 0 )
    goto LABEL_26;
  v5 = CMapiPreviewer::DrawItemOnHeader(
         this,
         0xD0u,
         0xE03001Fu,
         0,
         0,
         1,
         0xFAu,
         0x15Fu,
         SysColor,
         0x161u,
         0x160u,
         v3,
         0x162u,
         0);
  if ( v5 < 0 )
    goto LABEL_26;
  v5 = CMapiPreviewer::DrawItemOnHeader(this, 0xD5u, 0, 0, 0, 1, 0xFAu, 0x169u, SysColor, 0x16Bu, 0x16Au, v3, 0x16Cu, 1);
  if ( v5 < 0 )
    goto LABEL_26;
  v7 = 209;
  v10 = 372;
  v8 = 6291520;
  v6 = 373;
  v9 = 371;
  v11 = 374;
LABEL_23:
  v5 = CMapiPreviewer::DrawItemOnHeader(this, v7, v8, 0, 0, 1, 0xFAu, v9, SysColor, v6, v10, v3, v11, 0);
  if ( v5 < 0 )
    goto LABEL_26;
  v12 = *((_DWORD *)this + 299);
  if ( v12 )
    *((_DWORD *)this + 299) = v12 + 5;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180023304  push    rbx
0x180023306  push    rbp
0x180023307  push    rsi
0x180023308  push    rdi
0x180023309  push    r12
0x18002330b  push    r13
0x18002330d  push    r14
0x18002330f  push    r15
0x180023311  sub     rsp, 78h
0x180023315  xor     r13d, r13d
0x180023318  mov     rbx, rcx
0x18002331b  mov     [rcx+4A8h], r13
0x180023322  lea     ecx, [r13+8]; nIndex
0x180023326  call    cs:__imp_GetSysColor
0x18002332c  lea     ecx, [r13+11h]; nIndex
0x180023330  mov     ebp, eax
0x180023332  call    cs:__imp_GetSysColor
0x180023338  mov     r14d, eax
0x18002333b  lea     r15d, [r13+1]
0x18002333f  mov     eax, [rbx+0E0h]
0x180023345  test    eax, eax
0x180023347  jz      loc_1800236E1
0x18002334d  cmp     eax, 2
0x180023350  jz      loc_1800234FF
0x180023356  cmp     eax, 5
0x180023359  jz      short loc_18002336E
0x18002335b  cmp     eax, 7
0x18002335e  jz      loc_1800236E1
0x180023364  mov     edi, 8000FFFFh
0x180023369  jmp     loc_18002391E
0x18002336e  mov     [rsp+0B8h+var_50], r13d; int
0x180023373  mov     esi, 0FAh
0x180023378  mov     [rsp+0B8h+var_58], 180h; unsigned int
0x180023380  xor     r9d, r9d; wchar_t *
0x180023383  mov     [rsp+0B8h+var_60], r13d; unsigned int
0x180023388  xor     edx, edx; unsigned int
0x18002338a  mov     [rsp+0B8h+var_68], 17Eh; unsigned int
0x180023392  mov     r8d, 3001001Fh; unsigned int
0x180023398  mov     [rsp+0B8h+var_70], 17Fh; unsigned int
0x1800233a0  mov     rcx, rbx; this
0x1800233a3  mov     [rsp+0B8h+var_78], ebp; unsigned int
0x1800233a7  mov     [rsp+0B8h+var_80], 17Dh; unsigned int
0x1800233af  mov     [rsp+0B8h+var_88], esi; unsigned int
0x1800233b3  mov     [rsp+0B8h+var_90], r13d; int
0x1800233b8  mov     [rsp+0B8h+var_98], r13d; unsigned int
0x1800233bd  call    ?DrawItemOnHeader@CMapiPreviewer@@AEAAJKKPEB_WKHKKKKKKKH@Z; CMapiPreviewer::DrawItemOnHeader(ulong,ulong,wchar_t const *,ulong,int,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int)
0x1800233c2  mov     edi, eax
0x1800233c4  test    eax, eax
0x1800233c6  js      loc_18002391E
0x1800233cc  mov     [rsp+0B8h+var_50], r13d; int
0x1800233d1  lea     r9, a00062004000000; "{00062004-0000-0000-C000-000000000046}"
0x1800233d8  mov     [rsp+0B8h+var_58], 18Ah; unsigned int
0x1800233e0  xor     r8d, r8d; unsigned int
0x1800233e3  mov     [rsp+0B8h+var_60], r13d; unsigned int
0x1800233e8  xor     edx, edx; unsigned int
0x1800233ea  mov     [rsp+0B8h+var_68], 188h; unsigned int
0x1800233f2  mov     rcx, rbx; this
0x1800233f5  mov     [rsp+0B8h+var_70], 189h; unsigned int
0x1800233fd  mov     [rsp+0B8h+var_78], ebp; unsigned int
0x180023401  mov     [rsp+0B8h+var_80], 187h; unsigned int
0x180023409  mov     [rsp+0B8h+var_88], esi; unsigned int
0x18002340d  mov     [rsp+0B8h+var_90], r13d; int
0x180023412  mov     [rsp+0B8h+var_98], 8084001Fh; unsigned int
0x18002341a  call    ?DrawItemOnHeader@CMapiPreviewer@@AEAAJKKPEB_WKHKKKKKKKH@Z; CMapiPreviewer::DrawItemOnHeader(ulong,ulong,wchar_t const *,ulong,int,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int)
0x18002341f  mov     edi, eax
0x180023421  test    eax, eax
0x180023423  js      loc_18002391E
0x180023429  mov     [rsp+0B8h+var_50], r13d; int
0x18002342e  lea     edx, [rsi-28h]; unsigned int
0x180023431  mov     [rsp+0B8h+var_58], 194h; unsigned int
0x180023439  xor     r9d, r9d; wchar_t *
0x18002343c  mov     [rsp+0B8h+var_60], r14d; unsigned int
0x180023441  mov     r8d, 3A09001Fh; unsigned int
0x180023447  mov     [rsp+0B8h+var_68], 192h; unsigned int
0x18002344f  mov     rcx, rbx; this
0x180023452  mov     [rsp+0B8h+var_70], 193h; unsigned int
0x18002345a  mov     [rsp+0B8h+var_78], ebp; unsigned int
0x18002345e  mov     [rsp+0B8h+var_80], 191h; unsigned int
0x180023466  mov     [rsp+0B8h+var_88], esi; unsigned int
0x18002346a  mov     [rsp+0B8h+var_90], r15d; int
0x18002346f  mov     [rsp+0B8h+var_98], r13d; unsigned int
0x180023474  call    ?DrawItemOnHeader@CMapiPreviewer@@AEAAJKKPEB_WKHKKKKKKKH@Z; CMapiPreviewer::DrawItemOnHeader(ulong,ulong,wchar_t const *,ulong,int,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int)
0x180023479  mov     edi, eax
0x18002347b  test    eax, eax
0x18002347d  js      loc_18002391E
0x180023483  mov     [rsp+0B8h+var_50], r13d; int
0x180023488  lea     edx, [rsi-27h]; unsigned int
0x18002348b  mov     [rsp+0B8h+var_58], 19Eh; unsigned int
0x180023493  xor     r9d, r9d; wchar_t *
0x180023496  mov     [rsp+0B8h+var_60], r14d; unsigned int
0x18002349b  mov     r8d, 3A08001Fh; unsigned int
0x1800234a1  mov     [rsp+0B8h+var_68], 19Ch; unsigned int
0x1800234a9  mov     rcx, rbx; this
0x1800234ac  mov     [rsp+0B8h+var_70], 19Dh; unsigned int
0x1800234b4  mov     [rsp+0B8h+var_78], ebp; unsigned int
0x1800234b8  mov     [rsp+0B8h+var_80], 19Bh; unsigned int
0x1800234c0  mov     [rsp+0B8h+var_88], esi; unsigned int
0x1800234c4  mov     [rsp+0B8h+var_90], r15d; int
0x1800234c9  mov     [rsp+0B8h+var_98], r13d; unsigned int
0x1800234ce  call    ?DrawItemOnHeader@CMapiPreviewer@@AEAAJKKPEB_WKHKKKKKKKH@Z; CMapiPreviewer::DrawItemOnHeader(ulong,ulong,wchar_t const *,ulong,int,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int)
0x1800234d3  mov     edi, eax
0x1800234d5  test    eax, eax
0x1800234d7  js      loc_18002391E
0x1800234dd  mov     edi, 1A7h
0x1800234e2  lea     edx, [rsi-26h]
0x1800234e5  mov     r10d, r15d
0x1800234e8  mov     r8d, 3A1C001Fh
0x1800234ee  lea     r11d, [rdi-2]
0x1800234f2  lea     r15d, [rdi-1]
0x1800234f6  lea     r12d, [rdi+1]
0x1800234fa  jmp     loc_1800238BB
0x1800234ff  mov     [rsp+0B8h+var_50], r13d; int
0x180023504  mov     esi, 0FAh
0x180023509  mov     [rsp+0B8h+var_58], 108h; unsigned int
0x180023511  xor     r9d, r9d; wchar_t *
0x180023514  mov     [rsp+0B8h+var_60], r13d; unsigned int
0x180023519  xor     edx, edx; unsigned int
0x18002351b  mov     [rsp+0B8h+var_68], 106h; unsigned int
0x180023523  mov     r8d, 37001Fh; unsigned int
0x180023529  mov     [rsp+0B8h+var_70], 107h; unsigned int
0x180023531  mov     rcx, rbx; this
0x180023534  mov     [rsp+0B8h+var_78], ebp; unsigned int
0x180023538  mov     [rsp+0B8h+var_80], 105h; unsigned int
0x180023540  mov     [rsp+0B8h+var_88], esi; unsigned int
0x180023544  mov     [rsp+0B8h+var_90], r13d; int
0x180023549  mov     [rsp+0B8h+var_98], r13d; unsigned int
0x18002354e  call    ?DrawItemOnHeader@CMapiPreviewer@@AEAAJKKPEB_WKHKKKKKKKH@Z; CMapiPreviewer::DrawItemOnHeader(ulong,ulong,wchar_t const *,ulong,int,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int)
0x180023553  mov     edi, eax
0x180023555  test    eax, eax
0x180023557  js      loc_18002391E
0x18002355d  mov     [rsp+0B8h+var_50], r13d; int
0x180023562  xor     r9d, r9d; wchar_t *
0x180023565  mov     [rsp+0B8h+var_58], 112h; unsigned int
0x18002356d  xor     edx, edx; unsigned int
0x18002356f  mov     [rsp+0B8h+var_60], r13d; unsigned int
0x180023574  mov     r8d, 0C1A001Fh; unsigned int
0x18002357a  mov     [rsp+0B8h+var_68], 110h; unsigned int
0x180023582  mov     rcx, rbx; this
0x180023585  mov     [rsp+0B8h+var_70], 111h; unsigned int
0x18002358d  mov     [rsp+0B8h+var_78], ebp; unsigned int
0x180023591  mov     [rsp+0B8h+var_80], 10Fh; unsigned int
0x180023599  mov     [rsp+0B8h+var_88], esi; unsigned int
0x18002359d  mov     [rsp+0B8h+var_90], r13d; int
0x1800235a2  mov     [rsp+0B8h+var_98], r13d; unsigned int
0x1800235a7  call    ?DrawItemOnHeader@CMapiPreviewer@@AEAAJKKPEB_WKHKKKKKKKH@Z; CMapiPreviewer::DrawItemOnHeader(ulong,ulong,wchar_t const *,ulong,int,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int)
0x1800235ac  mov     edi, eax
0x1800235ae  test    eax, eax
0x1800235b0  js      loc_18002391E
0x1800235b6  mov     [rsp+0B8h+var_50], r13d; int
0x1800235bb  lea     edx, [rsi-31h]; unsigned int
0x1800235be  mov     [rsp+0B8h+var_58], 11Ch; unsigned int
0x1800235c6  xor     r9d, r9d; wchar_t *
0x1800235c9  mov     [rsp+0B8h+var_60], r14d; unsigned int
0x1800235ce  mov     r8d, 0E04001Fh; unsigned int
0x1800235d4  mov     [rsp+0B8h+var_68], 11Ah; unsigned int
0x1800235dc  mov     rcx, rbx; this
0x1800235df  mov     [rsp+0B8h+var_70], 11Bh; unsigned int
0x1800235e7  mov     [rsp+0B8h+var_78], ebp; unsigned int
0x1800235eb  mov     [rsp+0B8h+var_80], 119h; unsigned int
0x1800235f3  mov     [rsp+0B8h+var_88], esi; unsigned int
0x1800235f7  mov     [rsp+0B8h+var_90], r13d; int
0x1800235fc  mov     [rsp+0B8h+var_98], r13d; unsigned int
0x180023601  call    ?DrawItemOnHeader@CMapiPreviewer@@AEAAJKKPEB_WKHKKKKKKKH@Z; CMapiPreviewer::DrawItemOnHeader(ulong,ulong,wchar_t const *,ulong,int,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int)
0x180023606  mov     edi, eax
0x180023608  test    eax, eax
0x18002360a  js      loc_18002391E
0x180023610  mov     [rsp+0B8h+var_50], r13d; int
0x180023615  lea     edx, [rsi-30h]; unsigned int
0x180023618  mov     [rsp+0B8h+var_58], 126h; unsigned int
0x180023620  xor     r9d, r9d; wchar_t *
0x180023623  mov     [rsp+0B8h+var_60], r14d; unsigned int
0x180023628  mov     r8d, 0E03001Fh; unsigned int
0x18002362e  mov     [rsp+0B8h+var_68], 124h; unsigned int
0x180023636  mov     rcx, rbx; this
0x180023639  mov     [rsp+0B8h+var_70], 125h; unsigned int
0x180023641  mov     [rsp+0B8h+var_78], ebp; unsigned int
0x180023645  mov     [rsp+0B8h+var_80], 123h; unsigned int
0x18002364d  mov     [rsp+0B8h+var_88], esi; unsigned int
0x180023651  mov     [rsp+0B8h+var_90], r15d; int
0x180023656  mov     [rsp+0B8h+var_98], r13d; unsigned int
0x18002365b  call    ?DrawItemOnHeader@CMapiPreviewer@@AEAAJKKPEB_WKHKKKKKKKH@Z; CMapiPreviewer::DrawItemOnHeader(ulong,ulong,wchar_t const *,ulong,int,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int)
0x180023660  mov     edi, eax
0x180023662  test    eax, eax
0x180023664  js      loc_18002391E
0x18002366a  mov     [rsp+0B8h+var_50], r15d; int
0x18002366f  lea     edx, [rsi-25h]; unsigned int
0x180023672  mov     [rsp+0B8h+var_58], 130h; unsigned int
0x18002367a  xor     r9d, r9d; wchar_t *
0x18002367d  mov     [rsp+0B8h+var_60], r14d; unsigned int
0x180023682  xor     r8d, r8d; unsigned int
0x180023685  mov     [rsp+0B8h+var_68], 12Eh; unsigned int
0x18002368d  mov     rcx, rbx; this
0x180023690  mov     [rsp+0B8h+var_70], 12Fh; unsigned int
0x180023698  mov     [rsp+0B8h+var_78], ebp; unsigned int
0x18002369c  mov     [rsp+0B8h+var_80], 12Dh; unsigned int
0x1800236a4  mov     [rsp+0B8h+var_88], esi; unsigned int
0x1800236a8  mov     [rsp+0B8h+var_90], r15d; int
0x1800236ad  mov     [rsp+0B8h+var_98], r13d; unsigned int
0x1800236b2  call    ?DrawItemOnHeader@CMapiPreviewer@@AEAAJKKPEB_WKHKKKKKKKH@Z; CMapiPreviewer::DrawItemOnHeader(ulong,ulong,wchar_t const *,ulong,int,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int)
0x1800236b7  mov     edi, eax
0x1800236b9  test    eax, eax
0x1800236bb  js      loc_18002391E
0x1800236c1  mov     r10d, r15d
0x1800236c4  lea     edx, [rsi-2Dh]
0x1800236c7  lea     r15d, [rsi+3Eh]
0x1800236cb  mov     r8d, 0E060040h
0x1800236d1  lea     edi, [rsi+3Fh]
0x1800236d4  lea     r11d, [rsi+3Dh]
0x1800236d8  lea     r12d, [rsi+40h]
0x1800236dc  jmp     loc_1800238BB
0x1800236e1  mov     [rsp+0B8h+var_50], r13d; int
0x1800236e6  mov     esi, 0FAh
0x1800236eb  mov     [rsp+0B8h+var_58], 144h; unsigned int
0x1800236f3  xor     r9d, r9d; wchar_t *
0x1800236f6  mov     [rsp+0B8h+var_60], r13d; unsigned int
0x1800236fb  xor     edx, edx; unsigned int
0x1800236fd  mov     [rsp+0B8h+var_68], 142h; unsigned int
0x180023705  mov     r8d, 37001Fh; unsigned int
0x18002370b  mov     [rsp+0B8h+var_70], 143h; unsigned int
0x180023713  mov     rcx, rbx; this
0x180023716  mov     [rsp+0B8h+var_78], ebp; unsigned int
0x18002371a  mov     [rsp+0B8h+var_80], 141h; unsigned int
0x180023722  mov     [rsp+0B8h+var_88], esi; unsigned int
0x180023726  mov     [rsp+0B8h+var_90], r13d; int
0x18002372b  mov     [rsp+0B8h+var_98], r13d; unsigned int
0x180023730  call    ?DrawItemOnHeader@CMapiPreviewer@@AEAAJKKPEB_WKHKKKKKKKH@Z; CMapiPreviewer::DrawItemOnHeader(ulong,ulong,wchar_t const *,ulong,int,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int)
0x180023735  mov     edi, eax
0x180023737  test    eax, eax
0x180023739  js      loc_18002391E
0x18002373f  mov     [rsp+0B8h+var_50], r13d; int
0x180023744  lea     edx, [rsi-2Ch]; unsigned int
0x180023747  mov     [rsp+0B8h+var_58], 14Eh; unsigned int
0x18002374f  xor     r9d, r9d; wchar_t *
0x180023752  mov     [rsp+0B8h+var_60], r14d; unsigned int
0x180023757  mov     r8d, 0C1A001Fh; unsigned int
0x18002375d  mov     [rsp+0B8h+var_68], 14Ch; unsigned int
0x180023765  mov     rcx, rbx; this
0x180023768  mov     [rsp+0B8h+var_70], 14Dh; unsigned int
0x180023770  mov     [rsp+0B8h+var_78], ebp; unsigned int
0x180023774  mov     [rsp+0B8h+var_80], 14Bh; unsigned int
0x18002377c  mov     [rsp+0B8h+var_88], esi; unsigned int
0x180023780  mov     [rsp+0B8h+var_90], r13d; int
0x180023785  mov     [rsp+0B8h+var_98], r13d; unsigned int
0x18002378a  call    ?DrawItemOnHeader@CMapiPreviewer@@AEAAJKKPEB_WKHKKKKKKKH@Z; CMapiPreviewer::DrawItemOnHeader(ulong,ulong,wchar_t const *,ulong,int,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int)
0x18002378f  mov     edi, eax
0x180023791  test    eax, eax
0x180023793  js      loc_18002391E
0x180023799  mov     [rsp+0B8h+var_50], r13d; int
0x18002379e  lea     edx, [rsi-2Bh]; unsigned int
0x1800237a1  mov     [rsp+0B8h+var_58], 158h; unsigned int
0x1800237a9  xor     r9d, r9d; wchar_t *
0x1800237ac  mov     [rsp+0B8h+var_60], r14d; unsigned int
0x1800237b1  mov     r8d, 0E04001Fh; unsigned int
0x1800237b7  mov     [rsp+0B8h+var_68], 156h; unsigned int
0x1800237bf  mov     rcx, rbx; this
0x1800237c2  mov     [rsp+0B8h+var_70], 157h; unsigned int
0x1800237ca  mov     [rsp+0B8h+var_78], ebp; unsigned int
0x1800237ce  mov     [rsp+0B8h+var_80], 155h; unsigned int
0x1800237d6  mov     [rsp+0B8h+var_88], esi; unsigned int
0x1800237da  mov     [rsp+0B8h+var_90], r15d; int
0x1800237df  mov     [rsp+0B8h+var_98], r13d; unsigned int
0x1800237e4  call    ?DrawItemOnHeader@CMapiPreviewer@@AEAAJKKPEB_WKHKKKKKKKH@Z; CMapiPreviewer::DrawItemOnHeader(ulong,ulong,wchar_t const *,ulong,int,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int)
0x1800237e9  mov     edi, eax
0x1800237eb  test    eax, eax
0x1800237ed  js      loc_18002391E
0x1800237f3  mov     [rsp+0B8h+var_50], r13d; int
0x1800237f8  lea     edx, [rsi-2Ah]; unsigned int
0x1800237fb  mov     [rsp+0B8h+var_58], 162h; unsigned int
0x180023803  xor     r9d, r9d; wchar_t *
0x180023806  mov     [rsp+0B8h+var_60], r14d; unsigned int
0x18002380b  mov     r8d, 0E03001Fh; unsigned int
0x180023811  mov     [rsp+0B8h+var_68], 160h; unsigned int
0x180023819  mov     rcx, rbx; this
0x18002381c  mov     [rsp+0B8h+var_70], 161h; unsigned int
0x180023824  mov     [rsp+0B8h+var_78], ebp; unsigned int
0x180023828  mov     [rsp+0B8h+var_80], 15Fh; unsigned int
0x180023830  mov     [rsp+0B8h+var_88], esi; unsigned int
0x180023834  mov     [rsp+0B8h+var_90], r15d; int
0x180023839  mov     [rsp+0B8h+var_98], r13d; unsigned int
0x18002383e  call    ?DrawItemOnHeader@CMapiPreviewer@@AEAAJKKPEB_WKHKKKKKKKH@Z; CMapiPreviewer::DrawItemOnHeader(ulong,ulong,wchar_t const *,ulong,int,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int)
0x180023843  mov     edi, eax
0x180023845  test    eax, eax
0x180023847  js      loc_18002391E
0x18002384d  mov     [rsp+0B8h+var_50], r15d; int
0x180023852  lea     edx, [rsi-25h]; unsigned int
0x180023855  mov     [rsp+0B8h+var_58], 16Ch; unsigned int
0x18002385d  xor     r9d, r9d; wchar_t *
0x180023860  mov     [rsp+0B8h+var_60], r14d; unsigned int
0x180023865  xor     r8d, r8d; unsigned int
0x180023868  mov     [rsp+0B8h+var_68], 16Ah; unsigned int
0x180023870  mov     rcx, rbx; this
0x180023873  mov     [rsp+0B8h+var_70], 16Bh; unsigned int
0x18002387b  mov     [rsp+0B8h+var_78], ebp; unsigned int
0x18002387f  mov     [rsp+0B8h+var_80], 169h; unsigned int
0x180023887  mov     [rsp+0B8h+var_88], esi; unsigned int
0x18002388b  mov     [rsp+0B8h+var_90], r15d; int
0x180023890  mov     [rsp+0B8h+var_98], r13d; unsigned int
0x180023895  call    ?DrawItemOnHeader@CMapiPreviewer@@AEAAJKKPEB_WKHKKKKKKKH@Z; CMapiPreviewer::DrawItemOnHeader(ulong,ulong,wchar_t const *,ulong,int,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int)
0x18002389a  mov     edi, eax
0x18002389c  test    eax, eax
  ... truncated ...
```
