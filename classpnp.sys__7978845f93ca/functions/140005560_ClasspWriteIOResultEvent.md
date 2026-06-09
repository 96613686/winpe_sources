# ClasspWriteIOResultEvent

- ea: `0x140005560`
- end: `0x140005c1c`
- name: `ClasspWriteIOResultEvent`
- size: `1724`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140005190`
- `0x14001ccb0`

## callees

- `0x140005560`
- `0x140005c30`
- `0x140006300`
- `0x1400066cc`
- `0x140007788`
- `0x14003bf7c`
- `0x14003e430`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14000561d`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14000561d`

## pseudocode

```c
void __fastcall ClasspWriteIOResultEvent(__int64 a1, unsigned __int64 a2, IRP *a3)
{
  __int64 v3; // rsi
  unsigned __int64 v5; // rbx
  __int64 v7; // r15
  __int64 Status; // r8
  char v9; // r12
  char v10; // r13
  __int64 v11; // r14
  unsigned __int64 v12; // rcx
  char v13; // r10
  __int64 v14; // r8
  int v15; // edx
  char v16; // r9
  char v17; // al
  unsigned int v18; // r10d
  _BYTE *v19; // rax
  int v20; // r9d
  char *v21; // r11
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // r10
  int v25; // ecx
  unsigned __int64 v26; // rcx
  __int128 *v27; // rdi
  char v28; // cl
  __int64 v29; // rax
  char v30; // al
  char v31; // cl
  int v32; // eax
  int v33; // edx
  int v34; // ecx
  _BYTE *v35; // rdx
  unsigned int v36; // edi
  unsigned __int64 v37; // r8
  __int64 v38; // r11
  __int64 v39; // r9
  int v40; // ecx
  unsigned __int8 v41; // r8
  unsigned int v42; // r11d
  unsigned __int64 v43; // r9
  __int64 v44; // rdi
  __int64 v45; // r10
  int v46; // ecx
  _BYTE *v47; // rax
  char *v48; // r12
  unsigned int v49; // eax
  unsigned int v50; // edi
  unsigned int v51; // eax
  unsigned __int64 v52; // r11
  __int64 v53; // r15
  __int64 v54; // rbx
  int v55; // ecx
  int v56; // ecx
  char v57; // al
  char v58; // [rsp+20h] [rbp-C8h]
  char v59; // [rsp+70h] [rbp-78h]
  unsigned int v60; // [rsp+74h] [rbp-74h]
  unsigned int v61; // [rsp+74h] [rbp-74h]
  unsigned int v62; // [rsp+88h] [rbp-60h]
  _BYTE *v63; // [rsp+90h] [rbp-58h]
  __int128 v64; // [rsp+98h] [rbp-50h] BYREF

  v3 = *(_QWORD *)(a1 + 64);
  v5 = a2;
  v7 = *(_QWORD *)(v3 + 1144);
  v64 = 0;
  if ( !ClassPnPETWEnabled )
    return;
  Status = (unsigned int)a3->IoStatus.Status;
  if ( (int)Status >= 0 && (BYTE1(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x40) == 0 )
    return;
  v9 = 0;
  v10 = 0;
  v59 = 0;
  if ( a2 )
  {
    v18 = 0;
    v11 = *(_QWORD *)(a2 + 288);
    v62 = 0;
    v19 = *(_BYTE **)(*(_QWORD *)(a2 + 48) + 184LL);
    v63 = v19;
    if ( (int)Status >= 0 )
    {
      v27 = (__int128 *)(a2 + 328);
      goto LABEL_52;
    }
    v20 = *(unsigned __int8 *)(v11 + 2);
    if ( (_BYTE)v20 == 40 )
    {
      v21 = 0;
      if ( !*(_DWORD *)(v11 + 20) )
      {
        v60 = *(_DWORD *)(v11 + 56);
        if ( v60 )
        {
          while ( 1 )
          {
            v22 = *(unsigned int *)(v11 + 4LL * (_QWORD)v21 + 120);
            if ( (unsigned int)v22 < 0x80 )
              goto LABEL_27;
            a2 = *(unsigned int *)(v11 + 16);
            if ( (unsigned int)v22 >= (unsigned int)a2 )
              goto LABEL_27;
            v23 = v22 + v11;
            v24 = (unsigned int)v22;
            v25 = *(_DWORD *)(v22 + v11);
            if ( v25 == 64 )
              break;
            v56 = v25 - 65;
            if ( !v56 )
            {
              v26 = v24 + 56;
LABEL_26:
              if ( v26 <= a2 )
              {
                if ( *(_BYTE *)(v23 + 10) )
                {
                  v21 = (char *)(v23 + 24);
                  goto LABEL_36;
                }
                goto LABEL_28;
              }
              goto LABEL_27;
            }
            if ( v56 == 1 && v24 + 40 <= a2 )
            {
              if ( *(_DWORD *)(v23 + 12) )
              {
                v21 = (char *)(v23 + 32);
                goto LABEL_36;
              }
LABEL_28:
              v21 = 0;
              goto LABEL_36;
            }
LABEL_27:
            v21 = (char *)(unsigned int)((_DWORD)v21 + 1);
            if ( (unsigned int)v21 >= v60 )
              goto LABEL_28;
          }
          v26 = v24 + 40;
          goto LABEL_26;
        }
      }
    }
    else
    {
      v21 = (char *)(v11 + 72);
    }
LABEL_36:
    v28 = *v21;
    if ( *v21 == 30 || ((v28 - 26) & 0xBF) == 0 || v28 == 37 || v28 == -98 )
      goto LABEL_121;
    if ( ((v28 - 8) & 0x5D) == 0 )
    {
      if ( !v11 )
        goto LABEL_45;
      v29 = 24;
      if ( (_BYTE)v20 != 40 )
        v29 = 12;
      if ( (*(_DWORD *)(v29 + v11) & 0x1000) != 0 )
        v30 = 0;
      else
LABEL_45:
        v30 = *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 40) + 64LL) + 1144LL) + 660LL) - *(_BYTE *)(v5 + 57);
      v31 = v30;
      goto LABEL_47;
    }
    if ( v28 == -125 )
    {
      v57 = v21[1] & 0x1F;
      if ( v57 == 16 )
      {
LABEL_121:
        v31 = 1 - *(_BYTE *)(v5 + 57);
        goto LABEL_47;
      }
      if ( v57 == 17 )
      {
        v31 = 2 - *(_BYTE *)(v5 + 57);
        goto LABEL_47;
      }
    }
    if ( (unsigned __int8)ClasspIsReceiveTokenInformation(v21, a2, Status) )
      v31 = 2 - *(_BYTE *)(v5 + 57);
    else
      v31 = 0;
