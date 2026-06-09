# LdrpGetProcedureAddress

- ea: `0x18001e820`
- end: `0x18001eb71`
- name: `LdrpGetProcedureAddress`
- size: `849`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180053390`
- `0x1800bb8b0`
- `0x1800fb05c`
- `0x180136ed4`
- `0x18015afd0`
- `0x18015d5a4`

## callees

- `0x18001e820`
- `0x18001eb80`
- `0x18001f070`

## string_xrefs

- `0x18001e8f8`: `LdrpGetProcedureAddress`
- `0x18001e9c1`: `Procedure "%s" could not be located in DLL at base 0x%p.\n`

## pseudocode

```c
__int64 __fastcall LdrpGetProcedureAddress(unsigned __int64 a1, const char *a2, int a3, unsigned __int64 *a4)
{
  bool v8; // bl
  unsigned __int64 v9; // rsi
  __int16 v10; // cx
  unsigned int v11; // r12d
  _DWORD *v12; // rax
  __int64 v13; // r8
  int v14; // ecx
  _DWORD *v15; // rbx
  int v16; // edi
  int v17; // r10d
  int k; // eax
  int v19; // eax
  int v20; // r11d
  __int64 v21; // r9
  int v22; // edx
  unsigned int v23; // edi
  unsigned __int64 v24; // rcx
  __int64 v26; // r10
  unsigned int *v27; // r8
  unsigned int i; // edx
  __int64 v29; // r9
  unsigned int *v30; // r10
  unsigned int j; // edx
  __int64 v32; // r9
  __int64 v33[7]; // [rsp+40h] [rbp-38h] BYREF

  v33[0] = 0;
  if ( (a1 & 2) != 0 || (a1 & 1) != 0 )
  {
    v9 = a1 & 0xFFFFFFFFFFFFFFFCuLL;
    v8 = !(a1 & 1);
  }
  else
  {
    v8 = 1;
    v9 = a1;
  }
  RtlImageNtHeaderEx(1, v9, 0, v33);
  if ( !v33[0] )
    return 3221225594LL;
  v10 = *(_WORD *)(v33[0] + 24);
  v11 = 0;
  v12 = 0;
  if ( v10 == 267 )
  {
    if ( *(_DWORD *)(v33[0] + 116) )
    {
      v26 = *(unsigned int *)(v33[0] + 120);
      if ( (_DWORD)v26 )
      {
        v11 = *(_DWORD *)(v33[0] + 124);
        if ( !v8 && (unsigned int)v26 >= *(_DWORD *)(v33[0] + 84) )
        {
          v27 = (unsigned int *)(v33[0] + *(unsigned __int16 *)(v33[0] + 20) + 24LL);
          for ( i = 0; i < *(unsigned __int16 *)(v33[0] + 6); ++i )
          {
            v29 = v27[3];
            if ( (unsigned int)v26 >= (unsigned int)v29 && (unsigned int)v26 < (unsigned int)v29 + v27[4] )
            {
              v12 = (_DWORD *)(v26 + v9 + v27[5] - v29);
              if ( v12 )
                goto LABEL_11;
              goto LABEL_39;
            }
            v27 += 10;
          }
          goto LABEL_39;
        }
        v12 = (_DWORD *)(v9 + v26);
        v14 = 0;
      }
      else
      {
        v14 = -1073741822;
      }
      goto LABEL_12;
    }
LABEL_39:
    v14 = -1073741811;
    goto LABEL_12;
  }
  if ( v10 != 523 || !*(_DWORD *)(v33[0] + 132) )
    goto LABEL_39;
  v13 = *(unsigned int *)(v33[0] + 136);
  if ( (_DWORD)v13 )
  {
    v11 = *(_DWORD *)(v33[0] + 140);
    if ( !v8 && (unsigned int)v13 >= *(_DWORD *)(v33[0] + 84) )
    {
      v30 = (unsigned int *)(v33[0] + *(unsigned __int16 *)(v33[0] + 20) + 24LL);
      for ( j = 0; j < *(unsigned __int16 *)(v33[0] + 6); ++j )
      {
        v32 = v30[3];
        if ( (unsigned int)v13 >= (unsigned int)v32 && (unsigned int)v13 < (unsigned int)v32 + v30[4] )
        {
          v12 = (_DWORD *)(v13 + v9 + v30[5] - v32);
          if ( v12 )
            goto LABEL_11;
          v14 = -1073741811;
          goto LABEL_12;
        }
        v30 += 10;
      }
      goto LABEL_39;
    }
    v12 = (_DWORD *)(v9 + v13);
LABEL_11:
    v14 = 0;
  }
  else
  {
    v14 = -1073741822;
  }
LABEL_12:
  v15 = 0;
  if ( v14 >= 0 )
    v15 = v12;
  if ( !v15 )
    return 3221225594LL;
  if ( a2 )
  {
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrsnap.c",
      838,
      (int)"LdrpGetProcedureAddress",
      2,
      "Locating procedure \"%s\" by name\n",
      (char)a2);
    v16 = 0;
    v17 = v15[6] - 1;
    for ( k = v17; ; k = v16 + v17 )
    {
      v19 = k / 2;
      v20 = v19;
      if ( v17 < v16 )
        break;
      v21 = v19;
      v22 = strcmp(a2, (const char *)(a1 + *(unsigned int *)(a1 + (unsigned int)v15[8] + 4LL * v19)));
      if ( !v22 )
      {
        v23 = *(unsigned __int16 *)(a1 + (unsigned int)v15[9] + 2 * v21);
        goto LABEL_20;
      }
      if ( v22 >= 0 )
        v16 = v20 + 1;
      else
        v17 = v20 - 1;
    }
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrsnap.c",
      2286,
      (int)"LdrpNameToOrdinal",
      1,
      "Procedure \"%s\" could not be located in DLL at base 0x%p.\n",
      (char)a2);
    return 3221225594LL;
  }
  LdrpLogInternal(
    (int)"minkernel\\ldr\\ldrsnap.c",
    856,
    (int)"LdrpGetProcedureAddress",
    2,
    "Loading procedure 0x%lx by ordinal\n",
    a3);
  if ( !a3 )
    return 3221225485LL;
  v23 = a3 - v15[4];
