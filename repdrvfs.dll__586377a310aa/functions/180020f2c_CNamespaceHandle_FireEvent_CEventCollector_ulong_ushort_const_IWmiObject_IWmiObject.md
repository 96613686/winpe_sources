# CNamespaceHandle::FireEvent(CEventCollector &,ulong,ushort const *,_IWmiObject *,_IWmiObject *)

- ea: `0x180020f2c`
- end: `0x180021162`
- name: `?FireEvent@CNamespaceHandle@@IEAAJAEAVCEventCollector@@KPEBGPEAU_IWmiObject@@2@Z`
- size: `566`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, struct CEventCollector *, int, const unsigned __int16 *, struct _IWmiObject *, struct _IWmiObject *)`
- caller_count: `7`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014290`
- `0x18001e370`
- `0x1800253d4`
- `0x1800262cc`
- `0x180027814`
- `0x1800345c0`
- `0x180035f1c`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180020f2c`
- `0x180048010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180020f80`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180020f80`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x1800210ba`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x1800210ba`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800210cc`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800210cc`
- `wbemcomn!??0WString@@QEAA@PEBG@Z` at `0x180020fb5`
- `wbemcomn!??0WString@@QEAA@PEBG@Z` at `0x180020fc3`
- `wbemcomn!??0WString@@QEAA@PEBG@Z` at `0x180020fb5`
- `wbemcomn!??0WString@@QEAA@PEBG@Z` at `0x180020fc3`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180020f9b`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180020f9b`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180021078`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180021078`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800210a9`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800210dd`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800210a9`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800210dd`
- `wbemcomn!GetMemLogObject` at `0x18002101e`
- `wbemcomn!GetMemLogObject` at `0x1800210fc`
- `wbemcomn!GetMemLogObject` at `0x18002101e`
- `wbemcomn!GetMemLogObject` at `0x1800210fc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002102c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002110a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002102c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002110a`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::FireEvent(
        CNamespaceHandle *this,
        struct CEventCollector *a2,
        int a3,
        const unsigned __int16 *a4,
        struct _IWmiObject *a5,
        struct _IWmiObject *a6)
{
  _QWORD *v10; // rbx
  const unsigned __int16 *v11; // rsi
  CMemoryLog *MemLogObject; // rax
  __int64 result; // rax
  int v14; // edi
  CMemoryLog *v15; // rax
  CMemoryLog *v16; // rax
  _QWORD v17[9]; // [rsp+20h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 285, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  try
  {
    v10 = CWin32DefaultArena::WbemMemAlloc(0x30u);
    v17[0] = v10;
    if ( v10 )
    {
      v11 = (const unsigned __int16 *)WString::operator unsigned short *((char *)this + 48);
      *v10 = &CRepEvent::`vftable';
      WString::WString((WString *)(v10 + 2), a4);
      WString::WString((WString *)(v10 + 3), v11);
      v10[4] = 0;
      v10[5] = 0;
      *((_DWORD *)v10 + 2) = a3;
      if ( a5 )
      {
        v10[4] = a5;
        (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)a5 + 8LL))(a5);
      }
      if ( a6 )
      {
        v10[5] = a6;
        (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)a6 + 8LL))(a6);
      }
    }
    if ( !v10 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217402);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          286,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          2147749894LL);
      }
      return 2147749894LL;
    }
    CInCritSec::CInCritSec((CInCritSec *)v17, (struct _RTL_CRITICAL_SECTION *)((char *)a2 + 104));
    if ( *((_BYTE *)a2 + 96) && (unsigned int)(*((_DWORD *)v10 + 2) - 7) > 2 )
    {
      (*(void (__fastcall **)(_QWORD *, __int64))*v10)(v10, 1);
      CInCritSec::~CInCritSec((CInCritSec *)v17);
      return 0;
    }
    if ( CFlexArray::Add(a2, v10) )
      v14 = -1;
    else
      v14 = CFlexArray::Size(a2) - 1;
    CInCritSec::~CInCritSec((CInCritSec *)v17);
    if ( v14 >= 0 )
      return 0;
    (*(void (__fastcall **)(_QWORD *, __int64))*v10)(v10, 1);
    v15 = GetMemLogObject();
    CMemoryLog::Write(v15, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 287, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    result = 2147749894LL;
  }
  catch ( CX_MemoryException )
  {
    v16 = GetMemLogObject();
    CMemoryLog::Write(v16, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 288, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  v10 = CWin32DefaultArena::WbemMemAlloc(0x30u);
}

```

## disassembly

```asm
0x180020f2c  push    rbx
0x180020f2e  push    rsi
0x180020f2f  push    rdi
0x180020f30  push    r13
0x180020f32  push    r14
0x180020f34  push    r15
0x180020f36  sub     rsp, 38h
0x180020f3a  mov     r14, r9
0x180020f3d  mov     r15d, r8d
0x180020f40  mov     rdi, rdx
0x180020f43  mov     rsi, rcx
0x180020f46  lea     r13, WPP_GLOBAL_Control
0x180020f4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f54  cmp     rcx, r13
0x180020f57  jz      short loc_180020F7B
0x180020f59  test    byte ptr [rcx+1Ch], 1
0x180020f5d  jz      short loc_180020F7B
0x180020f5f  cmp     byte ptr [rcx+19h], 5
0x180020f63  jb      short loc_180020F7B
0x180020f65  mov     edx, 11Dh
0x180020f6a  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180020f71  mov     rcx, [rcx+10h]
0x180020f75  call    WPP_SF_
0x180020f7a  nop
0x180020f7b  mov     ecx, 30h ; '0'
0x180020f80  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180020f86  mov     rbx, rax
0x180020f89  mov     [rsp+68h+var_48], rax
0x180020f8e  test    rbx, rbx
0x180020f91  jz      loc_180021019
0x180020f97  lea     rcx, [rsi+30h]
0x180020f9b  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x180020fa1  mov     rsi, rax
0x180020fa4  lea     rax, ??_7CRepEvent@@6B@; const CRepEvent::`vftable'
0x180020fab  mov     [rbx], rax
0x180020fae  lea     rcx, [rbx+10h]
0x180020fb2  mov     rdx, r14
0x180020fb5  call    cs:__imp_??0WString@@QEAA@PEBG@Z; WString::WString(ushort const *)
0x180020fbb  nop
0x180020fbc  lea     rcx, [rbx+18h]
0x180020fc0  mov     rdx, rsi
0x180020fc3  call    cs:__imp_??0WString@@QEAA@PEBG@Z; WString::WString(ushort const *)
0x180020fc9  nop
0x180020fca  mov     qword ptr [rbx+20h], 0
0x180020fd2  mov     qword ptr [rbx+28h], 0
0x180020fda  mov     [rbx+8], r15d
0x180020fde  mov     rcx, [rsp+68h+arg_20]
0x180020fe6  test    rcx, rcx
0x180020fe9  jz      short loc_180020FFB
0x180020feb  mov     [rbx+20h], rcx
0x180020fef  mov     rax, [rcx]
0x180020ff2  mov     rax, [rax+8]
0x180020ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ffb  mov     rcx, [rsp+68h+arg_28]
0x180021003  test    rcx, rcx
0x180021006  jz      short loc_180021019
0x180021008  mov     [rbx+28h], rcx
0x18002100c  mov     rax, [rcx]
0x18002100f  mov     rax, [rax+8]
0x180021013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021018  nop
0x180021019  test    rbx, rbx
0x18002101c  jnz     short loc_18002106F
0x18002101e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180021024  mov     edx, 80041006h
0x180021029  mov     rcx, rax
0x18002102c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180021032  mov     rcx, cs:WPP_GLOBAL_Control
0x180021039  cmp     rcx, r13
0x18002103c  jz      short loc_180021065
0x18002103e  test    byte ptr [rcx+1Ch], 1
0x180021042  jz      short loc_180021065
0x180021044  cmp     byte ptr [rcx+19h], 2
0x180021048  jb      short loc_180021065
0x18002104a  mov     edx, 11Eh
0x18002104f  mov     r9d, 80041006h
0x180021055  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18002105c  mov     rcx, [rcx+10h]
0x180021060  call    WPP_SF_d
0x180021065  mov     eax, 80041006h
0x18002106a  jmp     loc_180021153
0x18002106f  lea     rdx, [rdi+68h]
0x180021073  lea     rcx, [rsp+68h+var_48]
0x180021078  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18002107e  nop
0x18002107f  cmp     byte ptr [rdi+60h], 0
0x180021083  jz      short loc_1800210B4
0x180021085  mov     eax, [rbx+8]
0x180021088  sub     eax, 7
0x18002108b  cmp     eax, 2
0x18002108e  jbe     short loc_1800210B4
0x180021090  mov     rax, [rbx]
0x180021093  mov     edx, 1
0x180021098  mov     rcx, rbx
0x18002109b  mov     rax, [rax]
0x18002109e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210a3  nop
0x1800210a4  lea     rcx, [rsp+68h+var_48]
0x1800210a9  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x1800210af  jmp     loc_18002114A
0x1800210b4  mov     rdx, rbx
0x1800210b7  mov     rcx, rdi
0x1800210ba  call    cs:__imp_?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x1800210c0  test    eax, eax
0x1800210c2  jz      short loc_1800210C9
0x1800210c4  or      edi, 0FFFFFFFFh
0x1800210c7  jmp     short loc_1800210D5
0x1800210c9  mov     rcx, rdi
0x1800210cc  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x1800210d2  lea     edi, [rax-1]
0x1800210d5  shr     edi, 1Fh
0x1800210d8  lea     rcx, [rsp+68h+var_48]
0x1800210dd  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x1800210e3  xor     dil, 1
0x1800210e7  jnz     short loc_18002114A
0x1800210e9  mov     rax, [rbx]
0x1800210ec  mov     edx, 1
0x1800210f1  mov     rcx, rbx
0x1800210f4  mov     rax, [rax]
0x1800210f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210fc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180021102  mov     edx, 80041006h
0x180021107  mov     rcx, rax
0x18002110a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180021110  mov     rcx, cs:WPP_GLOBAL_Control
0x180021117  cmp     rcx, r13
0x18002111a  jz      short loc_180021143
0x18002111c  test    byte ptr [rcx+1Ch], 1
0x180021120  jz      short loc_180021143
0x180021122  cmp     byte ptr [rcx+19h], 2
0x180021126  jb      short loc_180021143
0x180021128  mov     edx, 11Fh
0x18002112d  mov     r9d, 80041006h
0x180021133  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18002113a  mov     rcx, [rcx+10h]
0x18002113e  call    WPP_SF_d
0x180021143  mov     eax, 80041006h
0x180021148  jmp     short loc_180021153
0x18002114a  xor     eax, eax
0x18002114c  jmp     short loc_180021153
0x18002114e  mov     eax, 80041006h
0x180021153  add     rsp, 38h
0x180021157  pop     r15
0x180021159  pop     r14
0x18002115b  pop     r13
0x18002115d  pop     rdi
0x18002115e  pop     rsi
0x18002115f  pop     rbx
0x180021160  retn
```
