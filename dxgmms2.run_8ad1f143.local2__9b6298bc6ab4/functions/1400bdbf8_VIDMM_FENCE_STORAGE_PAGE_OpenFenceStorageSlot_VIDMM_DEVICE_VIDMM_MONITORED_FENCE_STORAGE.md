# VIDMM_FENCE_STORAGE_PAGE::OpenFenceStorageSlot(VIDMM_DEVICE *,VIDMM_MONITORED_FENCE_STORAGE *)

- ea: `0x1400bdbf8`
- end: `0x1400bdffd`
- name: `?OpenFenceStorageSlot@VIDMM_FENCE_STORAGE_PAGE@@QEAAJPEAVVIDMM_DEVICE@@PEAUVIDMM_MONITORED_FENCE_STORAGE@@@Z`
- size: `1029`
- prototype: `__int64 __fastcall(VIDMM_FENCE_STORAGE_PAGE *__hidden this, struct VIDMM_DEVICE *, struct VIDMM_MONITORED_FENCE_STORAGE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1400be680`

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x14002e850`
- `0x14002e950`
- `0x140030ae0`
- `0x140032a04`
- `0x1400bdbf8`
- `0x1400e1d30`
- `0x1400e84b4`
- `0x140102390`
- `0x14010416c`
- `0x140105808`

## import_xrefs

- `watchdog!WdLogSingleEntry0` at `0x1400bdf44`
- `watchdog!WdLogSingleEntry0` at `0x1400bdf44`
- `watchdog!WdLogSingleEntry1` at `0x1400bdddb`
- `watchdog!WdLogSingleEntry1` at `0x1400bde66`
- `watchdog!WdLogSingleEntry1` at `0x1400bdf20`
- `watchdog!WdLogSingleEntry1` at `0x1400bdddb`
- `watchdog!WdLogSingleEntry1` at `0x1400bde66`
- `watchdog!WdLogSingleEntry1` at `0x1400bdf20`

## string_xrefs

- `0x1400bdde7`: `Failed to create allocation for a fence storage page: 0x%I64x`
- `0x1400bde72`: `Failed to create VidMm allocation for a fence storage page: 0x%I64x`
- `0x1400bdf2c`: `MakeResident failed 0x%I64x`

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
  struct VIDMM_GLOBAL_ALLOC *v29; // [rsp+D0h] [rbp-80h] BYREF
  unsigned __int64 v30; // [rsp+D8h] [rbp-78h] BYREF
  unsigned __int64 v31; // [rsp+E0h] [rbp-70h] BYREF
  _BYTE v32[56]; // [rsp+E8h] [rbp-68h] BYREF
  __m128i v33; // [rsp+120h] [rbp-30h]
  __int128 v34; // [rsp+130h] [rbp-20h]
  __int128 v35; // [rsp+140h] [rbp-10h]
  __int64 v36; // [rsp+150h] [rbp+0h]
  char v37; // [rsp+1B0h] [rbp+60h] BYREF
  struct VIDMM_MULTI_ALLOC *v38; // [rsp+1B8h] [rbp+68h] BYREF

  if ( (*((_BYTE *)a3 + 40) & 4) == 0 )
    return 0;
  v7 = (VIDMM_GLOBAL *)*a2;
  v8 = (*a2)[4560][*((unsigned int *)this + 39)];
  v38 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v9 = *a2[9];
  DXGAUTOPUSHLOCKFASTEXCLUSIVE::DXGAUTOPUSHLOCKFASTEXCLUSIVE(
    (DXGAUTOPUSHLOCKFASTEXCLUSIVE *)v32,
    (VIDMM_FENCE_STORAGE_PAGE *)((char *)this + 72),
    (bool)a3);
  if ( *((struct _VIDSCH_SYNC_OBJECT *****)this + 17) != a2 )
    goto LABEL_26;
  v10 = *((_QWORD *)this + 18);
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
      if ( (*((_DWORD *)this + 38) & 1) != 0 )
        v17 = v35 | 1;
      v37 = 0;
      v18 = VIDMM_GLOBAL::CreateOneAllocation(
              (__int64)v7,
              0,
              *((_DWORD *)this + 39),
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
              this,
              &v29,
              &v37);
      v11 = v18;
      if ( v18 >= 0 )
      {
        v22 = v29;
        v23 = *((_DWORD *)this + 38) >> 1;
        *((_QWORD *)this + 23) = *((_QWORD *)this + 14);
        v24 = VIDMM_GLOBAL::OpenOneAllocation(v7, (struct VIDMM_PROCESS **)a2, v22, (v23 & 1) == 0, 0, &v38);
        v11 = v24;
        if ( v24 >= 0 )
        {
          Resident = VIDMM_GLOBAL::MakeResident(v7, (struct VIDMM_PAGING_QUEUE *)v9, &v38, 1u, 1, &v30, &v31);
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
            WdLogGlobalForLineNumber = 1112;
            goto LABEL_11;
          }
          v26 = operator new(72, 1714645334, 64);
          if ( v26 )
          {
            *(_QWORD *)v26 = v38;
            *(_QWORD *)(v26 + 8) = v29;
            *(_QWORD *)(v26 + 16) = a2;
            *(_DWORD *)(v26 + 28) = 1;
            *(_DWORD *)(v26 + 24) = *((_DWORD *)this + 38);
            *((_QWORD *)this + 18) = v26;
            goto LABEL_27;
          }
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 1122;
          DxgkLogInternalTriageEvent(v27, 0x40000, v28, (unsigned int)L"Failed to allocate pDevMapping", 1122, 0, 0, 0);
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
        WdLogGlobalForLineNumber = 1086;
      }
      else
      {
        WdLogSingleEntry1(1, v18);
        v21 = L"Failed to create allocation for a fence storage page: 0x%I64x";
        WdLogGlobalForLineNumber = 1065;
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
0x1400bdbf8  mov     [rsp-8+arg_0], rbx
0x1400bdbfd  push    rbp
0x1400bdbfe  push    rsi
0x1400bdbff  push    rdi
0x1400bdc00  push    r12
0x1400bdc02  push    r13
0x1400bdc04  push    r14
0x1400bdc06  push    r15
0x1400bdc08  lea     rbp, [rsp-10h]
0x1400bdc0d  sub     rsp, 160h
0x1400bdc14  test    byte ptr [r8+28h], 4
0x1400bdc19  mov     rdi, r8
0x1400bdc1c  mov     r12, rdx
0x1400bdc1f  mov     rbx, rcx
0x1400bdc22  jnz     short loc_1400BDC2B
0x1400bdc24  xor     eax, eax
0x1400bdc26  jmp     loc_1400BDFE1
0x1400bdc2b  mov     r15, [rdx]
0x1400bdc2e  mov     ecx, [rcx+9Ch]
0x1400bdc34  mov     rax, [r15+8E80h]
0x1400bdc3b  mov     rsi, [rax+rcx*8]
0x1400bdc3f  xor     eax, eax
0x1400bdc41  mov     [rbp+40h+arg_18], rax
0x1400bdc45  lea     rcx, [rbp+40h+var_A8]; this
0x1400bdc49  mov     [rbp+40h+var_C0], rax
0x1400bdc4d  mov     [rbp+40h+var_B8], rax
0x1400bdc51  mov     [rbp+40h+var_B0], rax
0x1400bdc55  mov     rax, [rdx+48h]
0x1400bdc59  lea     rdx, [rbx+48h]; struct DXGPUSHLOCKFAST *
0x1400bdc5d  mov     r13, [rax]
0x1400bdc60  call    ??0DXGAUTOPUSHLOCKFASTEXCLUSIVE@@QEAA@AEAVDXGPUSHLOCKFAST@@_N@Z; DXGAUTOPUSHLOCKFASTEXCLUSIVE::DXGAUTOPUSHLOCKFASTEXCLUSIVE(DXGPUSHLOCKFAST &,bool)
0x1400bdc65  cmp     [rbx+88h], r12
0x1400bdc6c  jnz     loc_1400BDFD1
0x1400bdc72  mov     r14, [rbx+90h]
0x1400bdc79  xor     r9d, r9d
0x1400bdc7c  test    r14, r14
0x1400bdc7f  jz      short loc_1400BDC91
0x1400bdc81  lea     esi, [r9+1]
0x1400bdc85  mov     edi, r9d
0x1400bdc88  add     [r14+1Ch], esi
0x1400bdc8c  jmp     loc_1400BDFD6
0x1400bdc91  movsxd  rax, dword ptr [rdi+30h]
0x1400bdc95  lea     rcx, [rax+rax*2]
0x1400bdc99  movsxd  rax, dword ptr [rdi+2Ch]
0x1400bdc9d  add     rcx, rax
0x1400bdca0  mov     rax, [r15+8E80h]
0x1400bdca7  imul    r8, rcx, 58h ; 'X'
0x1400bdcab  mov     ecx, [rdi+38h]
0x1400bdcae  mov     rdx, [rax+rcx*8]
0x1400bdcb2  movups  xmm2, xmmword ptr [r8+rdx+0A8h]
0x1400bdcbb  movups  xmm0, xmmword ptr [r8+rdx+0B8h]
0x1400bdcc4  movups  xmm1, xmmword ptr [r8+rdx+0C8h]
0x1400bdccd  movaps  [rbp+40h+var_70], xmm2
0x1400bdcd1  psrldq  xmm2, 0Ch
0x1400bdcd6  movaps  [rbp+40h+var_60], xmm0
0x1400bdcda  movsd   xmm0, qword ptr [r8+rdx+0D8h]
0x1400bdce4  movd    r8d, xmm2
0x1400bdce9  movaps  [rbp+40h+var_50], xmm1
0x1400bdced  movsd   [rbp+40h+var_40], xmm0
0x1400bdcf2  test    [rsi+54h], r8d
0x1400bdcf6  jz      loc_1400BDFD1
0x1400bdcfc  mov     eax, [rbx+98h]
0x1400bdd02  mov     esi, 1
0x1400bdd07  mov     edx, dword ptr [rbp+40h+var_50]
0x1400bdd0a  test    sil, al
0x1400bdd0d  jz      short loc_1400BDD11
0x1400bdd0f  or      edx, esi
0x1400bdd11  mov     eax, dword ptr [rbp+40h+var_40+4]
0x1400bdd14  lea     rcx, [rbp+40h+arg_10]
0x1400bdd18  mov     [rsp+190h+var_C8], rcx
0x1400bdd20  or      edx, 20400000h
0x1400bdd26  lea     rcx, [rbp+40h+var_C0]
0x1400bdd2a  mov     [rbp+40h+arg_10], r9b
0x1400bdd2e  mov     [rsp+190h+var_D0], rcx
0x1400bdd36  mov     rcx, [rbx+68h]
0x1400bdd3a  mov     [rsp+190h+var_D8], rbx
0x1400bdd42  mov     [rsp+190h+var_E0], r9
0x1400bdd4a  mov     [rsp+190h+var_E8], r9
0x1400bdd52  mov     [rsp+190h+var_F0], r9
0x1400bdd5a  mov     [rsp+190h+var_F8], r9b
0x1400bdd62  mov     [rsp+190h+var_100], r9d
0x1400bdd6a  mov     [rsp+190h+var_108], r9
0x1400bdd72  mov     [rsp+190h+var_110], r9
0x1400bdd7a  mov     [rsp+190h+var_118], rcx
0x1400bdd7f  mov     rcx, r15
0x1400bdd82  mov     [rsp+190h+var_120], r9
0x1400bdd87  mov     [rsp+190h+var_128], eax
0x1400bdd8b  mov     eax, dword ptr [rbp+40h+var_70+4]
0x1400bdd8e  mov     [rsp+190h+var_130], edx
0x1400bdd92  xor     edx, edx
0x1400bdd94  mov     [rsp+190h+var_138], eax
0x1400bdd98  mov     eax, dword ptr [rbp+40h+var_60]
0x1400bdd9b  mov     [rsp+190h+var_140], r9d
0x1400bdda0  mov     [rsp+190h+var_148], eax
0x1400bdda4  mov     [rsp+190h+var_150], r8d
0x1400bdda9  mov     r8d, [rbx+9Ch]
0x1400bddb0  mov     dword ptr [rsp+190h+var_158], r9d
0x1400bddb5  mov     dword ptr [rsp+190h+var_160], r9d
0x1400bddba  mov     r9d, 1000h
0x1400bddc0  mov     dword ptr [rsp+190h+var_168], r9d
0x1400bddc5  mov     qword ptr [rsp+190h+var_170], r9
0x1400bddca  call    ?CreateOneAllocation@VIDMM_GLOBAL@@QEAAJPEAVVIDMM_DEVICE@@K_K1KW4_DXGK_PAGESIZE@@2KKKU_D3DDDI_SEGMENTPREFERENCE@@U_DXGK_ALLOCATIONINFOFLAGS@@U_DXGK_ALLOCATIONINFOFLAGS2@@PEBVDXGADAPTERALLOCATION@@PEAX77KE7PEAVVIDMM_PAGE_TABLE_BASE@@PEAPEAUVIDMM_CROSSADAPTER_ALLOC@@PEAVVIDMM_FENCE_STORAGE_PAGE@@PEAPEAUVIDMM_GLOBAL_ALLOC@@PEAE@Z; VIDMM_GLOBAL::CreateOneAllocation(VIDMM_DEVICE *,ulong,unsigned __int64,unsigned __int64,ulong,_DXGK_PAGESIZE,_DXGK_PAGESIZE,ulong,ulong,ulong,_D3DDDI_SEGMENTPREFERENCE,_DXGK_ALLOCATIONINFOFLAGS,_DXGK_ALLOCATIONINFOFLAGS2,DXGADAPTERALLOCATION const *,void *,void *,void *,ulong,uchar,void *,VIDMM_PAGE_TABLE_BASE *,VIDMM_CROSSADAPTER_ALLOC * *,VIDMM_FENCE_STORAGE_PAGE *,VIDMM_GLOBAL_ALLOC * *,uchar *)
0x1400bddcf  movsxd  rdi, eax
0x1400bddd2  test    eax, eax
0x1400bddd4  jns     short loc_1400BDE1E
0x1400bddd6  mov     rdx, rdi
0x1400bddd9  mov     ecx, esi
0x1400bdddb  call    cs:__imp_WdLogSingleEntry1
0x1400bdde2  nop     dword ptr [rax+rax+00h]
0x1400bdde7  lea     r9, aFailedToCreate_14; "Failed to create allocation for a fence"...
0x1400bddee  mov     cs:WdLogGlobalForLineNumber, 429h
0x1400bddf8  xor     r13d, r13d
0x1400bddfb  mov     [rsp+190h+var_158], r13
0x1400bde00  mov     edx, 40000h
0x1400bde05  mov     [rsp+190h+var_160], r13
0x1400bde0a  mov     [rsp+190h+var_168], r13
0x1400bde0f  mov     qword ptr [rsp+190h+var_170], rdi
0x1400bde14  call    DxgkLogInternalTriageEvent
0x1400bde19  jmp     loc_1400BDF88
0x1400bde1e  mov     rax, [rbx+70h]
0x1400bde22  mov     rdx, r12; struct VIDMM_DEVICE *
0x1400bde25  mov     r9d, [rbx+98h]
0x1400bde2c  mov     rcx, r15; this
0x1400bde2f  mov     r8, [rbp+40h+var_C0]; struct VIDMM_GLOBAL_ALLOC *
0x1400bde33  shr     r9d, 1
0x1400bde36  mov     [rbx+0B8h], rax
0x1400bde3d  not     r9b
0x1400bde40  lea     rax, [rbp+40h+arg_18]
0x1400bde44  and     r9b, sil; bool
0x1400bde47  mov     [rsp+190h+var_168], rax; struct VIDMM_ALLOC **
0x1400bde4c  mov     qword ptr [rsp+190h+var_170], 0; struct DXGALLOCATION *
0x1400bde55  call    ?OpenOneAllocation@VIDMM_GLOBAL@@QEAAJPEAVVIDMM_DEVICE@@PEAUVIDMM_GLOBAL_ALLOC@@_NPEAVDXGALLOCATION@@PEAPEAUVIDMM_ALLOC@@@Z; VIDMM_GLOBAL::OpenOneAllocation(VIDMM_DEVICE *,VIDMM_GLOBAL_ALLOC *,bool,DXGALLOCATION *,VIDMM_ALLOC * *)
0x1400bde5a  movsxd  rdi, eax
0x1400bde5d  test    eax, eax
0x1400bde5f  jns     short loc_1400BDE88
0x1400bde61  mov     rdx, rdi
0x1400bde64  mov     ecx, esi
0x1400bde66  call    cs:__imp_WdLogSingleEntry1
0x1400bde6d  nop     dword ptr [rax+rax+00h]
0x1400bde72  lea     r9, aFailedToCreate_29; "Failed to create VidMm allocation for a"...
0x1400bde79  mov     cs:WdLogGlobalForLineNumber, 43Eh
0x1400bde83  jmp     loc_1400BDDF8
0x1400bde88  lea     rax, [rbp+40h+var_B0]
0x1400bde8c  mov     r9, rsi; unsigned __int64
0x1400bde8f  mov     [rsp+190h+var_160], rax; unsigned __int64 *
0x1400bde94  lea     r8, [rbp+40h+arg_18]; struct VIDMM_MULTI_ALLOC **
0x1400bde98  lea     rax, [rbp+40h+var_B8]
0x1400bde9c  mov     rdx, r13; struct VIDMM_PAGING_QUEUE *
0x1400bde9f  mov     [rsp+190h+var_168], rax; unsigned __int64 *
0x1400bdea4  mov     rcx, r15; this
0x1400bdea7  mov     dword ptr [rsp+190h+var_170], esi; char
0x1400bdeab  call    ?MakeResident@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_PAGING_QUEUE@@PEAPEAUVIDMM_MULTI_ALLOC@@_KKPEA_K3@Z; VIDMM_GLOBAL::MakeResident(VIDMM_PAGING_QUEUE *,VIDMM_MULTI_ALLOC * *,unsigned __int64,ulong,unsigned __int64 *,unsigned __int64 *)
0x1400bdeb0  movsxd  rdi, eax
0x1400bdeb3  cmp     edi, 103h
0x1400bdeb9  jnz     short loc_1400BDF14
0x1400bdebb  mov     r8, [rbp+40h+var_B8]; unsigned __int64
0x1400bdebf  mov     rcx, r15; this
0x1400bdec2  mov     rdx, [r13+58h]; struct _VIDSCH_SYNC_OBJECT *
0x1400bdec6  call    ?WaitForFence@VIDMM_GLOBAL@@QEAAXPEAU_VIDSCH_SYNC_OBJECT@@_K@Z; VIDMM_GLOBAL::WaitForFence(_VIDSCH_SYNC_OBJECT *,unsigned __int64)
0x1400bdecb  xor     r13d, r13d
0x1400bdece  mov     edi, r13d
0x1400bded1  mov     ecx, 48h ; 'H'
0x1400bded6  mov     edx, 66336956h
0x1400bdedb  lea     r8d, [rcx-8]
0x1400bdedf  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400bdee4  test    rax, rax
0x1400bdee7  jz      short loc_1400BDF42
0x1400bdee9  mov     rcx, [rbp+40h+arg_18]
0x1400bdeed  mov     [rax], rcx
0x1400bdef0  mov     rcx, [rbp+40h+var_C0]
0x1400bdef4  mov     [rax+8], rcx
0x1400bdef8  mov     [rax+10h], r12
0x1400bdefc  mov     [rax+1Ch], esi
0x1400bdeff  mov     ecx, [rbx+98h]
0x1400bdf05  mov     [rax+18h], ecx
0x1400bdf08  mov     [rbx+90h], rax
0x1400bdf0f  jmp     loc_1400BDFD6
0x1400bdf14  xor     r13d, r13d
0x1400bdf17  test    eax, eax
0x1400bdf19  jns     short loc_1400BDED1
0x1400bdf1b  mov     rdx, rdi
0x1400bdf1e  mov     ecx, esi
0x1400bdf20  call    cs:__imp_WdLogSingleEntry1
0x1400bdf27  nop     dword ptr [rax+rax+00h]
0x1400bdf2c  lea     r9, aMakeresidentFa; "MakeResident failed 0x%I64x"
0x1400bdf33  mov     cs:WdLogGlobalForLineNumber, 458h
0x1400bdf3d  jmp     loc_1400BDDFB
0x1400bdf42  mov     ecx, esi
0x1400bdf44  call    cs:__imp_WdLogSingleEntry0
0x1400bdf4b  nop     dword ptr [rax+rax+00h]
0x1400bdf50  mov     [rsp+190h+var_158], r13
0x1400bdf55  lea     r9, aFailedToAlloca_54; "Failed to allocate pDevMapping"
0x1400bdf5c  mov     eax, 462h
0x1400bdf61  mov     [rsp+190h+var_160], r13
0x1400bdf66  mov     [rsp+190h+var_168], r13
0x1400bdf6b  mov     edx, 40000h
0x1400bdf70  mov     cs:WdLogGlobalForLineNumber, eax
0x1400bdf76  mov     qword ptr [rsp+190h+var_170], rax
0x1400bdf7b  call    DxgkLogInternalTriageEvent
0x1400bdf80  mov     edi, 0C0000017h
0x1400bdf85  mov     r14, r13
0x1400bdf88  mov     rdx, [rbp+40h+arg_18]; struct VIDMM_ALLOC *
0x1400bdf8c  test    rdx, rdx
0x1400bdf8f  jz      short loc_1400BDFAC
0x1400bdf91  mov     [rsp+190h+var_168], r13; struct _KEVENT **
0x1400bdf96  xor     r9d, r9d; bool
0x1400bdf99  xor     r8d, r8d; struct VIDMM_LOCAL_ALLOC **
0x1400bdf9c  mov     dword ptr [rsp+190h+var_170], 3; struct _D3DDDICB_DESTROYALLOCATION2FLAGS
0x1400bdfa4  mov     rcx, r15; this
0x1400bdfa7  call    ?CloseOneAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_ALLOC@@PEAPEAUVIDMM_LOCAL_ALLOC@@_NU_D3DDDICB_DESTROYALLOCATION2FLAGS@@PEAPEAU_KEVENT@@@Z; VIDMM_GLOBAL::CloseOneAllocation(VIDMM_ALLOC *,VIDMM_LOCAL_ALLOC * *,bool,_D3DDDICB_DESTROYALLOCATION2FLAGS,_KEVENT * *)
0x1400bdfac  mov     r8, [rbp+40h+var_C0]; struct VIDMM_GLOBAL_ALLOC *
0x1400bdfb0  test    r8, r8
0x1400bdfb3  jz      short loc_1400BDFC2
0x1400bdfb5  xor     r9d, r9d; bool
0x1400bdfb8  xor     edx, edx; struct VIDMM_DEVICE *
0x1400bdfba  mov     rcx, r15; this
0x1400bdfbd  call    ?DestroyOneAllocation@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_DEVICE@@PEAUVIDMM_GLOBAL_ALLOC@@_N@Z; VIDMM_GLOBAL::DestroyOneAllocation(VIDMM_DEVICE *,VIDMM_GLOBAL_ALLOC *,bool)
0x1400bdfc2  test    r14, r14
0x1400bdfc5  jz      short loc_1400BDFD6
0x1400bdfc7  mov     rcx, r14; void *
0x1400bdfca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400bdfcf  jmp     short loc_1400BDFD6
0x1400bdfd1  mov     edi, 0C0000001h
0x1400bdfd6  lea     rcx, [rbp+40h+var_A8]; this
0x1400bdfda  call    ?Release@DXGAUTOPUSHLOCKFASTEXCLUSIVE@@QEAAXXZ; DXGAUTOPUSHLOCKFASTEXCLUSIVE::Release(void)
0x1400bdfdf  mov     eax, edi
0x1400bdfe1  mov     rbx, [rsp+190h+arg_0]
0x1400bdfe9  add     rsp, 160h
0x1400bdff0  pop     r15
0x1400bdff2  pop     r14
0x1400bdff4  pop     r13
0x1400bdff6  pop     r12
0x1400bdff8  pop     rdi
0x1400bdff9  pop     rsi
0x1400bdffa  pop     rbp
0x1400bdffb  retn
```
