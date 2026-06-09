# MF_ValidateArcDirection

- ea: `0x1800933b4`
- end: `0x18009358a`
- name: `MF_ValidateArcDirection`
- size: `470`
- prototype: `__int64 __fastcall(HDC hdc)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180028fe4`
- `0x180091540`
- `0x18009293c`

## callees

- `0x180018860`
- `0x18002ada0`
- `0x18002ade0`
- `0x18002bc14`
- `0x1800756cc`
- `0x1800933b4`

## import_xrefs

- `GDI32!GdiGetEntry` at `0x180093497`
- `GDI32!GdiGetEntry` at `0x180093497`
- `GDI32!gW32PID` at `0x1800934d1`
- `GDI32!gCookie` at `0x1800934ed`
- `GDI32!gMaxGdiHandleCount` at `0x180093472`
- `GDI32!pldcGet` at `0x1800933c4`
- `GDI32!pldcGet` at `0x1800933c4`
- `GDI32!GdiSetLastError` at `0x18009356e`
- `GDI32!GdiSetLastError` at `0x18009356e`
- `win32u!NtGdiUpdateTransform` at `0x18009351a`
- `win32u!NtGdiUpdateTransform` at `0x18009351a`

## pseudocode

```c
__int64 __fastcall MF_ValidateArcDirection(HDC hdc)
{
  __int64 v2; // rax
  __int64 v3; // rbp
  int v4; // r15d
  int DCDWord; // r14d
  int v6; // ebx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rsi
  __int128 v16; // [rsp+20h] [rbp-58h] BYREF
  __int64 v17; // [rsp+30h] [rbp-48h]

  v2 = pldcGet(hdc);
  v3 = v2;
  if ( !v2 || ((unsigned int)hdc & 0x7F0000) == 0x660000 )
  {
    GdiSetLastError(6);
    return 0;
  }
  v4 = (*(_DWORD *)(v2 + 8) >> 13) & 1;
  DCDWord = GetDCDWord(hdc, 4);
  v6 = DCDWord == 2;
  if ( GetGraphicsMode(hdc) != 1 )
    goto LABEL_21;
  v7 = GetMapMode(hdc) - 2;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            if ( (unsigned int)(v11 - 1) > 1 )
              goto LABEL_21;
            v12 = HANDLE_TO_INDEX(hdc);
            if ( v12 >= gMaxGdiHandleCount )
              goto LABEL_21;
            v17 = 0;
            v16 = 0;
            if ( (int)GdiGetEntry(v12, &v16) < 0 )
              goto LABEL_21;
            if ( BYTE14(v16) != 1 )
              goto LABEL_21;
            if ( WORD6(v16) != WORD1(hdc) )
              goto LABEL_21;
            if ( (DWORD2(v16) & 0xFFFFFFFE) != gW32PID )
              goto LABEL_21;
            if ( !v17 )
              goto LABEL_21;
            v13 = __ROR8__(v17, 64 - (gCookie & 0x3Fu));
            v14 = v13 ^ gCookie;
            if ( v13 == gCookie )
              goto LABEL_21;
            if ( (*(_DWORD *)((v13 ^ gCookie) + 0x154) & 0xE000) == 0 || (unsigned int)NtGdiUpdateTransform(hdc) )
            {
              if ( ((*(_DWORD *)(v14 + 340) ^ (*(_DWORD *)(v14 + 340) >> 1)) & 0x100) == 0 )
                goto LABEL_21;
              goto LABEL_20;
            }
            return 0;
          }
        }
      }
    }
  }
LABEL_20:
  v6 = DCDWord != 2;
LABEL_21:
  if ( v4 == v6 )
    return 1;
  *(_DWORD *)(v3 + 8) ^= 0x2000u;
  return MF_SetD(hdc, (unsigned int)(v6 + 1), 57);
}

```

## disassembly

