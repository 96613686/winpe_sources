# SetDCBrushColor

- ea: `0x1800794c0`
- end: `0x1800796eb`
- name: `SetDCBrushColor`
- size: `555`
- prototype: `COLORREF __stdcall(HDC hdc, COLORREF color)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18004d7b0`
- `0x1800756cc`
- `0x1800794c0`
- `0x18008f324`
- `0x180092a2c`

## import_xrefs

- `GDI32!GdiGetEntry` at `0x180079502`
- `GDI32!GdiGetEntry` at `0x180079502`
- `GDI32!gW32PID` at `0x180079540`
- `GDI32!gCookie` at `0x180079564`
- `GDI32!gMaxGdiHandleCount` at `0x1800794dc`
- `GDI32!pldcGet` at `0x1800795a6`
- `GDI32!pldcGet` at `0x1800795a6`
- `GDI32!GdiSetLastError` at `0x1800796b0`
- `GDI32!GdiSetLastError` at `0x1800796c9`
- `GDI32!GdiSetLastError` at `0x1800796b0`
- `GDI32!GdiSetLastError` at `0x1800796c9`
- `GDI32!DeleteObject` at `0x180079607`
- `GDI32!DeleteObject` at `0x180079607`

## pseudocode

```c
COLORREF __stdcall SetDCBrushColor(HDC hdc, COLORREF color)
{
  unsigned int v4; // eax
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rdi
  HBRUSH SolidBrush; // r14
  void *v9; // rcx
  int v10; // eax
  COLORREF v11; // edi
  COLORREF v12; // esi
  __int128 v14; // [rsp+30h] [rbp-38h] BYREF
  __int64 v15; // [rsp+40h] [rbp-28h]
  COLORREF v16; // [rsp+80h] [rbp+18h] BYREF

  v4 = HANDLE_TO_INDEX(hdc);
  if ( v4 < gMaxGdiHandleCount )
  {
    v15 = 0;
    v14 = 0;
    if ( (int)GdiGetEntry(v4, &v14) >= 0
      && BYTE14(v14) == 1
      && WORD6(v14) == WORD1(hdc)
      && (DWORD2(v14) & 0xFFFFFFFE) == gW32PID )
    {
      if ( v15 )
      {
        v5 = __ROR8__(v15, 64 - (gCookie & 0x3Fu)) ^ gCookie;
        if ( v5 )
        {
          if ( ((unsigned int)hdc & 0x7F0000) != 0x10000 && ((unsigned int)hdc & 0x7F0000) != 0x660000 )
          {
            v6 = pldcGet(hdc);
            v7 = v6;
            if ( v6 )
            {
              if ( *(_DWORD *)(v6 + 12) != 2 )
                goto LABEL_20;
              if ( (color & 0xFFFFFF) != 0 && (color & 0xFFFFFF) != 0xFFFFFF )
                *(_DWORD *)(v6 + 8) |= 0x20000000u;
              if ( *(_QWORD *)(v5 + 160) != ghbrDCBrush )
                goto LABEL_20;
              SolidBrush = CreateSolidBrush(color);
              if ( SolidBrush )
              {
                v9 = *(void **)(v7 + 304);
                if ( v9 )
                  DeleteObject(v9);
                v10 = MF_SelectAnyObject(hdc, SolidBrush);
                *(_QWORD *)(v7 + 304) = SolidBrush;
                if ( v10 )
                  goto LABEL_20;
              }
            }
            else
            {
              GdiSetLastError(6);
            }
            return -1;
          }
LABEL_20:
          v11 = *(_DWORD *)(v5 + 196);
          *(_DWORD *)(v5 + 196) = color;
          v12 = color & 0x13FFFFFF;
          if ( (v12 & 0x1000000) == 0 && (*(_DWORD *)(v5 + 240) & 0x11) == 1 )
          {
            if ( *(_QWORD *)(v5 + 248) )
            {
              v16 = 0;
              if ( (unsigned int)IcmTranslateCOLORREF((_DWORD)hdc, v5, v12, (unsigned int)&v16, 1) )
                v12 = v16;
            }
          }
          if ( v12 != *(_DWORD *)(v5 + 192) )
          {
            *(_DWORD *)(v5 + 192) = v12;
            *(_DWORD *)(v5 + 152) |= 1u;
          }
          return v11;
        }
      }
    }
  }
  v11 = -1;
  GdiSetLastError(87);
  return v11;
}

```

## disassembly

