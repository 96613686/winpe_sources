# FveReadWriteDeviceReconfig

- ea: `0x1400bda80`
- end: `0x1400bde00`
- name: `FveReadWriteDeviceReconfig`
- size: `896`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x140027db8`

## callees

- `0x14000ff74`
- `0x140010008`
- `0x140023560`
- `0x1400bda80`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400bdddf`
- `ntoskrnl!KeReleaseMutex` at `0x1400bdddf`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400bdbbb`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400bdbbb`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400bdbea`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400bddb6`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400bdbea`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400bddb6`
- `ntoskrnl!MmSizeOfMdl` at `0x1400bdb7a`
- `ntoskrnl!MmSizeOfMdl` at `0x1400bdb7a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bdabd`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bdabd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bddca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bddca`

## pseudocode

```c
LONG __fastcall FveReadWriteDeviceReconfig(
        __int64 a1,
        size_t *a2,
        PNPAGED_LOOKASIDE_LIST *a3,
        __int64 *a4,
        __int64 *a5,
        __int64 *a6)
{
  __int64 v6; // r14
  struct _NPAGED_LOOKASIDE_LIST *v11; // r15
  __int64 v12; // rbp
  bool v13; // bl
  __int64 v14; // rax
  __int128 v15; // xmm0
  __int64 v16; // rax
  unsigned int v17; // ecx
  int v18; // eax
  struct _NPAGED_LOOKASIDE_LIST *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // r8
  __int64 v23; // r8

  v6 = *(_QWORD *)(a1 + 8);
  v11 = 0;
  KeWaitForSingleObject((PVOID)(v6 + 9856), Executive, 0, 0, 0);
  v12 = a1 + 1592;
  v13 = memcmp((const void *)(a1 + 1592), a2, a2[52]) != 0;
  v14 = 3;
  do
  {
    v15 = *(_OWORD *)a2;
    a2 += 16;
    *(_OWORD *)v12 = v15;
    v12 += 128;
    *(_OWORD *)(v12 - 112) = *((_OWORD *)a2 - 7);
    *(_OWORD *)(v12 - 96) = *((_OWORD *)a2 - 6);
    *(_OWORD *)(v12 - 80) = *((_OWORD *)a2 - 5);
    *(_OWORD *)(v12 - 64) = *((_OWORD *)a2 - 4);
    *(_OWORD *)(v12 - 48) = *((_OWORD *)a2 - 3);
    *(_OWORD *)(v12 - 32) = *((_OWORD *)a2 - 2);
    *(_OWORD *)(v12 - 16) = *((_OWORD *)a2 - 1);
    --v14;
  }
  while ( v14 );
  *(_OWORD *)v12 = *(_OWORD *)a2;
  *(_OWORD *)(v12 + 16) = *((_OWORD *)a2 + 1);
  *(_QWORD *)(v12 + 32) = a2[4];
  v16 = *(unsigned int *)(v6 + 884);
  v17 = *(_DWORD *)(a1 + 4 * v16 + 1592);
  if ( v17 == *(_DWORD *)(v6 + 4 * v16 + 936) )
  {
    v21 = *(_QWORD *)(v6 + 9256);
    if ( *(_QWORD *)(a1 + 2016) != v21 )
      v11 = (struct _NPAGED_LOOKASIDE_LIST *)_InterlockedExchange64((volatile __int64 *)(a1 + 2016), v21);
    v20 = *(_QWORD *)(v6 + 9264);
  }
  else
  {
    v18 = MmSizeOfMdl(0, v17);
    ExInitializeNPagedLookasideList(
      *a3,
      0,
      0,
      0x200u,
      (unsigned int)(v18 + *(_DWORD *)(a1 + 4LL * *(unsigned int *)(v6 + 884) + 1592) + 64),
      0x70455646u,
      0);
    v19 = (struct _NPAGED_LOOKASIDE_LIST *)_InterlockedExchange64((volatile __int64 *)(a1 + 2016), (__int64)*a3);
    *a3 = v19;
    if ( v19 == *(struct _NPAGED_LOOKASIDE_LIST **)(v6 + 9256) )
    {
      *a3 = 0;
    }
    else if ( v19 )
    {
      ExDeleteNPagedLookasideList(v19);
    }
    v20 = 0;
  }
  *(_QWORD *)(a1 + 2024) = v20;
  *a4 = _InterlockedExchange64((volatile __int64 *)(a1 + 2056), *a4);
  *a5 = _InterlockedExchange64((volatile __int64 *)(a1 + 2104), *a5);
  *a6 = _InterlockedExchange64((volatile __int64 *)(a1 + 2112), *a6);
  if ( v13 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v22 = *(unsigned int *)(v6 + 884);
      WPP_SF_qLDDDDDDDDDDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        60,
        v22,
        a1,
        *(_DWORD *)(v6 + 884),
        *(_DWORD *)(a1 + 4 * v22 + 1592),
        *(_DWORD *)(a1 + 4 * v22 + 1604),
        *(_DWORD *)(a1 + 4 * v22 + 1616),
        *(_DWORD *)(a1 + 4 * v22 + 1640),
        *(_DWORD *)(a1 + 4 * v22 + 1652),
        *(_DWORD *)(a1 + 4 * v22 + 1676),
        *(_DWORD *)(a1 + 4 * v22 + 1688),
        *(_DWORD *)(a1 + 4 * v22 + 1700),
        *(_DWORD *)(a1 + 4 * v22 + 1712),
        *(_DWORD *)(a1 + 4 * v22 + 1724),
        *(_DWORD *)(a1 + 4 * v22 + 1736),
        *(_DWORD *)(a1 + 4 * v22 + 1748));
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v23 = *(unsigned int *)(v6 + 884);
      WPP_SF_qLDDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        61,
        v23,
        a1,
        *(_DWORD *)(v6 + 884),
        *(_DWORD *)(a1 + 4 * v23 + 1760),
        *(_DWORD *)(a1 + 4 * v23 + 1772),
        *(_DWORD *)(v6 + 4 * v23 + 972),
        *(_DWORD *)(v6 + 4 * v23 + 1008));
    }
  }
  if ( v11 && v11 != *(struct _NPAGED_LOOKASIDE_LIST **)(v6 + 9256) )
  {
    ExDeleteNPagedLookasideList(v11);
    ExFreePoolWithTag(v11, 0x30455646u);
  }
  return KeReleaseMutex((PRKMUTEX)(v6 + 9856), 0);
}

