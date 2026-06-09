# CNamespaceHandle::ExecInstanceQuery(QL_LEVEL_1_RPN_EXPRESSION *,ushort const *,bool,IWbemObjectSink *)

- ea: `0x1800015d8`
- end: `0x18000173c`
- name: `?ExecInstanceQuery@CNamespaceHandle@@IEAAJPEAUQL_LEVEL_1_RPN_EXPRESSION@@PEBG_NPEAUIWbemObjectSink@@@Z`
- size: `356`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, struct QL_LEVEL_1_RPN_EXPRESSION *, const unsigned __int16 *, char, struct IWbemObjectSink *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180001750`

## callees

- `0x180001274`
- `0x1800012b8`
- `0x1800015d8`
- `0x180006960`
- `0x18000a9b0`
- `0x18001d844`
- `0x180044420`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180001665`
- `wbemcomn!GetMemLogObject` at `0x1800016e0`
- `wbemcomn!GetMemLogObject` at `0x180001665`
- `wbemcomn!GetMemLogObject` at `0x1800016e0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180001675`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800016eb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180001675`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800016eb`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::ExecInstanceQuery(
        CNamespaceHandle *this,
        struct QL_LEVEL_1_RPN_EXPRESSION *a2,
        const unsigned __int16 *a3,
        char a4,
        struct IWbemObjectSink *a5)
{
  __int64 result; // rax
  struct QL_LEVEL_1_RPN_EXPRESSION *v10; // rdx
  CMemoryLog *MemLogObject; // rax
  unsigned int v12; // ebx
  CVarObjHeap *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  int v16; // eax
  CMemoryLog *v17; // rax
  unsigned __int16 v18[72]; // [rsp+20h] [rbp-C8h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 470, a3, a5);
  }
  if ( g_bShuttingDown )
    return 2147749939LL;
  if ( !A51Hash(a3, v18) )
  {
    MemLogObject = GetMemLogObject();
    v12 = -2147217402;
    CMemoryLog::Write(MemLogObject, -2147217402);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v12;
    }
    v14 = 471;
    v15 = 2147749894LL;
LABEL_12:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, v15);
    return v12;
  }
  if ( a4 )
    v16 = CNamespaceHandle::ExecDeepInstanceQuery(this, a2, v18, a5);
  else
    v16 = CNamespaceHandle::ExecShallowInstanceQuery(this, v10, v18, a5);
  v12 = v16;
  if ( v16 >= 0 )
    return 0;
  result = 2147749938LL;
  if ( v12 != -2147217358 )
  {
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, v12);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v12;
    }
    v14 = 472;
    v15 = v12;
    goto LABEL_12;
  }
  return result;
}

