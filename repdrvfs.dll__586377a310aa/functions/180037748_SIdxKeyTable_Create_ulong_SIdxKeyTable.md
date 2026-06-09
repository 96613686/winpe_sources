# SIdxKeyTable::Create(ulong,SIdxKeyTable * *)

- ea: `0x180037748`
- end: `0x18003796e`
- name: `?Create@SIdxKeyTable@@SAKKPEAPEAV1@@Z`
- size: `550`
- prototype: `__int64 __fastcall(int, struct SIdxKeyTable **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010fe4`
- `0x180037974`

## callees

- `0x1800012b8`
- `0x18000fb3c`
- `0x18000fcf0`
- `0x180037748`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180037764`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800377f8`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180037764`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800377f8`
- `wbemcomn!GetMemLogObject` at `0x1800378d4`
- `wbemcomn!GetMemLogObject` at `0x18003790e`
- `wbemcomn!GetMemLogObject` at `0x1800378d4`
- `wbemcomn!GetMemLogObject` at `0x18003790e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800378e4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003791e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800378e4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003791e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SIdxKeyTable::Create(int a1, struct SIdxKeyTable **a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  unsigned __int64 v6; // rsi
  _OWORD *v7; // rax
  _DWORD *v8; // rdx
  __int64 v9; // rax
  CMemoryLog *v11; // rax
  CVarObjHeap *v12; // rcx
  __int64 v13; // rdx
  CMemoryLog *MemLogObject; // rax

  v4 = CWin32DefaultArena::WbemMemAlloc(0x50u);
  v5 = v4;
  if ( !v4 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, 8);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 8;
    }
    v13 = 87;
    goto LABEL_28;
  }
  *v4 = 0;
  v4[1] = 0;
  v4[2] = 0;
  *((_DWORD *)v4 + 6) = 0;
  v4[6] = 0;
  v4[7] = 0;
  v4[8] = 0;
  v4[4] = 0;
  v4[5] = 0;
  v4[9] = 0;
  *((_DWORD *)v4 + 1) = a1;
  *((_DWORD *)v4 + 3) = 0;
  v6 = 256;
  v4[2] = _BtrMemAlloc(0x200u);
  *((_DWORD *)v5 + 6) = 256;
  v5[6] = _BtrMemAlloc(0x200u);
  v5[7] = 256;
  v5[4] = _BtrMemAlloc(0x400u);
  v5[5] = _BtrMemAlloc(0x404u);
  v7 = CWin32DefaultArena::WbemMemAlloc(0x30u);
  if ( v7 )
  {
    *v7 = 0;
    v7[1] = 0;
    v7[2] = 0;
    *((_BYTE *)v7 + 40) = 1;
  }
  else
  {
    v7 = 0;
  }
  v5[8] = v7;
  if ( v7 )
  {
    *(_QWORD *)(v5[8] + 8LL) = _BtrMemAlloc(0x200u);
    *(_DWORD *)(v5[8] + 16LL) = 256;
    *(_QWORD *)(v5[8] + 24LL) = _BtrMemAlloc(0x2200u);
    *(_DWORD *)(v5[8] + 32LL) = 8704;
  }
  if ( !v5[2]
    || !v5[6]
    || !v5[4]
    || (v8 = (_DWORD *)v5[5]) == 0
    || (v9 = v5[8]) == 0
    || !*(_QWORD *)(v9 + 8)
    || !*(_QWORD *)(v9 + 24) )
  {
    SIdxKeyTable::`scalar deleting destructor'((SIdxKeyTable *)v5);
    *a2 = 0;
    v11 = GetMemLogObject();
    CMemoryLog::Write(v11, 8);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 8;
    }
    v13 = 88;
LABEL_28:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 8);
    return 8;
  }
  if ( ((unsigned __int8)v8 & 4) != 0 )
    *v8++ = -1;
  else
    v6 = 257;
  memset(v8, 0xFFu, 8 * (v6 >> 1));
  if ( (v6 & 1) != 0 )
    v8[v6 - 1] = -1;
  _InterlockedIncrement((volatile signed __int32 *)v5);
  *a2 = (struct SIdxKeyTable *)v5;
  return 0;
}

