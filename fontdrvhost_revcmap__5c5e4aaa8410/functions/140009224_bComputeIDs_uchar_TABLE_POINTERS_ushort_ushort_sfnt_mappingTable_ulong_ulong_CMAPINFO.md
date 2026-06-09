# bComputeIDs(uchar *,_TABLE_POINTERS *,ushort *,ushort *,sfnt_mappingTable * *,ulong *,ulong *,_CMAPINFO *)

- ea: `0x140009224`
- end: `0x140009669`
- name: `?bComputeIDs@@YAHPEAEPEAU_TABLE_POINTERS@@PEAG2PEAPEAUsfnt_mappingTable@@PEAK4PEAU_CMAPINFO@@@Z`
- size: `1093`
- prototype: `int(unsigned __int8 *, struct _TABLE_POINTERS *, unsigned __int16 *, unsigned __int16 *, struct sfnt_mappingTable **, unsigned int *, unsigned int *, struct _CMAPINFO *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140007104`
- `0x1400086b4`

## callees

- `0x140009224`
- `0x140046b40`
- `0x140067448`
- `0x140070fe0`
- `0x140091db8`
- `0x140091e78`
- `0x140091ec8`

## pseudocode

```c
__int64 __fastcall bComputeIDs(
        unsigned __int8 *a1,
        struct _TABLE_POINTERS *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct sfnt_mappingTable **a5,
        unsigned int *a6,
        unsigned int *a7,
        struct _CMAPINFO *a8)
{
  unsigned int v8; // r10d
  unsigned __int16 *v9; // r9
  unsigned __int16 *v11; // rsi
  unsigned __int16 v12; // r8
  unsigned __int16 v13; // cx
  struct sfnt_mappingTable **v14; // r12
  unsigned int *v15; // r15
  unsigned int *v16; // r14
  unsigned __int16 *v17; // rdi
  unsigned __int64 v18; // rax
  unsigned __int16 *v19; // rbx
  unsigned __int8 *v20; // rbp
  unsigned __int16 v21; // dx
  unsigned __int16 v22; // cx
  int v23; // r8d
  int v24; // eax
  unsigned __int64 v25; // r8
  int v26; // ecx
  int v27; // eax
  unsigned __int16 v28; // cx
  __int64 result; // rax
  BOOL v30; // eax
  unsigned __int8 *v31; // rcx
  unsigned __int16 *v32; // rcx
  int v33; // r8d
  int v34; // eax
  unsigned int v35; // r8d
  struct sfnt_mappingTable *v36; // rcx
  struct sfnt_mappingTable *v37; // r11
  bool v38; // cf
  unsigned int v39; // [rsp+50h] [rbp-58h]
  unsigned __int64 v40; // [rsp+58h] [rbp-50h]
  unsigned int v42; // [rsp+B8h] [rbp+10h] BYREF
  unsigned __int16 *v43; // [rsp+C0h] [rbp+18h]
  unsigned __int16 *v44; // [rsp+C8h] [rbp+20h]

  v44 = a4;
  v43 = a3;
  v8 = *((_DWORD *)a2 + 1);
  v9 = a3;
  v42 = 0;
  v39 = v8;
  if ( v8 < 6 )
    return 0;
  v11 = (unsigned __int16 *)&a1[*(unsigned int *)a2];
  v12 = _byteswap_ushort(v11[1]);
  v13 = _byteswap_ushort(*v11);
  if ( v12 > (v8 - 4) >> 3 )
    return 0;
  v14 = a5;
  v15 = a7;
  *a5 = 0;
  *v15 = 0;
  if ( v13 || v12 > 0x1Eu )
    return 0;
  v16 = a6;
  v17 = v11 + 2;
  v18 = (unsigned __int64)&v11[4 * v12 + 2];
  v19 = v11 + 2;
  v40 = v18;
  v20 = 0;
  while ( 1 )
  {
    if ( (unsigned __int64)v19 >= v18 )
    {
      if ( v20 )
      {
        v32 = v44;
        v33 = v20[6] | ((v20[5] | (v20[4] << 8)) << 8);
        v34 = v20[7];
        *v9 = 1;
        *v32 = 0;
        v35 = v34 | (v33 << 8);
        v36 = (struct sfnt_mappingTable *)((char *)v11 + v35);
        *v14 = v36;
        if ( (unsigned int)bVerifyMacTable(v36, v8, v35) )
        {
          v38 = (unsigned int)bCvtUnToMac(a1, a2, *v43) != 0;
          result = 1;
          *v16 = 2 - v38;
          return result;
        }
        *v14 = v37;
      }
      return 0;
    }
    v21 = _byteswap_ushort(v19[1]);
    v22 = _byteswap_ushort(*v19);
    if ( v22 == 3 )
      break;
    if ( v22 == 1 && !v21 && !v20 )
      v20 = (unsigned __int8 *)v19;
LABEL_28:
    v18 = v40;
    v19 += 4;
  }
  v23 = *((unsigned __int8 *)v19 + 6) | ((*((unsigned __int8 *)v19 + 5) | (*((unsigned __int8 *)v19 + 4) << 8)) << 8);
  v24 = *((unsigned __int8 *)v19 + 7);
  *v9 = 3;
  v25 = v24 | (unsigned int)(v23 << 8);
  *v44 = _byteswap_ushort(v19[1]);
  if ( v25 > (unsigned __int64)v8 - 6 )
    goto LABEL_28;
  *v14 = (struct sfnt_mappingTable *)((char *)v11 + v25);
  v26 = (*((unsigned __int8 *)v11 + v25) << 8) | *((unsigned __int8 *)v11 + v25 + 1);
  if ( v26 == 2 )
  {
    v27 = bVerifyMsftHighByteTable(
            (struct sfnt_mappingTable *)((char *)v11 + v25),
            v16,
            a8,
            _byteswap_ushort(v19[1]),
            v8,
            v25);
    goto LABEL_16;
  }
  if ( v26 != 4 )
  {
LABEL_29:
    *v14 = 0;
    goto LABEL_28;
  }
  if ( v21 != 1 && (v21 == 2 || v21 == 3 || (unsigned int)v21 - 4 < 2) )
    v27 = bVerifyMsftTableGeneral(
            (struct sfnt_mappingTable *)((char *)v11 + v25),
            v16,
            a8,
            _byteswap_ushort(v19[1]),
            v8,
            v25,
            (struct sfnt_char2IndexDirectory *)v11);
  else
    v27 = bVerifyMsftTable(
            (struct sfnt_mappingTable *)((char *)v11 + v25),
            v16,
            v15,
            a8,
            _byteswap_ushort(v19[1]),
            &v42,
            v8,
            v25,
            (struct sfnt_char2IndexDirectory *)v11);
LABEL_16:
  if ( !v27 )
  {
    v8 = v39;
    v9 = v43;
    goto LABEL_29;
  }
  *((_WORD *)a8 + 4) = _byteswap_ushort(v19[1]);
  v28 = _byteswap_ushort(v19[1]);
  if ( !v28 )
  {
    v30 = 0;
    if ( *((_DWORD *)a2 + 16) )
    {
      v31 = &a1[*((unsigned int *)a2 + 16)];
      if ( v31 && !v31[62] )
        v30 = v31[32] == 5;
    }
    else
    {
      v31 = 0;
    }
    if ( !*v15 && !v30 )
      goto LABEL_48;
    goto LABEL_47;
  }
  if ( v28 == 1 && *v15 )
  {
    if ( *((_DWORD *)a2 + 16) )
      v31 = &a1[*((unsigned int *)a2 + 16)];
    else
      v31 = 0;
LABEL_47:
    *v16 = 4;
LABEL_48:
    vDetectOldBiDiFonts((struct sfnt_OS2 *)v31, v42, v16, v15);
  }
  while ( v17 < v19 )
  {
    if ( _byteswap_ushort(*v17) == *v43 && _byteswap_ushort(v17[1]) == *v44 )
      return 0;
    v17 += 4;
  }
  return 1;
}

```

