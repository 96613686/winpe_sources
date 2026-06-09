# NtfsQueryLxMetadataEa

- ea: `0x140181588`
- end: `0x140181b4d`
- name: `NtfsQueryLxMetadataEa`
- size: `1477`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140180dc0`

## callees

- `0x140007ea0`
- `0x1400596c0`
- `0x1401250b0`
- `0x140179a00`
- `0x140181588`
- `0x140182140`
- `0x1401e0660`

## import_xrefs

- `ntoskrnl!RtlCompareString` at `0x14018171d`
- `ntoskrnl!RtlCompareString` at `0x1401817b7`
- `ntoskrnl!RtlCompareString` at `0x14018184f`
- `ntoskrnl!RtlCompareString` at `0x1401818dc`
- `ntoskrnl!RtlCompareString` at `0x14018171d`
- `ntoskrnl!RtlCompareString` at `0x1401817b7`
- `ntoskrnl!RtlCompareString` at `0x14018184f`
- `ntoskrnl!RtlCompareString` at `0x1401818dc`
- `ntoskrnl!RtlInitString` at `0x1401816c1`
- `ntoskrnl!RtlInitString` at `0x140181701`
- `ntoskrnl!RtlInitString` at `0x140181761`
- `ntoskrnl!RtlInitString` at `0x14018179e`
- `ntoskrnl!RtlInitString` at `0x1401817f9`
- `ntoskrnl!RtlInitString` at `0x140181836`
- `ntoskrnl!RtlInitString` at `0x140181891`
- `ntoskrnl!RtlInitString` at `0x1401818c3`
- `ntoskrnl!RtlInitString` at `0x1401816c1`
- `ntoskrnl!RtlInitString` at `0x140181701`
- `ntoskrnl!RtlInitString` at `0x140181761`
- `ntoskrnl!RtlInitString` at `0x14018179e`
- `ntoskrnl!RtlInitString` at `0x1401817f9`
- `ntoskrnl!RtlInitString` at `0x140181836`
- `ntoskrnl!RtlInitString` at `0x140181891`
- `ntoskrnl!RtlInitString` at `0x1401818c3`
- `ntoskrnl!CcUnpinData` at `0x140181a35`
- `ntoskrnl!CcUnpinData` at `0x140181a5a`
- `ntoskrnl!CcUnpinData` at `0x140181a7f`
- `ntoskrnl!CcUnpinData` at `0x140181aa1`
- `ntoskrnl!CcUnpinData` at `0x1402aa69a`
- `ntoskrnl!CcUnpinData` at `0x140181a35`
- `ntoskrnl!CcUnpinData` at `0x140181a5a`
- `ntoskrnl!CcUnpinData` at `0x140181a7f`
- `ntoskrnl!CcUnpinData` at `0x140181aa1`
- `ntoskrnl!CcUnpinData` at `0x1402aa69a`

## pseudocode

```c
__int64 __fastcall NtfsQueryLxMetadataEa(__int64 a1, __int64 a2, __int64 a3, int a4, _DWORD *a5)
{
  __int64 v9; // rdi
  bool v10; // bl
  __int64 v11; // r13
  __int64 v12; // rsi
  unsigned int *v13; // rdi
  unsigned int v14; // r15d
  __int64 v15; // rax
  int v16; // r14d
  __int64 v17; // rbx
  unsigned int v18; // eax
  _DWORD *v19; // rbx
  __int64 v20; // rax
  __int64 v21; // r14
  unsigned int v22; // eax
  __int64 v23; // rax
  __int64 v24; // r14
  unsigned int v25; // eax
  unsigned int v26; // r15d
  __int64 v27; // rax
  int v28; // r14d
  __int64 v29; // rdi
  unsigned int v30; // eax
  unsigned int Ea; // ebx
  int v32; // ecx
  unsigned int v34; // r8d
  PVOID v35; // [rsp+58h] [rbp-D0h] BYREF
  struct _STRING DestinationString; // [rsp+60h] [rbp-C8h] BYREF
  STRING v37; // [rsp+70h] [rbp-B8h] BYREF
  STRING String2; // [rsp+80h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+90h] [rbp-98h]
  _QWORD v40[12]; // [rsp+A0h] [rbp-88h] BYREF
  unsigned int v41; // [rsp+140h] [rbp+18h] BYREF

  v35 = 0;
  memset(v40, 0, 0x58u);
  v9 = 0;
  DestinationString = 0;
  if ( a3 && (Ea = NtfsPrepareQueryEa(a3, a4), (Ea & 0x80000000) != 0) )
  {
    if ( NtfsStatusDebugFlags
      && Ea < 0xFFFFFFED
      && Ea != -1073741802
      && Ea != -1073741807
      && Ea + 2147483643 > 1
      && Ea != -1073741608 )
    {
      v34 = 918571;
LABEL_61:
      NtfsStatusTraceAndDebugInternal(0, Ea, v34);
    }
  }
  else
  {
    memset(v40, 0, 0x58u);
    v41 = 0;
    v10 = 0;
    if ( NtfsLookupInFileRecord(a1, a2, (_DWORD *)(a2 + 8), 208, 0, 0, 0, 0, 0, (__int64)v40) )
    {
      v9 = v40[0] + *(unsigned __int16 *)(v40[0] + 20LL);
      v39 = v9;
      v10 = *(_DWORD *)(v9 + 4) != 0;
    }
    if ( v10 )
    {
      v11 = NtfsMapExistingEas(a1, a2, &v35, &v41);
      RtlInitString(&DestinationString, "$LXUID");
      String2 = 0;
      v12 = v11 + 8;
      v13 = (unsigned int *)(v9 + 4);
      if ( !v11 )
        goto LABEL_11;
      v14 = *v13;
      v15 = 0;
      while ( 1 )
      {
        v16 = v15;
        v17 = v15 + v11;
        RtlInitString(&String2, (PCSZ)(v15 + v12));
        if ( !RtlCompareString(&DestinationString, &String2, 1u) )
          break;
        v18 = *(_DWORD *)v17;
        if ( !*(_DWORD *)v17 )
          v18 = (*(unsigned __int16 *)(v17 + 6) + *(unsigned __int8 *)(v17 + 5) + 12) & 0xFFFFFFFC;
        v15 = v16 + v18;
        if ( (unsigned int)v15 >= v14 )
          goto LABEL_11;
      }
      if ( *(_WORD *)(v17 + 6) == 4 )
      {
        v32 = *(_DWORD *)(*(unsigned __int8 *)(v17 + 5) + v17 + 9);
        v19 = a5;
        a5[19] = v32;
        v19[18] |= 1u;
      }
      else
      {
LABEL_11:
        v19 = a5;
      }
      RtlInitString(&DestinationString, "$LXGID");
      v37 = 0;
      if ( v11 )
      {
        v41 = *v13;
        v20 = 0;
        while ( 1 )
        {
          *(_QWORD *)&String2.Length = v20;
          v21 = v20 + v11;
          RtlInitString(&v37, (PCSZ)(v20 + v12));
          if ( !RtlCompareString(&DestinationString, &v37, 1u) )
            break;
          v22 = *(_DWORD *)v21;
          if ( !*(_DWORD *)v21 )
            v22 = (*(unsigned __int16 *)(v21 + 6) + *(unsigned __int8 *)(v21 + 5) + 12) & 0xFFFFFFFC;
          v20 = *(_DWORD *)&String2.Length + v22;
          if ( (unsigned int)v20 >= v41 )
            goto LABEL_18;
        }
        if ( *(_WORD *)(v21 + 6) == 4 )
        {
          v19[20] = *(_DWORD *)(*(unsigned __int8 *)(v21 + 5) + v21 + 9);
          v19[18] |= 2u;
        }
      }
LABEL_18:
      RtlInitString(&DestinationString, "$LXMOD");
      v37 = 0;
      if ( v11 )
      {
        v41 = *v13;
        v23 = 0;
        while ( 1 )
        {
          *(_QWORD *)&String2.Length = v23;
          v24 = v23 + v11;
          RtlInitString(&v37, (PCSZ)(v23 + v12));
          if ( !RtlCompareString(&DestinationString, &v37, 1u) )
            break;
          v25 = *(_DWORD *)v24;
          if ( !*(_DWORD *)v24 )
            v25 = (*(unsigned __int16 *)(v24 + 6) + *(unsigned __int8 *)(v24 + 5) + 12) & 0xFFFFFFFC;
          v23 = *(_DWORD *)&String2.Length + v25;
          if ( (unsigned int)v23 >= v41 )
            goto LABEL_24;
        }
        if ( *(_WORD *)(v24 + 6) == 4 )
        {
          v19[21] = *(_DWORD *)(*(unsigned __int8 *)(v24 + 5) + v24 + 9);
          v19[18] |= 4u;
        }
      }
LABEL_24:
      RtlInitString(&DestinationString, "$LXDEV");
      v37 = 0;
      if ( v11 )
      {
        v26 = *v13;
        v27 = 0;
        while ( 1 )
        {
          v28 = v27;
          v29 = v27 + v11;
          RtlInitString(&v37, (PCSZ)(v27 + v12));
          if ( !RtlCompareString(&DestinationString, &v37, 1u) )
            break;
          v30 = *(_DWORD *)v29;
          if ( !*(_DWORD *)v29 )
            v30 = (*(unsigned __int16 *)(v29 + 6) + *(unsigned __int8 *)(v29 + 5) + 12) & 0xFFFFFFFC;
          v27 = v28 + v30;
          if ( (unsigned int)v27 >= v26 )
            goto LABEL_30;
        }
        if ( *(_WORD *)(v29 + 6) == 8 )
        {
          v19[22] = *(_DWORD *)(*(unsigned __int8 *)(v29 + 5) + v29 + 9);
          v19[23] = *(_DWORD *)(*(unsigned __int8 *)(v29 + 5) + v29 + 13);
          v19[18] |= 8u;
        }
      }
LABEL_30:
      Ea = 0;
    }
    else
    {
      Ea = -1073741275;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC0000225, 0xE0446u);
    }
    if ( v40[2] )
    {
      CcUnpinData((PVOID)v40[2]);
      v40[2] = 0;
    }
    if ( v40[5] )
    {
      CcUnpinData((PVOID)v40[5]);
      v40[5] = 0;
    }
    if ( v40[9] )
    {
      CcUnpinData((PVOID)v40[9]);
      v40[9] = 0;
    }
    if ( v35 )
    {
      CcUnpinData(v35);
      v35 = 0;
    }
    if ( NtfsStatusDebugFlags && Ea )
    {
      v34 = 918695;
      goto LABEL_61;
    }
  }
  return Ea;
}

