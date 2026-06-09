# LdrpResolveForwarder

- ea: `0x18006cc40`
- end: `0x18006d185`
- name: `LdrpResolveForwarder`
- size: `1349`
- prototype: `__int64 __fastcall(char *Str)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callers

- `0x1800b6f08`

## callees

- `0x18001861c`
- `0x18001eb80`
- `0x18001f070`
- `0x180029010`
- `0x18006cc40`
- `0x18006e2e0`
- `0x180084a90`
- `0x1800c8f70`
- `0x18011a940`
- `0x18012c4e0`

## string_xrefs

- `0x18006ce0b`: `LdrpGetProcedureAddress`
- `0x18006cf7d`: `Procedure "%s" could not be located in DLL at base 0x%p.\n`

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
0x18006cc40  mov     rax, rsp
0x18006cc43  mov     [rax+8], rbx
0x18006cc47  mov     [rax+20h], r9
0x18006cc4b  push    rbp
0x18006cc4c  push    rsi
0x18006cc4d  push    rdi
0x18006cc4e  push    r12
0x18006cc50  push    r13
0x18006cc52  push    r14
0x18006cc54  push    r15
0x18006cc56  sub     rsp, 80h
0x18006cc5d  mov     rbp, [r8+0B0h]
0x18006cc64  xor     r15d, r15d
0x18006cc67  xorps   xmm0, xmm0
0x18006cc6a  mov     [rax+18h], r15d
0x18006cc6e  movups  xmmword ptr [rax-50h], xmm0
0x18006cc72  mov     [rsp+0B8h+var_78], r15d
0x18006cc77  mov     r14, r9
0x18006cc7a  mov     [rax-70h], r15
0x18006cc7e  mov     r12, r8
0x18006cc81  mov     [rsp+0B8h+var_58], rbp
0x18006cc86  mov     r13, rdx
0x18006cc89  mov     [rax-60h], r15
0x18006cc8d  mov     rdi, rcx
0x18006cc90  mov     edx, 2Eh ; '.'; Ch
0x18006cc95  mov     rcx, rdi; Str
0x18006cc98  call    strrchr
0x18006cc9d  mov     rsi, rax
0x18006cca0  test    rax, rax
0x18006cca3  jz      loc_18006D057
0x18006cca9  mov     rbx, rax
0x18006ccac  sub     rbx, rdi
0x18006ccaf  cmp     rbx, 0FFFFh
0x18006ccb6  ja      loc_18006D057
0x18006ccbc  inc     rsi
0x18006ccbf  mov     qword ptr [rsp+0B8h+var_50+8], rdi
0x18006ccc4  mov     word ptr [rsp+0B8h+var_50], bx
0x18006ccc9  mov     word ptr [rsp+0B8h+var_50+2], bx
0x18006ccce  cmp     byte ptr [rsi], 23h ; '#'
0x18006ccd1  jz      loc_18006D040
0x18006ccd7  cmp     bx, 5
0x18006ccdb  jnz     short loc_18006CCF5
0x18006ccdd  mov     eax, [rdi]
0x18006ccdf  or      eax, 20202020h
0x18006cce4  cmp     eax, 6C64746Eh
0x18006cce9  jnz     short loc_18006CCF5
0x18006cceb  movzx   eax, byte ptr [rdi+4]
0x18006ccef  or      al, 20h
0x18006ccf1  cmp     al, 6Ch ; 'l'
0x18006ccf3  jz      short loc_18006CD3B
0x18006ccf5  lea     rax, [rsp+0B8h+var_60]
0x18006ccfa  mov     r9d, 1
0x18006cd00  mov     qword ptr [rsp+0B8h+ArgList], rax
0x18006cd05  lea     rcx, [rsp+0B8h+var_50]
0x18006cd0a  lea     rax, [rsp+0B8h+var_70]
0x18006cd0f  mov     r8, r13
0x18006cd12  mov     rdx, rbp
0x18006cd15  mov     [rsp+0B8h+Format], rax
0x18006cd1a  call    LdrpLoadDependentModuleA
0x18006cd1f  mov     edi, eax
0x18006cd21  test    eax, eax
0x18006cd23  js      loc_18006CF2D
0x18006cd29  cmp     eax, 103h
0x18006cd2e  jz      loc_18006CF2D
0x18006cd34  mov     r13, [rsp+0B8h+var_70]
0x18006cd39  jmp     short loc_18006CD47
0x18006cd3b  mov     r13, cs:LdrpNtDllDataTableEntry
0x18006cd42  mov     [rsp+0B8h+var_70], r13
0x18006cd47  mov     rax, [r12+0B0h]
0x18006cd4f  test    dword ptr [rax+20h], 2000000h
0x18006cd56  jnz     loc_18006D158
0x18006cd5c  mov     r14, [r13+30h]
0x18006cd60  mov     rbx, r14
0x18006cd63  mov     [rsp+0B8h+var_68], r15
0x18006cd68  and     ebx, 1
0x18006cd6b  test    r14b, 2
0x18006cd6f  jnz     loc_18006D031
0x18006cd75  test    rbx, rbx
0x18006cd78  jnz     loc_18006D031
0x18006cd7e  mov     bl, 1
0x18006cd80  mov     rdi, r14
0x18006cd83  lea     r9, [rsp+0B8h+var_68]
0x18006cd88  xor     r8d, r8d
0x18006cd8b  mov     rdx, rdi
0x18006cd8e  mov     ecx, 1
0x18006cd93  call    RtlImageNtHeaderEx
0x18006cd98  mov     r9, [rsp+0B8h+var_68]
0x18006cd9d  test    r9, r9
0x18006cda0  jz      loc_18006CFAC
0x18006cda6  movzx   ecx, word ptr [r9+18h]
0x18006cdab  xor     eax, eax
0x18006cdad  mov     edx, 10Bh
0x18006cdb2  cmp     cx, dx
0x18006cdb5  jz      loc_18006CFB6
0x18006cdbb  mov     edx, 20Bh
0x18006cdc0  cmp     cx, dx
0x18006cdc3  jnz     loc_18006D027
0x18006cdc9  cmp     [r9+84h], eax
0x18006cdd0  jbe     loc_18006D027
0x18006cdd6  mov     ecx, [r9+88h]
0x18006cddd  test    ecx, ecx
0x18006cddf  jz      loc_18006D0AD
0x18006cde5  mov     r15d, [r9+8Ch]
0x18006cdec  test    bl, bl
0x18006cdee  jz      loc_18006D105
0x18006cdf4  lea     rax, [rdi+rcx]
0x18006cdf8  xor     ecx, ecx
0x18006cdfa  xor     ebp, ebp
0x18006cdfc  test    ecx, ecx
0x18006cdfe  cmovns  rbp, rax
0x18006ce02  test    rbp, rbp
0x18006ce05  jz      loc_18006CFAC
0x18006ce0b  lea     r8, aLdrpgetprocedu; "LdrpGetProcedureAddress"
0x18006ce12  mov     r9d, 2; int
0x18006ce18  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x18006ce1f  test    rsi, rsi
0x18006ce22  jz      loc_18006D080
0x18006ce28  lea     rax, aLocatingProced_0; "Locating procedure \"%s\" by name\n"
0x18006ce2f  mov     qword ptr [rsp+0B8h+ArgList], rsi; ArgList
0x18006ce34  mov     edx, 346h; int
0x18006ce39  mov     [rsp+0B8h+Format], rax; Format
0x18006ce3e  call    LdrpLogInternal
0x18006ce43  mov     edi, [rbp+20h]
0x18006ce46  xor     ebx, ebx
0x18006ce48  mov     r10d, [rbp+18h]
0x18006ce4c  add     rdi, r14
0x18006ce4f  dec     r10d
0x18006ce52  mov     eax, r10d
0x18006ce55  cdq
0x18006ce56  sub     eax, edx
0x18006ce58  sar     eax, 1
0x18006ce5a  mov     r11d, eax
0x18006ce5d  cmp     r10d, ebx
0x18006ce60  jl      loc_18006CF78
0x18006ce66  movsxd  r9, eax
0x18006ce69  mov     rcx, rsi
0x18006ce6c  mov     r8d, [rdi+r9*4]
0x18006ce70  add     r8, r14
0x18006ce73  sub     r8, rsi
0x18006ce76  nop     word ptr [rax+rax+00000000h]
0x18006ce80  movzx   edx, byte ptr [rcx]
0x18006ce83  movzx   eax, byte ptr [rcx+r8]
0x18006ce88  sub     edx, eax
0x18006ce8a  jnz     short loc_18006CE93
0x18006ce8c  inc     rcx
0x18006ce8f  test    eax, eax
0x18006ce91  jnz     short loc_18006CE80
0x18006ce93  test    edx, edx
0x18006ce95  jnz     loc_18006CF63
0x18006ce9b  mov     ecx, [rbp+24h]
0x18006ce9e  add     rcx, r14
0x18006cea1  movzx   ebx, word ptr [rcx+r9*2]
0x18006cea6  cmp     ebx, [rbp+14h]
0x18006cea9  jnb     loc_18006D13A
0x18006ceaf  mov     ecx, [rbp+1Ch]
0x18006ceb2  add     rcx, r14
0x18006ceb5  movsxd  rdx, ebx
0x18006ceb8  mov     edi, [rcx+rdx*4]
0x18006cebb  add     rdi, r14
0x18006cebe  mov     r14, [rsp+0B8h+arg_18]
0x18006cec6  mov     [r14], rdi
0x18006cec9  cmp     rdi, rbp
0x18006cecc  jnb     loc_18006D0BE
0x18006ced2  cmp     cs:qword_1801E3518, 0
0x18006ceda  jz      loc_18006D0B7
0x18006cee0  test    byte ptr cs:dword_1801E34FC, 1
0x18006cee7  jnz     loc_18006D0FE
0x18006ceed  mov     rbx, [r13+30h]
0x18006cef1  xor     eax, eax
0x18006cef3  mov     rcx, qword ptr cs:xmmword_1801E0450+8
0x18006cefa  xorps   xmm0, xmm0
0x18006cefd  mov     [rsp+0B8h+var_40], rax
0x18006cf02  movups  [rsp+0B8h+var_50], xmm0
0x18006cf07  cmp     rbx, rcx
0x18006cf0a  jnb     loc_18006D061
0x18006cf10  lea     rdx, [rsp+0B8h+var_50]
0x18006cf15  mov     rcx, rbx
0x18006cf18  call    RtlpxLookupFunctionTable
0x18006cf1d  mov     rcx, qword ptr [rsp+0B8h+var_50+8]
0x18006cf22  xor     edi, edi
0x18006cf24  cmp     rcx, rbx
0x18006cf27  jnz     loc_18006D0ED
0x18006cf2d  mov     r8, [rsp+0B8h+var_60]
0x18006cf32  test    r8, r8
0x18006cf35  jz      short loc_18006CF45
0x18006cf37  mov     rcx, cs:LdrpHeap
0x18006cf3e  xor     edx, edx
0x18006cf40  call    RtlFreeHeap_0
0x18006cf45  mov     eax, edi
0x18006cf47  mov     rbx, [rsp+0B8h+arg_0]
0x18006cf4f  add     rsp, 80h
0x18006cf56  pop     r15
0x18006cf58  pop     r14
0x18006cf5a  pop     r13
0x18006cf5c  pop     r12
0x18006cf5e  pop     rdi
0x18006cf5f  pop     rsi
0x18006cf60  pop     rbp
0x18006cf61  retn
0x18006cf63  jns     short loc_18006CF72
0x18006cf65  lea     r10d, [r11-1]
0x18006cf69  lea     eax, [rbx+r10]
0x18006cf6d  jmp     loc_18006CE55
0x18006cf72  lea     ebx, [r11+1]
0x18006cf76  jmp     short loc_18006CF69
0x18006cf78  mov     [rsp+0B8h+var_88], r14
0x18006cf7d  lea     rax, aProcedureSCoul; "Procedure \"%s\" could not be located i"...
0x18006cf84  mov     qword ptr [rsp+0B8h+ArgList], rsi; ArgList
0x18006cf89  lea     r8, aLdrpnametoordi; "LdrpNameToOrdinal"
0x18006cf90  mov     r9d, 1; int
0x18006cf96  mov     [rsp+0B8h+Format], rax; Format
0x18006cf9b  mov     edx, 8EEh; int
0x18006cfa0  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x18006cfa7  call    LdrpLogInternal
0x18006cfac  mov     edi, 0C000007Ah
0x18006cfb1  jmp     loc_18006CF2D
0x18006cfb6  cmp     [r9+74h], eax
0x18006cfba  jbe     short loc_18006D027
0x18006cfbc  mov     r10d, [r9+78h]
0x18006cfc0  test    r10d, r10d
0x18006cfc3  jz      loc_18006D14E
0x18006cfc9  mov     r15d, [r9+7Ch]
0x18006cfcd  test    bl, bl
0x18006cfcf  jnz     loc_18006D12F
0x18006cfd5  cmp     r10d, [r9+54h]
0x18006cfd9  jb      loc_18006D12F
0x18006cfdf  movzx   edx, word ptr [r9+14h]
0x18006cfe4  movzx   r11d, word ptr [r9+6]
0x18006cfe9  add     rdx, 18h
0x18006cfed  add     rdx, r9
0x18006cff0  xor     r9d, r9d
0x18006cff3  cmp     r9d, r11d
0x18006cff6  jnb     short loc_18006D027
0x18006cff8  mov     r8d, [rdx+0Ch]
0x18006cffc  cmp     r10d, r8d
0x18006cfff  jb      short loc_18006D00C
0x18006d001  mov     ecx, [rdx+10h]
0x18006d004  add     ecx, r8d
0x18006d007  cmp     r10d, ecx
0x18006d00a  jb      short loc_18006D015
0x18006d00c  add     rdx, 28h ; '('
0x18006d010  inc     r9d
0x18006d013  jmp     short loc_18006CFF3
0x18006d015  mov     eax, [rdx+14h]
0x18006d018  sub     rax, r8
0x18006d01b  add     rax, rdi
0x18006d01e  add     rax, r10
0x18006d021  jnz     loc_18006CDF8
0x18006d027  mov     ecx, 0C000000Dh
0x18006d02c  jmp     loc_18006CDFA
0x18006d031  mov     rdi, r14
0x18006d034  and     rdi, 0FFFFFFFFFFFFFFFCh
0x18006d038  xor     bl, 1
0x18006d03b  jmp     loc_18006CD83
0x18006d040  lea     rcx, [rsi+1]; String
0x18006d044  xor     edx, edx; Base
0x18006d046  lea     r8, [rsp+0B8h+Value]; Value
0x18006d04e  call    RtlCharToInteger
0x18006d053  test    eax, eax
0x18006d055  jns     short loc_18006D078
0x18006d057  mov     edi, 0C000007Bh
0x18006d05c  jmp     loc_18006CF2D
0x18006d061  mov     eax, dword ptr cs:qword_1801E0460
0x18006d067  add     rax, rcx
0x18006d06a  cmp     rbx, rax
0x18006d06d  jb      loc_18006CF22
0x18006d073  jmp     loc_18006CF10
0x18006d078  mov     rsi, r15
0x18006d07b  jmp     loc_18006CCD7
0x18006d080  mov     ebx, [rsp+0B8h+Value]
0x18006d087  lea     rax, aLoadingProcedu; "Loading procedure 0x%lx by ordinal\n"
0x18006d08e  mov     dword ptr [rsp+0B8h+ArgList], ebx; ArgList
0x18006d092  mov     edx, 358h; int
0x18006d097  mov     [rsp+0B8h+Format], rax; Format
0x18006d09c  call    LdrpLogInternal
0x18006d0a1  test    ebx, ebx
0x18006d0a3  jz      short loc_18006D0F4
0x18006d0a5  sub     ebx, [rbp+10h]
0x18006d0a8  jmp     loc_18006CEA6
0x18006d0ad  mov     ecx, 0C0000002h
0x18006d0b2  jmp     loc_18006CDFA
0x18006d0b7  xor     edi, edi
0x18006d0b9  jmp     loc_18006CF2D
0x18006d0be  mov     eax, r15d
0x18006d0c1  add     rax, rbp
0x18006d0c4  cmp     rdi, rax
0x18006d0c7  jnb     loc_18006CED2
0x18006d0cd  mov     ebx, [rsp+0B8h+var_78]
0x18006d0d1  inc     ebx
0x18006d0d3  mov     [rsp+0B8h+var_78], ebx
0x18006d0d7  cmp     ebx, 20h ; ' '
0x18006d0da  jz      loc_18006D057
0x18006d0e0  mov     rbp, [rsp+0B8h+var_58]
0x18006d0e5  xor     r15d, r15d
0x18006d0e8  jmp     loc_18006CC90
0x18006d0ed  mov     ecx, 18h
0x18006d0f2  int     29h; Win8: RtlFailFast(ecx)
0x18006d0f4  mov     edi, 0C000000Dh
0x18006d0f9  jmp     loc_18006CF2D
0x18006d0fe  xor     edi, edi
  ... truncated ...
```
