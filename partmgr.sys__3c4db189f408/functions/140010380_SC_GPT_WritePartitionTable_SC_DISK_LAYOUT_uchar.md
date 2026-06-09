# SC_GPT::WritePartitionTable(SC_DISK_LAYOUT *,uchar)

- ea: `0x140010380`
- end: `0x140010856`
- name: `?WritePartitionTable@SC_GPT@@QEAAJPEAVSC_DISK_LAYOUT@@E@Z`
- size: `1238`
- prototype: `__int64 __fastcall(SC_DISK **this, struct SC_DISK_LAYOUT *, char)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14000ea44`
- `0x14000f180`

## callees

- `0x140004ef8`
- `0x14000a530`
- `0x14000a93d`
- `0x14000ef60`
- `0x14000f264`
- `0x14000fb14`
- `0x14000ffcc`
- `0x140010380`
- `0x140011440`
- `0x14001c3bc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140010836`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010836`

## pseudocode

```c
__int64 __fastcall SC_GPT::WritePartitionTable(SC_DISK **this, struct SC_DISK_LAYOUT *a2, char a3)
{
  SC_DISK *v3; // r9
  struct SC_DISK_LAYOUT *v4; // r12
  __int64 v6; // rdi
  unsigned int v7; // ecx
  int Header; // ebx
  unsigned int v9; // edx
  __int64 v10; // r13
  unsigned int v11; // r8d
  unsigned int v12; // r15d
  int v13; // r14d
  __int64 v14; // r15
  unsigned __int64 v15; // r15
  char *v16; // r14
  __int64 v17; // r11
  char *v18; // rbx
  char *v19; // rbp
  int v20; // r11d
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rax
  __int128 v25; // xmm0
  SC_DISK *v26; // rcx
  ULONG v27; // eax
  ULONG v28; // r8d
  ULONG v29; // eax
  unsigned __int64 v30; // r8
  SC_DISK *v31; // rcx
  char *v32; // rbx
  __int64 v33; // rcx
  __int64 v34; // rax
  ULONG v35; // r8d
  ULONG v36; // eax
  unsigned __int64 v37; // r8
  int v39; // [rsp+20h] [rbp-68h]
  int v40; // [rsp+24h] [rbp-64h]
  unsigned __int64 v41; // [rsp+28h] [rbp-60h]
  __int64 v42; // [rsp+30h] [rbp-58h]
  unsigned __int64 v43; // [rsp+38h] [rbp-50h]
  unsigned int v46; // [rsp+A8h] [rbp+20h]

  v3 = *this;
  v40 = 0;
  v4 = a2;
  v6 = *((_QWORD *)*this + 33);
  if ( a3 )
  {
    if ( *(_WORD *)(v6 + 510) == 0xAA55 )
      v40 = *(_DWORD *)(v6 + 440);
    v7 = *((_DWORD *)a2 + 10);
    if ( v7 <= 0x80 )
    {
      v7 = 128;
    }
    else if ( v7 > 0x400 )
    {
      return (unsigned int)-1073741811;
    }
    v39 = 128;
    v9 = -*((_DWORD *)v3 + 59) & ((v7 << 7) + *((_DWORD *)v3 + 59) - 1);
    v10 = v9 >> *((_DWORD *)v3 + 60);
    v11 = v9 >> 7;
    v41 = (unsigned int)(v10 + 2);
  }
  else
  {
    v12 = 2 - ((*((_BYTE *)v3 + 200) & 1) != 0);
    v13 = 0;
    while ( 1 )
    {
      Header = SC_GPT::ReadHeader(this, v13, (struct GPT_HEADER *)v6);
      if ( Header >= 0 )
        break;
      if ( ++v13 >= v12 )
        return (unsigned int)Header;
    }
    v3 = *this;
    v11 = *(_DWORD *)(v6 + 80);
    v41 = *(_QWORD *)(v6 + 40);
    v39 = *(_DWORD *)(v6 + 84);
    v9 = -*((_DWORD *)*this + 59) & (v11 * v39 + *((_DWORD *)*this + 59) - 1);
    v10 = v9 >> *((_DWORD *)*this + 60);
  }
  v46 = v11;
  if ( *((_DWORD *)v4 + 1) > v11 )
    return (unsigned int)-1073741811;
  v14 = *((_QWORD *)v3 + 31);
  if ( (*((_DWORD *)v3 + 50) & 1) != 0 )
    v15 = v14 - 1;
  else
    v15 = v14 - (unsigned int)v10 - 2;
  v43 = v9 + (2 << *((_DWORD *)v3 + 60));
  v16 = (char *)SC_ENV::Allocate(v43, v9, v11, 1u);
  if ( v16 )
  {
    v17 = 0;
    v42 = 1 << *((_DWORD *)*this + 60);
    v18 = &v16[v42];
    while ( (unsigned int)v17 < *((_DWORD *)v4 + 1) )
    {
      v19 = (char *)v4 + 144 * v17;
      if ( !SC_PART_ENTRY::IsUnused((SC_PART_ENTRY *)(v19 + 48)) )
      {
        v21 = *((_QWORD *)v19 + 12) - *(_QWORD *)&GUID_NULL.Data1;
        if ( !v21 )
          v21 = *((_QWORD *)v19 + 13) - *(_QWORD *)GUID_NULL.Data4;
        if ( !v21 )
          SC_ENV::CreateGuid((struct _GUID *)v19 + 6);
        *(_OWORD *)v18 = *((_OWORD *)v19 + 5);
        *((_OWORD *)v18 + 1) = *((_OWORD *)v19 + 6);
        v22 = *((_QWORD *)v19 + 7);
        if ( *((_DWORD *)*this + 59) )
          v22 /= (__int64)*((unsigned int *)*this + 59);
        *((_QWORD *)v18 + 4) = v22;
        v23 = *((_QWORD *)v19 + 8) - 1LL + *((_QWORD *)v19 + 7);
        if ( *((_DWORD *)*this + 59) )
          v23 /= (__int64)*((unsigned int *)*this + 59);
        *((_QWORD *)v18 + 5) = v23;
        *((_QWORD *)v18 + 6) = *((_QWORD *)v19 + 14);
        RtlStringCbCopyW((unsigned __int16 *)v18 + 28, v23, (unsigned __int16 *)v19 + 60);
        if ( *((_QWORD *)v18 + 4) < v41 || *((_QWORD *)v18 + 5) > v15 )
        {
          Header = -1073741811;
          goto LABEL_45;
        }
        v4 = a2;
        v18 += 128;
      }
      v17 = (unsigned int)(v20 + 1);
    }
    v24 = *((_QWORD *)v4 + 1) - *(_QWORD *)&GUID_NULL.Data1;
    if ( !v24 )
      v24 = *((_QWORD *)v4 + 2) - *(_QWORD *)GUID_NULL.Data4;
    if ( !v24 )
      SC_ENV::CreateGuid((struct _GUID *)((char *)v4 + 8));
    v25 = *(_OWORD *)((char *)v4 + 8);
    *((_QWORD *)v4 + 4) = (v15 - v41 + 1) << *((_DWORD *)*this + 60);
    *(_QWORD *)v16 = 0x5452415020494645LL;
    *((_DWORD *)v4 + 10) = v46;
    *((_DWORD *)v16 + 20) = v46;
    v26 = *this;
    *((_QWORD *)v16 + 5) = v41;
    *((_QWORD *)v16 + 4) = v15 + v10 + 1;
    *((_QWORD *)v16 + 6) = v15;
    *((_QWORD *)v16 + 9) = v41 - (unsigned int)v10;
    *((_DWORD *)v16 + 21) = v39;
    *((_DWORD *)v16 + 2) = 0x10000;
    *((_DWORD *)v16 + 3) = 92;
    *((_QWORD *)v16 + 3) = 1;
    *(_OWORD *)(v16 + 56) = v25;
    v27 = RtlComputeCrc32_0(0, (PUCHAR)&v16[v42], (_DWORD)v10 << *((_DWORD *)v26 + 60));
    v28 = *((_DWORD *)v16 + 3);
    *((_DWORD *)v16 + 22) = v27;
    v29 = RtlComputeCrc32_0(0, (PUCHAR)v16, v28);
    v30 = *((_QWORD *)v16 + 3);
    v31 = *this;
    *((_DWORD *)v16 + 4) = v29;
    Header = SC_DISK::WriteSectors(v31, (int)v10 + 1, v30, v16);
    if ( Header >= 0 )
    {
      if ( (*((_DWORD *)*this + 50) & 1) != 0 )
        goto LABEL_43;
      v32 = &v16[v43 - v42];
      *(_OWORD *)v32 = *(_OWORD *)v16;
      *((_OWORD *)v32 + 1) = *((_OWORD *)v16 + 1);
      *((_OWORD *)v32 + 2) = *((_OWORD *)v16 + 2);
      *((_OWORD *)v32 + 3) = *((_OWORD *)v16 + 3);
      *((_OWORD *)v32 + 4) = *((_OWORD *)v16 + 4);
      *(_OWORD *)(v32 + 76) = *(_OWORD *)(v16 + 76);
      v33 = *((_QWORD *)v32 + 4);
      v34 = *((_QWORD *)v32 + 3);
      v35 = *((_DWORD *)v32 + 3);
      *((_QWORD *)v32 + 3) = v33;
      *((_QWORD *)v32 + 9) = v33 - (unsigned int)v10;
      *((_DWORD *)v32 + 4) = 0;
      *((_QWORD *)v32 + 4) = v34;
      v36 = RtlComputeCrc32_0(0, (PUCHAR)v32, v35);
      v37 = *((_QWORD *)v32 + 9);
      *((_DWORD *)v32 + 4) = v36;
      Header = SC_DISK::WriteSectors(*this, (int)v10 + 1, v37, &v16[v42]);
      if ( Header >= 0 )
      {
LABEL_43:
        *((_DWORD *)*this + 50) &= ~2u;
        if ( a3 )
        {
          memset((void *)v6, 0, 0x200u);
          *(_DWORD *)(v6 + 440) = v40;
          *(_BYTE *)(v6 + 450) = -18;
          *(_DWORD *)(v6 + 454) = 1;
          *(_DWORD *)(v6 + 458) = -1;
          MBR_ENTRY::ComputeChs((MBR_ENTRY *)(v6 + 446), (struct _DISK_GEOMETRY *)*this + 9);
          *(_WORD *)(v6 + 510) = -21931;
          Header = SC_DISK::WriteSectors(*this, 1u, 0, 0);
        }
      }
    }
LABEL_45:
    ExFreePoolWithTag(v16, 0);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)Header;
}