LABEL_47:
    if ( (_BYTE)v20 == 40 )
      v32 = *(_DWORD *)(v11 + 20);
    else
      v32 = v20;
    v58 = v31;
    v33 = a1;
    v27 = (__int128 *)(v5 + 328);
    v34 = v5 + 328;
    if ( v32 )
      ClasspWriteNonScsiSrbErrorResultEvent(v34, v33, Status, v11, v58);
    else
      ClasspWriteScsiSrbErrorResultEvent(v34, v33, Status, v11, v58);
    v19 = v63;
    v18 = 0;
LABEL_52:
    LODWORD(v12) = 2;
    if ( !v19 || (unsigned __int8)(*v19 - 3) > 1u )
      return;
    v64 = *v27;
    if ( *(_BYTE *)(v11 + 2) == 40 )
    {
      v35 = 0;
      if ( !*(_DWORD *)(v11 + 20) )
      {
        v36 = *(_DWORD *)(v11 + 56);
        if ( v36 )
        {
          do
          {
            v12 = *(unsigned int *)(v11 + 4LL * v18 + 120);
            if ( (unsigned int)v12 < 0x80 )
              goto LABEL_62;
            v37 = *(unsigned int *)(v11 + 16);
            if ( (unsigned int)v12 >= (unsigned int)v37 )
              goto LABEL_62;
            v38 = v12 + v11;
            v39 = (unsigned int)v12;
            v40 = *(_DWORD *)(v12 + v11);
            if ( v40 == 64 )
            {
              v12 = v39 + 40;
            }
            else
            {
              LODWORD(v12) = v40 - 65;
              if ( (_DWORD)v12 )
              {
                if ( (_DWORD)v12 == 1 )
                {
                  LODWORD(v12) = v39 + 40;
                  if ( v39 + 40 <= v37 )
                  {
                    v35 = *(_BYTE **)(v38 + 24);
                    break;
                  }
                }
                goto LABEL_62;
              }
              v12 = v39 + 56;
            }
            if ( v12 <= v37 )
            {
              v35 = *(_BYTE **)(v38 + 16);
              break;
            }
LABEL_62:
            ++v18;
          }
          while ( v18 < v36 );
        }
      }
      v41 = 0;
      if ( !*(_DWORD *)(v11 + 20) )
      {
        v61 = *(_DWORD *)(v11 + 56);
        if ( v61 )
        {
          v42 = 0;
          while ( 1 )
          {
            v12 = *(unsigned int *)(v11 + 4LL * v42 + 120);
            if ( (unsigned int)v12 < 0x80 )
              goto LABEL_71;
            v43 = *(unsigned int *)(v11 + 16);
            if ( (unsigned int)v12 >= (unsigned int)v43 )
              goto LABEL_71;
            v44 = v12 + v11;
            v45 = (unsigned int)v12;
            v46 = *(_DWORD *)(v12 + v11);
            if ( v46 == 64 )
              goto LABEL_69;
            LODWORD(v12) = v46 - 65;
            if ( (_DWORD)v12 )
              break;
            v12 = v45 + 56;
LABEL_70:
            if ( v12 <= v43 )
            {
              v41 = *(_BYTE *)(v44 + 9);
              goto LABEL_74;
            }
LABEL_71:
            if ( ++v42 >= v61 )
              goto LABEL_74;
          }
          if ( (_DWORD)v12 != 1 )
            goto LABEL_71;
LABEL_69:
          v12 = v45 + 40;
          goto LABEL_70;
        }
      }
    }
    else
    {
      v41 = *(_BYTE *)(v11 + 11);
      v35 = *(_BYTE **)(v11 + 32);
    }
