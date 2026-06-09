# CRefresherRecord::RemoteRefresh(long,long *,_WBEM_REFRESHED_OBJECT * *)

- ea: `0x18008bdf0`
- end: `0x18008c09f`
- name: `?RemoteRefresh@CRefresherRecord@@UEAAJJPEAJPEAPEAU_WBEM_REFRESHED_OBJECT@@@Z`
- size: `687`
- prototype: `__int64 __fastcall(CRefresherRecord *__hidden this, int, int *, struct _WBEM_REFRESHED_OBJECT **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180037120`
- `0x18008bc90`
- `0x18008bdf0`
- `0x18008c4c8`
- `0x180091972`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008be42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008be42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008bf98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c020`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008bf98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c020`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18008bebe`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18008bebe`
- `wbemcomn!GetMemLogObject` at `0x18008bf0e`
- `wbemcomn!GetMemLogObject` at `0x18008bfac`
- `wbemcomn!GetMemLogObject` at `0x18008c031`
- `wbemcomn!GetMemLogObject` at `0x18008bf0e`
- `wbemcomn!GetMemLogObject` at `0x18008bfac`
- `wbemcomn!GetMemLogObject` at `0x18008c031`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18008bea7`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18008bea7`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18008c07f`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18008c07f`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18008be19`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18008be19`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008bf1e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008bfb7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008c03c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008bf1e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008bfb7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008c03c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRefresherRecord::RemoteRefresh(
        struct _RTL_CRITICAL_SECTION *this,
        __int64 a2,
        int *a3,
        struct _WBEM_REFRESHED_OBJECT **a4)
{
  _DWORD *v7; // rdi
  ULONG_PTR *p_SpinCount; // rbp
  struct _WBEM_REFRESHED_OBJECT *v9; // rax
  int v10; // ebx
  int v11; // r13d
  int v12; // ebp
  int v13; // r12d
  CFlexArray *p_OwningThread; // rax
  int v15; // r15d
  int v16; // edx
  int v17; // eax
  CMemoryLog *MemLogObject; // rax
  CWbemRefreshingSvc *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  CMemoryLog *v22; // rax
  int v23; // eax
  CMemoryLog *v24; // rax
  CProviderRecord *v26; // [rsp+20h] [rbp-58h]
  CFlexArray *v27; // [rsp+28h] [rbp-50h]
  _BYTE v28[72]; // [rsp+30h] [rbp-48h] BYREF
  int v29; // [rsp+80h] [rbp+8h]
  int v30; // [rsp+98h] [rbp+20h] BYREF

  CInCritSec::CInCritSec((CInCritSec *)v28, this + 5);
  v7 = (_DWORD *)&this[3].SpinCount + 1;
  p_SpinCount = &this[3].SpinCount;
  if ( a4 )
  {
    v9 = (struct _WBEM_REFRESHED_OBJECT *)CoTaskMemAlloc(24LL * (*(_DWORD *)p_SpinCount + *v7));
    *a4 = v9;
    if ( !v9 )
    {
      MemLogObject = GetMemLogObject();
      v10 = -2147217402;
      CMemoryLog::Write(MemLogObject, -2147217402);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v20 = 23;
        v21 = 2147749894LL;
LABEL_46:
        WPP_SF_d(*((_QWORD *)v19 + 2), v20, WPP_03c64eaa4d8c32ecfb51fbe2c30fec97_Traceguids, v21);
      }
      goto LABEL_47;
    }
    memset_0(v9, 0, 24LL * (*(_DWORD *)p_SpinCount + *v7));
  }
  v10 = 0;
  if ( a3 )
    *a3 = *(_DWORD *)p_SpinCount + *v7;
  v30 = 0;
  v29 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  p_OwningThread = (CFlexArray *)&this[1].OwningThread;
  v27 = (CFlexArray *)&this[1].OwningThread;
  v15 = 0;
  while ( v13 < CFlexArray::Size(p_OwningThread) )
  {
    v26 = (CProviderRecord *)CFlexArray::GetAt(v27, v13);
    v10 = CProviderRecord::Refresh(v26, v16);
    if ( v10 >= 0 )
    {
      if ( a4 )
      {
        v10 = CProviderRecord::Store(v26, *a4, &v30);
        if ( v10 < 0 )
        {
          if ( *a4 )
          {
            CoTaskMemFree(*a4);
            *a4 = 0;
          }
          *a3 = 0;
          v22 = GetMemLogObject();
          CMemoryLog::Write(v22, v10);
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v20 = 24;
LABEL_45:
            v21 = (unsigned int)v10;
            goto LABEL_46;
          }
          goto LABEL_47;
        }
      }
    }
    if ( v11 )
    {
      v17 = v29;
    }
    else
    {
      v11 = 1;
      v17 = v10;
      v29 = v10;
    }
    if ( v10 )
    {
      if ( v15 )
        v12 = 1;
    }
    else
    {
      v15 = 1;
      if ( v17 )
        v12 = 1;
    }
    ++v13;
    p_OwningThread = v27;
  }
  if ( v12 )
  {
    v10 = 262160;
  }
  else if ( !v15 )
  {
    v10 = v29;
  }
  v23 = v30;
  if ( v30 != *a3 )
  {
    *a3 = v30;
    if ( !v23 )
    {
      if ( *a4 )
      {
        CoTaskMemFree(*a4);
        *a4 = 0;
      }
    }
  }
  if ( v10 < 0 )
  {
    v24 = GetMemLogObject();
    CMemoryLog::Write(v24, v10);
  }
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v20 = 25;
    goto LABEL_45;
  }
