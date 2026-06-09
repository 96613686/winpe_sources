# CFveApiBase::RefreshValidationInfoForBootApp(_GUID const *,ushort,_FVE_DATUM_VALIDATION_ENTRY *,ushort *)

- ea: `0x18009d858`
- end: `0x18009dc8d`
- name: `?RefreshValidationInfoForBootApp@CFveApiBase@@QEAAJPEBU_GUID@@GPEAU_FVE_DATUM_VALIDATION_ENTRY@@PEAG@Z`
- size: `1077`
- prototype: `__int64 __usercall@<rax>(CFveApiBase *__hidden this@<rcx>, const struct _GUID *@<rdx>, unsigned __int16@<r8w>, struct _FVE_DATUM_VALIDATION_ENTRY *@<r9>, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18005019c`
- `0x18009c910`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180018b10`
- `0x1800600c0`
- `0x180071210`
- `0x180099a58`
- `0x18009aca8`
- `0x18009d858`
- `0x18009e740`
- `0x18011f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18009dc32`
- `msvcrt!??3@YAXPEAX@Z` at `0x180124956`
- `msvcrt!??3@YAXPEAX@Z` at `0x18009dc32`
- `msvcrt!??3@YAXPEAX@Z` at `0x180124956`
- `bcd!BcdCloseStore` at `0x18009dc17`
- `bcd!BcdCloseStore` at `0x180124940`
- `bcd!BcdCloseStore` at `0x18009dc17`
- `bcd!BcdCloseStore` at `0x180124940`
- `bcd!BcdOpenSystemStore` at `0x18009da04`
- `bcd!BcdOpenSystemStore` at `0x18009da04`

## pseudocode

```c
__int64 __fastcall CFveApiBase::RefreshValidationInfoForBootApp(
        CFveApiBase *this,
        struct _GUID *a2,
        unsigned __int16 a3,
        struct _FVE_DATUM_VALIDATION_ENTRY *a4,
        unsigned __int16 *a5)
{
  unsigned __int64 v6; // r12
  unsigned __int16 v8; // si
  unsigned __int64 v9; // rax
  __int64 j; // rdx
  struct _FVE_DATUM_VALIDATION_ENTRY *v11; // r14
  unsigned int v12; // ebx
  PVOID *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  int v16; // eax
  int v17; // eax
  unsigned __int16 i; // r8
  __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned __int16 v22[2]; // [rsp+50h] [rbp-78h] BYREF
  unsigned __int16 v23; // [rsp+54h] [rbp-74h]
  int v24; // [rsp+58h] [rbp-70h]
  struct _GUID *v25; // [rsp+60h] [rbp-68h]
  CFveApiBase *v26; // [rsp+68h] [rbp-60h]
  struct _FVE_DATUM_VALIDATION_ENTRY *v27; // [rsp+70h] [rbp-58h]
  void *v28; // [rsp+78h] [rbp-50h] BYREF

  v6 = a3;
  v25 = a2;
  v26 = this;
  v27 = 0;
  v28 = 0;
  v22[0] = 0;
  v8 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_1559182127783aab3882fe828952d989_Traceguids);
  v9 = 40 * v6;
  if ( !is_mul_ok(v6, 0x28u) )
    v9 = -1;
  v11 = (struct _FVE_DATUM_VALIDATION_ENTRY *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v27 = v11;
  if ( !v11 )
  {
    v12 = -2147024882;
    v24 = -2147024882;
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_43;
    v14 = 56;
    v15 = 2147942414LL;
    goto LABEL_10;
  }
  v16 = CFveApiBase::DeleteValidationInfoForBootApp(this, v25, 1, v6, a4, a5);
  v12 = v16;
  v24 = v16;
  if ( v16 < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_43;
    v14 = 57;
LABEL_15:
    v15 = (unsigned int)v16;
LABEL_10:
    WPP_SF_d(v13[2], v14, &WPP_1559182127783aab3882fe828952d989_Traceguids, v15);
LABEL_42:
    v13 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_43;
  }
  v16 = CFveApiBase::AddValidationInfoForBootApp(v26, v25, 1, v6, a4, a5);
  v12 = v16;
  v24 = v16;
  if ( v16 < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_43;
    v14 = 58;
    goto LABEL_15;
  }
  v17 = BcdOpenSystemStore(&v28, j);
  v16 = FromNtStatus(v17);
  v12 = v16;
  v24 = v16;
  if ( v16 < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_43;
    v14 = 59;
    goto LABEL_15;
  }
  v16 = CFveApiBase::StoreValidationDataForAppEx(v26, v28, 0, 0, v6, v11, v22, 1, 0);
  v12 = v16;
  v24 = v16;
  if ( v16 < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_43;
    v14 = 60;
    goto LABEL_15;
  }
  while ( v8 < *a5 && *((_WORD *)a4 + 20 * v8) == 2 )
    v23 = ++v8;
  for ( i = v22[0]; ; v22[0] = i )
  {
    if ( v8 >= *a5 )
    {
      for ( j = 0; ; LOWORD(j) = j + 1 )
      {
        v23 = j;
        if ( (unsigned __int16)j >= i )
          break;
        v20 = 5LL * (unsigned __int16)j;
        *((_WORD *)a4 + 4 * v20) = *((_WORD *)v11 + 20 * (unsigned __int16)j);
        *((_WORD *)a4 + 4 * v20 + 1) = *((_WORD *)v11 + 20 * (unsigned __int16)j + 1);
        *((_DWORD *)a4 + 2 * v20 + 1) = *((_DWORD *)v11 + 10 * (unsigned __int16)j + 1);
        *(_OWORD *)((char *)a4 + 8 * v20 + 8) = *(_OWORD *)((char *)v11 + 40 * (unsigned __int16)j + 8);
        *(_OWORD *)((char *)a4 + 8 * v20 + 24) = *(_OWORD *)((char *)v11 + 40 * (unsigned __int16)j + 24);
      }
      *a5 = i;
      goto LABEL_42;
    }
    if ( i >= (unsigned __int16)v6 )
      break;
    j = 5LL * v8;
    v19 = 5LL * i;
    *((_WORD *)v11 + 4 * v19) = *((_WORD *)a4 + 20 * v8);
    *((_WORD *)v11 + 4 * v19 + 1) = *((_WORD *)a4 + 20 * v8 + 1);
    *((_DWORD *)v11 + 2 * v19 + 1) = *((_DWORD *)a4 + 10 * v8 + 1);
    *(_OWORD *)((char *)v11 + 8 * v19 + 8) = *(_OWORD *)((char *)a4 + 40 * v8 + 8);
    *(_OWORD *)((char *)v11 + 8 * v19 + 24) = *(_OWORD *)((char *)a4 + 40 * v8++ + 24);
    v23 = v8;
    ++i;
  }
  v12 = -2147024883;
  v24 = -2147024883;
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_DDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      61,
      &WPP_1559182127783aab3882fe828952d989_Traceguids,
      i,
      v6,
      -2147024883);
    goto LABEL_42;
  }