LABEL_74:
    if ( v35 && v41 )
    {
      v12 = (unsigned __int64)&v35[v41];
      v47 = v35 + 8;
      if ( (unsigned __int8)((*v35 & 0x7F) - 114) > 1u )
      {
        if ( (unsigned __int64)v47 > v12 )
        {
          LOBYTE(v12) = 0;
        }
        else
        {
          v48 = v35 + 13;
          v49 = v41;
          v59 = v35[2] & 0xF;
          if ( (unsigned int)(unsigned __int8)v35[7] + 8 <= v41 )
            v49 = (unsigned __int8)v35[7] + 8;
          v12 = (unsigned __int64)&v35[v49];
          if ( (unsigned __int64)v48 <= v12 )
            v10 = v35[12];
          if ( (unsigned __int64)(v35 + 14) <= v12 )
          {
            v9 = *v48;
            LOBYTE(v12) = 1;
            v13 = v35[2] & 0xF;
            goto LABEL_9;
          }
          v9 = 0;
          LOBYTE(v12) = 1;
        }
        v13 = v59;
        goto LABEL_9;
      }
      if ( (unsigned __int64)v47 <= v12 )
      {
        LOBYTE(v12) = 1;
        v10 = v35[2];
        v13 = v35[1] & 0xF;
        v9 = v35[3];
        goto LABEL_9;
      }
    }
    LOBYTE(v12) = 0;
    v13 = 0;
    goto LABEL_9;
  }
  v62 = 0;
  v11 = 0;
  IoGetActivityIdIrp(a3, &v64);
  if ( a3->IoStatus.Status < 0 )
    ClasspWriteUpperLevelIOFailureEvent((int)&v64, a1, a3);
  v13 = 0;
  LOBYTE(v12) = 0;