```

## disassembly

```asm
0x1400bda80  push    rbx
0x1400bda82  push    rbp
0x1400bda83  push    rsi
0x1400bda84  push    rdi
0x1400bda85  push    r12
0x1400bda87  push    r13
0x1400bda89  push    r14
0x1400bda8b  push    r15
0x1400bda8d  sub     rsp, 98h
0x1400bda94  mov     r14, [rcx+8]
0x1400bda98  mov     r13, r9
0x1400bda9b  mov     r12, r8
0x1400bda9e  mov     rsi, rdx
0x1400bdaa1  mov     rdi, rcx
0x1400bdaa4  xor     r15d, r15d
0x1400bdaa7  xor     r9d, r9d; Alertable
0x1400bdaaa  mov     [rsp+0D8h+Timeout], r15; Timeout
0x1400bdaaf  lea     rcx, [r14+2680h]; Object
0x1400bdab6  xor     r8d, r8d; WaitMode
0x1400bdab9  xor     edx, edx; WaitReason
0x1400bdabb  xor     bl, bl
0x1400bdabd  call    cs:__imp_KeWaitForSingleObject
0x1400bdac4  nop     dword ptr [rax+rax+00h]
0x1400bdac9  mov     r8, [rsi+1A0h]; Size
0x1400bdad0  lea     rbp, [rdi+638h]
0x1400bdad7  mov     rcx, rbp; Buf1
0x1400bdada  mov     rdx, rsi; Buf2
0x1400bdadd  call    memcmp
0x1400bdae2  test    eax, eax
0x1400bdae4  movzx   ebx, bl
0x1400bdae7  lea     ecx, [r15+1]
0x1400bdaeb  cmovnz  ebx, ecx
0x1400bdaee  lea     eax, [rcx+2]
0x1400bdaf1  movups  xmm0, xmmword ptr [rsi]
0x1400bdaf4  lea     rsi, [rsi+80h]
0x1400bdafb  movups  xmmword ptr [rbp+0], xmm0
0x1400bdaff  lea     rbp, [rbp+80h]
0x1400bdb06  movups  xmm1, xmmword ptr [rsi-70h]
0x1400bdb0a  movups  xmmword ptr [rbp-70h], xmm1
0x1400bdb0e  movups  xmm0, xmmword ptr [rsi-60h]
0x1400bdb12  movups  xmmword ptr [rbp-60h], xmm0
0x1400bdb16  movups  xmm1, xmmword ptr [rsi-50h]
0x1400bdb1a  movups  xmmword ptr [rbp-50h], xmm1
0x1400bdb1e  movups  xmm0, xmmword ptr [rsi-40h]
0x1400bdb22  movups  xmmword ptr [rbp-40h], xmm0
0x1400bdb26  movups  xmm1, xmmword ptr [rsi-30h]
0x1400bdb2a  movups  xmmword ptr [rbp-30h], xmm1
0x1400bdb2e  movups  xmm0, xmmword ptr [rsi-20h]
0x1400bdb32  movups  xmmword ptr [rbp-20h], xmm0
0x1400bdb36  movups  xmm1, xmmword ptr [rsi-10h]
0x1400bdb3a  movups  xmmword ptr [rbp-10h], xmm1
0x1400bdb3e  sub     rax, rcx
0x1400bdb41  jnz     short loc_1400BDAF1
0x1400bdb43  movups  xmm0, xmmword ptr [rsi]
0x1400bdb46  movups  xmmword ptr [rbp+0], xmm0
0x1400bdb4a  movups  xmm1, xmmword ptr [rsi+10h]
0x1400bdb4e  movups  xmmword ptr [rbp+10h], xmm1
0x1400bdb52  mov     rax, [rsi+20h]
0x1400bdb56  mov     [rbp+20h], rax
0x1400bdb5a  mov     eax, [r14+374h]
0x1400bdb61  mov     ecx, [rdi+rax*4+638h]
0x1400bdb68  cmp     ecx, [r14+rax*4+3A8h]
0x1400bdb70  jz      loc_1400BDBFA
0x1400bdb76  mov     edx, ecx; Length
0x1400bdb78  xor     ecx, ecx; Base
0x1400bdb7a  call    cs:__imp_MmSizeOfMdl
0x1400bdb81  nop     dword ptr [rax+rax+00h]
0x1400bdb86  mov     ecx, [r14+374h]
0x1400bdb8d  xor     r8d, r8d; Free
0x1400bdb90  mov     [rsp+0D8h+Depth], r8w; Depth
0x1400bdb96  mov     r9d, 200h; Flags
0x1400bdb9c  mov     [rsp+0D8h+Tag], 70455646h; Tag
0x1400bdba4  xor     edx, edx; Allocate
0x1400bdba6  mov     ecx, [rdi+rcx*4+638h]
0x1400bdbad  add     ecx, 40h ; '@'
0x1400bdbb0  add     ecx, eax
0x1400bdbb2  mov     [rsp+0D8h+Timeout], rcx; Size
0x1400bdbb7  mov     rcx, [r12]; Lookaside
0x1400bdbbb  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400bdbc2  nop     dword ptr [rax+rax+00h]
0x1400bdbc7  mov     rcx, [r12]
0x1400bdbcb  xchg    rcx, [rdi+7E0h]; Lookaside
0x1400bdbd2  mov     [r12], rcx
0x1400bdbd6  cmp     rcx, [r14+2428h]
0x1400bdbdd  jnz     short loc_1400BDBE5
0x1400bdbdf  mov     [r12], r15
0x1400bdbe3  jmp     short loc_1400BDBF6
0x1400bdbe5  test    rcx, rcx
0x1400bdbe8  jz      short loc_1400BDBF6
0x1400bdbea  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400bdbf1  nop     dword ptr [rax+rax+00h]
0x1400bdbf6  xor     eax, eax
0x1400bdbf8  jmp     short loc_1400BDC1B
0x1400bdbfa  mov     rax, [r14+2428h]
0x1400bdc01  cmp     [rdi+7E0h], rax
0x1400bdc08  jz      short loc_1400BDC14
0x1400bdc0a  mov     r15, rax
0x1400bdc0d  xchg    r15, [rdi+7E0h]
0x1400bdc14  mov     rax, [r14+2430h]
0x1400bdc1b  mov     rcx, [rsp+0D8h+arg_20]
0x1400bdc23  mov     [rdi+7E8h], rax
0x1400bdc2a  mov     rax, [r13+0]
0x1400bdc2e  xchg    rax, [rdi+808h]
0x1400bdc35  mov     [r13+0], rax
0x1400bdc39  mov     rax, [rcx]
0x1400bdc3c  xchg    rax, [rdi+838h]
0x1400bdc43  mov     [rcx], rax
0x1400bdc46  mov     rcx, [rsp+0D8h+arg_28]
0x1400bdc4e  mov     rax, [rcx]
0x1400bdc51  xchg    rax, [rdi+840h]
0x1400bdc58  mov     [rcx], rax
0x1400bdc5b  test    bl, bl
0x1400bdc5d  jz      loc_1400BDDA5
0x1400bdc63  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bdc6a  lea     rbx, WPP_GLOBAL_Control
0x1400bdc71  cmp     rcx, rbx
0x1400bdc74  jz      loc_1400BDDA5
0x1400bdc7a  mov     eax, [rcx+2Ch]
0x1400bdc7d  test    al, al
0x1400bdc7f  jns     loc_1400BDD3F
0x1400bdc85  cmp     byte ptr [rcx+29h], 4
0x1400bdc89  jb      loc_1400BDD3F
0x1400bdc8f  mov     r8d, [r14+374h]
0x1400bdc96  mov     edx, 3Ch ; '<'
0x1400bdc9b  mov     rcx, [rcx+18h]
0x1400bdc9f  mov     r9, rdi
0x1400bdca2  mov     eax, [rdi+r8*4+6D4h]
0x1400bdcaa  mov     [rsp+0D8h+var_58], eax
0x1400bdcb1  mov     eax, [rdi+r8*4+6C8h]
0x1400bdcb9  mov     [rsp+0D8h+var_60], eax
0x1400bdcbd  mov     eax, [rdi+r8*4+6BCh]
0x1400bdcc5  mov     [rsp+0D8h+var_68], eax
0x1400bdcc9  mov     eax, [rdi+r8*4+6B0h]
0x1400bdcd1  mov     [rsp+0D8h+var_70], eax
0x1400bdcd5  mov     eax, [rdi+r8*4+6A4h]
0x1400bdcdd  mov     [rsp+0D8h+var_78], eax
0x1400bdce1  mov     eax, [rdi+r8*4+698h]
0x1400bdce9  mov     [rsp+0D8h+var_80], eax
0x1400bdced  mov     eax, [rdi+r8*4+68Ch]
0x1400bdcf5  mov     [rsp+0D8h+var_88], eax
0x1400bdcf9  mov     eax, [rdi+r8*4+674h]
0x1400bdd01  mov     [rsp+0D8h+var_90], eax
0x1400bdd05  mov     eax, [rdi+r8*4+668h]
0x1400bdd0d  mov     [rsp+0D8h+var_98], eax
0x1400bdd11  mov     eax, [rdi+r8*4+650h]
0x1400bdd19  mov     [rsp+0D8h+var_A0], eax
0x1400bdd1d  mov     eax, [rdi+r8*4+644h]
0x1400bdd25  mov     dword ptr [rsp+0D8h+Depth], eax
0x1400bdd29  mov     eax, [rdi+r8*4+638h]
0x1400bdd31  mov     [rsp+0D8h+Tag], eax
0x1400bdd35  mov     dword ptr [rsp+0D8h+Timeout], r8d
0x1400bdd3a  call    WPP_SF_qLDDDDDDDDDDDD
0x1400bdd3f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bdd46  cmp     rcx, rbx
0x1400bdd49  jz      short loc_1400BDDA5
0x1400bdd4b  mov     eax, [rcx+2Ch]
0x1400bdd4e  test    al, al
0x1400bdd50  jns     short loc_1400BDDA5
0x1400bdd52  cmp     byte ptr [rcx+29h], 4
0x1400bdd56  jb      short loc_1400BDDA5
0x1400bdd58  mov     r8d, [r14+374h]
0x1400bdd5f  mov     edx, 3Dh ; '='
0x1400bdd64  mov     rcx, [rcx+18h]
0x1400bdd68  mov     r9, rdi
0x1400bdd6b  mov     eax, [r14+r8*4+3F0h]
0x1400bdd73  mov     [rsp+0D8h+var_98], eax
0x1400bdd77  mov     eax, [r14+r8*4+3CCh]
0x1400bdd7f  mov     [rsp+0D8h+var_A0], eax
0x1400bdd83  mov     eax, [rdi+r8*4+6ECh]
0x1400bdd8b  mov     dword ptr [rsp+0D8h+Depth], eax
0x1400bdd8f  mov     eax, [rdi+r8*4+6E0h]
0x1400bdd97  mov     [rsp+0D8h+Tag], eax
0x1400bdd9b  mov     dword ptr [rsp+0D8h+Timeout], r8d
0x1400bdda0  call    WPP_SF_qLDDDD
0x1400bdda5  test    r15, r15
0x1400bdda8  jz      short loc_1400BDDD6
0x1400bddaa  cmp     r15, [r14+2428h]
0x1400bddb1  jz      short loc_1400BDDD6
0x1400bddb3  mov     rcx, r15; Lookaside
0x1400bddb6  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400bddbd  nop     dword ptr [rax+rax+00h]
0x1400bddc2  mov     edx, 30455646h; Tag
0x1400bddc7  mov     rcx, r15; P
0x1400bddca  call    cs:__imp_ExFreePoolWithTag
0x1400bddd1  nop     dword ptr [rax+rax+00h]
0x1400bddd6  xor     edx, edx; Wait
0x1400bddd8  lea     rcx, [r14+2680h]; Mutex
0x1400bdddf  call    cs:__imp_KeReleaseMutex
0x1400bdde6  nop     dword ptr [rax+rax+00h]
0x1400bddeb  add     rsp, 98h
0x1400bddf2  pop     r15
0x1400bddf4  pop     r14
0x1400bddf6  pop     r13
0x1400bddf8  pop     r12
0x1400bddfa  pop     rdi
0x1400bddfb  pop     rsi
0x1400bddfc  pop     rbp
0x1400bddfd  pop     rbx
0x1400bddfe  retn
```
