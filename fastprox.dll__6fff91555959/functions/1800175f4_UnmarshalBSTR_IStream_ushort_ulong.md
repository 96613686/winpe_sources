# UnmarshalBSTR(IStream *,ushort * &,ulong &)

- ea: `0x1800175f4`
- end: `0x180017857`
- name: `?UnmarshalBSTR@@YAJPEAUIStream@@AEAPEAGAEAK@Z`
- size: `611`
- prototype: `__int64 __fastcall(struct IStream *, unsigned __int16 **, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180016edc`
- `0x18006182c`

## callees

- `0x180017534`
- `0x1800175f4`
- `0x180037120`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800176bd`
- `wbemcomn!GetMemLogObject` at `0x1800176e5`
- `wbemcomn!GetMemLogObject` at `0x180017751`
- `wbemcomn!GetMemLogObject` at `0x1800177b9`
- `wbemcomn!GetMemLogObject` at `0x180017813`
- `wbemcomn!GetMemLogObject` at `0x1800176bd`
- `wbemcomn!GetMemLogObject` at `0x1800176e5`
- `wbemcomn!GetMemLogObject` at `0x180017751`
- `wbemcomn!GetMemLogObject` at `0x1800177b9`
- `wbemcomn!GetMemLogObject` at `0x180017813`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800176c8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800176f5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001775f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800177c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017821`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800176c8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800176f5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001775f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800177c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180017821`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001766c`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001766c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800177b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18001780d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800177b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18001780d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UnmarshalBSTR(struct IStream *a1, unsigned __int16 **a2, unsigned int *a3)
{
  struct IStreamVtbl *lpVtbl; // rax
  unsigned int v7; // ebx
  UINT v8; // eax
  unsigned int v9; // ebx
  unsigned __int16 *v10; // rax
  int v11; // esi
  CMemoryLog *MemLogObject; // rax
  CWbemRefreshingSvc *v14; // r10
  CMemoryLog *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r9
  CMemoryLog *v18; // rax
  CWbemRefreshingSvc *v19; // rax
  __int64 v20; // rdx
  CMemoryLog *v21; // rax
  CMemoryLog *v22; // rax
  unsigned int v23[4]; // [rsp+30h] [rbp-10h] BYREF
  int v24; // [rsp+60h] [rbp+20h] BYREF
  UINT ui; // [rsp+78h] [rbp+38h] BYREF

  lpVtbl = a1->lpVtbl;
  ui = 0;
  v24 = 0;
  v7 = ((__int64 (__fastcall *)(struct IStream *, UINT *, __int64, int *))lpVtbl->Read)(a1, &ui, 4, &v24);
  if ( (v7 & 0x80000000) != 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v7);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v7;
    }
    v16 = 15;
    v17 = v7;
    goto LABEL_14;
  }
  if ( v24 != 4 )
  {
    v18 = GetMemLogObject();
    CMemoryLog::Write(v18, -2147467259);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147500037LL;
    }
    v20 = 16;
    goto LABEL_22;
  }
  v8 = ui;
  *a3 -= 4;
  v23[0] = v8;
  SafeInt<unsigned long>::operator*=<int>(v23);
  v9 = v23[0];
  if ( v23[0] > *a3 )
    return 2147500037LL;
  v10 = SysAllocStringLen(0, ui);
  *a2 = v10;
  if ( !v10 )
  {
    v15 = GetMemLogObject();
    v7 = -2147217402;
    CMemoryLog::Write(v15, -2147217402);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v7;
    }
    v16 = 17;
    v17 = 2147749894LL;
LABEL_14:
    WPP_SF_d(*((_QWORD *)v14 + 2), v16, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids, v17);
    return v7;
  }
  v11 = ((__int64 (__fastcall *)(struct IStream *, unsigned __int16 *, _QWORD, int *))a1->lpVtbl->Read)(
          a1,
          v10,
          v9,
          &v24);
  if ( v11 >= 0 )
  {
    if ( v9 == v24 )
    {
      *a3 -= v9;
      return 0;
    }
    SysFreeString(*a2);
    v22 = GetMemLogObject();
    CMemoryLog::Write(v22, -2147467259);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147500037LL;
    }
    v20 = 19;