LABEL_47:
  CInCritSec::~CInCritSec((CInCritSec *)v28);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18008bdf0  mov     [rsp+arg_8], rbx
0x18008bdf5  push    rbp
0x18008bdf6  push    rsi
0x18008bdf7  push    rdi
0x18008bdf8  push    r12
0x18008bdfa  push    r13
0x18008bdfc  push    r14
0x18008bdfe  push    r15
0x18008be00  sub     rsp, 40h
0x18008be04  mov     rsi, r9
0x18008be07  mov     r14, r8
0x18008be0a  mov     r15, rcx
0x18008be0d  lea     rdx, [rcx+0C8h]
0x18008be14  lea     rcx, [rsp+78h+var_48]
0x18008be19  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18008be1f  nop
0x18008be20  lea     rdi, [r15+9Ch]
0x18008be27  lea     rbp, [r15+98h]
0x18008be2e  test    rsi, rsi
0x18008be31  jz      short loc_18008BE6E
0x18008be33  mov     eax, [rdi]
0x18008be35  add     eax, [rbp+0]
0x18008be38  cdqe
0x18008be3a  lea     rcx, [rax+rax*2]
0x18008be3e  shl     rcx, 3; cb
0x18008be42  call    cs:__imp_CoTaskMemAlloc
0x18008be48  mov     [rsi], rax
0x18008be4b  test    rax, rax
0x18008be4e  jz      loc_18008BF0E
0x18008be54  mov     ecx, [rdi]
0x18008be56  add     ecx, [rbp+0]
0x18008be59  movsxd  rcx, ecx
0x18008be5c  lea     r8, [rcx+rcx*2]
0x18008be60  shl     r8, 3; Size
0x18008be64  xor     edx, edx; Val
0x18008be66  mov     rcx, rax; void *
0x18008be69  call    memset_0
0x18008be6e  xor     ebx, ebx
0x18008be70  test    r14, r14
0x18008be73  jz      short loc_18008BE7D
0x18008be75  mov     eax, [rdi]
0x18008be77  add     eax, [rbp+0]
0x18008be7a  mov     [r14], eax
0x18008be7d  mov     [rsp+78h+arg_18], ebx
0x18008be84  xor     eax, eax
0x18008be86  mov     [rsp+78h+arg_0], eax
0x18008be8d  xor     r13d, r13d
0x18008be90  xor     ebp, ebp
0x18008be92  xor     r12d, r12d
0x18008be95  lea     rax, [r15+38h]
0x18008be99  mov     [rsp+78h+var_50], rax
0x18008be9e  lea     edi, [rbp+1]
0x18008bea1  mov     r15d, ebx
0x18008bea4  mov     rcx, rax
0x18008bea7  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18008bead  cmp     r12d, eax
0x18008beb0  jge     loc_18008BFEF
0x18008beb6  mov     edx, r12d
0x18008beb9  mov     rcx, [rsp+78h+var_50]
0x18008bebe  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18008bec4  mov     [rsp+78h+var_58], rax
0x18008bec9  mov     rcx, rax; this
0x18008becc  call    ?Refresh@CProviderRecord@@QEAAJJ@Z; CProviderRecord::Refresh(long)
0x18008bed1  mov     ebx, eax
0x18008bed3  test    eax, eax
0x18008bed5  js      short loc_18008BEFB
0x18008bed7  test    rsi, rsi
0x18008beda  jz      short loc_18008BEFB
0x18008bedc  lea     r8, [rsp+78h+arg_18]; int *
0x18008bee4  mov     rdx, [rsi]; struct _WBEM_REFRESHED_OBJECT *
0x18008bee7  mov     rcx, [rsp+78h+var_58]; this
0x18008beec  call    ?Store@CProviderRecord@@QEAAJPEAU_WBEM_REFRESHED_OBJECT@@PEAJ@Z; CProviderRecord::Store(_WBEM_REFRESHED_OBJECT *,long *)
0x18008bef1  mov     ebx, eax
0x18008bef3  test    eax, eax
0x18008bef5  js      loc_18008BF90
0x18008befb  test    r13d, r13d
0x18008befe  jnz     short loc_18008BF62
0x18008bf00  mov     r13d, edi
0x18008bf03  mov     eax, ebx
0x18008bf05  mov     [rsp+78h+arg_0], ebx
0x18008bf0c  jmp     short loc_18008BF69
0x18008bf0e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008bf14  mov     ebx, 80041006h
0x18008bf19  mov     edx, ebx
0x18008bf1b  mov     rcx, rax
0x18008bf1e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008bf24  lea     rax, WPP_GLOBAL_Control
0x18008bf2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bf32  cmp     rcx, rax
0x18008bf35  jz      loc_18008C07A
0x18008bf3b  mov     edi, 1
0x18008bf40  test    [rcx+1Ch], dil
0x18008bf44  jz      loc_18008C07A
0x18008bf4a  cmp     byte ptr [rcx+19h], 2
0x18008bf4e  jb      loc_18008C07A
0x18008bf54  lea     edx, [rdi+16h]
0x18008bf57  mov     r9d, 80041006h
0x18008bf5d  jmp     loc_18008C069
0x18008bf62  mov     eax, [rsp+78h+arg_0]
0x18008bf69  test    ebx, ebx
0x18008bf6b  jnz     short loc_18008BF7D
0x18008bf6d  mov     r15d, edi
0x18008bf70  test    r13d, r13d
0x18008bf73  jz      short loc_18008BF83
0x18008bf75  test    eax, eax
0x18008bf77  jz      short loc_18008BF83
0x18008bf79  mov     ebp, edi
0x18008bf7b  jmp     short loc_18008BF83
0x18008bf7d  test    r15d, r15d
0x18008bf80  cmovnz  ebp, edi
0x18008bf83  add     r12d, edi
0x18008bf86  mov     rax, [rsp+78h+var_50]
0x18008bf8b  jmp     loc_18008BEA4
0x18008bf90  mov     rcx, [rsi]; pv
0x18008bf93  test    rcx, rcx
0x18008bf96  jz      short loc_18008BFA5
0x18008bf98  call    cs:__imp_CoTaskMemFree
0x18008bf9e  mov     qword ptr [rsi], 0
0x18008bfa5  mov     dword ptr [r14], 0
0x18008bfac  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008bfb2  mov     edx, ebx
0x18008bfb4  mov     rcx, rax
0x18008bfb7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008bfbd  lea     rax, WPP_GLOBAL_Control
0x18008bfc4  mov     rcx, cs:WPP_GLOBAL_Control
0x18008bfcb  cmp     rcx, rax
0x18008bfce  jz      loc_18008C07A
0x18008bfd4  test    [rcx+1Ch], dil
0x18008bfd8  jz      loc_18008C07A
0x18008bfde  cmp     byte ptr [rcx+19h], 2
0x18008bfe2  jb      loc_18008C07A
0x18008bfe8  mov     edx, 18h
0x18008bfed  jmp     short loc_18008C066
0x18008bfef  test    ebp, ebp
0x18008bff1  jz      short loc_18008BFFA
0x18008bff3  mov     ebx, 40010h
0x18008bff8  jmp     short loc_18008C005
0x18008bffa  test    r15d, r15d
0x18008bffd  cmovz   ebx, [rsp+78h+arg_0]
0x18008c005  mov     eax, [rsp+78h+arg_18]
0x18008c00c  cmp     eax, [r14]
0x18008c00f  jz      short loc_18008C02D
0x18008c011  mov     [r14], eax
0x18008c014  test    eax, eax
0x18008c016  jnz     short loc_18008C02D
0x18008c018  mov     rcx, [rsi]; pv
0x18008c01b  test    rcx, rcx
0x18008c01e  jz      short loc_18008C02D
0x18008c020  call    cs:__imp_CoTaskMemFree
0x18008c026  mov     qword ptr [rsi], 0
0x18008c02d  test    ebx, ebx
0x18008c02f  jns     short loc_18008C042
0x18008c031  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008c037  mov     edx, ebx
0x18008c039  mov     rcx, rax
0x18008c03c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008c042  lea     rax, WPP_GLOBAL_Control
0x18008c049  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c050  cmp     rcx, rax
0x18008c053  jz      short loc_18008C07A
0x18008c055  test    [rcx+1Ch], dil
0x18008c059  jz      short loc_18008C07A
0x18008c05b  cmp     byte ptr [rcx+19h], 2
0x18008c05f  jb      short loc_18008C07A
0x18008c061  mov     edx, 19h
0x18008c066  mov     r9d, ebx
0x18008c069  lea     r8, WPP_03c64eaa4d8c32ecfb51fbe2c30fec97_Traceguids
0x18008c070  mov     rcx, [rcx+10h]
0x18008c074  call    WPP_SF_d
0x18008c079  nop
0x18008c07a  lea     rcx, [rsp+78h+var_48]
0x18008c07f  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18008c085  mov     eax, ebx
0x18008c087  mov     rbx, [rsp+78h+arg_8]
0x18008c08f  add     rsp, 40h
0x18008c093  pop     r15
0x18008c095  pop     r14
0x18008c097  pop     r13
0x18008c099  pop     r12
0x18008c09b  pop     rdi
0x18008c09c  pop     rsi
0x18008c09d  pop     rbp
0x18008c09e  retn
```
