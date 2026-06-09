# LdrpResolveForwarder

- ea: `0x180050260`
- end: `0x1800507a5`
- name: `LdrpResolveForwarder`
- size: `1349`
- prototype: `__int64 __fastcall(char *Str)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callers

- `0x1800ac3d0`

## callees

- `0x18001861c`
- `0x18001eb80`
- `0x18001f070`
- `0x180029120`
- `0x180050260`
- `0x180051900`
- `0x1800680b0`
- `0x1800c54a0`
- `0x180119e50`
- `0x18012b9f0`

## string_xrefs

- `0x18005042b`: `LdrpGetProcedureAddress`
- `0x18005059d`: `Procedure "%s" could not be located in DLL at base 0x%p.\n`

## pseudocode

```c
__int64 __fastcall LdrpResolveForwarder(char *Str, int a2, __int64 a3, __int64 *a4)
{
  __int64 v4; // rbp
  int v5; // r15d
  __int64 *v6; // r14
  __int64 v8; // r13
  char *v10; // rax
  __int16 v11; // bx
  char *ArgList; // rsi
  int DependentModuleA; // eax
  unsigned int v14; // edi
  unsigned __int64 v15; // r14
  bool v16; // bl
  unsigned __int64 v17; // rdi
  __int16 v18; // cx
  __int64 v19; // rax
  __int64 v20; // rcx
  int v21; // ecx
  char *v22; // rbp
  int v23; // ebx
  int v24; // r10d
  int j; // eax
  int v26; // eax
  int v27; // r11d
  __int64 v28; // r9
  char *v29; // rcx
  unsigned __int64 v30; // r8
  int v31; // eax
  int v32; // edx
  ULONG v33; // ebx
  unsigned __int64 v34; // rbx
  __int64 v35; // rcx
  __int64 v37; // r10
  unsigned int *v38; // rdx
  unsigned int i; // r9d
  __int64 v40; // r8
  ULONG v41; // ebx
  __int64 v42; // rax
  int v43; // [rsp+40h] [rbp-78h]
  __int64 v44; // [rsp+48h] [rbp-70h] BYREF
  __int64 v45; // [rsp+50h] [rbp-68h] BYREF
  __int64 v46; // [rsp+58h] [rbp-60h] BYREF
  __int64 v47; // [rsp+60h] [rbp-58h]
  __int128 v48; // [rsp+68h] [rbp-50h] BYREF
  __int64 v49; // [rsp+78h] [rbp-40h]
  ULONG Value; // [rsp+D0h] [rbp+18h] BYREF
  __int64 *v51; // [rsp+D8h] [rbp+20h]

  v51 = a4;
  v4 = *(_QWORD *)(a3 + 176);
  v5 = 0;
  Value = 0;
  v48 = 0;
  v43 = 0;
  v6 = a4;
  v44 = 0;
  v47 = v4;
  LODWORD(v8) = a2;
  v46 = 0;
  while ( 1 )
  {
    v10 = strrchr(Str, 46);
    if ( !v10 || (v11 = (_WORD)v10 - (_WORD)Str, (unsigned __int64)(v10 - Str) > 0xFFFF) )
    {
LABEL_64:
      v14 = -1073741701;
      goto LABEL_42;
    }
    ArgList = v10 + 1;
    *((_QWORD *)&v48 + 1) = Str;
    LOWORD(v48) = (_WORD)v10 - (_WORD)Str;
    WORD1(v48) = (_WORD)v10 - (_WORD)Str;
    if ( v10[1] == 35 )
    {
      if ( RtlCharToInteger(v10 + 2, 0, &Value) < 0 )
        goto LABEL_64;
      ArgList = 0;
    }
    if ( v11 == 5 && (*(_DWORD *)Str | 0x20202020) == 0x6C64746E && ((unsigned __int8)Str[4] | 0x20) == 0x6C )
    {
      v8 = LdrpNtDllDataTableEntry;
      v44 = LdrpNtDllDataTableEntry;
    }
    else
    {
      DependentModuleA = LdrpLoadDependentModuleA((unsigned int)&v48, v4, v8, 1, (__int64)&v44, (__int64)&v46);
      v14 = DependentModuleA;
      if ( DependentModuleA < 0 || DependentModuleA == 259 )
        goto LABEL_42;
      v8 = v44;
    }
    if ( (*(_DWORD *)(*(_QWORD *)(a3 + 176) + 32LL) & 0x2000000) != 0 )
    {
      if ( ArgList )
      {
        v42 = LdrpCheckRedirection(a3, v8, ArgList);
        *v6 = v42;
        if ( v42 != -4530927 )
          return 0;
      }
    }
    v15 = *(_QWORD *)(v8 + 48);
    v45 = 0;
    if ( (v15 & 2) != 0 || (v15 & 1) != 0 )
    {
      v17 = v15 & 0xFFFFFFFFFFFFFFFCuLL;
      v16 = !(v15 & 1);
    }
    else
    {
      v16 = 1;
      v17 = v15;
    }
    RtlImageNtHeaderEx(1, v17, 0, &v45);
    if ( !v45 )
      goto LABEL_50;
    v18 = *(_WORD *)(v45 + 24);
    v19 = 0;
    if ( v18 == 267 )
    {
      if ( !*(_DWORD *)(v45 + 116) )
        goto LABEL_61;
      v37 = *(unsigned int *)(v45 + 120);
      if ( (_DWORD)v37 )
      {
        v5 = *(_DWORD *)(v45 + 124);
        if ( !v16 && (unsigned int)v37 >= *(_DWORD *)(v45 + 84) )
        {
          v38 = (unsigned int *)(v45 + *(unsigned __int16 *)(v45 + 20) + 24LL);
          for ( i = 0; i < *(unsigned __int16 *)(v45 + 6); ++i )
          {
            v40 = v38[3];
            if ( (unsigned int)v37 >= (unsigned int)v40 && (unsigned int)v37 < (unsigned int)v40 + v38[4] )
            {
              v19 = v37 + v17 + v38[5] - v40;
              if ( v19 )
                goto LABEL_23;
              break;
            }
            v38 += 10;
          }
LABEL_61:
          v21 = -1073741811;
          goto LABEL_24;
        }
        v19 = v17 + v37;
        v21 = 0;
      }
      else
      {
        v21 = -1073741822;
      }
    }
    else
    {
      if ( v18 != 523 || !*(_DWORD *)(v45 + 132) )
        goto LABEL_61;
      v20 = *(unsigned int *)(v45 + 136);
      if ( (_DWORD)v20 )
      {
        v5 = *(_DWORD *)(v45 + 140);
        if ( v16 || (unsigned int)v20 < *(_DWORD *)(v45 + 84) )
        {
          v19 = v17 + v20;
LABEL_23:
          v21 = 0;
        }
        else
        {
          v19 = RtlAddressInSectionTable(v45, v17, (unsigned int)v20);
          v21 = 0;
          if ( !v19 )
            v21 = -1073741811;
        }
      }
      else
      {
        v21 = -1073741822;
      }
    }
LABEL_24:
    v22 = 0;
    if ( v21 >= 0 )
      v22 = (char *)v19;
    if ( !v22 )
      goto LABEL_50;
    if ( ArgList )
    {
      LdrpLogInternal(
        (int)"minkernel\\ldr\\ldrsnap.c",
        838,
        (int)"LdrpGetProcedureAddress",
        2,
        "Locating procedure \"%s\" by name\n",
        (char)ArgList);
      v23 = 0;
      v24 = *((_DWORD *)v22 + 6) - 1;
      for ( j = v24; ; j = v23 + v24 )
      {
        v26 = j / 2;
        v27 = v26;
        if ( v24 < v23 )
          break;
        v28 = v26;
        v29 = ArgList;
        v30 = v15 + *(unsigned int *)(v15 + *((unsigned int *)v22 + 8) + 4LL * v26) - (_QWORD)ArgList;
        do
        {
          v31 = (unsigned __int8)v29[v30];
          v32 = (unsigned __int8)*v29 - v31;
          if ( v32 )
            break;
          ++v29;
        }
        while ( v31 );
        if ( !v32 )
        {
          v33 = *(unsigned __int16 *)(v15 + *((unsigned int *)v22 + 9) + 2 * v28);
          goto LABEL_35;
        }
        if ( v32 >= 0 )
          v23 = v27 + 1;
        else
          v24 = v27 - 1;
      }
      LdrpLogInternal(
        (int)"minkernel\\ldr\\ldrsnap.c",
        2286,
        (int)"LdrpNameToOrdinal",
        1,
        "Procedure \"%s\" could not be located in DLL at base 0x%p.\n",
        (char)ArgList);
LABEL_50:
      v14 = -1073741702;
      goto LABEL_42;
    }
    v41 = Value;
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrsnap.c",
      856,
      (int)"LdrpGetProcedureAddress",
      2,
      "Loading procedure 0x%lx by ordinal\n",
      Value);
    if ( !v41 )
    {
      v14 = -1073741811;
      goto LABEL_42;
    }
    v33 = v41 - *((_DWORD *)v22 + 4);
LABEL_35:
    if ( v33 >= *((_DWORD *)v22 + 5) )
    {
      v14 = (ArgList != 0) - 1073741512;
      goto LABEL_42;
    }
    Str = (char *)(v15 + *(unsigned int *)(v15 + *((unsigned int *)v22 + 7) + 4LL * (int)v33));
    v6 = v51;
    *v51 = (__int64)Str;
    if ( Str < v22 || Str >= &v22[v5] )
      break;
    if ( ++v43 == 32 )
      goto LABEL_64;
    LODWORD(v4) = v47;
    v5 = 0;
  }
  if ( qword_1801E3518 )
  {
    if ( (dword_1801E34FC & 1) != 0 )
    {
      v14 = 0;
    }
    else
    {
      v34 = *(_QWORD *)(v8 + 48);
      v35 = *((_QWORD *)&xmmword_1801E0450 + 1);
      v49 = 0;
      v48 = 0;
      if ( v34 < *((_QWORD *)&xmmword_1801E0450 + 1)
        || v34 >= *((_QWORD *)&xmmword_1801E0450 + 1) + (unsigned __int64)(unsigned int)qword_1801E0460 )
      {
        RtlpxLookupFunctionTable(v34, &v48);
        v35 = *((_QWORD *)&v48 + 1);
      }
      v14 = 0;
      if ( v35 != v34 )
        __fastfail(0x18u);
    }
  }
  else
  {
    v14 = 0;
  }
