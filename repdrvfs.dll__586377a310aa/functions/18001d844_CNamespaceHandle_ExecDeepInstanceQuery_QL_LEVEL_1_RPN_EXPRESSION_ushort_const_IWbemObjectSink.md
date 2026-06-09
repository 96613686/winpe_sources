# CNamespaceHandle::ExecDeepInstanceQuery(QL_LEVEL_1_RPN_EXPRESSION *,ushort const *,IWbemObjectSink *)

- ea: `0x18001d844`
- end: `0x18001dba1`
- name: `?ExecDeepInstanceQuery@CNamespaceHandle@@IEAAJPEAUQL_LEVEL_1_RPN_EXPRESSION@@PEBGPEAUIWbemObjectSink@@@Z`
- size: `861`
- prototype: `__int64 __fastcall(CNamespaceHandle *__hidden this, struct QL_LEVEL_1_RPN_EXPRESSION *, const unsigned __int16 *, struct IWbemObjectSink *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800015d8`
- `0x18001d844`

## callees

- `0x180001274`
- `0x1800012b8`
- `0x18000a9b0`
- `0x18001d844`
- `0x18001dba8`

## import_xrefs

- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18001d9b8`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18001d9b8`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x18001da1b`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x18001da1b`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x18001d935`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x18001d935`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18001db26`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18001db26`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x18001d8a7`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x18001d8a7`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x18001d94a`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x18001d94a`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18001d8bb`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18001d8bb`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18001d90b`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18001d9cb`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18001db95`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18001d90b`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18001d9cb`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18001db95`
- `wbemcomn!GetMemLogObject` at `0x18001d9d8`
- `wbemcomn!GetMemLogObject` at `0x18001da3f`
- `wbemcomn!GetMemLogObject` at `0x18001dacf`
- `wbemcomn!GetMemLogObject` at `0x18001db46`
- `wbemcomn!GetMemLogObject` at `0x18001d9d8`
- `wbemcomn!GetMemLogObject` at `0x18001da3f`
- `wbemcomn!GetMemLogObject` at `0x18001dacf`
- `wbemcomn!GetMemLogObject` at `0x18001db46`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d9e3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001da4a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001dada`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001db56`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d9e3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001da4a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001dada`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001db56`
- `wbemcomn!?Add@CWStringArray@@QEAAHPEBG@Z` at `0x18001db35`
- `wbemcomn!?Add@CWStringArray@@QEAAHPEBG@Z` at `0x18001db35`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CNamespaceHandle::ExecDeepInstanceQuery(
        CNamespaceHandle *this,
        struct QL_LEVEL_1_RPN_EXPRESSION *a2,
        const unsigned __int16 *a3,
        struct IWbemObjectSink *a4)
{
  int ChildHashesByHash; // ebx
  __int64 v9; // rbx
  __int64 *v10; // r11
  __int64 *v11; // rax
  __int64 *v12; // r9
  __int64 v13; // rcx
  char *v14; // r10
  int v15; // r8d
  int v16; // edx
  unsigned int i; // edi
  __int64 result; // rax
  const unsigned __int16 *v19; // rax
  int v20; // r8d
  int v21; // ecx
  __int64 v22; // rax
  int v23; // ebx
  CFlexArray *v24; // rdi
  CMemoryLog *v25; // rax
  CVarObjHeap *v26; // rcx
  __int64 v27; // rdx
  const unsigned __int16 *v28; // rax
  CMemoryLog *v29; // rax
  CMemoryLog *v30; // rax
  const unsigned __int16 *v31; // rax
  CMemoryLog *MemLogObject; // rax
  _BYTE v33[16]; // [rsp+20h] [rbp-A8h] BYREF
  _BYTE v34[152]; // [rsp+30h] [rbp-98h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 473, a3, a4);
  }
  if ( g_bShuttingDown )
    return 2147749939LL;
  ChildHashesByHash = CNamespaceHandle::ExecShallowInstanceQuery(this, a2, a3, a4);
  if ( ChildHashesByHash >= 0 )
  {
    CWStringArray::CWStringArray((CWStringArray *)v34, 0, 100);
    v9 = *((_QWORD *)this + 11);
    CInCritSec::CInCritSec((CInCritSec *)v33, *(struct _RTL_CRITICAL_SECTION **)(v9 + 16));
    v10 = *(__int64 **)(v9 + 24);
    v11 = (__int64 *)v10[1];
    v12 = v10;
    if ( *((_BYTE *)v11 + 25) )
      goto LABEL_12;
    do
    {
      v13 = v11[4];
      v14 = (char *)a3 - v13;
      do
      {
        v15 = *(unsigned __int16 *)&v14[v13];
        v16 = *(unsigned __int16 *)v13 - v15;
        if ( v16 )
          break;
        v13 += 2;
      }
      while ( v15 );
      if ( v16 >= 0 )
      {
        v12 = v11;
        v11 = (__int64 *)*v11;
      }
      else
      {
        v11 = (__int64 *)v11[2];
      }
    }
    while ( !*((_BYTE *)v11 + 25) );
    if ( v12 == v10 )
      goto LABEL_12;
    v19 = a3;
    do
    {
      v20 = *(const unsigned __int16 *)((char *)v19 + v12[4] - (_QWORD)a3);
      v21 = *v19 - v20;
      if ( v21 )
        break;
      ++v19;
    }
    while ( v20 );
    if ( v21 < 0 || (v22 = v12[5]) == 0 || !*(_BYTE *)(v22 + 305) )
    {
LABEL_12:
      CInCritSec::~CInCritSec((CInCritSec *)v33);
      ChildHashesByHash = CNamespaceHandle::GetChildHashesByHash(this, a3, (struct CWStringArray *)v34, 0);
    }
    else
    {
      v23 = 0;
      v24 = (CFlexArray *)(v22 + 208);
      while ( 1 )
      {
        if ( v23 >= CFlexArray::Size(v24) )
        {
          CInCritSec::~CInCritSec((CInCritSec *)v33);
          ChildHashesByHash = 0;
          goto LABEL_13;
        }
        v31 = (const unsigned __int16 *)CFlexArray::GetAt(v24, v23);
        if ( (int)CWStringArray::Add((CWStringArray *)v34, v31 + 20) < 0 )
          break;
        ++v23;
      }
      MemLogObject = GetMemLogObject();
      ChildHashesByHash = -2147217402;
      CMemoryLog::Write(MemLogObject, -2147217402);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_73e6a18982e8318987457e2893328bf6_Traceguids, 2147749894LL);
      }
      CInCritSec::~CInCritSec((CInCritSec *)v33);
    }
