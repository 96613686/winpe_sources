# CSnapinThreadTable::UnregisterThread(int,ulong)

- ea: `0x18000f9d8`
- end: `0x18000fb9a`
- name: `?UnregisterThread@CSnapinThreadTable@@QEAAJHK@Z`
- size: `450`
- prototype: `int(CSnapinThreadTable *__hidden this, int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18000e3f0`

## callees

- `0x1800022f0`
- `0x1800046d0`
- `0x18000585c`
- `0x18000b980`
- `0x18000b9cc`
- `0x18000bd34`
- `0x18000f3f8`
- `0x18000f9d8`
- `0x180019de8`

## import_xrefs

- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x18000fb80`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x18000fb80`

## pseudocode

```c
__int64 __fastcall CSnapinThreadTable::UnregisterThread(CSnapinThreadTable *this, int a2, unsigned int a3)
{
  LKRhash::CLKRLinearHashTable *v3; // rdi
  unsigned __int64 v5; // rsi
  volatile __int32 *v6; // r15
  int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rdx
  int Key; // eax
  __int64 v11; // rcx
  __int64 v12; // rdx
  void *v13; // r14
  int v14; // eax
  unsigned int v15; // eax
  __int64 result; // rax
  _DWORD *v17; // [rsp+70h] [rbp+8h] BYREF

  v3 = BookKeeping::s_pSnapinThreadTable;
  v5 = a3;
  v17 = 0;
  v6 = (volatile __int32 *)((char *)BookKeeping::s_pSnapinThreadTable + 176);
  CSmallSpinLock::WriteLock((LKRhash::CLKRLinearHashTable *)((char *)BookKeeping::s_pSnapinThreadTable + 176));
  if ( !(_DWORD)v5 )
  {
    v7 = -2147024809;
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v9 = 30;
LABEL_5:
      WPP_SF_(*(_QWORD *)(v8 + 16), v9, WPP_8949107765ef31f55290197bfd8c288d_Traceguids);
      goto LABEL_26;
    }
    goto LABEL_26;
  }
  if ( !a2 )
  {
    v7 = -2147024809;
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v9 = 31;
      goto LABEL_5;
    }
    goto LABEL_26;
  }
  Key = LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,unsigned long,LKRhash::CLKRLinearHashTable>::FindKey(
          v3,
          (unsigned int)v5,
          &v17);
  v7 = BookKeeping::LKResult2HRESULT(Key);
  if ( v7 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_26;
    v12 = 32;
LABEL_14:
    WPP_SF_dd(*(_QWORD *)(v11 + 16), v12, WPP_8949107765ef31f55290197bfd8c288d_Traceguids, (unsigned int)v5, v7);
    goto LABEL_26;
  }
  v13 = v17;
  if ( v17[1] != a2 )
  {
    v7 = -2147319765;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      WPP_SF_ddd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        33,
        WPP_8949107765ef31f55290197bfd8c288d_Traceguids,
        (unsigned int)v5,
        a2,
        -2147319765);
    goto LABEL_26;
  }
  v14 = *((_DWORD *)v3 + 5);
  if ( !v14 )
  {
    v15 = LKRhash::CLKRLinearHashTable::_CalcKeyHash(v3, v5);
    v14 = LKRhash::CLKRLinearHashTable::_DeleteKey(v3, v5, v15);
  }
  v7 = BookKeeping::LKResult2HRESULT(v14);
  if ( v7 >= 0 )
  {
    operator delete(v13);
    goto LABEL_26;
  }
  v11 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v12 = 34;
    goto LABEL_14;
  }
LABEL_26:
  result = (unsigned int)v7;
  _InterlockedExchange(v6, 0);
  return result;
}

```

## disassembly