```

## disassembly

```asm
0x140010380  mov     [rsp+arg_10], r8b
0x140010385  mov     [rsp+arg_8], rdx
0x14001038a  push    rbx
0x14001038b  push    rbp
0x14001038c  push    rsi
0x14001038d  push    rdi
0x14001038e  push    r12
0x140010390  push    r13
0x140010392  push    r14
0x140010394  push    r15
0x140010396  sub     rsp, 48h
0x14001039a  mov     r9, [rcx]
0x14001039d  mov     ebp, 2
0x1400103a2  mov     [rsp+88h+var_64], 0
0x1400103aa  mov     r12, rdx
0x1400103ad  mov     rsi, rcx
0x1400103b0  mov     ecx, 0AA55h
0x1400103b5  mov     rdi, [r9+108h]
0x1400103bc  lea     edx, [rbp+7Eh]
0x1400103bf  test    r8b, r8b
0x1400103c2  jz      short loc_14001042A
0x1400103c4  cmp     [rdi+1FEh], cx
0x1400103cb  jnz     short loc_1400103D7
0x1400103cd  mov     eax, [rdi+1B8h]
0x1400103d3  mov     [rsp+88h+var_64], eax
0x1400103d7  mov     ecx, [r12+28h]
0x1400103dc  cmp     ecx, edx
0x1400103de  jbe     short loc_1400103F2
0x1400103e0  cmp     ecx, 400h
0x1400103e6  jbe     short loc_1400103F4
0x1400103e8  mov     ebx, 0C000000Dh
0x1400103ed  jmp     loc_140010842
0x1400103f2  mov     ecx, edx
0x1400103f4  mov     eax, [r9+0ECh]
0x1400103fb  mov     [rsp+88h+var_68], edx
0x1400103ff  shl     ecx, 7
0x140010402  lea     edx, [rax-1]
0x140010405  neg     eax
0x140010407  add     edx, ecx
0x140010409  mov     ecx, [r9+0F0h]
0x140010410  and     edx, eax
0x140010412  mov     r13d, edx
0x140010415  mov     r8d, edx
0x140010418  shr     r13d, cl
0x14001041b  shr     r8d, 7
0x14001041f  lea     r10d, [r13+2]
0x140010423  mov     [rsp+88h+var_60], r10
0x140010428  jmp     short loc_14001049C
0x14001042a  mov     al, [r9+0C8h]
0x140010431  and     al, 1
0x140010433  neg     al
0x140010435  sbb     r15d, r15d
0x140010438  add     r15d, ebp
0x14001043b  xor     r14d, r14d
0x14001043e  mov     r8, rdi; struct GPT_HEADER *
0x140010441  mov     edx, r14d; unsigned int
0x140010444  mov     rcx, rsi; this
0x140010447  call    ?ReadHeader@SC_GPT@@AEAAJKPEAVGPT_HEADER@@@Z; SC_GPT::ReadHeader(ulong,GPT_HEADER *)
0x14001044c  mov     ebx, eax
0x14001044e  test    eax, eax
0x140010450  jns     short loc_14001045F
0x140010452  inc     r14d
0x140010455  cmp     r14d, r15d
0x140010458  jb      short loc_14001043E
0x14001045a  jmp     loc_140010842
0x14001045f  mov     r9, [rsi]
0x140010462  mov     rax, [rdi+28h]
0x140010466  mov     r11d, [rdi+54h]
0x14001046a  mov     r8d, [rdi+50h]; unsigned __int8
0x14001046e  mov     ecx, [r9+0ECh]
0x140010475  mov     [rsp+88h+var_60], rax
0x14001047a  mov     eax, r11d
0x14001047d  imul    eax, r8d
0x140010481  mov     [rsp+88h+var_68], r11d
0x140010486  lea     edx, [rcx-1]
0x140010489  neg     ecx
0x14001048b  add     edx, eax
0x14001048d  and     edx, ecx; unsigned int
0x14001048f  mov     ecx, [r9+0F0h]
0x140010496  mov     r13d, edx
0x140010499  shr     r13d, cl
0x14001049c  mov     [rsp+88h+arg_18], r8d
0x1400104a4  cmp     [r12+4], r8d
0x1400104a9  ja      loc_1400103E8
0x1400104af  mov     eax, [r9+0C8h]
0x1400104b6  mov     r15, [r9+0F8h]
0x1400104bd  test    al, 1
0x1400104bf  jz      short loc_1400104C6
0x1400104c1  dec     r15
0x1400104c4  jmp     short loc_1400104CF
0x1400104c6  mov     eax, r13d
0x1400104c9  sub     r15, rax
0x1400104cc  sub     r15, rbp
0x1400104cf  mov     ecx, [r9+0F0h]
0x1400104d6  mov     r9d, 1; unsigned int
0x1400104dc  shl     ebp, cl
0x1400104de  lea     ecx, [rdx+rbp]; unsigned __int64
0x1400104e1  mov     [rsp+88h+var_50], rcx
0x1400104e6  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x1400104eb  mov     r14, rax
0x1400104ee  test    rax, rax
0x1400104f1  jnz     short loc_1400104FD
0x1400104f3  mov     ebx, 0C000009Ah
0x1400104f8  jmp     loc_140010842
0x1400104fd  mov     rcx, [rsi]
0x140010500  mov     eax, 1
0x140010505  mov     ecx, [rcx+0F0h]
0x14001050b  shl     eax, cl
0x14001050d  cdqe
0x14001050f  xor     r11d, r11d
0x140010512  mov     [rsp+88h+var_58], rax
0x140010517  lea     rbx, [r14+rax]
0x14001051b  mov     [rsp+88h+arg_0], r11d
0x140010523  cmp     r11d, [r12+4]
0x140010528  jnb     loc_14001061C
0x14001052e  lea     rbp, [r11+r11*8]
0x140010532  shl     rbp, 4
0x140010536  add     rbp, r12
0x140010539  lea     rcx, [rbp+30h]; this
0x14001053d  call    ?IsUnused@SC_PART_ENTRY@@QEAAEXZ; SC_PART_ENTRY::IsUnused(void)
0x140010542  test    al, al
0x140010544  jnz     loc_14001060A
0x14001054a  lea     r12, [rbp+60h]
0x14001054e  mov     rax, [r12]
0x140010552  sub     rax, qword ptr cs:GUID_NULL.Data1
0x140010559  jnz     short loc_140010567
0x14001055b  mov     rax, [r12+8]
0x140010560  sub     rax, qword ptr cs:GUID_NULL.Data4
0x140010567  test    rax, rax
0x14001056a  jnz     short loc_14001057C
0x14001056c  mov     rcx, r12; struct _GUID *
0x14001056f  call    ?CreateGuid@SC_ENV@@SAJPEAU_GUID@@@Z; SC_ENV::CreateGuid(_GUID *)
0x140010574  mov     r11d, [rsp+88h+arg_0]
0x14001057c  movups  xmm0, xmmword ptr [rbp+50h]
0x140010580  movdqu  xmmword ptr [rbx], xmm0
0x140010584  movups  xmm1, xmmword ptr [r12]
0x140010589  movdqu  xmmword ptr [rbx+10h], xmm1
0x14001058e  mov     rax, [rsi]
0x140010591  mov     rdx, [rbp+38h]
0x140010595  mov     ecx, [rax+0ECh]
0x14001059b  test    ecx, ecx
0x14001059d  jz      short loc_1400105AA
0x14001059f  mov     rax, rdx
0x1400105a2  cqo
0x1400105a4  idiv    rcx
0x1400105a7  mov     rdx, rax
0x1400105aa  mov     [rbx+20h], rdx
0x1400105ae  mov     rcx, [rbp+40h]
0x1400105b2  mov     rax, [rsi]
0x1400105b5  dec     rcx
0x1400105b8  mov     rdx, [rbp+38h]
0x1400105bc  add     rdx, rcx
0x1400105bf  mov     ecx, [rax+0ECh]
0x1400105c5  test    ecx, ecx
0x1400105c7  jz      short loc_1400105D4
0x1400105c9  mov     rax, rdx
0x1400105cc  cqo
0x1400105ce  idiv    rcx
0x1400105d1  mov     rdx, rax; unsigned __int64
0x1400105d4  mov     [rbx+28h], rdx
0x1400105d8  lea     r8, [rbp+78h]; unsigned __int16 *
0x1400105dc  mov     rax, [rbp+70h]
0x1400105e0  lea     rcx, [rbx+38h]; unsigned __int16 *
0x1400105e4  mov     [rbx+30h], rax
0x1400105e8  call    ?RtlStringCbCopyW@@YAJPEAG_KPEBG@Z; RtlStringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1400105ed  mov     rax, [rsp+88h+var_60]
0x1400105f2  cmp     [rbx+20h], rax
0x1400105f6  jb      short loc_140010612
0x1400105f8  cmp     [rbx+28h], r15
0x1400105fc  ja      short loc_140010612
0x1400105fe  mov     r12, [rsp+88h+arg_8]
0x140010606  sub     rbx, 0FFFFFFFFFFFFFF80h
0x14001060a  inc     r11d
0x14001060d  jmp     loc_14001051B
0x140010612  mov     ebx, 0C000000Dh
0x140010617  jmp     loc_140010831
0x14001061c  lea     rbx, [r12+8]
0x140010621  mov     rax, [rbx]
0x140010624  sub     rax, qword ptr cs:GUID_NULL.Data1
0x14001062b  jnz     short loc_140010638
0x14001062d  mov     rax, [rbx+8]
0x140010631  sub     rax, qword ptr cs:GUID_NULL.Data4
0x140010638  test    rax, rax
0x14001063b  jnz     short loc_140010645
0x14001063d  mov     rcx, rbx; struct _GUID *
0x140010640  call    ?CreateGuid@SC_ENV@@SAJPEAU_GUID@@@Z; SC_ENV::CreateGuid(_GUID *)
0x140010645  mov     rcx, [rsi]
0x140010648  mov     rax, r15
0x14001064b  mov     rdx, [rsp+88h+var_60]
0x140010650  mov     r8d, r13d
0x140010653  movups  xmm0, xmmword ptr [rbx]
0x140010656  sub     rax, rdx
0x140010659  mov     ebp, r13d
0x14001065c  mov     ecx, [rcx+0F0h]
0x140010662  inc     rax
0x140010665  shl     rax, cl
0x140010668  mov     ecx, [rsp+88h+arg_18]
0x14001066f  mov     [r12+20h], rax
0x140010674  mov     rax, 5452415020494645h
0x14001067e  mov     [r14], rax
0x140010681  lea     rax, [r13+1]
0x140010685  mov     [r12+28h], ecx
0x14001068a  add     rax, r15
0x14001068d  mov     r12, [rsp+88h+var_58]
0x140010692  mov     [r14+50h], ecx
0x140010696  mov     rcx, [rsi]
0x140010699  mov     [r14+28h], rdx
0x14001069d  sub     rdx, rbp
0x1400106a0  mov     [r14+20h], rax
0x1400106a4  mov     eax, [rsp+88h+var_68]
0x1400106a8  mov     [r14+30h], r15
0x1400106ac  lea     r15, [r14+r12]
0x1400106b0  mov     [r14+48h], rdx
0x1400106b4  mov     rdx, r15; Buffer
0x1400106b7  mov     [r14+54h], eax
0x1400106bb  mov     dword ptr [r14+8], 10000h
0x1400106c3  mov     dword ptr [r14+0Ch], 5Ch ; '\'
0x1400106cb  mov     qword ptr [r14+18h], 1
0x1400106d3  movdqu  xmmword ptr [r14+38h], xmm0
0x1400106d9  mov     ecx, [rcx+0F0h]
0x1400106df  shl     r8d, cl; Length
0x1400106e2  xor     ecx, ecx; InitialCrc
0x1400106e4  call    RtlComputeCrc32_0
0x1400106e9  mov     r8d, [r14+0Ch]; Length
0x1400106ed  mov     rdx, r14; Buffer
0x1400106f0  xor     ecx, ecx; InitialCrc
0x1400106f2  mov     [r14+58h], eax
0x1400106f6  call    RtlComputeCrc32_0
0x1400106fb  mov     r8, [r14+18h]; unsigned __int64
0x1400106ff  lea     edx, [r13+1]; unsigned int
0x140010703  mov     rcx, [rsi]; this
0x140010706  mov     r9, r14; void *
0x140010709  mov     [r14+10h], eax
0x14001070d  call    ?WriteSectors@SC_DISK@@QEAAJK_KPEAX@Z; SC_DISK::WriteSectors(ulong,unsigned __int64,void *)
0x140010712  mov     ebx, eax
0x140010714  test    eax, eax
0x140010716  js      loc_140010831
0x14001071c  mov     rax, [rsi]
0x14001071f  mov     ecx, [rax+0C8h]
0x140010725  test    cl, 1
0x140010728  jnz     loc_1400107B5
0x14001072e  movups  xmm0, xmmword ptr [r14]
0x140010732  mov     rbx, [rsp+88h+var_50]
0x140010737  sub     rbx, r12
0x14001073a  add     rbx, r14
0x14001073d  mov     rdx, rbx; Buffer
0x140010740  movups  xmmword ptr [rbx], xmm0
0x140010743  movups  xmm1, xmmword ptr [r14+10h]
0x140010748  movups  xmmword ptr [rbx+10h], xmm1
0x14001074c  movups  xmm0, xmmword ptr [r14+20h]
0x140010751  movups  xmmword ptr [rbx+20h], xmm0
0x140010755  movups  xmm1, xmmword ptr [r14+30h]
0x14001075a  movups  xmmword ptr [rbx+30h], xmm1
0x14001075e  movups  xmm0, xmmword ptr [r14+40h]
0x140010763  movups  xmmword ptr [rbx+40h], xmm0
0x140010767  movups  xmm1, xmmword ptr [r14+4Ch]
0x14001076c  movups  xmmword ptr [rbx+4Ch], xmm1
0x140010770  mov     rcx, [rbx+20h]
0x140010774  mov     rax, [rbx+18h]
0x140010778  mov     r8d, [rbx+0Ch]; Length
0x14001077c  mov     [rbx+18h], rcx
0x140010780  sub     rcx, rbp
0x140010783  mov     [rbx+48h], rcx
0x140010787  xor     ecx, ecx; InitialCrc
0x140010789  mov     dword ptr [rbx+10h], 0
0x140010790  mov     [rbx+20h], rax
0x140010794  call    RtlComputeCrc32_0
0x140010799  mov     r8, [rbx+48h]; unsigned __int64
0x14001079d  lea     edx, [r13+1]; unsigned int
0x1400107a1  mov     [rbx+10h], eax
0x1400107a4  mov     r9, r15; void *
0x1400107a7  mov     rcx, [rsi]; this
0x1400107aa  call    ?WriteSectors@SC_DISK@@QEAAJK_KPEAX@Z; SC_DISK::WriteSectors(ulong,unsigned __int64,void *)
0x1400107af  mov     ebx, eax
0x1400107b1  test    eax, eax
0x1400107b3  js      short loc_140010831
0x1400107b5  mov     rax, [rsi]
0x1400107b8  and     dword ptr [rax+0C8h], 0FFFFFFFDh
0x1400107bf  cmp     [rsp+88h+arg_10], 0
0x1400107c7  jz      short loc_140010831
0x1400107c9  xor     edx, edx; Val
0x1400107cb  mov     r8d, 200h; Size
0x1400107d1  mov     rcx, rdi; void *
0x1400107d4  call    memset
0x1400107d9  mov     eax, [rsp+88h+var_64]
0x1400107dd  lea     rcx, [rdi+1BEh]; this
0x1400107e4  mov     [rdi+1B8h], eax
0x1400107ea  mov     byte ptr [rdi+1C2h], 0EEh
0x1400107f1  mov     dword ptr [rdi+1C6h], 1
0x1400107fb  mov     dword ptr [rdi+1CAh], 0FFFFFFFFh
0x140010805  mov     rdx, [rsi]
0x140010808  add     rdx, 0D8h; struct _DISK_GEOMETRY *
0x14001080f  call    ?ComputeChs@MBR_ENTRY@@QEAAXPEAU_DISK_GEOMETRY@@@Z; MBR_ENTRY::ComputeChs(_DISK_GEOMETRY *)
0x140010814  xor     r9d, r9d; void *
0x140010817  mov     word ptr [rdi+1FEh], 0AA55h
0x140010820  mov     rcx, [rsi]; this
0x140010823  xor     r8d, r8d; unsigned __int64
0x140010826  lea     edx, [r9+1]; unsigned int
0x14001082a  call    ?WriteSectors@SC_DISK@@QEAAJK_KPEAX@Z; SC_DISK::WriteSectors(ulong,unsigned __int64,void *)
0x14001082f  mov     ebx, eax
  ... truncated ...
```