```

## disassembly

```asm
0x1800015d8  mov     [rsp+arg_18], rbx
0x1800015dd  push    rbp
0x1800015de  push    rsi
0x1800015df  push    rdi
0x1800015e0  push    r12
0x1800015e2  push    r14
0x1800015e4  sub     rsp, 0C0h
0x1800015eb  mov     rax, cs:__security_cookie
0x1800015f2  xor     rax, rsp
0x1800015f5  mov     [rsp+0E8h+var_38], rax
0x1800015fd  mov     rbx, [rsp+0E8h+arg_20]
0x180001605  mov     sil, r9b
0x180001608  mov     rbp, r8
0x18000160b  mov     r14, rdx
0x18000160e  mov     rdi, rcx
0x180001611  mov     rcx, cs:WPP_GLOBAL_Control
0x180001618  lea     r12, WPP_GLOBAL_Control
0x18000161f  cmp     rcx, r12
0x180001622  jz      short loc_180001641
0x180001624  test    byte ptr [rcx+1Ch], 1
0x180001628  jz      short loc_180001641
0x18000162a  cmp     byte ptr [rcx+19h], 5
0x18000162e  jb      short loc_180001641
0x180001630  mov     rcx, [rcx+10h]
0x180001634  mov     edx, 1D6h
0x180001639  mov     r9, rbx
0x18000163c  call    WPP_SF_q
0x180001641  cmp     cs:?g_bShuttingDown@@3_NA, 0; bool g_bShuttingDown
0x180001648  jz      short loc_180001654
0x18000164a  mov     eax, 80041033h
0x18000164f  jmp     loc_180001715
0x180001654  lea     rdx, [rsp+0E8h+var_C8]; unsigned __int16 *
0x180001659  mov     rcx, rbp; unsigned __int16 *
0x18000165c  call    ?A51Hash@@YA_NPEBGPEAG@Z; A51Hash(ushort const *,ushort *)
0x180001661  test    al, al
0x180001663  jnz     short loc_1800016B2
0x180001665  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000166b  mov     ebx, 80041006h
0x180001670  mov     rcx, rax
0x180001673  mov     edx, ebx
0x180001675  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000167b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001682  cmp     rcx, r12
0x180001685  jz      short loc_1800016AE
0x180001687  test    byte ptr [rcx+1Ch], 1
0x18000168b  jz      short loc_1800016AE
0x18000168d  cmp     byte ptr [rcx+19h], 2
0x180001691  jb      short loc_1800016AE
0x180001693  mov     edx, 1D7h
0x180001698  mov     r9d, 80041006h
0x18000169e  mov     rcx, [rcx+10h]
0x1800016a2  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800016a9  call    WPP_SF_d
0x1800016ae  mov     eax, ebx
0x1800016b0  jmp     short loc_180001715
0x1800016b2  lea     r8, [rsp+0E8h+var_C8]; unsigned __int16 *
0x1800016b7  mov     r9, rbx; struct IWbemObjectSink *
0x1800016ba  mov     rcx, rdi; this
0x1800016bd  test    sil, sil
0x1800016c0  jz      short loc_1800016CC
0x1800016c2  mov     rdx, r14; struct QL_LEVEL_1_RPN_EXPRESSION *
0x1800016c5  call    ?ExecDeepInstanceQuery@CNamespaceHandle@@IEAAJPEAUQL_LEVEL_1_RPN_EXPRESSION@@PEBGPEAUIWbemObjectSink@@@Z; CNamespaceHandle::ExecDeepInstanceQuery(QL_LEVEL_1_RPN_EXPRESSION *,ushort const *,IWbemObjectSink *)
0x1800016ca  jmp     short loc_1800016D1
0x1800016cc  call    ?ExecShallowInstanceQuery@CNamespaceHandle@@IEAAJPEAUQL_LEVEL_1_RPN_EXPRESSION@@PEBGPEAUIWbemObjectSink@@@Z; CNamespaceHandle::ExecShallowInstanceQuery(QL_LEVEL_1_RPN_EXPRESSION *,ushort const *,IWbemObjectSink *)
0x1800016d1  mov     ebx, eax
0x1800016d3  test    eax, eax
0x1800016d5  jns     short loc_180001713
0x1800016d7  mov     eax, 80041032h
0x1800016dc  cmp     ebx, eax
0x1800016de  jz      short loc_180001715
0x1800016e0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800016e6  mov     rcx, rax
0x1800016e9  mov     edx, ebx
0x1800016eb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800016f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800016f8  cmp     rcx, r12
0x1800016fb  jz      short loc_1800016AE
0x1800016fd  test    byte ptr [rcx+1Ch], 1
0x180001701  jz      short loc_1800016AE
0x180001703  cmp     byte ptr [rcx+19h], 2
0x180001707  jb      short loc_1800016AE
0x180001709  mov     edx, 1D8h
0x18000170e  mov     r9d, ebx
0x180001711  jmp     short loc_18000169E
0x180001713  xor     eax, eax
0x180001715  mov     rcx, [rsp+0E8h+var_38]
0x18000171d  xor     rcx, rsp; StackCookie
0x180001720  call    __security_check_cookie
0x180001725  mov     rbx, [rsp+0E8h+arg_18]
0x18000172d  add     rsp, 0C0h
0x180001734  pop     r14
0x180001736  pop     r12
0x180001738  pop     rdi
0x180001739  pop     rsi
0x18000173a  pop     rbp
0x18000173b  retn
```
