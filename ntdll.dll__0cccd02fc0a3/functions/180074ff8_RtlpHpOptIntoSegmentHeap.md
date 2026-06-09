# RtlpHpOptIntoSegmentHeap

- ea: `0x180074ff8`
- end: `0x180075eb2`
- name: `RtlpHpOptIntoSegmentHeap`
- size: `3770`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180074b1c`

## callees

- `0x180002c20`
- `0x180074ff8`
- `0x180090d30`
- `0x1800dc930`
- `0x1800e5e34`
- `0x180127e50`
- `0x180162000`

## string_xrefs

- `0x180075de6`: `http://schemas.microsoft.com/SMI/2020/WindowsSettings`

## pseudocode

```c
__int64 __fastcall RtlpHpOptIntoSegmentHeap(__int64 a1, unsigned int *a2)
{
  char v2; // r15
  unsigned int *v3; // rsi
  __int64 v4; // r14
  struct _PEB *v6; // rdi
  _BYTE *pShimData; // rcx
  __int64 v8; // rdx
  char v9; // r9
  char *v10; // rdx
  __int64 v11; // r11
  char v12; // di
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
  unsigned int v28; // edi
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
  if ( (RtlpLowFragHeapGlobalFlags & 0x10) != 0 )
  {
    *a2 = ((unsigned int)RtlpLowFragHeapGlobalFlags >> 5) & 1;
    return 1;
  }
  if ( (qword_1801C6268 & 3) == 1 )
  {
    *a2 = 1;
    return 1;
  }
  v30 = 0;
  v6 = NtCurrentPeb();
  *a2 = 0;
  v31 = v6;
  pShimData = v6->pShimData;
  if ( !pShimData )
    goto LABEL_81;
  if ( *((_DWORD *)pShimData + 130) < 0x11C0u
    || !*((_DWORD *)pShimData + 1136)
    || (v8 = *((unsigned int *)pShimData + 1137), !(_DWORD)v8) )
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
LABEL_81:
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
      v28 = 1;
      *v3 = 1;
      return v28;
    }
    if ( (v6->BitField & 0x10) != 0 )
    {
      v28 = 1;
      if ( (int)RtlQueryPackageClaims(-4, 0, 0, 0, 0, 0, &v30, 0) < 0 || (v30 & 0x88000) == 0 )
        return v28;
    }
    else if ( v6->ProcessParameters->HeapPartitionName.Buffer || v4 && (unsigned int)RtlpHpFindImageNameInList(v4) )
    {
      return 1;
    }
    return 0;
  }
  v39 = 0;
  *(_DWORD *)((char *)&String1[4] + 1) = 0;
  *(wchar_t *)((char *)&String1[6] + 1) = 0;
  HIBYTE(String1[7]) = 0;
  v36 = 0;
  v37 = 0;
  v38 = 436273155;
  v9 = 26;
  *(_DWORD *)String1 = 1114168;
  v40 = 0;
  wmemcpy(&String1[2], L"«0", 2);
  LOBYTE(String1[4]) = 21;
  v34 = 0u;
  v35 = -65536;
  v10 = &pShimData[v8];
  if ( (unsigned __int8)v10[2] >> 4 != 1 )
    goto LABEL_73;
  if ( !v10[3] )
  {
    if ( v10[8] != 21 || *(_WORD *)v10 != 56 || v10[4] != -85 )
      goto LABEL_73;
    if ( !v10[3] )
      goto LABEL_19;
  }
  if ( v10[8] == 21 )
  {
LABEL_73:
    v27 = 0;
    goto LABEL_74;
  }
LABEL_19:
  v11 = *((unsigned __int16 *)v10 + 3) - 48LL;
  v12 = 2;
  if ( (unsigned __int8)v10[8] < 0xEu || (v13 = 1, (v10[v11 + 49] & 0x20) == 0) )
    v13 = 0;
  if ( v13 )
    v9 = v10[42] & 3 | 0x18;
  if ( (unsigned __int8)v10[8] < 0xFu || (v14 = 1, (v10[v11 + 49] & 0x40) == 0) )
    v14 = 0;
  if ( ((v40 & 0x4000) != 0) != v14 )
    v9 = v9 & 0xFB | (4 * ((v10[42] & 4) != 0));
  if ( (unsigned __int8)v10[8] < 0x10u || (v15 = 1, v10[v11 + 49] >= 0) )
    v15 = 0;
  if ( v15 )
    v9 = v9 & 0xF7 | (8 * ((v10[42] & 8) != 0));
  if ( (unsigned __int8)v10[8] < 0x11u || (v16 = 1, (v10[v11 + 50] & 1) == 0) )
    v16 = 0;
  if ( v16 )
    v9 = v9 & 0xEF | (16 * ((v10[42] & 0x10) != 0));
  v17 = (unsigned __int8)v10[8] >= 0x11u && (v10[v11 + 50] & 1) != 0;
  v18 = v17;
  if ( (unsigned __int8)v10[8] < 0x12u || (v19 = 1, (v10[v11 + 50] & 2) == 0) )
    v19 = 0;
  if ( v19 )
    v9 = v9 & 0xDF | (32 * ((v10[42] & 0x20) != 0));
  if ( (unsigned __int8)v10[8] < 0x12u || (v10[v11 + 50] & 2) == 0 )
    v12 = 0;
  v20 = v12 | v18 & 0xFD;
  if ( (unsigned __int8)v10[8] < 0x13u || (v21 = 1, (v10[v11 + 50] & 4) == 0) )
    v21 = 0;
  if ( v21 )
    v9 = v9 & 0xBF | (((v10[42] & 0x40) != 0) << 6);
  if ( (unsigned __int8)v10[8] >= 0x13u && (v10[v11 + 50] & 4) != 0 )
    v22 = 4;
  else
    v22 = 0;
  v23 = v22 | v20 & 0xFB;
  if ( (unsigned __int8)v10[8] < 0x14u || (v24 = 1, (v10[v11 + 50] & 8) == 0) )
    v24 = 0;
  if ( v24 )
    v9 = v9 & 0x7F | ((unsigned __int8)v10[42] >> 7 << 7);
  if ( (unsigned __int8)v10[8] < 0x14u || (v10[v11 + 50] & 8) == 0 )
    v2 = 0;
  v25 = v2 | v23 & 0xF7;
  if ( (unsigned __int8)v10[8] >= 0x15u && (v10[v11 + 50] & 0x10) != 0 )
    v26 = 16;
  else
    v26 = 0;
  v27 = v26 | v25 & 0xEF;
LABEL_74:
  if ( (v27 & 4) == 0 )
  {
    v3 = a2;
    v6 = v31;
    v4 = v32;
    goto LABEL_81;
  }
  if ( (v9 & 0x40) == 0 )
    return 0;
  *a2 = 1;
  return 1;
}

```

