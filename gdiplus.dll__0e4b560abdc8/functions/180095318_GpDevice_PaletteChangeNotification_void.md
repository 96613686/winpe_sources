# GpDevice::PaletteChangeNotification(void)

- ea: `0x180095318`
- end: `0x1800954ea`
- name: `?PaletteChangeNotification@GpDevice@@QEAAXXZ`
- size: `466`
- prototype: `void __fastcall(GpDevice *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180094c5c`
- `0x180094f84`
- `0x180102b18`
- `0x180136430`

## callees

- `0x180095318`
- `0x1800e5044`
- `0x1800e9380`
- `0x1800ea0ec`

## import_xrefs

- `GDI32!SetDIBColorTable` at `0x1800954b5`
- `GDI32!SetDIBColorTable` at `0x1800954b5`
- `GDI32!GetDeviceCaps` at `0x180095356`
- `GDI32!GetDeviceCaps` at `0x180095370`
- `GDI32!GetDeviceCaps` at `0x180095394`
- `GDI32!GetDeviceCaps` at `0x180095356`
- `GDI32!GetDeviceCaps` at `0x180095370`
- `GDI32!GetDeviceCaps` at `0x180095394`
- `GDI32!GetSystemPaletteEntries` at `0x180095406`
- `GDI32!GetSystemPaletteEntries` at `0x180095406`

## pseudocode

```c
void __fastcall GpDevice::PaletteChangeNotification(HDC *this)
{
  char DeviceCaps; // bl
  signed int v3; // esi
  __int64 v4; // rax
  __int64 i; // r9
  struct tagPALETTEENTRY *v6; // r8
  HDC v7; // rcx
  struct tagPALETTEENTRY pPalEntries[256]; // [rsp+28h] [rbp-E0h] BYREF
  RGBQUAD prgbq[256]; // [rsp+428h] [rbp+320h] BYREF

  DeviceCaps = GetDeviceCaps(this[188], 14);
  v3 = 1 << (GetDeviceCaps(this[188], 12) * DeviceCaps);
  if ( GetDeviceCaps(this[188], 2) == 1 && v3 <= 256 )
  {
    if ( this[197] || (v4 = GpMallocEx(1036, 0), (this[197] = (HDC)v4) != 0) )
    {
      pPalEntries[0].peRed = 0;
      memset_0(&pPalEntries[0].peGreen, 0, 0x3FFu);
      GetSystemPaletteEntries(this[188], 0, 0x100u, pPalEntries);
      *((_DWORD *)this[197] + 1) = v3;
      if ( v3 > 0 )
      {
        for ( i = 0; i < v3; prgbq[i++].rgbReserved = 0 )
        {
          v6 = &pPalEntries[i];
          *(_DWORD *)((char *)this[197] + (_QWORD)v6 + 8LL - (_QWORD)pPalEntries) = pPalEntries[i].peBlue
                                                                                  | ((pPalEntries[i].peGreen
                                                                                    | ((v6->peRed | 0xFFFFFF00) << 8)) << 8);
          prgbq[i].rgbRed = v6->peRed;
          prgbq[i].rgbGreen = pPalEntries[i].peGreen;
          prgbq[i].rgbBlue = pPalEntries[i].peBlue;
        }
      }
      v7 = this[3];
      if ( v7 )
        SetDIBColorTable(v7, 0, v3, prgbq);
    }
  }
}

```

## disassembly

