# CProviderRecord::Remove(long,int *)

- ea: `0x18008c0a8`
- end: `0x18008c266`
- name: `?Remove@CProviderRecord@@QEAAJJPEAH@Z`
- size: `446`
- prototype: `__int64 __fastcall(CProviderRecord *__hidden this, int, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18008c26c`

## callees

- `0x180037120`
- `0x18008ab80`
- `0x18008b7bc`
- `0x18008c0a8`

## import_xrefs

- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18008c0f7`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18008c11a`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18008c1ab`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18008c1ce`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18008c0f7`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18008c11a`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18008c1ab`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18008c1ce`
- `wbemcomn!GetMemLogObject` at `0x18008c146`
- `wbemcomn!GetMemLogObject` at `0x18008c1fd`
- `wbemcomn!GetMemLogObject` at `0x18008c146`
- `wbemcomn!GetMemLogObject` at `0x18008c1fd`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18008c0e4`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18008c198`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18008c0e4`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18008c198`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18008c24f`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18008c24f`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18008c0c9`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18008c0c9`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x18008c128`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x18008c1dc`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x18008c128`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x18008c1dc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008c151`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008c208`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008c151`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008c208`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProviderRecord::Remove(CProviderRecord *this, int a2, int *a3)
{
  int v6; // edi
  CFlexArray *v7; // rbp
  _DWORD *v8; // rax
  int v9; // ebx
  CEnumRequestRecord *v10; // rsi
  CMemoryLog *MemLogObject; // rax
  CWbemRefreshingSvc *v12; // rcx
  __int64 v13; // rdx
  int v14; // edi
  CFlexArray *v15; // rsi
  _DWORD *v16; // rax
  CEnumRequestRecord *v17; // rbp
  CMemoryLog *v18; // rax
  _BYTE v20[72]; // [rsp+20h] [rbp-48h] BYREF

  CInCritSec::CInCritSec((CInCritSec *)v20, (struct _RTL_CRITICAL_SECTION *)((char *)this + 48));
  *a3 = 0;
  v6 = 0;
  v7 = (CProviderRecord *)((char *)this + 88);
  while ( v6 < CFlexArray::Size((CProviderRecord *)((char *)this + 88)) )
  {
    v8 = CFlexArray::GetAt((CProviderRecord *)((char *)this + 88), v6);
    if ( v8[2] == a2 )
    {
      v9 = CProviderRecord::Cancel(this, v8[6]);
      v10 = (CEnumRequestRecord *)CFlexArray::GetAt(v7, v6);
      if ( !CFlexArray::RemoveAt(v7, v6) && v10 )
        CEnumRequestRecord::`vector deleting destructor'(v10, 1u);
      if ( v9 < 0 )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, v9);
      }
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 14;
LABEL_27:
        WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_03c64eaa4d8c32ecfb51fbe2c30fec97_Traceguids, (unsigned int)v9);
      }
      goto LABEL_29;
    }
    ++v6;
  }
  v14 = 0;
  v15 = (CProviderRecord *)((char *)this + 184);
  while ( 1 )
  {
    if ( v14 >= CFlexArray::Size((CProviderRecord *)((char *)this + 184)) )
    {
      v9 = 1;
      goto LABEL_29;
    }
    v16 = CFlexArray::GetAt((CProviderRecord *)((char *)this + 184), v14);
    if ( v16[2] == a2 )
      break;
    ++v14;
  }
  v9 = CProviderRecord::Cancel(this, v16[6]);
  v17 = (CEnumRequestRecord *)CFlexArray::GetAt(v15, v14);
  if ( !CFlexArray::RemoveAt(v15, v14) && v17 )
    CEnumRequestRecord::`vector deleting destructor'(v17, 1u);
  *a3 = 1;
  if ( v9 < 0 )
  {
    v18 = GetMemLogObject();
    CMemoryLog::Write(v18, v9);
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = 15;
    goto LABEL_27;
  }
LABEL_29:
  CInCritSec::~CInCritSec((CInCritSec *)v20);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18008c0a8  push    rbx
0x18008c0aa  push    rbp
0x18008c0ab  push    rsi
0x18008c0ac  push    rdi
0x18008c0ad  push    r12
0x18008c0af  push    r14
0x18008c0b1  push    r15
0x18008c0b3  sub     rsp, 30h
0x18008c0b7  mov     r15, r8
0x18008c0ba  mov     r14d, edx
0x18008c0bd  mov     rbx, rcx
0x18008c0c0  lea     rdx, [rcx+30h]
0x18008c0c4  lea     rcx, [rsp+68h+var_48]
0x18008c0c9  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18008c0cf  nop
0x18008c0d0  mov     dword ptr [r15], 0
0x18008c0d7  xor     edi, edi
0x18008c0d9  lea     rbp, [rbx+58h]
0x18008c0dd  lea     r12d, [rdi+1]
0x18008c0e1  mov     rcx, rbp
0x18008c0e4  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18008c0ea  cmp     edi, eax
0x18008c0ec  jge     loc_18008C18C
0x18008c0f2  mov     edx, edi
0x18008c0f4  mov     rcx, rbp
0x18008c0f7  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18008c0fd  cmp     [rax+8], r14d
0x18008c101  jz      short loc_18008C108
0x18008c103  add     edi, r12d
0x18008c106  jmp     short loc_18008C0E1
0x18008c108  mov     edx, [rax+18h]; int
0x18008c10b  mov     rcx, rbx; this
0x18008c10e  call    ?Cancel@CProviderRecord@@QEAAJJ@Z; CProviderRecord::Cancel(long)
0x18008c113  mov     ebx, eax
0x18008c115  mov     edx, edi
0x18008c117  mov     rcx, rbp
0x18008c11a  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18008c120  mov     rsi, rax
0x18008c123  mov     edx, edi
0x18008c125  mov     rcx, rbp
0x18008c128  call    cs:__imp_?RemoveAt@CFlexArray@@QEAAHH@Z; CFlexArray::RemoveAt(int)
0x18008c12e  test    eax, eax
0x18008c130  jnz     short loc_18008C142
0x18008c132  test    rsi, rsi
0x18008c135  jz      short loc_18008C142
0x18008c137  mov     edx, r12d; unsigned int
0x18008c13a  mov     rcx, rsi; this
0x18008c13d  call    ??_ECEnumRequestRecord@@UEAAPEAXI@Z; CEnumRequestRecord::`vector deleting destructor'(uint)
0x18008c142  test    ebx, ebx
0x18008c144  jns     short loc_18008C157
0x18008c146  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008c14c  mov     edx, ebx
0x18008c14e  mov     rcx, rax
0x18008c151  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008c157  lea     rax, WPP_GLOBAL_Control
0x18008c15e  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c165  cmp     rcx, rax
0x18008c168  jz      loc_18008C24A
0x18008c16e  test    [rcx+1Ch], r12b
0x18008c172  jz      loc_18008C24A
0x18008c178  cmp     byte ptr [rcx+19h], 2
0x18008c17c  jb      loc_18008C24A
0x18008c182  mov     edx, 0Eh
0x18008c187  jmp     loc_18008C232
0x18008c18c  xor     edi, edi
0x18008c18e  lea     rsi, [rbx+0B8h]
0x18008c195  mov     rcx, rsi
0x18008c198  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18008c19e  cmp     edi, eax
0x18008c1a0  jge     loc_18008C247
0x18008c1a6  mov     edx, edi
0x18008c1a8  mov     rcx, rsi
0x18008c1ab  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18008c1b1  cmp     [rax+8], r14d
0x18008c1b5  jz      short loc_18008C1BC
0x18008c1b7  add     edi, r12d
0x18008c1ba  jmp     short loc_18008C195
0x18008c1bc  mov     edx, [rax+18h]; int
0x18008c1bf  mov     rcx, rbx; this
0x18008c1c2  call    ?Cancel@CProviderRecord@@QEAAJJ@Z; CProviderRecord::Cancel(long)
0x18008c1c7  mov     ebx, eax
0x18008c1c9  mov     edx, edi
0x18008c1cb  mov     rcx, rsi
0x18008c1ce  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18008c1d4  mov     rbp, rax
0x18008c1d7  mov     edx, edi
0x18008c1d9  mov     rcx, rsi
0x18008c1dc  call    cs:__imp_?RemoveAt@CFlexArray@@QEAAHH@Z; CFlexArray::RemoveAt(int)
0x18008c1e2  test    eax, eax
0x18008c1e4  jnz     short loc_18008C1F6
0x18008c1e6  test    rbp, rbp
0x18008c1e9  jz      short loc_18008C1F6
0x18008c1eb  mov     edx, r12d; unsigned int
0x18008c1ee  mov     rcx, rbp; this
0x18008c1f1  call    ??_ECEnumRequestRecord@@UEAAPEAXI@Z; CEnumRequestRecord::`vector deleting destructor'(uint)
0x18008c1f6  mov     [r15], r12d
0x18008c1f9  test    ebx, ebx
0x18008c1fb  jns     short loc_18008C20E
0x18008c1fd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008c203  mov     edx, ebx
0x18008c205  mov     rcx, rax
0x18008c208  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008c20e  lea     rax, WPP_GLOBAL_Control
0x18008c215  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c21c  cmp     rcx, rax
0x18008c21f  jz      short loc_18008C24A
0x18008c221  test    [rcx+1Ch], r12b
0x18008c225  jz      short loc_18008C24A
0x18008c227  cmp     byte ptr [rcx+19h], 2
0x18008c22b  jb      short loc_18008C24A
0x18008c22d  mov     edx, 0Fh
0x18008c232  mov     r9d, ebx
0x18008c235  lea     r8, WPP_03c64eaa4d8c32ecfb51fbe2c30fec97_Traceguids
0x18008c23c  mov     rcx, [rcx+10h]
0x18008c240  call    WPP_SF_d
0x18008c245  jmp     short loc_18008C24A
0x18008c247  mov     ebx, r12d
0x18008c24a  lea     rcx, [rsp+68h+var_48]
0x18008c24f  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18008c255  mov     eax, ebx
0x18008c257  add     rsp, 30h
0x18008c25b  pop     r15
0x18008c25d  pop     r14
0x18008c25f  pop     r12
0x18008c261  pop     rdi
0x18008c262  pop     rsi
0x18008c263  pop     rbp
0x18008c264  pop     rbx
0x18008c265  retn
```