LABEL_20:
  if ( v23 >= v15[5] )
    return (unsigned int)(a2 != 0) - 1073741512;
  v24 = a1 + *(unsigned int *)(a1 + (unsigned int)v15[7] + 4LL * (int)v23);
  *a4 = v24;
  if ( v24 >= (unsigned __int64)v15 )
    return v24 < (unsigned __int64)v15 + v11 ? 0xC000022D : 0;
  else
    return 0;
}

```

## disassembly

```asm
0x18001e820  mov     [rsp+arg_10], rbx
0x18001e825  push    rbp
0x18001e826  push    rsi
0x18001e827  push    rdi
0x18001e828  push    r14
0x18001e82a  push    r15
0x18001e82c  sub     rsp, 50h
0x18001e830  mov     rbx, rcx
0x18001e833  mov     [rsp+78h+var_38], 0
0x18001e83c  and     ebx, 1
0x18001e83f  mov     r15, r9
0x18001e842  mov     edi, r8d
0x18001e845  mov     rbp, rdx
0x18001e848  mov     r14, rcx
0x18001e84b  test    cl, 2
0x18001e84e  jnz     loc_18001EA8C
0x18001e854  test    rbx, rbx
0x18001e857  jnz     loc_18001EA8C
0x18001e85d  mov     bl, 1
0x18001e85f  mov     rsi, rcx
0x18001e862  lea     r9, [rsp+78h+var_38]
0x18001e867  mov     [rsp+78h+arg_8], r12
0x18001e86f  xor     r8d, r8d
0x18001e872  mov     rdx, rsi
0x18001e875  mov     ecx, 1
0x18001e87a  call    RtlImageNtHeaderEx
0x18001e87f  mov     rdx, [rsp+78h+var_38]
0x18001e884  test    rdx, rdx
0x18001e887  jz      loc_18001E9F0
0x18001e88d  movzx   ecx, word ptr [rdx+18h]
0x18001e891  xor     r12d, r12d
0x18001e894  xor     eax, eax
0x18001e896  mov     r8d, 10Bh
0x18001e89c  cmp     cx, r8w
0x18001e8a0  jz      loc_18001EA12
0x18001e8a6  mov     r8d, 20Bh
0x18001e8ac  cmp     cx, r8w
0x18001e8b0  jnz     loc_18001EA82
0x18001e8b6  cmp     [rdx+84h], eax
0x18001e8bc  jbe     loc_18001EA82
0x18001e8c2  mov     r8d, [rdx+88h]
0x18001e8c9  test    r8d, r8d
0x18001e8cc  jz      loc_18001EAC1
0x18001e8d2  mov     r12d, [rdx+8Ch]
0x18001e8d9  test    bl, bl
0x18001e8db  jz      loc_18001EAEA
0x18001e8e1  lea     rax, [rsi+r8]
0x18001e8e5  xor     ecx, ecx
0x18001e8e7  xor     ebx, ebx
0x18001e8e9  test    ecx, ecx
0x18001e8eb  cmovns  rbx, rax
0x18001e8ef  test    rbx, rbx
0x18001e8f2  jz      loc_18001E9F0
0x18001e8f8  lea     r8, aLdrpgetprocedu; "LdrpGetProcedureAddress"
0x18001e8ff  mov     r9d, 2; int
0x18001e905  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x18001e90c  test    rbp, rbp
0x18001e90f  jz      loc_18001EA9B
0x18001e915  lea     rax, aLocatingProced_0; "Locating procedure \"%s\" by name\n"
0x18001e91c  mov     qword ptr [rsp+78h+ArgList], rbp; ArgList
0x18001e921  mov     edx, 346h; int
0x18001e926  mov     [rsp+78h+Format], rax; Format
0x18001e92b  call    LdrpLogInternal
0x18001e930  mov     esi, [rbx+20h]
0x18001e933  xor     edi, edi
0x18001e935  mov     r10d, [rbx+18h]
0x18001e939  add     rsi, r14
0x18001e93c  dec     r10d
0x18001e93f  mov     eax, r10d
0x18001e942  cdq
0x18001e943  sub     eax, edx
0x18001e945  sar     eax, 1
0x18001e947  mov     r11d, eax
0x18001e94a  cmp     r10d, edi
0x18001e94d  jl      short loc_18001E9BC
0x18001e94f  movsxd  r9, eax
0x18001e952  mov     rax, rbp
0x18001e955  mov     r8d, [rsi+r9*4]
0x18001e959  add     r8, r14
0x18001e95c  sub     r8, rbp
0x18001e95f  nop
0x18001e960  movzx   edx, byte ptr [rax]
0x18001e963  movzx   ecx, byte ptr [rax+r8]
0x18001e968  sub     edx, ecx
0x18001e96a  jnz     short loc_18001E973
0x18001e96c  inc     rax
0x18001e96f  test    ecx, ecx
0x18001e971  jnz     short loc_18001E960
0x18001e973  test    edx, edx
0x18001e975  jnz     short loc_18001E9AA
0x18001e977  mov     ecx, [rbx+24h]
0x18001e97a  add     rcx, r14
0x18001e97d  movzx   edi, word ptr [rcx+r9*2]
0x18001e982  cmp     edi, [rbx+14h]
0x18001e985  jnb     loc_18001EB55
0x18001e98b  mov     ecx, [rbx+1Ch]
0x18001e98e  add     rcx, r14
0x18001e991  movsxd  rdx, edi
0x18001e994  mov     ecx, [rcx+rdx*4]
0x18001e997  add     rcx, r14
0x18001e99a  mov     [r15], rcx
0x18001e99d  cmp     rcx, rbx
0x18001e9a0  jnb     loc_18001EACB
0x18001e9a6  xor     eax, eax
0x18001e9a8  jmp     short loc_18001E9F5
0x18001e9aa  jns     short loc_18001E9B6
0x18001e9ac  lea     r10d, [r11-1]
0x18001e9b0  lea     eax, [rdi+r10]
0x18001e9b4  jmp     short loc_18001E942
0x18001e9b6  lea     edi, [r11+1]
0x18001e9ba  jmp     short loc_18001E9B0
0x18001e9bc  mov     [rsp+78h+var_48], r14
0x18001e9c1  lea     rax, aProcedureSCoul; "Procedure \"%s\" could not be located i"...
0x18001e9c8  mov     qword ptr [rsp+78h+ArgList], rbp; ArgList
0x18001e9cd  lea     r8, aLdrpnametoordi; "LdrpNameToOrdinal"
0x18001e9d4  mov     r9d, 1; int
0x18001e9da  mov     [rsp+78h+Format], rax; Format
0x18001e9df  mov     edx, 8EEh; int
0x18001e9e4  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x18001e9eb  call    LdrpLogInternal
0x18001e9f0  mov     eax, 0C000007Ah
0x18001e9f5  mov     r12, [rsp+78h+arg_8]
0x18001e9fd  mov     rbx, [rsp+78h+arg_10]
0x18001ea05  add     rsp, 50h
0x18001ea09  pop     r15
0x18001ea0b  pop     r14
0x18001ea0d  pop     rdi
0x18001ea0e  pop     rsi
0x18001ea0f  pop     rbp
0x18001ea10  retn
0x18001ea12  cmp     [rdx+74h], eax
0x18001ea15  jbe     short loc_18001EA82
0x18001ea17  mov     r10d, [rdx+78h]
0x18001ea1b  test    r10d, r10d
0x18001ea1e  jz      loc_18001EB67
0x18001ea24  mov     r12d, [rdx+7Ch]
0x18001ea28  test    bl, bl
0x18001ea2a  jnz     loc_18001EB4A
0x18001ea30  cmp     r10d, [rdx+54h]
0x18001ea34  jb      loc_18001EB4A
0x18001ea3a  movzx   r8d, word ptr [rdx+14h]
0x18001ea3f  movzx   r11d, word ptr [rdx+6]
0x18001ea44  add     r8, 18h
0x18001ea48  add     r8, rdx
0x18001ea4b  xor     edx, edx
0x18001ea4d  cmp     edx, r11d
0x18001ea50  jnb     short loc_18001EA82
0x18001ea52  mov     r9d, [r8+0Ch]
0x18001ea56  cmp     r10d, r9d
0x18001ea59  jb      short loc_18001EA67
0x18001ea5b  mov     ecx, [r8+10h]
0x18001ea5f  add     ecx, r9d
0x18001ea62  cmp     r10d, ecx
0x18001ea65  jb      short loc_18001EA6F
0x18001ea67  add     r8, 28h ; '('
0x18001ea6b  inc     edx
0x18001ea6d  jmp     short loc_18001EA4D
0x18001ea6f  mov     eax, [r8+14h]
0x18001ea73  sub     rax, r9
0x18001ea76  add     rax, rsi
0x18001ea79  add     rax, r10
0x18001ea7c  jnz     loc_18001E8E5
0x18001ea82  mov     ecx, 0C000000Dh
0x18001ea87  jmp     loc_18001E8E7
0x18001ea8c  mov     rsi, r14
0x18001ea8f  and     rsi, 0FFFFFFFFFFFFFFFCh
0x18001ea93  xor     bl, 1
0x18001ea96  jmp     loc_18001E862
0x18001ea9b  lea     rax, aLoadingProcedu; "Loading procedure 0x%lx by ordinal\n"
0x18001eaa2  mov     dword ptr [rsp+78h+ArgList], edi; ArgList
0x18001eaa6  mov     edx, 358h; int
0x18001eaab  mov     [rsp+78h+Format], rax; Format
0x18001eab0  call    LdrpLogInternal
0x18001eab5  test    edi, edi
0x18001eab7  jz      short loc_18001EAE0
0x18001eab9  sub     edi, [rbx+10h]
0x18001eabc  jmp     loc_18001E982
0x18001eac1  mov     ecx, 0C0000002h
0x18001eac6  jmp     loc_18001E8E7
0x18001eacb  mov     eax, r12d
0x18001eace  add     rax, rbx
0x18001ead1  cmp     rcx, rax
0x18001ead4  sbb     eax, eax
0x18001ead6  and     eax, 0C000022Dh
0x18001eadb  jmp     loc_18001E9F5
0x18001eae0  mov     eax, 0C000000Dh
0x18001eae5  jmp     loc_18001E9F5
0x18001eaea  cmp     r8d, [rdx+54h]
0x18001eaee  jb      loc_18001E8E1
0x18001eaf4  movzx   r10d, word ptr [rdx+14h]
0x18001eaf9  movzx   r11d, word ptr [rdx+6]
0x18001eafe  add     r10, 18h
0x18001eb02  add     r10, rdx
0x18001eb05  xor     edx, edx
0x18001eb07  cmp     edx, r11d
0x18001eb0a  jnb     loc_18001EA82
0x18001eb10  mov     r9d, [r10+0Ch]
0x18001eb14  cmp     r8d, r9d
0x18001eb17  jb      short loc_18001EB25
0x18001eb19  mov     ecx, [r10+10h]
0x18001eb1d  add     ecx, r9d
0x18001eb20  cmp     r8d, ecx
0x18001eb23  jb      short loc_18001EB2D
0x18001eb25  add     r10, 28h ; '('
0x18001eb29  inc     edx
0x18001eb2b  jmp     short loc_18001EB07
0x18001eb2d  mov     eax, [r10+14h]
0x18001eb31  sub     rax, r9
0x18001eb34  add     rax, rsi
0x18001eb37  add     rax, r8
0x18001eb3a  jnz     loc_18001E8E5
0x18001eb40  mov     ecx, 0C000000Dh
0x18001eb45  jmp     loc_18001E8E7
0x18001eb4a  lea     rax, [rsi+r10]
0x18001eb4e  xor     ecx, ecx
0x18001eb50  jmp     loc_18001E8E7
0x18001eb55  xor     eax, eax
0x18001eb57  test    rbp, rbp
0x18001eb5a  setnz   al
0x18001eb5d  add     eax, 0C0000138h
0x18001eb62  jmp     loc_18001E9F5
0x18001eb67  mov     ecx, 0C0000002h
0x18001eb6c  jmp     loc_18001E8E7
```