```asm
0x18000f9d8  mov     [rsp+arg_0], rcx
0x18000f9dd  push    rbx
0x18000f9de  push    rbp
0x18000f9df  push    rsi
0x18000f9e0  push    rdi
0x18000f9e1  push    r14
0x18000f9e3  push    r15
0x18000f9e5  sub     rsp, 38h
0x18000f9e9  mov     rdi, cs:?s_pSnapinThreadTable@BookKeeping@@0PEAVCSnapinThreadTable@@EA; CSnapinThreadTable * BookKeeping::s_pSnapinThreadTable
0x18000f9f0  mov     ebp, edx
0x18000f9f2  mov     esi, r8d
0x18000f9f5  mov     [rsp+68h+arg_0], 0
0x18000f9fe  lea     r15, [rdi+0B0h]
0x18000fa05  mov     rcx, r15; this
0x18000fa08  call    ?WriteLock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteLock(void)
0x18000fa0d  test    esi, esi
0x18000fa0f  jnz     short loc_18000FA4F
0x18000fa11  mov     ebx, 80070057h
0x18000fa16  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa1d  lea     rax, WPP_GLOBAL_Control
0x18000fa24  cmp     rcx, rax
0x18000fa27  jz      loc_18000FB86
0x18000fa2d  cmp     byte ptr [rcx+19h], 2
0x18000fa31  jb      loc_18000FB86
0x18000fa37  lea     edx, [rsi+1Eh]
0x18000fa3a  mov     rcx, [rcx+10h]
0x18000fa3e  lea     r8, WPP_8949107765ef31f55290197bfd8c288d_Traceguids
0x18000fa45  call    WPP_SF_
0x18000fa4a  jmp     loc_18000FB86
0x18000fa4f  test    ebp, ebp
0x18000fa51  jnz     short loc_18000FA7E
0x18000fa53  mov     ebx, 80070057h
0x18000fa58  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa5f  lea     rax, WPP_GLOBAL_Control
0x18000fa66  cmp     rcx, rax
0x18000fa69  jz      loc_18000FB86
0x18000fa6f  cmp     byte ptr [rcx+19h], 2
0x18000fa73  jb      loc_18000FB86
0x18000fa79  lea     edx, [rbp+1Fh]
0x18000fa7c  jmp     short loc_18000FA3A
0x18000fa7e  lea     r8, [rsp+68h+arg_0]
0x18000fa83  mov     edx, esi
0x18000fa85  mov     rcx, rdi
0x18000fa88  call    ?FindKey@?$CTypedHashTable@VCSnapinThreadTable@@VCSnapinThread@@KVCLKRLinearHashTable@LKRhash@@@LKRhash@@QEBA?AW4LK_RETCODE@2@KPEAPEAVCSnapinThread@@@Z; LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,ulong,LKRhash::CLKRLinearHashTable>::FindKey(ulong,CSnapinThread * *)
0x18000fa8d  movsxd  rcx, eax; __int64
0x18000fa90  call    ?LKResult2HRESULT@BookKeeping@@SAJ_J@Z; BookKeeping::LKResult2HRESULT(__int64)
0x18000fa95  mov     ebx, eax
0x18000fa97  test    eax, eax
0x18000fa99  jns     short loc_18000FADD
0x18000fa9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000faa2  lea     rax, WPP_GLOBAL_Control
0x18000faa9  cmp     rcx, rax
0x18000faac  jz      loc_18000FB86
0x18000fab2  cmp     byte ptr [rcx+19h], 2
0x18000fab6  jb      loc_18000FB86
0x18000fabc  mov     edx, 20h ; ' '
0x18000fac1  mov     rcx, [rcx+10h]
0x18000fac5  lea     r8, WPP_8949107765ef31f55290197bfd8c288d_Traceguids
0x18000facc  mov     r9d, esi
0x18000facf  mov     [rsp+68h+var_48], ebx
0x18000fad3  call    WPP_SF_dd
0x18000fad8  jmp     loc_18000FB86
0x18000fadd  mov     r14, [rsp+68h+arg_0]
0x18000fae2  cmp     [r14+4], ebp
0x18000fae6  jz      short loc_18000FB2C
0x18000fae8  mov     ebx, 8002802Bh
0x18000faed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000faf4  lea     rax, WPP_GLOBAL_Control
0x18000fafb  cmp     rcx, rax
0x18000fafe  jz      loc_18000FB86
0x18000fb04  cmp     byte ptr [rcx+19h], 2
0x18000fb08  jb      short loc_18000FB86
0x18000fb0a  mov     rcx, [rcx+10h]
0x18000fb0e  lea     r8, WPP_8949107765ef31f55290197bfd8c288d_Traceguids
0x18000fb15  mov     edx, 21h ; '!'
0x18000fb1a  mov     [rsp+68h+var_40], ebx
0x18000fb1e  mov     r9d, esi
0x18000fb21  mov     [rsp+68h+var_48], ebp
0x18000fb25  call    WPP_SF_ddd
0x18000fb2a  jmp     short loc_18000FB86
0x18000fb2c  mov     eax, [rdi+14h]
0x18000fb2f  test    eax, eax
0x18000fb31  jnz     short loc_18000FB4C
0x18000fb33  mov     rdx, rsi; unsigned __int64
0x18000fb36  mov     rcx, rdi; this
0x18000fb39  call    ?_CalcKeyHash@CLKRLinearHashTable@LKRhash@@AEBAK_K@Z; LKRhash::CLKRLinearHashTable::_CalcKeyHash(unsigned __int64)
0x18000fb3e  mov     r8d, eax
0x18000fb41  mov     rdx, rsi
0x18000fb44  mov     rcx, rdi
0x18000fb47  call    ?_DeleteKey@CLKRLinearHashTable@LKRhash@@AEAA?AW4LK_RETCODE@2@_KK@Z; LKRhash::CLKRLinearHashTable::_DeleteKey(unsigned __int64,ulong)
0x18000fb4c  movsxd  rcx, eax; __int64
0x18000fb4f  call    ?LKResult2HRESULT@BookKeeping@@SAJ_J@Z; BookKeeping::LKResult2HRESULT(__int64)
0x18000fb54  mov     ebx, eax
0x18000fb56  test    eax, eax
0x18000fb58  jns     short loc_18000FB7D
0x18000fb5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb61  lea     rax, WPP_GLOBAL_Control
0x18000fb68  cmp     rcx, rax
0x18000fb6b  jz      short loc_18000FB86
0x18000fb6d  cmp     byte ptr [rcx+19h], 2
0x18000fb71  jb      short loc_18000FB86
0x18000fb73  mov     edx, 22h ; '"'
0x18000fb78  jmp     loc_18000FAC1
0x18000fb7d  mov     rcx, r14
0x18000fb80  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000fb86  xor     ecx, ecx
0x18000fb88  mov     eax, ebx
0x18000fb8a  xchg    ecx, [r15]
0x18000fb8d  add     rsp, 38h
0x18000fb91  pop     r15
0x18000fb93  pop     r14
0x18000fb95  pop     rdi
0x18000fb96  pop     rsi
0x18000fb97  pop     rbp
0x18000fb98  pop     rbx
0x18000fb99  retn
```
