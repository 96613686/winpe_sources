# SC_GPT::WritePartitionTable(SC_DISK_LAYOUT *,uchar)

- ea: `0x1801c6ef4`
- end: `0x1801c73f5`
- name: `?WritePartitionTable@SC_GPT@@QEAAJPEAVSC_DISK_LAYOUT@@E@Z`
- size: `1281`
- prototype: `__int64 __fastcall(SC_GPT *__hidden this, struct SC_DISK_LAYOUT *, unsigned __int8)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801c402c`
- `0x1801c5104`

## callees

- `0x180006dd4`
- `0x1801c4864`
- `0x1801c4db4`
- `0x1801c522c`
- `0x1801c62a0`
- `0x1801c6ad8`
- `0x1801c6ef4`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1801c70de`
- `RPCRT4!UuidCreate` at `0x1801c71b9`
- `RPCRT4!UuidCreate` at `0x1801c70de`
- `RPCRT4!UuidCreate` at `0x1801c71b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801c73c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801c73c7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801c7056`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801c7056`
- `ntdll!RtlComputeCrc32` at `0x1801c7264`
- `ntdll!RtlComputeCrc32` at `0x1801c727d`
- `ntdll!RtlComputeCrc32` at `0x1801c7320`
- `ntdll!RtlComputeCrc32` at `0x1801c7264`
- `ntdll!RtlComputeCrc32` at `0x1801c727d`
- `ntdll!RtlComputeCrc32` at `0x1801c7320`

## pseudocode

