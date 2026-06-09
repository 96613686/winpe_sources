# GuestStatePartition::FormatBlockStorage(void)

- ea: `0x18005ca2c`
- end: `0x18005ce1a`
- name: `?FormatBlockStorage@GuestStatePartition@@AEAAXXZ`
- size: `1006`
- prototype: `void __fastcall(GuestStatePartition *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18005ce60`
- `0x18005cea0`

## callees

- `0x180007438`
- `0x180014114`
- `0x180014380`
- `0x1800156b4`
- `0x18005c340`
- `0x18005ca2c`
- `0x18005f4cc`
- `0x18005f584`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18005ccc7`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18005ccc7`
- `RPCRT4!UuidCreate` at `0x18005cc5b`
- `RPCRT4!UuidCreate` at `0x18005cc9b`
- `RPCRT4!UuidCreate` at `0x18005cc5b`
- `RPCRT4!UuidCreate` at `0x18005cc9b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall GuestStatePartition::FormatBlockStorage(GuestStatePartition *this)
{
  __int64 v2; // r15
  __int64 v3; // rdi
  __int64 v4; // rsi
  __int64 v5; // rbx
  __int64 v6; // rbx
  __int64 v7; // rax
  char v8; // dl
  __int64 v9; // rax
  char v10; // dl
  __int64 v11; // r12
  unsigned int v12; // esi
  int v13; // eax
  unsigned int v14; // edi
  __int64 v15; // r13
  unsigned __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // r13
  unsigned __int64 v19; // r15
  unsigned __int64 v20; // rbx
  __int64 v21; // rdi
  size_t v22; // rax
  size_t v23; // rbx
  __int64 v24; // rdi
  __int64 v25; // rbx
  unsigned int v26; // r8d
  unsigned int v27; // r8d
  __int64 i; // r9
  __int64 v29; // rbx
  __int64 v30; // rcx
  __int64 j; // r8
  _BYTE v32[4]; // [rsp+40h] [rbp-29h] BYREF
  _DWORD v33[5]; // [rsp+44h] [rbp-25h] BYREF
  __int64 v34; // [rsp+58h] [rbp-11h]
  __int64 v35; // [rsp+60h] [rbp-9h] BYREF
  UUID Uuid; // [rsp+70h] [rbp+7h] BYREF

  v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 96LL))(*((_QWORD *)this + 1));
  v3 = *((unsigned int *)this + 8);
  v4 = v2 * v3;
  *(_OWORD *)&v33[1] = 0;
  v34 = 0;
  if ( v3 )
  {
    std::vector<unsigned char>::_Buy_nonzero(&v33[1], (unsigned int)v3);
    v5 = *(_QWORD *)&v33[1];
    memset_0(*(void **)&v33[1], 0, (unsigned int)v3);
    *(_QWORD *)&v33[3] = v3 + v5;
    v35 = 0;
    std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&v35);
  }
  v6 = *(_QWORD *)&v33[1];
  *(_BYTE *)(*(_QWORD *)&v33[1] + 446LL) = 0;
  v7 = DiskStructs::Utilities::ChsAddressFromLba(v33, 1, v4);
  v8 = *(_BYTE *)(v7 + 2);
  *(_WORD *)(v6 + 447) = *(_WORD *)v7;
  *(_BYTE *)(v6 + 449) = v8;
  *(_BYTE *)(v6 + 450) = -18;
  *(_DWORD *)(v6 + 454) = 1;
  v9 = DiskStructs::Utilities::ChsAddressFromLba(v33, v2, v4);
  v10 = *(_BYTE *)(v9 + 2);
  *(_WORD *)(v6 + 451) = *(_WORD *)v9;
  *(_BYTE *)(v6 + 453) = v10;
  v11 = v2 - 1;
  v12 = -1;
  v13 = v2 - 1;
  if ( (unsigned __int64)(v2 - 1) >= 0xFFFFFFFF )
    v13 = -1;
  *(_DWORD *)(v6 + 458) = v13;
  *(_WORD *)(v6 + 510) = -21931;
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int, _QWORD))(**((_QWORD **)this + 1) + 128LL))(
    *((_QWORD *)this + 1),
    *(_QWORD *)&v33[1],
    *((unsigned int *)this + 8),
    0,
    1,
    0);
  memset_0(*(void **)&v33[1], 0, *(_QWORD *)&v33[3] - *(_QWORD *)&v33[1]);
  v14 = *((_DWORD *)this + 8);
  v33[0] = -v14 & (v14 + 0x3FFF);
  v15 = v33[0] / v14;
  v35 = v15;
  v16 = v2 - v15 - 1;
  v17 = (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 112LL))(
          *((_QWORD *)this + 1),
          v33[0] % v14)
      / v14;
  v18 = ~(v17 - 1) & ((unsigned int)v17 + v15 + 1);
  v19 = v16 - v16 % (unsigned int)v17 - 1;
  v32[0] = 0;
  v20 = (unsigned int)(*((_DWORD *)this + 8) + v33[0]);
  v21 = *(_QWORD *)&v33[3];
  if ( v20 < *(_QWORD *)&v33[3] - *(_QWORD *)&v33[1] )
  {
    v22 = v20 + *(_QWORD *)&v33[1];
LABEL_11:
    *(_QWORD *)&v33[3] = v22;
    goto LABEL_12;
  }
  if ( v20 > *(_QWORD *)&v33[3] - *(_QWORD *)&v33[1] )
  {
    if ( v20 <= v34 - *(_QWORD *)&v33[1] )
    {
      v23 = v20 - (*(_QWORD *)&v33[3] - *(_QWORD *)&v33[1]);
      memset_0(*(void **)&v33[3], 0, v23);
      v22 = v23 + v21;
      goto LABEL_11;
    }
    std::vector<unsigned char>::_Resize_reallocate<unsigned char>(
      &v33[1],
      (unsigned int)(*((_DWORD *)this + 8) + v33[0]),
      v32);
  }
LABEL_12:
  v24 = *(_QWORD *)&v33[1];
  **(_QWORD **)&v33[1] = 0x5452415020494645LL;
  *(_DWORD *)(v24 + 8) = 0x10000;
  *(_DWORD *)(v24 + 12) = 92;
  *(_QWORD *)(v24 + 24) = 1;
  *(_QWORD *)(v24 + 32) = v11;
  *(_QWORD *)(v24 + 40) = v18;
  *(_QWORD *)(v24 + 48) = v19;
  Uuid = 0;
  UuidCreate(&Uuid);
  *(UUID *)(v24 + 56) = Uuid;
  *(_QWORD *)(v24 + 72) = 2;
  *(_DWORD *)(v24 + 80) = 128;
  *(_DWORD *)(v24 + 84) = 128;
  v25 = *(_QWORD *)&v33[1] + *((unsigned int *)this + 8);
  *(GUID *)v25 = GPT_PARTITION_TYPE_GUEST_STATE;
  Uuid = 0;
  UuidCreate(&Uuid);
  *(UUID *)(v25 + 16) = Uuid;
  *(_QWORD *)(v25 + 32) = v18;
  *(_QWORD *)(v25 + 40) = v19;
  _o_wcsncpy_s(v25 + 56, 36, L"Guest Runtime State Partition", 30);
  *(_DWORD *)(v24 + 88) = DiskStructs::Utilities::ComputeGptChecksum(
                            (DiskStructs::Utilities *)v25,
                            (const void *)v33[0],
                            v26);
  v27 = -1;
  for ( i = 0; i != 92; ++i )
    v27 = *((_DWORD *)qword_1800B8FA0 + ((unsigned __int8)v27 ^ (unsigned __int64)*(unsigned __int8 *)(v24 + i)))
        ^ (v27 >> 8);
  *(_DWORD *)(v24 + 16) = ~v27;
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, _DWORD, _QWORD))(**((_QWORD **)this + 1) + 128LL))(
    *((_QWORD *)this + 1),
    *(_QWORD *)&v33[1],
    (unsigned int)(*((_DWORD *)this + 8) + v33[0]),
    1,
    v35 + 1,
    0);
  v29 = v11 - v35;
  v30 = *(_QWORD *)(v24 + 24);
  *(_QWORD *)(v24 + 24) = *(_QWORD *)(v24 + 32);
  *(_QWORD *)(v24 + 32) = v30;
  *(_QWORD *)(v24 + 72) = v29;
  for ( j = 0; j != 92; ++j )
    v12 = *((_DWORD *)qword_1800B8FA0 + ((unsigned __int8)v12 ^ (unsigned __int64)*(unsigned __int8 *)(v24 + j)))
        ^ (v12 >> 8);
  *(_DWORD *)(v24 + 16) = ~v12;
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, int, _QWORD))(**((_QWORD **)this + 1) + 128LL))(
    *((_QWORD *)this + 1),
    *(_QWORD *)&v33[1],
    *((unsigned int *)this + 8),
    v11,
    1,
    0);
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, _DWORD, _QWORD))(**((_QWORD **)this + 1) + 128LL))(
    *((_QWORD *)this + 1),
    *(_QWORD *)&v33[1] + *((unsigned int *)this + 8),
    v33[0],
    v29,
    v35,
    0);
  *((_QWORD *)this + 2) = v18;
  *((_QWORD *)this + 3) = v19 - v18 + 1;
  std::vector<unsigned char>::~vector<unsigned char>(&v33[1]);
}

```

