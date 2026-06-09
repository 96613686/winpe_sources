# CipInstrumentVbsPolicyFailure

- ea: `0x18006b7ac`
- end: `0x18006bb22`
- name: `CipInstrumentVbsPolicyFailure`
- size: `886`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18006b07c`
- `0x18006b0d0`

## callees

- `0x18000a2f4`
- `0x18000fb30`
- `0x18002bef0`
- `0x18006b7ac`
- `0x1800e3e80`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18006bacd`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006baeb`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006bacd`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006baeb`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18006ba51`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18006ba51`

## pseudocode

```c
void __fastcall CipInstrumentVbsPolicyFailure(
        __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        int a5)
{
  unsigned __int16 *v5; // rdi
  void *v6; // r13
  unsigned __int16 *v7; // r14
  char v8; // bl
  __int64 v9; // rcx
  __int64 v10; // r12
  unsigned __int16 v11; // r15
  __int64 v12; // rax
  int v13; // eax
  PVOID v14; // rsi
  int v15; // r9d
  int v16; // eax
  PVOID v17; // rdi
  char v18; // al
  char IsCurrentThreadInServerSilo; // al
  __int64 v20; // r8
  char v21; // [rsp+30h] [rbp-D0h] BYREF
  char v22; // [rsp+31h] [rbp-CFh] BYREF
  char v23; // [rsp+32h] [rbp-CEh] BYREF
  char v24; // [rsp+33h] [rbp-CDh] BYREF
  char v25; // [rsp+34h] [rbp-CCh] BYREF
  char v26; // [rsp+35h] [rbp-CBh] BYREF
  unsigned __int16 v27; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v28; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+48h] [rbp-B8h] BYREF
  PVOID P[2]; // [rsp+50h] [rbp-B0h] BYREF
  PVOID v31[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+70h] [rbp-90h] BYREF
  __int128 v33; // [rsp+78h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v34; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v35; // [rsp+B0h] [rbp-50h]
  __int64 v36; // [rsp+B8h] [rbp-48h]
  _DWORD *v37; // [rsp+C0h] [rbp-40h]
  __int64 v38; // [rsp+C8h] [rbp-38h]
  PVOID v39; // [rsp+D0h] [rbp-30h]
  _DWORD v40[2]; // [rsp+D8h] [rbp-28h] BYREF
  _DWORD *v41; // [rsp+E0h] [rbp-20h]
  __int64 v42; // [rsp+E8h] [rbp-18h]
  PVOID v43; // [rsp+F0h] [rbp-10h]
  _DWORD v44[2]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 **v45; // [rsp+100h] [rbp+0h]
  __int64 v46; // [rsp+108h] [rbp+8h]
  char *v47; // [rsp+110h] [rbp+10h]
  __int64 v48; // [rsp+118h] [rbp+18h]
  __int64 *v49; // [rsp+120h] [rbp+20h]
  __int64 v50; // [rsp+128h] [rbp+28h]
  char *v51; // [rsp+130h] [rbp+30h]
  __int64 v52; // [rsp+138h] [rbp+38h]
  _DWORD *v53; // [rsp+140h] [rbp+40h]
  __int64 v54; // [rsp+148h] [rbp+48h]
  __int64 v55; // [rsp+150h] [rbp+50h]
  _DWORD v56[2]; // [rsp+158h] [rbp+58h] BYREF
  PVOID *v57; // [rsp+160h] [rbp+60h]
  __int64 v58; // [rsp+168h] [rbp+68h]
  __int16 *v59; // [rsp+170h] [rbp+70h]
  __int64 v60; // [rsp+178h] [rbp+78h]
  __int64 v61; // [rsp+180h] [rbp+80h]
  int v62; // [rsp+188h] [rbp+88h]
  int v63; // [rsp+18Ch] [rbp+8Ch]
  char *v64; // [rsp+190h] [rbp+90h]
  __int64 v65; // [rsp+198h] [rbp+98h]
  char *v66; // [rsp+1A0h] [rbp+A0h]
  __int64 v67; // [rsp+1A8h] [rbp+A8h]
  PVOID *v68; // [rsp+1B0h] [rbp+B0h]
  __int64 v69; // [rsp+1B8h] [rbp+B8h]

  v28 = a4;
  v29 = a1;
  v23 = 0;
  v22 = 0;
  v5 = a4;
  v33 = 0;
  *(_OWORD *)v31 = 0;
  *(_OWORD *)P = 0;
  if ( a2 )
  {
    v6 = *(void **)(a2 + 840);
    v7 = (unsigned __int16 *)(a2 + 744);
    v8 = 0;
    v9 = 160LL * (((unsigned __int8)*(_DWORD *)(a2 + 32) - 1) & 3 & (unsigned int)-(*(_DWORD *)(a2 + 32) != 0));
    v10 = v9 + a2 + 128;
    v11 = *(_WORD *)(v9 + a2 + 124);
    v12 = *(_QWORD *)(a2 + 984);
    v21 = *(_BYTE *)(v9 + a2 + 92);
    v5 = v28;
    if ( v12 )
      v8 = BYTE1(*(_DWORD *)(*(_QWORD *)(v12 + 8) + 48LL)) & 1;
  }
  else
  {
    v10 = 0;
    v21 = 0;
    v11 = 0;
    v7 = (unsigned __int16 *)&v33;
    v6 = 0;
    v8 = 1;
  }
  v13 = CiSanitizeFileName(a3, (struct _UNICODE_STRING *)v31, &v23);
  v14 = v31[1];
  LOBYTE(v15) = 0;
  if ( v13 >= 0 )
  {
    v16 = CiSanitizeFileName(v5, (struct _UNICODE_STRING *)P, &v22);
    v17 = P[1];
    LOBYTE(v15) = 0;
    if ( v16 >= 0
      && (unsigned int)dword_180048128 > 5
      && (unsigned __int8)tlgKeywordOn(&dword_180048128, 0x800000000000LL) )
    {
      v32 = (unsigned int)(v15 + 1);
      v35 = &v32;
      v37 = v40;
      v40[0] = LOWORD(v31[0]);
      v41 = v44;
      v44[0] = LOWORD(P[0]);
      LODWORD(v28) = a5;
      v45 = &v28;
      v18 = (v15 + 1) & *(_BYTE *)(v29 + 46);
      v36 = 8;
      v24 = v18;
      v47 = &v24;
      v29 = *(_QWORD *)(v29 + 32);
      v49 = &v29;
      v51 = &v21;
      v53 = v56;
      v55 = *((_QWORD *)v7 + 1);
      v56[0] = *v7;
      v57 = P;
      v59 = (__int16 *)&v27;
      v62 = v11;
      v64 = &v25;
      v38 = 2;
      v39 = v14;
      v40[1] = v15;
      v42 = 2;
      v43 = v17;
      v44[1] = v15;
      v46 = 4;
      v48 = v32;
      v50 = 8;
      v52 = v32;
      v54 = 2;
      v56[1] = v15;
      P[0] = v6;
      v58 = 8;
      v27 = v11;
      v60 = 2;
      v61 = v10;
      v63 = v15;
      v25 = v8;
      v65 = v32;
      IsCurrentThreadInServerSilo = PsIsCurrentThreadInServerSilo();
      v67 = 1;
      v26 = IsCurrentThreadInServerSilo;
      v69 = 8;
      v66 = &v26;
      v31[0] = (PVOID)0x80000000LL;
      v68 = v31;
      tlgWriteAgg((__int64)&dword_180048128, (unsigned __int8 *)&byte_18003DE69, v20, 0x13u, &v34);
      LOBYTE(v15) = 0;
    }
    if ( v22 != (_BYTE)v15 )
    {
      ExFreePoolWithTag(v17, 0x63734943u);
      LOBYTE(v15) = 0;
    }
  }
  if ( v23 != (_BYTE)v15 )
    ExFreePoolWithTag(v14, 0x63734943u);
}