LABEL_13:
    if ( ChildHashesByHash < 0 )
    {
      v25 = GetMemLogObject();
      CMemoryLog::Write(v25, ChildHashesByHash);
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_17;
      }
      v27 = 475;
    }
    else
    {
      for ( i = 0; ; ++i )
      {
        if ( (signed int)i >= CWStringArray::Size((CWStringArray *)v34) )
        {
          ChildHashesByHash = 0;
          goto LABEL_17;
        }
        v28 = (const unsigned __int16 *)CWStringArray::operator[](v34, i);
        ChildHashesByHash = CNamespaceHandle::ExecDeepInstanceQuery(this, a2, v28, a4);
        if ( ChildHashesByHash < 0 )
          break;
      }
      v29 = GetMemLogObject();
      CMemoryLog::Write(v29, ChildHashesByHash);
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_17;
      }
      v27 = 476;
    }
    WPP_SF_d(
      *((_QWORD *)v26 + 2),
      v27,
      WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
      (unsigned int)ChildHashesByHash);
LABEL_17:
    CWStringArray::~CWStringArray((CWStringArray *)v34);
    return (unsigned int)ChildHashesByHash;
  }
  result = 2147749938LL;
  if ( ChildHashesByHash != -2147217358 )
  {
    v30 = GetMemLogObject();
    CMemoryLog::Write(v30, ChildHashesByHash);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        474,
        WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
        (unsigned int)ChildHashesByHash);
    }
    return (unsigned int)ChildHashesByHash;
  }
  return result;
}

