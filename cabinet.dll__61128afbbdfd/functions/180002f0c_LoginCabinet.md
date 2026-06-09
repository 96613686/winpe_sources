# LoginCabinet

- ea: `0x180002f0c`
- end: `0x180003339`
- name: `LoginCabinet`
- size: `1069`
- prototype: `_BOOL8 __fastcall(__int64, __int64, size_t *, unsigned __int16)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18000254c`
- `0x1800048d0`

## callees

- `0x180002a64`
- `0x180002cfc`
- `0x180002f0c`
- `0x180004700`
- `0x180004be8`
- `0x180014dc0`
- `0x18001562a`
- `0x18001c010`

## pseudocode

```c
_BOOL8 __fastcall LoginCabinet(__int64 a1, __int64 a2, size_t *a3, unsigned __int16 a4)
{
  char *v5; // rsi
  unsigned __int16 v7; // r14
  unsigned int v8; // r11d
  STRSAFE_LPCSTR v9; // r10
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdx
  int v13; // eax
  __int128 v14; // xmm1
  unsigned __int16 v15; // cx
  __int64 v16; // rax
  int v17; // r8d
  unsigned int v18; // eax
  __int64 v19; // rax
  unsigned int v20; // eax
  void *v21; // rax
  int v22; // eax
  _QWORD *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rdx
  _DWORD *v27; // rcx
  int v28; // eax
  size_t v29; // [rsp+20h] [rbp-50h]
  int v30; // [rsp+30h] [rbp-40h] BYREF
  __int128 v31; // [rsp+38h] [rbp-38h] BYREF
  __int128 v32; // [rsp+48h] [rbp-28h]
  int v33; // [rsp+58h] [rbp-18h]

  v5 = (char *)(a1 + 1810);
  v33 = 0;
  v30 = 0;
  v7 = (unsigned __int16)a3;
  v31 = 0;
  v32 = 0;
  StringCopyWorkerA((STRSAFE_LPSTR)(a1 + 1810), 0x101u, a3, (STRSAFE_PCNZCH)(a1 + 1553), v29);
  StringCchCatA(v5, v8, v9);
  v10 = (*(__int64 (__fastcall **)(char *, __int64, __int64))(a1 + 24))(v5, 0x8000, 384);
  *(_QWORD *)(a1 + 216) = v10;
  if ( v10 == -1
    || (v11 = (*(__int64 (__fastcall **)(char *, __int64, __int64))(a1 + 24))(v5, 0x8000, 384),
        *(_QWORD *)(a1 + 208) = v11,
        v11 == -1) )
  {
    v24 = *(_QWORD **)a1;
    **(_QWORD **)a1 = 1;
    goto LABEL_30;
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD, __int128 *, __int64))(a1 + 32))(*(_QWORD *)(a1 + 216), &v31, 36) == 36
    && (_DWORD)v31 == 1178817357 )
  {
    if ( WORD4(v32) != 259 )
    {
      v27 = *(_DWORD **)a1;
      v28 = WORD4(v32);
      *v27 = 3;
      v27[1] = v28;
      v27[2] = 1;
      return 0;
    }
    if ( a4 != 0xFFFF && __PAIR32__(a4, v7) != v33 )
    {
      v24 = *(_QWORD **)a1;
      **(_QWORD **)a1 = 10;
      goto LABEL_30;
    }
    v13 = v33;
    v14 = v32;
    v15 = 0;
    HIWORD(v30) = 0;
    *(_OWORD *)(a1 + 152) = v31;
    LOWORD(v30) = 0;
    *(_OWORD *)(a1 + 168) = v14;
    *(_DWORD *)(a1 + 184) = v13;
    if ( (*(_BYTE *)(a1 + 182) & 4) == 0
      || (*(unsigned int (__fastcall **)(_QWORD, int *, __int64))(a1 + 32))(*(_QWORD *)(a1 + 216), &v30, 4) == 4
      && (v15 = v30, (unsigned __int16)v30 <= 0xEA60u) )
    {
      if ( *(_DWORD *)(a1 + 248) != v15 )
      {
        if ( *(_QWORD *)(a1 + 144) )
        {
          (*(void (__fastcall **)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 144));
          v15 = v30;
          *(_QWORD *)(a1 + 144) = 0;
        }
        *(_DWORD *)(a1 + 248) = v15;
        if ( v15 )
        {
          v16 = (*(__int64 (**)(void))(a1 + 16))();
          *(_QWORD *)(a1 + 144) = v16;
          if ( !v16 )
            goto LABEL_38;
        }
      }
      v17 = *(_DWORD *)(a1 + 248);
      if ( !v17
        || v17 == (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(a1 + 32))(
                    *(_QWORD *)(a1 + 216),
                    *(_QWORD *)(a1 + 144)) )
      {
        v18 = BYTE2(v30) + 8;
        if ( *(_QWORD *)(a1 + 128) )
        {
          if ( v18 != *(_DWORD *)(a1 + 252) )
          {
LABEL_33:
            v24 = *(_QWORD **)a1;
            **(_QWORD **)a1 = 9;
            goto LABEL_30;
          }
        }
        else
        {
          *(_DWORD *)(a1 + 252) = v18;
          v19 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 16))(v18);
          *(_QWORD *)(a1 + 128) = v19;
          if ( !v19 )
            goto LABEL_38;
        }
        v20 = HIBYTE(v30) + 8;
        if ( !*(_QWORD *)(a1 + 136) )
        {
          *(_DWORD *)(a1 + 256) = v20;
          v21 = (void *)(*(__int64 (__fastcall **)(_QWORD))(a1 + 16))(v20);
          *(_QWORD *)(a1 + 136) = v21;
          if ( v21 )
          {
            memset_0(v21, 0, *(unsigned int *)(a1 + 256));
LABEL_22:
            if ( (*(_BYTE *)(a1 + 182) & 1) != 0 )
            {
              if ( !(unsigned int)FDIReadPSZ(a1 + 525, v12, a1) || !(unsigned int)FDIReadPSZ(a1 + 782, v25, a1) )
                return 0;
            }
            else
            {
              *(_BYTE *)(a1 + 525) = 0;
              *(_BYTE *)(a1 + 782) = 0;
            }
            if ( (*(_BYTE *)(a1 + 182) & 2) != 0 )
            {
              if ( !(unsigned int)FDIReadPSZ(a1 + 1039, v12, a1) || !(unsigned int)FDIReadPSZ(a1 + 1296, v26, a1) )
                return 0;
            }
            else
            {
              *(_BYTE *)(a1 + 1039) = 0;
              *(_BYTE *)(a1 + 1296) = 0;
            }
            v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(a1 + 56))(*(_QWORD *)(a1 + 216), 0, 1);
            *(_DWORD *)(a1 + 88) = v22;
            if ( v22 != -1
              && (*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD))(a1 + 56))(
                   *(_QWORD *)(a1 + 216),
                   *(unsigned int *)(a1 + 168),
                   0) != -1 )
            {
              *(_WORD *)(a1 + 260) = *(_WORD *)(a1 + 180);
              return (unsigned int)doCabinetInfoNotify(a1) != 0;
            }
            v24 = *(_QWORD **)a1;
            **(_QWORD **)a1 = 4;
            goto LABEL_30;
          }
LABEL_38:
          v24 = *(_QWORD **)a1;
          **(_QWORD **)a1 = 5;
          goto LABEL_30;
        }
        if ( v20 == *(_DWORD *)(a1 + 256) )
          goto LABEL_22;
        goto LABEL_33;
      }
    }
  }
  v24 = *(_QWORD **)a1;
  **(_QWORD **)a1 = 2;
LABEL_30:
  *((_DWORD *)v24 + 2) = 1;
  return 0;
}

```

