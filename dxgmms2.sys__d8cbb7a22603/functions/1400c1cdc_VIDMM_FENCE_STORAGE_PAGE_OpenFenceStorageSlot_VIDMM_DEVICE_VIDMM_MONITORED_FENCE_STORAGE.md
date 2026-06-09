# VIDMM_FENCE_STORAGE_PAGE::OpenFenceStorageSlot(VIDMM_DEVICE *,VIDMM_MONITORED_FENCE_STORAGE *)

- ea: `0x1400c1cdc`
- end: `0x1400c20ec`
- name: `?OpenFenceStorageSlot@VIDMM_FENCE_STORAGE_PAGE@@QEAAJPEAVVIDMM_DEVICE@@PEAUVIDMM_MONITORED_FENCE_STORAGE@@@Z`
- size: `1040`
- prototype: `__int64 __fastcall(VIDMM_FENCE_STORAGE_PAGE *__hidden this, struct VIDMM_DEVICE *, struct VIDMM_MONITORED_FENCE_STORAGE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1400c2770`

## callees

- `0x140003490`
- `0x140004268`
- `0x14002b730`
- `0x14002b830`
- `0x14002e6c0`
- `0x140030854`
- `0x1400b4cd8`
- `0x1400c1cdc`
- `0x1400ea180`
- `0x1400f24e0`
- `0x1400fdc1c`
- `0x1400feb90`

## import_xrefs

- `watchdog!WdLogSingleEntry0` at `0x1400c2033`
- `watchdog!WdLogSingleEntry0` at `0x1400c2033`
- `watchdog!WdLogSingleEntry1` at `0x1400c1ec7`
- `watchdog!WdLogSingleEntry1` at `0x1400c1f55`
- `watchdog!WdLogSingleEntry1` at `0x1400c200f`
- `watchdog!WdLogSingleEntry1` at `0x1400c1ec7`
- `watchdog!WdLogSingleEntry1` at `0x1400c1f55`
- `watchdog!WdLogSingleEntry1` at `0x1400c200f`

## string_xrefs

- `0x1400c1ed3`: `Failed to create allocation for a fence storage page: 0x%I64x`
- `0x1400c1f61`: `Failed to create VidMm allocation for a fence storage page: 0x%I64x`
- `0x1400c201b`: `MakeResident failed 0x%I64x`

## pseudocode

