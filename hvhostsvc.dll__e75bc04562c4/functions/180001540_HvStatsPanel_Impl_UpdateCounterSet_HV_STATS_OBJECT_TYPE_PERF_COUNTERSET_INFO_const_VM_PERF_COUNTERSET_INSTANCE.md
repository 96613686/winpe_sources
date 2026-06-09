# HvStatsPanel::Impl::UpdateCounterSet(_HV_STATS_OBJECT_TYPE,_PERF_COUNTERSET_INFO const *,_VM_PERF_COUNTERSET_INSTANCE *,std::array<_HV_STATS_PAGE const *,2> const &)

- ea: `0x180001540`
- end: `0x1800017c5`
- name: `?UpdateCounterSet@Impl@HvStatsPanel@@AEAAXW4_HV_STATS_OBJECT_TYPE@@PEBU_PERF_COUNTERSET_INFO@@PEAU_VM_PERF_COUNTERSET_INSTANCE@@AEBV?$array@PEBU_HV_STATS_PAGE@@$01@std@@@Z`
- size: `645`
- prototype: `void __fastcall(_QWORD *, unsigned int, __int64, PPERF_COUNTERSET_INSTANCE *, const struct _HV_STATS_PAGE **)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800013a0`

## callees

- `0x180001190`
- `0x1800012c0`
- `0x180001540`
- `0x1800017cc`
- `0x1800072d4`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x180001796`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x180001796`

## pseudocode

```c
void __fastcall HvStatsPanel::Impl::UpdateCounterSet(
        _QWORD *a1,
        unsigned int a2,
        __int64 a3,
        PPERF_COUNTERSET_INSTANCE *a4,
        const struct _HV_STATS_PAGE **a5)
{
  unsigned __int64 v5; // rbp
  ULONG *v6; // r14
  unsigned int v7; // r12d
  unsigned __int16 v10; // si
  unsigned __int16 v11; // ax
  unsigned __int16 v12; // dx
  int v13; // ecx
  __int16 v14; // r10
  ULONGLONG *v15; // r11
  int v16; // ecx
  int v17; // ecx
  unsigned int v18; // r11d
  int v19; // ebx
  unsigned __int16 v20; // dx
  unsigned __int64 v21; // rbx
  unsigned __int64 *LpCalculatedCounter; // rax
  int v23; // ebx
  unsigned __int16 v24; // dx
  unsigned __int64 v25; // rbx
  char *GroupTrait; // rax
  unsigned __int16 v27; // dx
  __int64 v28; // rax
  void *v29; // rcx
  HvStatsPanel::Impl *v30; // [rsp+20h] [rbp-68h]
  __int64 v31; // [rsp+40h] [rbp-48h]
  unsigned __int64 v32[8]; // [rsp+48h] [rbp-40h] BYREF
  unsigned __int64 v34; // [rsp+A0h] [rbp+18h]

  v5 = 0;
  v6 = (ULONG *)(a3 + 40);
  v7 = 0;
  v34 = 0;
  v31 = 0;
  if ( *(_DWORD *)(a3 + 32) )
  {
    while ( 1 )
    {
      v10 = *(_WORD *)v6 & 0x1FF;
      v11 = (*v6 >> 9) & 0xF;
      if ( v11 == 15 && v10 == 17 )
        goto LABEL_24;
      v32[0] = 0;
      v13 = *((_DWORD *)HvStatsPageUtil::details::GetGroupTrait(a2, v11) + 2);
      if ( !v13 )
        goto LABEL_24;
      v16 = v13 - 1;
      if ( !v16 )
        break;
      v17 = v16 - 1;
      if ( v17 )
      {
        if ( v17 != 1 )
          goto LABEL_21;
        if ( a2 == 2 )
        {
          if ( v5 )
          {
            v21 = v34;
          }
          else
          {
            v19 = *((unsigned __int16 *)HvStatsPageUtil::details::GetGroupTrait(2, 2u) + 1);
            v5 = *HvStatsPageUtil::details::GetPointerToCounterInternal(v18, v20, v18 - v19, a5);
            v21 = *HvStatsPageUtil::details::GetPointerToCounterInternal(2, 2u, 3 - v19, a5);
            v34 = v21;
          }
          v30 = (HvStatsPanel::Impl *)(a1[29] - a1[27]);
          LpCalculatedCounter = HvStatsPanel::Impl::GetLpCalculatedCounter(
                                  v30,
                                  v10,
                                  v5,
                                  v21,
                                  (unsigned __int64)v30,
                                  *a5,
                                  v32);
          goto LABEL_20;
        }
        if ( a2 == 65538 )
        {
          if ( v5 )
          {
            LODWORD(v25) = v34;
            v28 = v31;
          }
          else
          {
            v23 = *((unsigned __int16 *)HvStatsPageUtil::details::GetGroupTrait(65538, 2u) + 1);
            v5 = *HvStatsPageUtil::details::GetPointerToCounterInternal(65538, v24, 1 - v23, a5);
            v25 = *HvStatsPageUtil::details::GetPointerToCounterInternal(65538, 2u, 2 - v23, a5);
            v34 = v25;
            GroupTrait = HvStatsPageUtil::details::GetGroupTrait(65538, 3u);
            v28 = *HvStatsPageUtil::details::GetPointerToCounterInternal(
                     65538,
                     v27,
                     148 - (unsigned int)*((unsigned __int16 *)GroupTrait + 1),
                     a5);
            v31 = v28;
          }
          LpCalculatedCounter = (unsigned __int64 *)HvStatsPanel::Impl::GetVpCalculatedCounter(
                                                      (unsigned int)v32,
                                                      v10,
                                                      v5,
                                                      v25,
                                                      v28,
                                                      (__int64)a5,
                                                      (__int64)v32);
          goto LABEL_20;
        }
      }
      else if ( *a5 != (const struct _HV_STATS_PAGE *)v15 )
      {
        break;
      }
LABEL_24:
      ++v7;
      v6 += 8;
      if ( v7 >= *(_DWORD *)(a3 + 32) )
        return;
    }
    LpCalculatedCounter = HvStatsPageUtil::details::GetPointerToCounterInternal(a2, v12, (v14 & 0x1FFu) - 1, a5);
LABEL_20:
    v15 = LpCalculatedCounter;
LABEL_21:
    if ( v15 )
    {
      v29 = (void *)a1[2];
      if ( v29 )
        PerfSetULongLongCounterValue(v29, *a4, *v6, *v15);
    }
    goto LABEL_24;
  }
}

```