LABEL_9:
  if ( (BYTE1(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x40) == 0 )
    return;
  if ( !v5 )
  {
    v15 = 0;
    LOBYTE(v14) = (_BYTE)a3;
    goto LABEL_14;
  }
  v14 = *(_QWORD *)(v5 + 48);
  v15 = *(unsigned __int8 *)(v7 + 660) - *(unsigned __int8 *)(v5 + 57);
  if ( !(_BYTE)v12 )
  {
LABEL_14:
    if ( !v5 )
    {
      v16 = 0;
      v17 = 0;
      v10 = 0;
      v9 = 0;
      v13 = 0;
      goto LABEL_16;
    }
    v9 = 0;
    if ( !(_BYTE)v12 )
    {
      v13 = 0;
      v10 = 0;
    }
  }
  if ( *(_BYTE *)(v11 + 2) != 40 )
  {
    v16 = *(_BYTE *)(v11 + 4);
LABEL_33:
    v17 = *(_BYTE *)(v11 + 3);
    goto LABEL_16;
  }
  v16 = 0;
  if ( *(_DWORD *)(v11 + 20) )
    goto LABEL_33;
  v50 = *(_DWORD *)(v11 + 56);
  if ( !v50 )
    goto LABEL_33;
  v51 = 0;
  while ( 1 )
  {
    v12 = *(unsigned int *)(v11 + 4LL * v51 + 120);
    if ( (unsigned int)v12 < 0x80 )
      goto LABEL_93;
    v52 = *(unsigned int *)(v11 + 16);
    if ( (unsigned int)v12 >= (unsigned int)v52 )
      goto LABEL_93;
    v53 = v12 + v11;
    v54 = (unsigned int)v12;
    v55 = *(_DWORD *)(v12 + v11);
    if ( v55 == 64 )
      goto LABEL_91;
    LODWORD(v12) = v55 - 65;
    if ( (_DWORD)v12 )
    {
      if ( (_DWORD)v12 != 1 )
        goto LABEL_93;
LABEL_91:
      v12 = v54 + 40;
      goto LABEL_92;
    }
    v12 = v54 + 56;
LABEL_92:
    if ( v12 <= v52 )
      break;
LABEL_93:
    v51 = v62 + 1;
    v62 = v51;
    if ( v51 >= v50 )
      goto LABEL_33;
  }
  v16 = *(_BYTE *)(v53 + 8);
  v17 = *(_BYTE *)(v11 + 3);
LABEL_16:
  McTemplateK0qpduuuuupq_EtwWriteTransfer(
    v12,
    v15,
    (unsigned int)&v64,
    *(_DWORD *)(v3 + 588),
    (char)a3,
    a3->IoStatus.Status,
    v17,
    v16,
    v13,
    v10,
    v9,
    v14,
    v15);
}