```

## disassembly

```asm
0x140181588  mov     [rsp+arg_0], rbx
0x14018158d  mov     [rsp+arg_8], rsi
0x140181592  push    rdi
0x140181593  push    r12
0x140181595  push    r13
0x140181597  push    r14
0x140181599  push    r15
0x14018159b  sub     rsp, 100h
0x1401815a2  mov     r15d, r9d
0x1401815a5  mov     rbx, r8
0x1401815a8  mov     rsi, rdx
0x1401815ab  mov     r14, rcx
0x1401815ae  xor     r13d, r13d
0x1401815b1  mov     [rsp+128h+var_D0], r13
0x1401815b6  lea     r12d, [r13+58h]
0x1401815ba  mov     r8d, r12d; Size
0x1401815bd  xor     edx, edx; Val
0x1401815bf  lea     rcx, [rsp+128h+var_88]; void *
0x1401815c7  call    memset
0x1401815cc  mov     [rsp+128h+var_D7], r13b
0x1401815d1  xor     edi, edi
0x1401815d3  xorps   xmm0, xmm0
0x1401815d6  movups  xmmword ptr [rsp+128h+DestinationString.Length], xmm0
0x1401815db  test    rbx, rbx
0x1401815de  jnz     loc_140181AE0
0x1401815e4  mov     r8, r12; Size
0x1401815e7  xor     edx, edx; Val
0x1401815e9  lea     rcx, [rsp+128h+var_88]; void *
0x1401815f1  call    memset
0x1401815f6  mov     r12d, 1
0x1401815fc  mov     [rsp+128h+var_D7], r12b
0x140181601  mov     [rsp+128h+arg_10], 0
0x14018160c  mov     [rsp+128h+var_D8], 0
0x140181611  xor     bl, bl
0x140181613  mov     [rsp+128h+var_D8], bl
0x140181617  lea     r8, [rsi+8]
0x14018161b  lea     rax, [rsp+128h+var_88]
0x140181623  mov     [rsp+128h+var_E0], rax
0x140181628  mov     [rsp+128h+var_E8], 0
0x140181630  mov     [rsp+128h+var_F0], 0
0x140181639  mov     [rsp+128h+var_F8], bl
0x14018163d  mov     [rsp+128h+var_100], 0
0x140181646  mov     [rsp+128h+var_108], 0
0x14018164f  mov     r9d, 0D0h
0x140181655  mov     rdx, rsi
0x140181658  mov     rcx, r14
0x14018165b  call    NtfsLookupInFileRecord
0x140181660  test    al, al
0x140181662  jz      short loc_14018168A
0x140181664  mov     rcx, [rsp+128h+var_88]
0x14018166c  movzx   edi, word ptr [rcx+14h]
0x140181670  add     rdi, rcx
0x140181673  mov     [rsp+128h+var_98], rdi
0x14018167b  movzx   ebx, bl
0x14018167e  cmp     dword ptr [rdi+4], 0
0x140181682  cmovnz  ebx, r12d
0x140181686  mov     [rsp+128h+var_D8], bl
0x14018168a  test    bl, bl
0x14018168c  jz      loc_14018197C
0x140181692  lea     r9, [rsp+128h+arg_10]
0x14018169a  lea     r8, [rsp+128h+var_D0]
0x14018169f  mov     rdx, rsi
0x1401816a2  mov     rcx, r14
0x1401816a5  call    NtfsMapExistingEas
0x1401816aa  mov     r13, rax
0x1401816ad  test    bl, bl
0x1401816af  jz      loc_14018197C
0x1401816b5  lea     rdx, aLxuid; "$LXUID"
0x1401816bc  lea     rcx, [rsp+128h+DestinationString]; DestinationString
0x1401816c1  call    cs:__imp_RtlInitString
0x1401816c8  nop     dword ptr [rax+rax+00h]
0x1401816cd  xorps   xmm0, xmm0
0x1401816d0  movups  xmmword ptr [rsp+128h+String2.Length], xmm0
0x1401816d8  lea     rsi, [r13+8]
0x1401816dc  add     rdi, 4
0x1401816e0  test    r13, r13
0x1401816e3  jz      short loc_140181747
0x1401816e5  mov     r15d, [rdi]
0x1401816e8  xor     eax, eax
0x1401816ea  mov     [rsp+128h+var_D4], eax
0x1401816ee  mov     r14d, eax
0x1401816f1  lea     rbx, [rax+r13]
0x1401816f5  lea     rdx, [rax+rsi]; SourceString
0x1401816f9  lea     rcx, [rsp+128h+String2]; DestinationString
0x140181701  call    cs:__imp_RtlInitString
0x140181708  nop     dword ptr [rax+rax+00h]
0x14018170d  mov     r8b, r12b; CaseInSensitive
0x140181710  lea     rdx, [rsp+128h+String2]; String2
0x140181718  lea     rcx, [rsp+128h+DestinationString]; String1
0x14018171d  call    cs:__imp_RtlCompareString
0x140181724  nop     dword ptr [rax+rax+00h]
0x140181729  test    eax, eax
0x14018172b  jz      loc_14018192E
0x140181731  mov     eax, [rbx]
0x140181733  test    eax, eax
0x140181735  jz      loc_1401819A3
0x14018173b  add     eax, r14d
0x14018173e  mov     [rsp+128h+var_D4], eax
0x140181742  cmp     eax, r15d
0x140181745  jb      short loc_1401816EE
0x140181747  mov     r15d, 4
0x14018174d  mov     rbx, [rsp+128h+arg_20]
0x140181755  lea     rdx, aLxgid; "$LXGID"
0x14018175c  lea     rcx, [rsp+128h+DestinationString]; DestinationString
0x140181761  call    cs:__imp_RtlInitString
0x140181768  nop     dword ptr [rax+rax+00h]
0x14018176d  xorps   xmm0, xmm0
0x140181770  movups  xmmword ptr [rsp+128h+var_B8.Length], xmm0
0x140181775  test    r13, r13
0x140181778  jz      short loc_1401817ED
0x14018177a  mov     eax, [rdi]
0x14018177c  mov     [rsp+128h+arg_10], eax
0x140181783  xor     eax, eax
0x140181785  mov     [rsp+128h+var_D4], eax
0x140181789  mov     qword ptr [rsp+128h+String2.Length], rax
0x140181791  lea     r14, [rax+r13]
0x140181795  lea     rdx, [rax+rsi]; SourceString
0x140181799  lea     rcx, [rsp+128h+var_B8]; DestinationString
0x14018179e  call    cs:__imp_RtlInitString
0x1401817a5  nop     dword ptr [rax+rax+00h]
0x1401817aa  mov     r8b, r12b; CaseInSensitive
0x1401817ad  lea     rdx, [rsp+128h+var_B8]; String2
0x1401817b2  lea     rcx, [rsp+128h+DestinationString]; String1
0x1401817b7  call    cs:__imp_RtlCompareString
0x1401817be  nop     dword ptr [rax+rax+00h]
0x1401817c3  test    eax, eax
0x1401817c5  jz      loc_14018190D
0x1401817cb  mov     eax, [r14]
0x1401817ce  test    eax, eax
0x1401817d0  jz      loc_1401819B8
0x1401817d6  mov     rcx, qword ptr [rsp+128h+String2.Length]
0x1401817de  add     eax, ecx
0x1401817e0  mov     [rsp+128h+var_D4], eax
0x1401817e4  cmp     eax, [rsp+128h+arg_10]
0x1401817eb  jb      short loc_140181789
0x1401817ed  lea     rdx, aLxmod; "$LXMOD"
0x1401817f4  lea     rcx, [rsp+128h+DestinationString]; DestinationString
0x1401817f9  call    cs:__imp_RtlInitString
0x140181800  nop     dword ptr [rax+rax+00h]
0x140181805  xorps   xmm0, xmm0
0x140181808  movups  xmmword ptr [rsp+128h+var_B8.Length], xmm0
0x14018180d  test    r13, r13
0x140181810  jz      short loc_140181885
0x140181812  mov     eax, [rdi]
0x140181814  mov     [rsp+128h+arg_10], eax
0x14018181b  xor     eax, eax
0x14018181d  mov     [rsp+128h+var_D4], eax
0x140181821  mov     qword ptr [rsp+128h+String2.Length], rax
0x140181829  lea     r14, [rax+r13]
0x14018182d  lea     rdx, [rax+rsi]; SourceString
0x140181831  lea     rcx, [rsp+128h+var_B8]; DestinationString
0x140181836  call    cs:__imp_RtlInitString
0x14018183d  nop     dword ptr [rax+rax+00h]
0x140181842  mov     r8b, r12b; CaseInSensitive
0x140181845  lea     rdx, [rsp+128h+var_B8]; String2
0x14018184a  lea     rcx, [rsp+128h+DestinationString]; String1
0x14018184f  call    cs:__imp_RtlCompareString
0x140181856  nop     dword ptr [rax+rax+00h]
0x14018185b  test    eax, eax
0x14018185d  jz      loc_14018195B
0x140181863  mov     eax, [r14]
0x140181866  test    eax, eax
0x140181868  jz      loc_1401819CF
0x14018186e  mov     rcx, qword ptr [rsp+128h+String2.Length]
0x140181876  add     eax, ecx
0x140181878  mov     [rsp+128h+var_D4], eax
0x14018187c  cmp     eax, [rsp+128h+arg_10]
0x140181883  jb      short loc_140181821
0x140181885  lea     rdx, aLxdev; "$LXDEV"
0x14018188c  lea     rcx, [rsp+128h+DestinationString]; DestinationString
0x140181891  call    cs:__imp_RtlInitString
0x140181898  nop     dword ptr [rax+rax+00h]
0x14018189d  xorps   xmm0, xmm0
0x1401818a0  movups  xmmword ptr [rsp+128h+var_B8.Length], xmm0
0x1401818a5  test    r13, r13
0x1401818a8  jz      short loc_140181906
0x1401818aa  mov     r15d, [rdi]
0x1401818ad  xor     eax, eax
0x1401818af  mov     [rsp+128h+var_D4], eax
0x1401818b3  mov     r14d, eax
0x1401818b6  lea     rdi, [rax+r13]
0x1401818ba  lea     rdx, [rax+rsi]; SourceString
0x1401818be  lea     rcx, [rsp+128h+var_B8]; DestinationString
0x1401818c3  call    cs:__imp_RtlInitString
0x1401818ca  nop     dword ptr [rax+rax+00h]
0x1401818cf  mov     r8b, r12b; CaseInSensitive
0x1401818d2  lea     rdx, [rsp+128h+var_B8]; String2
0x1401818d7  lea     rcx, [rsp+128h+DestinationString]; String1
0x1401818dc  call    cs:__imp_RtlCompareString
0x1401818e3  nop     dword ptr [rax+rax+00h]
0x1401818e8  test    eax, eax
0x1401818ea  jz      loc_1401819FB
0x1401818f0  mov     eax, [rdi]
0x1401818f2  test    eax, eax
0x1401818f4  jz      loc_1401819E6
0x1401818fa  add     eax, r14d
0x1401818fd  mov     [rsp+128h+var_D4], eax
0x140181901  cmp     eax, r15d
0x140181904  jb      short loc_1401818B3
0x140181906  xor     ebx, ebx
0x140181908  jmp     loc_140181A28
0x14018190d  cmp     [r14+6], r15w
0x140181912  jnz     loc_1401817ED
0x140181918  movzx   eax, byte ptr [r14+5]
0x14018191d  mov     ecx, [rax+r14+9]
0x140181922  mov     [rbx+50h], ecx
0x140181925  or      dword ptr [rbx+48h], 2
0x140181929  jmp     loc_1401817ED
0x14018192e  mov     r15d, 4
0x140181934  cmp     [rbx+6], r15w
0x140181939  jnz     loc_14018174D
0x14018193f  movzx   eax, byte ptr [rbx+5]
0x140181943  mov     ecx, [rax+rbx+9]
0x140181947  mov     rbx, [rsp+128h+arg_20]
0x14018194f  mov     [rbx+4Ch], ecx
0x140181952  or      [rbx+48h], r12d
0x140181956  jmp     loc_140181755
0x14018195b  cmp     [r14+6], r15w
0x140181960  jnz     loc_140181885
0x140181966  movzx   eax, byte ptr [r14+5]
0x14018196b  mov     ecx, [rax+r14+9]
0x140181970  mov     [rbx+54h], ecx
0x140181973  or      [rbx+48h], r15d
0x140181977  jmp     loc_140181885
0x14018197c  mov     al, cs:NtfsStatusDebugFlags
0x140181982  mov     ebx, 0C0000225h
0x140181987  test    al, al
0x140181989  jz      loc_140181A28
0x14018198f  mov     r8d, 0E0446h
0x140181995  mov     edx, ebx
0x140181997  xor     ecx, ecx
0x140181999  call    NtfsStatusTraceAndDebugInternal
0x14018199e  jmp     loc_140181A28
0x1401819a3  movzx   ecx, word ptr [rbx+6]
0x1401819a7  movzx   eax, byte ptr [rbx+5]
0x1401819ab  add     eax, 0Ch
0x1401819ae  add     eax, ecx
0x1401819b0  and     eax, 0FFFFFFFCh
0x1401819b3  jmp     loc_14018173B
0x1401819b8  movzx   ecx, word ptr [r14+6]
0x1401819bd  movzx   eax, byte ptr [r14+5]
0x1401819c2  add     eax, 0Ch
0x1401819c5  add     eax, ecx
0x1401819c7  and     eax, 0FFFFFFFCh
0x1401819ca  jmp     loc_1401817D6
0x1401819cf  movzx   ecx, word ptr [r14+6]
0x1401819d4  movzx   eax, byte ptr [r14+5]
0x1401819d9  add     eax, 0Ch
0x1401819dc  add     eax, ecx
0x1401819de  and     eax, 0FFFFFFFCh
0x1401819e1  jmp     loc_14018186E
0x1401819e6  movzx   ecx, word ptr [rdi+6]
0x1401819ea  movzx   eax, byte ptr [rdi+5]
0x1401819ee  add     eax, 0Ch
0x1401819f1  add     eax, ecx
0x1401819f3  and     eax, 0FFFFFFFCh
0x1401819f6  jmp     loc_1401818FA
0x1401819fb  mov     edx, 8
0x140181a00  cmp     [rdi+6], dx
0x140181a04  jnz     loc_140181906
0x140181a0a  movzx   eax, byte ptr [rdi+5]
0x140181a0e  mov     ecx, [rax+rdi+9]
0x140181a12  mov     [rbx+58h], ecx
0x140181a15  movzx   eax, byte ptr [rdi+5]
0x140181a19  mov     ecx, [rax+rdi+0Dh]
0x140181a1d  mov     [rbx+5Ch], ecx
0x140181a20  or      [rbx+48h], edx
0x140181a23  jmp     loc_140181906
0x140181a28  mov     rcx, [rsp+128h+Bcb]; Bcb
0x140181a30  test    rcx, rcx
0x140181a33  jz      short loc_140181A4D
0x140181a35  call    cs:__imp_CcUnpinData
0x140181a3c  nop     dword ptr [rax+rax+00h]
0x140181a41  mov     [rsp+128h+Bcb], 0
0x140181a4d  mov     rcx, [rsp+128h+var_60]; Bcb
0x140181a55  test    rcx, rcx
0x140181a58  jz      short loc_140181A72
0x140181a5a  call    cs:__imp_CcUnpinData
0x140181a61  nop     dword ptr [rax+rax+00h]
0x140181a66  mov     [rsp+128h+var_60], 0
0x140181a72  mov     rcx, [rsp+128h+var_40]; Bcb
0x140181a7a  test    rcx, rcx
0x140181a7d  jz      short loc_140181A97
0x140181a7f  call    cs:__imp_CcUnpinData
0x140181a86  nop     dword ptr [rax+rax+00h]
0x140181a8b  mov     [rsp+128h+var_40], 0
0x140181a97  mov     rcx, [rsp+128h+var_D0]; Bcb
0x140181a9c  test    rcx, rcx
0x140181a9f  jz      short loc_140181AB6
0x140181aa1  call    cs:__imp_CcUnpinData
0x140181aa8  nop     dword ptr [rax+rax+00h]
0x140181aad  mov     [rsp+128h+var_D0], 0
0x140181ab6  mov     cl, cs:NtfsStatusDebugFlags
0x140181abc  test    cl, cl
0x140181abe  jnz     short loc_140181B35
0x140181ac0  mov     eax, ebx
0x140181ac2  lea     r11, [rsp+128h+var_28]
0x140181aca  mov     rbx, [r11+30h]
0x140181ace  mov     rsi, [r11+38h]
0x140181ad2  mov     rsp, r11
  ... truncated ...
```