## disassembly

```asm
0x180001540  mov     [rsp+arg_8], rbx
0x180001545  mov     [rsp+arg_18], r9
0x18000154a  mov     [rsp+arg_0], rcx
0x18000154f  push    rbp
0x180001550  push    rsi
0x180001551  push    rdi
0x180001552  push    r12
0x180001554  push    r13
0x180001556  push    r14
0x180001558  push    r15
0x18000155a  sub     rsp, 50h
0x18000155e  xor     ebp, ebp
0x180001560  lea     r14, [r8+28h]
0x180001564  xor     r12d, r12d
0x180001567  mov     [rsp+88h+arg_10], rbp
0x18000156f  mov     r13, r8
0x180001572  mov     r15d, edx
0x180001575  mov     [rsp+88h+var_48], rbp
0x18000157a  cmp     [r8+20h], ebp
0x18000157e  jbe     loc_1800017AD
0x180001584  mov     rdi, [rsp+88h+arg_20]
0x18000158c  mov     r10d, [r14]
0x18000158f  mov     esi, 1FFh
0x180001594  and     si, [r14]
0x180001598  mov     eax, r10d
0x18000159b  shr     eax, 9
0x18000159e  and     ax, 0Fh
0x1800015a2  movzx   ebx, ax
0x1800015a5  cmp     ax, 0Fh
0x1800015a9  jnz     short loc_1800015B5
0x1800015ab  cmp     si, 11h
0x1800015af  jz      loc_18000179C
0x1800015b5  movzx   edx, bx
0x1800015b8  mov     [rsp+88h+var_40], 0
0x1800015c1  mov     ecx, r15d
0x1800015c4  xor     r11d, r11d
0x1800015c7  call    ?GetGroupTrait@details@HvStatsPageUtil@@YA@W4_HV_STATS_OBJECT_TYPE@@G@Z; HvStatsPageUtil::details::GetGroupTrait(_HV_STATS_OBJECT_TYPE,ushort)
0x1800015cc  mov     ecx, [rax+8]
0x1800015cf  test    ecx, ecx
0x1800015d1  jz      loc_18000179C
0x1800015d7  sub     ecx, 1
0x1800015da  jz      loc_180001756
0x1800015e0  sub     ecx, 1
0x1800015e3  jz      loc_180001751
0x1800015e9  cmp     ecx, 1
0x1800015ec  jnz     loc_18000176F
0x1800015f2  lea     r11d, [rcx+1]
0x1800015f6  cmp     r15d, r11d
0x1800015f9  jnz     loc_180001694
0x1800015ff  test    rbp, rbp
0x180001602  jnz     short loc_18000164C
0x180001604  mov     edx, r11d
0x180001607  mov     ecx, r11d
0x18000160a  call    ?GetGroupTrait@details@HvStatsPageUtil@@YA@W4_HV_STATS_OBJECT_TYPE@@G@Z; HvStatsPageUtil::details::GetGroupTrait(_HV_STATS_OBJECT_TYPE,ushort)
0x18000160f  mov     r8d, r11d
0x180001612  mov     r9, rdi
0x180001615  mov     ecx, r11d
0x180001618  movzx   ebx, word ptr [rax+2]
0x18000161c  sub     r8d, ebx
0x18000161f  call    ?GetPointerToCounterInternal@details@HvStatsPageUtil@@YAPEA_KW4_HV_STATS_OBJECT_TYPE@@GIAEBV?$array@PEBU_HV_STATS_PAGE@@$01@std@@@Z; HvStatsPageUtil::details::GetPointerToCounterInternal(_HV_STATS_OBJECT_TYPE,ushort,uint,std::array<_HV_STATS_PAGE const *,2> const &)
0x180001624  mov     r8d, 3
0x18000162a  mov     edx, 2
0x18000162f  sub     r8d, ebx
0x180001632  mov     ecx, edx
0x180001634  mov     r9, rdi
0x180001637  mov     rbp, [rax]
0x18000163a  call    ?GetPointerToCounterInternal@details@HvStatsPageUtil@@YAPEA_KW4_HV_STATS_OBJECT_TYPE@@GIAEBV?$array@PEBU_HV_STATS_PAGE@@$01@std@@@Z; HvStatsPageUtil::details::GetPointerToCounterInternal(_HV_STATS_OBJECT_TYPE,ushort,uint,std::array<_HV_STATS_PAGE const *,2> const &)
0x18000163f  mov     rbx, [rax]
0x180001642  mov     [rsp+88h+arg_10], rbx
0x18000164a  jmp     short loc_180001654
0x18000164c  mov     rbx, [rsp+88h+arg_10]
0x180001654  mov     rax, [rsp+88h+arg_0]
0x18000165c  mov     r9, rbx; unsigned __int64
0x18000165f  movzx   edx, si; unsigned int
0x180001662  mov     r8, rbp; unsigned __int64
0x180001665  mov     rcx, [rax+0E8h]
0x18000166c  sub     rcx, [rax+0D8h]; this
0x180001673  lea     rax, [rsp+88h+var_40]
0x180001678  mov     [rsp+88h+var_58], rax; unsigned __int64 *
0x18000167d  mov     rax, [rdi]
0x180001680  mov     [rsp+88h+var_60], rax; struct _HV_STATS_PAGE *
0x180001685  mov     [rsp+88h+var_68], rcx; unsigned __int64
0x18000168a  call    ?GetLpCalculatedCounter@Impl@HvStatsPanel@@AEAAPEA_KI_K00PEBU_HV_STATS_PAGE@@PEA_K@Z; HvStatsPanel::Impl::GetLpCalculatedCounter(uint,unsigned __int64,unsigned __int64,unsigned __int64,_HV_STATS_PAGE const *,unsigned __int64 *)
0x18000168f  jmp     loc_18000176C
0x180001694  cmp     r15d, 10002h
0x18000169b  jnz     loc_18000179C
0x1800016a1  test    rbp, rbp
0x1800016a4  jnz     short loc_180001720
0x1800016a6  mov     edx, r11d
0x1800016a9  mov     ecx, r15d
0x1800016ac  call    ?GetGroupTrait@details@HvStatsPageUtil@@YA@W4_HV_STATS_OBJECT_TYPE@@G@Z; HvStatsPageUtil::details::GetGroupTrait(_HV_STATS_OBJECT_TYPE,ushort)
0x1800016b1  lea     r8d, [rbp+1]
0x1800016b5  mov     r9, rdi
0x1800016b8  mov     ecx, r15d
0x1800016bb  movzx   ebx, word ptr [rax+2]
0x1800016bf  sub     r8d, ebx
0x1800016c2  call    ?GetPointerToCounterInternal@details@HvStatsPageUtil@@YAPEA_KW4_HV_STATS_OBJECT_TYPE@@GIAEBV?$array@PEBU_HV_STATS_PAGE@@$01@std@@@Z; HvStatsPageUtil::details::GetPointerToCounterInternal(_HV_STATS_OBJECT_TYPE,ushort,uint,std::array<_HV_STATS_PAGE const *,2> const &)
0x1800016c7  mov     r8d, 2
0x1800016cd  mov     edx, 2
0x1800016d2  sub     r8d, ebx
0x1800016d5  mov     r9, rdi
0x1800016d8  mov     ecx, r15d
0x1800016db  mov     rbp, [rax]
0x1800016de  call    ?GetPointerToCounterInternal@details@HvStatsPageUtil@@YAPEA_KW4_HV_STATS_OBJECT_TYPE@@GIAEBV?$array@PEBU_HV_STATS_PAGE@@$01@std@@@Z; HvStatsPageUtil::details::GetPointerToCounterInternal(_HV_STATS_OBJECT_TYPE,ushort,uint,std::array<_HV_STATS_PAGE const *,2> const &)
0x1800016e3  mov     edx, 3
0x1800016e8  mov     ecx, r15d
0x1800016eb  mov     r10d, r15d
0x1800016ee  mov     rbx, [rax]
0x1800016f1  mov     [rsp+88h+arg_10], rbx
0x1800016f9  call    ?GetGroupTrait@details@HvStatsPageUtil@@YA@W4_HV_STATS_OBJECT_TYPE@@G@Z; HvStatsPageUtil::details::GetGroupTrait(_HV_STATS_OBJECT_TYPE,ushort)
0x1800016fe  mov     r8d, 94h
0x180001704  mov     r9, rdi
0x180001707  movzx   ecx, word ptr [rax+2]
0x18000170b  sub     r8d, ecx
0x18000170e  mov     ecx, r15d
0x180001711  call    ?GetPointerToCounterInternal@details@HvStatsPageUtil@@YAPEA_KW4_HV_STATS_OBJECT_TYPE@@GIAEBV?$array@PEBU_HV_STATS_PAGE@@$01@std@@@Z; HvStatsPageUtil::details::GetPointerToCounterInternal(_HV_STATS_OBJECT_TYPE,ushort,uint,std::array<_HV_STATS_PAGE const *,2> const &)
0x180001716  mov     rax, [rax]
0x180001719  mov     [rsp+88h+var_48], rax
0x18000171e  jmp     short loc_18000172D
0x180001720  mov     rbx, [rsp+88h+arg_10]
0x180001728  mov     rax, [rsp+88h+var_48]
0x18000172d  lea     rcx, [rsp+88h+var_40]
0x180001732  movzx   edx, si
0x180001735  mov     [rsp+88h+var_58], rcx
0x18000173a  mov     r9, rbx
0x18000173d  mov     [rsp+88h+var_60], rdi
0x180001742  mov     r8, rbp
0x180001745  mov     [rsp+88h+var_68], rax
0x18000174a  call    ?GetVpCalculatedCounter@Impl@HvStatsPanel@@AEAAPEA_KI_K00AEBV?$array@PEBU_HV_STATS_PAGE@@$01@std@@PEA_K@Z; HvStatsPanel::Impl::GetVpCalculatedCounter(uint,unsigned __int64,unsigned __int64,unsigned __int64,std::array<_HV_STATS_PAGE const *,2> const &,unsigned __int64 *)
0x18000174f  jmp     short loc_18000176C
0x180001751  cmp     [rdi], r11
0x180001754  jz      short loc_18000179C
0x180001756  and     r10d, 1FFh
0x18000175d  mov     r9, rdi
0x180001760  mov     ecx, r15d
0x180001763  lea     r8d, [r10-1]
0x180001767  call    ?GetPointerToCounterInternal@details@HvStatsPageUtil@@YAPEA_KW4_HV_STATS_OBJECT_TYPE@@GIAEBV?$array@PEBU_HV_STATS_PAGE@@$01@std@@@Z; HvStatsPageUtil::details::GetPointerToCounterInternal(_HV_STATS_OBJECT_TYPE,ushort,uint,std::array<_HV_STATS_PAGE const *,2> const &)
0x18000176c  mov     r11, rax
0x18000176f  test    r11, r11
0x180001772  jz      short loc_18000179C
0x180001774  mov     rax, [rsp+88h+arg_0]
0x18000177c  mov     rcx, [rax+10h]; Provider
0x180001780  test    rcx, rcx
0x180001783  jz      short loc_18000179C
0x180001785  mov     rax, [rsp+88h+arg_18]
0x18000178d  mov     r9, [r11]; Value
0x180001790  mov     r8d, [r14]; CounterId
0x180001793  mov     rdx, [rax]; Instance
0x180001796  call    cs:__imp_PerfSetULongLongCounterValue
0x18000179c  inc     r12d
0x18000179f  add     r14, 20h ; ' '
0x1800017a3  cmp     r12d, [r13+20h]
0x1800017a7  jb      loc_18000158C
0x1800017ad  mov     rbx, [rsp+88h+arg_8]
0x1800017b5  add     rsp, 50h
0x1800017b9  pop     r15
0x1800017bb  pop     r14
0x1800017bd  pop     r13
0x1800017bf  pop     r12
0x1800017c1  pop     rdi
0x1800017c2  pop     rsi
0x1800017c3  pop     rbp
0x1800017c4  retn
```