LABEL_43:
  if ( v28 )
  {
    BcdCloseStore(v28, j);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 )
  {
    operator delete(v11);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 0x20) != 0 )
    WPP_SF_d(v13[2], 62, &WPP_1559182127783aab3882fe828952d989_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x18009d858  push    rbx
0x18009d85a  push    rsi
0x18009d85b  push    r12
0x18009d85d  push    r13
0x18009d85f  push    r14
0x18009d861  push    r15
0x18009d863  sub     rsp, 98h
0x18009d86a  mov     rax, cs:__security_cookie
0x18009d871  xor     rax, rsp
0x18009d874  mov     [rsp+0C8h+var_48], rax
0x18009d87c  mov     r15, r9
0x18009d87f  movzx   r12d, r8w
0x18009d883  mov     [rsp+0C8h+var_68], rdx
0x18009d888  mov     rbx, rcx
0x18009d88b  mov     [rsp+0C8h+var_60], rcx
0x18009d890  mov     r13, [rsp+0C8h+arg_20]
0x18009d898  mov     [rsp+0C8h+var_58], 0
0x18009d8a1  mov     [rsp+0C8h+var_50], 0
0x18009d8aa  xor     eax, eax
0x18009d8ac  mov     [rsp+0C8h+var_78], ax
0x18009d8b1  xor     esi, esi
0x18009d8b3  lea     rax, WPP_GLOBAL_Control
0x18009d8ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d8c1  cmp     rcx, rax
0x18009d8c4  jz      short loc_18009D8E0
0x18009d8c6  test    byte ptr [rcx+1Ch], 20h
0x18009d8ca  jz      short loc_18009D8E0
0x18009d8cc  lea     edx, [rsi+37h]
0x18009d8cf  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x18009d8d6  mov     rcx, [rcx+10h]
0x18009d8da  call    WPP_SF_
0x18009d8df  nop
0x18009d8e0  mov     eax, 28h ; '('
0x18009d8e5  mul     r12
0x18009d8e8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18009d8ef  cmovb   rax, rcx
0x18009d8f3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009d8fa  mov     rcx, rax; unsigned __int64
0x18009d8fd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18009d902  mov     r14, rax
0x18009d905  mov     [rsp+0C8h+var_58], rax
0x18009d90a  test    rax, rax
0x18009d90d  jnz     short loc_18009D954
0x18009d90f  mov     ebx, 8007000Eh
0x18009d914  mov     [rsp+0C8h+var_70], ebx
0x18009d918  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d91f  lea     rsi, WPP_GLOBAL_Control
0x18009d926  cmp     rcx, rsi
0x18009d929  jz      loc_18009DC0A
0x18009d92f  test    byte ptr [rcx+1Ch], 2
0x18009d933  jz      loc_18009DC0A
0x18009d939  lea     edx, [rax+38h]
0x18009d93c  mov     r9d, ebx
0x18009d93f  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x18009d946  mov     rcx, [rcx+10h]
0x18009d94a  call    WPP_SF_d
0x18009d94f  jmp     loc_18009DC03
0x18009d954  mov     [rsp+0C8h+var_A0], r13; unsigned __int16 *
0x18009d959  mov     [rsp+0C8h+var_A8], r15; struct _FVE_DATUM_VALIDATION_ENTRY *
0x18009d95e  movzx   r9d, r12w; unsigned __int16
0x18009d962  mov     r8d, 1; int
0x18009d968  mov     rdx, [rsp+0C8h+var_68]; struct _GUID *
0x18009d96d  mov     rcx, rbx; this
0x18009d970  call    ?DeleteValidationInfoForBootApp@CFveApiBase@@QEAAJPEBU_GUID@@HGPEAU_FVE_DATUM_VALIDATION_ENTRY@@PEAG@Z; CFveApiBase::DeleteValidationInfoForBootApp(_GUID const *,int,ushort,_FVE_DATUM_VALIDATION_ENTRY *,ushort *)
0x18009d975  mov     ebx, eax
0x18009d977  mov     [rsp+0C8h+var_70], eax
0x18009d97b  test    eax, eax
0x18009d97d  jns     short loc_18009D9AA
0x18009d97f  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d986  lea     rsi, WPP_GLOBAL_Control
0x18009d98d  cmp     rcx, rsi
0x18009d990  jz      loc_18009DC0A
0x18009d996  test    byte ptr [rcx+1Ch], 2
0x18009d99a  jz      loc_18009DC0A
0x18009d9a0  mov     edx, 39h ; '9'
0x18009d9a5  mov     r9d, eax
0x18009d9a8  jmp     short loc_18009D93F
0x18009d9aa  mov     [rsp+0C8h+var_A0], r13; unsigned __int16 *
0x18009d9af  mov     [rsp+0C8h+var_A8], r15; struct _FVE_DATUM_VALIDATION_ENTRY *
0x18009d9b4  movzx   r9d, r12w; unsigned __int16
0x18009d9b8  mov     r8d, 1; int
0x18009d9be  mov     rdx, [rsp+0C8h+var_68]; struct _GUID *
0x18009d9c3  mov     rcx, [rsp+0C8h+var_60]; this
0x18009d9c8  call    ?AddValidationInfoForBootApp@CFveApiBase@@QEAAJPEBU_GUID@@HGPEAU_FVE_DATUM_VALIDATION_ENTRY@@PEAG@Z; CFveApiBase::AddValidationInfoForBootApp(_GUID const *,int,ushort,_FVE_DATUM_VALIDATION_ENTRY *,ushort *)
0x18009d9cd  mov     ebx, eax
0x18009d9cf  mov     [rsp+0C8h+var_70], eax
0x18009d9d3  test    eax, eax
0x18009d9d5  jns     short loc_18009D9FF
0x18009d9d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d9de  lea     rsi, WPP_GLOBAL_Control
0x18009d9e5  cmp     rcx, rsi
0x18009d9e8  jz      loc_18009DC0A
0x18009d9ee  test    byte ptr [rcx+1Ch], 2
0x18009d9f2  jz      loc_18009DC0A
0x18009d9f8  mov     edx, 3Ah ; ':'
0x18009d9fd  jmp     short loc_18009D9A5
0x18009d9ff  lea     rcx, [rsp+0C8h+var_50]
0x18009da04  call    cs:__imp_BcdOpenSystemStore
0x18009da0b  nop     dword ptr [rax+rax+00h]
0x18009da10  mov     ecx, eax; int
0x18009da12  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009da17  mov     ebx, eax
0x18009da19  mov     [rsp+0C8h+var_70], eax
0x18009da1d  test    eax, eax
0x18009da1f  jns     short loc_18009DA4C
0x18009da21  mov     rcx, cs:WPP_GLOBAL_Control
0x18009da28  lea     rsi, WPP_GLOBAL_Control
0x18009da2f  cmp     rcx, rsi
0x18009da32  jz      loc_18009DC0A
0x18009da38  test    byte ptr [rcx+1Ch], 2
0x18009da3c  jz      loc_18009DC0A
0x18009da42  mov     edx, 3Bh ; ';'
0x18009da47  jmp     loc_18009D9A5
0x18009da4c  mov     [rsp+0C8h+var_88], 0
0x18009da51  mov     [rsp+0C8h+var_90], 1
0x18009da56  lea     rax, [rsp+0C8h+var_78]
0x18009da5b  mov     [rsp+0C8h+var_98], rax
0x18009da60  mov     [rsp+0C8h+var_A0], r14
0x18009da65  mov     word ptr [rsp+0C8h+var_A8], r12w
0x18009da6b  xor     r9d, r9d
0x18009da6e  xor     r8d, r8d
0x18009da71  mov     rdx, [rsp+0C8h+var_50]
0x18009da76  mov     rcx, [rsp+0C8h+var_60]
0x18009da7b  call    ?StoreValidationDataForAppEx@CFveApiBase@@QEAAJPEAXPEBU_GUID@@W4eFveBootApplicationPolicy@@GPEAU_FVE_DATUM_VALIDATION_ENTRY@@PEAG_N5@Z; CFveApiBase::StoreValidationDataForAppEx(void *,_GUID const *,eFveBootApplicationPolicy,ushort,_FVE_DATUM_VALIDATION_ENTRY *,ushort *,bool,bool)
0x18009da80  mov     ebx, eax
0x18009da82  mov     [rsp+0C8h+var_70], eax
0x18009da86  test    eax, eax
0x18009da88  jns     short loc_18009DAB5
0x18009da8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009da91  lea     rsi, WPP_GLOBAL_Control
0x18009da98  cmp     rcx, rsi
0x18009da9b  jz      loc_18009DC0A
0x18009daa1  test    byte ptr [rcx+1Ch], 2
0x18009daa5  jz      loc_18009DC0A
0x18009daab  mov     edx, 3Ch ; '<'
0x18009dab0  jmp     loc_18009D9A5
0x18009dab5  mov     r9d, 1
0x18009dabb  cmp     si, [r13+0]
0x18009dac0  jnb     short loc_18009DADC
0x18009dac2  movzx   eax, si
0x18009dac5  lea     rcx, [rax+rax*4]
0x18009dac9  cmp     word ptr [r15+rcx*8], 2
0x18009dacf  jnz     short loc_18009DADC
0x18009dad1  add     si, r9w
0x18009dad5  mov     [rsp+0C8h+var_74], si
0x18009dada  jmp     short loc_18009DABB
0x18009dadc  movzx   r8d, [rsp+0C8h+var_78]
0x18009dae2  cmp     si, [r13+0]
0x18009dae7  jnb     loc_18009DBA5
0x18009daed  cmp     r8w, r12w
0x18009daf1  jb      short loc_18009DB46
0x18009daf3  mov     ebx, 8007000Dh
0x18009daf8  mov     [rsp+0C8h+var_70], ebx
0x18009dafc  mov     rcx, cs:WPP_GLOBAL_Control
0x18009db03  lea     rsi, WPP_GLOBAL_Control
0x18009db0a  cmp     rcx, rsi
0x18009db0d  jz      loc_18009DC0A
0x18009db13  test    byte ptr [rcx+1Ch], 2
0x18009db17  jz      loc_18009DC0A
0x18009db1d  mov     eax, r12d
0x18009db20  movzx   r9d, r8w
0x18009db24  mov     edx, 3Dh ; '='
0x18009db29  mov     dword ptr [rsp+0C8h+var_A0], ebx
0x18009db2d  mov     dword ptr [rsp+0C8h+var_A8], eax
0x18009db31  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x18009db38  mov     rcx, [rcx+10h]
0x18009db3c  call    WPP_SF_DDD
0x18009db41  jmp     loc_18009DC03
0x18009db46  movzx   eax, si
0x18009db49  lea     rdx, [rax+rax*4]
0x18009db4d  movzx   eax, r8w
0x18009db51  lea     rcx, [rax+rax*4]
0x18009db55  movzx   eax, word ptr [r15+rdx*8]
0x18009db5a  mov     [r14+rcx*8], ax
0x18009db5f  movzx   eax, word ptr [r15+rdx*8+2]
0x18009db65  mov     [r14+rcx*8+2], ax
0x18009db6b  mov     eax, [r15+rdx*8+4]
0x18009db70  mov     [r14+rcx*8+4], eax
0x18009db75  movups  xmm0, xmmword ptr [r15+rdx*8+8]
0x18009db7b  movups  xmmword ptr [r14+rcx*8+8], xmm0
0x18009db81  movups  xmm1, xmmword ptr [r15+rdx*8+18h]
0x18009db87  movups  xmmword ptr [r14+rcx*8+18h], xmm1
0x18009db8d  add     si, r9w
0x18009db91  mov     [rsp+0C8h+var_74], si
0x18009db96  add     r8w, r9w
0x18009db9a  mov     [rsp+0C8h+var_78], r8w
0x18009dba0  jmp     loc_18009DAE2
0x18009dba5  xor     edx, edx
0x18009dba7  mov     [rsp+0C8h+var_74], dx
0x18009dbac  cmp     dx, r8w
0x18009dbb0  jnb     short loc_18009DBF7
0x18009dbb2  movzx   eax, dx
0x18009dbb5  lea     rcx, [rax+rax*4]
0x18009dbb9  movzx   eax, word ptr [r14+rcx*8]
0x18009dbbe  mov     [r15+rcx*8], ax
0x18009dbc3  movzx   eax, word ptr [r14+rcx*8+2]
0x18009dbc9  mov     [r15+rcx*8+2], ax
0x18009dbcf  mov     eax, [r14+rcx*8+4]
0x18009dbd4  mov     [r15+rcx*8+4], eax
0x18009dbd9  movups  xmm0, xmmword ptr [r14+rcx*8+8]
0x18009dbdf  movups  xmmword ptr [r15+rcx*8+8], xmm0
0x18009dbe5  movups  xmm1, xmmword ptr [r14+rcx*8+18h]
0x18009dbeb  movups  xmmword ptr [r15+rcx*8+18h], xmm1
0x18009dbf1  add     dx, r9w
0x18009dbf5  jmp     short loc_18009DBA7
0x18009dbf7  mov     [r13+0], r8w
0x18009dbfc  lea     rsi, WPP_GLOBAL_Control
0x18009dc03  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dc0a  mov     rax, [rsp+0C8h+var_50]
0x18009dc0f  test    rax, rax
0x18009dc12  jz      short loc_18009DC2A
0x18009dc14  mov     rcx, rax
0x18009dc17  call    cs:__imp_BcdCloseStore
0x18009dc1e  nop     dword ptr [rax+rax+00h]
0x18009dc23  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dc2a  test    r14, r14
0x18009dc2d  jz      short loc_18009DC45
0x18009dc2f  mov     rcx, r14
0x18009dc32  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18009dc39  nop     dword ptr [rax+rax+00h]
0x18009dc3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dc45  cmp     rcx, rsi
0x18009dc48  jz      short loc_18009DC68
0x18009dc4a  test    byte ptr [rcx+1Ch], 20h
0x18009dc4e  jz      short loc_18009DC68
0x18009dc50  mov     edx, 3Eh ; '>'
0x18009dc55  mov     r9d, ebx
0x18009dc58  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x18009dc5f  mov     rcx, [rcx+10h]
0x18009dc63  call    WPP_SF_d
0x18009dc68  mov     eax, ebx
0x18009dc6a  mov     rcx, [rsp+0C8h+var_48]
0x18009dc72  xor     rcx, rsp; StackCookie
0x18009dc75  call    __security_check_cookie
0x18009dc7a  add     rsp, 98h
0x18009dc81  pop     r15
0x18009dc83  pop     r14
0x18009dc85  pop     r13
0x18009dc87  pop     r12
0x18009dc89  pop     rsi
0x18009dc8a  pop     rbx
0x18009dc8b  retn
0x18012492e  push    rbp
0x180124930  sub     rsp, 50h
0x180124934  mov     rbp, rdx
0x180124937  mov     rcx, [rbp+78h]
0x18012493b  test    rcx, rcx
0x18012493e  jz      short loc_18012494D
0x180124940  call    cs:__imp_BcdCloseStore
0x180124947  nop     dword ptr [rax+rax+00h]
0x18012494c  nop
0x18012494d  mov     rcx, [rbp+70h]
0x180124951  test    rcx, rcx
0x180124954  jz      short loc_180124963
0x180124956  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18012495d  nop     dword ptr [rax+rax+00h]
0x180124962  nop
0x180124963  add     rsp, 50h
0x180124967  pop     rbp
0x180124968  retn
```
