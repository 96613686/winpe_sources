# CreateCompatibleDC

- ea: `0x1800200a0`
- end: `0x18002018a`
- name: `CreateCompatibleDC`
- size: `234`
- prototype: `HDC __stdcall(HDC hdc)`
- caller_count: `13`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800032a8`
- `0x18001eb10`
- `0x18001ede0`
- `0x180020a90`
- `0x1800215b0`
- `0x180021b90`
- `0x180024c40`
- `0x180029730`
- `0x180034f78`
- `0x1800479b0`
- `0x18004ac60`
- `0x180057710`
- `0x18005a5b4`

## callees

- `0x1800200a0`
- `0x18002fda0`
- `0x1800756cc`
- `0x18008e270`

## import_xrefs

- `GDI32!GdiGetEntry` at `0x1800200fb`
- `GDI32!GdiGetEntry` at `0x1800200fb`
- `GDI32!gW32PID` at `0x18002012b`
- `GDI32!gCookie` at `0x180020147`
- `GDI32!gMaxGdiHandleCount` at `0x1800200d6`
- `win32u!NtGdiCreateCompatibleDC` at `0x1800200ad`
- `win32u!NtGdiCreateCompatibleDC` at `0x1800200ad`

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
0x1800200a0  mov     [rsp+arg_0], rbx
0x1800200a5  push    rdi
0x1800200a6  sub     rsp, 40h
0x1800200aa  mov     rbx, rcx
0x1800200ad  call    cs:__imp_NtGdiCreateCompatibleDC
0x1800200b4  nop     dword ptr [rax+rax+00h]
0x1800200b9  mov     rdi, rax
0x1800200bc  test    rbx, rbx
0x1800200bf  jz      loc_180020178
0x1800200c5  test    rax, rax
0x1800200c8  jz      loc_180020178
0x1800200ce  mov     rcx, rbx
0x1800200d1  call    HANDLE_TO_INDEX
0x1800200d6  mov     rcx, cs:__imp_gMaxGdiHandleCount
0x1800200dd  cmp     eax, [rcx]
0x1800200df  jnb     loc_180020178
0x1800200e5  xor     ecx, ecx
0x1800200e7  lea     rdx, [rsp+48h+var_28]
0x1800200ec  mov     [rsp+48h+var_18], rcx
0x1800200f1  xorps   xmm0, xmm0
0x1800200f4  mov     ecx, eax
0x1800200f6  movups  [rsp+48h+var_28], xmm0
0x1800200fb  call    cs:__imp_GdiGetEntry
0x180020102  nop     dword ptr [rax+rax+00h]
0x180020107  test    eax, eax
0x180020109  js      short loc_180020178
0x18002010b  cmp     byte ptr [rsp+48h+var_28+0Eh], 1
0x180020110  jnz     short loc_180020178
0x180020112  movzx   ecx, byte ptr [rsp+48h+var_28+0Dh]
0x180020117  movzx   eax, byte ptr [rsp+48h+var_28+0Ch]
0x18002011c  shl     cx, 8
0x180020120  or      cx, ax
0x180020123  shr     ebx, 10h
0x180020126  cmp     cx, bx
0x180020129  jnz     short loc_180020178
0x18002012b  mov     rax, cs:__imp_gW32PID
0x180020132  mov     ecx, dword ptr [rsp+48h+var_28+8]
0x180020136  and     ecx, 0FFFFFFFEh
0x180020139  cmp     ecx, [rax]
0x18002013b  jnz     short loc_180020178
0x18002013d  mov     rdx, [rsp+48h+var_18]
0x180020142  test    rdx, rdx
0x180020145  jz      short loc_180020178
0x180020147  mov     rax, cs:__imp_gCookie
0x18002014e  mov     ecx, 40h ; '@'
0x180020153  mov     r8, [rax]
0x180020156  mov     eax, r8d
0x180020159  and     eax, 3Fh
0x18002015c  sub     ecx, eax
0x18002015e  ror     rdx, cl
0x180020161  xor     r8, rdx
0x180020164  jz      short loc_180020178
0x180020166  cmp     qword ptr [r8+108h], 0
0x18002016e  jz      short loc_180020178
0x180020170  mov     rcx, rdi
0x180020173  call    IcmEnableForCompatibleDC
0x180020178  mov     rcx, rdi
0x18002017b  mov     rbx, [rsp+48h+arg_0]
0x180020180  add     rsp, 40h
0x180020184  pop     rdi
0x180020185  jmp     GdiTrackHCreate
```
