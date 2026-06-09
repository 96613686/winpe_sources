# ClasspWriteSenseDataEvent

- ea: `0x140008024`
- end: `0x140008359`
- name: `ClasspWriteSenseDataEvent`
- size: `821`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400077ac`
- `0x140008360`

## callees

- `0x140008024`
- `0x14003d8ac`
- `0x14003e430`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14000813e`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14000813e`

## pseudocode

```c
void __fastcall ClasspWriteSenseDataEvent(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  bool v4; // zf
  __int64 v7; // r15
  char v9; // bp
  _BYTE *v10; // rbx
  unsigned int v11; // r10d
  __int64 v12; // r9
  char v13; // r11
  __int64 v14; // rcx
  unsigned __int64 v15; // r8
  int v16; // ecx
  unsigned __int8 v17; // si
  unsigned int v18; // r10d
  __int64 v19; // r9
  char v20; // r11
  __int64 v21; // rcx
  unsigned __int64 v22; // r8
  int v23; // ecx
  __int64 v24; // r14
  char v25; // r9
  char v26; // r8
  _BYTE *v27; // rcx
  _BYTE *v28; // rax
  char *v29; // r8
  unsigned int v30; // eax
  unsigned __int64 v31; // rcx
  int v32; // ecx
  int v33; // ecx
  __int128 v34; // [rsp+40h] [rbp-48h] BYREF

  v4 = *(_BYTE *)(a3 + 2) == 40;
  v34 = 0;
  v7 = a2;
  v9 = 1;
  if ( v4 )
  {
    v10 = 0;
    if ( !*(_DWORD *)(a3 + 20) )
    {
      v11 = *(_DWORD *)(a3 + 56);
      if ( v11 )
      {
        v12 = 0;
        v13 = 0;
        do
        {
          v14 = *(unsigned int *)(a3 + 4 * v12 + 120);
          if ( (unsigned int)v14 >= 0x80 )
          {
            v15 = *(unsigned int *)(a3 + 16);
            if ( (unsigned int)v14 < (unsigned int)v15 )
            {
              a2 = (unsigned int)v14;
              v16 = *(_DWORD *)(v14 + a3) - 64;
              if ( v16 )
              {
                v33 = v16 - 1;
                if ( v33 )
                {
                  if ( v33 == 1 && a2 + 40 <= v15 )
                  {
                    v10 = *(_BYTE **)(a2 + a3 + 24);
                    break;
                  }
                }
                else if ( a2 + 56 <= v15 )
                {
                  v10 = *(_BYTE **)(a2 + a3 + 16);
                  v13 = 1;
                }
              }
              else if ( a2 + 40 <= v15 )
              {
                v10 = *(_BYTE **)(a2 + a3 + 16);
                break;
              }
              if ( v13 )
                break;
            }
          }
          v12 = (unsigned int)(v12 + 1);
        }
        while ( (unsigned int)v12 < v11 );
      }
    }
    v17 = 0;
    if ( *(_DWORD *)(a3 + 20) )
      goto LABEL_18;
    v18 = *(_DWORD *)(a3 + 56);
    if ( !v18 )
      goto LABEL_18;
    v19 = 0;
    v20 = 0;
    while ( 1 )
    {
      v21 = *(unsigned int *)(a3 + 4 * v19 + 120);
      if ( (unsigned int)v21 >= 0x80 )
      {
        v22 = *(unsigned int *)(a3 + 16);
        if ( (unsigned int)v21 < (unsigned int)v22 )
          break;
      }
LABEL_44:
      v19 = (unsigned int)(v19 + 1);
      if ( (unsigned int)v19 >= v18 )
        goto LABEL_18;
    }
    a2 = (unsigned int)v21;
    v23 = *(_DWORD *)(v21 + a3) - 64;
    if ( !v23 )
      goto LABEL_16;
    v32 = v23 - 1;
    if ( v32 )
    {
      if ( v32 == 1 )
      {
LABEL_16:
        if ( a2 + 40 <= v22 )
        {
          v17 = *(_BYTE *)(a2 + a3 + 9);
          goto LABEL_18;
        }
      }
    }
    else if ( a2 + 56 <= v22 )
    {
      v17 = *(_BYTE *)(a2 + a3 + 9);
      v20 = 1;
    }
    if ( v20 )
      goto LABEL_18;
    goto LABEL_44;
  }
  v17 = *(_BYTE *)(a3 + 11);
  v10 = *(_BYTE **)(a3 + 32);
LABEL_18:
  if ( !ClassPnPETWEnabled )
    return;
  v24 = *(_QWORD *)(a1 + 64);
  if ( v7 )
    IoGetActivityIdIrp(v7, &v34);
  if ( *(char *)(a3 + 3) >= 0 || !v10 || !v17 )
    return;
  LOBYTE(a2) = 0;
  v25 = 0;
  v26 = 0;
  v27 = &v10[v17];
  v28 = v10 + 8;
  if ( (unsigned __int8)((*v10 & 0x7F) - 114) > 1u )
  {
    if ( v28 <= v27 )
    {
      v29 = v10 + 13;
      LOBYTE(a2) = v10[2] & 0xF;
      v30 = v17;
      if ( (unsigned int)(unsigned __int8)v10[7] + 8 <= v17 )
        v30 = (unsigned __int8)v10[7] + 8;
      v31 = (unsigned __int64)&v10[v30];
      if ( (unsigned __int64)v29 <= v31 )
        v25 = v10[12];
      if ( (unsigned __int64)(v10 + 14) <= v31 )
        v26 = *v29;
      else
        v26 = 0;
      goto LABEL_32;
    }
    goto LABEL_57;
  }
  if ( v28 > v27 )
  {
LABEL_57:
    v9 = 0;
    goto LABEL_32;
  }
  v25 = v10[2];
  LOBYTE(a2) = v10[1] & 0xF;
  v26 = v10[3];
LABEL_32:
  if ( !v9 )
    return;
  if ( (unsigned __int8)a2 != 2 )
  {
    if ( (unsigned __int8)a2 == 6 )
    {
      if ( v25 != 56 || v26 != 7 || ((__int64)WPP_MAIN_CB.Queue.Wcb.CurrentIrp & 0x40) == 0 )
        return;
    }
    else if ( (unsigned __int8)a2 != 7
           || v25 != 39
           || v26 != 7
           || ((__int64)WPP_MAIN_CB.Queue.Wcb.CurrentIrp & 0x40) == 0 )
    {
      return;
    }
    McTemplateK0quuuq_EtwWriteTransfer(
      (unsigned __int8)a2 - 6,
      a2,
      (unsigned int)&v34,
      *(_DWORD *)(v24 + 588),
      a2,
      v25,
      7,
      a4,
      v34);
    return;
  }
  if ( v25 == 4 && v26 == 20 && ((__int64)WPP_MAIN_CB.Queue.Wcb.CurrentIrp & 0x40) != 0 )
    McTemplateK0quuuq_EtwWriteTransfer(
      (unsigned __int8)a2 - 2,
      a2,
      (unsigned int)&v34,
      *(_DWORD *)(v24 + 588),
      a2,
      4,
      20,
      a4,
      v34);
}

