# VRS::ReadAndVerify(ulong,ulong *,ulong *)

- ea: `0x180074ba8`
- end: `0x180075072`
- name: `?ReadAndVerify@VRS@@QEAAEKPEAK0@Z`
- size: `1226`
- prototype: `unsigned __int8 __fastcall(VRS *__hidden this, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18006b540`

## callees

- `0x180028568`
- `0x18002db48`
- `0x180074ba8`
- `0x180075078`
- `0x180075180`
- `0x1800751d8`
- `0x18007524c`
- `0x180075310`
- `0x18007d0b0`
- `0x180088010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180075055`
- `ntdll!RtlFreeHeap` at `0x180075055`
- `ntdll!RtlAllocateHeap` at `0x180074c81`
- `ntdll!RtlAllocateHeap` at `0x180074c81`

## pseudocode

```c
unsigned __int8 __fastcall VRS::ReadAndVerify(VRS *this, int a2, unsigned int *a3, unsigned int *a4)
{
  VRS *v6; // rsi
  unsigned int v7; // eax
  unsigned __int64 v8; // rbp
  unsigned int v9; // r15d
  int v10; // ebx
  int v11; // eax
  char *Heap; // rax
  char *v13; // r12
  int v14; // r14d
  unsigned int v15; // ebp
  int v16; // edi
  int v17; // eax
  int v18; // ebx
  unsigned int v19; // eax
  unsigned int v20; // r13d
  __int64 v21; // rcx
  unsigned __int64 v22; // rdx
  __int64 v23; // r8
  unsigned int v24; // esi
  PVOID *v25; // rcx
  unsigned int v26; // eax
  const char *v27; // r9
  __int64 v28; // rdx
  char v29; // bl
  int v31; // [rsp+40h] [rbp-78h]
  unsigned int v32; // [rsp+44h] [rbp-74h]
  unsigned int v33; // [rsp+48h] [rbp-70h]
  int v34; // [rsp+50h] [rbp-68h]
  unsigned int v35; // [rsp+58h] [rbp-60h]
  char *P; // [rsp+60h] [rbp-58h]
  char v38; // [rsp+C8h] [rbp+10h]

  v6 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_60e6b7acf7153e8f1d9b3f92aac16d28_Traceguids);
  v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v6 + 2) + 24LL))(*((_QWORD *)v6 + 2));
  v8 = ((unsigned __int64)v7 + 2047) / v7;
  v35 = v8;
  v9 = a2 + 0x8000 / (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)v6 + 2) + 24LL))(*((_QWORD *)v6 + 2));
  v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v6 + 2) + 24LL))(*((_QWORD *)v6 + 2));
  if ( a3 )
    *a3 = v9;
  v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v6 + 2) + 24LL))(*((_QWORD *)v6 + 2));
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)(v8 * v11));
  P = Heap;
  if ( !Heap )
    return (unsigned __int8)Heap;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = v9 * v10;
  v18 = 0;
  v34 = v17;
  v19 = 0;
  v31 = 0;
  v20 = 0;
  v38 = 0;
  while ( 1 )
  {
    v32 = v19;
    if ( (((*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)v6 + 2) + 24LL))(*((_QWORD *)v6 + 2)) - 1) & v34) == 0 )
    {
      v13 = P;
      if ( !(unsigned __int8)IO_DP_DRIVE::Read(*((_QWORD *)v6 + 2), v9, v35, P) )
      {
        v25 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_55;
      }
      v9 += v35;
    }
    v24 = v20++;
    v33 = VRS::VerifyVsd(v21, (__int64)v13);
    v22 = v33;
    if ( !v33 )
    {
      v38 = 1;
      goto LABEL_50;
    }
    if ( v33 == 1 )
    {
      if ( !v16 )
      {
        if ( v31 )
        {
          v25 = (PVOID *)WPP_GLOBAL_Control;
          v22 = (unsigned __int64)&WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_31;
          WPP_SF_Lss(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"TEA01", (__int64)"BEA01");
        }
        v25 = (PVOID *)WPP_GLOBAL_Control;
        v22 = (unsigned __int64)&WPP_GLOBAL_Control;
LABEL_31:
        if ( v20 != 1 )
        {
          if ( v25 == &WPP_GLOBAL_Control )
          {
LABEL_48:
            v18 = 1;
            ++v16;
            goto LABEL_51;
          }
          if ( (*((_BYTE *)v25 + 28) & 1) != 0 )
          {
            WPP_SF_Ls(v25[2], &WPP_GLOBAL_Control, v23, v24);
            v25 = (PVOID *)WPP_GLOBAL_Control;
            v22 = (unsigned __int64)&WPP_GLOBAL_Control;
          }
        }
        if ( v25 == &WPP_GLOBAL_Control || (*((_BYTE *)v25 + 28) & 1) == 0 )
          goto LABEL_48;
        WPP_SF_(v25[2], 13, &WPP_60e6b7acf7153e8f1d9b3f92aac16d28_Traceguids);
LABEL_47:
        v25 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_48;
      }
      if ( v32 != 2 )
      {
        v25 = (PVOID *)WPP_GLOBAL_Control;
        v22 = (unsigned __int64)&WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_43;
        WPP_SF_ss(*((_QWORD *)WPP_GLOBAL_Control + 2), 14);
      }
      v25 = (PVOID *)WPP_GLOBAL_Control;
      v22 = (unsigned __int64)&WPP_GLOBAL_Control;
LABEL_43:
      if ( !v18 || v25 == &WPP_GLOBAL_Control || (*((_BYTE *)v25 + 28) & 1) == 0 )
        goto LABEL_48;
      WPP_SF_ss(v25[2], 15);
      goto LABEL_47;
    }
    v22 = v33 - 2;
    if ( v33 == 2 )
    {
      if ( v16 && v18 != 1 )
      {
        v25 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_24;
        WPP_SF_ss(*((_QWORD *)WPP_GLOBAL_Control + 2), 16);
      }
      v25 = (PVOID *)WPP_GLOBAL_Control;
LABEL_24:
      v18 = 0;
      ++v31;
      goto LABEL_51;
    }
    v22 = v33 - 8;
    if ( v33 == 8 )
    {
      ++v15;
LABEL_50:
      v25 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_51;
    }
    v25 = (PVOID *)WPP_GLOBAL_Control;
    if ( v33 == 10 )
      ++v14;
LABEL_51:
    v6 = this;
    v34 += 2048;
    v13 += 2048;
    if ( v38 )
      break;
    v19 = v33;
  }
  v13 = P;
LABEL_55:
  if ( a3 && a4 )
  {
    v26 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v6 + 2) + 24LL))(*((_QWORD *)v6 + 2));
    v25 = (PVOID *)WPP_GLOBAL_Control;
    v23 = v26;
    v22 = ((unsigned __int64)v26 + ((__int64)(int)(v20 - 1) << 11) - 1) % v26;
    *a4 = ((unsigned __int64)v26 + ((__int64)(int)(v20 - 1) << 11) - 1) / v26;
  }
  if ( v16 )
  {
    if ( v25 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v25 + 28) & 1) != 0 )
      {
        WPP_SF_(v25[2], 17, &WPP_60e6b7acf7153e8f1d9b3f92aac16d28_Traceguids);
        v25 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_62;
    }
LABEL_71:
    v29 = 1;
    if ( v32 != 2 )
    {
      if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 )
      {
        v28 = 20;
        v27 = "TEA01";
        goto LABEL_75;
      }
      goto LABEL_76;
    }
  }
  else
  {
LABEL_62:
    if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 )
    {
      WPP_SF_(v25[2], 18, &WPP_60e6b7acf7153e8f1d9b3f92aac16d28_Traceguids);
      v25 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v16 )
      goto LABEL_71;
    if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 )
    {
      v27 = "Empty";
      if ( v20 )
        v27 = "No Extended Area in";
      v28 = 19;
LABEL_75:
      WPP_SF_s(v25[2], v28, &WPP_60e6b7acf7153e8f1d9b3f92aac16d28_Traceguids, v27);
      v25 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_76:
    v29 = 0;
  }
  if ( v15 && v14 )
  {
    if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 )
      WPP_SF_LsLs(v25[2], v22, v23, v15);
    goto LABEL_86;
  }
  if ( !(v14 + v15) )
  {
    if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 )
      WPP_SF_(v25[2], 22, &WPP_60e6b7acf7153e8f1d9b3f92aac16d28_Traceguids);
LABEL_86:
    v29 = 0;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
  LOBYTE(Heap) = v29;
  *((_BYTE *)v6 + 24) = 1;
  return (unsigned __int8)Heap;
}

```

