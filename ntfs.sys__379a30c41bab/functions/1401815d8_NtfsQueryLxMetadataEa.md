# NtfsQueryLxMetadataEa

- ea: `0x1401815d8`
- end: `0x140181b9d`
- name: `NtfsQueryLxMetadataEa`
- size: `1477`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140180e10`

## callees

- `0x140007ea0`
- `0x140059740`
- `0x140125100`
- `0x140179a50`
- `0x1401815d8`
- `0x140182190`
- `0x1401e06b0`

## import_xrefs

- `ntoskrnl!RtlCompareString` at `0x14018176d`
- `ntoskrnl!RtlCompareString` at `0x140181807`
- `ntoskrnl!RtlCompareString` at `0x14018189f`
- `ntoskrnl!RtlCompareString` at `0x14018192c`
- `ntoskrnl!RtlCompareString` at `0x14018176d`
- `ntoskrnl!RtlCompareString` at `0x140181807`
- `ntoskrnl!RtlCompareString` at `0x14018189f`
- `ntoskrnl!RtlCompareString` at `0x14018192c`
- `ntoskrnl!RtlInitString` at `0x140181711`
- `ntoskrnl!RtlInitString` at `0x140181751`
- `ntoskrnl!RtlInitString` at `0x1401817b1`
- `ntoskrnl!RtlInitString` at `0x1401817ee`
- `ntoskrnl!RtlInitString` at `0x140181849`
- `ntoskrnl!RtlInitString` at `0x140181886`
- `ntoskrnl!RtlInitString` at `0x1401818e1`
- `ntoskrnl!RtlInitString` at `0x140181913`
- `ntoskrnl!RtlInitString` at `0x140181711`
- `ntoskrnl!RtlInitString` at `0x140181751`
- `ntoskrnl!RtlInitString` at `0x1401817b1`
- `ntoskrnl!RtlInitString` at `0x1401817ee`
- `ntoskrnl!RtlInitString` at `0x140181849`
- `ntoskrnl!RtlInitString` at `0x140181886`
- `ntoskrnl!RtlInitString` at `0x1401818e1`
- `ntoskrnl!RtlInitString` at `0x140181913`
- `ntoskrnl!CcUnpinData` at `0x140181a85`
- `ntoskrnl!CcUnpinData` at `0x140181aaa`
- `ntoskrnl!CcUnpinData` at `0x140181acf`
- `ntoskrnl!CcUnpinData` at `0x140181af1`
- `ntoskrnl!CcUnpinData` at `0x1402aa6ea`
- `ntoskrnl!CcUnpinData` at `0x140181a85`
- `ntoskrnl!CcUnpinData` at `0x140181aaa`
- `ntoskrnl!CcUnpinData` at `0x140181acf`
- `ntoskrnl!CcUnpinData` at `0x140181af1`
- `ntoskrnl!CcUnpinData` at `0x1402aa6ea`

## pseudocode

```c
__int64 __fastcall NtfsQueryLxMetadataEa(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, _DWORD *a5)
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
  __int64 v34; // r8
  char v35; // [rsp+30h] [rbp-F8h]
  PVOID v36; // [rsp+58h] [rbp-D0h] BYREF
  struct _STRING DestinationString; // [rsp+60h] [rbp-C8h] BYREF
  STRING v38; // [rsp+70h] [rbp-B8h] BYREF
  STRING String2; // [rsp+80h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+90h] [rbp-98h]
  _QWORD v41[12]; // [rsp+A0h] [rbp-88h] BYREF
  unsigned int v42; // [rsp+140h] [rbp+18h] BYREF

  v36 = 0;
  memset(v41, 0, 0x58u);
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
    memset(v41, 0, 0x58u);
    v42 = 0;
    v10 = 0;
    v35 = 0;
    if ( (unsigned __int8)NtfsLookupInFileRecord(a1, a2, a2 + 8, 208, 0, 0, v35, 0, 0, v41) )
    {
      v9 = v41[0] + *(unsigned __int16 *)(v41[0] + 20LL);
      v40 = v9;
      v10 = *(_DWORD *)(v9 + 4) != 0;
    }
    if ( v10 )
    {
      v11 = NtfsMapExistingEas(a1, a2, &v36, &v42);
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
      v38 = 0;
      if ( v11 )
      {
        v42 = *v13;
        v20 = 0;
        while ( 1 )
        {
          *(_QWORD *)&String2.Length = v20;
          v21 = v20 + v11;
          RtlInitString(&v38, (PCSZ)(v20 + v12));
          if ( !RtlCompareString(&DestinationString, &v38, 1u) )
            break;
          v22 = *(_DWORD *)v21;
          if ( !*(_DWORD *)v21 )
            v22 = (*(unsigned __int16 *)(v21 + 6) + *(unsigned __int8 *)(v21 + 5) + 12) & 0xFFFFFFFC;
          v20 = *(_DWORD *)&String2.Length + v22;
          if ( (unsigned int)v20 >= v42 )
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
      v38 = 0;
      if ( v11 )
      {
        v42 = *v13;
        v23 = 0;
        while ( 1 )
        {
          *(_QWORD *)&String2.Length = v23;
          v24 = v23 + v11;
          RtlInitString(&v38, (PCSZ)(v23 + v12));
          if ( !RtlCompareString(&DestinationString, &v38, 1u) )
            break;
          v25 = *(_DWORD *)v24;
          if ( !*(_DWORD *)v24 )
            v25 = (*(unsigned __int16 *)(v24 + 6) + *(unsigned __int8 *)(v24 + 5) + 12) & 0xFFFFFFFC;
          v23 = *(_DWORD *)&String2.Length + v25;
          if ( (unsigned int)v23 >= v42 )
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
      v38 = 0;
      if ( v11 )
      {
        v26 = *v13;
        v27 = 0;
        while ( 1 )
        {
          v28 = v27;
          v29 = v27 + v11;
          RtlInitString(&v38, (PCSZ)(v27 + v12));
          if ( !RtlCompareString(&DestinationString, &v38, 1u) )
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
        NtfsStatusTraceAndDebugInternal(0, 3221226021LL, 918598);
    }
    if ( v41[2] )
    {
      CcUnpinData((PVOID)v41[2]);
      v41[2] = 0;
    }
    if ( v41[5] )
    {
      CcUnpinData((PVOID)v41[5]);
      v41[5] = 0;
    }
    if ( v41[9] )
    {
      CcUnpinData((PVOID)v41[9]);
      v41[9] = 0;
    }
    if ( v36 )
    {
      CcUnpinData(v36);
      v36 = 0;
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
0x1401815d8  mov     [rsp+arg_0], rbx
0x1401815dd  mov     [rsp+arg_8], rsi
0x1401815e2  push    rdi
0x1401815e3  push    r12
0x1401815e5  push    r13
0x1401815e7  push    r14
0x1401815e9  push    r15
0x1401815eb  sub     rsp, 100h
0x1401815f2  mov     r15d, r9d
0x1401815f5  mov     rbx, r8
0x1401815f8  mov     rsi, rdx
0x1401815fb  mov     r14, rcx
0x1401815fe  xor     r13d, r13d
0x140181601  mov     [rsp+128h+var_D0], r13
0x140181606  lea     r12d, [r13+58h]
0x14018160a  mov     r8d, r12d; Size
0x14018160d  xor     edx, edx; Val
0x14018160f  lea     rcx, [rsp+128h+var_88]; void *
0x140181617  call    memset
0x14018161c  mov     [rsp+128h+var_D7], r13b
0x140181621  xor     edi, edi
0x140181623  xorps   xmm0, xmm0
0x140181626  movups  xmmword ptr [rsp+128h+DestinationString.Length], xmm0
0x14018162b  test    rbx, rbx
0x14018162e  jnz     loc_140181B30
0x140181634  mov     r8, r12; Size
0x140181637  xor     edx, edx; Val
0x140181639  lea     rcx, [rsp+128h+var_88]; void *
0x140181641  call    memset
0x140181646  mov     r12d, 1
0x14018164c  mov     [rsp+128h+var_D7], r12b
0x140181651  mov     [rsp+128h+arg_10], 0
0x14018165c  mov     [rsp+128h+var_D8], 0
0x140181661  xor     bl, bl
0x140181663  mov     [rsp+128h+var_D8], bl
0x140181667  lea     r8, [rsi+8]
0x14018166b  lea     rax, [rsp+128h+var_88]
0x140181673  mov     [rsp+128h+var_E0], rax
0x140181678  mov     [rsp+128h+var_E8], 0
0x140181680  mov     [rsp+128h+var_F0], 0
0x140181689  mov     [rsp+128h+var_F8], bl
0x14018168d  mov     [rsp+128h+var_100], 0
0x140181696  mov     [rsp+128h+var_108], 0
0x14018169f  mov     r9d, 0D0h
0x1401816a5  mov     rdx, rsi
0x1401816a8  mov     rcx, r14
0x1401816ab  call    NtfsLookupInFileRecord
0x1401816b0  test    al, al
0x1401816b2  jz      short loc_1401816DA
0x1401816b4  mov     rcx, [rsp+128h+var_88]
0x1401816bc  movzx   edi, word ptr [rcx+14h]
0x1401816c0  add     rdi, rcx
0x1401816c3  mov     [rsp+128h+var_98], rdi
0x1401816cb  movzx   ebx, bl
0x1401816ce  cmp     dword ptr [rdi+4], 0
0x1401816d2  cmovnz  ebx, r12d
0x1401816d6  mov     [rsp+128h+var_D8], bl
0x1401816da  test    bl, bl
0x1401816dc  jz      loc_1401819CC
0x1401816e2  lea     r9, [rsp+128h+arg_10]
0x1401816ea  lea     r8, [rsp+128h+var_D0]
0x1401816ef  mov     rdx, rsi
0x1401816f2  mov     rcx, r14
0x1401816f5  call    NtfsMapExistingEas
0x1401816fa  mov     r13, rax
0x1401816fd  test    bl, bl
0x1401816ff  jz      loc_1401819CC
0x140181705  lea     rdx, aLxuid; "$LXUID"
0x14018170c  lea     rcx, [rsp+128h+DestinationString]; DestinationString
0x140181711  call    cs:__imp_RtlInitString
0x140181718  nop     dword ptr [rax+rax+00h]
0x14018171d  xorps   xmm0, xmm0
0x140181720  movups  xmmword ptr [rsp+128h+String2.Length], xmm0
0x140181728  lea     rsi, [r13+8]
0x14018172c  add     rdi, 4
0x140181730  test    r13, r13
0x140181733  jz      short loc_140181797
0x140181735  mov     r15d, [rdi]
0x140181738  xor     eax, eax
0x14018173a  mov     [rsp+128h+var_D4], eax
0x14018173e  mov     r14d, eax
0x140181741  lea     rbx, [rax+r13]
0x140181745  lea     rdx, [rax+rsi]; SourceString
0x140181749  lea     rcx, [rsp+128h+String2]; DestinationString
0x140181751  call    cs:__imp_RtlInitString
0x140181758  nop     dword ptr [rax+rax+00h]
0x14018175d  mov     r8b, r12b; CaseInSensitive
0x140181760  lea     rdx, [rsp+128h+String2]; String2
0x140181768  lea     rcx, [rsp+128h+DestinationString]; String1
0x14018176d  call    cs:__imp_RtlCompareString
0x140181774  nop     dword ptr [rax+rax+00h]
0x140181779  test    eax, eax
0x14018177b  jz      loc_14018197E
0x140181781  mov     eax, [rbx]
0x140181783  test    eax, eax
0x140181785  jz      loc_1401819F3
0x14018178b  add     eax, r14d
0x14018178e  mov     [rsp+128h+var_D4], eax
0x140181792  cmp     eax, r15d
0x140181795  jb      short loc_14018173E
0x140181797  mov     r15d, 4
0x14018179d  mov     rbx, [rsp+128h+arg_20]
0x1401817a5  lea     rdx, aLxgid; "$LXGID"
0x1401817ac  lea     rcx, [rsp+128h+DestinationString]; DestinationString
0x1401817b1  call    cs:__imp_RtlInitString
0x1401817b8  nop     dword ptr [rax+rax+00h]
0x1401817bd  xorps   xmm0, xmm0
0x1401817c0  movups  xmmword ptr [rsp+128h+var_B8.Length], xmm0
0x1401817c5  test    r13, r13
0x1401817c8  jz      short loc_14018183D
0x1401817ca  mov     eax, [rdi]
0x1401817cc  mov     [rsp+128h+arg_10], eax
0x1401817d3  xor     eax, eax
0x1401817d5  mov     [rsp+128h+var_D4], eax
0x1401817d9  mov     qword ptr [rsp+128h+String2.Length], rax
0x1401817e1  lea     r14, [rax+r13]
0x1401817e5  lea     rdx, [rax+rsi]; SourceString
0x1401817e9  lea     rcx, [rsp+128h+var_B8]; DestinationString
0x1401817ee  call    cs:__imp_RtlInitString
0x1401817f5  nop     dword ptr [rax+rax+00h]
0x1401817fa  mov     r8b, r12b; CaseInSensitive
0x1401817fd  lea     rdx, [rsp+128h+var_B8]; String2
0x140181802  lea     rcx, [rsp+128h+DestinationString]; String1
0x140181807  call    cs:__imp_RtlCompareString
0x14018180e  nop     dword ptr [rax+rax+00h]
0x140181813  test    eax, eax
0x140181815  jz      loc_14018195D
0x14018181b  mov     eax, [r14]
0x14018181e  test    eax, eax
0x140181820  jz      loc_140181A08
0x140181826  mov     rcx, qword ptr [rsp+128h+String2.Length]
0x14018182e  add     eax, ecx
0x140181830  mov     [rsp+128h+var_D4], eax
0x140181834  cmp     eax, [rsp+128h+arg_10]
0x14018183b  jb      short loc_1401817D9
0x14018183d  lea     rdx, aLxmod; "$LXMOD"
0x140181844  lea     rcx, [rsp+128h+DestinationString]; DestinationString
0x140181849  call    cs:__imp_RtlInitString
0x140181850  nop     dword ptr [rax+rax+00h]
0x140181855  xorps   xmm0, xmm0
0x140181858  movups  xmmword ptr [rsp+128h+var_B8.Length], xmm0
0x14018185d  test    r13, r13
0x140181860  jz      short loc_1401818D5
0x140181862  mov     eax, [rdi]
0x140181864  mov     [rsp+128h+arg_10], eax
0x14018186b  xor     eax, eax
0x14018186d  mov     [rsp+128h+var_D4], eax
0x140181871  mov     qword ptr [rsp+128h+String2.Length], rax
0x140181879  lea     r14, [rax+r13]
0x14018187d  lea     rdx, [rax+rsi]; SourceString
0x140181881  lea     rcx, [rsp+128h+var_B8]; DestinationString
0x140181886  call    cs:__imp_RtlInitString
0x14018188d  nop     dword ptr [rax+rax+00h]
0x140181892  mov     r8b, r12b; CaseInSensitive
0x140181895  lea     rdx, [rsp+128h+var_B8]; String2
0x14018189a  lea     rcx, [rsp+128h+DestinationString]; String1
0x14018189f  call    cs:__imp_RtlCompareString
0x1401818a6  nop     dword ptr [rax+rax+00h]
0x1401818ab  test    eax, eax
0x1401818ad  jz      loc_1401819AB
0x1401818b3  mov     eax, [r14]
0x1401818b6  test    eax, eax
0x1401818b8  jz      loc_140181A1F
0x1401818be  mov     rcx, qword ptr [rsp+128h+String2.Length]
0x1401818c6  add     eax, ecx
0x1401818c8  mov     [rsp+128h+var_D4], eax
0x1401818cc  cmp     eax, [rsp+128h+arg_10]
0x1401818d3  jb      short loc_140181871
0x1401818d5  lea     rdx, aLxdev; "$LXDEV"
0x1401818dc  lea     rcx, [rsp+128h+DestinationString]; DestinationString
0x1401818e1  call    cs:__imp_RtlInitString
0x1401818e8  nop     dword ptr [rax+rax+00h]
0x1401818ed  xorps   xmm0, xmm0
0x1401818f0  movups  xmmword ptr [rsp+128h+var_B8.Length], xmm0
0x1401818f5  test    r13, r13
0x1401818f8  jz      short loc_140181956
0x1401818fa  mov     r15d, [rdi]
0x1401818fd  xor     eax, eax
0x1401818ff  mov     [rsp+128h+var_D4], eax
0x140181903  mov     r14d, eax
0x140181906  lea     rdi, [rax+r13]
0x14018190a  lea     rdx, [rax+rsi]; SourceString
0x14018190e  lea     rcx, [rsp+128h+var_B8]; DestinationString
0x140181913  call    cs:__imp_RtlInitString
0x14018191a  nop     dword ptr [rax+rax+00h]
0x14018191f  mov     r8b, r12b; CaseInSensitive
0x140181922  lea     rdx, [rsp+128h+var_B8]; String2
0x140181927  lea     rcx, [rsp+128h+DestinationString]; String1
0x14018192c  call    cs:__imp_RtlCompareString
0x140181933  nop     dword ptr [rax+rax+00h]
0x140181938  test    eax, eax
0x14018193a  jz      loc_140181A4B
0x140181940  mov     eax, [rdi]
0x140181942  test    eax, eax
0x140181944  jz      loc_140181A36
0x14018194a  add     eax, r14d
0x14018194d  mov     [rsp+128h+var_D4], eax
0x140181951  cmp     eax, r15d
0x140181954  jb      short loc_140181903
0x140181956  xor     ebx, ebx
0x140181958  jmp     loc_140181A78
0x14018195d  cmp     [r14+6], r15w
0x140181962  jnz     loc_14018183D
0x140181968  movzx   eax, byte ptr [r14+5]
0x14018196d  mov     ecx, [rax+r14+9]
0x140181972  mov     [rbx+50h], ecx
0x140181975  or      dword ptr [rbx+48h], 2
0x140181979  jmp     loc_14018183D
0x14018197e  mov     r15d, 4
0x140181984  cmp     [rbx+6], r15w
0x140181989  jnz     loc_14018179D
0x14018198f  movzx   eax, byte ptr [rbx+5]
0x140181993  mov     ecx, [rax+rbx+9]
0x140181997  mov     rbx, [rsp+128h+arg_20]
0x14018199f  mov     [rbx+4Ch], ecx
0x1401819a2  or      [rbx+48h], r12d
0x1401819a6  jmp     loc_1401817A5
0x1401819ab  cmp     [r14+6], r15w
0x1401819b0  jnz     loc_1401818D5
0x1401819b6  movzx   eax, byte ptr [r14+5]
0x1401819bb  mov     ecx, [rax+r14+9]
0x1401819c0  mov     [rbx+54h], ecx
0x1401819c3  or      [rbx+48h], r15d
0x1401819c7  jmp     loc_1401818D5
0x1401819cc  mov     al, cs:NtfsStatusDebugFlags
0x1401819d2  mov     ebx, 0C0000225h
0x1401819d7  test    al, al
0x1401819d9  jz      loc_140181A78
0x1401819df  mov     r8d, 0E0446h
0x1401819e5  mov     edx, ebx
0x1401819e7  xor     ecx, ecx
0x1401819e9  call    NtfsStatusTraceAndDebugInternal
0x1401819ee  jmp     loc_140181A78
0x1401819f3  movzx   ecx, word ptr [rbx+6]
0x1401819f7  movzx   eax, byte ptr [rbx+5]
0x1401819fb  add     eax, 0Ch
0x1401819fe  add     eax, ecx
0x140181a00  and     eax, 0FFFFFFFCh
0x140181a03  jmp     loc_14018178B
0x140181a08  movzx   ecx, word ptr [r14+6]
0x140181a0d  movzx   eax, byte ptr [r14+5]
0x140181a12  add     eax, 0Ch
0x140181a15  add     eax, ecx
0x140181a17  and     eax, 0FFFFFFFCh
0x140181a1a  jmp     loc_140181826
0x140181a1f  movzx   ecx, word ptr [r14+6]
0x140181a24  movzx   eax, byte ptr [r14+5]
0x140181a29  add     eax, 0Ch
0x140181a2c  add     eax, ecx
0x140181a2e  and     eax, 0FFFFFFFCh
0x140181a31  jmp     loc_1401818BE
0x140181a36  movzx   ecx, word ptr [rdi+6]
0x140181a3a  movzx   eax, byte ptr [rdi+5]
0x140181a3e  add     eax, 0Ch
0x140181a41  add     eax, ecx
0x140181a43  and     eax, 0FFFFFFFCh
0x140181a46  jmp     loc_14018194A
0x140181a4b  mov     edx, 8
0x140181a50  cmp     [rdi+6], dx
0x140181a54  jnz     loc_140181956
0x140181a5a  movzx   eax, byte ptr [rdi+5]
0x140181a5e  mov     ecx, [rax+rdi+9]
0x140181a62  mov     [rbx+58h], ecx
0x140181a65  movzx   eax, byte ptr [rdi+5]
0x140181a69  mov     ecx, [rax+rdi+0Dh]
0x140181a6d  mov     [rbx+5Ch], ecx
0x140181a70  or      [rbx+48h], edx
0x140181a73  jmp     loc_140181956
0x140181a78  mov     rcx, [rsp+128h+Bcb]; Bcb
0x140181a80  test    rcx, rcx
0x140181a83  jz      short loc_140181A9D
0x140181a85  call    cs:__imp_CcUnpinData
0x140181a8c  nop     dword ptr [rax+rax+00h]
0x140181a91  mov     [rsp+128h+Bcb], 0
0x140181a9d  mov     rcx, [rsp+128h+var_60]; Bcb
0x140181aa5  test    rcx, rcx
0x140181aa8  jz      short loc_140181AC2
0x140181aaa  call    cs:__imp_CcUnpinData
0x140181ab1  nop     dword ptr [rax+rax+00h]
0x140181ab6  mov     [rsp+128h+var_60], 0
0x140181ac2  mov     rcx, [rsp+128h+var_40]; Bcb
0x140181aca  test    rcx, rcx
0x140181acd  jz      short loc_140181AE7
0x140181acf  call    cs:__imp_CcUnpinData
0x140181ad6  nop     dword ptr [rax+rax+00h]
0x140181adb  mov     [rsp+128h+var_40], 0
0x140181ae7  mov     rcx, [rsp+128h+var_D0]; Bcb
0x140181aec  test    rcx, rcx
0x140181aef  jz      short loc_140181B06
0x140181af1  call    cs:__imp_CcUnpinData
0x140181af8  nop     dword ptr [rax+rax+00h]
0x140181afd  mov     [rsp+128h+var_D0], 0
0x140181b06  mov     cl, cs:NtfsStatusDebugFlags
0x140181b0c  test    cl, cl
0x140181b0e  jnz     short loc_140181B85
0x140181b10  mov     eax, ebx
0x140181b12  lea     r11, [rsp+128h+var_28]
0x140181b1a  mov     rbx, [r11+30h]
0x140181b1e  mov     rsi, [r11+38h]
0x140181b22  mov     rsp, r11
  ... truncated ...
```