LABEL_42:
  if ( v46 )
    RtlFreeHeap_0(LdrpHeap, 0, v46);
  return v14;
}

```

## disassembly

```asm
0x180050260  mov     rax, rsp
0x180050263  mov     [rax+8], rbx
0x180050267  mov     [rax+20h], r9
0x18005026b  push    rbp
0x18005026c  push    rsi
0x18005026d  push    rdi
0x18005026e  push    r12
0x180050270  push    r13
0x180050272  push    r14
0x180050274  push    r15
0x180050276  sub     rsp, 80h
0x18005027d  mov     rbp, [r8+0B0h]
0x180050284  xor     r15d, r15d
0x180050287  xorps   xmm0, xmm0
0x18005028a  mov     [rax+18h], r15d
0x18005028e  movups  xmmword ptr [rax-50h], xmm0
0x180050292  mov     [rsp+0B8h+var_78], r15d
0x180050297  mov     r14, r9
0x18005029a  mov     [rax-70h], r15
0x18005029e  mov     r12, r8
0x1800502a1  mov     [rsp+0B8h+var_58], rbp
0x1800502a6  mov     r13, rdx
0x1800502a9  mov     [rax-60h], r15
0x1800502ad  mov     rdi, rcx
0x1800502b0  mov     edx, 2Eh ; '.'; Ch
0x1800502b5  mov     rcx, rdi; Str
0x1800502b8  call    strrchr
0x1800502bd  mov     rsi, rax
0x1800502c0  test    rax, rax
0x1800502c3  jz      loc_180050677
0x1800502c9  mov     rbx, rax
0x1800502cc  sub     rbx, rdi
0x1800502cf  cmp     rbx, 0FFFFh
0x1800502d6  ja      loc_180050677
0x1800502dc  inc     rsi
0x1800502df  mov     qword ptr [rsp+0B8h+var_50+8], rdi
0x1800502e4  mov     word ptr [rsp+0B8h+var_50], bx
0x1800502e9  mov     word ptr [rsp+0B8h+var_50+2], bx
0x1800502ee  cmp     byte ptr [rsi], 23h ; '#'
0x1800502f1  jz      loc_180050660
0x1800502f7  cmp     bx, 5
0x1800502fb  jnz     short loc_180050315
0x1800502fd  mov     eax, [rdi]
0x1800502ff  or      eax, 20202020h
0x180050304  cmp     eax, 6C64746Eh
0x180050309  jnz     short loc_180050315
0x18005030b  movzx   eax, byte ptr [rdi+4]
0x18005030f  or      al, 20h
0x180050311  cmp     al, 6Ch ; 'l'
0x180050313  jz      short loc_18005035B
0x180050315  lea     rax, [rsp+0B8h+var_60]
0x18005031a  mov     r9d, 1
0x180050320  mov     qword ptr [rsp+0B8h+ArgList], rax
0x180050325  lea     rcx, [rsp+0B8h+var_50]
0x18005032a  lea     rax, [rsp+0B8h+var_70]
0x18005032f  mov     r8, r13
0x180050332  mov     rdx, rbp
0x180050335  mov     [rsp+0B8h+Format], rax
0x18005033a  call    LdrpLoadDependentModuleA
0x18005033f  mov     edi, eax
0x180050341  test    eax, eax
0x180050343  js      loc_18005054D
0x180050349  cmp     eax, 103h
0x18005034e  jz      loc_18005054D
0x180050354  mov     r13, [rsp+0B8h+var_70]
0x180050359  jmp     short loc_180050367
0x18005035b  mov     r13, cs:LdrpNtDllDataTableEntry
0x180050362  mov     [rsp+0B8h+var_70], r13
0x180050367  mov     rax, [r12+0B0h]
0x18005036f  test    dword ptr [rax+20h], 2000000h
0x180050376  jnz     loc_180050778
0x18005037c  mov     r14, [r13+30h]
0x180050380  mov     rbx, r14
0x180050383  mov     [rsp+0B8h+var_68], r15
0x180050388  and     ebx, 1
0x18005038b  test    r14b, 2
0x18005038f  jnz     loc_180050651
0x180050395  test    rbx, rbx
0x180050398  jnz     loc_180050651
0x18005039e  mov     bl, 1
0x1800503a0  mov     rdi, r14
0x1800503a3  lea     r9, [rsp+0B8h+var_68]
0x1800503a8  xor     r8d, r8d
0x1800503ab  mov     rdx, rdi
0x1800503ae  mov     ecx, 1
0x1800503b3  call    RtlImageNtHeaderEx
0x1800503b8  mov     r9, [rsp+0B8h+var_68]
0x1800503bd  test    r9, r9
0x1800503c0  jz      loc_1800505CC
0x1800503c6  movzx   ecx, word ptr [r9+18h]
0x1800503cb  xor     eax, eax
0x1800503cd  mov     edx, 10Bh
0x1800503d2  cmp     cx, dx
0x1800503d5  jz      loc_1800505D6
0x1800503db  mov     edx, 20Bh
0x1800503e0  cmp     cx, dx
0x1800503e3  jnz     loc_180050647
0x1800503e9  cmp     [r9+84h], eax
0x1800503f0  jbe     loc_180050647
0x1800503f6  mov     ecx, [r9+88h]
0x1800503fd  test    ecx, ecx
0x1800503ff  jz      loc_1800506CD
0x180050405  mov     r15d, [r9+8Ch]
0x18005040c  test    bl, bl
0x18005040e  jz      loc_180050725
0x180050414  lea     rax, [rdi+rcx]
0x180050418  xor     ecx, ecx
0x18005041a  xor     ebp, ebp
0x18005041c  test    ecx, ecx
0x18005041e  cmovns  rbp, rax
0x180050422  test    rbp, rbp
0x180050425  jz      loc_1800505CC
0x18005042b  lea     r8, aLdrpgetprocedu; "LdrpGetProcedureAddress"
0x180050432  mov     r9d, 2; int
0x180050438  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x18005043f  test    rsi, rsi
0x180050442  jz      loc_1800506A0
0x180050448  lea     rax, aLocatingProced_0; "Locating procedure \"%s\" by name\n"
0x18005044f  mov     qword ptr [rsp+0B8h+ArgList], rsi; ArgList
0x180050454  mov     edx, 346h; int
0x180050459  mov     [rsp+0B8h+Format], rax; Format
0x18005045e  call    LdrpLogInternal
0x180050463  mov     edi, [rbp+20h]
0x180050466  xor     ebx, ebx
0x180050468  mov     r10d, [rbp+18h]
0x18005046c  add     rdi, r14
0x18005046f  dec     r10d
0x180050472  mov     eax, r10d
0x180050475  cdq
0x180050476  sub     eax, edx
0x180050478  sar     eax, 1
0x18005047a  mov     r11d, eax
0x18005047d  cmp     r10d, ebx
0x180050480  jl      loc_180050598
0x180050486  movsxd  r9, eax
0x180050489  mov     rcx, rsi
0x18005048c  mov     r8d, [rdi+r9*4]
0x180050490  add     r8, r14
0x180050493  sub     r8, rsi
0x180050496  nop     word ptr [rax+rax+00000000h]
0x1800504a0  movzx   edx, byte ptr [rcx]
0x1800504a3  movzx   eax, byte ptr [rcx+r8]
0x1800504a8  sub     edx, eax
0x1800504aa  jnz     short loc_1800504B3
0x1800504ac  inc     rcx
0x1800504af  test    eax, eax
0x1800504b1  jnz     short loc_1800504A0
0x1800504b3  test    edx, edx
0x1800504b5  jnz     loc_180050583
0x1800504bb  mov     ecx, [rbp+24h]
0x1800504be  add     rcx, r14
0x1800504c1  movzx   ebx, word ptr [rcx+r9*2]
0x1800504c6  cmp     ebx, [rbp+14h]
0x1800504c9  jnb     loc_18005075A
0x1800504cf  mov     ecx, [rbp+1Ch]
0x1800504d2  add     rcx, r14
0x1800504d5  movsxd  rdx, ebx
0x1800504d8  mov     edi, [rcx+rdx*4]
0x1800504db  add     rdi, r14
0x1800504de  mov     r14, [rsp+0B8h+arg_18]
0x1800504e6  mov     [r14], rdi
0x1800504e9  cmp     rdi, rbp
0x1800504ec  jnb     loc_1800506DE
0x1800504f2  cmp     cs:qword_1801E3518, 0
0x1800504fa  jz      loc_1800506D7
0x180050500  test    byte ptr cs:dword_1801E34FC, 1
0x180050507  jnz     loc_18005071E
0x18005050d  mov     rbx, [r13+30h]
0x180050511  xor     eax, eax
0x180050513  mov     rcx, qword ptr cs:xmmword_1801E0450+8
0x18005051a  xorps   xmm0, xmm0
0x18005051d  mov     [rsp+0B8h+var_40], rax
0x180050522  movups  [rsp+0B8h+var_50], xmm0
0x180050527  cmp     rbx, rcx
0x18005052a  jnb     loc_180050681
0x180050530  lea     rdx, [rsp+0B8h+var_50]
0x180050535  mov     rcx, rbx
0x180050538  call    RtlpxLookupFunctionTable
0x18005053d  mov     rcx, qword ptr [rsp+0B8h+var_50+8]
0x180050542  xor     edi, edi
0x180050544  cmp     rcx, rbx
0x180050547  jnz     loc_18005070D
0x18005054d  mov     r8, [rsp+0B8h+var_60]
0x180050552  test    r8, r8
0x180050555  jz      short loc_180050565
0x180050557  mov     rcx, cs:LdrpHeap
0x18005055e  xor     edx, edx
0x180050560  call    RtlFreeHeap_0
0x180050565  mov     eax, edi
0x180050567  mov     rbx, [rsp+0B8h+arg_0]
0x18005056f  add     rsp, 80h
0x180050576  pop     r15
0x180050578  pop     r14
0x18005057a  pop     r13
0x18005057c  pop     r12
0x18005057e  pop     rdi
0x18005057f  pop     rsi
0x180050580  pop     rbp
0x180050581  retn
0x180050583  jns     short loc_180050592
0x180050585  lea     r10d, [r11-1]
0x180050589  lea     eax, [rbx+r10]
0x18005058d  jmp     loc_180050475
0x180050592  lea     ebx, [r11+1]
0x180050596  jmp     short loc_180050589
0x180050598  mov     [rsp+0B8h+var_88], r14
0x18005059d  lea     rax, aProcedureSCoul; "Procedure \"%s\" could not be located i"...
0x1800505a4  mov     qword ptr [rsp+0B8h+ArgList], rsi; ArgList
0x1800505a9  lea     r8, aLdrpnametoordi; "LdrpNameToOrdinal"
0x1800505b0  mov     r9d, 1; int
0x1800505b6  mov     [rsp+0B8h+Format], rax; Format
0x1800505bb  mov     edx, 8EEh; int
0x1800505c0  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x1800505c7  call    LdrpLogInternal
0x1800505cc  mov     edi, 0C000007Ah
0x1800505d1  jmp     loc_18005054D
0x1800505d6  cmp     [r9+74h], eax
0x1800505da  jbe     short loc_180050647
0x1800505dc  mov     r10d, [r9+78h]
0x1800505e0  test    r10d, r10d
0x1800505e3  jz      loc_18005076E
0x1800505e9  mov     r15d, [r9+7Ch]
0x1800505ed  test    bl, bl
0x1800505ef  jnz     loc_18005074F
0x1800505f5  cmp     r10d, [r9+54h]
0x1800505f9  jb      loc_18005074F
0x1800505ff  movzx   edx, word ptr [r9+14h]
0x180050604  movzx   r11d, word ptr [r9+6]
0x180050609  add     rdx, 18h
0x18005060d  add     rdx, r9
0x180050610  xor     r9d, r9d
0x180050613  cmp     r9d, r11d
0x180050616  jnb     short loc_180050647
0x180050618  mov     r8d, [rdx+0Ch]
0x18005061c  cmp     r10d, r8d
0x18005061f  jb      short loc_18005062C
0x180050621  mov     ecx, [rdx+10h]
0x180050624  add     ecx, r8d
0x180050627  cmp     r10d, ecx
0x18005062a  jb      short loc_180050635
0x18005062c  add     rdx, 28h ; '('
0x180050630  inc     r9d
0x180050633  jmp     short loc_180050613
0x180050635  mov     eax, [rdx+14h]
0x180050638  sub     rax, r8
0x18005063b  add     rax, rdi
0x18005063e  add     rax, r10
0x180050641  jnz     loc_180050418
0x180050647  mov     ecx, 0C000000Dh
0x18005064c  jmp     loc_18005041A
0x180050651  mov     rdi, r14
0x180050654  and     rdi, 0FFFFFFFFFFFFFFFCh
0x180050658  xor     bl, 1
0x18005065b  jmp     loc_1800503A3
0x180050660  lea     rcx, [rsi+1]; String
0x180050664  xor     edx, edx; Base
0x180050666  lea     r8, [rsp+0B8h+Value]; Value
0x18005066e  call    RtlCharToInteger
0x180050673  test    eax, eax
0x180050675  jns     short loc_180050698
0x180050677  mov     edi, 0C000007Bh
0x18005067c  jmp     loc_18005054D
0x180050681  mov     eax, dword ptr cs:qword_1801E0460
0x180050687  add     rax, rcx
0x18005068a  cmp     rbx, rax
0x18005068d  jb      loc_180050542
0x180050693  jmp     loc_180050530
0x180050698  mov     rsi, r15
0x18005069b  jmp     loc_1800502F7
0x1800506a0  mov     ebx, [rsp+0B8h+Value]
0x1800506a7  lea     rax, aLoadingProcedu; "Loading procedure 0x%lx by ordinal\n"
0x1800506ae  mov     dword ptr [rsp+0B8h+ArgList], ebx; ArgList
0x1800506b2  mov     edx, 358h; int
0x1800506b7  mov     [rsp+0B8h+Format], rax; Format
0x1800506bc  call    LdrpLogInternal
0x1800506c1  test    ebx, ebx
0x1800506c3  jz      short loc_180050714
0x1800506c5  sub     ebx, [rbp+10h]
0x1800506c8  jmp     loc_1800504C6
0x1800506cd  mov     ecx, 0C0000002h
0x1800506d2  jmp     loc_18005041A
0x1800506d7  xor     edi, edi
0x1800506d9  jmp     loc_18005054D
0x1800506de  mov     eax, r15d
0x1800506e1  add     rax, rbp
0x1800506e4  cmp     rdi, rax
0x1800506e7  jnb     loc_1800504F2
0x1800506ed  mov     ebx, [rsp+0B8h+var_78]
0x1800506f1  inc     ebx
0x1800506f3  mov     [rsp+0B8h+var_78], ebx
0x1800506f7  cmp     ebx, 20h ; ' '
0x1800506fa  jz      loc_180050677
0x180050700  mov     rbp, [rsp+0B8h+var_58]
0x180050705  xor     r15d, r15d
0x180050708  jmp     loc_1800502B0
0x18005070d  mov     ecx, 18h
0x180050712  int     29h; Win8: RtlFailFast(ecx)
0x180050714  mov     edi, 0C000000Dh
0x180050719  jmp     loc_18005054D
0x18005071e  xor     edi, edi
  ... truncated ...
```
