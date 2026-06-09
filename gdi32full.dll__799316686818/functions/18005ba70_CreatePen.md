# CreatePen

- ea: `0x18005ba70`
- end: `0x18005bbaf`
- name: `CreatePen`
- size: `319`
- prototype: `HPEN __stdcall(int iStyle, int cWidth, COLORREF color)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180011fc0`
- `0x18003bd30`
- `0x18005b9a0`
- `0x18005ba50`
- `0x180074dc0`

## callees

- `0x180025090`
- `0x180026cf0`
- `0x18005ba70`
- `0x1800710c4`

## import_xrefs

- `GDI32!hGetPEBHandle` at `0x18005bac6`
- `GDI32!hGetPEBHandle` at `0x18005bac6`
- `GDI32!GdiGetEntry` at `0x18005bb05`
- `GDI32!GdiGetEntry` at `0x18005bb05`
- `GDI32!gW32PID` at `0x18005bb31`
- `GDI32!gCookie` at `0x18005bb4d`
- `GDI32!gMaxGdiHandleCount` at `0x18005bae0`
- `GDI32!DeleteObject` at `0x18005bb88`
- `GDI32!DeleteObject` at `0x18005bb88`
- `win32u!NtGdiCreatePen` at `0x18005bb98`
- `win32u!NtGdiCreatePen` at `0x18005bb98`

## pseudocode

```c
HPEN __stdcall CreatePen(int iStyle, int cWidth, COLORREF color)
{
  unsigned int v5; // edi
  __int64 v6; // r9
  __int64 PEBHandle; // rax
  void *v8; // rbx
  unsigned int v9; // eax
  __int64 v10; // r8
  __int64 Pen; // rcx
  __int128 v13; // [rsp+20h] [rbp-48h] BYREF
  __int64 v14; // [rsp+30h] [rbp-38h]

  v5 = iStyle;
  v6 = (unsigned int)iStyle;
  if ( iStyle )
  {
    v6 = (unsigned int)(iStyle - 1);
    if ( iStyle != 1 )
    {
      v6 = (unsigned int)(iStyle - 2);
      if ( iStyle != 2 )
      {
        v6 = (unsigned int)(iStyle - 3);
        if ( iStyle != 3 )
        {
          v6 = (unsigned int)(iStyle - 4);
          if ( iStyle != 4 )
          {
            v6 = (unsigned int)(iStyle - 5);
            if ( iStyle == 5 )
              return (HPEN)GetStockObject(8);
            if ( iStyle != 6 )
              v5 = 0;
          }
        }
      }
    }
  }
  if ( !cWidth && !v5 )
  {
    PEBHandle = hGetPEBHandle(1, 0, color, v6);
    v8 = (void *)PEBHandle;
    if ( PEBHandle )
    {
      v9 = HANDLE_TO_INDEX(PEBHandle);
      if ( v9 < gMaxGdiHandleCount )
      {
        v14 = 0;
        v13 = 0;
        if ( (int)GdiGetEntry(v9, &v13) >= 0
          && BYTE14(v13) == 16
          && WORD6(v13) == WORD1(v8)
          && (DWORD2(v13) & 0xFFFFFFFE) == gW32PID )
        {
          if ( v14 )
          {
            v10 = __ROR8__(v14, 64 - (gCookie & 0x3Fu));
            if ( v10 != gCookie )
            {
              if ( *(_DWORD *)((v10 ^ gCookie) + 4) != color )
              {
                *(_DWORD *)(v10 ^ gCookie) |= 4u;
                *(_DWORD *)((v10 ^ gCookie) + 4) = color;
              }
              Pen = (__int64)v8;
              return (HPEN)GdiTrackHCreate(Pen);
            }
          }
        }
      }
      DeleteObject(v8);
    }
  }
  Pen = NtGdiCreatePen(v5, (unsigned int)cWidth, color, 0);
  return (HPEN)GdiTrackHCreate(Pen);
}

```

## disassembly

