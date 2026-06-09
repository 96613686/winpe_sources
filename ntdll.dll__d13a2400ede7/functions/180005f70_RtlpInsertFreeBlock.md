# RtlpInsertFreeBlock

- ea: `0x180005f70`
- end: `0x1800067e6`
- name: `RtlpInsertFreeBlock`
- size: `2166`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004770`
- `0x1800050f0`
- `0x180008488`
- `0x180045608`
- `0x180088294`
- `0x1801012d0`

## callees

- `0x180005f70`
- `0x180007060`
- `0x180007cb0`
- `0x18011d208`

## string_xrefs

- `0x18000655c`: `((FreeBlock->Flags & HEAP_ENTRY_DECOMMITTED) || (ROUND_UP_TO_POWER2(FreeBlock, PAGE_SIZE) == (ULONG_PTR)FreeBlock))`

## pseudocode

```c
void __fastcall RtlpInsertFreeBlock(unsigned __int64 a1, unsigned __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rbx
  __int16 v5; // di
  __int64 v6; // rax
  unsigned __int64 v7; // r12
  char v8; // al
  unsigned __int16 v9; // si
  char v10; // cl
  __int64 v11; // rdx
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // r15
  unsigned __int64 v14; // rdx
  _DWORD *v15; // r8
  __int64 *v16; // rdi
  _QWORD *v17; // rdx
  unsigned __int64 v18; // rax
  int v19; // r14d
  int v20; // r11d
  _QWORD *v21; // rsi
  _DWORD *v22; // r9
  _QWORD *v23; // rax
  int v24; // ebp
  _DWORD *v25; // rdx
  __int64 v26; // r8
  int v27; // ebp
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // r8
  unsigned int v31; // edx
  __int64 v32; // r10
  int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // eax
  _QWORD *v36; // r14
  __int64 *v37; // rax
  _QWORD *v38; // r15
  __int64 *v39; // rdi
  unsigned __int64 v40; // rbp
  unsigned __int64 v41; // rax
  int v42; // ecx
  int v43; // edx
  unsigned int v44; // esi
  __int64 v45; // rax
  __int64 v46; // r12
  __int64 v47; // r14
  _DWORD *v48; // rdx
  int v49; // ecx
  unsigned __int16 v50; // ax
  int v51; // edx
  _QWORD *i; // r15
  int v53; // ebp
  int v54; // [rsp+30h] [rbp-68h]
  unsigned __int16 v55; // [rsp+34h] [rbp-64h]
  int v56; // [rsp+38h] [rbp-60h]
  __int16 v57; // [rsp+38h] [rbp-60h]
  _DWORD *v58; // [rsp+40h] [rbp-58h]
  unsigned __int64 v59; // [rsp+48h] [rbp-50h]
  _DWORD *v60; // [rsp+50h] [rbp-48h]
  unsigned __int64 v61; // [rsp+58h] [rbp-40h]
  unsigned __int64 v62; // [rsp+B0h] [rbp+18h]
  char v63; // [rsp+B8h] [rbp+20h]

  if ( a3 )
  {
    v62 = a3;
    v3 = a2;
    v5 = *(_WORD *)(a1 + 140) ^ *(_WORD *)(a2 + 12);
    if ( !v5
      && RtlpHeapErrorHandlerThreshold >= 1
      && (*(_BYTE *)(a2 + 10) & 8) == 0
      && ((a2 + 4095) & 0xFFFFFFFFFFFFF000uLL) != a2 )
    {
      if ( NtCurrentPeb()->Ldr )
        DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink);
      else
        DbgPrint("HEAP: ");
      DbgPrint(
        "((FreeBlock->Flags & HEAP_ENTRY_DECOMMITTED) || (ROUND_UP_TO_POWER2(FreeBlock, PAGE_SIZE) == (ULONG_PTR)FreeBlock))");
      RtlpHeapHandleError(1);
      a3 = v62;
    }
    v6 = *(unsigned __int8 *)(v3 + 14);
    if ( (_BYTE)v6 )
      v7 = (v3 & 0xFFFFFFFFFFFF0000uLL) - (v6 << 16) + 0x10000;
    else
      v7 = a1;
    v8 = *(_BYTE *)(v3 + 10);
    v63 = v8;
    v59 = v7;
    while ( a3 )
    {
      if ( a3 > 0xFF00 )
      {
        v10 = 0;
        v9 = -272;
        if ( a3 != 65281 )
          v9 = -256;
      }
      else
      {
        v9 = a3;
        v10 = v8;
      }
      *(_BYTE *)(v3 + 10) = v10;
      *(_WORD *)(v3 + 12) = *(_WORD *)(a1 + 140) ^ v5;
      v11 = *(_QWORD *)(v7 + 40);
      v55 = v9;
      if ( v11 == v7 )
      {
        LOBYTE(v12) = 0;
      }
      else
      {
        v12 = ((v3 - v7) >> 16) + 1;
        if ( v12 >= 0xFE )
        {
          RtlpLogHeapFailure(3, v11, v3, v7, 0, 0);
          v10 = *(_BYTE *)(v3 + 10);
        }
      }
      *(_BYTE *)(v3 + 14) = v12;
      *(_BYTE *)(v3 + 10) = v10 & 0xF0;
      *(_WORD *)(v3 + 8) = v9;
      *(_BYTE *)(v3 + 11) = 0;
      v13 = v9;
      *(_BYTE *)(v3 + 15) = 0;
      v61 = v9;
      if ( (*(_BYTE *)(a1 + 112) & 0x40) != 0 )
      {
        v14 = (16 * (unsigned __int64)v9 - 32) >> 2;
        if ( v14 )
        {
          v15 = (_DWORD *)(v3 + 32);
          if ( (((_BYTE)v3 + 32) & 4) != 0 )
          {
            --v14;
            *v15 = -17891602;
            v15 = (_DWORD *)(v3 + 36);
          }
          memset64(v15, 0xFEEEFEEEFEEEFEEEuLL, v14 >> 1);
          if ( (v14 & 1) != 0 )
            v15[v14 - 1] = -17891602;
        }
        *(_BYTE *)(v3 + 10) |= 4u;
      }
      v16 = *(__int64 **)(a1 + 312);
      v17 = (_QWORD *)(a1 + 336);
      if ( v16 )
      {
        while ( 1 )
        {
          v18 = *((unsigned int *)v16 + 2);
          if ( v9 < v18 )
          {
            v19 = v9;
            goto LABEL_26;
          }
          if ( !*v16 )
            break;
          v16 = (__int64 *)*v16;
        }
        v19 = v18 - 1;
LABEL_26:
        v20 = v9;
        v54 = v9;
        while ( 2 )
        {
          v21 = (_QWORD *)v16[4];
          v22 = (_DWORD *)(a1 + 124);
          v58 = (_DWORD *)(a1 + 124);
          v23 = (_QWORD *)v21[1];
          if ( v21 == v23 )
          {
            v36 = (_QWORD *)v16[4];
            v54 = v13;
            v20 = v13;
          }
          else
          {
            v24 = *((_DWORD *)v23 - 2);
            v25 = (_DWORD *)(a1 + 136);
            v56 = *((_DWORD *)v16 + 6);
            v60 = (_DWORD *)(a1 + 136);
            if ( *v22 )
            {
              v24 ^= *v25;
              if ( HIBYTE(v24) == ((unsigned __int8)v24 ^ (unsigned __int8)(BYTE1(v24) ^ BYTE2(v24))) )
              {
                v60 = (_DWORD *)(a1 + 136);
              }
              else
              {
                RtlpLogHeapFailure(3, a1, (_DWORD)v23 - 16, 0, 0, 0);
                v25 = (_DWORD *)(a1 + 136);
                v20 = v54;
                v22 = (_DWORD *)(a1 + 124);
              }
            }
            if ( (int)(v13 - (unsigned __int16)v24) > 0 )
            {
              v36 = v21;
            }
            else
            {
              v26 = *v21 - 16LL;
              v27 = *(_DWORD *)(v26 + 8);
              if ( *v22 )
              {
                v27 ^= *v25;
                if ( HIBYTE(v27) != ((unsigned __int8)v27 ^ (unsigned __int8)(BYTE1(v27) ^ BYTE2(v27))) )
                {
                  RtlpLogHeapFailure(3, a1, v26, 0, 0, 0);
                  v20 = v54;
                  v22 = (_DWORD *)(a1 + 124);
                }
              }
              if ( v20 - (unsigned __int16)v27 <= 0 )
              {
                v36 = (_QWORD *)*v21;
                goto LABEL_45;
              }
              v28 = (unsigned int)(v19 - v56);
              if ( *v16 || v19 != *((_DWORD *)v16 + 2) - 1 )
              {
                v29 = v16[5];
                v30 = (unsigned int)v28 >> 5;
                v31 = *(_DWORD *)(v29 + 4 * v30) & (-1 << (v19 - v56));
                v32 = v29 + 4 * v30;
                if ( v31 )
                {
LABEL_39:
                  if ( (_WORD)v31 )
                  {
                    if ( (_BYTE)v31 )
                      v33 = (unsigned __int8)RtlpBitsClearLow[(unsigned __int8)v31];
                    else
                      v33 = (unsigned __int8)RtlpBitsClearLow[BYTE1(v31)] + 8;
                  }
                  else if ( (v31 & 0xFF0000) != 0 )
                  {
                    v33 = (unsigned __int8)RtlpBitsClearLow[BYTE2(v31)] + 16;
                  }
                  else
                  {
                    v33 = (unsigned __int8)RtlpBitsClearLow[(unsigned __int64)v31 >> 24] + 24;
                  }
                  v22 = (_DWORD *)(a1 + 124);
                  v34 = 32 * v30 + v33;
                  v35 = 2 * v34;
                  if ( !*((_DWORD *)v16 + 3) )
                    v35 = v34;
                  v36 = *(_QWORD **)(v16[6] + 8LL * v35);
                  goto LABEL_45;
                }
                while ( (unsigned int)v30 <= ((unsigned int)(*((_DWORD *)v16 + 2) - *((_DWORD *)v16 + 6)) >> 5) - 1 )
                {
                  v31 = *(_DWORD *)(v32 + 4);
                  v32 += 4;
                  LODWORD(v30) = v30 + 1;
                  if ( v31 )
                    goto LABEL_39;
                }
                v54 = v20;
LABEL_71:
                v16 = (__int64 *)*v16;
                v19 = *((_DWORD *)v16 + 6);
                continue;
              }
              v36 = 0;
              if ( *((_DWORD *)v16 + 3) )
                v28 = (unsigned int)(2 * v28);
              for ( i = *(_QWORD **)(v16[6] + 8 * v28); v21 != i; i = (_QWORD *)*i )
              {
                v53 = *((_DWORD *)i - 2);
                if ( *v22 )
                {
                  v53 ^= *v60;
                  if ( HIBYTE(v53) != ((unsigned __int8)v53 ^ (unsigned __int8)(BYTE1(v53) ^ BYTE2(v53))) )
                  {
                    RtlpLogHeapFailure(3, a1, (_DWORD)i - 16, 0, 0, 0);
                    v20 = v54;
                    v22 = (_DWORD *)(a1 + 124);
                  }
                }
                if ( v20 - (unsigned __int16)v53 <= 0 )
                {
                  v36 = i;
                  break;
                }
              }
              v13 = v61;
LABEL_45:
              v58 = v22;
            }
            v54 = v20;
          }
          break;
        }
        if ( v36 )
        {
          v7 = v59;
          v17 = (_QWORD *)(a1 + 336);
          goto LABEL_49;
        }
        goto LABEL_71;
      }
      v36 = (_QWORD *)*v17;
      v22 = (_DWORD *)(a1 + 124);
      v58 = (_DWORD *)(a1 + 124);
LABEL_49:
      while ( v17 != v36 )
      {
        if ( *v22 )
        {
          v49 = *((_DWORD *)v36 - 2);
          if ( (v49 & *v22) != 0 )
            v50 = v49 ^ *(_WORD *)(a1 + 136);
          else
            v50 = *((_DWORD *)v36 - 2);
        }
        else
        {
          v50 = *((_WORD *)v36 - 4);
        }
        if ( v13 <= v50 )
          break;
        v36 = (_QWORD *)*v36;
      }
      v37 = (__int64 *)v36[1];
      v38 = (_QWORD *)(v3 + 16);
      if ( (_QWORD *)*v37 == v36 )
      {
        *v38 = v36;
        *(_QWORD *)(v3 + 24) = v37;
        *v37 = (__int64)v38;
        v36[1] = v38;
      }
      else
      {
        RtlpLogHeapFailure(13, 0, (_DWORD)v36, 0, *v37, 0);
        v22 = v58;
      }
      *(_QWORD *)(a1 + 192) += *(unsigned __int16 *)(v3 + 8);
      v39 = *(__int64 **)(a1 + 312);
      if ( v39 )
      {
        v40 = *(unsigned __int16 *)(v3 + 8);
        while ( 1 )
        {
          v41 = *((unsigned int *)v39 + 2);
          if ( v40 < v41 )
          {
            v42 = *(unsigned __int16 *)(v3 + 8);
            v43 = v41 - 1;
            goto LABEL_58;
          }
          if ( !*v39 )
            break;
          v39 = (__int64 *)*v39;
        }
        v42 = v41 - 1;
        v43 = v41 - 1;
LABEL_58:
        ++*((_DWORD *)v39 + 4);
        v44 = v42 - *((_DWORD *)v39 + 6);
        v45 = 2 * v44;
        if ( !*((_DWORD *)v39 + 3) )
          v45 = v44;
        v46 = 8 * v45;
        v47 = *(_QWORD *)(8 * v45 + v39[6]);
        if ( v42 == v43 )
          ++*((_DWORD *)v39 + 5);
        if ( !v47 )
          goto LABEL_63;
        v51 = *(_DWORD *)(v47 - 8);
        if ( *v22 )
        {
          v51 ^= *(_DWORD *)(a1 + 136);
          v57 = v51;
          if ( HIBYTE(v51) != ((unsigned __int8)v51 ^ (unsigned __int8)(BYTE1(v51) ^ BYTE2(v51))) )
          {
            RtlpLogHeapFailure(3, a1, v47 - 16, 0, 0, 0);
            LOWORD(v51) = v57;
            v22 = v58;
          }
        }
        if ( (int)(v40 - (unsigned __int16)v51) > 0 )
        {
          v7 = v59;
        }
        else
        {
LABEL_63:
          *(_QWORD *)(v46 + v39[6]) = v38;
          v7 = v59;
          if ( !v47 )
          {
            v48 = (_DWORD *)(v39[5] + 4 * ((unsigned __int64)v44 >> 5));
            *v48 |= 1 << (v44 & 0x1F);
          }
        }
      }
      if ( *v22 )
      {
        *(_BYTE *)(v3 + 11) = *(_BYTE *)(v3 + 8) ^ *(_BYTE *)(v3 + 9) ^ *(_BYTE *)(v3 + 10);
        *(_DWORD *)(v3 + 8) ^= *(_DWORD *)(a1 + 136);
      }
      v5 = v55;
      a3 = v62 - v61;
      v3 += 16 * v61;
      v62 -= v61;
      v8 = v63;
      if ( v3 >= *(_QWORD *)(v7 + 72) )
        return;
    }
    *(_WORD *)(v3 + 12) = *(_WORD *)(a1 + 140) ^ v5;
    if ( !v5 && RtlpHeapErrorHandlerThreshold >= 1 && ((v3 + 4095) & 0xFFFFFFFFFFFFF000uLL) != v3 )
    {
      if ( NtCurrentPeb()->Ldr )
        DbgPrint("HEAP[%wZ]: ", &NtCurrentPeb()->Ldr->InLoadOrderModuleList.Flink[5].Blink, 0, 0xFEEEFEEEFEEEFEEEuLL);
      else
        DbgPrint("HEAP: ", 65280, 0, 0xFEEEFEEEFEEEFEEEuLL);
      DbgPrint("ROUND_UP_TO_POWER2(FreeBlock, PAGE_SIZE) == (ULONG_PTR)FreeBlock");
      RtlpHeapHandleError(1);
    }
  }
}