```

## disassembly

```asm
0x140008024  mov     [rsp+arg_10], rbx
0x140008029  mov     [rsp+arg_18], rbp
0x14000802e  push    rsi
0x14000802f  push    rdi
0x140008030  push    r12
0x140008032  push    r14
0x140008034  push    r15
0x140008036  sub     rsp, 60h
0x14000803a  mov     rax, cs:__security_cookie
0x140008041  xor     rax, rsp
0x140008044  mov     [rsp+88h+var_38], rax
0x140008049  cmp     byte ptr [r8+2], 28h ; '('
0x14000804e  xorps   xmm0, xmm0
0x140008051  movups  [rsp+88h+var_48], xmm0
0x140008056  mov     r12d, r9d
0x140008059  mov     rdi, r8
0x14000805c  mov     r15, rdx
0x14000805f  mov     r14, rcx
0x140008062  mov     ebp, 1
0x140008067  jnz     loc_140008207
0x14000806d  xor     ebx, ebx
0x14000806f  cmp     [r8+14h], ebx
0x140008073  jnz     short loc_1400080C6
0x140008075  mov     r10d, [r8+38h]
0x140008079  test    r10d, r10d
0x14000807c  jz      short loc_1400080C6
0x14000807e  xor     r9d, r9d
0x140008081  xor     r11b, r11b
0x140008084  mov     ecx, [rdi+r9*4+78h]
0x140008089  cmp     ecx, 80h
0x14000808f  jb      loc_14000825D
0x140008095  mov     r8d, [rdi+10h]
0x140008099  cmp     ecx, r8d
0x14000809c  jnb     loc_14000825D
0x1400080a2  mov     edx, ecx
0x1400080a4  mov     ecx, [rcx+rdi]
0x1400080a7  sub     ecx, 40h ; '@'
0x1400080aa  jnz     loc_140008229
0x1400080b0  lea     rcx, [rdx+28h]
0x1400080b4  cmp     rcx, r8
0x1400080b7  jbe     loc_140008278
0x1400080bd  test    r11b, r11b
0x1400080c0  jz      loc_14000825D
0x1400080c6  xor     sil, sil
0x1400080c9  cmp     dword ptr [rdi+14h], 0
0x1400080cd  jnz     short loc_140008120
0x1400080cf  mov     r10d, [rdi+38h]
0x1400080d3  test    r10d, r10d
0x1400080d6  jz      short loc_140008120
0x1400080d8  xor     r9d, r9d
0x1400080db  xor     r11b, r11b
0x1400080de  mov     ecx, [rdi+r9*4+78h]
0x1400080e3  cmp     ecx, 80h
0x1400080e9  jb      loc_14000824C
0x1400080ef  mov     r8d, [rdi+10h]
0x1400080f3  cmp     ecx, r8d
0x1400080f6  jnb     loc_14000824C
0x1400080fc  mov     edx, ecx
0x1400080fe  mov     ecx, [rcx+rdi]
0x140008101  sub     ecx, 40h ; '@'
0x140008104  jnz     loc_140008214
0x14000810a  lea     rcx, [rdx+28h]
0x14000810e  cmp     rcx, r8
0x140008111  jbe     loc_14000826E
0x140008117  test    r11b, r11b
0x14000811a  jz      loc_14000824C
0x140008120  cmp     cs:ClassPnPETWEnabled, 0
0x140008127  jz      loc_1400081E0
0x14000812d  mov     r14, [r14+40h]
0x140008131  test    r15, r15
0x140008134  jz      short loc_14000814A
0x140008136  lea     rdx, [rsp+88h+var_48]
0x14000813b  mov     rcx, r15
0x14000813e  call    cs:__imp_IoGetActivityIdIrp
0x140008145  nop     dword ptr [rax+rax+00h]
0x14000814a  cmp     byte ptr [rdi+3], 0
0x14000814e  jge     loc_1400081E0
0x140008154  test    rbx, rbx
0x140008157  jz      loc_1400081E0
0x14000815d  test    sil, sil
0x140008160  jz      short loc_1400081E0
0x140008162  mov     al, [rbx]
0x140008164  xor     dl, dl
0x140008166  and     al, 7Fh
0x140008168  movzx   ecx, sil
0x14000816c  sub     al, 72h ; 'r'
0x14000816e  xor     r9b, r9b
0x140008171  xor     r8b, r8b
0x140008174  add     rcx, rbx
0x140008177  cmp     al, bpl
0x14000817a  lea     rax, [rbx+8]
0x14000817e  jbe     loc_140008282
0x140008184  cmp     rax, rcx
0x140008187  ja      loc_1400082DF
0x14000818d  movzx   ecx, byte ptr [rbx+7]
0x140008191  lea     r8, [rbx+0Dh]
0x140008195  mov     dl, [rbx+2]
0x140008198  add     ecx, 8
0x14000819b  and     dl, 0Fh
0x14000819e  movzx   eax, sil
0x1400081a2  cmp     ecx, eax
0x1400081a4  cmovbe  eax, ecx
0x1400081a7  mov     ecx, eax
0x1400081a9  add     rcx, rbx
0x1400081ac  cmp     r8, rcx
0x1400081af  jbe     loc_14000829A
0x1400081b5  lea     rax, [rbx+0Eh]
0x1400081b9  cmp     rax, rcx
0x1400081bc  jbe     loc_1400082A3
0x1400081c2  xor     r8b, r8b
0x1400081c5  test    bpl, bpl
0x1400081c8  jz      short loc_1400081E0
0x1400081ca  movzx   ecx, dl
0x1400081cd  sub     ecx, 2
0x1400081d0  jnz     loc_1400082E7
0x1400081d6  cmp     r9b, 4
0x1400081da  jz      loc_14000832E
0x1400081e0  mov     rcx, [rsp+88h+var_38]
0x1400081e5  xor     rcx, rsp; StackCookie
0x1400081e8  call    __security_check_cookie
0x1400081ed  lea     r11, [rsp+88h+var_28]
0x1400081f2  mov     rbx, [r11+40h]
0x1400081f6  mov     rbp, [r11+48h]
0x1400081fa  mov     rsp, r11
0x1400081fd  pop     r15
0x1400081ff  pop     r14
0x140008201  pop     r12
0x140008203  pop     rdi
0x140008204  pop     rsi
0x140008205  retn
0x140008207  mov     sil, [r8+0Bh]
0x14000820b  mov     rbx, [r8+20h]
0x14000820f  jmp     loc_140008120
0x140008214  sub     ecx, ebp
0x140008216  jz      loc_1400082C5
0x14000821c  cmp     ecx, ebp
0x14000821e  jnz     loc_140008117
0x140008224  jmp     loc_14000810A
0x140008229  sub     ecx, ebp
0x14000822b  jz      short loc_1400082AB
0x14000822d  cmp     ecx, ebp
0x14000822f  jnz     loc_1400080BD
0x140008235  lea     rcx, [rdx+28h]
0x140008239  cmp     rcx, r8
0x14000823c  ja      loc_1400080BD
0x140008242  mov     rbx, [rdx+rdi+18h]
0x140008247  jmp     loc_1400080C6
0x14000824c  add     r9d, ebp
0x14000824f  cmp     r9d, r10d
0x140008252  jnb     loc_140008120
0x140008258  jmp     loc_1400080DE
0x14000825d  add     r9d, ebp
0x140008260  cmp     r9d, r10d
0x140008263  jnb     loc_1400080C6
0x140008269  jmp     loc_140008084
0x14000826e  mov     sil, [rdx+rdi+9]
0x140008273  jmp     loc_140008120
0x140008278  mov     rbx, [rdx+rdi+10h]
0x14000827d  jmp     loc_1400080C6
0x140008282  cmp     rax, rcx
0x140008285  ja      short loc_1400082DF
0x140008287  mov     dl, [rbx+1]
0x14000828a  mov     r9b, [rbx+2]
0x14000828e  and     dl, 0Fh
0x140008291  mov     r8b, [rbx+3]
0x140008295  jmp     loc_1400081C5
0x14000829a  mov     r9b, [rbx+0Ch]
0x14000829e  jmp     loc_1400081B5
0x1400082a3  mov     r8b, [r8]
0x1400082a6  jmp     loc_1400081C5
0x1400082ab  lea     rcx, [rdx+38h]
0x1400082af  cmp     rcx, r8
0x1400082b2  ja      loc_1400080BD
0x1400082b8  mov     rbx, [rdx+rdi+10h]
0x1400082bd  mov     r11b, bpl
0x1400082c0  jmp     loc_1400080BD
0x1400082c5  lea     rcx, [rdx+38h]
0x1400082c9  cmp     rcx, r8
0x1400082cc  ja      loc_140008117
0x1400082d2  mov     sil, [rdx+rdi+9]
0x1400082d7  mov     r11b, bpl
0x1400082da  jmp     loc_140008117
0x1400082df  xor     bpl, bpl
0x1400082e2  jmp     loc_1400081C5
0x1400082e7  sub     ecx, 4
0x1400082ea  jz      loc_14003F3A0
0x1400082f0  cmp     ecx, 1
0x1400082f3  jnz     loc_1400081E0
0x1400082f9  cmp     r9b, 27h ; '''
0x1400082fd  jnz     loc_1400081E0
0x140008303  cmp     r8b, 7
0x140008307  jnz     loc_1400081E0
0x14000830d  test    byte ptr cs:WPP_MAIN_CB.Queue+38h, 40h
0x140008314  jz      loc_1400081E0
0x14000831a  mov     [rsp+88h+var_50], r12d
0x14000831f  mov     [rsp+88h+var_58], r8b
0x140008324  mov     [rsp+88h+var_60], r9b
0x140008329  jmp     loc_14003F3D0
0x14000832e  cmp     r8b, 14h
0x140008332  jnz     loc_1400081E0
0x140008338  test    byte ptr cs:WPP_MAIN_CB.Queue+38h, 40h
0x14000833f  jz      loc_1400081E0
0x140008345  mov     [rsp+88h+var_50], r12d
0x14000834a  mov     [rsp+88h+var_58], r8b
0x14000834f  mov     [rsp+88h+var_60], 4
0x140008354  jmp     loc_14003F3D0
0x14003f3a0  cmp     r9b, 38h ; '8'
0x14003f3a4  jnz     loc_1400081E0
0x14003f3aa  cmp     r8b, 7
0x14003f3ae  jnz     loc_1400081E0
0x14003f3b4  test    byte ptr cs:WPP_MAIN_CB.Queue+38h, 40h
0x14003f3bb  jz      loc_1400081E0
0x14003f3c1  mov     [rsp+88h+var_50], r12d
0x14003f3c6  mov     [rsp+88h+var_58], r8b
0x14003f3cb  mov     [rsp+88h+var_60], r9b
0x14003f3d0  mov     r9d, [r14+24Ch]
0x14003f3d7  lea     r8, [rsp+88h+var_48]
0x14003f3dc  mov     [rsp+88h+var_68], dl
0x14003f3e0  call    McTemplateK0quuuq_EtwWriteTransfer
0x14003f3e5  nop
0x14003f3e6  jmp     loc_1400081E0
```