```c
__int64 __fastcall SC_GPT::WritePartitionTable(SC_GPT *this, struct SC_DISK_LAYOUT *a2, char a3)
{
  __int64 v3; // r9
  __int64 v6; // rdi
  unsigned int v7; // ecx
  int Header; // ebx
  unsigned int v9; // edx
  __int64 v10; // r13
  unsigned int v11; // r8d
  unsigned int v12; // r15d
  unsigned int v13; // r14d
  __int64 v14; // r15
  unsigned __int64 v15; // r15
  char *v16; // r14
  __int64 v17; // r11
  char *i; // rbx
  char *v19; // rbp
  int v20; // r11d
  UUID *v21; // rcx
  __int64 v22; // rdx
  signed __int64 v23; // rdx
  __int128 v24; // xmm0
  ULONG v25; // eax
  ULONG v26; // r8d
  ULONG v27; // eax
  unsigned __int64 v28; // r8
  char *v29; // rbx
  __int64 v30; // rcx
  __int64 v31; // rax
  ULONG v32; // r8d
  ULONG v33; // eax
  unsigned __int64 v34; // r8
  int v36; // [rsp+20h] [rbp-58h]
  int v37; // [rsp+24h] [rbp-54h]
  unsigned __int64 v38; // [rsp+28h] [rbp-50h]
  __int64 v39; // [rsp+30h] [rbp-48h]
  SIZE_T v40; // [rsp+38h] [rbp-40h]
  unsigned int v42; // [rsp+98h] [rbp+20h]

  v3 = *(_QWORD *)this;
  v37 = 0;
  v6 = *(_QWORD *)(*(_QWORD *)this + 264LL);
  if ( a3 )
  {
    if ( *(_WORD *)(v6 + 510) == 0xAA55 )
      v37 = *(_DWORD *)(v6 + 440);
    v7 = *((_DWORD *)a2 + 10);
    if ( v7 <= 0x80 )
    {
      v7 = 128;
    }
    else if ( v7 > 0x400 )
    {
      return (unsigned int)-1073741811;
    }
    v36 = 128;
    v9 = -*(_DWORD *)(v3 + 236) & ((v7 << 7) + *(_DWORD *)(v3 + 236) - 1);
    v10 = v9 >> *(_DWORD *)(v3 + 240);
    v11 = v9 >> 7;
    v38 = (unsigned int)(v10 + 2);
  }
  else
  {
    v12 = 2 - ((*(_BYTE *)(v3 + 200) & 1) != 0);
    v13 = 0;
    while ( 1 )
    {
      Header = SC_GPT::ReadHeader(this, v13, (struct GPT_HEADER *)v6);
      if ( Header >= 0 )
        break;
      if ( ++v13 >= v12 )
        return (unsigned int)Header;
    }
    v3 = *(_QWORD *)this;
    v11 = *(_DWORD *)(v6 + 80);
    v38 = *(_QWORD *)(v6 + 40);
    v36 = *(_DWORD *)(v6 + 84);
    v9 = -*(_DWORD *)(*(_QWORD *)this + 236LL) & (v11 * v36 + *(_DWORD *)(*(_QWORD *)this + 236LL) - 1);
    v10 = v9 >> *(_DWORD *)(*(_QWORD *)this + 240LL);
  }
  v42 = v11;
  if ( *((_DWORD *)a2 + 1) > v11 )
    return (unsigned int)-1073741811;
  v14 = *(_QWORD *)(v3 + 248);
  if ( (*(_BYTE *)(v3 + 200) & 1) != 0 )
    v15 = v14 - 1;
  else
    v15 = v14 - (unsigned int)v10 - 2;
  v40 = (2 << *(_DWORD *)(v3 + 240)) + v9;
  v16 = (char *)LocalAlloc(0x40u, v40);
  if ( v16 )
  {
    v17 = 0;
    v39 = 1 << *(_DWORD *)(*(_QWORD *)this + 240LL);
    for ( i = &v16[v39]; (unsigned int)v17 < *((_DWORD *)a2 + 1); v17 = (unsigned int)(v20 + 1) )
    {
      v19 = (char *)a2 + 144 * v17;
      if ( !SC_PART_ENTRY::IsUnused((SC_PART_ENTRY *)(v19 + 48)) )
      {
        v21 = (UUID *)(v19 + 96);
        if ( *((_QWORD *)v19 + 12) == *(_QWORD *)&GUID_NULL.Data1 && *((_QWORD *)v19 + 13) == *(_QWORD *)GUID_NULL.Data4 )
        {
          UuidCreate(v21);
          v21 = (UUID *)(v19 + 96);
        }
        *(_OWORD *)i = *((_OWORD *)v19 + 5);
        *((UUID *)i + 1) = *v21;
        v22 = *((_QWORD *)v19 + 7);
        if ( *(_DWORD *)(*(_QWORD *)this + 236LL) )
          v22 /= (__int64)*(unsigned int *)(*(_QWORD *)this + 236LL);
        *((_QWORD *)i + 4) = v22;
        v23 = *((_QWORD *)v19 + 8) - 1LL + *((_QWORD *)v19 + 7);
        if ( *(_DWORD *)(*(_QWORD *)this + 236LL) )
          v23 /= (__int64)*(unsigned int *)(*(_QWORD *)this + 236LL);
        *((_QWORD *)i + 5) = v23;
        *((_QWORD *)i + 6) = *((_QWORD *)v19 + 14);
        RtlStringCbCopyW((unsigned __int16 *)i + 28, v23, (const unsigned __int16 *)v19 + 60);
        if ( *((_QWORD *)i + 4) < v38 || *((_QWORD *)i + 5) > v15 )
        {
          Header = -1073741811;
          goto LABEL_41;
        }
        i += 128;
      }
    }
    if ( *((_QWORD *)a2 + 1) == *(_QWORD *)&GUID_NULL.Data1 && *((_QWORD *)a2 + 2) == *(_QWORD *)GUID_NULL.Data4 )
      UuidCreate((UUID *)((char *)a2 + 8));
    *((_QWORD *)a2 + 4) = (v15 - v38 + 1) << *(_DWORD *)(*(_QWORD *)this + 240LL);
    *((_DWORD *)a2 + 10) = v42;
    *(_QWORD *)v16 = 0x5452415020494645LL;
    *((_QWORD *)v16 + 5) = v38;
    *((_QWORD *)v16 + 4) = v15 + v10 + 1;
    *((_QWORD *)v16 + 6) = v15;
    *((_DWORD *)v16 + 2) = 0x10000;
    *((_DWORD *)v16 + 3) = 92;
    *((_QWORD *)v16 + 3) = 1;
    v24 = *(_OWORD *)((char *)a2 + 8);
    *((_QWORD *)v16 + 9) = v38 - (unsigned int)v10;
    *((_DWORD *)v16 + 20) = v42;
    *(_OWORD *)(v16 + 56) = v24;
    *((_DWORD *)v16 + 21) = v36;
    v25 = RtlComputeCrc32(0, (PUCHAR)&v16[v39], (_DWORD)v10 << *(_DWORD *)(*(_QWORD *)this + 240LL));
    v26 = *((_DWORD *)v16 + 3);
    *((_DWORD *)v16 + 22) = v25;
    v27 = RtlComputeCrc32(0, (PUCHAR)v16, v26);
    v28 = *((_QWORD *)v16 + 3);
    *((_DWORD *)v16 + 4) = v27;
    Header = SC_DISK::WriteSectors(*(SC_DISK **)this, (int)v10 + 1, v28, v16);
    if ( Header >= 0 )
    {
      if ( (*(_BYTE *)(*(_QWORD *)this + 200LL) & 1) != 0 )
        goto LABEL_39;
      v29 = &v16[v40 - v39];
      *(_OWORD *)v29 = *(_OWORD *)v16;
      *((_OWORD *)v29 + 1) = *((_OWORD *)v16 + 1);
      *((_OWORD *)v29 + 2) = *((_OWORD *)v16 + 2);
      *((_OWORD *)v29 + 3) = *((_OWORD *)v16 + 3);
      *((_OWORD *)v29 + 4) = *((_OWORD *)v16 + 4);
      *(_OWORD *)(v29 + 76) = *(_OWORD *)(v16 + 76);
      v30 = *((_QWORD *)v29 + 4);
      v31 = *((_QWORD *)v29 + 3);
      v32 = *((_DWORD *)v29 + 3);
      *((_QWORD *)v29 + 3) = v30;
      *((_QWORD *)v29 + 9) = v30 - (unsigned int)v10;
      *((_DWORD *)v29 + 4) = 0;
      *((_QWORD *)v29 + 4) = v31;
      v33 = RtlComputeCrc32(0, (PUCHAR)v29, v32);
      v34 = *((_QWORD *)v29 + 9);
      *((_DWORD *)v29 + 4) = v33;
      Header = SC_DISK::WriteSectors(*(SC_DISK **)this, (int)v10 + 1, v34, &v16[v39]);
      if ( Header >= 0 )
      {
LABEL_39:
        *(_DWORD *)(*(_QWORD *)this + 200LL) &= ~2u;
        if ( a3 )
        {
          memset_0((void *)v6, 0, 0x200u);
          *(_DWORD *)(v6 + 440) = v37;
          *(_BYTE *)(v6 + 450) = -18;
          *(_DWORD *)(v6 + 454) = 1;
          *(_DWORD *)(v6 + 458) = -1;
          MBR_ENTRY::ComputeChs((MBR_ENTRY *)(v6 + 446), (struct _DISK_GEOMETRY *)(*(_QWORD *)this + 216LL));
          *(_WORD *)(v6 + 510) = -21931;
          Header = SC_DISK::WriteSectors(*(SC_DISK **)this, 1u, 0, 0);
        }
      }
    }
LABEL_41:
    LocalFree(v16);
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
0x1801c6ef4  mov     [rsp+arg_8], rbx
0x1801c6ef9  mov     [rsp+arg_10], r8b
0x1801c6efe  push    rbp
0x1801c6eff  push    rsi
0x1801c6f00  push    rdi
0x1801c6f01  push    r12
0x1801c6f03  push    r13
0x1801c6f05  push    r14
0x1801c6f07  push    r15
0x1801c6f09  sub     rsp, 40h
0x1801c6f0d  mov     r9, [rcx]
0x1801c6f10  mov     ebp, 2
0x1801c6f15  mov     [rsp+78h+var_54], 0
0x1801c6f1d  mov     r12, rdx
0x1801c6f20  mov     rsi, rcx
0x1801c6f23  mov     ecx, 0AA55h
0x1801c6f28  mov     rdi, [r9+108h]
0x1801c6f2f  lea     edx, [rbp+7Eh]
0x1801c6f32  test    r8b, r8b
0x1801c6f35  jz      short loc_1801C6F9D
0x1801c6f37  cmp     [rdi+1FEh], cx
0x1801c6f3e  jnz     short loc_1801C6F4A
0x1801c6f40  mov     eax, [rdi+1B8h]
0x1801c6f46  mov     [rsp+78h+var_54], eax
0x1801c6f4a  mov     ecx, [r12+28h]
0x1801c6f4f  cmp     ecx, edx
0x1801c6f51  jbe     short loc_1801C6F65
0x1801c6f53  cmp     ecx, 400h
0x1801c6f59  jbe     short loc_1801C6F67
0x1801c6f5b  mov     ebx, 0C000000Dh
0x1801c6f60  jmp     loc_1801C73D3
0x1801c6f65  mov     ecx, edx
0x1801c6f67  mov     eax, [r9+0ECh]
0x1801c6f6e  mov     [rsp+78h+var_58], edx
0x1801c6f72  shl     ecx, 7
0x1801c6f75  lea     edx, [rax-1]
0x1801c6f78  neg     eax
0x1801c6f7a  add     edx, ecx
0x1801c6f7c  mov     ecx, [r9+0F0h]
0x1801c6f83  and     edx, eax
0x1801c6f85  mov     r13d, edx
0x1801c6f88  mov     r8d, edx
0x1801c6f8b  shr     r13d, cl
0x1801c6f8e  shr     r8d, 7
0x1801c6f92  lea     r10d, [r13+2]
0x1801c6f96  mov     [rsp+78h+var_50], r10
0x1801c6f9b  jmp     short loc_1801C700F
0x1801c6f9d  mov     al, [r9+0C8h]
0x1801c6fa4  and     al, 1
0x1801c6fa6  neg     al
0x1801c6fa8  sbb     r15d, r15d
0x1801c6fab  add     r15d, ebp
0x1801c6fae  xor     r14d, r14d
0x1801c6fb1  mov     r8, rdi; struct GPT_HEADER *
0x1801c6fb4  mov     edx, r14d; unsigned int
0x1801c6fb7  mov     rcx, rsi; this
0x1801c6fba  call    ?ReadHeader@SC_GPT@@AEAAJKPEAVGPT_HEADER@@@Z; SC_GPT::ReadHeader(ulong,GPT_HEADER *)
0x1801c6fbf  mov     ebx, eax
0x1801c6fc1  test    eax, eax
0x1801c6fc3  jns     short loc_1801C6FD2
0x1801c6fc5  inc     r14d
0x1801c6fc8  cmp     r14d, r15d
0x1801c6fcb  jb      short loc_1801C6FB1
0x1801c6fcd  jmp     loc_1801C73D3
0x1801c6fd2  mov     r9, [rsi]
0x1801c6fd5  mov     rax, [rdi+28h]
0x1801c6fd9  mov     r11d, [rdi+54h]
0x1801c6fdd  mov     r8d, [rdi+50h]
0x1801c6fe1  mov     ecx, [r9+0ECh]
0x1801c6fe8  mov     [rsp+78h+var_50], rax
0x1801c6fed  mov     eax, r11d
0x1801c6ff0  imul    eax, r8d
0x1801c6ff4  mov     [rsp+78h+var_58], r11d
0x1801c6ff9  lea     edx, [rcx-1]
0x1801c6ffc  neg     ecx
0x1801c6ffe  add     edx, eax
0x1801c7000  and     edx, ecx
0x1801c7002  mov     ecx, [r9+0F0h]
0x1801c7009  mov     r13d, edx
0x1801c700c  shr     r13d, cl
0x1801c700f  mov     [rsp+78h+arg_18], r8d
0x1801c7017  cmp     [r12+4], r8d
0x1801c701c  ja      loc_1801C6F5B
0x1801c7022  test    byte ptr [r9+0C8h], 1
0x1801c702a  mov     r15, [r9+0F8h]
0x1801c7031  jz      short loc_1801C7038
0x1801c7033  dec     r15
0x1801c7036  jmp     short loc_1801C7041
0x1801c7038  mov     ebx, r13d
0x1801c703b  sub     r15, rbx
0x1801c703e  sub     r15, rbp
0x1801c7041  mov     ecx, [r9+0F0h]
0x1801c7048  shl     ebp, cl
0x1801c704a  mov     ecx, 40h ; '@'; uFlags
0x1801c704f  add     edx, ebp; uBytes
0x1801c7051  mov     [rsp+78h+var_40], rdx
0x1801c7056  call    cs:__imp_LocalAlloc
0x1801c705d  nop     dword ptr [rax+rax+00h]
0x1801c7062  mov     r14, rax
0x1801c7065  test    rax, rax
0x1801c7068  jnz     short loc_1801C7074
0x1801c706a  mov     ebx, 0C000009Ah
0x1801c706f  jmp     loc_1801C73D3
0x1801c7074  mov     rcx, [rsi]
0x1801c7077  mov     eax, 1
0x1801c707c  xor     r11d, r11d
0x1801c707f  mov     [rsp+78h+arg_0], r11d
0x1801c7087  mov     ecx, [rcx+0F0h]
0x1801c708d  shl     eax, cl
0x1801c708f  cdqe
0x1801c7091  mov     [rsp+78h+var_48], rax
0x1801c7096  lea     rbx, [r14+rax]
0x1801c709a  cmp     [r12+4], r11d
0x1801c709f  jbe     loc_1801C7198
0x1801c70a5  lea     rbp, [r11+r11*8]
0x1801c70a9  shl     rbp, 4
0x1801c70ad  add     rbp, r12
0x1801c70b0  lea     rcx, [rbp+30h]; this
0x1801c70b4  call    ?IsUnused@SC_PART_ENTRY@@QEAAEXZ; SC_PART_ENTRY::IsUnused(void)
0x1801c70b9  test    al, al
0x1801c70bb  jnz     loc_1801C7182
0x1801c70c1  lea     rcx, [rbp+60h]; Uuid
0x1801c70c5  mov     rax, [rcx]
0x1801c70c8  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1801c70cf  jnz     short loc_1801C70F6
0x1801c70d1  mov     rax, [rcx+8]
0x1801c70d5  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1801c70dc  jnz     short loc_1801C70F6
0x1801c70de  call    cs:__imp_UuidCreate
0x1801c70e5  nop     dword ptr [rax+rax+00h]
0x1801c70ea  mov     r11d, [rsp+78h+arg_0]
0x1801c70f2  lea     rcx, [rbp+60h]
0x1801c70f6  movups  xmm0, xmmword ptr [rbp+50h]
0x1801c70fa  movdqu  xmmword ptr [rbx], xmm0
0x1801c70fe  movups  xmm1, xmmword ptr [rcx]
0x1801c7101  movdqu  xmmword ptr [rbx+10h], xmm1
0x1801c7106  mov     rax, [rsi]
0x1801c7109  mov     rdx, [rbp+38h]
0x1801c710d  mov     ecx, [rax+0ECh]
0x1801c7113  test    ecx, ecx
0x1801c7115  jz      short loc_1801C7122
0x1801c7117  mov     rax, rdx
0x1801c711a  cqo
0x1801c711c  idiv    rcx
0x1801c711f  mov     rdx, rax
0x1801c7122  mov     [rbx+20h], rdx
0x1801c7126  mov     rcx, [rbp+40h]
0x1801c712a  mov     rax, [rsi]
0x1801c712d  dec     rcx
0x1801c7130  mov     rdx, [rbp+38h]
0x1801c7134  add     rdx, rcx
0x1801c7137  mov     ecx, [rax+0ECh]
0x1801c713d  test    ecx, ecx
0x1801c713f  jz      short loc_1801C714C
0x1801c7141  mov     rax, rdx
0x1801c7144  cqo
0x1801c7146  idiv    rcx
0x1801c7149  mov     rdx, rax; unsigned __int64
0x1801c714c  mov     [rbx+28h], rdx
0x1801c7150  lea     r8, [rbp+78h]; unsigned __int16 *
0x1801c7154  mov     rax, [rbp+70h]
0x1801c7158  lea     rcx, [rbx+38h]; unsigned __int16 *
0x1801c715c  mov     [rbx+30h], rax
0x1801c7160  call    ?RtlStringCbCopyW@@YAJPEAG_KPEBG@Z; RtlStringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1801c7165  mov     rax, [rsp+78h+var_50]
0x1801c716a  cmp     [rbx+20h], rax
0x1801c716e  jb      loc_1801C73EE
0x1801c7174  cmp     [rbx+28h], r15
0x1801c7178  ja      loc_1801C73EE
0x1801c717e  sub     rbx, 0FFFFFFFFFFFFFF80h
0x1801c7182  inc     r11d
0x1801c7185  mov     [rsp+78h+arg_0], r11d
0x1801c718d  cmp     r11d, [r12+4]
0x1801c7192  jb      loc_1801C70A5
0x1801c7198  lea     rbx, [r12+8]
0x1801c719d  mov     rax, [rbx]
0x1801c71a0  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1801c71a7  jnz     short loc_1801C71C5
0x1801c71a9  mov     rax, [rbx+8]
0x1801c71ad  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1801c71b4  jnz     short loc_1801C71C5
0x1801c71b6  mov     rcx, rbx; Uuid
0x1801c71b9  call    cs:__imp_UuidCreate
0x1801c71c0  nop     dword ptr [rax+rax+00h]
0x1801c71c5  mov     rcx, [rsi]
0x1801c71c8  mov     rax, r15
0x1801c71cb  mov     rdx, [rsp+78h+var_50]
0x1801c71d0  mov     r8d, r13d
0x1801c71d3  sub     rax, rdx
0x1801c71d6  mov     ebp, r13d
0x1801c71d9  inc     rax
0x1801c71dc  mov     ecx, [rcx+0F0h]
0x1801c71e2  shl     rax, cl
0x1801c71e5  mov     ecx, [rsp+78h+arg_18]
0x1801c71ec  mov     [r12+20h], rax
0x1801c71f1  mov     rax, 5452415020494645h
0x1801c71fb  mov     [r12+28h], ecx
0x1801c7200  mov     r12, [rsp+78h+var_48]
0x1801c7205  mov     [r14], rax
0x1801c7208  lea     rax, [r13+1]
0x1801c720c  mov     [r14+28h], rdx
0x1801c7210  add     rax, r15
0x1801c7213  mov     [r14+20h], rax
0x1801c7217  sub     rdx, rbp
0x1801c721a  mov     eax, [rsp+78h+var_58]
0x1801c721e  mov     [r14+30h], r15
0x1801c7222  lea     r15, [r14+r12]
0x1801c7226  mov     dword ptr [r14+8], 10000h
0x1801c722e  mov     dword ptr [r14+0Ch], 5Ch ; '\'
0x1801c7236  mov     qword ptr [r14+18h], 1
0x1801c723e  movups  xmm0, xmmword ptr [rbx]
0x1801c7241  mov     [r14+48h], rdx
0x1801c7245  mov     rdx, r15; Buffer
0x1801c7248  mov     [r14+50h], ecx
0x1801c724c  movdqu  xmmword ptr [r14+38h], xmm0
0x1801c7252  mov     [r14+54h], eax
0x1801c7256  mov     rcx, [rsi]
0x1801c7259  mov     ecx, [rcx+0F0h]
0x1801c725f  shl     r8d, cl; Length
0x1801c7262  xor     ecx, ecx; InitialCrc
0x1801c7264  call    cs:__imp_RtlComputeCrc32
0x1801c726b  nop     dword ptr [rax+rax+00h]
0x1801c7270  mov     r8d, [r14+0Ch]; Length
0x1801c7274  mov     rdx, r14; Buffer
0x1801c7277  xor     ecx, ecx; InitialCrc
0x1801c7279  mov     [r14+58h], eax
0x1801c727d  call    cs:__imp_RtlComputeCrc32
0x1801c7284  nop     dword ptr [rax+rax+00h]
0x1801c7289  mov     r8, [r14+18h]; unsigned __int64
0x1801c728d  lea     edx, [r13+1]; unsigned int
0x1801c7291  mov     [r14+10h], eax
0x1801c7295  mov     r9, r14; void *
0x1801c7298  mov     rcx, [rsi]; this
0x1801c729b  call    ?WriteSectors@SC_DISK@@QEAAJK_KPEAX@Z; SC_DISK::WriteSectors(ulong,unsigned __int64,void *)
0x1801c72a0  mov     ebx, eax
0x1801c72a2  test    eax, eax
0x1801c72a4  js      loc_1801C73C4
0x1801c72aa  mov     rax, [rsi]
0x1801c72ad  test    byte ptr [rax+0C8h], 1
0x1801c72b4  jnz     loc_1801C7348
0x1801c72ba  movups  xmm0, xmmword ptr [r14]
0x1801c72be  mov     rbx, [rsp+78h+var_40]
0x1801c72c3  sub     rbx, r12
0x1801c72c6  add     rbx, r14
0x1801c72c9  mov     rdx, rbx; Buffer
0x1801c72cc  movups  xmmword ptr [rbx], xmm0
0x1801c72cf  movups  xmm1, xmmword ptr [r14+10h]
0x1801c72d4  movups  xmmword ptr [rbx+10h], xmm1
0x1801c72d8  movups  xmm0, xmmword ptr [r14+20h]
0x1801c72dd  movups  xmmword ptr [rbx+20h], xmm0
0x1801c72e1  movups  xmm1, xmmword ptr [r14+30h]
0x1801c72e6  movups  xmmword ptr [rbx+30h], xmm1
0x1801c72ea  movups  xmm0, xmmword ptr [r14+40h]
0x1801c72ef  movups  xmmword ptr [rbx+40h], xmm0
0x1801c72f3  movups  xmm1, xmmword ptr [r14+4Ch]
0x1801c72f8  movups  xmmword ptr [rbx+4Ch], xmm1
0x1801c72fc  mov     rcx, [rbx+20h]
0x1801c7300  mov     rax, [rbx+18h]
0x1801c7304  mov     r8d, [rbx+0Ch]; Length
0x1801c7308  mov     [rbx+18h], rcx
0x1801c730c  sub     rcx, rbp
0x1801c730f  mov     [rbx+48h], rcx
0x1801c7313  xor     ecx, ecx; InitialCrc
0x1801c7315  mov     dword ptr [rbx+10h], 0
0x1801c731c  mov     [rbx+20h], rax
0x1801c7320  call    cs:__imp_RtlComputeCrc32
0x1801c7327  nop     dword ptr [rax+rax+00h]
0x1801c732c  mov     r8, [rbx+48h]; unsigned __int64
0x1801c7330  lea     edx, [r13+1]; unsigned int
0x1801c7334  mov     [rbx+10h], eax
0x1801c7337  mov     r9, r15; void *
0x1801c733a  mov     rcx, [rsi]; this
0x1801c733d  call    ?WriteSectors@SC_DISK@@QEAAJK_KPEAX@Z; SC_DISK::WriteSectors(ulong,unsigned __int64,void *)
0x1801c7342  mov     ebx, eax
0x1801c7344  test    eax, eax
0x1801c7346  js      short loc_1801C73C4
0x1801c7348  mov     rax, [rsi]
0x1801c734b  and     dword ptr [rax+0C8h], 0FFFFFFFDh
0x1801c7352  cmp     [rsp+78h+arg_10], 0
0x1801c735a  jz      short loc_1801C73C4
0x1801c735c  xor     edx, edx; Val
0x1801c735e  mov     r8d, 200h; Size
0x1801c7364  mov     rcx, rdi; void *
0x1801c7367  call    memset_0
0x1801c736c  mov     eax, [rsp+78h+var_54]
0x1801c7370  lea     rcx, [rdi+1BEh]; this
0x1801c7377  mov     [rdi+1B8h], eax
0x1801c737d  mov     byte ptr [rdi+1C2h], 0EEh
0x1801c7384  mov     dword ptr [rdi+1C6h], 1
0x1801c738e  mov     dword ptr [rdi+1CAh], 0FFFFFFFFh
0x1801c7398  mov     rdx, [rsi]
0x1801c739b  add     rdx, 0D8h; struct _DISK_GEOMETRY *
0x1801c73a2  call    ?ComputeChs@MBR_ENTRY@@QEAAXPEAU_DISK_GEOMETRY@@@Z; MBR_ENTRY::ComputeChs(_DISK_GEOMETRY *)
0x1801c73a7  xor     r9d, r9d; void *
0x1801c73aa  mov     word ptr [rdi+1FEh], 0AA55h
0x1801c73b3  mov     rcx, [rsi]; this
0x1801c73b6  xor     r8d, r8d; unsigned __int64
0x1801c73b9  lea     edx, [r9+1]; unsigned int
0x1801c73bd  call    ?WriteSectors@SC_DISK@@QEAAJK_KPEAX@Z; SC_DISK::WriteSectors(ulong,unsigned __int64,void *)
0x1801c73c2  mov     ebx, eax
  ... truncated ...
```