```asm
0x1800933b4  push    rbx
0x1800933b6  push    rbp
0x1800933b7  push    rsi
0x1800933b8  push    rdi
0x1800933b9  push    r14
0x1800933bb  push    r15
0x1800933bd  sub     rsp, 48h
0x1800933c1  mov     rdi, rcx
0x1800933c4  call    cs:__imp_pldcGet
0x1800933cb  nop     dword ptr [rax+rax+00h]
0x1800933d0  mov     rbp, rax
0x1800933d3  test    rax, rax
0x1800933d6  jz      loc_180093569
0x1800933dc  mov     edx, edi
0x1800933de  and     edx, 7F0000h
0x1800933e4  cmp     edx, 660000h
0x1800933ea  jz      loc_180093569
0x1800933f0  mov     r15d, [rax+8]
0x1800933f4  xor     r8d, r8d
0x1800933f7  shr     r15d, 0Dh
0x1800933fb  mov     rcx, rdi
0x1800933fe  and     r15d, 1
0x180093402  lea     edx, [r8+4]
0x180093406  call    GetDCDWord
0x18009340b  xor     ebx, ebx
0x18009340d  mov     rcx, rdi; hdc
0x180093410  cmp     eax, 2
0x180093413  mov     r14d, eax
0x180093416  setz    bl
0x180093419  call    GetGraphicsMode
0x18009341e  cmp     eax, 1
0x180093421  jnz     loc_180093545
0x180093427  mov     rcx, rdi; hdc
0x18009342a  call    GetMapMode
0x18009342f  sub     eax, 2
0x180093432  jz      loc_18009353C
0x180093438  sub     eax, 1
0x18009343b  jz      loc_18009353C
0x180093441  sub     eax, 1
0x180093444  jz      loc_18009353C
0x18009344a  sub     eax, 1
0x18009344d  jz      loc_18009353C
0x180093453  sub     eax, 1
0x180093456  jz      loc_18009353C
0x18009345c  sub     eax, 1
0x18009345f  jz      short loc_18009346A
0x180093461  cmp     eax, 1
0x180093464  jnz     loc_180093545
0x18009346a  mov     rcx, rdi
0x18009346d  call    HANDLE_TO_INDEX
0x180093472  mov     rcx, cs:__imp_gMaxGdiHandleCount
0x180093479  cmp     eax, [rcx]
0x18009347b  jnb     loc_180093545
0x180093481  xor     ecx, ecx
0x180093483  lea     rdx, [rsp+78h+var_58]
0x180093488  mov     [rsp+78h+var_48], rcx
0x18009348d  xorps   xmm0, xmm0
0x180093490  mov     ecx, eax
0x180093492  movups  [rsp+78h+var_58], xmm0
0x180093497  call    cs:__imp_GdiGetEntry
0x18009349e  nop     dword ptr [rax+rax+00h]
0x1800934a3  test    eax, eax
0x1800934a5  js      loc_180093545
0x1800934ab  cmp     byte ptr [rsp+78h+var_58+0Eh], 1
0x1800934b0  jnz     loc_180093545
0x1800934b6  movzx   eax, byte ptr [rsp+78h+var_58+0Ch]
0x1800934bb  movzx   ecx, byte ptr [rsp+78h+var_58+0Dh]
0x1800934c0  shl     cx, 8
0x1800934c4  or      cx, ax
0x1800934c7  mov     eax, edi
0x1800934c9  shr     eax, 10h
0x1800934cc  cmp     cx, ax
0x1800934cf  jnz     short loc_180093545
0x1800934d1  mov     rax, cs:__imp_gW32PID
0x1800934d8  mov     ecx, dword ptr [rsp+78h+var_58+8]
0x1800934dc  and     ecx, 0FFFFFFFEh
0x1800934df  cmp     ecx, [rax]
0x1800934e1  jnz     short loc_180093545
0x1800934e3  mov     rdx, [rsp+78h+var_48]
0x1800934e8  test    rdx, rdx
0x1800934eb  jz      short loc_180093545
0x1800934ed  mov     rax, cs:__imp_gCookie
0x1800934f4  mov     ecx, 40h ; '@'
0x1800934f9  mov     rsi, [rax]
0x1800934fc  mov     eax, esi
0x1800934fe  and     eax, 3Fh
0x180093501  sub     ecx, eax
0x180093503  ror     rdx, cl
0x180093506  xor     rsi, rdx
0x180093509  jz      short loc_180093545
0x18009350b  test    dword ptr [rsi+154h], 0E000h
0x180093515  jz      short loc_18009352A
0x180093517  mov     rcx, rdi
0x18009351a  call    cs:__imp_NtGdiUpdateTransform
0x180093521  nop     dword ptr [rax+rax+00h]
0x180093526  test    eax, eax
0x180093528  jz      short loc_18009357A
0x18009352a  mov     eax, [rsi+154h]
0x180093530  mov     ecx, eax
0x180093532  shr     ecx, 1
0x180093534  xor     ecx, eax
0x180093536  bt      ecx, 8
0x18009353a  jnb     short loc_180093545
0x18009353c  xor     ebx, ebx
0x18009353e  cmp     r14d, 2
0x180093542  setnz   bl
0x180093545  cmp     r15d, ebx
0x180093548  jnz     short loc_180093551
0x18009354a  mov     eax, 1
0x18009354f  jmp     short loc_18009357C
0x180093551  btc     dword ptr [rbp+8], 0Dh
0x180093556  lea     edx, [rbx+1]
0x180093559  mov     r8d, 39h ; '9'
0x18009355f  mov     rcx, rdi
0x180093562  call    MF_SetD
0x180093567  jmp     short loc_18009357C
0x180093569  mov     ecx, 6
0x18009356e  call    cs:__imp_GdiSetLastError
0x180093575  nop     dword ptr [rax+rax+00h]
0x18009357a  xor     eax, eax
0x18009357c  add     rsp, 48h
0x180093580  pop     r15
0x180093582  pop     r14
0x180093584  pop     rdi
0x180093585  pop     rsi
0x180093586  pop     rbp
0x180093587  pop     rbx
0x180093588  retn
```