## disassembly

```asm
0x180002f0c  mov     [rsp-28h+arg_10], rbx
0x180002f11  push    rbp
0x180002f12  push    rsi
0x180002f13  push    rdi
0x180002f14  push    r14
0x180002f16  push    r15
0x180002f18  mov     rbp, rsp
0x180002f1b  sub     rsp, 70h
0x180002f1f  mov     rax, cs:__security_cookie
0x180002f26  xor     rax, rsp
0x180002f29  mov     [rbp+var_10], rax
0x180002f2d  movzx   ebx, r9w
0x180002f31  lea     rsi, [rcx+712h]
0x180002f38  lea     r9, [rcx+611h]; pszSrc
0x180002f3f  mov     r10, rdx
0x180002f42  mov     rdi, rcx
0x180002f45  xorps   xmm0, xmm0
0x180002f48  xor     eax, eax
0x180002f4a  mov     r11d, 101h
0x180002f50  xor     r15d, r15d
0x180002f53  mov     [rbp+var_18], eax
0x180002f56  mov     edx, r11d; cchDest
0x180002f59  mov     [rbp+var_40], r15d
0x180002f5d  mov     rcx, rsi; pszDest
0x180002f60  movzx   r14d, r8w
0x180002f64  movups  [rbp+var_38], xmm0
0x180002f68  movups  [rbp+var_28], xmm0
0x180002f6c  call    StringCopyWorkerA
0x180002f71  mov     r8, r10; pszSrc
0x180002f74  mov     edx, r11d; cchDest
0x180002f77  mov     rcx, rsi; pszDest
0x180002f7a  call    StringCchCatA
0x180002f7f  mov     rax, [rdi+18h]
0x180002f83  mov     edx, 8000h
0x180002f88  mov     r8d, 180h
0x180002f8e  mov     rcx, rsi
0x180002f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f96  mov     [rdi+0D8h], rax
0x180002f9d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002fa1  jz      loc_1800032F2
0x180002fa7  mov     rax, [rdi+18h]
0x180002fab  mov     edx, 8000h
0x180002fb0  mov     r8d, 180h
0x180002fb6  mov     rcx, rsi
0x180002fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fbe  mov     [rdi+0D0h], rax
0x180002fc5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002fc9  jz      loc_1800032F2
0x180002fcf  mov     rcx, [rdi+0D8h]
0x180002fd6  lea     r8d, [r15+24h]
0x180002fda  mov     rax, [rdi+20h]
0x180002fde  lea     rdx, [rbp+var_38]
0x180002fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fe7  cmp     eax, 24h ; '$'
0x180002fea  jnz     loc_18000322E
0x180002ff0  cmp     dword ptr [rbp+var_38], 4643534Dh
0x180002ff7  jnz     loc_18000322E
0x180002ffd  mov     eax, 103h
0x180003002  cmp     word ptr [rbp+var_28+8], ax
0x180003006  jnz     loc_180003301
0x18000300c  mov     eax, 0FFFFh
0x180003011  cmp     bx, ax
0x180003014  jnz     loc_18000325B
0x18000301a  movups  xmm0, [rbp+var_38]
0x18000301e  mov     eax, [rbp+var_18]
0x180003021  mov     esi, 4
0x180003026  movups  xmm1, [rbp+var_28]
0x18000302a  mov     ecx, r15d
0x18000302d  mov     word ptr [rbp+var_40+2], r15w
0x180003032  movups  xmmword ptr [rdi+98h], xmm0
0x180003039  mov     word ptr [rbp+var_40], cx
0x18000303d  movups  xmmword ptr [rdi+0A8h], xmm1
0x180003044  mov     [rdi+0B8h], eax
0x18000304a  test    [rdi+0B6h], sil
0x180003051  jz      short loc_180003084
0x180003053  mov     rcx, [rdi+0D8h]
0x18000305a  lea     rdx, [rbp+var_40]
0x18000305e  mov     rax, [rdi+20h]
0x180003062  mov     r8d, esi
0x180003065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000306a  cmp     eax, esi
0x18000306c  jnz     loc_18000322E
0x180003072  movzx   ecx, word ptr [rbp+var_40]
0x180003076  mov     eax, 0EA60h
0x18000307b  cmp     cx, ax
0x18000307e  ja      loc_18000322E
0x180003084  movzx   eax, cx
0x180003087  cmp     [rdi+0F8h], eax
0x18000308d  jz      short loc_1800030C5
0x18000308f  mov     rax, [rdi+90h]
0x180003096  test    rax, rax
0x180003099  jnz     loc_18000331D
0x18000309f  movzx   ecx, cx
0x1800030a2  mov     [rdi+0F8h], ecx
0x1800030a8  test    ecx, ecx
0x1800030aa  jz      short loc_1800030C5
0x1800030ac  mov     rax, [rdi+10h]
0x1800030b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030b5  mov     [rdi+90h], rax
0x1800030bc  test    rax, rax
0x1800030bf  jz      loc_18000327C
0x1800030c5  mov     r8d, [rdi+0F8h]
0x1800030cc  test    r8d, r8d
0x1800030cf  jz      short loc_1800030F3
0x1800030d1  mov     rdx, [rdi+90h]
0x1800030d8  mov     ebx, r8d
0x1800030db  mov     rcx, [rdi+0D8h]
0x1800030e2  mov     rax, [rdi+20h]
0x1800030e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030eb  cmp     ebx, eax
0x1800030ed  jnz     loc_18000322E
0x1800030f3  movzx   eax, byte ptr [rbp+var_40+2]
0x1800030f7  add     eax, 8
0x1800030fa  cmp     [rdi+80h], r15
0x180003101  jnz     loc_180003243
0x180003107  mov     [rdi+0FCh], eax
0x18000310d  mov     ecx, eax
0x18000310f  mov     rax, [rdi+10h]
0x180003113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003118  mov     [rdi+80h], rax
0x18000311f  test    rax, rax
0x180003122  jz      loc_18000327C
0x180003128  movzx   eax, byte ptr [rbp+var_40+3]
0x18000312c  add     eax, 8
0x18000312f  cmp     [rdi+88h], r15
0x180003136  jnz     loc_18000326E
0x18000313c  mov     [rdi+100h], eax
0x180003142  mov     ecx, eax
0x180003144  mov     rax, [rdi+10h]
0x180003148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000314d  mov     [rdi+88h], rax
0x180003154  test    rax, rax
0x180003157  jz      loc_18000327C
0x18000315d  mov     r8d, [rdi+100h]; Size
0x180003164  xor     edx, edx; Val
0x180003166  mov     rcx, rax; void *
0x180003169  call    memset_0
0x18000316e  test    byte ptr [rdi+0B6h], 1
0x180003175  lea     rax, [rdi+20Dh]
0x18000317c  jnz     loc_180003290
0x180003182  mov     [rax], r15b
0x180003185  mov     [rdi+30Eh], r15b
0x18000318c  test    byte ptr [rdi+0B6h], 2
0x180003193  lea     rax, [rdi+40Fh]
0x18000319a  jnz     loc_1800032C3
0x1800031a0  mov     [rax], r15b
0x1800031a3  mov     [rdi+510h], r15b
0x1800031aa  mov     rcx, [rdi+0D8h]
0x1800031b1  xor     edx, edx
0x1800031b3  mov     rax, [rdi+38h]
0x1800031b7  lea     r8d, [rdx+1]
0x1800031bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031c0  mov     [rdi+58h], eax
0x1800031c3  cmp     eax, 0FFFFFFFFh
0x1800031c6  jz      loc_180003288
0x1800031cc  mov     edx, [rdi+0A8h]
0x1800031d2  xor     r8d, r8d
0x1800031d5  mov     rcx, [rdi+0D8h]
0x1800031dc  mov     rax, [rdi+38h]
0x1800031e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031e5  cmp     eax, 0FFFFFFFFh
0x1800031e8  jz      loc_180003288
0x1800031ee  movzx   eax, word ptr [rdi+0B4h]
0x1800031f5  mov     rcx, rdi
0x1800031f8  mov     [rdi+104h], ax
0x1800031ff  call    doCabinetInfoNotify
0x180003204  test    eax, eax
0x180003206  mov     ecx, r15d
0x180003209  setnz   cl
0x18000320c  mov     eax, ecx
0x18000320e  mov     rcx, [rbp+var_10]
0x180003212  xor     rcx, rsp; StackCookie
0x180003215  call    __security_check_cookie
0x18000321a  mov     rbx, [rsp+70h+arg_10]
0x180003222  add     rsp, 70h
0x180003226  pop     r15
0x180003228  pop     r14
0x18000322a  pop     rdi
0x18000322b  pop     rsi
0x18000322c  pop     rbp
0x18000322d  retn
0x18000322e  mov     rax, [rdi]
0x180003231  mov     qword ptr [rax], 2
0x180003238  mov     dword ptr [rax+8], 1
0x18000323f  xor     eax, eax
0x180003241  jmp     short loc_18000320E
0x180003243  cmp     eax, [rdi+0FCh]
0x180003249  jz      loc_180003128
0x18000324f  mov     rax, [rdi]
0x180003252  mov     qword ptr [rax], 9
0x180003259  jmp     short loc_180003238
0x18000325b  cmp     r14w, word ptr [rbp+var_18]
0x180003260  jz      short loc_1800032B8
0x180003262  mov     rax, [rdi]
0x180003265  mov     qword ptr [rax], 0Ah
0x18000326c  jmp     short loc_180003238
0x18000326e  cmp     eax, [rdi+100h]
0x180003274  jz      loc_18000316E
0x18000327a  jmp     short loc_18000324F
0x18000327c  mov     rax, [rdi]
0x18000327f  mov     qword ptr [rax], 5
0x180003286  jmp     short loc_180003238
0x180003288  mov     rax, [rdi]
0x18000328b  mov     [rax], rsi
0x18000328e  jmp     short loc_180003238
0x180003290  mov     r8, rdi
0x180003293  mov     rcx, rax
0x180003296  call    FDIReadPSZ
0x18000329b  test    eax, eax
0x18000329d  jz      short loc_18000323F
0x18000329f  lea     rcx, [rdi+30Eh]
0x1800032a6  mov     r8, rdi
0x1800032a9  call    FDIReadPSZ
0x1800032ae  test    eax, eax
0x1800032b0  jnz     loc_18000318C
0x1800032b6  jmp     short loc_18000323F
0x1800032b8  cmp     bx, word ptr [rbp+var_18+2]
0x1800032bc  jnz     short loc_180003262
0x1800032be  jmp     loc_18000301A
0x1800032c3  mov     r8, rdi
0x1800032c6  mov     rcx, rax
0x1800032c9  call    FDIReadPSZ
0x1800032ce  test    eax, eax
0x1800032d0  jz      loc_18000323F
0x1800032d6  lea     rcx, [rdi+510h]
0x1800032dd  mov     r8, rdi
0x1800032e0  call    FDIReadPSZ
0x1800032e5  test    eax, eax
0x1800032e7  jnz     loc_1800031AA
0x1800032ed  jmp     loc_18000323F
0x1800032f2  mov     rax, [rdi]
0x1800032f5  mov     qword ptr [rax], 1
0x1800032fc  jmp     loc_180003238
0x180003301  mov     rcx, [rdi]
0x180003304  movzx   eax, word ptr [rbp+var_28+8]
0x180003308  mov     dword ptr [rcx], 3
0x18000330e  mov     [rcx+4], eax
0x180003311  mov     dword ptr [rcx+8], 1
0x180003318  jmp     loc_18000323F
0x18000331d  mov     rcx, rax
0x180003320  mov     rax, [rdi+8]
0x180003324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003329  movzx   ecx, word ptr [rbp+var_40]
0x18000332d  mov     [rdi+90h], r15
0x180003334  jmp     loc_18000309F
```