```asm
0x180095318  mov     rax, rsp
0x18009531b  mov     [rax+10h], rbx
0x18009531f  mov     [rax+18h], rsi
0x180095323  mov     [rax+20h], rdi
0x180095327  push    rbp
0x180095328  lea     rbp, [rax-738h]
0x18009532f  sub     rsp, 830h
0x180095336  mov     rax, cs:__security_cookie
0x18009533d  xor     rax, rsp
0x180095340  mov     [rbp+730h+var_10], rax
0x180095347  mov     rdi, rcx
0x18009534a  mov     edx, 0Eh; index
0x18009534f  mov     rcx, [rcx+5E0h]; hdc
0x180095356  call    cs:__imp_GetDeviceCaps
0x18009535d  nop     dword ptr [rax+rax+00h]
0x180095362  mov     rcx, [rdi+5E0h]; hdc
0x180095369  mov     edx, 0Ch; index
0x18009536e  mov     ebx, eax
0x180095370  call    cs:__imp_GetDeviceCaps
0x180095377  nop     dword ptr [rax+rax+00h]
0x18009537c  imul    ebx, eax
0x18009537f  mov     esi, 1
0x180095384  mov     edx, 2; index
0x180095389  mov     cl, bl
0x18009538b  shl     esi, cl
0x18009538d  mov     rcx, [rdi+5E0h]; hdc
0x180095394  call    cs:__imp_GetDeviceCaps
0x18009539b  nop     dword ptr [rax+rax+00h]
0x1800953a0  cmp     eax, 1
0x1800953a3  jnz     loc_1800954C1
0x1800953a9  cmp     esi, 100h
0x1800953af  jg      loc_1800954C1
0x1800953b5  xor     ebx, ebx
0x1800953b7  cmp     [rdi+628h], rbx
0x1800953be  jnz     short loc_1800953DC
0x1800953c0  xor     edx, edx
0x1800953c2  mov     ecx, 40Ch
0x1800953c7  call    GpMallocEx
0x1800953cc  mov     [rdi+628h], rax
0x1800953d3  test    rax, rax
0x1800953d6  jz      loc_1800954C1
0x1800953dc  xor     edx, edx; Val
0x1800953de  mov     [rsp+830h+pPalEntries.peRed], bl
0x1800953e2  mov     r8d, 3FFh; Size
0x1800953e8  lea     rcx, [rsp+830h+pPalEntries.peGreen]; void *
0x1800953ed  call    memset_0
0x1800953f2  mov     rcx, [rdi+5E0h]; hdc
0x1800953f9  lea     r9, [rsp+830h+pPalEntries]; pPalEntries
0x1800953fe  xor     edx, edx; iStart
0x180095400  mov     r8d, 100h; cEntries
0x180095406  call    cs:__imp_GetSystemPaletteEntries
0x18009540d  nop     dword ptr [rax+rax+00h]
0x180095412  mov     rax, [rdi+628h]
0x180095419  movsxd  r11, esi
0x18009541c  mov     [rax+4], esi
0x18009541f  test    esi, esi
0x180095421  jle     short loc_1800954A0
0x180095423  lea     rax, [rsp+830h+pPalEntries]
0x180095428  mov     r10d, 8
0x18009542e  sub     r10, rax
0x180095431  mov     r9, rbx
0x180095434  movzx   eax, [rsp+r9*4+830h+pPalEntries.peGreen]
0x18009543a  lea     r8, [rsp+830h+pPalEntries]
0x18009543f  lea     r8, [r8+r9*4]
0x180095443  movzx   edx, byte ptr [r8]
0x180095447  lea     rcx, [r8+r10]
0x18009544b  or      edx, 0FFFFFF00h
0x180095451  shl     edx, 8
0x180095454  or      edx, eax
0x180095456  movzx   eax, [rsp+r9*4+830h+pPalEntries.peBlue]
0x18009545c  shl     edx, 8
0x18009545f  or      edx, eax
0x180095461  mov     rax, [rdi+628h]
0x180095468  mov     [rcx+rax], edx
0x18009546b  mov     al, [r8]
0x18009546e  mov     [rbp+r9*4+730h+prgbq.rgbRed], al
0x180095476  mov     al, [rsp+r9*4+830h+pPalEntries.peGreen]
0x18009547b  mov     [rbp+r9*4+730h+prgbq.rgbGreen], al
0x180095483  mov     al, [rsp+r9*4+830h+pPalEntries.peBlue]
0x180095488  mov     [rbp+r9*4+730h+prgbq.rgbBlue], al
0x180095490  mov     [rbp+r9*4+730h+prgbq.rgbReserved], bl
0x180095498  inc     r9
0x18009549b  cmp     r9, r11
0x18009549e  jl      short loc_180095434
0x1800954a0  mov     rcx, [rdi+18h]; hdc
0x1800954a4  test    rcx, rcx
0x1800954a7  jz      short loc_1800954C1
0x1800954a9  lea     r9, [rbp+730h+prgbq]; prgbq
0x1800954b0  mov     r8d, esi; cEntries
0x1800954b3  xor     edx, edx; iStart
0x1800954b5  call    cs:__imp_SetDIBColorTable
0x1800954bc  nop     dword ptr [rax+rax+00h]
0x1800954c1  mov     rcx, [rbp+730h+var_10]
0x1800954c8  xor     rcx, rsp; StackCookie
0x1800954cb  call    __security_check_cookie
0x1800954d0  lea     r11, [rsp+830h+var_s0]
0x1800954d8  mov     rbx, [r11+18h]
0x1800954dc  mov     rsi, [r11+20h]
0x1800954e0  mov     rdi, [r11+28h]
0x1800954e4  mov     rsp, r11
0x1800954e7  pop     rbp
0x1800954e8  retn
```