## disassembly

```asm
0x180074ff8  mov     [rsp-8+arg_10], rbx
0x180074ffd  push    rbp
0x180074ffe  push    rsi
0x180074fff  push    rdi
0x180075000  push    r12
0x180075002  push    r13
0x180075004  push    r14
0x180075006  push    r15
0x180075008  lea     rbp, [rsp-27h]
0x18007500d  sub     rsp, 0E0h
0x180075014  mov     rax, cs:__security_cookie
0x18007501b  xor     rax, rsp
0x18007501e  mov     [rbp+57h+var_38], rax
0x180075022  mov     eax, cs:RtlpLowFragHeapGlobalFlags
0x180075028  mov     r15b, 8
0x18007502b  mov     [rbp+57h+var_90], rdx
0x18007502f  mov     rsi, rdx
0x180075032  mov     [rbp+57h+var_78], rcx
0x180075036  mov     r14, rcx
0x180075039  test    r15b, al
0x18007503c  jz      short loc_180075045
0x18007503e  xor     eax, eax
0x180075040  jmp     loc_180075E8A
0x180075045  mov     ebx, 1
0x18007504a  test    al, 10h
0x18007504c  jz      short loc_18007505C
0x18007504e  shr     eax, 5
0x180075051  and     eax, ebx
0x180075053  mov     [rdx], eax
0x180075055  mov     eax, ebx
0x180075057  jmp     loc_180075E8A
0x18007505c  mov     al, byte ptr cs:qword_1801C6268
0x180075062  and     al, 3
0x180075064  cmp     al, bl
0x180075066  jnz     short loc_18007506C
0x180075068  mov     [rdx], ebx
0x18007506a  jmp     short loc_180075055
0x18007506c  xorps   xmm0, xmm0
0x18007506f  xor     r13d, r13d
0x180075072  xor     eax, eax
0x180075074  mov     [rbp+57h+var_88], r13
0x180075078  movups  [rbp+57h+var_C8], xmm0
0x18007507c  mov     [rbp+57h+var_98], rax
0x180075080  movups  [rbp+57h+var_B8], xmm0
0x180075084  movups  [rbp+57h+var_A8], xmm0
0x180075088  mov     rdi, gs:60h
0x180075091  mov     [rdx], r13d
0x180075094  mov     [rbp+57h+var_80], rdi
0x180075098  mov     rcx, [rdi+2D8h]
0x18007509f  test    rcx, rcx
0x1800750a2  jz      loc_180075DBB
0x1800750a8  cmp     dword ptr [rcx+208h], 11C0h
0x1800750b2  jb      loc_180075D92
0x1800750b8  cmp     [rcx+11C0h], r13d
0x1800750bf  jz      loc_180075D92
0x1800750c5  mov     edx, [rcx+11C4h]
0x1800750cb  test    edx, edx
0x1800750cd  jz      loc_180075D92
0x1800750d3  mov     r9b, byte ptr [rbp+57h+var_A8+7]
0x1800750d7  lea     eax, [r13+30h]
0x1800750db  mov     r11b, byte ptr [rbp+57h+var_A8+0Bh]
0x1800750df  mov     r12b, 0E3h
0x1800750e2  mov     sil, byte ptr [rbp+57h+var_A8+9]
0x1800750e6  and     r9b, r12b
0x1800750e9  movups  [rbp+57h+var_50], xmm0
0x1800750ed  and     byte ptr [rbp+57h+var_50+0Bh], 0FEh
0x1800750f1  and     r11b, 0FEh
0x1800750f5  movups  xmmword ptr [rbp+57h+String1], xmm0
0x1800750f9  mov     [rbp+57h+String1+6], ax
0x1800750fd  and     r11b, 0FEh
0x180075101  xor     eax, eax
0x180075103  mov     [rbp+57h+var_CC], r11b
0x180075107  mov     dword ptr [rbp+57h+String1+9], eax
0x18007510a  or      r9b, 3
0x18007510e  mov     [rbp+57h+String1+0Dh], ax
0x180075112  and     sil, 81h
0x180075116  mov     byte ptr [rbp+57h+String1+0Fh], al
0x180075119  and     r9b, r12b
0x18007511c  mov     word ptr [rbp+57h+var_50+4], ax
0x180075120  or      r9b, 3
0x180075124  mov     byte ptr [rbp+57h+var_50+6], al
0x180075127  or      sil, bl
0x18007512a  mov     al, byte ptr [rbp+57h+var_50+7]
0x18007512d  and     sil, 81h
0x180075131  and     al, r12b
0x180075134  mov     byte ptr [rbp+57h+var_A8+0Bh], r11b
0x180075138  or      al, 3
0x18007513a  mov     [rbp+57h+var_CD], r9b
0x18007513e  mov     [rbp+57h+var_CB], al
0x180075141  or      sil, bl
0x180075144  mov     byte ptr [rbp+57h+var_50+7], al
0x180075147  mov     r11b, 11h
0x18007514a  mov     al, byte ptr [rbp+57h+var_50+9]
0x18007514d  xor     r8b, r8b
0x180075150  and     al, 81h
0x180075152  mov     byte ptr [rbp+57h+var_A8+7], r9b
0x180075156  or      al, bl
0x180075158  shr     r11b, 4
0x18007515c  mov     [rbp+57h+var_CF], al
0x18007515f  mov     r9b, 1Ah
0x180075162  mov     byte ptr [rbp+57h+var_50+9], al
0x180075165  mov     r12b, 4
0x180075168  xor     eax, eax
0x18007516a  mov     dword ptr [rbp+57h+String1], 110038h
0x180075171  mov     [rbp+57h+var_40], rax
0x180075175  lea     eax, [r13+30h]
0x180075179  mov     word ptr [rbp+57h+var_C8+6], ax
0x18007517d  xor     eax, eax
0x18007517f  mov     dword ptr [rbp+57h+var_C8+9], eax
0x180075182  mov     word ptr [rbp+57h+var_C8+0Dh], ax
0x180075186  mov     byte ptr [rbp+57h+var_C8+0Fh], al
0x180075189  mov     qword ptr [rbp+57h+var_B8], rax
0x18007518d  mov     qword ptr [rbp+57h+var_B8+8], rax
0x180075191  mov     word ptr [rbp+57h+var_A8+4], ax
0x180075195  mov     byte ptr [rbp+57h+var_A8+6], al
0x180075198  mov     [rbp+57h+var_D0], al
0x18007519b  mov     byte ptr [rbp+57h+var_A8+8], al
0x18007519e  mov     [rbp+57h+var_98], rax
0x1800751a2  mov     al, 11h
0x1800751a4  movups  [rbp+57h+var_60], xmm0
0x1800751a8  shr     al, 4
0x1800751ab  mov     byte ptr [rbp+57h+String1+4], 0ABh
0x1800751af  mov     byte ptr [rbp+57h+String1+8], 15h
0x1800751b3  mov     qword ptr [rbp+57h+var_60], r13
0x1800751b7  mov     qword ptr [rbp+57h+var_60+8], r13
0x1800751bb  mov     dword ptr [rbp+57h+var_50], 0FFFF0000h
0x1800751c2  mov     byte ptr [rbp+57h+var_50+8], r13b
0x1800751c6  mov     byte ptr [rbp+57h+var_50+0Ah], 1Ah
0x1800751ca  mov     dword ptr [rbp+57h+var_C8], 110038h
0x1800751d1  mov     byte ptr [rbp+57h+var_C8+4], 0ABh
0x1800751d5  mov     byte ptr [rbp+57h+var_C8+8], 15h
0x1800751d9  mov     dword ptr [rbp+57h+var_A8], 0FFFF0000h
0x1800751e0  mov     byte ptr [rbp+57h+var_A8+9], sil
0x1800751e4  mov     byte ptr [rbp+57h+var_A8+0Ah], r9b
0x1800751e8  mov     [rbp+57h+var_CE], 40h ; '@'
0x1800751ec  cmp     al, r11b
0x1800751ef  jnz     loc_180075D77
0x1800751f5  add     rdx, rcx
0x1800751f8  mov     al, [rdx+2]
0x1800751fb  shr     al, 4
0x1800751fe  cmp     al, r11b
0x180075201  jnz     loc_180075D77
0x180075207  lea     ecx, [r13+38h]
0x18007520b  mov     al, 15h
0x18007520d  mov     r11b, 0ABh
0x180075210  cmp     [rdx+3], r8b
0x180075214  jnz     short loc_180075238
0x180075216  cmp     [rdx+8], al
0x180075219  jnz     loc_180075D77
0x18007521f  cmp     [rdx], cx
0x180075222  jnz     loc_180075D77
0x180075228  cmp     [rdx+4], r11b
0x18007522c  jnz     loc_180075D77
0x180075232  cmp     [rdx+3], r8b
0x180075236  jz      short loc_180075241
0x180075238  cmp     [rdx+8], al
0x18007523b  jz      loc_180075D77
0x180075241  movzx   r11d, word ptr [rdx+6]
0x180075246  mov     ecx, 30h ; '0'
0x18007524b  movzx   eax, cx
0x18007524e  movzx   r8d, cx
0x180075252  sub     r11, rax
0x180075255  sub     r8, rax
0x180075258  test    byte ptr [rbp+r8+57h+var_40], bl
0x18007525d  jz      short loc_180075263
0x18007525f  mov     ecx, ebx
0x180075261  jmp     short loc_180075265
0x180075263  xor     ecx, ecx
0x180075265  cmp     [rdx+8], bl
0x180075268  jb      short loc_180075275
0x18007526a  test    [r11+rdx+30h], bl
0x18007526f  jz      short loc_180075275
0x180075271  mov     eax, ebx
0x180075273  jmp     short loc_180075277
0x180075275  xor     eax, eax
0x180075277  cmp     ecx, eax
0x180075279  jz      short loc_180075288
0x18007527b  test    byte ptr [rbp+r8+57h+var_40], bl
0x180075280  jz      short loc_18007528F
0x180075282  mov     qword ptr [rbp+57h+var_B8], r13
0x180075286  jmp     short loc_180075297
0x180075288  test    byte ptr [rbp+r8+57h+var_40], bl
0x18007528d  jz      short loc_18007529E
0x18007528f  mov     rax, [rdx+10h]
0x180075293  mov     qword ptr [rbp+57h+var_B8], rax
0x180075297  test    byte ptr [rbp+r8+57h+var_40], bl
0x18007529c  jnz     short loc_1800752AA
0x18007529e  cmp     [rdx+8], bl
0x1800752a1  jb      short loc_1800752AE
0x1800752a3  test    [r11+rdx+30h], bl
0x1800752a8  jz      short loc_1800752AE
0x1800752aa  mov     al, bl
0x1800752ac  jmp     short loc_1800752B0
0x1800752ae  xor     al, al
0x1800752b0  mov     cl, byte ptr [rbp+57h+var_98]
0x1800752b3  mov     dil, 2
0x1800752b6  and     cl, 0FEh
0x1800752b9  or      cl, al
0x1800752bb  mov     byte ptr [rbp+57h+var_98], cl
0x1800752be  test    byte ptr [rbp+r8+57h+var_40], dil
0x1800752c3  jz      short loc_1800752CA
0x1800752c5  mov     r10d, ebx
0x1800752c8  jmp     short loc_1800752CD
0x1800752ca  xor     r10d, r10d
0x1800752cd  cmp     [rdx+8], dil
0x1800752d1  jb      short loc_1800752DE
0x1800752d3  test    [r11+rdx+30h], dil
0x1800752d8  jz      short loc_1800752DE
0x1800752da  mov     eax, ebx
0x1800752dc  jmp     short loc_1800752E0
0x1800752de  xor     eax, eax
0x1800752e0  mov     r14b, 15h
0x1800752e3  cmp     r10d, eax
0x1800752e6  jz      short loc_1800752F5
0x1800752e8  test    byte ptr [rbp+r8+57h+var_40], dil
0x1800752ed  jz      short loc_1800752FC
0x1800752ef  mov     dword ptr [rbp+57h+var_B8+8], r13d
0x1800752f3  jmp     short loc_180075302
0x1800752f5  test    byte ptr [rbp+r8+57h+var_40], dil
0x1800752fa  jz      short loc_180075302
0x1800752fc  mov     eax, [rdx+18h]
0x1800752ff  mov     dword ptr [rbp+57h+var_B8+8], eax
0x180075302  cmp     r14b, dil
0x180075305  jb      short loc_18007530E
0x180075307  test    byte ptr [rbp+r8+57h+var_40], dil
0x18007530c  jnz     short loc_18007531B
0x18007530e  cmp     [rdx+8], dil
0x180075312  jb      short loc_180075320
0x180075314  test    [r11+rdx+30h], dil
0x180075319  jz      short loc_180075320
0x18007531b  mov     al, dil
0x18007531e  jmp     short loc_180075322
0x180075320  xor     al, al
0x180075322  and     cl, 0FDh
0x180075325  or      cl, al
0x180075327  mov     byte ptr [rbp+57h+var_98], cl
0x18007532a  cmp     r14b, 3
0x18007532e  jb      short loc_18007533C
0x180075330  test    byte ptr [rbp+r8+57h+var_40], r12b
0x180075335  jz      short loc_18007533C
0x180075337  mov     r10d, ebx
0x18007533a  jmp     short loc_18007533F
0x18007533c  xor     r10d, r10d
0x18007533f  cmp     byte ptr [rdx+8], 3
0x180075343  jb      short loc_180075350
0x180075345  test    [r11+rdx+30h], r12b
0x18007534a  jz      short loc_180075350
0x18007534c  mov     eax, ebx
0x18007534e  jmp     short loc_180075352
0x180075350  xor     eax, eax
0x180075352  cmp     r10d, eax
0x180075355  jz      short loc_18007536A
0x180075357  cmp     r14b, 3
0x18007535b  jb      short loc_180075377
0x18007535d  test    byte ptr [rbp+r8+57h+var_40], r12b
0x180075362  jz      short loc_180075377
0x180075364  mov     dword ptr [rbp+57h+var_B8+0Ch], r13d
0x180075368  jmp     short loc_18007537D
0x18007536a  cmp     r14b, 3
0x18007536e  jb      short loc_18007538A
0x180075370  test    byte ptr [rbp+r8+57h+var_40], r12b
0x180075375  jz      short loc_18007537D
0x180075377  mov     eax, [rdx+1Ch]
0x18007537a  mov     dword ptr [rbp+57h+var_B8+0Ch], eax
0x18007537d  cmp     r14b, 3
0x180075381  jb      short loc_18007538A
0x180075383  test    byte ptr [rbp+r8+57h+var_40], r12b
0x180075388  jnz     short loc_180075397
0x18007538a  cmp     byte ptr [rdx+8], 3
0x18007538e  jb      short loc_18007539C
0x180075390  test    [r11+rdx+30h], r12b
0x180075395  jz      short loc_18007539C
0x180075397  mov     al, r12b
0x18007539a  jmp     short loc_18007539F
0x18007539c  mov     al, r13b
0x18007539f  and     cl, 0FBh
0x1800753a2  or      cl, al
0x1800753a4  mov     byte ptr [rbp+57h+var_98], cl
0x1800753a7  cmp     r14b, r12b
0x1800753aa  jb      short loc_1800753B6
0x1800753ac  mov     r10d, ebx
0x1800753af  test    byte ptr [rbp+r8+57h+var_40], r15b
0x1800753b4  jnz     short loc_1800753B9
0x1800753b6  mov     r10d, r13d
0x1800753b9  cmp     [rdx+8], r12b
0x1800753bd  jb      short loc_1800753C8
0x1800753bf  mov     eax, ebx
0x1800753c1  test    [r11+rdx+30h], r15b
0x1800753c6  jnz     short loc_1800753CB
0x1800753c8  mov     eax, r13d
0x1800753cb  cmp     r10d, eax
0x1800753ce  jz      short loc_1800753E0
0x1800753d0  cmp     r14b, r12b
0x1800753d3  jb      short loc_1800753EC
0x1800753d5  test    byte ptr [rbp+r8+57h+var_40], r15b
0x1800753da  jz      short loc_1800753EC
0x1800753dc  xor     eax, eax
0x1800753de  jmp     short loc_1800753F0
0x1800753e0  cmp     r14b, r12b
0x1800753e3  jb      short loc_180075400
  ... truncated ...
```