LABEL_22:
    WPP_SF_d(*((_QWORD *)v19 + 2), v20, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids, 2147500037LL);
    return 2147500037LL;
  }
  SysFreeString(*a2);
  v21 = GetMemLogObject();
  CMemoryLog::Write(v21, v11);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
      (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800175f4  mov     [rsp-18h+arg_8], rbx
0x1800175f9  mov     [rsp-18h+arg_10], rsi
0x1800175fe  push    rbp
0x1800175ff  push    rdi
0x180017600  push    r14
0x180017602  mov     rbp, rsp
0x180017605  sub     rsp, 40h
0x180017609  mov     rax, [rcx]
0x18001760c  lea     r9, [rbp+arg_0]
0x180017610  mov     rdi, r8
0x180017613  mov     [rbp+ui], 0
0x18001761a  mov     r14, rdx
0x18001761d  mov     [rbp+arg_0], 0
0x180017624  mov     r8d, 4
0x18001762a  lea     rdx, [rbp+ui]
0x18001762e  mov     rax, [rax+18h]
0x180017632  mov     rsi, rcx
0x180017635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001763a  mov     ebx, eax
0x18001763c  test    eax, eax
0x18001763e  js      short loc_1800176BD
0x180017640  cmp     [rbp+arg_0], 4
0x180017644  jnz     loc_180017751
0x18001764a  mov     eax, [rbp+ui]
0x18001764d  lea     rcx, [rbp+var_10]
0x180017651  add     dword ptr [rdi], 0FFFFFFFCh
0x180017654  mov     [rbp+var_10], eax
0x180017657  call    ??$?XH@?$SafeInt@K@@QEAAAEAV0@H@Z; SafeInt<ulong>::operator*=<int>(int)
0x18001765c  mov     ebx, [rbp+var_10]
0x18001765f  cmp     ebx, [rdi]
0x180017661  ja      loc_1800177A6
0x180017667  mov     edx, [rbp+ui]; ui
0x18001766a  xor     ecx, ecx; strIn
0x18001766c  call    cs:__imp_SysAllocStringLen
0x180017672  mov     [r14], rax
0x180017675  mov     rdx, rax
0x180017678  test    rax, rax
0x18001767b  jz      short loc_1800176E5
0x18001767d  mov     rax, [rsi]
0x180017680  lea     r9, [rbp+arg_0]
0x180017684  mov     r8d, ebx
0x180017687  mov     rcx, rsi
0x18001768a  mov     rax, [rax+18h]
0x18001768e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017693  mov     esi, eax
0x180017695  test    eax, eax
0x180017697  js      loc_1800177B0
0x18001769d  cmp     ebx, [rbp+arg_0]
0x1800176a0  jnz     loc_18001780A
0x1800176a6  sub     [rdi], ebx
0x1800176a8  xor     eax, eax
0x1800176aa  mov     rbx, [rsp+40h+arg_8]
0x1800176af  mov     rsi, [rsp+40h+arg_10]
0x1800176b4  add     rsp, 40h
0x1800176b8  pop     r14
0x1800176ba  pop     rdi
0x1800176bb  pop     rbp
0x1800176bc  retn
0x1800176bd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800176c3  mov     rcx, rax
0x1800176c6  mov     edx, ebx
0x1800176c8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800176ce  mov     r10, cs:WPP_GLOBAL_Control
0x1800176d5  lea     rcx, WPP_GLOBAL_Control
0x1800176dc  cmp     r10, rcx
0x1800176df  jnz     short loc_180017739
0x1800176e1  mov     eax, ebx
0x1800176e3  jmp     short loc_1800176AA
0x1800176e5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800176eb  mov     ebx, 80041006h
0x1800176f0  mov     rcx, rax
0x1800176f3  mov     edx, ebx
0x1800176f5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800176fb  mov     r10, cs:WPP_GLOBAL_Control
0x180017702  lea     rcx, WPP_GLOBAL_Control
0x180017709  cmp     r10, rcx
0x18001770c  jz      short loc_1800176E1
0x18001770e  test    byte ptr [r10+1Ch], 1
0x180017713  jz      short loc_1800176E1
0x180017715  cmp     byte ptr [r10+19h], 2
0x18001771a  jb      short loc_1800176E1
0x18001771c  mov     edx, 11h
0x180017721  mov     r9d, 80041006h
0x180017727  mov     rcx, [r10+10h]
0x18001772b  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x180017732  call    WPP_SF_d
0x180017737  jmp     short loc_1800176E1
0x180017739  test    byte ptr [r10+1Ch], 1
0x18001773e  jz      short loc_1800176E1
0x180017740  cmp     byte ptr [r10+19h], 2
0x180017745  jb      short loc_1800176E1
0x180017747  mov     edx, 0Fh
0x18001774c  mov     r9d, ebx
0x18001774f  jmp     short loc_180017727
0x180017751  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180017757  mov     rcx, rax
0x18001775a  mov     edx, 80004005h
0x18001775f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180017765  mov     rax, cs:WPP_GLOBAL_Control
0x18001776c  lea     rcx, WPP_GLOBAL_Control
0x180017773  cmp     rax, rcx
0x180017776  jz      short loc_1800177A6
0x180017778  test    byte ptr [rax+1Ch], 1
0x18001777c  jz      short loc_1800177A6
0x18001777e  cmp     byte ptr [rax+19h], 2
0x180017782  jb      short loc_1800177A6
0x180017784  mov     edx, 10h
0x180017789  jmp     short loc_180017790
0x18001778b  mov     edx, 13h
0x180017790  mov     rcx, [rax+10h]
0x180017794  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x18001779b  mov     r9d, 80004005h
0x1800177a1  call    WPP_SF_d
0x1800177a6  mov     eax, 80004005h
0x1800177ab  jmp     loc_1800176AA
0x1800177b0  mov     rcx, [r14]; bstrString
0x1800177b3  call    cs:__imp_SysFreeString
0x1800177b9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800177bf  mov     rcx, rax
0x1800177c2  mov     edx, esi
0x1800177c4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800177ca  mov     r10, cs:WPP_GLOBAL_Control
0x1800177d1  lea     rcx, WPP_GLOBAL_Control
0x1800177d8  cmp     r10, rcx
0x1800177db  jz      short loc_180017803
0x1800177dd  test    byte ptr [r10+1Ch], 1
0x1800177e2  jz      short loc_180017803
0x1800177e4  cmp     byte ptr [r10+19h], 2
0x1800177e9  jb      short loc_180017803
0x1800177eb  mov     rcx, [r10+10h]
0x1800177ef  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x1800177f6  mov     edx, 12h
0x1800177fb  mov     r9d, esi
0x1800177fe  call    WPP_SF_d
0x180017803  mov     eax, esi
0x180017805  jmp     loc_1800176AA
0x18001780a  mov     rcx, [r14]; bstrString
0x18001780d  call    cs:__imp_SysFreeString
0x180017813  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180017819  mov     rcx, rax
0x18001781c  mov     edx, 80004005h
0x180017821  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180017827  mov     rax, cs:WPP_GLOBAL_Control
0x18001782e  lea     rcx, WPP_GLOBAL_Control
0x180017835  cmp     rax, rcx
0x180017838  jz      loc_1800177A6
0x18001783e  test    byte ptr [rax+1Ch], 1
0x180017842  jz      loc_1800177A6
0x180017848  cmp     byte ptr [rax+19h], 2
0x18001784c  jb      loc_1800177A6
0x180017852  jmp     loc_18001778B
```