```

## disassembly

```asm
0x140005560  push    rbx
0x140005562  push    rbp
0x140005563  push    rsi
0x140005564  push    rdi
0x140005565  push    r15
0x140005567  sub     rsp, 0C0h
0x14000556e  mov     rax, cs:__security_cookie
0x140005575  xor     rax, rsp
0x140005578  mov     [rsp+0E8h+var_40], rax
0x140005580  cmp     cs:ClassPnPETWEnabled, 0
0x140005587  xorps   xmm0, xmm0
0x14000558a  mov     rsi, [rcx+40h]
0x14000558e  mov     rbp, r8
0x140005591  mov     rbx, rdx
0x140005594  mov     rdi, rcx
0x140005597  mov     r15, [rsi+478h]
0x14000559e  movups  [rsp+0E8h+var_50], xmm0
0x1400055a6  jz      short loc_1400055BA
0x1400055a8  mov     r8d, [r8+30h]
0x1400055ac  test    r8d, r8d
0x1400055af  js      short loc_1400055D9
0x1400055b1  test    byte ptr cs:WPP_MAIN_CB.Queue+39h, 40h
0x1400055b8  jnz     short loc_1400055D9
0x1400055ba  mov     rcx, [rsp+0E8h+var_40]
0x1400055c2  xor     rcx, rsp; StackCookie
0x1400055c5  call    __security_check_cookie
0x1400055ca  add     rsp, 0C0h
0x1400055d1  pop     r15
0x1400055d3  pop     rdi
0x1400055d4  pop     rsi
0x1400055d5  pop     rbp
0x1400055d6  pop     rbx
0x1400055d7  retn
0x1400055d9  mov     [rsp+0E8h+arg_18], r12
0x1400055e1  xor     r12b, r12b
0x1400055e4  mov     [rsp+0E8h+var_30], r13
0x1400055ec  xor     r13b, r13b
0x1400055ef  mov     [rsp+0E8h+var_38], r14
0x1400055f7  mov     [rsp+0E8h+var_78], 0
0x1400055fc  test    rbx, rbx
0x1400055ff  jnz     loc_1400056EA
0x140005605  xor     eax, eax
0x140005607  lea     rdx, [rsp+0E8h+var_50]
0x14000560f  mov     rcx, rbp
0x140005612  mov     [rsp+0E8h+var_60], rax
0x14000561a  mov     r14d, eax
0x14000561d  call    cs:__imp_IoGetActivityIdIrp
0x140005624  nop     dword ptr [rax+rax+00h]
0x140005629  cmp     [rbp+30h], r14d
0x14000562d  jge     short loc_140005642
0x14000562f  mov     r8, rbp
0x140005632  lea     rcx, [rsp+0E8h+var_50]
0x14000563a  mov     rdx, rdi
0x14000563d  call    ClasspWriteUpperLevelIOFailureEvent
0x140005642  xor     r10b, r10b
0x140005645  xor     cl, cl
0x140005647  test    byte ptr cs:WPP_MAIN_CB.Queue+39h, 40h
0x14000564e  jz      short loc_1400056CD
0x140005650  test    rbx, rbx
0x140005653  jz      short loc_140005670
0x140005655  movzx   eax, byte ptr [rbx+39h]
0x140005659  movzx   edx, byte ptr [r15+294h]
0x140005661  mov     r8, [rbx+30h]
0x140005665  sub     edx, eax
0x140005667  test    cl, cl
0x140005669  jz      short loc_140005675
0x14000566b  jmp     loc_1400057AD
0x140005670  xor     edx, edx
0x140005672  mov     r8, rbp
0x140005675  test    rbx, rbx
0x140005678  jnz     loc_14000578E
0x14000567e  xor     r9b, r9b
0x140005681  xor     al, al
0x140005683  xor     r13b, r13b
0x140005686  xor     r12b, r12b
0x140005689  xor     r10b, r10b
0x14000568c  mov     [rsp+0E8h+var_88], edx
0x140005690  mov     [rsp+0E8h+var_90], r8
0x140005695  lea     r8, [rsp+0E8h+var_50]
0x14000569d  mov     [rsp+0E8h+var_98], r12b
0x1400056a2  mov     [rsp+0E8h+var_A0], r13b
0x1400056a7  mov     [rsp+0E8h+var_A8], r10b
0x1400056ac  mov     [rsp+0E8h+var_B0], r9b
0x1400056b1  mov     r9d, [rsi+24Ch]
0x1400056b8  mov     [rsp+0E8h+var_B8], al
0x1400056bc  mov     eax, [rbp+30h]
0x1400056bf  mov     [rsp+0E8h+var_C0], eax
0x1400056c3  mov     [rsp+0E8h+var_C8], rbp
0x1400056c8  call    McTemplateK0qpduuuuupq_EtwWriteTransfer
0x1400056cd  mov     r13, [rsp+0E8h+var_30]
0x1400056d5  mov     r12, [rsp+0E8h+arg_18]
0x1400056dd  mov     r14, [rsp+0E8h+var_38]
0x1400056e5  jmp     loc_1400055BA
0x1400056ea  mov     rax, [rdx+30h]
0x1400056ee  xor     r10d, r10d
0x1400056f1  mov     r14, [rdx+120h]
0x1400056f8  mov     [rsp+0E8h+var_60], r10
0x140005700  mov     rax, [rax+0B8h]
0x140005707  mov     [rsp+0E8h+var_58], rax
0x14000570f  test    r8d, r8d
0x140005712  jns     loc_1400057C7
0x140005718  movzx   r9d, byte ptr [r14+2]
0x14000571d  cmp     r9b, 28h ; '('
0x140005721  jnz     loc_1400057D3
0x140005727  mov     r11d, r10d
0x14000572a  mov     [rsp+0E8h+var_70], r10
0x14000572f  cmp     [r14+14h], r10d
0x140005733  jnz     loc_1400057D7
0x140005739  mov     eax, [r14+38h]
0x14000573d  mov     [rsp+0E8h+var_74], eax
0x140005741  test    eax, eax
0x140005743  jz      loc_1400057D7
0x140005749  mov     ecx, [r14+r11*4+78h]
0x14000574e  cmp     ecx, 80h
0x140005754  jb      short loc_14000577D
0x140005756  mov     edx, [r14+10h]
0x14000575a  cmp     ecx, edx
0x14000575c  jnb     short loc_14000577D
0x14000575e  lea     rax, [rcx+r14]
0x140005762  mov     r10d, ecx
0x140005765  mov     ecx, [rax]
0x140005767  cmp     ecx, 40h ; '@'
0x14000576a  jnz     loc_140005AA4
0x140005770  lea     rcx, [r10+28h]
0x140005774  cmp     rcx, rdx
0x140005777  jbe     loc_140005B0D
0x14000577d  inc     r11d
0x140005780  cmp     r11d, [rsp+0E8h+var_74]
0x140005785  jb      short loc_140005749
0x140005787  mov     r11, [rsp+0E8h+var_70]
0x14000578c  jmp     short loc_1400057D7
0x14000578e  test    cl, cl
0x140005790  jz      loc_140005BC6
0x140005796  xor     r12b, r12b
0x140005799  jmp     short loc_1400057AD
0x14000579b  test    rbx, rbx
0x14000579e  jz      loc_14000567E
0x1400057a4  xor     r12b, r12b
0x1400057a7  xor     r10b, r10b
0x1400057aa  xor     r13b, r13b
0x1400057ad  cmp     byte ptr [r14+2], 28h ; '('
0x1400057b2  jz      loc_1400059F6
0x1400057b8  movzx   r9d, byte ptr [r14+4]
0x1400057bd  movzx   eax, byte ptr [r14+3]
0x1400057c2  jmp     loc_14000568C
0x1400057c7  lea     rdi, [rdx+148h]
0x1400057ce  jmp     loc_140005885
0x1400057d3  lea     r11, [r14+48h]
0x1400057d7  movzx   ecx, byte ptr [r11]
0x1400057db  cmp     cl, 1Eh
0x1400057de  jz      loc_140005B7D
0x1400057e4  lea     eax, [rcx-1Ah]
0x1400057e7  test    al, 0BFh
0x1400057e9  jz      loc_140005B7D
0x1400057ef  cmp     cl, 25h ; '%'
0x1400057f2  jz      loc_140005B7D
0x1400057f8  cmp     cl, 9Eh
0x1400057fb  jz      loc_140005B7D
0x140005801  lea     eax, [rcx-8]
0x140005804  test    al, 5Dh
0x140005806  jnz     loc_140005B6D
0x14000580c  test    r14, r14
0x14000580f  jz      short loc_140005830
0x140005811  cmp     r9b, 28h ; '('
0x140005815  mov     eax, 18h
0x14000581a  mov     ecx, 0Ch
0x14000581f  cmovnz  eax, ecx
0x140005822  test    dword ptr [rax+r14], 1000h
0x14000582a  jnz     loc_140005B8A
0x140005830  mov     rax, [rbx+28h]
0x140005834  mov     rcx, [rax+40h]
0x140005838  mov     rax, [rcx+478h]
0x14000583f  movzx   eax, byte ptr [rax+294h]
0x140005846  sub     al, [rbx+39h]
0x140005849  movzx   ecx, al
0x14000584c  cmp     r9b, 28h ; '('
0x140005850  jz      loc_140005C02
0x140005856  mov     eax, r9d
0x140005859  mov     byte ptr [rsp+0E8h+var_C8], cl
0x14000585d  mov     rdx, rdi
0x140005860  lea     rdi, [rbx+148h]
0x140005867  mov     r9, r14
0x14000586a  mov     rcx, rdi
0x14000586d  test    eax, eax
0x14000586f  jnz     loc_140005C0B
0x140005875  call    ClasspWriteScsiSrbErrorResultEvent
0x14000587a  mov     rax, [rsp+0E8h+var_58]
0x140005882  xor     r10d, r10d
0x140005885  mov     rdx, r14
0x140005888  mov     ecx, 2
0x14000588d  test    rax, rax
0x140005890  jz      loc_1400056CD
0x140005896  movzx   eax, byte ptr [rax]
0x140005899  sub     al, 3
0x14000589b  cmp     al, 1
0x14000589d  ja      loc_1400056CD
0x1400058a3  movups  xmm0, xmmword ptr [rdi]
0x1400058a6  movups  [rsp+0E8h+var_50], xmm0
0x1400058ae  cmp     byte ptr [rdx+rcx], 28h ; '('
0x1400058b2  jnz     loc_14000596B
0x1400058b8  cmp     dword ptr [r14+14h], 0
0x1400058bd  mov     rdx, r10
0x1400058c0  jnz     short loc_14000590E
0x1400058c2  mov     edi, [r14+38h]
0x1400058c6  test    edi, edi
0x1400058c8  jz      short loc_14000590E
0x1400058ca  mov     eax, r10d
0x1400058cd  mov     ecx, [r14+rax*4+78h]
0x1400058d2  cmp     ecx, 80h
0x1400058d8  jb      short loc_140005903
0x1400058da  mov     r8d, [r14+10h]
0x1400058de  cmp     ecx, r8d
0x1400058e1  jnb     short loc_140005903
0x1400058e3  lea     r11, [rcx+r14]
0x1400058e7  mov     r9d, ecx
0x1400058ea  mov     ecx, [r11]
0x1400058ed  cmp     ecx, 40h ; '@'
0x1400058f0  jnz     loc_140005A7C
0x1400058f6  lea     rcx, [r9+28h]
0x1400058fa  cmp     rcx, r8
0x1400058fd  jbe     loc_140005B04
0x140005903  inc     r10d
0x140005906  cmp     r10d, edi
0x140005909  jb      short loc_1400058CA
0x14000590b  xor     r10d, r10d
0x14000590e  xor     r8b, r8b
0x140005911  cmp     dword ptr [r14+14h], 0
0x140005916  jnz     short loc_140005974
0x140005918  mov     eax, [r14+38h]
0x14000591c  mov     [rsp+0E8h+var_74], eax
0x140005920  test    eax, eax
0x140005922  jz      short loc_140005974
0x140005924  mov     r11d, r10d
0x140005927  mov     eax, r11d
0x14000592a  mov     ecx, [r14+rax*4+78h]
0x14000592f  cmp     ecx, 80h
0x140005935  jb      short loc_14000595F
0x140005937  mov     r9d, [r14+10h]
0x14000593b  cmp     ecx, r9d
0x14000593e  jnb     short loc_14000595F
0x140005940  lea     rdi, [rcx+r14]
0x140005944  mov     r10d, ecx
0x140005947  mov     ecx, [rdi]
0x140005949  cmp     ecx, 40h ; '@'
0x14000594c  jnz     loc_140005A65
0x140005952  lea     rcx, [r10+28h]
0x140005956  cmp     rcx, r9
0x140005959  jbe     loc_140005AFA
0x14000595f  inc     r11d
0x140005962  cmp     r11d, [rsp+0E8h+var_74]
0x140005967  jb      short loc_140005927
0x140005969  jmp     short loc_140005974
0x14000596b  movzx   r8d, byte ptr [r14+0Bh]
0x140005970  mov     rdx, [r14+20h]
0x140005974  test    rdx, rdx
0x140005977  jz      loc_140005AF0
0x14000597d  test    r8b, r8b
0x140005980  jz      loc_140005AF0
0x140005986  movzx   eax, byte ptr [rdx]
0x140005989  and     al, 7Fh
0x14000598b  movzx   ecx, r8b
0x14000598f  sub     al, 72h ; 'r'
0x140005991  add     rcx, rdx
0x140005994  cmp     al, 1
0x140005996  lea     rax, [rdx+8]
0x14000599a  jbe     loc_140005B32
0x1400059a0  cmp     rax, rcx
0x1400059a3  ja      loc_140005C15
0x1400059a9  movzx   ecx, byte ptr [rdx+7]
0x1400059ad  lea     r12, [rdx+0Dh]
0x1400059b1  movzx   r9d, byte ptr [rdx+2]
0x1400059b6  add     ecx, 8
0x1400059b9  and     r9b, 0Fh
0x1400059bd  movzx   eax, r8b
0x1400059c1  cmp     ecx, eax
0x1400059c3  mov     [rsp+0E8h+var_78], r9b
0x1400059c8  cmovbe  eax, ecx
0x1400059cb  mov     ecx, eax
0x1400059cd  add     rcx, rdx
0x1400059d0  cmp     r12, rcx
0x1400059d3  jbe     loc_140005B51
0x1400059d9  lea     rax, [rdx+0Eh]
0x1400059dd  cmp     rax, rcx
0x1400059e0  jbe     loc_140005B5B
0x1400059e6  xor     r12b, r12b
0x1400059e9  mov     cl, 1
0x1400059eb  movzx   r10d, [rsp+0E8h+var_78]
0x1400059f1  jmp     loc_140005647
0x1400059f6  xor     r9b, r9b
0x1400059f9  cmp     dword ptr [r14+14h], 0
0x1400059fe  jnz     loc_1400057BD
0x140005a04  mov     edi, [r14+38h]
0x140005a08  test    edi, edi
0x140005a0a  jz      loc_1400057BD
0x140005a10  xor     eax, eax
0x140005a12  mov     eax, eax
0x140005a14  mov     ecx, [r14+rax*4+78h]
0x140005a19  cmp     ecx, 80h
0x140005a1f  jb      short loc_140005A49
0x140005a21  mov     r11d, [r14+10h]
  ... truncated ...
```
