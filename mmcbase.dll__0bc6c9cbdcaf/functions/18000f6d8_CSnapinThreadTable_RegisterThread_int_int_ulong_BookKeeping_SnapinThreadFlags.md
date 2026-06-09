# CSnapinThreadTable::RegisterThread(int,int,ulong,BookKeeping::SnapinThreadFlags)

- ea: `0x18000f6d8`
- end: `0x18000f8d3`
- name: `?RegisterThread@CSnapinThreadTable@@QEAAJHHKW4SnapinThreadFlags@BookKeeping@@@Z`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000dd40`

## callees

- `0x1800022f0`
- `0x180002640`
- `0x18000585c`
- `0x180008630`
- `0x18000b980`
- `0x18000bd34`
- `0x18000f3f8`
- `0x18000f6d8`

## import_xrefs

- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x18000f7b2`
- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x18000f7b2`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x18000f8b4`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x18000f8b4`

## pseudocode

```c
__int64 __fastcall CSnapinThreadTable::RegisterThread(__int64 a1, int a2, int a3, unsigned int a4, int a5)
{
  LKRhash::CLKRLinearHashTable *v5; // r14
  _DWORD *v6; // rbx
  volatile __int32 *v10; // r15
  int v11; // edi
  __int64 v12; // rcx
  __int64 v13; // rdx
  int Key; // eax
  _DWORD *v15; // rax
  int inserted; // eax
  __int64 v17; // rcx
  __int64 v18; // rdx
  int v19; // eax
  _DWORD *v21; // [rsp+60h] [rbp+8h] BYREF

  v5 = BookKeeping::s_pSnapinThreadTable;
  v6 = 0;
  v21 = 0;
  v10 = (volatile __int32 *)((char *)BookKeeping::s_pSnapinThreadTable + 176);
  CSmallSpinLock::WriteLock((LKRhash::CLKRLinearHashTable *)((char *)BookKeeping::s_pSnapinThreadTable + 176));
  if ( !a4 )
  {
    v11 = -2147024809;
    v12 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v13 = 25;
LABEL_5:
      WPP_SF_(*(_QWORD *)(v12 + 16), v13, WPP_8949107765ef31f55290197bfd8c288d_Traceguids);
      goto LABEL_26;
    }
    goto LABEL_26;
  }
  if ( a3 )
  {
    Key = LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,unsigned long,LKRhash::CLKRLinearHashTable>::FindKey(
            v5,
            a4,
            &v21);
    v11 = BookKeeping::LKResult2HRESULT(Key);
    if ( v11 == -2147319765 )
    {
      v15 = operator new(0x10u);
      v21 = v15;
      v6 = v15;
      if ( !v15 )
      {
        v6 = 0;
        v11 = -2147024882;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 27, WPP_8949107765ef31f55290197bfd8c288d_Traceguids, a4);
        goto LABEL_26;
      }
      *(_QWORD *)v15 = 0;
      v15[2] = a4;
      v15[3] = 0;
      inserted = LKRhash::CLKRLinearHashTable::InsertRecord(v5, v15);
      v11 = BookKeeping::LKResult2HRESULT(inserted);
      if ( v11 < 0 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
          goto LABEL_26;
        v18 = 28;
        goto LABEL_16;
      }
    }
    else
    {
      if ( v11 < 0 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
          goto LABEL_26;
        v18 = 29;
LABEL_16:
        WPP_SF_dd(*(_QWORD *)(v17 + 16), v18, WPP_8949107765ef31f55290197bfd8c288d_Traceguids, a4, v11);
        goto LABEL_26;
      }
      v6 = v21;
    }
    v19 = a5;
    *v6 = a2;
    v6[1] = a3;
    v6[3] = v19;
    goto LABEL_26;
  }
  v11 = -2147024809;
  v12 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v13 = 26;
    goto LABEL_5;
  }