## disassembly

```asm
0x18005ca2c  push    rbp
0x18005ca2e  push    rbx
0x18005ca2f  push    rsi
0x18005ca30  push    rdi
0x18005ca31  push    r12
0x18005ca33  push    r13
0x18005ca35  push    r14
0x18005ca37  push    r15
0x18005ca39  lea     rbp, [rsp-1Fh]
0x18005ca3e  sub     rsp, 88h
0x18005ca45  mov     r14, rcx
0x18005ca48  mov     rcx, [rcx+8]
0x18005ca4c  mov     rax, [rcx]
0x18005ca4f  mov     rax, [rax+60h]
0x18005ca53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ca58  mov     r15, rax
0x18005ca5b  mov     edi, [r14+20h]
0x18005ca5f  mov     esi, edi
0x18005ca61  imul    rsi, rax
0x18005ca65  xorps   xmm1, xmm1
0x18005ca68  movdqu  xmmword ptr [rbp+57h+var_7C+4], xmm1
0x18005ca6d  xor     r13d, r13d
0x18005ca70  mov     [rbp+57h+var_68], r13
0x18005ca74  test    rdi, rdi
0x18005ca77  jz      short loc_18005CAAB
0x18005ca79  mov     edx, edi
0x18005ca7b  lea     rcx, [rbp+57h+var_7C+4]
0x18005ca7f  call    ?_Buy_nonzero@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Buy_nonzero(unsigned __int64)
0x18005ca84  mov     rbx, qword ptr [rbp+57h+var_7C+4]
0x18005ca88  mov     r8d, edi; Size
0x18005ca8b  xor     edx, edx; Val
0x18005ca8d  mov     rcx, rbx; void *
0x18005ca90  call    memset_0
0x18005ca95  lea     rax, [rdi+rbx]
0x18005ca99  mov     qword ptr [rbp+57h+var_7C+0Ch], rax
0x18005ca9d  mov     [rbp+57h+var_60], r13
0x18005caa1  lea     rcx, [rbp+57h+var_60]
0x18005caa5  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x18005caaa  nop
0x18005caab  mov     rbx, qword ptr [rbp+57h+var_7C+4]
0x18005caaf  mov     [rbx+1BEh], r13b
0x18005cab6  mov     r8, rsi
0x18005cab9  mov     edi, 1
0x18005cabe  mov     edx, edi
0x18005cac0  lea     rcx, [rbp+57h+var_7C]
0x18005cac4  call    ?ChsAddressFromLba@Utilities@DiskStructs@@YA?AU_CHS_ADDRESS@@_K0@Z; DiskStructs::Utilities::ChsAddressFromLba(unsigned __int64,unsigned __int64)
0x18005cac9  movzx   ecx, word ptr [rax]
0x18005cacc  mov     dl, [rax+2]
0x18005cacf  mov     [rbx+1BFh], cx
0x18005cad6  mov     [rbx+1C1h], dl
0x18005cadc  mov     byte ptr [rbx+1C2h], 0EEh
0x18005cae3  mov     [rbx+1C6h], edi
0x18005cae9  mov     r8, rsi
0x18005caec  mov     rdx, r15
0x18005caef  lea     rcx, [rbp+57h+var_7C]
0x18005caf3  call    ?ChsAddressFromLba@Utilities@DiskStructs@@YA?AU_CHS_ADDRESS@@_K0@Z; DiskStructs::Utilities::ChsAddressFromLba(unsigned __int64,unsigned __int64)
0x18005caf8  movzx   ecx, word ptr [rax]
0x18005cafb  mov     dl, [rax+2]
0x18005cafe  mov     [rbx+1C3h], cx
0x18005cb05  mov     [rbx+1C5h], dl
0x18005cb0b  lea     r12, [r15-1]
0x18005cb0f  mov     esi, 0FFFFFFFFh
0x18005cb14  cmp     r12, rsi
0x18005cb17  mov     eax, r12d
0x18005cb1a  jb      short loc_18005CB1E
0x18005cb1c  mov     eax, esi
0x18005cb1e  mov     [rbx+1CAh], eax
0x18005cb24  mov     word ptr [rbx+1FEh], 0AA55h
0x18005cb2d  mov     rcx, [r14+8]
0x18005cb31  mov     rax, [rcx]
0x18005cb34  mov     [rsp+0C0h+var_98], r13
0x18005cb39  mov     [rsp+0C0h+var_A0], edi
0x18005cb3d  xor     r9d, r9d
0x18005cb40  mov     r8d, [r14+20h]
0x18005cb44  mov     rdx, qword ptr [rbp+57h+var_7C+4]
0x18005cb48  mov     rax, [rax+80h]
0x18005cb4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cb54  mov     rcx, qword ptr [rbp+57h+var_7C+4]; void *
0x18005cb58  mov     r8, qword ptr [rbp+57h+var_7C+0Ch]
0x18005cb5c  sub     r8, rcx; Size
0x18005cb5f  xor     edx, edx; Val
0x18005cb61  call    memset_0
0x18005cb66  mov     edi, [r14+20h]
0x18005cb6a  lea     ecx, [rdi+3FFFh]
0x18005cb70  mov     eax, edi
0x18005cb72  neg     eax
0x18005cb74  and     ecx, eax
0x18005cb76  mov     dword ptr [rbp+57h+var_7C], ecx
0x18005cb79  xor     edx, edx
0x18005cb7b  mov     eax, ecx
0x18005cb7d  div     edi
0x18005cb7f  mov     r13d, eax
0x18005cb82  mov     [rbp+57h+var_60], r13
0x18005cb86  sub     r15, r13
0x18005cb89  lea     rbx, [r15-1]
0x18005cb8d  mov     rcx, [r14+8]
0x18005cb91  mov     rax, [rcx]
0x18005cb94  mov     rax, [rax+70h]
0x18005cb98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cb9d  xor     edx, edx
0x18005cb9f  div     edi
0x18005cba1  mov     ecx, eax
0x18005cba3  inc     r13
0x18005cba6  add     r13, rcx
0x18005cba9  dec     rax
0x18005cbac  not     rax
0x18005cbaf  and     r13, rax
0x18005cbb2  xor     edx, edx
0x18005cbb4  mov     rax, rbx
0x18005cbb7  div     rcx
0x18005cbba  sub     rbx, rdx
0x18005cbbd  lea     r15, [rbx-1]
0x18005cbc1  mov     [rbp+57h+var_80], 0
0x18005cbc5  mov     ebx, dword ptr [rbp+57h+var_7C]
0x18005cbc8  add     ebx, [r14+20h]
0x18005cbcc  mov     rdx, qword ptr [rbp+57h+var_7C+4]
0x18005cbd0  mov     rdi, qword ptr [rbp+57h+var_7C+0Ch]
0x18005cbd4  mov     rcx, rdi
0x18005cbd7  sub     rcx, rdx
0x18005cbda  cmp     rbx, rcx
0x18005cbdd  jnb     short loc_18005CBE5
0x18005cbdf  lea     rax, [rbx+rdx]
0x18005cbe3  jmp     short loc_18005CC19
0x18005cbe5  jbe     short loc_18005CC1D
0x18005cbe7  mov     rax, [rbp+57h+var_68]
0x18005cbeb  sub     rax, rdx
0x18005cbee  cmp     rbx, rax
0x18005cbf1  jbe     short loc_18005CC05
0x18005cbf3  lea     r8, [rbp+57h+var_80]
0x18005cbf7  mov     rdx, rbx
0x18005cbfa  lea     rcx, [rbp+57h+var_7C+4]
0x18005cbfe  call    ??$_Resize_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBE@Z; std::vector<uchar>::_Resize_reallocate<uchar>(unsigned __int64,uchar const &)
0x18005cc03  jmp     short loc_18005CC1D
0x18005cc05  sub     rbx, rcx
0x18005cc08  mov     r8, rbx; Size
0x18005cc0b  xor     edx, edx; Val
0x18005cc0d  mov     rcx, rdi; void *
0x18005cc10  call    memset_0
0x18005cc15  lea     rax, [rbx+rdi]
0x18005cc19  mov     qword ptr [rbp+57h+var_7C+0Ch], rax
0x18005cc1d  mov     rdi, qword ptr [rbp+57h+var_7C+4]
0x18005cc21  mov     rax, 5452415020494645h
0x18005cc2b  mov     [rdi], rax
0x18005cc2e  mov     dword ptr [rdi+8], 10000h
0x18005cc35  mov     dword ptr [rdi+0Ch], 5Ch ; '\'
0x18005cc3c  mov     qword ptr [rdi+18h], 1
0x18005cc44  mov     [rdi+20h], r12
0x18005cc48  mov     [rdi+28h], r13
0x18005cc4c  mov     [rdi+30h], r15
0x18005cc50  xorps   xmm0, xmm0
0x18005cc53  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x18005cc57  lea     rcx, [rbp+57h+Uuid]; Uuid
0x18005cc5b  call    cs:__imp_UuidCreate
0x18005cc61  movaps  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x18005cc65  movdqu  xmmword ptr [rdi+38h], xmm0
0x18005cc6a  mov     qword ptr [rdi+48h], 2
0x18005cc72  mov     eax, 80h
0x18005cc77  mov     [rdi+50h], eax
0x18005cc7a  mov     [rdi+54h], eax
0x18005cc7d  mov     ebx, [r14+20h]
0x18005cc81  add     rbx, qword ptr [rbp+57h+var_7C+4]
0x18005cc85  movups  xmm0, xmmword ptr cs:?GPT_PARTITION_TYPE_GUEST_STATE@@3U_GUID@@B.Data1; _GUID const GPT_PARTITION_TYPE_GUEST_STATE ...
0x18005cc8c  movdqu  xmmword ptr [rbx], xmm0
0x18005cc90  xorps   xmm0, xmm0
0x18005cc93  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x18005cc97  lea     rcx, [rbp+57h+Uuid]; Uuid
0x18005cc9b  call    cs:__imp_UuidCreate
0x18005cca1  movaps  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x18005cca5  movdqu  xmmword ptr [rbx+10h], xmm0
0x18005ccaa  mov     [rbx+20h], r13
0x18005ccae  mov     [rbx+28h], r15
0x18005ccb2  lea     rcx, [rbx+38h]
0x18005ccb6  mov     r9d, 1Eh
0x18005ccbc  lea     r8, ?GPT_PARTITION_NAME_GUEST_STATE@@3QBGB; "Guest Runtime State Partition"
0x18005ccc3  lea     edx, [r9+6]
0x18005ccc7  call    cs:__imp__o_wcsncpy_s
0x18005cccd  mov     edx, dword ptr [rbp+57h+var_7C]; void *
0x18005ccd0  mov     rcx, rbx; this
0x18005ccd3  call    ?ComputeGptChecksum@Utilities@DiskStructs@@YAKPEBXK@Z; DiskStructs::Utilities::ComputeGptChecksum(void const *,ulong)
0x18005ccd8  mov     [rdi+58h], eax
0x18005ccdb  mov     r8d, esi
0x18005ccde  xor     r9d, r9d
0x18005cce1  lea     r10, qword_1800B8FA0
0x18005cce8  movzx   edx, byte ptr [rdi+r9]
0x18005cced  movzx   ecx, r8b
0x18005ccf1  xor     rdx, rcx
0x18005ccf4  shr     r8d, 8
0x18005ccf8  xor     r8d, [r10+rdx*4]
0x18005ccfc  inc     r9
0x18005ccff  cmp     r9, 5Ch ; '\'
0x18005cd03  jnz     short loc_18005CCE8
0x18005cd05  not     r8d
0x18005cd08  mov     [rdi+10h], r8d
0x18005cd0c  mov     rcx, [r14+8]
0x18005cd10  mov     rdx, [rcx]
0x18005cd13  mov     r9, [rbp+57h+var_60]
0x18005cd17  inc     r9d
0x18005cd1a  mov     r8d, dword ptr [rbp+57h+var_7C]
0x18005cd1e  add     r8d, [r14+20h]
0x18005cd22  mov     rax, [rdx+80h]
0x18005cd29  mov     [rsp+0C0h+var_98], 0
0x18005cd32  mov     [rsp+0C0h+var_A0], r9d
0x18005cd37  mov     r9d, 1
0x18005cd3d  mov     rdx, qword ptr [rbp+57h+var_7C+4]
0x18005cd41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cd46  mov     rbx, r12
0x18005cd49  sub     rbx, [rbp+57h+var_60]
0x18005cd4d  mov     rcx, [rdi+18h]
0x18005cd51  mov     rax, [rdi+20h]
0x18005cd55  mov     [rdi+18h], rax
0x18005cd59  mov     [rdi+20h], rcx
0x18005cd5d  mov     [rdi+48h], rbx
0x18005cd61  xor     r8d, r8d
0x18005cd64  lea     r9, qword_1800B8FA0
0x18005cd6b  movzx   edx, byte ptr [rdi+r8]
0x18005cd70  movzx   ecx, sil
0x18005cd74  xor     rdx, rcx
0x18005cd77  shr     esi, 8
0x18005cd7a  xor     esi, [r9+rdx*4]
0x18005cd7e  inc     r8
0x18005cd81  cmp     r8, 5Ch ; '\'
0x18005cd85  jnz     short loc_18005CD6B
0x18005cd87  not     esi
0x18005cd89  mov     [rdi+10h], esi
0x18005cd8c  mov     rcx, [r14+8]
0x18005cd90  mov     rax, [rcx]
0x18005cd93  mov     [rsp+0C0h+var_98], 0
0x18005cd9c  mov     [rsp+0C0h+var_A0], 1
0x18005cda4  mov     r9, r12
0x18005cda7  mov     r8d, [r14+20h]
0x18005cdab  mov     rdx, qword ptr [rbp+57h+var_7C+4]
0x18005cdaf  mov     rax, [rax+80h]
0x18005cdb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cdbb  mov     rcx, [r14+8]
0x18005cdbf  mov     rax, [rcx]
0x18005cdc2  mov     edx, [r14+20h]
0x18005cdc6  add     rdx, qword ptr [rbp+57h+var_7C+4]
0x18005cdca  mov     [rsp+0C0h+var_98], 0
0x18005cdd3  mov     r8, [rbp+57h+var_60]
0x18005cdd7  mov     [rsp+0C0h+var_A0], r8d
0x18005cddc  mov     r9, rbx
0x18005cddf  mov     r8d, dword ptr [rbp+57h+var_7C]
0x18005cde3  mov     rax, [rax+80h]
0x18005cdea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cdef  mov     [r14+10h], r13
0x18005cdf3  sub     r15, r13
0x18005cdf6  inc     r15
0x18005cdf9  mov     [r14+18h], r15
0x18005cdfd  lea     rcx, [rbp+57h+var_7C+4]
0x18005ce01  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18005ce06  add     rsp, 88h
0x18005ce0d  pop     r15
0x18005ce0f  pop     r14
0x18005ce11  pop     r13
0x18005ce13  pop     r12
0x18005ce15  pop     rdi
0x18005ce16  pop     rsi
0x18005ce17  pop     rbx
0x18005ce18  pop     rbp
0x18005ce19  retn
```