```

## disassembly

```asm
0x18006b7ac  mov     [rsp-8+arg_0], rbx
0x18006b7b1  push    rbp
0x18006b7b2  push    rsi
0x18006b7b3  push    rdi
0x18006b7b4  push    r12
0x18006b7b6  push    r13
0x18006b7b8  push    r14
0x18006b7ba  push    r15
0x18006b7bc  lea     rbp, [rsp-0D0h]
0x18006b7c4  sub     rsp, 1D0h
0x18006b7cb  mov     rax, cs:__security_cookie
0x18006b7d2  xor     rax, rsp
0x18006b7d5  mov     [rbp+100h+var_40], rax
0x18006b7dc  xor     r11d, r11d
0x18006b7df  mov     [rsp+200h+var_1C0], r9
0x18006b7e4  mov     [rsp+200h+var_1B8], rcx
0x18006b7e9  xorps   xmm0, xmm0
0x18006b7ec  mov     [rsp+200h+var_1CE], r11b
0x18006b7f1  xorps   xmm1, xmm1
0x18006b7f4  mov     [rsp+200h+var_1CF], r11b
0x18006b7f9  mov     rdi, r9
0x18006b7fc  mov     r10, r8
0x18006b7ff  mov     r9, rdx
0x18006b802  movups  [rsp+200h+var_188], xmm0
0x18006b807  movups  xmmword ptr [rsp+200h+var_1A0], xmm1
0x18006b80c  movups  xmmword ptr [rsp+200h+P], xmm0
0x18006b811  test    rdx, rdx
0x18006b814  jz      short loc_18006B88C
0x18006b816  mov     edx, [rdx+20h]
0x18006b819  lea     r12, [r9+80h]
0x18006b820  mov     r13, [r9+348h]
0x18006b827  lea     r14, [r9+2E8h]
0x18006b82e  mov     eax, edx
0x18006b830  mov     bl, r11b
0x18006b833  lea     r8d, [rdx-1]
0x18006b837  and     r8d, 3
0x18006b83b  neg     eax
0x18006b83d  sbb     ecx, ecx
0x18006b83f  and     ecx, r8d
0x18006b842  lea     rcx, [rcx+rcx*4]
0x18006b846  shl     rcx, 5
0x18006b84a  add     r12, rcx
0x18006b84d  neg     edx
0x18006b84f  movzx   r15d, word ptr [rcx+r9+7Ch]
0x18006b855  sbb     eax, eax
0x18006b857  and     eax, r8d
0x18006b85a  lea     rcx, [rax+rax*4]
0x18006b85e  mov     rax, [r9+3D8h]
0x18006b865  shl     rcx, 5
0x18006b869  mov     dil, [rcx+r9+5Ch]
0x18006b86e  mov     [rsp+200h+var_1D0], dil
0x18006b873  mov     rdi, [rsp+200h+var_1C0]
0x18006b878  test    rax, rax
0x18006b87b  jz      short loc_18006B8A1
0x18006b87d  mov     rax, [rax+8]
0x18006b881  mov     ebx, [rax+30h]
0x18006b884  shr     ebx, 8
0x18006b887  and     bl, 1
0x18006b88a  jmp     short loc_18006B8A1
0x18006b88c  mov     r12, r11
0x18006b88f  mov     [rsp+200h+var_1D0], r11b
0x18006b894  mov     r15d, r11d
0x18006b897  lea     r14, [rsp+200h+var_188]
0x18006b89c  mov     r13, r11
0x18006b89f  mov     bl, 1
0x18006b8a1  lea     r8, [rsp+200h+var_1CE]
0x18006b8a6  mov     rcx, r10
0x18006b8a9  lea     rdx, [rsp+200h+var_1A0]
0x18006b8ae  call    CiSanitizeFileName
0x18006b8b3  mov     rsi, [rsp+200h+var_1A0+8]
0x18006b8b8  xor     r9d, r9d
0x18006b8bb  test    eax, eax
0x18006b8bd  js      loc_18006BADC
0x18006b8c3  lea     r8, [rsp+200h+var_1CF]
0x18006b8c8  mov     rcx, rdi
0x18006b8cb  lea     rdx, [rsp+200h+P]
0x18006b8d0  call    CiSanitizeFileName
0x18006b8d5  mov     rdi, [rsp+200h+P+8]
0x18006b8da  xor     r9d, r9d
0x18006b8dd  test    eax, eax
0x18006b8df  js      loc_18006BABE
0x18006b8e5  mov     eax, cs:dword_180048128
0x18006b8eb  cmp     eax, 5
0x18006b8ee  jbe     loc_18006BABE
0x18006b8f4  mov     rdx, 800000000000h
0x18006b8fe  lea     rcx, dword_180048128
0x18006b905  call    _tlgKeywordOn
0x18006b90a  test    al, al
0x18006b90c  jz      loc_18006BABE
0x18006b912  mov     rcx, [rsp+200h+var_1B8]
0x18006b917  lea     r10d, [r9+1]
0x18006b91b  lea     rax, [rsp+200h+var_190]
0x18006b920  mov     [rsp+200h+var_190], r10
0x18006b925  mov     [rbp+100h+var_150], rax
0x18006b929  lea     rax, [rbp+100h+var_128]
0x18006b92d  mov     [rbp+100h+var_140], rax
0x18006b931  movzx   eax, word ptr [rsp+200h+var_1A0]
0x18006b936  mov     [rbp+100h+var_128], eax
0x18006b939  lea     rax, [rbp+100h+var_108]
0x18006b93d  mov     [rbp+100h+var_120], rax
0x18006b941  movzx   eax, word ptr [rsp+200h+P]
0x18006b946  mov     [rbp+100h+var_108], eax
0x18006b949  mov     eax, [rbp+100h+arg_20]
0x18006b94f  mov     dword ptr [rsp+200h+var_1C0], eax
0x18006b953  lea     rax, [rsp+200h+var_1C0]
0x18006b958  mov     [rbp+100h+var_100], rax
0x18006b95c  mov     al, [rcx+2Eh]
0x18006b95f  and     al, r10b
0x18006b962  mov     [rbp+100h+var_148], 8
0x18006b96a  mov     [rsp+200h+var_1CD], al
0x18006b96e  lea     rax, [rsp+200h+var_1CD]
0x18006b973  mov     [rbp+100h+var_F0], rax
0x18006b977  mov     rax, [rcx+20h]
0x18006b97b  mov     [rsp+200h+var_1B8], rax
0x18006b980  lea     rax, [rsp+200h+var_1B8]
0x18006b985  mov     [rbp+100h+var_E0], rax
0x18006b989  mov     al, [rsp+200h+var_1D0]
0x18006b98d  mov     [rsp+200h+var_1D0], al
0x18006b991  lea     rax, [rsp+200h+var_1D0]
0x18006b996  mov     [rbp+100h+var_D0], rax
0x18006b99a  lea     rax, [rbp+100h+var_A8]
0x18006b99e  mov     [rbp+100h+var_C0], rax
0x18006b9a2  mov     rax, [r14+8]
0x18006b9a6  mov     [rbp+100h+var_B0], rax
0x18006b9aa  movzx   eax, word ptr [r14]
0x18006b9ae  mov     [rbp+100h+var_A8], eax
0x18006b9b1  lea     rax, [rsp+200h+P]
0x18006b9b6  mov     [rbp+100h+var_A0], rax
0x18006b9ba  lea     rax, [rsp+200h+var_1C8]
0x18006b9bf  mov     [rbp+100h+var_90], rax
0x18006b9c3  movzx   eax, r15w
0x18006b9c7  mov     [rbp+100h+var_78], eax
0x18006b9cd  lea     rax, [rsp+200h+var_1CC]
0x18006b9d2  mov     [rbp+100h+var_70], rax
0x18006b9d9  mov     [rbp+100h+var_138], 2
0x18006b9e1  mov     [rbp+100h+var_130], rsi
0x18006b9e5  mov     [rbp+100h+var_124], r9d
0x18006b9e9  mov     [rbp+100h+var_118], 2
0x18006b9f1  mov     [rbp+100h+var_110], rdi
0x18006b9f5  mov     [rbp+100h+var_104], r9d
0x18006b9f9  mov     [rbp+100h+var_F8], 4
0x18006ba01  mov     [rbp+100h+var_E8], r10
0x18006ba05  mov     [rbp+100h+var_D8], 8
0x18006ba0d  mov     [rbp+100h+var_C8], r10
0x18006ba11  mov     [rbp+100h+var_B8], 2
0x18006ba19  mov     [rbp+100h+var_A4], r9d
0x18006ba1d  mov     [rsp+200h+P], r13
0x18006ba22  mov     [rbp+100h+var_98], 8
0x18006ba2a  mov     [rsp+200h+var_1C8], r15w
0x18006ba30  mov     [rbp+100h+var_88], 2
0x18006ba38  mov     [rbp+100h+var_80], r12
0x18006ba3f  mov     [rbp+100h+var_74], r9d
0x18006ba46  mov     [rsp+200h+var_1CC], bl
0x18006ba4a  mov     [rbp+100h+var_68], r10
0x18006ba51  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x18006ba58  nop     dword ptr [rax+rax+00h]
0x18006ba5d  mov     r9d, 13h; int
0x18006ba63  mov     [rbp+100h+var_58], 1
0x18006ba6e  mov     [rsp+200h+var_1CB], al
0x18006ba72  lea     rdx, byte_18003DE69; int
0x18006ba79  lea     rax, [rsp+200h+var_1CB]
0x18006ba7e  mov     [rbp+100h+var_48], 8
0x18006ba89  mov     [rbp+100h+var_60], rax
0x18006ba90  lea     rcx, dword_180048128; int
0x18006ba97  mov     eax, 80000000h
0x18006ba9c  mov     [rsp+200h+var_1A0], rax
0x18006baa1  lea     rax, [rsp+200h+var_1A0]
0x18006baa6  mov     [rbp+100h+var_50], rax
0x18006baad  lea     rax, [rbp+100h+var_170]
0x18006bab1  mov     [rsp+200h+var_1E0], rax; PEVENT_DATA_DESCRIPTOR
0x18006bab6  call    _tlgWriteAgg
0x18006babb  xor     r9d, r9d
0x18006babe  cmp     [rsp+200h+var_1CF], r9b
0x18006bac3  jz      short loc_18006BADC
0x18006bac5  mov     edx, 63734943h; Tag
0x18006baca  mov     rcx, rdi; P
0x18006bacd  call    cs:__imp_ExFreePoolWithTag
0x18006bad4  nop     dword ptr [rax+rax+00h]
0x18006bad9  xor     r9d, r9d
0x18006badc  cmp     [rsp+200h+var_1CE], r9b
0x18006bae1  jz      short loc_18006BAF7
0x18006bae3  mov     edx, 63734943h; Tag
0x18006bae8  mov     rcx, rsi; P
0x18006baeb  call    cs:__imp_ExFreePoolWithTag
0x18006baf2  nop     dword ptr [rax+rax+00h]
0x18006baf7  mov     rcx, [rbp+100h+var_40]
0x18006bafe  xor     rcx, rsp; StackCookie
0x18006bb01  call    __security_check_cookie
0x18006bb06  mov     rbx, [rsp+200h+arg_0]
0x18006bb0e  add     rsp, 1D0h
0x18006bb15  pop     r15
0x18006bb17  pop     r14
0x18006bb19  pop     r13
0x18006bb1b  pop     r12
0x18006bb1d  pop     rdi
0x18006bb1e  pop     rsi
0x18006bb1f  pop     rbp
0x18006bb20  retn
```