## disassembly

```asm
0x140009224  mov     rax, rsp
0x140009227  mov     [rax+20h], r9
0x14000922b  mov     [rax+18h], r8
0x14000922f  mov     [rax+8], rcx
0x140009233  push    rbx
0x140009234  push    rbp
0x140009235  push    rsi
0x140009236  push    rdi
0x140009237  push    r12
0x140009239  push    r13
0x14000923b  push    r14
0x14000923d  push    r15
0x14000923f  sub     rsp, 68h
0x140009243  mov     r10d, [rdx+4]
0x140009247  mov     r9, r8
0x14000924a  mov     dword ptr [rax+10h], 0
0x140009251  mov     r13, rdx
0x140009254  mov     [rsp+0A8h+var_58], r10d
0x140009259  cmp     r10d, 6
0x14000925d  jb      loc_1400094CF
0x140009263  mov     esi, [rdx]
0x140009265  add     rsi, rcx
0x140009268  movzx   eax, byte ptr [rsi+2]
0x14000926c  movzx   r8d, byte ptr [rsi+3]
0x140009271  movzx   ecx, byte ptr [rsi+1]
0x140009275  shl     ax, 8
0x140009279  or      r8w, ax
0x14000927d  movzx   eax, byte ptr [rsi]
0x140009280  shl     ax, 8
0x140009284  or      cx, ax
0x140009287  movzx   edx, r8w
0x14000928b  lea     eax, [r10-4]
0x14000928f  shr     eax, 3
0x140009292  cmp     edx, eax
0x140009294  ja      loc_1400094CF
0x14000929a  mov     r12, [rsp+0A8h+arg_20]
0x1400092a2  xor     r11d, r11d
0x1400092a5  mov     r15, [rsp+0A8h+arg_30]
0x1400092ad  mov     [r12], r11
0x1400092b1  mov     [r15], r11d
0x1400092b4  test    cx, cx
0x1400092b7  jnz     loc_1400094CF
0x1400092bd  cmp     edx, 1Eh
0x1400092c0  ja      loc_1400094CF
0x1400092c6  mov     r14, [rsp+0A8h+arg_28]
0x1400092ce  lea     rdi, [rsi+4]
0x1400092d2  lea     rax, [rdi+rdx*8]
0x1400092d6  mov     rbx, rdi
0x1400092d9  mov     [rsp+0A8h+var_50], rax
0x1400092de  lea     r8d, [r11+3]
0x1400092e2  mov     ebp, r11d
0x1400092e5  cmp     rbx, rax
0x1400092e8  jnb     loc_1400094C6
0x1400092ee  movzx   eax, byte ptr [rbx+3]
0x1400092f2  movzx   edx, byte ptr [rbx+2]
0x1400092f6  movzx   ecx, byte ptr [rbx]
0x1400092f9  shl     dx, 8
0x1400092fd  or      dx, ax
0x140009300  shl     cx, 8
0x140009304  movzx   eax, byte ptr [rbx+1]
0x140009308  or      cx, ax
0x14000930b  cmp     cx, r8w
0x14000930f  jnz     loc_140009493
0x140009315  movzx   eax, byte ptr [rbx+5]
0x140009319  movzx   r8d, byte ptr [rbx+4]
0x14000931e  shl     r8d, 8
0x140009322  or      r8d, eax
0x140009325  movzx   eax, byte ptr [rbx+6]
0x140009329  shl     r8d, 8
0x14000932d  or      r8d, eax
0x140009330  movzx   eax, byte ptr [rbx+7]
0x140009334  mov     word ptr [r9], 3
0x14000933a  movzx   ecx, byte ptr [rbx+2]
0x14000933e  shl     r8d, 8
0x140009342  or      r8d, eax
0x140009345  shl     cx, 8
0x140009349  movzx   eax, byte ptr [rbx+3]
0x14000934d  or      cx, ax
0x140009350  mov     rax, [rsp+0A8h+arg_18]
0x140009358  mov     [rax], cx
0x14000935b  mov     eax, r10d
0x14000935e  sub     rax, 6
0x140009362  cmp     r8, rax
0x140009365  ja      loc_1400094BE
0x14000936b  lea     r11, [r8+rsi]
0x14000936f  mov     [r12], r11
0x140009373  movzx   eax, byte ptr [r11]
0x140009377  movzx   ecx, byte ptr [r11+1]
0x14000937c  shl     eax, 8
0x14000937f  or      ecx, eax
0x140009381  cmp     ecx, 2
0x140009384  jz      loc_14000950C
0x14000938a  cmp     ecx, 4
0x14000938d  jnz     loc_1400094B7
0x140009393  movzx   ecx, dx
0x140009396  sub     ecx, 1
0x140009399  jz      short loc_1400093BF
0x14000939b  sub     ecx, 1
0x14000939e  jz      loc_1400094D3
0x1400093a4  sub     ecx, 1
0x1400093a7  jz      loc_1400094D3
0x1400093ad  sub     ecx, 1
0x1400093b0  jz      loc_1400094D3
0x1400093b6  cmp     ecx, 1
0x1400093b9  jz      loc_1400094D3
0x1400093bf  movzx   ecx, byte ptr [rbx+2]
0x1400093c3  mov     rdx, r14; unsigned int *
0x1400093c6  movzx   eax, byte ptr [rbx+3]
0x1400093ca  mov     r9, [rsp+0A8h+arg_38]; struct _CMAPINFO *
0x1400093d2  mov     [rsp+0A8h+var_68], rsi; struct sfnt_char2IndexDirectory *
0x1400093d7  mov     [rsp+0A8h+var_70], r8d; unsigned int
0x1400093dc  mov     r8, r15; unsigned int *
0x1400093df  shl     cx, 8
0x1400093e3  or      cx, ax
0x1400093e6  mov     dword ptr [rsp+0A8h+var_78], r10d; unsigned int
0x1400093eb  lea     rax, [rsp+0A8h+arg_8]
0x1400093f3  mov     [rsp+0A8h+var_80], rax; unsigned int *
0x1400093f8  mov     word ptr [rsp+0A8h+var_88], cx; unsigned __int16
0x1400093fd  mov     rcx, r11; struct sfnt_mappingTable *
0x140009400  call    ?bVerifyMsftTable@@YAHPEAUsfnt_mappingTable@@PEAK1PEAU_CMAPINFO@@G1IIPEAUsfnt_char2IndexDirectory@@@Z; bVerifyMsftTable(sfnt_mappingTable *,ulong *,ulong *,_CMAPINFO *,ushort,ulong *,uint,uint,sfnt_char2IndexDirectory *)
0x140009405  xor     r11d, r11d
0x140009408  test    eax, eax
0x14000940a  jz      loc_140009540
0x140009410  movzx   ecx, byte ptr [rbx+2]
0x140009414  movzx   eax, byte ptr [rbx+3]
0x140009418  shl     cx, 8
0x14000941c  or      cx, ax
0x14000941f  mov     rax, [rsp+0A8h+arg_38]
0x140009427  mov     [rax+8], cx
0x14000942b  movzx   ecx, byte ptr [rbx+2]
0x14000942f  movzx   eax, byte ptr [rbx+3]
0x140009433  shl     cx, 8
0x140009437  or      cx, ax
0x14000943a  jz      loc_140009552
0x140009440  lea     eax, [r11+1]
0x140009444  cmp     cx, ax
0x140009447  jnz     short loc_140009452
0x140009449  cmp     [r15], r11d
0x14000944c  jnz     loc_14000958A
0x140009452  mov     r8, [rsp+0A8h+arg_10]
0x14000945a  cmp     rdi, rbx
0x14000945d  jnb     short loc_14000947D
0x14000945f  movzx   ecx, byte ptr [rdi]
0x140009462  movzx   eax, byte ptr [rdi+1]
0x140009466  shl     cx, 8
0x14000946a  or      cx, ax
0x14000946d  cmp     cx, [r8]
0x140009471  jz      loc_1400095BF
0x140009477  add     rdi, 8
0x14000947b  jmp     short loc_14000945A
0x14000947d  mov     eax, 1
0x140009482  add     rsp, 68h
0x140009486  pop     r15
0x140009488  pop     r14
0x14000948a  pop     r13
0x14000948c  pop     r12
0x14000948e  pop     rdi
0x14000948f  pop     rsi
0x140009490  pop     rbp
0x140009491  pop     rbx
0x140009492  retn
0x140009493  mov     eax, 1
0x140009498  cmp     cx, ax
0x14000949b  jnz     short loc_1400094A9
0x14000949d  test    dx, dx
0x1400094a0  jnz     short loc_1400094A9
0x1400094a2  test    rbp, rbp
0x1400094a5  cmovz   rbp, rbx
0x1400094a9  mov     rax, [rsp+0A8h+var_50]
0x1400094ae  add     rbx, 8
0x1400094b2  jmp     loc_1400092E5
0x1400094b7  xor     r11d, r11d
0x1400094ba  mov     [r12], r11
0x1400094be  mov     r8d, 3
0x1400094c4  jmp     short loc_1400094A9
0x1400094c6  test    rbp, rbp
0x1400094c9  jnz     loc_1400095E4
0x1400094cf  xor     eax, eax
0x1400094d1  jmp     short loc_140009482
0x1400094d3  movzx   r9d, byte ptr [rbx+2]
0x1400094d8  mov     rdx, r14; unsigned int *
0x1400094db  movzx   eax, byte ptr [rbx+3]
0x1400094df  mov     rcx, r11; struct sfnt_mappingTable *
0x1400094e2  shl     r9w, 8
0x1400094e7  mov     [rsp+0A8h+var_78], rsi; struct sfnt_char2IndexDirectory *
0x1400094ec  or      r9w, ax; unsigned __int16
0x1400094f0  mov     dword ptr [rsp+0A8h+var_80], r8d; unsigned int
0x1400094f5  mov     r8, [rsp+0A8h+arg_38]; struct _CMAPINFO *
0x1400094fd  mov     [rsp+0A8h+var_88], r10d; unsigned int
0x140009502  call    ?bVerifyMsftTableGeneral@@YAHPEAUsfnt_mappingTable@@PEAKPEAU_CMAPINFO@@GIIPEAUsfnt_char2IndexDirectory@@@Z; bVerifyMsftTableGeneral(sfnt_mappingTable *,ulong *,_CMAPINFO *,ushort,uint,uint,sfnt_char2IndexDirectory *)
0x140009507  jmp     loc_140009405
0x14000950c  movzx   r9d, byte ptr [rbx+2]
0x140009511  mov     rdx, r14; unsigned int *
0x140009514  movzx   eax, byte ptr [rbx+3]
0x140009518  mov     rcx, r11; struct sfnt_mappingTable *
0x14000951b  mov     dword ptr [rsp+0A8h+var_80], r8d; unsigned int
0x140009520  mov     r8, [rsp+0A8h+arg_38]; struct _CMAPINFO *
0x140009528  shl     r9w, 8
0x14000952d  or      r9w, ax; unsigned __int16
0x140009531  mov     [rsp+0A8h+var_88], r10d; unsigned int
0x140009536  call    ?bVerifyMsftHighByteTable@@YAHPEAUsfnt_mappingTable@@PEAKPEAU_CMAPINFO@@GII@Z; bVerifyMsftHighByteTable(sfnt_mappingTable *,ulong *,_CMAPINFO *,ushort,uint,uint)
0x14000953b  jmp     loc_140009405
0x140009540  mov     r10d, [rsp+0A8h+var_58]
0x140009545  mov     r9, [rsp+0A8h+arg_10]
0x14000954d  jmp     loc_1400094BA
0x140009552  mov     eax, r11d
0x140009555  cmp     [r13+40h], r11d
0x140009559  jz      short loc_14000957C
0x14000955b  mov     ecx, [r13+40h]
0x14000955f  add     rcx, [rsp+0A8h+arg_0]
0x140009567  jz      short loc_14000957F
0x140009569  cmp     [rcx+3Eh], r11b
0x14000956d  jnz     short loc_14000957F
0x14000956f  cmp     byte ptr [rcx+20h], 5
0x140009573  jnz     short loc_14000957F
0x140009575  mov     eax, 1
0x14000957a  jmp     short loc_14000957F
0x14000957c  mov     rcx, r11
0x14000957f  cmp     [r15], r11d
0x140009582  jnz     short loc_1400095A1
0x140009584  test    eax, eax
0x140009586  jnz     short loc_1400095A1
0x140009588  jmp     short loc_1400095A8
0x14000958a  cmp     [r13+40h], r11d
0x14000958e  jz      short loc_14000959E
0x140009590  mov     ecx, [r13+40h]
0x140009594  add     rcx, [rsp+0A8h+arg_0]
0x14000959c  jmp     short loc_1400095A1
0x14000959e  mov     rcx, r11; struct sfnt_OS2 *
0x1400095a1  mov     dword ptr [r14], 4
0x1400095a8  mov     edx, [rsp+0A8h+arg_8]; unsigned int
0x1400095af  mov     r9, r15; unsigned int *
0x1400095b2  mov     r8, r14; unsigned int *
0x1400095b5  call    ?vDetectOldBiDiFonts@@YAXPEAUsfnt_OS2@@KPEAK1@Z; vDetectOldBiDiFonts(sfnt_OS2 *,ulong,ulong *,ulong *)
0x1400095ba  jmp     loc_140009452
0x1400095bf  movzx   eax, byte ptr [rdi+2]
0x1400095c3  movzx   ecx, byte ptr [rdi+3]
0x1400095c7  shl     ax, 8
0x1400095cb  or      cx, ax
0x1400095ce  mov     rax, [rsp+0A8h+arg_18]
0x1400095d6  cmp     cx, [rax]
0x1400095d9  jz      loc_1400094CF
0x1400095df  jmp     loc_140009477
0x1400095e4  movzx   eax, byte ptr [rbp+5]
0x1400095e8  mov     ebx, 1
0x1400095ed  movzx   r8d, byte ptr [rbp+4]
0x1400095f2  mov     edx, r10d; unsigned int
0x1400095f5  mov     rcx, [rsp+0A8h+arg_18]
0x1400095fd  shl     r8d, 8
0x140009601  or      r8d, eax
0x140009604  movzx   eax, byte ptr [rbp+6]
0x140009608  shl     r8d, 8
0x14000960c  or      r8d, eax
0x14000960f  movzx   eax, byte ptr [rbp+7]
0x140009613  mov     [r9], bx
0x140009617  mov     [rcx], r11w
0x14000961b  shl     r8d, 8
0x14000961f  or      r8d, eax; unsigned int
0x140009622  lea     rcx, [r8+rsi]; struct sfnt_mappingTable *
0x140009626  mov     [r12], rcx
0x14000962a  call    ?bVerifyMacTable@@YAHPEAUsfnt_mappingTable@@II@Z; bVerifyMacTable(sfnt_mappingTable *,uint,uint)
0x14000962f  test    eax, eax
0x140009631  jnz     short loc_14000963C
0x140009633  mov     [r12], r11
0x140009637  jmp     loc_1400094CF
0x14000963c  mov     r8, [rsp+0A8h+arg_10]
0x140009644  mov     rdx, r13; struct _TABLE_POINTERS *
0x140009647  mov     rcx, [rsp+0A8h+arg_0]; unsigned __int8 *
0x14000964f  movzx   r8d, word ptr [r8]; unsigned __int16
0x140009653  call    ?bCvtUnToMac@@YAHPEAEPEAU_TABLE_POINTERS@@G@Z; bCvtUnToMac(uchar *,_TABLE_POINTERS *,ushort)
0x140009658  neg     eax
0x14000965a  mov     eax, ebx
0x14000965c  sbb     ecx, ecx
0x14000965e  add     ecx, 2
0x140009661  mov     [r14], ecx
0x140009664  jmp     loc_140009482
```