```asm
0x18005ba70  push    rbx
0x18005ba72  push    rbp
0x18005ba73  push    rsi
0x18005ba74  push    rdi
0x18005ba75  sub     rsp, 48h
0x18005ba79  mov     esi, r8d
0x18005ba7c  mov     ebp, edx
0x18005ba7e  mov     edi, ecx
0x18005ba80  mov     r9d, ecx
0x18005ba83  test    ecx, ecx
0x18005ba85  jz      short loc_18005BAB1
0x18005ba87  sub     r9d, 1
0x18005ba8b  jz      short loc_18005BAB1
0x18005ba8d  sub     r9d, 1
0x18005ba91  jz      short loc_18005BAB1
0x18005ba93  sub     r9d, 1
0x18005ba97  jz      short loc_18005BAB1
0x18005ba99  sub     r9d, 1
0x18005ba9d  jz      short loc_18005BAB1
0x18005ba9f  sub     r9d, 1
0x18005baa3  jz      loc_18005BB79
0x18005baa9  cmp     r9d, 1
0x18005baad  jz      short loc_18005BAB1
0x18005baaf  xor     edi, edi
0x18005bab1  test    ebp, ebp
0x18005bab3  jnz     loc_18005BB8E
0x18005bab9  test    edi, edi
0x18005babb  jnz     loc_18005BB8E
0x18005bac1  xor     edx, edx
0x18005bac3  lea     ecx, [rbp+1]
0x18005bac6  call    cs:__imp_hGetPEBHandle
0x18005bacc  mov     rbx, rax
0x18005bacf  test    rax, rax
0x18005bad2  jz      loc_18005BB8E
0x18005bad8  mov     rcx, rax
0x18005badb  call    HANDLE_TO_INDEX
0x18005bae0  mov     rcx, cs:__imp_gMaxGdiHandleCount
0x18005bae7  cmp     eax, [rcx]
0x18005bae9  jnb     loc_18005BB85
0x18005baef  xor     ecx, ecx
0x18005baf1  lea     rdx, [rsp+68h+var_48]
0x18005baf6  mov     [rsp+68h+var_38], rcx
0x18005bafb  xorps   xmm0, xmm0
0x18005bafe  mov     ecx, eax
0x18005bb00  movups  [rsp+68h+var_48], xmm0
0x18005bb05  call    cs:__imp_GdiGetEntry
0x18005bb0b  test    eax, eax
0x18005bb0d  js      short loc_18005BB85
0x18005bb0f  cmp     byte ptr [rsp+68h+var_48+0Eh], 10h
0x18005bb14  jnz     short loc_18005BB85
0x18005bb16  movzx   eax, byte ptr [rsp+68h+var_48+0Ch]
0x18005bb1b  movzx   ecx, byte ptr [rsp+68h+var_48+0Dh]
0x18005bb20  shl     cx, 8
0x18005bb24  or      cx, ax
0x18005bb27  mov     eax, ebx
0x18005bb29  shr     eax, 10h
0x18005bb2c  cmp     cx, ax
0x18005bb2f  jnz     short loc_18005BB85
0x18005bb31  mov     rax, cs:__imp_gW32PID
0x18005bb38  mov     ecx, dword ptr [rsp+68h+var_48+8]
0x18005bb3c  and     ecx, 0FFFFFFFEh
0x18005bb3f  cmp     ecx, [rax]
0x18005bb41  jnz     short loc_18005BB85
0x18005bb43  mov     r8, [rsp+68h+var_38]
0x18005bb48  test    r8, r8
0x18005bb4b  jz      short loc_18005BB85
0x18005bb4d  mov     rax, cs:__imp_gCookie
0x18005bb54  lea     ecx, [rbp+40h]
0x18005bb57  mov     rdx, [rax]
0x18005bb5a  mov     eax, edx
0x18005bb5c  and     eax, 3Fh
0x18005bb5f  sub     ecx, eax
0x18005bb61  ror     r8, cl
0x18005bb64  xor     rdx, r8
0x18005bb67  jz      short loc_18005BB85
0x18005bb69  cmp     [rdx+4], esi
0x18005bb6c  jz      short loc_18005BB74
0x18005bb6e  or      dword ptr [rdx], 4
0x18005bb71  mov     [rdx+4], esi
0x18005bb74  mov     rcx, rbx
0x18005bb77  jmp     short loc_18005BBA1
0x18005bb79  mov     ecx, 8; i
0x18005bb7e  call    GetStockObject
0x18005bb83  jmp     short loc_18005BBA6
0x18005bb85  mov     rcx, rbx; ho
0x18005bb88  call    cs:__imp_DeleteObject
0x18005bb8e  xor     r9d, r9d
0x18005bb91  mov     r8d, esi
0x18005bb94  mov     edx, ebp
0x18005bb96  mov     ecx, edi
0x18005bb98  call    cs:__imp_NtGdiCreatePen
0x18005bb9e  mov     rcx, rax
0x18005bba1  call    GdiTrackHCreate
0x18005bba6  add     rsp, 48h
0x18005bbaa  pop     rdi
0x18005bbab  pop     rsi
0x18005bbac  pop     rbp
0x18005bbad  pop     rbx
0x18005bbae  retn
```
