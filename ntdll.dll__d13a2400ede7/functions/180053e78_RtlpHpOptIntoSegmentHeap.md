# RtlpHpOptIntoSegmentHeap

- ea: `0x180053e78`
- end: `0x180055172`
- name: `RtlpHpOptIntoSegmentHeap`
- size: `4858`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800539a4`

## callees

- `0x180002c20`
- `0x180053180`
- `0x180053e78`
- `0x18009cb00`
- `0x1800e61b4`
- `0x180128940`
- `0x180162810`

## string_xrefs

- `0x180053f77`: `http://schemas.microsoft.com/SMI/2020/WindowsSettings`

## pseudocode

```c
__int64 __fastcall RtlpHpOptIntoSegmentHeap(__int64 a1, unsigned int *a2)
{
  char v2; // r15
  unsigned int *v3; // rsi
  __int64 v4; // r14
  struct _PEB *v5; // rdi
  _BYTE *pShimData; // rcx
  unsigned int v7; // edi
  __int64 v9; // rdx
  char v10; // r9
  char *v11; // rdx
  __int64 v12; // r11
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  bool v17; // al
  bool v18; // r10
  int v19; // eax
  char v20; // r10
  int v21; // eax
  char v22; // al
  char v23; // r10
  int v24; // eax
  char v25; // r10
  char v26; // al
  char v27; // r10
  char v28; // di
  __int64 v30; // [rsp+88h] [rbp-31h] BYREF
  struct _PEB *v31; // [rsp+90h] [rbp-29h]
  __int64 v32; // [rsp+98h] [rbp-21h]
  wchar_t String1[8]; // [rsp+A0h] [rbp-19h] BYREF
  __int128 v34; // [rsp+B0h] [rbp-9h]
  int v35; // [rsp+C0h] [rbp+7h]
  __int16 v36; // [rsp+C4h] [rbp+Bh]
  char v37; // [rsp+C6h] [rbp+Dh]
  __int64 v38; // [rsp+C7h] [rbp+Eh]
  char v39; // [rsp+CFh] [rbp+16h]
  __int64 v40; // [rsp+D0h] [rbp+17h]

  v2 = 8;
  v3 = a2;
  v32 = a1;
  v4 = a1;
  if ( (RtlpLowFragHeapGlobalFlags & 8) != 0 )
    return 0;
  if ( (RtlpLowFragHeapGlobalFlags & 0x10) == 0 )
  {
    v30 = 0;
    v5 = NtCurrentPeb();
    *a2 = 0;
    v31 = v5;
    pShimData = v5->pShimData;
    if ( !pShimData )
      goto LABEL_6;
    if ( *((_DWORD *)pShimData + 130) < 0x11C0u
      || !*((_DWORD *)pShimData + 1136)
      || (v9 = *((unsigned int *)pShimData + 1137), !(_DWORD)v9) )
    {
      if ( (pShimData[4530] & 4) != 0 )
      {
        if ( (pShimData[4522] & 0x40) != 0 )
        {
          *v3 = 1;
          return 1;
        }
        return 0;
      }
      goto LABEL_6;
    }
    v39 = 0;
    *(_DWORD *)String1 = 1114168;
    wmemcpy(&String1[2], L"«0", 2);
    LOBYTE(String1[4]) = 21;
    *(_DWORD *)((char *)&String1[4] + 1) = 0;
    *(wchar_t *)((char *)&String1[6] + 1) = 0;
    HIBYTE(String1[7]) = 0;
    v36 = 0;
    v10 = 26;
    v37 = 0;
    v35 = -65536;
    v38 = 436273155;
    v40 = 0;
    v34 = 0u;
    v11 = &pShimData[v9];
    if ( (unsigned __int8)v11[2] >> 4 != 1 )
      goto LABEL_75;
    if ( !v11[3] )
    {
      if ( v11[8] != 21 || *(_WORD *)v11 != 56 || v11[4] != -85 )
        goto LABEL_75;
      if ( !v11[3] )
      {
LABEL_20:
        v12 = *((unsigned __int16 *)v11 + 3) - 48LL;
        v28 = 2;
        if ( (unsigned __int8)v11[8] < 0xEu || (v13 = 1, (v11[v12 + 49] & 0x20) == 0) )
          v13 = 0;
        if ( v13 )
          v10 = v11[42] & 3 | 0x18;
        if ( (unsigned __int8)v11[8] < 0xFu || (v14 = 1, (v11[v12 + 49] & 0x40) == 0) )
          v14 = 0;
        if ( ((v40 & 0x4000) != 0) != v14 )
          v10 = v10 & 0xFB | (4 * ((v11[42] & 4) != 0));
        if ( (unsigned __int8)v11[8] < 0x10u || (v15 = 1, v11[v12 + 49] >= 0) )
          v15 = 0;
        if ( v15 )
          v10 = v10 & 0xF7 | (8 * ((v11[42] & 8) != 0));
        if ( (unsigned __int8)v11[8] < 0x11u || (v16 = 1, (v11[v12 + 50] & 1) == 0) )
          v16 = 0;
        if ( v16 )
          v10 = v10 & 0xEF | (16 * ((v11[42] & 0x10) != 0));
        v17 = (unsigned __int8)v11[8] >= 0x11u && (v11[v12 + 50] & 1) != 0;
        v18 = v17;
        if ( (unsigned __int8)v11[8] < 0x12u || (v19 = 1, (v11[v12 + 50] & 2) == 0) )
          v19 = 0;
        if ( v19 )
          v10 = v10 & 0xDF | (32 * ((v11[42] & 0x20) != 0));
        if ( (unsigned __int8)v11[8] < 0x12u || (v11[v12 + 50] & 2) == 0 )
          v28 = 0;
        v20 = v28 | v18 & 0xFD;
        if ( (unsigned __int8)v11[8] < 0x13u || (v21 = 1, (v11[v12 + 50] & 4) == 0) )
          v21 = 0;
        if ( v21 )
          v10 = v10 & 0xBF | (((v11[42] & 0x40) != 0) << 6);
        if ( (unsigned __int8)v11[8] >= 0x13u && (v11[v12 + 50] & 4) != 0 )
          v22 = 4;
        else
          v22 = 0;
        v23 = v22 | v20 & 0xFB;
        if ( (unsigned __int8)v11[8] < 0x14u || (v24 = 1, (v11[v12 + 50] & 8) == 0) )
          v24 = 0;
        if ( v24 )
          v10 = v10 & 0x7F | ((unsigned __int8)v11[42] >> 7 << 7);
        if ( (unsigned __int8)v11[8] < 0x14u || (v11[v12 + 50] & 8) == 0 )
          v2 = 0;
        v25 = v2 | v23 & 0xF7;
        if ( (unsigned __int8)v11[8] >= 0x15u && (v11[v12 + 50] & 0x10) != 0 )
          v26 = 16;
        else
          v26 = 0;
        v27 = v26 | v25 & 0xEF;
        goto LABEL_66;
      }
    }
    if ( v11[8] != 21 )
      goto LABEL_20;
LABEL_75:
    v27 = 0;
LABEL_66:
    if ( (v27 & 4) != 0 )
    {
      if ( (v10 & 0x40) != 0 )
      {
        *a2 = 1;
        return 1;
      }
      return 0;
    }
    v3 = a2;
    v5 = v31;
    v4 = v32;
LABEL_6:
    if ( (RtlGetSuiteMask() & 0x10000) != 0 )
      return 1;
    if ( (int)RtlQueryActivationContextApplicationSettings(
                0,
                0,
                L"http://schemas.microsoft.com/SMI/2020/WindowsSettings",
                L"heapType",
                String1,
                15,
                0) >= 0
      && !wcsnicmp(String1, L"SegmentHeap", 0xFu) )
    {
      v7 = 1;
      *v3 = 1;
      return v7;
    }
    if ( (v5->BitField & 0x10) != 0 )
    {
      v7 = 1;
      if ( (int)RtlQueryPackageClaims(-4, 0, 0, 0, 0, 0, &v30, 0) < 0 || (v30 & 0x88000) == 0 )
        return v7;
    }
    else if ( v5->ProcessParameters->HeapPartitionName.Buffer || v4 && (unsigned int)RtlpHpFindImageNameInList(v4) )
    {
      return 1;
    }
    return 0;
  }
  *a2 = ((unsigned int)RtlpLowFragHeapGlobalFlags >> 5) & 1;
  return 1;
}

```