```

## disassembly

```asm
0x180037748  mov     [rsp+arg_0], rbx
0x18003774d  mov     [rsp+arg_8], rbp
0x180037752  push    rsi
0x180037753  push    rdi
0x180037754  push    r14
0x180037756  sub     rsp, 20h
0x18003775a  mov     edi, ecx
0x18003775c  mov     r14, rdx
0x18003775f  mov     ecx, 50h ; 'P'
0x180037764  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003776a  xor     ebp, ebp
0x18003776c  mov     [rsp+38h+arg_10], rax
0x180037771  mov     rbx, rax
0x180037774  test    rax, rax
0x180037777  jz      loc_18003790E
0x18003777d  mov     [rax], rbp
0x180037780  mov     [rax+8], rbp
0x180037784  mov     [rax+10h], rbp
0x180037788  mov     [rax+18h], ebp
0x18003778b  mov     [rax+30h], rbp
0x18003778f  mov     [rax+38h], rbp
0x180037793  mov     [rax+40h], rbp
0x180037797  mov     [rax+20h], rbp
0x18003779b  mov     [rax+28h], rbp
0x18003779f  mov     [rax+48h], rbp
0x1800377a3  test    rax, rax
0x1800377a6  jz      loc_18003790E
0x1800377ac  mov     [rax+4], edi
0x1800377af  mov     edi, 200h
0x1800377b4  mov     ecx, edi; unsigned __int64
0x1800377b6  mov     [rax+0Ch], ebp
0x1800377b9  call    ?_BtrMemAlloc@@YAPEAX_K@Z; _BtrMemAlloc(unsigned __int64)
0x1800377be  mov     esi, 100h
0x1800377c3  mov     [rbx+10h], rax
0x1800377c7  mov     ecx, edi; unsigned __int64
0x1800377c9  mov     [rbx+18h], esi
0x1800377cc  call    ?_BtrMemAlloc@@YAPEAX_K@Z; _BtrMemAlloc(unsigned __int64)
0x1800377d1  mov     ecx, 400h; unsigned __int64
0x1800377d6  mov     [rbx+30h], rax
0x1800377da  mov     [rbx+38h], rsi
0x1800377de  call    ?_BtrMemAlloc@@YAPEAX_K@Z; _BtrMemAlloc(unsigned __int64)
0x1800377e3  mov     ecx, 404h; unsigned __int64
0x1800377e8  mov     [rbx+20h], rax
0x1800377ec  call    ?_BtrMemAlloc@@YAPEAX_K@Z; _BtrMemAlloc(unsigned __int64)
0x1800377f1  lea     ecx, [rbp+30h]
0x1800377f4  mov     [rbx+28h], rax
0x1800377f8  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800377fe  mov     [rsp+38h+arg_10], rax
0x180037803  test    rax, rax
0x180037806  jz      short loc_18003781C
0x180037808  xorps   xmm0, xmm0
0x18003780b  movups  xmmword ptr [rax], xmm0
0x18003780e  movups  xmmword ptr [rax+10h], xmm0
0x180037812  movups  xmmword ptr [rax+20h], xmm0
0x180037816  mov     byte ptr [rax+28h], 1
0x18003781a  jmp     short loc_18003781F
0x18003781c  mov     rax, rbp
0x18003781f  mov     [rbx+40h], rax
0x180037823  test    rax, rax
0x180037826  jz      short loc_18003785A
0x180037828  mov     rcx, rdi; unsigned __int64
0x18003782b  call    ?_BtrMemAlloc@@YAPEAX_K@Z; _BtrMemAlloc(unsigned __int64)
0x180037830  mov     rcx, [rbx+40h]
0x180037834  mov     edi, 2200h
0x180037839  mov     [rcx+8], rax
0x18003783d  mov     ecx, edi; unsigned __int64
0x18003783f  mov     rax, [rbx+40h]
0x180037843  mov     [rax+10h], esi
0x180037846  call    ?_BtrMemAlloc@@YAPEAX_K@Z; _BtrMemAlloc(unsigned __int64)
0x18003784b  mov     rcx, [rbx+40h]
0x18003784f  mov     [rcx+18h], rax
0x180037853  mov     rax, [rbx+40h]
0x180037857  mov     [rax+20h], edi
0x18003785a  cmp     [rbx+10h], rbp
0x18003785e  jz      short loc_1800378C9
0x180037860  cmp     [rbx+30h], rbp
0x180037864  jz      short loc_1800378C9
0x180037866  cmp     [rbx+20h], rbp
0x18003786a  jz      short loc_1800378C9
0x18003786c  mov     rdx, [rbx+28h]
0x180037870  test    rdx, rdx
0x180037873  jz      short loc_1800378C9
0x180037875  mov     rax, [rbx+40h]
0x180037879  test    rax, rax
0x18003787c  jz      short loc_1800378C9
0x18003787e  cmp     [rax+8], rbp
0x180037882  jz      short loc_1800378C9
0x180037884  cmp     [rax+18h], rbp
0x180037888  jz      short loc_1800378C9
0x18003788a  or      r8d, 0FFFFFFFFh
0x18003788e  test    dl, 4
0x180037891  jz      short loc_18003789C
0x180037893  mov     [rdx], r8d
0x180037896  add     rdx, 4
0x18003789a  jmp     short loc_1800378A1
0x18003789c  mov     esi, 101h
0x1800378a1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800378a5  mov     rcx, rsi
0x1800378a8  shr     rcx, 1
0x1800378ab  mov     rdi, rdx
0x1800378ae  rep stosq
0x1800378b1  test    sil, 1
0x1800378b5  jz      short loc_1800378BC
0x1800378b7  mov     [rdx+rsi*4-4], r8d
0x1800378bc  lock inc dword ptr [rbx]
0x1800378bf  mov     [r14], rbx
0x1800378c2  xor     eax, eax
0x1800378c4  jmp     loc_18003795B
0x1800378c9  mov     rcx, rbx; this
0x1800378cc  call    ??_GSIdxKeyTable@@AEAAPEAXI@Z; SIdxKeyTable::`scalar deleting destructor'(uint)
0x1800378d1  mov     [r14], rbp
0x1800378d4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800378da  mov     edi, 8
0x1800378df  mov     rcx, rax
0x1800378e2  mov     edx, edi
0x1800378e4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800378ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800378f1  lea     rax, WPP_GLOBAL_Control
0x1800378f8  cmp     rcx, rax
0x1800378fb  jz      short loc_180037959
0x1800378fd  test    byte ptr [rcx+1Ch], 1
0x180037901  jz      short loc_180037959
0x180037903  cmp     byte ptr [rcx+19h], 2
0x180037907  jb      short loc_180037959
0x180037909  lea     edx, [rdi+50h]
0x18003790c  jmp     short loc_180037946
0x18003790e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180037914  mov     edi, 8
0x180037919  mov     rcx, rax
0x18003791c  mov     edx, edi
0x18003791e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180037924  mov     rcx, cs:WPP_GLOBAL_Control
0x18003792b  lea     rax, WPP_GLOBAL_Control
0x180037932  cmp     rcx, rax
0x180037935  jz      short loc_180037959
0x180037937  test    byte ptr [rcx+1Ch], 1
0x18003793b  jz      short loc_180037959
0x18003793d  cmp     byte ptr [rcx+19h], 2
0x180037941  jb      short loc_180037959
0x180037943  lea     edx, [rdi+4Fh]
0x180037946  mov     rcx, [rcx+10h]
0x18003794a  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x180037951  mov     r9d, edi
0x180037954  call    WPP_SF_d
0x180037959  mov     eax, edi
0x18003795b  mov     rbx, [rsp+38h+arg_0]
0x180037960  mov     rbp, [rsp+38h+arg_8]
0x180037965  add     rsp, 20h
0x180037969  pop     r14
0x18003796b  pop     rdi
0x18003796c  pop     rsi
0x18003796d  retn
```