LABEL_26:
  _InterlockedExchange(v10, 0);
  if ( v11 < 0 && v6 )
    operator delete(v6);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000f6d8  mov     rax, rsp
0x18000f6db  mov     [rax+10h], rbx
0x18000f6df  mov     [rax+18h], rbp
0x18000f6e3  mov     [rax+8], rcx
0x18000f6e7  push    rsi
0x18000f6e8  push    rdi
0x18000f6e9  push    r12
0x18000f6eb  push    r14
0x18000f6ed  push    r15
0x18000f6ef  sub     rsp, 30h
0x18000f6f3  mov     r14, cs:?s_pSnapinThreadTable@BookKeeping@@0PEAVCSnapinThreadTable@@EA; CSnapinThreadTable * BookKeeping::s_pSnapinThreadTable
0x18000f6fa  xor     ebx, ebx
0x18000f6fc  mov     esi, r9d
0x18000f6ff  mov     [rax+8], rbx
0x18000f703  mov     ebp, r8d
0x18000f706  mov     r12d, edx
0x18000f709  lea     r15, [r14+0B0h]
0x18000f710  mov     rcx, r15; this
0x18000f713  call    ?WriteLock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteLock(void)
0x18000f718  test    esi, esi
0x18000f71a  jnz     short loc_18000F75A
0x18000f71c  mov     edi, 80070057h
0x18000f721  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f728  lea     rax, WPP_GLOBAL_Control
0x18000f72f  cmp     rcx, rax
0x18000f732  jz      loc_18000F8A3
0x18000f738  cmp     byte ptr [rcx+19h], 2
0x18000f73c  jb      loc_18000F8A3
0x18000f742  lea     edx, [rbx+19h]
0x18000f745  mov     rcx, [rcx+10h]
0x18000f749  lea     r8, WPP_8949107765ef31f55290197bfd8c288d_Traceguids
0x18000f750  call    WPP_SF_
0x18000f755  jmp     loc_18000F8A3
0x18000f75a  test    ebp, ebp
0x18000f75c  jnz     short loc_18000F789
0x18000f75e  mov     edi, 80070057h
0x18000f763  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f76a  lea     rax, WPP_GLOBAL_Control
0x18000f771  cmp     rcx, rax
0x18000f774  jz      loc_18000F8A3
0x18000f77a  cmp     byte ptr [rcx+19h], 2
0x18000f77e  jb      loc_18000F8A3
0x18000f784  lea     edx, [rbp+1Ah]
0x18000f787  jmp     short loc_18000F745
0x18000f789  lea     r8, [rsp+58h+arg_0]
0x18000f78e  mov     edx, esi
0x18000f790  mov     rcx, r14
0x18000f793  call    ?FindKey@?$CTypedHashTable@VCSnapinThreadTable@@VCSnapinThread@@KVCLKRLinearHashTable@LKRhash@@@LKRhash@@QEBA?AW4LK_RETCODE@2@KPEAPEAVCSnapinThread@@@Z; LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,ulong,LKRhash::CLKRLinearHashTable>::FindKey(ulong,CSnapinThread * *)
0x18000f798  movsxd  rcx, eax; __int64
0x18000f79b  call    ?LKResult2HRESULT@BookKeeping@@SAJ_J@Z; BookKeeping::LKResult2HRESULT(__int64)
0x18000f7a0  mov     edi, eax
0x18000f7a2  cmp     eax, 8002802Bh
0x18000f7a7  jnz     loc_18000F86A
0x18000f7ad  mov     ecx, 10h
0x18000f7b2  call    cs:__imp_??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f7b8  mov     [rsp+58h+arg_0], rax
0x18000f7bd  mov     rbx, rax
0x18000f7c0  test    rax, rax
0x18000f7c3  jz      short loc_18000F832
0x18000f7c5  mov     rdx, rax
0x18000f7c8  mov     qword ptr [rax], 0
0x18000f7cf  mov     rcx, r14
0x18000f7d2  mov     [rax+8], esi
0x18000f7d5  mov     dword ptr [rax+0Ch], 0
0x18000f7dc  call    ?InsertRecord@CLKRLinearHashTable@LKRhash@@QEAA?AW4LK_RETCODE@2@PEBX_NPEAPEBX@Z; LKRhash::CLKRLinearHashTable::InsertRecord(void const *,bool,void const * *)
0x18000f7e1  movsxd  rcx, eax; __int64
0x18000f7e4  call    ?LKResult2HRESULT@BookKeeping@@SAJ_J@Z; BookKeeping::LKResult2HRESULT(__int64)
0x18000f7e9  mov     edi, eax
0x18000f7eb  test    eax, eax
0x18000f7ed  jns     loc_18000F893
0x18000f7f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f7fa  lea     rax, WPP_GLOBAL_Control
0x18000f801  cmp     rcx, rax
0x18000f804  jz      loc_18000F8A3
0x18000f80a  cmp     byte ptr [rcx+19h], 2
0x18000f80e  jb      loc_18000F8A3
0x18000f814  mov     edx, 1Ch
0x18000f819  mov     rcx, [rcx+10h]
0x18000f81d  lea     r8, WPP_8949107765ef31f55290197bfd8c288d_Traceguids
0x18000f824  mov     r9d, esi
0x18000f827  mov     [rsp+58h+var_38], edi
0x18000f82b  call    WPP_SF_dd
0x18000f830  jmp     short loc_18000F8A3
0x18000f832  xor     ebx, ebx
0x18000f834  mov     edi, 8007000Eh
0x18000f839  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f840  lea     rax, WPP_GLOBAL_Control
0x18000f847  cmp     rcx, rax
0x18000f84a  jz      short loc_18000F8A3
0x18000f84c  cmp     byte ptr [rcx+19h], 2
0x18000f850  jb      short loc_18000F8A3
0x18000f852  mov     rcx, [rcx+10h]
0x18000f856  lea     edx, [rbx+1Bh]
0x18000f859  mov     r9d, esi
0x18000f85c  lea     r8, WPP_8949107765ef31f55290197bfd8c288d_Traceguids
0x18000f863  call    WPP_SF_d
0x18000f868  jmp     short loc_18000F8A3
0x18000f86a  test    edi, edi
0x18000f86c  jns     short loc_18000F88E
0x18000f86e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f875  lea     rax, WPP_GLOBAL_Control
0x18000f87c  cmp     rcx, rax
0x18000f87f  jz      short loc_18000F8A3
0x18000f881  cmp     byte ptr [rcx+19h], 2
0x18000f885  jb      short loc_18000F8A3
0x18000f887  mov     edx, 1Dh
0x18000f88c  jmp     short loc_18000F819
0x18000f88e  mov     rbx, [rsp+58h+arg_0]
0x18000f893  mov     eax, [rsp+58h+arg_20]
0x18000f89a  mov     [rbx], r12d
0x18000f89d  mov     [rbx+4], ebp
0x18000f8a0  mov     [rbx+0Ch], eax
0x18000f8a3  xor     edx, edx
0x18000f8a5  xchg    edx, [r15]
0x18000f8a8  test    edi, edi
0x18000f8aa  jns     short loc_18000F8BA
0x18000f8ac  test    rbx, rbx
0x18000f8af  jz      short loc_18000F8BA
0x18000f8b1  mov     rcx, rbx
0x18000f8b4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f8ba  mov     rbx, [rsp+58h+arg_8]
0x18000f8bf  mov     eax, edi
0x18000f8c1  mov     rbp, [rsp+58h+arg_10]
0x18000f8c6  add     rsp, 30h
0x18000f8ca  pop     r15
0x18000f8cc  pop     r14
0x18000f8ce  pop     r12
0x18000f8d0  pop     rdi
0x18000f8d1  pop     rsi
0x18000f8d2  retn
```
