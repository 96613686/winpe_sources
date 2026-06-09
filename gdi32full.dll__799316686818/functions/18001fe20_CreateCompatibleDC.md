# CreateCompatibleDC

- ea: `0x18001fe20`
- end: `0x18001fefe`
- name: `CreateCompatibleDC`
- size: `222`
- prototype: `HDC __stdcall(HDC hdc)`
- caller_count: `13`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011fc0`
- `0x180014710`
- `0x180015190`
- `0x180015700`
- `0x18001de14`
- `0x18001e870`
- `0x18001f0a0`
- `0x180020a00`
- `0x18003bd30`
- `0x1800400d0`
- `0x180051bac`
- `0x1800566ac`
- `0x180059230`

## callees

- `0x18001fe20`
- `0x180026cf0`
- `0x1800710c4`
- `0x180088cd4`

## import_xrefs

- `GDI32!GdiGetEntry` at `0x18001fe75`
- `GDI32!GdiGetEntry` at `0x18001fe75`
- `GDI32!gW32PID` at `0x18001fe9f`
- `GDI32!gCookie` at `0x18001febb`
- `GDI32!gMaxGdiHandleCount` at `0x18001fe50`
- `win32u!NtGdiCreateCompatibleDC` at `0x18001fe2d`
- `win32u!NtGdiCreateCompatibleDC` at `0x18001fe2d`

## pseudocode

```c
HDC __stdcall CreateCompatibleDC(HDC hdc)
{
  __int64 CompatibleDC; // rax
  const BITMAPINFOHEADER *v3; // rdx
  DWORD v4; // r8d
  const void *v5; // r9
  HDC v6; // rdi
  unsigned int v7; // eax
  __int128 v9; // [rsp+20h] [rbp-28h] BYREF
  const BITMAPINFOHEADER *v10; // [rsp+30h] [rbp-18h]
  const BITMAPINFO *v11; // [rsp+70h] [rbp+28h]
  UINT v12; // [rsp+78h] [rbp+30h]

  CompatibleDC = NtGdiCreateCompatibleDC();
  v6 = (HDC)CompatibleDC;
  if ( hdc )
  {
    if ( CompatibleDC )
    {
      v7 = HANDLE_TO_INDEX(hdc);
      if ( v7 < gMaxGdiHandleCount )
      {
        v10 = 0;
        v9 = 0;
        if ( (int)GdiGetEntry(v7, &v9) >= 0
          && BYTE14(v9) == 1
          && WORD6(v9) == WORD1(hdc)
          && (DWORD2(v9) & 0xFFFFFFFE) == gW32PID )
        {
          v3 = v10;
          if ( v10 )
          {
            v3 = (const BITMAPINFOHEADER *)__ROR8__(v10, 64 - (gCookie & 0x3Fu));
            v4 = (unsigned int)v3 ^ gCookie;
            if ( (unsigned __int64)v3 != gCookie )
            {
              if ( *(_QWORD *)(((unsigned __int64)v3 ^ gCookie) + 0x108) )
                IcmEnableForCompatibleDC(v6);
            }
          }
        }
      }
    }
  }
  return (HDC)GdiTrackHCreate(v6, v3, v4, v5, v11, v12);
}

```

## disassembly

```asm
0x18001fe20  mov     [rsp+arg_0], rbx
0x18001fe25  push    rdi
0x18001fe26  sub     rsp, 40h
0x18001fe2a  mov     rbx, rcx
0x18001fe2d  call    cs:__imp_NtGdiCreateCompatibleDC
0x18001fe33  mov     rdi, rax
0x18001fe36  test    rbx, rbx
0x18001fe39  jz      loc_18001FEEC
0x18001fe3f  test    rax, rax
0x18001fe42  jz      loc_18001FEEC
0x18001fe48  mov     rcx, rbx
0x18001fe4b  call    HANDLE_TO_INDEX
0x18001fe50  mov     rcx, cs:__imp_gMaxGdiHandleCount
0x18001fe57  cmp     eax, [rcx]
0x18001fe59  jnb     loc_18001FEEC
0x18001fe5f  xor     ecx, ecx
0x18001fe61  lea     rdx, [rsp+48h+var_28]
0x18001fe66  mov     [rsp+48h+var_18], rcx
0x18001fe6b  xorps   xmm0, xmm0
0x18001fe6e  mov     ecx, eax
0x18001fe70  movups  [rsp+48h+var_28], xmm0
0x18001fe75  call    cs:__imp_GdiGetEntry
0x18001fe7b  test    eax, eax
0x18001fe7d  js      short loc_18001FEEC
0x18001fe7f  cmp     byte ptr [rsp+48h+var_28+0Eh], 1
0x18001fe84  jnz     short loc_18001FEEC
0x18001fe86  movzx   ecx, byte ptr [rsp+48h+var_28+0Dh]
0x18001fe8b  movzx   eax, byte ptr [rsp+48h+var_28+0Ch]
0x18001fe90  shl     cx, 8
0x18001fe94  or      cx, ax
0x18001fe97  shr     ebx, 10h
0x18001fe9a  cmp     cx, bx
0x18001fe9d  jnz     short loc_18001FEEC
0x18001fe9f  mov     rax, cs:__imp_gW32PID
0x18001fea6  mov     ecx, dword ptr [rsp+48h+var_28+8]
0x18001feaa  and     ecx, 0FFFFFFFEh
0x18001fead  cmp     ecx, [rax]
0x18001feaf  jnz     short loc_18001FEEC
0x18001feb1  mov     rdx, [rsp+48h+var_18]
0x18001feb6  test    rdx, rdx
0x18001feb9  jz      short loc_18001FEEC
0x18001febb  mov     rax, cs:__imp_gCookie
0x18001fec2  mov     ecx, 40h ; '@'
0x18001fec7  mov     r8, [rax]
0x18001feca  mov     eax, r8d
0x18001fecd  and     eax, 3Fh
0x18001fed0  sub     ecx, eax
0x18001fed2  ror     rdx, cl
0x18001fed5  xor     r8, rdx
0x18001fed8  jz      short loc_18001FEEC
0x18001feda  cmp     qword ptr [r8+108h], 0
0x18001fee2  jz      short loc_18001FEEC
0x18001fee4  mov     rcx, rdi
0x18001fee7  call    IcmEnableForCompatibleDC
0x18001feec  mov     rcx, rdi
0x18001feef  mov     rbx, [rsp+48h+arg_0]
0x18001fef4  add     rsp, 40h
0x18001fef8  pop     rdi
0x18001fef9  jmp     GdiTrackHCreate
```