```c
__int64 __fastcall VIDMM_FENCE_STORAGE_PAGE::OpenFenceStorageSlot(
        VIDMM_FENCE_STORAGE_PAGE *this,
        struct _VIDSCH_SYNC_OBJECT ****a2,
        struct VIDMM_MONITORED_FENCE_STORAGE *a3)
{
  VIDMM_GLOBAL *v7; // r15
  struct _VIDSCH_SYNC_OBJECT *v8; // rsi
  struct _VIDSCH_SYNC_OBJECT **v9; // r13
  __int64 v10; // r14
  __int64 v11; // rdi
  __int64 v12; // r8
  __int64 v13; // rdx
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  unsigned int v16; // r8d
  int v17; // edx
  int v18; // eax
  int v19; // ecx
  int v20; // r8d
  const wchar_t *v21; // r9
  struct VIDMM_GLOBAL_ALLOC *v22; // r8
  int v23; // r9d
  int v24; // eax
  int Resident; // eax
  __int64 v26; // rax
  int v27; // ecx
  int v28; // r8d
  struct VIDMM_GLOBAL_ALLOC *v29; // [rsp+E0h] [rbp-80h] BYREF
  unsigned __int64 v30; // [rsp+E8h] [rbp-78h] BYREF
  unsigned __int64 v31; // [rsp+F0h] [rbp-70h] BYREF
  _BYTE v32[56]; // [rsp+F8h] [rbp-68h] BYREF
  __m128i v33; // [rsp+130h] [rbp-30h]
  __int128 v34; // [rsp+140h] [rbp-20h]
  __int128 v35; // [rsp+150h] [rbp-10h]
  __int64 v36; // [rsp+160h] [rbp+0h]
  char v37; // [rsp+1C0h] [rbp+60h] BYREF
  struct VIDMM_MULTI_ALLOC *v38; // [rsp+1C8h] [rbp+68h] BYREF

  if ( (*((_BYTE *)a3 + 40) & 4) == 0 )
    return 0;
  v7 = (VIDMM_GLOBAL *)*a2;
  v8 = (*a2)[4560][*((unsigned int *)this + 45)];
  v38 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v9 = *a2[9];
  DXGAUTOPUSHLOCKFASTEXCLUSIVE::DXGAUTOPUSHLOCKFASTEXCLUSIVE(
    (DXGAUTOPUSHLOCKFASTEXCLUSIVE *)v32,
    (VIDMM_FENCE_STORAGE_PAGE *)((char *)this + 72),
    (bool)a3);
  if ( *((struct _VIDSCH_SYNC_OBJECT *****)this + 20) != a2 )
    goto LABEL_26;
  v10 = *((_QWORD *)this + 21);
  if ( !v10 )
  {
    v12 = 88 * (*((int *)a3 + 11) + 3LL * *((int *)a3 + 12));
    v13 = *(_QWORD *)(*((_QWORD *)v7 + 4560) + 8LL * *((unsigned int *)a3 + 14));
    v14 = *(_OWORD *)(v12 + v13 + 184);
    v15 = *(_OWORD *)(v12 + v13 + 200);
    v33 = *(__m128i *)(v12 + v13 + 168);
    v34 = v14;
    *(_QWORD *)&v14 = *(_QWORD *)(v12 + v13 + 216);
    v16 = _mm_cvtsi128_si32(_mm_srli_si128(v33, 12));
    v35 = v15;
    v36 = v14;
    if ( (v16 & *((_DWORD *)v8 + 21)) != 0 )
    {
      v17 = v35;
      if ( (*((_DWORD *)this + 44) & 1) != 0 )
        v17 = v35 | 1;
      v37 = 0;
      v18 = VIDMM_GLOBAL::CreateOneAllocation(
              (__int64)v7,
              0,
              *((_DWORD *)this + 45),
              0x1000u,
              0x1000u,
              0x1000u,
              0,
              0,
              v16,
              v34,
              0,
              *(_D3DDDI_SEGMENTPREFERENCE *)((char *)v33.m128i_i64 + 4),
              v17 | 0x20400000u,
              HIDWORD(v36),
              0,
              *((_QWORD *)this + 13),
              0,
              0,
              0,
              0,
              0,
              0,
              0,
              0,
              this,
              &v29,
              &v37);
      v11 = v18;
      if ( v18 >= 0 )
      {
        v22 = v29;
        v23 = *((_DWORD *)this + 44) >> 1;
        *((_QWORD *)this + 26) = *((_QWORD *)this + 17);
        v24 = VIDMM_GLOBAL::OpenOneAllocation(v7, (struct VIDMM_PROCESS **)a2, v22, (v23 & 1) == 0, 0, &v38);
        v11 = v24;
        if ( v24 >= 0 )
        {
          Resident = VIDMM_GLOBAL::MakeResident(v7, (struct VIDMM_PAGING_QUEUE *)v9, &v38, 1u, 1u, &v30, &v31);
          v11 = Resident;
          if ( Resident == 259 )
          {
            VIDMM_GLOBAL::WaitForFence(v7, v9[11], v30);
            LODWORD(v11) = 0;
          }
          else if ( Resident < 0 )
          {
            WdLogSingleEntry1(1, Resident);
            v21 = L"MakeResident failed 0x%I64x";
            WdLogGlobalForLineNumber = 1215;
            goto LABEL_11;
          }
          v26 = operator new(72, 1714645334, 64);
          if ( v26 )
          {
            *(_QWORD *)v26 = v38;
            *(_QWORD *)(v26 + 8) = v29;
            *(_QWORD *)(v26 + 16) = a2;
            *(_DWORD *)(v26 + 28) = 1;
            *(_DWORD *)(v26 + 24) = *((_DWORD *)this + 44);
            *((_QWORD *)this + 21) = v26;
            goto LABEL_27;
          }
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 1225;
          DxgkLogInternalTriageEvent(v27, 0x40000, v28, (unsigned int)L"Failed to allocate pDevMapping", 1225, 0, 0, 0);
          LODWORD(v11) = -1073741801;
LABEL_21:
          if ( v38 )
            VIDMM_GLOBAL::CloseOneAllocation(v7, (__int64 **)v38, 0, 0, (struct _D3DDDICB_DESTROYALLOCATION2FLAGS)3, 0);
          if ( v29 )
            VIDMM_GLOBAL::DestroyOneAllocation(v7, 0, v29, 0);
          goto LABEL_27;
        }
        WdLogSingleEntry1(1, v24);
        v21 = L"Failed to create VidMm allocation for a fence storage page: 0x%I64x";
        WdLogGlobalForLineNumber = 1189;
      }
      else
      {
        WdLogSingleEntry1(1, v18);
        v21 = L"Failed to create allocation for a fence storage page: 0x%I64x";
        WdLogGlobalForLineNumber = 1168;
      }
LABEL_11:
      DxgkLogInternalTriageEvent(v19, 0x40000, v20, (_DWORD)v21, v11, 0, 0, 0);
      goto LABEL_21;
    }
LABEL_26:
    LODWORD(v11) = -1073741823;
    goto LABEL_27;
  }
  LODWORD(v11) = 0;
  ++*(_DWORD *)(v10 + 28);
LABEL_27:
  DXGAUTOPUSHLOCKFASTEXCLUSIVE::Release((DXGAUTOPUSHLOCKFASTEXCLUSIVE *)v32);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400c1cdc  mov     [rsp-8+arg_0], rbx
0x1400c1ce1  push    rbp
0x1400c1ce2  push    rsi
0x1400c1ce3  push    rdi
0x1400c1ce4  push    r12
0x1400c1ce6  push    r13
0x1400c1ce8  push    r14
0x1400c1cea  push    r15
0x1400c1cec  lea     rbp, [rsp-10h]
0x1400c1cf1  sub     rsp, 170h
0x1400c1cf8  test    byte ptr [r8+28h], 4
0x1400c1cfd  mov     rdi, r8
0x1400c1d00  mov     r12, rdx
0x1400c1d03  mov     rbx, rcx
0x1400c1d06  jnz     short loc_1400C1D0F
0x1400c1d08  xor     eax, eax
0x1400c1d0a  jmp     loc_1400C20D0
0x1400c1d0f  mov     r15, [rdx]
0x1400c1d12  mov     ecx, [rcx+0B4h]
0x1400c1d18  mov     rax, [r15+8E80h]
0x1400c1d1f  mov     rsi, [rax+rcx*8]
0x1400c1d23  xor     eax, eax
0x1400c1d25  mov     [rbp+40h+arg_18], rax
0x1400c1d29  lea     rcx, [rbp+40h+var_A8]; this
0x1400c1d2d  mov     [rbp+40h+var_C0], rax
0x1400c1d31  mov     [rbp+40h+var_B8], rax
0x1400c1d35  mov     [rbp+40h+var_B0], rax
0x1400c1d39  mov     rax, [rdx+48h]
0x1400c1d3d  lea     rdx, [rbx+48h]; struct DXGPUSHLOCKFAST *
0x1400c1d41  mov     r13, [rax]
0x1400c1d44  call    ??0DXGAUTOPUSHLOCKFASTEXCLUSIVE@@QEAA@AEAVDXGPUSHLOCKFAST@@_N@Z; DXGAUTOPUSHLOCKFASTEXCLUSIVE::DXGAUTOPUSHLOCKFASTEXCLUSIVE(DXGPUSHLOCKFAST &,bool)
0x1400c1d49  cmp     [rbx+0A0h], r12
0x1400c1d50  jnz     loc_1400C20C0
0x1400c1d56  mov     r14, [rbx+0A8h]
0x1400c1d5d  xor     r9d, r9d
0x1400c1d60  test    r14, r14
0x1400c1d63  jz      short loc_1400C1D75
0x1400c1d65  lea     esi, [r9+1]
0x1400c1d69  mov     edi, r9d
0x1400c1d6c  add     [r14+1Ch], esi
0x1400c1d70  jmp     loc_1400C20C5
0x1400c1d75  movsxd  rax, dword ptr [rdi+30h]
0x1400c1d79  lea     rcx, [rax+rax*2]
0x1400c1d7d  movsxd  rax, dword ptr [rdi+2Ch]
0x1400c1d81  add     rcx, rax
0x1400c1d84  mov     rax, [r15+8E80h]
0x1400c1d8b  imul    r8, rcx, 58h ; 'X'
0x1400c1d8f  mov     ecx, [rdi+38h]
0x1400c1d92  mov     rdx, [rax+rcx*8]
0x1400c1d96  movups  xmm2, xmmword ptr [r8+rdx+0A8h]
0x1400c1d9f  movups  xmm0, xmmword ptr [r8+rdx+0B8h]
0x1400c1da8  movups  xmm1, xmmword ptr [r8+rdx+0C8h]
0x1400c1db1  movaps  [rbp+40h+var_70], xmm2
0x1400c1db5  psrldq  xmm2, 0Ch
0x1400c1dba  movaps  [rbp+40h+var_60], xmm0
0x1400c1dbe  movsd   xmm0, qword ptr [r8+rdx+0D8h]
0x1400c1dc8  movd    r8d, xmm2
0x1400c1dcd  movaps  [rbp+40h+var_50], xmm1
0x1400c1dd1  movsd   [rbp+40h+var_40], xmm0
0x1400c1dd6  test    [rsi+54h], r8d
0x1400c1dda  jz      loc_1400C20C0
0x1400c1de0  mov     eax, [rbx+0B0h]
0x1400c1de6  mov     esi, 1
0x1400c1deb  mov     edx, dword ptr [rbp+40h+var_50]
0x1400c1dee  test    sil, al
0x1400c1df1  jz      short loc_1400C1DF5
0x1400c1df3  or      edx, esi
0x1400c1df5  mov     eax, dword ptr [rbp+40h+var_40+4]
0x1400c1df8  lea     rcx, [rbp+40h+arg_10]
0x1400c1dfc  mov     [rsp+1A0h+var_D0], rcx
0x1400c1e04  or      edx, 20400000h
0x1400c1e0a  lea     rcx, [rbp+40h+var_C0]
0x1400c1e0e  mov     [rbp+40h+arg_10], r9b
0x1400c1e12  mov     [rsp+1A0h+var_D8], rcx
0x1400c1e1a  mov     rcx, [rbx+68h]
0x1400c1e1e  mov     [rsp+1A0h+var_E0], rbx
0x1400c1e26  mov     [rsp+1A0h+var_E8], r9
0x1400c1e2e  mov     [rsp+1A0h+var_F0], r9
0x1400c1e36  mov     [rsp+1A0h+var_F8], r9
0x1400c1e3e  mov     [rsp+1A0h+var_100], r9b
0x1400c1e46  mov     [rsp+1A0h+var_108], r9d
0x1400c1e4e  mov     [rsp+1A0h+var_110], r9
0x1400c1e56  mov     [rsp+1A0h+var_118], r9
0x1400c1e5e  mov     [rsp+1A0h+var_120], r9
0x1400c1e66  mov     [rsp+1A0h+var_128], rcx
0x1400c1e6b  mov     rcx, r15
0x1400c1e6e  mov     [rsp+1A0h+var_130], r9
0x1400c1e73  mov     [rsp+1A0h+var_138], eax
0x1400c1e77  mov     eax, dword ptr [rbp+40h+var_70+4]
0x1400c1e7a  mov     [rsp+1A0h+var_140], edx
0x1400c1e7e  xor     edx, edx
0x1400c1e80  mov     [rsp+1A0h+var_148], eax
0x1400c1e84  mov     eax, dword ptr [rbp+40h+var_60]
0x1400c1e87  mov     [rsp+1A0h+var_150], r9d
0x1400c1e8c  mov     [rsp+1A0h+var_158], eax
0x1400c1e90  mov     [rsp+1A0h+var_160], r8d
0x1400c1e95  mov     r8d, [rbx+0B4h]
0x1400c1e9c  mov     dword ptr [rsp+1A0h+var_168], r9d
0x1400c1ea1  mov     dword ptr [rsp+1A0h+var_170], r9d
0x1400c1ea6  mov     r9d, 1000h
0x1400c1eac  mov     dword ptr [rsp+1A0h+var_178], r9d
0x1400c1eb1  mov     qword ptr [rsp+1A0h+var_180], r9
0x1400c1eb6  call    ?CreateOneAllocation@VIDMM_GLOBAL@@QEAAJPEAVVIDMM_DEVICE@@K_K1KW4_DXGK_PAGESIZE@@2KKKU_D3DDDI_SEGMENTPREFERENCE@@U_DXGK_ALLOCATIONINFOFLAGS@@U_DXGK_ALLOCATIONINFOFLAGS2@@PEBVDXGADAPTERALLOCATION@@PEAX777KE7PEAVVIDMM_PAGE_TABLE_BASE@@PEAPEAUVIDMM_CROSSADAPTER_ALLOC@@PEAVVIDMM_FENCE_STORAGE_PAGE@@PEAPEAUVIDMM_GLOBAL_ALLOC@@PEAE@Z; VIDMM_GLOBAL::CreateOneAllocation(VIDMM_DEVICE *,ulong,unsigned __int64,unsigned __int64,ulong,_DXGK_PAGESIZE,_DXGK_PAGESIZE,ulong,ulong,ulong,_D3DDDI_SEGMENTPREFERENCE,_DXGK_ALLOCATIONINFOFLAGS,_DXGK_ALLOCATIONINFOFLAGS2,DXGADAPTERALLOCATION const *,void *,void *,void *,void *,ulong,uchar,void *,VIDMM_PAGE_TABLE_BASE *,VIDMM_CROSSADAPTER_ALLOC * *,VIDMM_FENCE_STORAGE_PAGE *,VIDMM_GLOBAL_ALLOC * *,uchar *)
0x1400c1ebb  movsxd  rdi, eax
0x1400c1ebe  test    eax, eax
0x1400c1ec0  jns     short loc_1400C1F0A
0x1400c1ec2  mov     rdx, rdi
0x1400c1ec5  mov     ecx, esi
0x1400c1ec7  call    cs:__imp_WdLogSingleEntry1
0x1400c1ece  nop     dword ptr [rax+rax+00h]
0x1400c1ed3  lea     r9, aFailedToCreate_14; "Failed to create allocation for a fence"...
0x1400c1eda  mov     cs:WdLogGlobalForLineNumber, 490h
0x1400c1ee4  xor     r13d, r13d
0x1400c1ee7  mov     [rsp+1A0h+var_168], r13
0x1400c1eec  mov     edx, 40000h
0x1400c1ef1  mov     [rsp+1A0h+var_170], r13
0x1400c1ef6  mov     [rsp+1A0h+var_178], r13
0x1400c1efb  mov     qword ptr [rsp+1A0h+var_180], rdi
0x1400c1f00  call    DxgkLogInternalTriageEvent
0x1400c1f05  jmp     loc_1400C2077
0x1400c1f0a  mov     rax, [rbx+88h]
0x1400c1f11  mov     rdx, r12; struct VIDMM_DEVICE *
0x1400c1f14  mov     r9d, [rbx+0B0h]
0x1400c1f1b  mov     rcx, r15; this
0x1400c1f1e  mov     r8, [rbp+40h+var_C0]; struct VIDMM_GLOBAL_ALLOC *
0x1400c1f22  shr     r9d, 1
0x1400c1f25  mov     [rbx+0D0h], rax
0x1400c1f2c  not     r9b
0x1400c1f2f  lea     rax, [rbp+40h+arg_18]
0x1400c1f33  and     r9b, sil; bool
0x1400c1f36  mov     [rsp+1A0h+var_178], rax; struct VIDMM_ALLOC **
0x1400c1f3b  mov     qword ptr [rsp+1A0h+var_180], 0; struct DXGALLOCATION *
0x1400c1f44  call    ?OpenOneAllocation@VIDMM_GLOBAL@@QEAAJPEAVVIDMM_DEVICE@@PEAUVIDMM_GLOBAL_ALLOC@@_NPEAVDXGALLOCATION@@PEAPEAUVIDMM_ALLOC@@@Z; VIDMM_GLOBAL::OpenOneAllocation(VIDMM_DEVICE *,VIDMM_GLOBAL_ALLOC *,bool,DXGALLOCATION *,VIDMM_ALLOC * *)
0x1400c1f49  movsxd  rdi, eax
0x1400c1f4c  test    eax, eax
0x1400c1f4e  jns     short loc_1400C1F77
0x1400c1f50  mov     rdx, rdi
0x1400c1f53  mov     ecx, esi
0x1400c1f55  call    cs:__imp_WdLogSingleEntry1
0x1400c1f5c  nop     dword ptr [rax+rax+00h]
0x1400c1f61  lea     r9, aFailedToCreate_29; "Failed to create VidMm allocation for a"...
0x1400c1f68  mov     cs:WdLogGlobalForLineNumber, 4A5h
0x1400c1f72  jmp     loc_1400C1EE4
0x1400c1f77  lea     rax, [rbp+40h+var_B0]
0x1400c1f7b  mov     r9, rsi; unsigned __int64
0x1400c1f7e  mov     [rsp+1A0h+var_170], rax; unsigned __int64 *
0x1400c1f83  lea     r8, [rbp+40h+arg_18]; struct VIDMM_MULTI_ALLOC **
0x1400c1f87  lea     rax, [rbp+40h+var_B8]
0x1400c1f8b  mov     rdx, r13; struct VIDMM_PAGING_QUEUE *
0x1400c1f8e  mov     [rsp+1A0h+var_178], rax; unsigned __int64 *
0x1400c1f93  mov     rcx, r15; this
0x1400c1f96  mov     dword ptr [rsp+1A0h+var_180], esi; unsigned int
0x1400c1f9a  call    ?MakeResident@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_QUEUE@@PEAPEAUVIDMM_MULTI_ALLOC@@_KKPEA_K3@Z; VIDMM_GLOBAL::MakeResident(VIDMM_PAGING_QUEUE *,VIDMM_MULTI_ALLOC * *,unsigned __int64,ulong,unsigned __int64 *,unsigned __int64 *)
0x1400c1f9f  movsxd  rdi, eax
0x1400c1fa2  cmp     edi, 103h
0x1400c1fa8  jnz     short loc_1400C2003
0x1400c1faa  mov     r8, [rbp+40h+var_B8]; unsigned __int64
0x1400c1fae  mov     rcx, r15; this
0x1400c1fb1  mov     rdx, [r13+58h]; struct _VIDSCH_SYNC_OBJECT *
0x1400c1fb5  call    ?WaitForFence@VIDMM_GLOBAL@@QEAAXPEAU_VIDSCH_SYNC_OBJECT@@_K@Z; VIDMM_GLOBAL::WaitForFence(_VIDSCH_SYNC_OBJECT *,unsigned __int64)
0x1400c1fba  xor     r13d, r13d
0x1400c1fbd  mov     edi, r13d
0x1400c1fc0  mov     ecx, 48h ; 'H'
0x1400c1fc5  mov     edx, 66336956h
0x1400c1fca  lea     r8d, [rcx-8]
0x1400c1fce  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400c1fd3  test    rax, rax
0x1400c1fd6  jz      short loc_1400C2031
0x1400c1fd8  mov     rcx, [rbp+40h+arg_18]
0x1400c1fdc  mov     [rax], rcx
0x1400c1fdf  mov     rcx, [rbp+40h+var_C0]
0x1400c1fe3  mov     [rax+8], rcx
0x1400c1fe7  mov     [rax+10h], r12
0x1400c1feb  mov     [rax+1Ch], esi
0x1400c1fee  mov     ecx, [rbx+0B0h]
0x1400c1ff4  mov     [rax+18h], ecx
0x1400c1ff7  mov     [rbx+0A8h], rax
0x1400c1ffe  jmp     loc_1400C20C5
0x1400c2003  xor     r13d, r13d
0x1400c2006  test    eax, eax
0x1400c2008  jns     short loc_1400C1FC0
0x1400c200a  mov     rdx, rdi
0x1400c200d  mov     ecx, esi
0x1400c200f  call    cs:__imp_WdLogSingleEntry1
0x1400c2016  nop     dword ptr [rax+rax+00h]
0x1400c201b  lea     r9, aMakeresidentFa; "MakeResident failed 0x%I64x"
0x1400c2022  mov     cs:WdLogGlobalForLineNumber, 4BFh
0x1400c202c  jmp     loc_1400C1EE7
0x1400c2031  mov     ecx, esi
0x1400c2033  call    cs:__imp_WdLogSingleEntry0
0x1400c203a  nop     dword ptr [rax+rax+00h]
0x1400c203f  mov     [rsp+1A0h+var_168], r13
0x1400c2044  lea     r9, aFailedToAlloca_58; "Failed to allocate pDevMapping"
0x1400c204b  mov     eax, 4C9h
0x1400c2050  mov     [rsp+1A0h+var_170], r13
0x1400c2055  mov     [rsp+1A0h+var_178], r13
0x1400c205a  mov     edx, 40000h
0x1400c205f  mov     cs:WdLogGlobalForLineNumber, eax
0x1400c2065  mov     qword ptr [rsp+1A0h+var_180], rax
0x1400c206a  call    DxgkLogInternalTriageEvent
0x1400c206f  mov     edi, 0C0000017h
0x1400c2074  mov     r14, r13
0x1400c2077  mov     rdx, [rbp+40h+arg_18]; struct VIDMM_ALLOC *
0x1400c207b  test    rdx, rdx
0x1400c207e  jz      short loc_1400C209B
0x1400c2080  mov     [rsp+1A0h+var_178], r13; struct _KEVENT **
0x1400c2085  xor     r9d, r9d; bool
0x1400c2088  xor     r8d, r8d; struct VIDMM_LOCAL_ALLOC **
0x1400c208b  mov     dword ptr [rsp+1A0h+var_180], 3; struct _D3DDDICB_DESTROYALLOCATION2FLAGS
0x1400c2093  mov     rcx, r15; this
0x1400c2096  call    ?CloseOneAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_ALLOC@@PEAPEAUVIDMM_LOCAL_ALLOC@@_NU_D3DDDICB_DESTROYALLOCATION2FLAGS@@PEAPEAU_KEVENT@@@Z; VIDMM_GLOBAL::CloseOneAllocation(VIDMM_ALLOC *,VIDMM_LOCAL_ALLOC * *,bool,_D3DDDICB_DESTROYALLOCATION2FLAGS,_KEVENT * *)
0x1400c209b  mov     r8, [rbp+40h+var_C0]; struct VIDMM_GLOBAL_ALLOC *
0x1400c209f  test    r8, r8
0x1400c20a2  jz      short loc_1400C20B1
0x1400c20a4  xor     r9d, r9d; bool
0x1400c20a7  xor     edx, edx; struct VIDMM_DEVICE *
0x1400c20a9  mov     rcx, r15; this
0x1400c20ac  call    ?DestroyOneAllocation@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_DEVICE@@PEAUVIDMM_GLOBAL_ALLOC@@_N@Z; VIDMM_GLOBAL::DestroyOneAllocation(VIDMM_DEVICE *,VIDMM_GLOBAL_ALLOC *,bool)
0x1400c20b1  test    r14, r14
0x1400c20b4  jz      short loc_1400C20C5
0x1400c20b6  mov     rcx, r14; void *
0x1400c20b9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400c20be  jmp     short loc_1400C20C5
0x1400c20c0  mov     edi, 0C0000001h
0x1400c20c5  lea     rcx, [rbp+40h+var_A8]; this
0x1400c20c9  call    ?Release@DXGAUTOPUSHLOCKFASTEXCLUSIVE@@QEAAXXZ; DXGAUTOPUSHLOCKFASTEXCLUSIVE::Release(void)
0x1400c20ce  mov     eax, edi
0x1400c20d0  mov     rbx, [rsp+1A0h+arg_0]
0x1400c20d8  add     rsp, 170h
0x1400c20df  pop     r15
0x1400c20e1  pop     r14
0x1400c20e3  pop     r13
0x1400c20e5  pop     r12
0x1400c20e7  pop     rdi
0x1400c20e8  pop     rsi
0x1400c20e9  pop     rbp
0x1400c20ea  retn
```