## disassembly

```asm
0x180053e78  mov     [rsp-8+arg_10], rbx
0x180053e7d  push    rbp
0x180053e7e  push    rsi
0x180053e7f  push    rdi
0x180053e80  push    r12
0x180053e82  push    r13
0x180053e84  push    r14
0x180053e86  push    r15
0x180053e88  lea     rbp, [rsp-27h]
0x180053e8d  sub     rsp, 0E0h
0x180053e94  mov     rax, cs:__security_cookie
0x180053e9b  xor     rax, rsp
0x180053e9e  mov     [rbp+57h+var_38], rax
0x180053ea2  mov     eax, cs:RtlpLowFragHeapGlobalFlags
0x180053ea8  mov     r15b, 8
0x180053eab  mov     [rbp+57h+var_90], rdx
0x180053eaf  mov     rsi, rdx
0x180053eb2  mov     [rbp+57h+var_78], rcx
0x180053eb6  mov     r14, rcx
0x180053eb9  test    r15b, al
0x180053ebc  jnz     loc_1800547FE
0x180053ec2  mov     ebx, 1
0x180053ec7  test    al, 10h
0x180053ec9  jnz     loc_180054805
0x180053ecf  xorps   xmm0, xmm0
0x180053ed2  xor     r13d, r13d
0x180053ed5  xor     eax, eax
0x180053ed7  mov     [rbp+57h+var_88], r13
0x180053edb  movups  [rbp+57h+var_C8], xmm0
0x180053edf  mov     [rbp+57h+var_98], rax
0x180053ee3  movups  [rbp+57h+var_B8], xmm0
0x180053ee7  movups  [rbp+57h+var_A8], xmm0
0x180053eeb  mov     rdi, gs:60h
0x180053ef4  mov     [rdx], r13d
0x180053ef7  mov     [rbp+57h+var_80], rdi
0x180053efb  mov     rcx, [rdi+2D8h]
0x180053f02  test    rcx, rcx
0x180053f05  jz      short loc_180053F27
0x180053f07  cmp     dword ptr [rcx+208h], 11C0h
0x180053f11  jnb     loc_180053FC8
0x180053f17  mov     r12b, 4
0x180053f1a  test    [rcx+11B2h], r12b
0x180053f21  jnz     loc_180055119
0x180053f27  call    RtlGetSuiteMask
0x180053f2c  bt      eax, 10h
0x180053f30  jnb     short loc_180053F5E
0x180053f32  mov     edi, ebx
0x180053f34  mov     eax, edi
0x180053f36  mov     rcx, [rbp+57h+var_38]
0x180053f3a  xor     rcx, rsp; StackCookie
0x180053f3d  call    __security_check_cookie
0x180053f42  mov     rbx, [rsp+110h+arg_10]
0x180053f4a  add     rsp, 0E0h
0x180053f51  pop     r15
0x180053f53  pop     r14
0x180053f55  pop     r13
0x180053f57  pop     r12
0x180053f59  pop     rdi
0x180053f5a  pop     rsi
0x180053f5b  pop     rbp
0x180053f5c  retn
0x180053f5e  mov     [rsp+110h+var_E0], r13
0x180053f63  lea     rax, [rbp+57h+String1]
0x180053f67  mov     [rsp+110h+var_E8], 0Fh
0x180053f70  lea     r9, aHeaptype; "heapType"
0x180053f77  lea     r8, aHttpSchemasMic_0; "http://schemas.microsoft.com/SMI/2020/W"...
0x180053f7e  mov     [rsp+110h+var_F0], rax
0x180053f83  xor     edx, edx
0x180053f85  xor     ecx, ecx
0x180053f87  call    RtlQueryActivationContextApplicationSettings
0x180053f8c  test    eax, eax
0x180053f8e  jns     loc_180054197
0x180053f94  test    byte ptr [rdi+3], 10h
0x180053f98  jnz     loc_18005512D
0x180053f9e  mov     rax, [rdi+20h]
0x180053fa2  cmp     [rax+428h], r13
0x180053fa9  jnz     short loc_180053F32
0x180053fab  test    r14, r14
0x180053fae  jz      short loc_180053FC0
0x180053fb0  mov     rcx, r14
0x180053fb3  call    RtlpHpFindImageNameInList
0x180053fb8  test    eax, eax
0x180053fba  jnz     loc_180053F32
0x180053fc0  mov     edi, r13d
0x180053fc3  jmp     loc_180053F34
0x180053fc8  cmp     [rcx+11C0h], r13d
0x180053fcf  jz      loc_180053F17
0x180053fd5  mov     edx, [rcx+11C4h]
0x180053fdb  test    edx, edx
0x180053fdd  jz      loc_180053F17
0x180053fe3  mov     r9b, byte ptr [rbp+57h+var_A8+7]
0x180053fe7  mov     r12b, 0E3h
0x180053fea  mov     r11b, byte ptr [rbp+57h+var_A8+0Bh]
0x180053fee  and     r9b, r12b
0x180053ff1  mov     sil, byte ptr [rbp+57h+var_A8+9]
0x180053ff5  and     r11b, 0FEh
0x180053ff9  movups  [rbp+57h+var_50], xmm0
0x180053ffd  and     byte ptr [rbp+57h+var_50+0Bh], 0FEh
0x180054001  and     r11b, 0FEh
0x180054005  movups  xmmword ptr [rbp+57h+String1], xmm0
0x180054009  or      r9b, 3
0x18005400d  mov     [rbp+57h+var_CC], r11b
0x180054011  and     sil, 81h
0x180054015  mov     byte ptr [rbp+57h+var_A8+0Bh], r11b
0x180054019  and     r9b, r12b
0x18005401c  mov     dword ptr [rbp+57h+String1], 110038h
0x180054023  or      r9b, 3
0x180054027  mov     byte ptr [rbp+57h+String1+4], 0ABh
0x18005402b  or      sil, bl
0x18005402e  mov     [rbp+57h+var_CD], r9b
0x180054032  mov     eax, 30h ; '0'
0x180054037  mov     byte ptr [rbp+57h+var_A8+7], r9b
0x18005403b  mov     [rbp+57h+String1+6], ax
0x18005403f  and     sil, 81h
0x180054043  xor     eax, eax
0x180054045  mov     byte ptr [rbp+57h+String1+8], 15h
0x180054049  mov     dword ptr [rbp+57h+String1+9], eax
0x18005404c  or      sil, bl
0x18005404f  mov     [rbp+57h+String1+0Dh], ax
0x180054053  mov     r11b, 11h
0x180054056  mov     byte ptr [rbp+57h+String1+0Fh], al
0x180054059  xor     r8b, r8b
0x18005405c  mov     word ptr [rbp+57h+var_50+4], ax
0x180054060  mov     r9b, 1Ah
0x180054063  mov     byte ptr [rbp+57h+var_50+6], al
0x180054066  mov     al, byte ptr [rbp+57h+var_50+7]
0x180054069  and     al, r12b
0x18005406c  shr     r11b, 4
0x180054070  or      al, 3
0x180054072  mov     dword ptr [rbp+57h+var_50], 0FFFF0000h
0x180054079  mov     [rbp+57h+var_CB], al
0x18005407c  mov     r12b, 4
0x18005407f  mov     byte ptr [rbp+57h+var_50+7], al
0x180054082  mov     al, byte ptr [rbp+57h+var_50+9]
0x180054085  and     al, 81h
0x180054087  mov     byte ptr [rbp+57h+var_50+8], r13b
0x18005408b  or      al, bl
0x18005408d  mov     byte ptr [rbp+57h+var_50+0Ah], 1Ah
0x180054091  mov     [rbp+57h+var_CF], al
0x180054094  mov     byte ptr [rbp+57h+var_50+9], al
0x180054097  xor     eax, eax
0x180054099  mov     [rbp+57h+var_40], rax
0x18005409d  mov     eax, 30h ; '0'
0x1800540a2  mov     word ptr [rbp+57h+var_C8+6], ax
0x1800540a6  xor     eax, eax
0x1800540a8  mov     dword ptr [rbp+57h+var_C8+9], eax
0x1800540ab  mov     word ptr [rbp+57h+var_C8+0Dh], ax
0x1800540af  mov     byte ptr [rbp+57h+var_C8+0Fh], al
0x1800540b2  mov     qword ptr [rbp+57h+var_B8], rax
0x1800540b6  mov     qword ptr [rbp+57h+var_B8+8], rax
0x1800540ba  mov     word ptr [rbp+57h+var_A8+4], ax
0x1800540be  mov     byte ptr [rbp+57h+var_A8+6], al
0x1800540c1  mov     [rbp+57h+var_D0], al
0x1800540c4  mov     byte ptr [rbp+57h+var_A8+8], al
0x1800540c7  mov     [rbp+57h+var_98], rax
0x1800540cb  mov     al, 11h
0x1800540cd  movups  [rbp+57h+var_60], xmm0
0x1800540d1  shr     al, 4
0x1800540d4  mov     qword ptr [rbp+57h+var_60], r13
0x1800540d8  mov     qword ptr [rbp+57h+var_60+8], r13
0x1800540dc  mov     dword ptr [rbp+57h+var_C8], 110038h
0x1800540e3  mov     byte ptr [rbp+57h+var_C8+4], 0ABh
0x1800540e7  mov     byte ptr [rbp+57h+var_C8+8], 15h
0x1800540eb  mov     dword ptr [rbp+57h+var_A8], 0FFFF0000h
0x1800540f2  mov     byte ptr [rbp+57h+var_A8+9], sil
0x1800540f6  mov     byte ptr [rbp+57h+var_A8+0Ah], r9b
0x1800540fa  mov     [rbp+57h+var_CE], 40h ; '@'
0x1800540fe  cmp     al, r11b
0x180054101  jnz     loc_180054827
0x180054107  add     rdx, rcx
0x18005410a  mov     al, [rdx+2]
0x18005410d  shr     al, 4
0x180054110  cmp     al, r11b
0x180054113  jnz     loc_180054827
0x180054119  mov     al, 15h
0x18005411b  mov     ecx, 38h ; '8'
0x180054120  mov     r11b, 0ABh
0x180054123  cmp     [rdx+3], r8b
0x180054127  jz      loc_180054813
0x18005412d  cmp     [rdx+8], al
0x180054130  jz      loc_180054827
0x180054136  movzx   r11d, word ptr [rdx+6]
0x18005413b  mov     ecx, 30h ; '0'
0x180054140  movzx   eax, cx
0x180054143  movzx   r8d, cx
0x180054147  sub     r11, rax
0x18005414a  sub     r8, rax
0x18005414d  test    byte ptr [rbp+r8+57h+var_40], bl
0x180054152  jz      loc_180054830
0x180054158  mov     ecx, ebx
0x18005415a  cmp     [rdx+8], bl
0x18005415d  jnb     loc_180054837
0x180054163  xor     eax, eax
0x180054165  cmp     ecx, eax
0x180054167  jnz     loc_180054849
0x18005416d  test    byte ptr [rbp+r8+57h+var_40], bl
0x180054172  jz      short loc_180054187
0x180054174  mov     rax, [rdx+10h]
0x180054178  mov     qword ptr [rbp+57h+var_B8], rax
0x18005417c  test    byte ptr [rbp+r8+57h+var_40], bl
0x180054181  jnz     loc_180054868
0x180054187  cmp     [rdx+8], bl
0x18005418a  jnb     loc_18005485D
0x180054190  xor     al, al
0x180054192  jmp     loc_18005486A
0x180054197  mov     r8d, 0Fh; MaxCount
0x18005419d  lea     rdx, aSegmentheap; "SegmentHeap"
0x1800541a4  lea     rcx, [rbp+57h+String1]; String1
0x1800541a8  call    _wcsnicmp
0x1800541ad  test    eax, eax
0x1800541af  jnz     loc_180053F94
0x1800541b5  mov     edi, ebx
0x1800541b7  mov     [rsi], ebx
0x1800541b9  jmp     loc_180053F34
0x1800541be  cmp     byte ptr [rdx+8], 0Dh
0x1800541c2  jnb     loc_180054D00
0x1800541c8  mov     eax, r13d
0x1800541cb  cmp     ecx, eax
0x1800541cd  jnz     loc_180054D13
0x1800541d3  test    byte ptr [rbp+r8+57h+var_40+1], 10h
0x1800541d9  mov     r14b, 15h
0x1800541dc  jnz     loc_180054D30
0x1800541e2  cmp     r14b, 0Dh
0x1800541e6  jnb     loc_180054D44
0x1800541ec  cmp     byte ptr [rdx+8], 0Dh
0x1800541f0  jnb     loc_180054D51
0x1800541f6  mov     al, r13b
0x1800541f9  and     r10b, 0EFh
0x1800541fd  mov     sil, 0Eh
0x180054200  or      r10b, al
0x180054203  mov     byte ptr [rbp+57h+var_98+1], r10b
0x180054207  cmp     r14b, sil
0x18005420a  jnb     loc_180054D64
0x180054210  mov     ecx, r13d
0x180054213  cmp     [rdx+8], sil
0x180054217  jnb     loc_180054D77
0x18005421d  mov     eax, r13d
0x180054220  cmp     ecx, eax
0x180054222  jnz     loc_180054D8A
0x180054228  cmp     r14b, sil
0x18005422b  jnb     loc_180054DA1
0x180054231  cmp     [rdx+8], sil
0x180054235  jnb     loc_180054DD4
0x18005423b  mov     al, r13b
0x18005423e  mov     sil, [rbp+57h+var_CE]
0x180054242  and     r10b, 0DFh
0x180054246  or      r10b, al
0x180054249  mov     byte ptr [rbp+57h+var_98+1], r10b
0x18005424d  cmp     r14b, 0Fh
0x180054251  jnb     loc_180054DE7
0x180054257  mov     ecx, r13d
0x18005425a  cmp     byte ptr [rdx+8], 0Fh
0x18005425e  jnb     loc_180054DF9
0x180054264  mov     eax, r13d
0x180054267  cmp     ecx, eax
0x180054269  jnz     loc_180054E0B
0x18005426f  cmp     r14b, 0Fh
0x180054273  jnb     loc_180054E2D
0x180054279  cmp     byte ptr [rdx+8], 0Fh
0x18005427d  jnb     loc_180054E5F
0x180054283  mov     al, r13b
0x180054286  and     r10b, 0BFh
0x18005428a  or      r10b, al
0x18005428d  mov     byte ptr [rbp+57h+var_98+1], r10b
0x180054291  cmp     r14b, 10h
0x180054295  jnb     loc_180054E72
0x18005429b  mov     ecx, r13d
0x18005429e  cmp     byte ptr [rdx+8], 10h
0x1800542a2  jnb     loc_180054E84
0x1800542a8  mov     eax, r13d
0x1800542ab  cmp     ecx, eax
0x1800542ad  jnz     loc_180054E96
0x1800542b3  cmp     r14b, 10h
0x1800542b7  jnb     loc_180054EB8
0x1800542bd  cmp     byte ptr [rdx+8], 10h
0x1800542c1  jnb     loc_180054EEA
0x1800542c7  mov     al, r13b
0x1800542ca  and     r10b, 7Fh
0x1800542ce  or      r10b, al
0x1800542d1  mov     byte ptr [rbp+57h+var_98+1], r10b
0x1800542d5  mov     r10b, 11h
0x1800542d8  cmp     r14b, r10b
0x1800542db  jnb     loc_180054EFC
0x1800542e1  mov     ecx, r13d
0x1800542e4  cmp     [rdx+8], r10b
0x1800542e8  jnb     loc_180054F0E
0x1800542ee  mov     eax, r13d
0x1800542f1  cmp     ecx, eax
0x1800542f3  jnz     loc_180054F20
0x1800542f9  cmp     r14b, r10b
0x1800542fc  jnb     loc_180054F41
0x180054302  cmp     [rdx+8], r10b
0x180054306  jnb     loc_180054F72
0x18005430c  mov     al, r13b
0x18005430f  mov     r10b, byte ptr [rbp+57h+var_98+2]
0x180054313  and     r10b, 0FEh
0x180054317  or      r10b, al
0x18005431a  mov     byte ptr [rbp+57h+var_98+2], r10b
0x18005431e  cmp     r14b, 12h
0x180054322  jnb     loc_180054F84
  ... truncated ...
```
