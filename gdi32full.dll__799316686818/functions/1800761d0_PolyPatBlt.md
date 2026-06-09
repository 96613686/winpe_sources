# PolyPatBlt

- ea: `0x1800761d0`
- end: `0x18007658f`
- name: `PolyPatBlt`
- size: `959`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, DWORD rop@<edx>, void *Src@<r8>, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800710c4`
- `0x180075e30`
- `0x1800761d0`
- `0x1800a3010`
- `0x1800a3514`

## import_xrefs

- `GDI32!SelectObject` at `0x18007651a`
- `GDI32!SelectObject` at `0x180076532`
- `GDI32!SelectObject` at `0x180076575`
- `GDI32!SelectObject` at `0x18007651a`
- `GDI32!SelectObject` at `0x180076532`
- `GDI32!SelectObject` at `0x180076575`
- `GDI32!GdiGetEntry` at `0x18007621b`
- `GDI32!GdiGetEntry` at `0x18007621b`
- `GDI32!GdiBatchLimit` at `0x1800764c1`
- `GDI32!gW32PID` at `0x180076247`
- `GDI32!gCookie` at `0x180076263`
- `GDI32!gMaxGdiHandleCount` at `0x1800761fc`
- `USER32!IsThreadDesktopComposited` at `0x1800762fe`
- `USER32!IsThreadDesktopComposited` at `0x1800762fe`
- `win32u!NtGdiFlush` at `0x1800764dc`
- `win32u!NtGdiFlush` at `0x1800764dc`
- `win32u!NtGdiPolyPatBlt` at `0x1800764fb`
- `win32u!NtGdiPolyPatBlt` at `0x1800764fb`

## pseudocode

```c
__int64 __fastcall PolyPatBlt(HDC hdc, DWORD rop, HGDIOBJ *Src, unsigned int a4, int a5)
{
  __int64 v5; // r14
  unsigned int v9; // r13d
  unsigned int v10; // eax
  __int64 v11; // rdi
  unsigned __int16 v12; // bp
  struct _TEB *v13; // rbx
  HDC v14; // rax
  __int64 v15; // r12
  ULONG Offset; // eax
  int v17; // ecx
  HGDIOBJ v18; // rbp
  __int64 v19; // rbx
  __int64 v20; // rdi
  __int128 v22; // [rsp+30h] [rbp-68h] BYREF
  __int64 v23; // [rsp+40h] [rbp-58h]

  v5 = a4;
  v9 = 0;
  v10 = HANDLE_TO_INDEX(hdc);
  v11 = 0;
  if ( v10 < gMaxGdiHandleCount )
  {
    v22 = 0;
    v23 = 0;
    if ( (int)GdiGetEntry(v10, &v22) >= 0
      && BYTE14(v22) == 1
      && WORD6(v22) == WORD1(hdc)
      && (DWORD2(v22) & 0xFFFFFFFE) == gW32PID
      && v23 )
    {
      v11 = gCookie ^ __ROR8__(v23, 64 - (gCookie & 0x3Fu));
    }
  }
  if ( ((unsigned int)hdc & 0x7F0000) != 0x10000 || v11 && (*(_BYTE *)(v11 + 240) & 3) != 0 )
  {
    v18 = 0;
    v19 = 0;
    if ( (_DWORD)v5 )
    {
      do
      {
        if ( (_DWORD)v19 )
        {
          v20 = (unsigned int)v19;
          SelectObject(hdc, Src[3 * v19 + 2]);
        }
        else
        {
          v18 = SelectObject(hdc, Src[2]);
          v20 = 0;
        }
        v19 = (unsigned int)(v19 + 1);
        v9 = PatBlt(
               hdc,
               (int)Src[3 * v20],
               HIDWORD(Src[3 * v20]),
               (int)Src[3 * v20 + 1],
               HIDWORD(Src[3 * v20 + 1]),
               rop);
      }
      while ( (unsigned int)v19 < (unsigned int)v5 );
      if ( v18 )
        SelectObject(hdc, v18);
    }
  }
  else
  {
    LODWORD(NtCurrentTeb()->Win32ClientInfo[1]) = 0;
    if ( (_DWORD)v5 && Src && !a5 )
    {
      if ( (unsigned int)v5 > 0xAAA )
        return (unsigned int)NtGdiPolyPatBlt(hdc, rop, Src, (unsigned int)v5, 0);
      v12 = 24 * v5 + 56;
      if ( (unsigned __int16)(24 * v5) >= 0xFFC8u )
        return (unsigned int)NtGdiPolyPatBlt(hdc, rop, Src, (unsigned int)v5, 0);
      if ( (unsigned int)IsThreadDesktopComposited() )
        return (unsigned int)NtGdiPolyPatBlt(hdc, rop, Src, (unsigned int)v5, 0);
      v13 = NtCurrentTeb();
      v14 = (HDC)v13->GdiTebBatch.HDC;
      if ( v14 )
      {
        if ( v14 != hdc )
          return (unsigned int)NtGdiPolyPatBlt(hdc, rop, Src, (unsigned int)v5, 0);
      }
      if ( v12 > 0x4D8u )
        return (unsigned int)NtGdiPolyPatBlt(hdc, rop, Src, (unsigned int)v5, 0);
      if ( v12 + (v13->GdiTebBatch.Offset & 0x3FFFFFFF) > 0x4D8 )
        return (unsigned int)NtGdiPolyPatBlt(hdc, rop, Src, (unsigned int)v5, 0);
      if ( !v11 )
        return (unsigned int)NtGdiPolyPatBlt(hdc, rop, Src, (unsigned int)v5, 0);
      v9 = 1;
      if ( (*(_BYTE *)v11 & 1) != 0 )
      {
        return (unsigned int)NtGdiPolyPatBlt(hdc, rop, Src, (unsigned int)v5, 0);
      }
      else
      {
        if ( (v13->GdiTebBatch.Offset & 0x40000000) != 0 )
          TraceLoggingGdiBatchInProcessing(1);
        v15 = v13->GdiTebBatch.Offset & 0x3FFFFFFF;
        *(_WORD *)((char *)v13->GdiTebBatch.Buffer + v15 + 2) = 1;
        *(_WORD *)((char *)v13->GdiTebBatch.Buffer + v15) = (24 * v5 + 63) & 0xFFF8;
        *(_DWORD *)(v11 + 152) |= 0x200000u;
        *(ULONG *)((char *)&v13->GdiTebBatch.Buffer[1] + v15) = rop;
        *(ULONG *)((char *)&v13->GdiTebBatch.Buffer[3] + v15) = v5;
        *(ULONG *)((char *)&v13->GdiTebBatch.Buffer[2] + v15) = 0;
        *(ULONG *)((char *)&v13->GdiTebBatch.Buffer[4] + v15) = *(_DWORD *)(v11 + 184);
        *(ULONG *)((char *)&v13->GdiTebBatch.Buffer[5] + v15) = *(_DWORD *)(v11 + 176);
        *(ULONG *)((char *)&v13->GdiTebBatch.Buffer[6] + v15) = *(_DWORD *)(v11 + 192);
        *(_QWORD *)((char *)&v13->GdiTebBatch.Buffer[10] + v15) = *(_QWORD *)(v11 + 324);
        *(ULONG *)((char *)&v13->GdiTebBatch.Buffer[7] + v15) = *(_DWORD *)(v11 + 188);
        *(ULONG *)((char *)&v13->GdiTebBatch.Buffer[8] + v15) = *(_DWORD *)(v11 + 180);
        *(ULONG *)((char *)&v13->GdiTebBatch.Buffer[9] + v15) = *(_DWORD *)(v11 + 196);
        memcpy_0((char *)&v13->GdiTebBatch.Buffer[12] + v15, Src, 24 * v5);
        if ( !*(_QWORD *)((char *)&v13->GdiTebBatch.Buffer[16] + v15) )
          *(_QWORD *)((char *)&v13->GdiTebBatch.Buffer[16] + v15) = *(_QWORD *)(v11 + 160);
        if ( hdc )
        {
          v13->GdiTebBatch.HDC = hdc;
          if ( !*(_WORD *)((char *)v13->GdiTebBatch.Buffer + v15 + 2)
            || *(_WORD *)((char *)v13->GdiTebBatch.Buffer + v15 + 2) == 1
            || (unsigned int)*(unsigned __int16 *)((char *)v13->GdiTebBatch.Buffer + v15 + 2) - 2 <= 1 )
          {
            v13->GdiTebBatch.Offset |= 0x80000000;
          }
        }
        Offset = v13->GdiTebBatch.Offset;
        v17 = *(unsigned __int16 *)((char *)v13->GdiTebBatch.Buffer + v15);
        ++v13->GdiBatchCount;
        v13->GdiTebBatch.Offset = Offset ^ (Offset ^ (Offset + ((v17 + 7) & 0xFFFFFFF8))) & 0x3FFFFFFF;
        if ( v13->GdiBatchCount >= GdiBatchLimit )
          NtGdiFlush();
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1800761d0  mov     [rsp+arg_8], edx
0x1800761d4  push    rbx
0x1800761d5  push    rbp
0x1800761d6  push    rsi
0x1800761d7  push    rdi
0x1800761d8  push    r12
0x1800761da  push    r13
0x1800761dc  push    r14
0x1800761de  push    r15
0x1800761e0  sub     rsp, 58h
0x1800761e4  mov     r14d, r9d
0x1800761e7  mov     r15, r8
0x1800761ea  mov     r12d, edx
0x1800761ed  mov     rsi, rcx
0x1800761f0  xor     r13d, r13d
0x1800761f3  call    HANDLE_TO_INDEX
0x1800761f8  mov     ecx, eax
0x1800761fa  xor     edi, edi
0x1800761fc  mov     rax, cs:__imp_gMaxGdiHandleCount
0x180076203  cmp     ecx, [rax]
0x180076205  jnb     short loc_180076280
0x180076207  xorps   xmm0, xmm0
0x18007620a  lea     rdx, [rsp+98h+var_68]
0x18007620f  xor     eax, eax
0x180076211  movups  [rsp+98h+var_68], xmm0
0x180076216  mov     [rsp+98h+var_58], rax
0x18007621b  call    cs:__imp_GdiGetEntry
0x180076221  test    eax, eax
0x180076223  js      short loc_180076280
0x180076225  cmp     byte ptr [rsp+98h+var_68+0Eh], 1
0x18007622a  jnz     short loc_180076280
0x18007622c  movzx   eax, byte ptr [rsp+98h+var_68+0Ch]
0x180076231  movzx   ecx, byte ptr [rsp+98h+var_68+0Dh]
0x180076236  shl     cx, 8
0x18007623a  or      cx, ax
0x18007623d  mov     eax, esi
0x18007623f  shr     eax, 10h
0x180076242  cmp     cx, ax
0x180076245  jnz     short loc_180076280
0x180076247  mov     rax, cs:__imp_gW32PID
0x18007624e  mov     ecx, dword ptr [rsp+98h+var_68+8]
0x180076252  and     ecx, 0FFFFFFFEh
0x180076255  cmp     ecx, [rax]
0x180076257  jnz     short loc_180076280
0x180076259  mov     r8, [rsp+98h+var_58]
0x18007625e  test    r8, r8
0x180076261  jz      short loc_180076280
0x180076263  mov     rax, cs:__imp_gCookie
0x18007626a  lea     ecx, [rdi+40h]
0x18007626d  mov     rdi, r8
0x180076270  mov     rdx, [rax]
0x180076273  mov     eax, edx
0x180076275  and     eax, 3Fh
0x180076278  sub     ecx, eax
0x18007627a  ror     rdi, cl
0x18007627d  xor     rdi, rdx
0x180076280  mov     eax, esi
0x180076282  and     eax, 7F0000h
0x180076287  cmp     eax, 10000h
0x18007628c  jnz     loc_180076506
0x180076292  test    rdi, rdi
0x180076295  jz      short loc_1800762A4
0x180076297  test    byte ptr [rdi+0F0h], 3
0x18007629e  jnz     loc_180076506
0x1800762a4  mov     rax, gs:30h
0x1800762ad  mov     [rax+808h], r13d
0x1800762b4  test    r14d, r14d
0x1800762b7  jz      loc_18007657B
0x1800762bd  test    r15, r15
0x1800762c0  jz      loc_18007657B
0x1800762c6  cmp     [rsp+98h+arg_20], r13d
0x1800762ce  jnz     loc_18007657B
0x1800762d4  cmp     r14d, 0AAAh
0x1800762db  ja      loc_1800764E7
0x1800762e1  movzx   eax, r14w
0x1800762e5  add     ax, ax
0x1800762e8  lea     ebp, [rax+r14]
0x1800762ec  shl     bp, 3
0x1800762f0  add     bp, 38h ; '8'
0x1800762f4  cmp     bp, 38h ; '8'
0x1800762f8  jb      loc_1800764E7
0x1800762fe  call    cs:__imp_IsThreadDesktopComposited
0x180076304  test    eax, eax
0x180076306  jnz     loc_1800764E7
0x18007630c  mov     rbx, gs:30h
0x180076315  mov     rax, [rbx+2F8h]
0x18007631c  test    rax, rax
0x18007631f  jz      short loc_18007632A
0x180076321  cmp     rax, rsi
0x180076324  jnz     loc_1800764E7
0x18007632a  mov     r8d, 4D8h
0x180076330  cmp     bp, r8w
0x180076334  ja      loc_1800764E7
0x18007633a  mov     edx, [rbx+2F0h]
0x180076340  mov     ecx, edx
0x180076342  and     ecx, 3FFFFFFFh
0x180076348  movzx   eax, bp
0x18007634b  add     ecx, eax
0x18007634d  cmp     ecx, r8d
0x180076350  ja      loc_1800764E7
0x180076356  test    rdi, rdi
0x180076359  jz      loc_1800764E7
0x18007635f  mov     r13d, 1
0x180076365  test    [rdi], r13b
0x180076368  jnz     loc_1800764E7
0x18007636e  bt      edx, 1Eh
0x180076372  jnb     short loc_18007637C
0x180076374  mov     ecx, r13d
0x180076377  call    TraceLoggingGdiBatchInProcessing
0x18007637c  mov     r12d, [rbx+2F0h]
0x180076383  lea     r8, [r14+r14*2]
0x180076387  and     r12d, 3FFFFFFFh
0x18007638e  shl     r8, 3; Size
0x180076392  mov     eax, 0FFF8h
0x180076397  lea     rcx, [rbx+330h]
0x18007639e  add     bp, 7
0x1800763a2  add     rcx, r12; void *
0x1800763a5  and     bp, ax
0x1800763a8  mov     rdx, r15; Src
0x1800763ab  mov     eax, [rsp+98h+arg_8]
0x1800763b2  mov     [r12+rbx+302h], r13w
0x1800763bb  mov     [r12+rbx+300h], bp
0x1800763c4  bts     dword ptr [rdi+98h], 15h
0x1800763cc  mov     [r12+rbx+304h], eax
0x1800763d4  mov     [r12+rbx+30Ch], r14d
0x1800763dc  mov     dword ptr [r12+rbx+308h], 0
0x1800763e8  mov     eax, [rdi+0B8h]
0x1800763ee  mov     [r12+rbx+310h], eax
0x1800763f6  mov     eax, [rdi+0B0h]
0x1800763fc  mov     [r12+rbx+314h], eax
0x180076404  mov     eax, [rdi+0C0h]
0x18007640a  mov     [r12+rbx+318h], eax
0x180076412  mov     rax, [rdi+144h]
0x180076419  mov     [r12+rbx+328h], rax
0x180076421  mov     eax, [rdi+0BCh]
0x180076427  mov     [r12+rbx+31Ch], eax
0x18007642f  mov     eax, [rdi+0B4h]
0x180076435  mov     [r12+rbx+320h], eax
0x18007643d  mov     eax, [rdi+0C4h]
0x180076443  mov     [r12+rbx+324h], eax
0x18007644b  call    memcpy_0
0x180076450  cmp     qword ptr [r12+rbx+340h], 0
0x180076459  jnz     short loc_18007646A
0x18007645b  mov     rax, [rdi+0A0h]
0x180076462  mov     [r12+rbx+340h], rax
0x18007646a  test    rsi, rsi
0x18007646d  jz      short loc_18007649A
0x18007646f  mov     [rbx+2F8h], rsi
0x180076476  movzx   ecx, word ptr [r12+rbx+302h]
0x18007647f  test    ecx, ecx
0x180076481  jz      short loc_180076492
0x180076483  sub     ecx, r13d
0x180076486  jz      short loc_180076492
0x180076488  sub     ecx, r13d
0x18007648b  jz      short loc_180076492
0x18007648d  cmp     ecx, r13d
0x180076490  jnz     short loc_18007649A
0x180076492  bts     dword ptr [rbx+2F0h], 1Fh
0x18007649a  mov     eax, [rbx+2F0h]
0x1800764a0  movzx   ecx, word ptr [r12+rbx+300h]
0x1800764a9  inc     dword ptr [rbx+1740h]
0x1800764af  add     ecx, 7
0x1800764b2  and     ecx, 0FFFFFFF8h
0x1800764b5  add     ecx, eax
0x1800764b7  xor     ecx, eax
0x1800764b9  and     ecx, 3FFFFFFFh
0x1800764bf  xor     ecx, eax
0x1800764c1  mov     rax, cs:__imp_GdiBatchLimit
0x1800764c8  mov     [rbx+2F0h], ecx
0x1800764ce  mov     ecx, [rbx+1740h]
0x1800764d4  cmp     ecx, [rax]
0x1800764d6  jb      loc_18007657B
0x1800764dc  call    cs:__imp_NtGdiFlush
0x1800764e2  jmp     loc_18007657B
0x1800764e7  mov     r9d, r14d
0x1800764ea  mov     [rsp+98h+h], 0
0x1800764f2  mov     r8, r15
0x1800764f5  mov     edx, r12d
0x1800764f8  mov     rcx, rsi
0x1800764fb  call    cs:__imp_NtGdiPolyPatBlt
0x180076501  mov     r13d, eax
0x180076504  jmp     short loc_18007657B
0x180076506  xor     ebp, ebp
0x180076508  xor     ebx, ebx
0x18007650a  test    r14d, r14d
0x18007650d  jz      short loc_18007657B
0x18007650f  mov     rcx, rsi; hdc
0x180076512  test    ebx, ebx
0x180076514  jnz     short loc_180076527
0x180076516  mov     rdx, [r15+10h]; h
0x18007651a  call    cs:__imp_SelectObject
0x180076520  mov     rbp, rax
0x180076523  xor     edi, edi
0x180076525  jmp     short loc_180076538
0x180076527  lea     rdx, [rbx+rbx*2]
0x18007652b  mov     edi, ebx
0x18007652d  mov     rdx, [r15+rdx*8+10h]; h
0x180076532  call    cs:__imp_SelectObject
0x180076538  lea     rdx, [rdi+rdi*2]
0x18007653c  mov     [rsp+98h+rop], r12d; rop
0x180076541  mov     eax, [r15+rdx*8+0Ch]
0x180076546  mov     rcx, rsi; hdc
0x180076549  mov     r9d, [r15+rdx*8+8]; w
0x18007654e  mov     r8d, [r15+rdx*8+4]; y
0x180076553  mov     edx, [r15+rdx*8]; x
0x180076557  mov     [rsp+98h+h], eax; h
0x18007655b  call    PatBlt
0x180076560  inc     ebx
0x180076562  mov     r13d, eax
0x180076565  cmp     ebx, r14d
0x180076568  jb      short loc_18007650F
0x18007656a  test    rbp, rbp
0x18007656d  jz      short loc_18007657B
0x18007656f  mov     rdx, rbp; h
0x180076572  mov     rcx, rsi; hdc
0x180076575  call    cs:__imp_SelectObject
0x18007657b  mov     eax, r13d
0x18007657e  add     rsp, 58h
0x180076582  pop     r15
0x180076584  pop     r14
0x180076586  pop     r13
0x180076588  pop     r12
0x18007658a  pop     rdi
0x18007658b  pop     rsi
0x18007658c  pop     rbp
0x18007658d  pop     rbx
0x18007658e  retn
```