```

## disassembly

```asm
0x180005f70  test    r8, r8
0x180005f73  jz      locret_180006115
0x180005f79  mov     rax, rsp
0x180005f7c  mov     [rax+18h], r8
0x180005f80  push    rbx
0x180005f81  push    r13
0x180005f83  sub     rsp, 88h
0x180005f8a  mov     [rax+8], rbp
0x180005f8e  mov     rbx, rdx
0x180005f91  mov     [rax-18h], rsi
0x180005f95  mov     r13, rcx
0x180005f98  mov     [rax-20h], rdi
0x180005f9c  movzx   edi, word ptr [rdx+0Ch]
0x180005fa0  xor     di, [rcx+8Ch]
0x180005fa7  mov     [rax-28h], r12
0x180005fab  mov     [rax-30h], r14
0x180005faf  mov     [rax-38h], r15
0x180005fb3  jz      loc_18000650F
0x180005fb9  movzx   eax, byte ptr [rbx+0Eh]
0x180005fbd  test    al, al
0x180005fbf  jnz     loc_180006401
0x180005fc5  mov     r12, r13
0x180005fc8  movzx   eax, byte ptr [rbx+0Ah]
0x180005fcc  mov     edx, 0FF00h
0x180005fd1  mov     [rsp+98h+arg_18], al
0x180005fd8  mov     r9, 0FEEEFEEEFEEEFEEEh
0x180005fe2  mov     [rsp+98h+var_50], r12
0x180005fe7  test    r8, r8
0x180005fea  jz      loc_1800060CF
0x180005ff0  cmp     r8, rdx
0x180005ff3  ja      loc_1800066F0
0x180005ff9  movzx   esi, r8w
0x180005ffd  movzx   ecx, al
0x180006000  mov     [rbx+0Ah], cl
0x180006003  xor     di, [r13+8Ch]
0x18000600b  mov     [rbx+0Ch], di
0x18000600f  mov     rdx, [r12+28h]
0x180006014  mov     [rsp+98h+var_64], esi
0x180006018  cmp     rdx, r12
0x18000601b  jz      loc_18000648A
0x180006021  mov     rdi, rbx
0x180006024  sub     rdi, r12
0x180006027  shr     rdi, 10h
0x18000602b  inc     rdi
0x18000602e  cmp     rdi, 0FEh
0x180006035  jnb     loc_18000677E
0x18000603b  and     cl, 0F0h
0x18000603e  mov     [rbx+0Eh], dil
0x180006042  mov     [rbx+0Ah], cl
0x180006045  mov     [rbx+8], si
0x180006049  mov     byte ptr [rbx+0Bh], 0
0x18000604d  movzx   r15d, si
0x180006051  mov     byte ptr [rbx+0Fh], 0
0x180006055  test    byte ptr [r13+70h], 40h
0x18000605a  mov     [rsp+98h+var_40], r15
0x18000605f  jz      short loc_18000609F
0x180006061  mov     edx, r15d
0x180006064  shl     rdx, 4
0x180006068  sub     rdx, 20h ; ' '
0x18000606c  shr     rdx, 2
0x180006070  test    rdx, rdx
0x180006073  jz      short loc_18000609B
0x180006075  lea     r8, [rbx+20h]
0x180006079  test    r8b, 4
0x18000607d  jnz     loc_1800067C5
0x180006083  mov     rcx, rdx
0x180006086  mov     rax, r9
0x180006089  shr     rcx, 1
0x18000608c  mov     rdi, r8
0x18000608f  rep stosq
0x180006092  test    dl, 1
0x180006095  jnz     loc_1800067D8
0x18000609b  or      byte ptr [rbx+0Ah], 4
0x18000609f  mov     rdi, [r13+138h]
0x1800060a6  lea     rdx, [r13+150h]
0x1800060ad  test    rdi, rdi
0x1800060b0  jz      loc_180006698
0x1800060b6  mov     eax, [rdi+8]
0x1800060b9  cmp     r15, rax
0x1800060bc  jb      short loc_180006117
0x1800060be  mov     rcx, [rdi]
0x1800060c1  test    rcx, rcx
0x1800060c4  jz      loc_180006492
0x1800060ca  mov     rdi, rcx
0x1800060cd  jmp     short loc_1800060B6
0x1800060cf  movzx   eax, di
0x1800060d2  xor     ax, [r13+8Ch]
0x1800060da  mov     [rbx+0Ch], ax
0x1800060de  test    di, di
0x1800060e1  jz      loc_18000657F
0x1800060e7  mov     r14, [rsp+98h+var_30]
0x1800060ec  mov     r12, [rsp+98h+var_28]
0x1800060f1  mov     rdi, [rsp+98h+var_20]
0x1800060f6  mov     rsi, [rsp+98h+var_18]
0x1800060fe  mov     rbp, [rsp+98h+arg_0]
0x180006106  mov     r15, [rsp+98h+var_38]
0x18000610b  add     rsp, 88h
0x180006112  pop     r13
0x180006114  pop     rbx
0x180006115  retn
0x180006117  mov     r14, r15
0x18000611a  mov     r11d, r15d
0x18000611d  mov     [rsp+98h+var_68], r15d
0x180006122  lea     r12, RtlpBitsClearLow; "\b"
0x180006129  mov     rsi, [rdi+20h]
0x18000612d  lea     r9, [r13+7Ch]
0x180006131  mov     [rsp+98h+var_58], r9
0x180006136  mov     rax, [rsi+8]
0x18000613a  cmp     rsi, rax
0x18000613d  jz      loc_1800066E0
0x180006143  mov     ebp, [rax-8]
0x180006146  lea     r8, [rax-10h]
0x18000614a  cmp     dword ptr [r9], 0
0x18000614e  lea     rdx, [r13+88h]
0x180006155  mov     ecx, [rdi+18h]
0x180006158  mov     [rsp+98h+var_60], ecx
0x18000615c  mov     [rsp+98h+var_48], rdx
0x180006161  jz      short loc_1800061B2
0x180006163  xor     ebp, [rdx]
0x180006165  mov     ecx, ebp
0x180006167  mov     eax, ebp
0x180006169  shr     eax, 8
0x18000616c  shr     ecx, 10h
0x18000616f  xor     cl, al
0x180006171  mov     eax, ebp
0x180006173  shr     eax, 18h
0x180006176  xor     cl, bpl
0x180006179  cmp     al, cl
0x18000617b  jz      loc_1800067B3
0x180006181  mov     [rsp+98h+var_70], 0
0x18000618a  xor     r9d, r9d
0x18000618d  mov     rdx, r13
0x180006190  mov     [rsp+98h+var_78], 0
0x180006199  mov     ecx, 3
0x18000619e  call    RtlpLogHeapFailure
0x1800061a3  mov     rdx, [rsp+98h+var_48]
0x1800061a8  mov     r11d, [rsp+98h+var_68]
0x1800061ad  mov     r9, [rsp+98h+var_58]
0x1800061b2  movzx   eax, bp
0x1800061b5  mov     ecx, r15d
0x1800061b8  sub     ecx, eax
0x1800061ba  test    ecx, ecx
0x1800061bc  jg      loc_18000672D
0x1800061c2  mov     r8, [rsi]
0x1800061c5  add     r8, 0FFFFFFFFFFFFFFF0h
0x1800061c9  mov     ebp, [r8+8]
0x1800061cd  cmp     dword ptr [r9], 0
0x1800061d1  jz      short loc_180006213
0x1800061d3  xor     ebp, [rdx]
0x1800061d5  mov     ecx, ebp
0x1800061d7  mov     eax, ebp
0x1800061d9  shr     eax, 8
0x1800061dc  shr     ecx, 10h
0x1800061df  xor     cl, al
0x1800061e1  mov     eax, ebp
0x1800061e3  shr     eax, 18h
0x1800061e6  xor     cl, bpl
0x1800061e9  cmp     al, cl
0x1800061eb  jz      short loc_180006213
0x1800061ed  xor     eax, eax
0x1800061ef  xor     r9d, r9d
0x1800061f2  mov     [rsp+98h+var_70], rax
0x1800061f7  mov     rdx, r13
0x1800061fa  mov     ecx, 3
0x1800061ff  mov     [rsp+98h+var_78], rax
0x180006204  call    RtlpLogHeapFailure
0x180006209  mov     r11d, [rsp+98h+var_68]
0x18000620e  mov     r9, [rsp+98h+var_58]
0x180006213  movzx   eax, bp
0x180006216  mov     ecx, r11d
0x180006219  sub     ecx, eax
0x18000621b  test    ecx, ecx
0x18000621d  jle     loc_18000667C
0x180006223  mov     ecx, r14d
0x180006226  sub     ecx, [rsp+98h+var_60]
0x18000622a  cmp     qword ptr [rdi], 0
0x18000622e  jnz     short loc_18000623E
0x180006230  mov     eax, [rdi+8]
0x180006233  dec     eax
0x180006235  cmp     r14d, eax
0x180006238  jz      loc_1800065DD
0x18000623e  mov     r9d, [rdi+8]
0x180006242  mov     r8d, ecx
0x180006245  sub     r9d, [rdi+18h]
0x180006249  mov     edx, 0FFFFFFFFh
0x18000624e  mov     rax, [rdi+28h]
0x180006252  shr     r8d, 5
0x180006256  shr     r9d, 5
0x18000625a  dec     r9d
0x18000625d  shl     edx, cl
0x18000625f  and     edx, [rax+r8*4]
0x180006263  lea     r10, [rax+r8*4]
0x180006267  jz      loc_180006760
0x18000626d  mov     ecx, edx
0x18000626f  test    dx, dx
0x180006272  jnz     loc_180006475
0x180006278  test    edx, 0FF0000h
0x18000627e  jnz     loc_180006684
0x180006284  shr     rcx, 18h
0x180006288  movzx   ecx, byte ptr [rcx+r12]
0x18000628d  add     ecx, 18h
0x180006290  mov     r9, [rsp+98h+var_58]
0x180006295  shl     r8d, 5
0x180006299  add     ecx, r8d
0x18000629c  cmp     dword ptr [rdi+0Ch], 0
0x1800062a0  lea     eax, [rcx+rcx]
0x1800062a3  cmovz   eax, ecx
0x1800062a6  mov     ecx, eax
0x1800062a8  mov     rax, [rdi+30h]
0x1800062ac  mov     r14, [rax+rcx*8]
0x1800062b0  mov     [rsp+98h+var_58], r9
0x1800062b5  mov     [rsp+98h+var_68], r11d
0x1800062ba  test    r14, r14
0x1800062bd  jz      loc_180006423
0x1800062c3  mov     r12, [rsp+98h+var_50]
0x1800062c8  lea     rdx, [r13+150h]
0x1800062cf  cmp     rdx, r14
0x1800062d2  jnz     loc_180006430
0x1800062d8  mov     rax, [r14+8]
0x1800062dc  lea     r15, [rbx+10h]
0x1800062e0  mov     rcx, [rax]
0x1800062e3  cmp     rcx, r14
0x1800062e6  jnz     loc_180006735
0x1800062ec  mov     [r15], r14
0x1800062ef  mov     [r15+8], rax
0x1800062f3  mov     [rax], r15
0x1800062f6  mov     [r14+8], r15
0x1800062fa  movzx   eax, word ptr [rbx+8]
0x1800062fe  add     [r13+0C0h], rax
0x180006305  mov     rdi, [r13+138h]
0x18000630c  test    rdi, rdi
0x18000630f  jz      loc_180006399
0x180006315  movzx   ebp, word ptr [rbx+8]
0x180006319  mov     eax, [rdi+8]
0x18000631c  cmp     rbp, rax
0x18000631f  jb      short loc_180006332
0x180006321  mov     rcx, [rdi]
0x180006324  test    rcx, rcx
0x180006327  jz      loc_18000646B
0x18000632d  mov     rdi, rcx
0x180006330  jmp     short loc_180006319
0x180006332  mov     ecx, ebp
0x180006334  lea     edx, [rax-1]
0x180006337  inc     dword ptr [rdi+10h]
0x18000633a  mov     esi, ecx
0x18000633c  sub     esi, [rdi+18h]
0x18000633f  cmp     dword ptr [rdi+0Ch], 0
0x180006343  lea     eax, [rsi+rsi]
0x180006346  cmovz   eax, esi
0x180006349  lea     r12, ds:0[rax*8]
0x180006351  mov     rax, [rdi+30h]
0x180006355  mov     r14, [r12+rax]
0x180006359  cmp     ecx, edx
0x18000635b  jnz     short loc_180006360
0x18000635d  inc     dword ptr [rdi+14h]
0x180006360  test    r14, r14
0x180006363  jnz     loc_18000649B
0x180006369  mov     rax, [rdi+30h]
0x18000636d  mov     [r12+rax], r15
0x180006371  mov     r12, [rsp+98h+var_50]
0x180006376  test    r14, r14
0x180006379  jnz     short loc_180006399
0x18000637b  mov     rax, [rdi+28h]
0x18000637f  mov     edx, esi
0x180006381  and     esi, 1Fh
0x180006384  shr     rdx, 5
0x180006388  movzx   ecx, sil
0x18000638c  lea     rdx, [rax+rdx*4]
0x180006390  mov     eax, 1
0x180006395  shl     eax, cl
0x180006397  or      [rdx], eax
0x180006399  cmp     dword ptr [r9], 0
0x18000639d  jz      short loc_1800063B6
0x18000639f  movzx   eax, byte ptr [rbx+0Ah]
0x1800063a3  xor     al, [rbx+9]
0x1800063a6  xor     al, [rbx+8]
0x1800063a9  mov     [rbx+0Bh], al
0x1800063ac  mov     eax, [r13+88h]
0x1800063b3  xor     [rbx+8], eax
0x1800063b6  mov     rax, [rsp+98h+var_40]
0x1800063bb  mov     edx, 0FF00h
0x1800063c0  mov     r8, [rsp+98h+arg_10]
0x1800063c8  mov     r9, 0FEEEFEEEFEEEFEEEh
0x1800063d2  movzx   edi, word ptr [rsp+98h+var_64]
0x1800063d7  sub     r8, rax
0x1800063da  shl     rax, 4
0x1800063de  add     rbx, rax
0x1800063e1  mov     [rsp+98h+arg_10], r8
0x1800063e9  movzx   eax, [rsp+98h+arg_18]
0x1800063f1  cmp     rbx, [r12+48h]
0x1800063f6  jb      loc_180005FE7
0x1800063fc  jmp     loc_1800060E7
0x180006401  shl     rax, 10h
0x180006405  mov     r12, rbx
0x180006408  and     r12, 0FFFFFFFFFFFF0000h
0x18000640f  sub     r12, rax
0x180006412  add     r12, 10000h
0x180006419  jmp     loc_180005FC8
0x18000641e  mov     [rsp+98h+var_68], r11d
0x180006423  mov     rdi, [rdi]
  ... truncated ...
```