## disassembly

```asm
0x180074ba8  mov     [rsp+arg_18], r9
0x180074bad  mov     [rsp+arg_10], r8
0x180074bb2  mov     [rsp+arg_0], rcx
0x180074bb7  push    rbx
0x180074bb8  push    rbp
0x180074bb9  push    rsi
0x180074bba  push    rdi
0x180074bbb  push    r12
0x180074bbd  push    r13
0x180074bbf  push    r14
0x180074bc1  push    r15
0x180074bc3  sub     rsp, 78h
0x180074bc7  mov     rdi, r8
0x180074bca  mov     ebx, edx
0x180074bcc  mov     rsi, rcx
0x180074bcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180074bd6  lea     rax, WPP_GLOBAL_Control
0x180074bdd  cmp     rcx, rax
0x180074be0  jz      short loc_180074BFD
0x180074be2  test    byte ptr [rcx+1Ch], 1
0x180074be6  jz      short loc_180074BFD
0x180074be8  mov     rcx, [rcx+10h]
0x180074bec  lea     r8, WPP_60e6b7acf7153e8f1d9b3f92aac16d28_Traceguids
0x180074bf3  mov     edx, 0Ah
0x180074bf8  call    WPP_SF_
0x180074bfd  mov     rcx, [rsi+10h]
0x180074c01  mov     rax, [rcx]
0x180074c04  mov     rax, [rax+18h]
0x180074c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074c0d  mov     ecx, eax
0x180074c0f  xor     edx, edx
0x180074c11  lea     rax, [rcx+7FFh]
0x180074c18  div     rcx
0x180074c1b  mov     rcx, [rsi+10h]
0x180074c1f  mov     rbp, rax
0x180074c22  mov     [rsp+0B8h+var_60], rax
0x180074c27  mov     rdx, [rcx]
0x180074c2a  mov     rax, [rdx+18h]
0x180074c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074c33  mov     ecx, eax
0x180074c35  xor     edx, edx
0x180074c37  mov     eax, 8000h
0x180074c3c  div     ecx
0x180074c3e  mov     rcx, [rsi+10h]
0x180074c42  mov     rdx, [rcx]
0x180074c45  lea     r15d, [rbx+rax]
0x180074c49  mov     rax, [rdx+18h]
0x180074c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074c52  mov     ebx, eax
0x180074c54  test    rdi, rdi
0x180074c57  jz      short loc_180074C5C
0x180074c59  mov     [rdi], r15d
0x180074c5c  mov     rcx, [rsi+10h]
0x180074c60  mov     rdx, [rcx]
0x180074c63  mov     rax, [rdx+18h]
0x180074c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074c6c  mov     rcx, gs:60h
0x180074c75  xor     edx, edx; Flags
0x180074c77  imul    eax, ebp
0x180074c7a  mov     rcx, [rcx+30h]; HeapHandle
0x180074c7e  mov     r8d, eax; Size
0x180074c81  call    cs:__imp_RtlAllocateHeap
0x180074c87  mov     [rsp+0B8h+P], rax
0x180074c8c  test    rax, rax
0x180074c8f  jz      loc_180075061
0x180074c95  imul    ebx, r15d
0x180074c99  xor     r12d, r12d
0x180074c9c  xor     r14d, r14d
0x180074c9f  xor     ebp, ebp
0x180074ca1  xor     edi, edi
0x180074ca3  mov     eax, ebx
0x180074ca5  xor     ebx, ebx
0x180074ca7  mov     [rsp+0B8h+var_68], rax
0x180074cac  xor     eax, eax
0x180074cae  mov     [rsp+0B8h+var_78], eax
0x180074cb2  xor     r13d, r13d
0x180074cb5  mov     [rsp+0B8h+arg_8], al
0x180074cbc  mov     rcx, [rsi+10h]
0x180074cc0  mov     [rsp+0B8h+var_74], eax
0x180074cc4  mov     rax, [rcx]
0x180074cc7  mov     rax, [rax+18h]
0x180074ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074cd0  dec     eax
0x180074cd2  test    [rsp+0B8h+var_68], rax
0x180074cd7  jnz     short loc_180074CFF
0x180074cd9  mov     r12, [rsp+0B8h+P]
0x180074cde  mov     r8d, dword ptr [rsp+0B8h+var_60]
0x180074ce3  mov     r9, r12
0x180074ce6  mov     rcx, [rsi+10h]
0x180074cea  mov     edx, r15d
0x180074ced  call    ?Read@IO_DP_DRIVE@@QEAAEVBIG_INT@@KPEAX@Z; IO_DP_DRIVE::Read(BIG_INT,ulong,void *)
0x180074cf2  test    al, al
0x180074cf4  jz      loc_180074EDA
0x180074cfa  add     r15d, dword ptr [rsp+0B8h+var_60]
0x180074cff  mov     rdx, r12
0x180074d02  mov     esi, r13d
0x180074d05  call    ?VerifyVsd@VRS@@AEAA?AW4_VSD_IDENT@@PEAUVSD_GENERIC@@@Z; VRS::VerifyVsd(VSD_GENERIC *)
0x180074d0a  inc     r13d
0x180074d0d  mov     [rsp+0B8h+var_70], eax
0x180074d11  mov     edx, eax
0x180074d13  test    eax, eax
0x180074d15  jz      loc_180074EA3
0x180074d1b  sub     edx, 1
0x180074d1e  jz      short loc_180074D8B
0x180074d20  sub     edx, 1
0x180074d23  jz      short loc_180074D49
0x180074d25  sub     edx, 6
0x180074d28  jz      short loc_180074D42
0x180074d2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180074d31  cmp     edx, 2
0x180074d34  jnz     loc_180074EB2
0x180074d3a  inc     r14d
0x180074d3d  jmp     loc_180074EB2
0x180074d42  inc     ebp
0x180074d44  jmp     loc_180074EAB
0x180074d49  test    edi, edi
0x180074d4b  jz      short loc_180074D79
0x180074d4d  cmp     ebx, 1
0x180074d50  jz      short loc_180074D79
0x180074d52  mov     rcx, cs:WPP_GLOBAL_Control
0x180074d59  lea     rax, WPP_GLOBAL_Control
0x180074d60  cmp     rcx, rax
0x180074d63  jz      short loc_180074D80
0x180074d65  test    byte ptr [rcx+1Ch], 1
0x180074d69  jz      short loc_180074D80
0x180074d6b  mov     rcx, [rcx+10h]
0x180074d6f  mov     edx, 10h
0x180074d74  call    WPP_SF_ss
0x180074d79  mov     rcx, cs:WPP_GLOBAL_Control
0x180074d80  xor     ebx, ebx
0x180074d82  inc     [rsp+0B8h+var_78]
0x180074d86  jmp     loc_180074EB2
0x180074d8b  test    edi, edi
0x180074d8d  jnz     loc_180074E3A
0x180074d93  mov     eax, [rsp+0B8h+var_78]
0x180074d97  test    eax, eax
0x180074d99  jz      short loc_180074DDB
0x180074d9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180074da2  lea     rdx, WPP_GLOBAL_Control
0x180074da9  cmp     rcx, rdx
0x180074dac  jz      short loc_180074DE9
0x180074dae  test    byte ptr [rcx+1Ch], 1
0x180074db2  jz      short loc_180074DE9
0x180074db4  mov     rcx, [rcx+10h]; LoggerHandle
0x180074db8  lea     r8, aBea01; "BEA01"
0x180074dbf  mov     [rsp+0B8h+var_90], r8; __int64
0x180074dc4  lea     edx, [rdi+0Bh]
0x180074dc7  lea     r8, aTea01; "TEA01"
0x180074dce  mov     r9d, eax
0x180074dd1  mov     [rsp+0B8h+var_98], r8; __int64
0x180074dd6  call    WPP_SF_Lss
0x180074ddb  mov     rcx, cs:WPP_GLOBAL_Control
0x180074de2  lea     rdx, WPP_GLOBAL_Control
0x180074de9  cmp     r13d, 1
0x180074ded  jz      short loc_180074E18
0x180074def  cmp     rcx, rdx
0x180074df2  jz      loc_180074E9A
0x180074df8  test    byte ptr [rcx+1Ch], 1
0x180074dfc  jz      short loc_180074E18
0x180074dfe  mov     rcx, [rcx+10h]
0x180074e02  mov     r9d, esi
0x180074e05  call    WPP_SF_Ls
0x180074e0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180074e11  lea     rdx, WPP_GLOBAL_Control
0x180074e18  cmp     rcx, rdx
0x180074e1b  jz      short loc_180074E9A
0x180074e1d  test    byte ptr [rcx+1Ch], 1
0x180074e21  jz      short loc_180074E9A
0x180074e23  mov     rcx, [rcx+10h]
0x180074e27  lea     r8, WPP_60e6b7acf7153e8f1d9b3f92aac16d28_Traceguids
0x180074e2e  mov     edx, 0Dh
0x180074e33  call    WPP_SF_
0x180074e38  jmp     short loc_180074E93
0x180074e3a  cmp     [rsp+0B8h+var_74], 2
0x180074e3f  jz      short loc_180074E68
0x180074e41  mov     rcx, cs:WPP_GLOBAL_Control
0x180074e48  lea     rdx, WPP_GLOBAL_Control
0x180074e4f  cmp     rcx, rdx
0x180074e52  jz      short loc_180074E76
0x180074e54  test    byte ptr [rcx+1Ch], 1
0x180074e58  jz      short loc_180074E76
0x180074e5a  mov     rcx, [rcx+10h]
0x180074e5e  mov     edx, 0Eh
0x180074e63  call    WPP_SF_ss
0x180074e68  mov     rcx, cs:WPP_GLOBAL_Control
0x180074e6f  lea     rdx, WPP_GLOBAL_Control
0x180074e76  test    ebx, ebx
0x180074e78  jz      short loc_180074E9A
0x180074e7a  cmp     rcx, rdx
0x180074e7d  jz      short loc_180074E9A
0x180074e7f  test    byte ptr [rcx+1Ch], 1
0x180074e83  jz      short loc_180074E9A
0x180074e85  mov     rcx, [rcx+10h]
0x180074e89  mov     edx, 0Fh
0x180074e8e  call    WPP_SF_ss
0x180074e93  mov     rcx, cs:WPP_GLOBAL_Control
0x180074e9a  mov     ebx, 1
0x180074e9f  inc     edi
0x180074ea1  jmp     short loc_180074EB2
0x180074ea3  mov     [rsp+0B8h+arg_8], 1
0x180074eab  mov     rcx, cs:WPP_GLOBAL_Control
0x180074eb2  mov     rsi, [rsp+0B8h+arg_0]
0x180074eba  mov     eax, 800h
0x180074ebf  add     [rsp+0B8h+var_68], rax
0x180074ec4  add     r12, rax
0x180074ec7  cmp     [rsp+0B8h+arg_8], 0
0x180074ecf  jnz     short loc_180074EE3
0x180074ed1  mov     eax, [rsp+0B8h+var_70]
0x180074ed5  jmp     loc_180074CBC
0x180074eda  mov     rcx, cs:WPP_GLOBAL_Control
0x180074ee1  jmp     short loc_180074EE8
0x180074ee3  mov     r12, [rsp+0B8h+P]
0x180074ee8  cmp     [rsp+0B8h+arg_10], 0
0x180074ef1  jz      short loc_180074F31
0x180074ef3  mov     rbx, [rsp+0B8h+arg_18]
0x180074efb  test    rbx, rbx
0x180074efe  jz      short loc_180074F31
0x180074f00  mov     rcx, [rsi+10h]
0x180074f04  mov     rax, [rcx]
0x180074f07  mov     rax, [rax+18h]
0x180074f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074f10  mov     rcx, cs:WPP_GLOBAL_Control
0x180074f17  xor     edx, edx
0x180074f19  mov     r8d, eax
0x180074f1c  lea     eax, [r13-1]
0x180074f20  cdqe
0x180074f22  shl     rax, 0Bh
0x180074f26  dec     rax
0x180074f29  add     rax, r8
0x180074f2c  div     r8
0x180074f2f  mov     [rbx], eax
0x180074f31  test    edi, edi
0x180074f33  jz      short loc_180074F65
0x180074f35  lea     r15, WPP_GLOBAL_Control
0x180074f3c  cmp     rcx, r15
0x180074f3f  jz      short loc_180074FBC
0x180074f41  test    byte ptr [rcx+1Ch], 1
0x180074f45  jz      short loc_180074F6C
0x180074f47  mov     rcx, [rcx+10h]
0x180074f4b  lea     r8, WPP_60e6b7acf7153e8f1d9b3f92aac16d28_Traceguids
0x180074f52  mov     edx, 11h
0x180074f57  call    WPP_SF_
0x180074f5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180074f63  jmp     short loc_180074F6C
0x180074f65  lea     r15, WPP_GLOBAL_Control
0x180074f6c  cmp     rcx, r15
0x180074f6f  jz      short loc_180074F93
0x180074f71  test    byte ptr [rcx+1Ch], 1
0x180074f75  jz      short loc_180074F93
0x180074f77  mov     rcx, [rcx+10h]
0x180074f7b  lea     r8, WPP_60e6b7acf7153e8f1d9b3f92aac16d28_Traceguids
0x180074f82  mov     edx, 12h
0x180074f87  call    WPP_SF_
0x180074f8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180074f93  test    edi, edi
0x180074f95  jnz     short loc_180074FBC
0x180074f97  cmp     rcx, r15
0x180074f9a  jz      short loc_180074FF2
0x180074f9c  test    byte ptr [rcx+1Ch], 1
0x180074fa0  jz      short loc_180074FF2
0x180074fa2  test    r13d, r13d
0x180074fa5  lea     rax, aNoExtendedArea; "No Extended Area in"
0x180074fac  lea     r9, aEmpty; "Empty"
0x180074fb3  cmovnz  r9, rax
0x180074fb7  lea     edx, [rdi+13h]
0x180074fba  jmp     short loc_180074FDB
0x180074fbc  cmp     [rsp+0B8h+var_74], 2
0x180074fc1  mov     bl, 1
0x180074fc3  jz      short loc_180074FF4
0x180074fc5  cmp     rcx, r15
0x180074fc8  jz      short loc_180074FF2
0x180074fca  test    [rcx+1Ch], bl
0x180074fcd  jz      short loc_180074FF2
0x180074fcf  mov     edx, 14h
0x180074fd4  lea     r9, aTea01; "TEA01"
0x180074fdb  mov     rcx, [rcx+10h]
0x180074fdf  lea     r8, WPP_60e6b7acf7153e8f1d9b3f92aac16d28_Traceguids
0x180074fe6  call    WPP_SF_s
0x180074feb  mov     rcx, cs:WPP_GLOBAL_Control
0x180074ff2  xor     bl, bl
0x180074ff4  test    ebp, ebp
0x180074ff6  jz      short loc_18007501B
0x180074ff8  test    r14d, r14d
0x180074ffb  jz      short loc_18007501B
0x180074ffd  cmp     rcx, r15
0x180075000  jz      short loc_180075041
0x180075002  test    byte ptr [rcx+1Ch], 1
0x180075006  jz      short loc_180075041
0x180075008  mov     rcx, [rcx+10h]
0x18007500c  mov     r9d, ebp
0x18007500f  mov     dword ptr [rsp+0B8h+var_90], r14d
0x180075014  call    WPP_SF_LsLs
0x180075019  jmp     short loc_180075041
0x18007501b  lea     eax, [r14+rbp]
0x18007501f  test    eax, eax
0x180075021  jnz     short loc_180075043
0x180075023  cmp     rcx, r15
0x180075026  jz      short loc_180075041
0x180075028  test    byte ptr [rcx+1Ch], 1
0x18007502c  jz      short loc_180075041
  ... truncated ...
```