```

## disassembly

```asm
0x18001d844  push    rbx
0x18001d846  push    rbp
0x18001d847  push    rsi
0x18001d848  push    rdi
0x18001d849  push    r13
0x18001d84b  push    r14
0x18001d84d  sub     rsp, 98h
0x18001d854  mov     rbp, r9
0x18001d857  mov     rdi, r8
0x18001d85a  mov     r14, rdx
0x18001d85d  mov     rsi, rcx
0x18001d860  lea     r13, WPP_GLOBAL_Control
0x18001d867  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d86e  cmp     rcx, r13
0x18001d871  jnz     loc_18001DA91
0x18001d877  cmp     cs:?g_bShuttingDown@@3_NA, 0; bool g_bShuttingDown
0x18001d87e  jnz     loc_18001DAB8
0x18001d884  mov     r9, rbp; struct IWbemObjectSink *
0x18001d887  mov     r8, rdi; unsigned __int16 *
0x18001d88a  mov     rcx, rsi; this
0x18001d88d  call    ?ExecShallowInstanceQuery@CNamespaceHandle@@IEAAJPEAUQL_LEVEL_1_RPN_EXPRESSION@@PEBGPEAUIWbemObjectSink@@@Z; CNamespaceHandle::ExecShallowInstanceQuery(QL_LEVEL_1_RPN_EXPRESSION *,ushort const *,IWbemObjectSink *)
0x18001d892  mov     ebx, eax
0x18001d894  test    eax, eax
0x18001d896  js      loc_18001DAC2
0x18001d89c  xor     edx, edx
0x18001d89e  lea     r8d, [rdx+64h]
0x18001d8a2  lea     rcx, [rsp+0C8h+var_98]
0x18001d8a7  call    cs:__imp_??0CWStringArray@@QEAA@HH@Z; CWStringArray::CWStringArray(int,int)
0x18001d8ad  nop
0x18001d8ae  mov     rbx, [rsi+58h]
0x18001d8b2  mov     rdx, [rbx+10h]
0x18001d8b6  lea     rcx, [rsp+0C8h+var_A8]
0x18001d8bb  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18001d8c1  nop
0x18001d8c2  mov     r11, [rbx+18h]
0x18001d8c6  mov     rax, [r11+8]
0x18001d8ca  mov     r9, r11
0x18001d8cd  cmp     byte ptr [rax+19h], 0
0x18001d8d1  jnz     short loc_18001D906
0x18001d8d3  mov     rcx, [rax+20h]
0x18001d8d7  mov     r10, rdi
0x18001d8da  sub     r10, rcx
0x18001d8dd  movzx   edx, word ptr [rcx]
0x18001d8e0  movzx   r8d, word ptr [rcx+r10]
0x18001d8e5  sub     edx, r8d
0x18001d8e8  jnz     short loc_18001D8F3
0x18001d8ea  add     rcx, 2
0x18001d8ee  test    r8d, r8d
0x18001d8f1  jnz     short loc_18001D8DD
0x18001d8f3  test    edx, edx
0x18001d8f5  jns     short loc_18001D962
0x18001d8f7  mov     rax, [rax+10h]
0x18001d8fb  cmp     byte ptr [rax+19h], 0
0x18001d8ff  jz      short loc_18001D8D3
0x18001d901  cmp     r9, r11
0x18001d904  jnz     short loc_18001D96A
0x18001d906  lea     rcx, [rsp+0C8h+var_A8]
0x18001d90b  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18001d911  xor     r9d, r9d; unsigned int
0x18001d914  lea     r8, [rsp+0C8h+var_98]; struct CWStringArray *
0x18001d919  mov     rdx, rdi; unsigned __int16 *
0x18001d91c  mov     rcx, rsi; this
0x18001d91f  call    ?GetChildHashesByHash@CNamespaceHandle@@IEAAJPEBGAEAVCWStringArray@@K@Z; CNamespaceHandle::GetChildHashesByHash(ushort const *,CWStringArray &,ulong)
0x18001d924  mov     ebx, eax
0x18001d926  test    ebx, ebx
0x18001d928  js      loc_18001D9D8
0x18001d92e  xor     edi, edi
0x18001d930  lea     rcx, [rsp+0C8h+var_98]
0x18001d935  call    cs:__imp_?Size@CWStringArray@@QEBAHXZ; CWStringArray::Size(void)
0x18001d93b  cmp     edi, eax
0x18001d93d  jl      loc_18001DA14
0x18001d943  xor     ebx, ebx
0x18001d945  lea     rcx, [rsp+0C8h+var_98]
0x18001d94a  call    cs:__imp_??1CWStringArray@@QEAA@XZ; CWStringArray::~CWStringArray(void)
0x18001d950  mov     eax, ebx
0x18001d952  add     rsp, 98h
0x18001d959  pop     r14
0x18001d95b  pop     r13
0x18001d95d  pop     rdi
0x18001d95e  pop     rsi
0x18001d95f  pop     rbp
0x18001d960  pop     rbx
0x18001d961  retn
0x18001d962  mov     r9, rax
0x18001d965  mov     rax, [rax]
0x18001d968  jmp     short loc_18001D8FB
0x18001d96a  mov     rax, rdi
0x18001d96d  mov     rdx, [r9+20h]
0x18001d971  sub     rdx, rdi
0x18001d974  movzx   ecx, word ptr [rax]
0x18001d977  movzx   r8d, word ptr [rax+rdx]
0x18001d97c  sub     ecx, r8d
0x18001d97f  jnz     short loc_18001D98A
0x18001d981  add     rax, 2
0x18001d985  test    r8d, r8d
0x18001d988  jnz     short loc_18001D974
0x18001d98a  test    ecx, ecx
0x18001d98c  js      loc_18001D906
0x18001d992  mov     rax, [r9+28h]
0x18001d996  test    rax, rax
0x18001d999  jz      loc_18001D906
0x18001d99f  cmp     byte ptr [rax+131h], 0
0x18001d9a6  jz      loc_18001D906
0x18001d9ac  xor     ebx, ebx
0x18001d9ae  lea     rdi, [rax+0D0h]
0x18001d9b5  mov     rcx, rdi
0x18001d9b8  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18001d9be  cmp     ebx, eax
0x18001d9c0  jl      loc_18001DB21
0x18001d9c6  lea     rcx, [rsp+0C8h+var_A8]
0x18001d9cb  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18001d9d1  xor     ebx, ebx
0x18001d9d3  jmp     loc_18001D926
0x18001d9d8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001d9de  mov     edx, ebx
0x18001d9e0  mov     rcx, rax
0x18001d9e3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001d9e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d9f0  cmp     rcx, r13
0x18001d9f3  jz      loc_18001D945
0x18001d9f9  test    byte ptr [rcx+1Ch], 1
0x18001d9fd  jz      loc_18001D945
0x18001da03  cmp     byte ptr [rcx+19h], 2
0x18001da07  jb      loc_18001D945
0x18001da0d  mov     edx, 1DBh
0x18001da12  jmp     short loc_18001DA79
0x18001da14  mov     edx, edi
0x18001da16  lea     rcx, [rsp+0C8h+var_98]
0x18001da1b  call    cs:__imp_??ACWStringArray@@QEBAPEAGH@Z; CWStringArray::operator[](int)
0x18001da21  mov     r9, rbp; struct IWbemObjectSink *
0x18001da24  mov     r8, rax; unsigned __int16 *
0x18001da27  mov     rdx, r14; struct QL_LEVEL_1_RPN_EXPRESSION *
0x18001da2a  mov     rcx, rsi; this
0x18001da2d  call    ?ExecDeepInstanceQuery@CNamespaceHandle@@IEAAJPEAUQL_LEVEL_1_RPN_EXPRESSION@@PEBGPEAUIWbemObjectSink@@@Z; CNamespaceHandle::ExecDeepInstanceQuery(QL_LEVEL_1_RPN_EXPRESSION *,ushort const *,IWbemObjectSink *)
0x18001da32  mov     ebx, eax
0x18001da34  test    eax, eax
0x18001da36  js      short loc_18001DA3F
0x18001da38  inc     edi
0x18001da3a  jmp     loc_18001D930
0x18001da3f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001da45  mov     edx, ebx
0x18001da47  mov     rcx, rax
0x18001da4a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001da50  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da57  cmp     rcx, r13
0x18001da5a  jz      loc_18001D945
0x18001da60  test    byte ptr [rcx+1Ch], 1
0x18001da64  jz      loc_18001D945
0x18001da6a  cmp     byte ptr [rcx+19h], 2
0x18001da6e  jb      loc_18001D945
0x18001da74  mov     edx, 1DCh
0x18001da79  mov     r9d, ebx
0x18001da7c  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001da83  mov     rcx, [rcx+10h]
0x18001da87  call    WPP_SF_d
0x18001da8c  jmp     loc_18001D945
0x18001da91  test    byte ptr [rcx+1Ch], 1
0x18001da95  jz      loc_18001D877
0x18001da9b  cmp     byte ptr [rcx+19h], 5
0x18001da9f  jb      loc_18001D877
0x18001daa5  mov     edx, 1D9h
0x18001daaa  mov     rcx, [rcx+10h]
0x18001daae  call    WPP_SF_q
0x18001dab3  jmp     loc_18001D877
0x18001dab8  mov     eax, 80041033h
0x18001dabd  jmp     loc_18001D952
0x18001dac2  mov     eax, 80041032h
0x18001dac7  cmp     ebx, eax
0x18001dac9  jz      loc_18001D952
0x18001dacf  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001dad5  mov     edx, ebx
0x18001dad7  mov     rcx, rax
0x18001dada  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001dae0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dae7  cmp     rcx, r13
0x18001daea  jz      loc_18001D950
0x18001daf0  test    byte ptr [rcx+1Ch], 1
0x18001daf4  jz      loc_18001D950
0x18001dafa  cmp     byte ptr [rcx+19h], 2
0x18001dafe  jb      loc_18001D950
0x18001db04  mov     edx, 1DAh
0x18001db09  mov     r9d, ebx
0x18001db0c  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001db13  mov     rcx, [rcx+10h]
0x18001db17  call    WPP_SF_d
0x18001db1c  jmp     loc_18001D950
0x18001db21  mov     edx, ebx
0x18001db23  mov     rcx, rdi
0x18001db26  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18001db2c  lea     rdx, [rax+28h]
0x18001db30  lea     rcx, [rsp+0C8h+var_98]
0x18001db35  call    cs:__imp_?Add@CWStringArray@@QEAAHPEBG@Z; CWStringArray::Add(ushort const *)
0x18001db3b  test    eax, eax
0x18001db3d  js      short loc_18001DB46
0x18001db3f  inc     ebx
0x18001db41  jmp     loc_18001D9B5
0x18001db46  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001db4c  mov     ebx, 80041006h
0x18001db51  mov     edx, ebx
0x18001db53  mov     rcx, rax
0x18001db56  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001db5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db63  cmp     rcx, r13
0x18001db66  jz      short loc_18001DB90
0x18001db68  test    byte ptr [rcx+1Ch], 1
0x18001db6c  jz      short loc_18001DB90
0x18001db6e  cmp     byte ptr [rcx+19h], 2
0x18001db72  jb      short loc_18001DB90
0x18001db74  mov     edx, 14h
0x18001db79  mov     r9d, 80041006h
0x18001db7f  lea     r8, WPP_73e6a18982e8318987457e2893328bf6_Traceguids
0x18001db86  mov     rcx, [rcx+10h]
0x18001db8a  call    WPP_SF_d
0x18001db8f  nop
0x18001db90  lea     rcx, [rsp+0C8h+var_A8]
0x18001db95  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18001db9b  jmp     loc_18001D926
```