```asm
0x1800794c0  mov     [rsp+arg_0], rbx
0x1800794c5  mov     [rsp+arg_8], rbp
0x1800794ca  push    rsi
0x1800794cb  push    rdi
0x1800794cc  push    r14
0x1800794ce  sub     rsp, 50h
0x1800794d2  mov     esi, edx
0x1800794d4  mov     rbp, rcx
0x1800794d7  call    HANDLE_TO_INDEX
0x1800794dc  mov     r8, cs:__imp_gMaxGdiHandleCount
0x1800794e3  cmp     eax, [r8]
0x1800794e6  jnb     loc_1800796C1
0x1800794ec  xor     ecx, ecx
0x1800794ee  lea     rdx, [rsp+68h+var_38]
0x1800794f3  mov     [rsp+68h+var_28], rcx
0x1800794f8  xorps   xmm0, xmm0
0x1800794fb  mov     ecx, eax
0x1800794fd  movups  [rsp+68h+var_38], xmm0
0x180079502  call    cs:__imp_GdiGetEntry
0x180079509  nop     dword ptr [rax+rax+00h]
0x18007950e  test    eax, eax
0x180079510  js      loc_1800796C1
0x180079516  cmp     byte ptr [rsp+68h+var_38+0Eh], 1
0x18007951b  jnz     loc_1800796C1
0x180079521  movzx   eax, byte ptr [rsp+68h+var_38+0Ch]
0x180079526  movzx   ecx, byte ptr [rsp+68h+var_38+0Dh]
0x18007952b  shl     cx, 8
0x18007952f  or      cx, ax
0x180079532  mov     eax, ebp
0x180079534  shr     eax, 10h
0x180079537  cmp     cx, ax
0x18007953a  jnz     loc_1800796C1
0x180079540  mov     rax, cs:__imp_gW32PID
0x180079547  mov     ecx, dword ptr [rsp+68h+var_38+8]
0x18007954b  and     ecx, 0FFFFFFFEh
0x18007954e  cmp     ecx, [rax]
0x180079550  jnz     loc_1800796C1
0x180079556  mov     rdx, [rsp+68h+var_28]
0x18007955b  test    rdx, rdx
0x18007955e  jz      loc_1800796C1
0x180079564  mov     rax, cs:__imp_gCookie
0x18007956b  mov     ecx, 40h ; '@'
0x180079570  mov     rbx, [rax]
0x180079573  mov     eax, ebx
0x180079575  and     eax, 3Fh
0x180079578  sub     ecx, eax
0x18007957a  ror     rdx, cl
0x18007957d  xor     rbx, rdx
0x180079580  jz      loc_1800796C1
0x180079586  mov     eax, ebp
0x180079588  and     eax, 7F0000h
0x18007958d  cmp     eax, 10000h
0x180079592  jz      loc_180079633
0x180079598  cmp     eax, 660000h
0x18007959d  jz      loc_180079633
0x1800795a3  mov     rcx, rbp
0x1800795a6  call    cs:__imp_pldcGet
0x1800795ad  nop     dword ptr [rax+rax+00h]
0x1800795b2  mov     rdi, rax
0x1800795b5  test    rax, rax
0x1800795b8  jz      loc_1800796AB
0x1800795be  cmp     dword ptr [rax+0Ch], 2
0x1800795c2  jnz     short loc_180079633
0x1800795c4  mov     eax, esi
0x1800795c6  mov     ecx, 0FFFFFFh
0x1800795cb  and     eax, ecx
0x1800795cd  jz      short loc_1800795D8
0x1800795cf  cmp     eax, ecx
0x1800795d1  jz      short loc_1800795D8
0x1800795d3  bts     dword ptr [rdi+8], 1Dh
0x1800795d8  mov     rax, cs:ghbrDCBrush
0x1800795df  cmp     [rbx+0A0h], rax
0x1800795e6  jnz     short loc_180079633
0x1800795e8  mov     ecx, esi; color
0x1800795ea  call    CreateSolidBrush
0x1800795ef  mov     r14, rax
0x1800795f2  test    rax, rax
0x1800795f5  jz      loc_1800796BC
0x1800795fb  mov     rcx, [rdi+130h]; ho
0x180079602  test    rcx, rcx
0x180079605  jz      short loc_180079613
0x180079607  call    cs:__imp_DeleteObject
0x18007960e  nop     dword ptr [rax+rax+00h]
0x180079613  mov     r8d, 25h ; '%'
0x180079619  mov     rdx, r14; void *
0x18007961c  mov     rcx, rbp; void *
0x18007961f  call    MF_SelectAnyObject
0x180079624  mov     [rdi+130h], r14
0x18007962b  test    eax, eax
0x18007962d  jz      loc_1800796BC
0x180079633  mov     edi, [rbx+0C4h]
0x180079639  mov     [rbx+0C4h], esi
0x18007963f  and     esi, 13FFFFFFh
0x180079645  bt      esi, 18h
0x180079649  jb      short loc_180079694
0x18007964b  mov     eax, [rbx+0F0h]
0x180079651  and     al, 11h
0x180079653  cmp     al, 1
0x180079655  jnz     short loc_180079694
0x180079657  cmp     qword ptr [rbx+0F8h], 0
0x18007965f  jz      short loc_180079694
0x180079661  lea     r9, [rsp+68h+arg_10]
0x180079669  mov     [rsp+68h+arg_10], 0
0x180079674  mov     r8d, esi
0x180079677  mov     [rsp+68h+var_48], 1
0x18007967f  mov     rdx, rbx
0x180079682  mov     rcx, rbp
0x180079685  call    IcmTranslateCOLORREF
0x18007968a  test    eax, eax
0x18007968c  cmovnz  esi, [rsp+68h+arg_10]
0x180079694  cmp     esi, [rbx+0C0h]
0x18007969a  jz      short loc_1800796D5
0x18007969c  mov     [rbx+0C0h], esi
0x1800796a2  or      dword ptr [rbx+98h], 1
0x1800796a9  jmp     short loc_1800796D5
0x1800796ab  mov     ecx, 6
0x1800796b0  call    cs:__imp_GdiSetLastError
0x1800796b7  nop     dword ptr [rax+rax+00h]
0x1800796bc  or      eax, 0FFFFFFFFh
0x1800796bf  jmp     short loc_1800796D7
0x1800796c1  or      edi, 0FFFFFFFFh
0x1800796c4  mov     ecx, 57h ; 'W'
0x1800796c9  call    cs:__imp_GdiSetLastError
0x1800796d0  nop     dword ptr [rax+rax+00h]
0x1800796d5  mov     eax, edi
0x1800796d7  mov     rbx, [rsp+68h+arg_0]
0x1800796dc  mov     rbp, [rsp+68h+arg_8]
0x1800796e1  add     rsp, 50h
0x1800796e5  pop     r14
0x1800796e7  pop     rdi
0x1800796e8  pop     rsi
0x1800796e9  retn
```
