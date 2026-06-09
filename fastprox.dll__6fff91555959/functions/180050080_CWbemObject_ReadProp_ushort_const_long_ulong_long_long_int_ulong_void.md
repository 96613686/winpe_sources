# CWbemObject::ReadProp(ushort const *,long,ulong,long *,long *,int *,ulong *,void *)

- ea: `0x180050080`
- end: `0x18005030c`
- name: `?ReadProp@CWbemObject@@UEAAJPEBGJKPEAJ1PEAHPEAKPEAX@Z`
- size: `652`
- prototype: `__int64 __usercall@<rax>(CWbemObject *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, int@<r8d>, unsigned int@<r9d>, int *, int *, int *, unsigned int *, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180037120`
- `0x18004f4f4`
- `0x180050080`
- `0x18006ee70`
- `0x18008d544`
- `0x18008dd1c`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800501d3`
- `wbemcomn!GetMemLogObject` at `0x1800501e6`
- `wbemcomn!GetMemLogObject` at `0x1800501d3`
- `wbemcomn!GetMemLogObject` at `0x1800501e6`
- `wbemcomn!?IsNull@CVar@@QEAAHXZ` at `0x180050147`
- `wbemcomn!?IsNull@CVar@@QEAAHXZ` at `0x180050147`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180050117`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180050117`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800501de`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800501f6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800501de`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800501f6`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18005018a`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18005018a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180050262`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180050262`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWbemObject::ReadProp(
        CWbemObject *this,
        const unsigned __int16 *a2,
        int a3,
        unsigned int a4,
        int *a5,
        int *a6,
        int *a7,
        unsigned int *a8,
        unsigned __int16 *a9)
{
  int UserBuffFromCVar; // ebx
  __int16 v13; // di
  unsigned int v14; // edi
  int IsNull; // eax
  __int64 result; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v18; // rax
  struct IUnknown *v19; // rax
  CWmiArray *v20; // rdi
  CMemoryLog *v21; // rax
  CMemoryLog *v22; // rax
  int v23; // [rsp+34h] [rbp-64h] BYREF
  CWbemObject *v24; // [rsp+38h] [rbp-60h]
  struct IUnknown *v25; // [rsp+40h] [rbp-58h]
  _BYTE v26[80]; // [rsp+48h] [rbp-50h] BYREF

  try
  {
    if ( !a3 )
    {
      v24 = this;
      (*(void (__fastcall **)(CWbemObject *, __int64))(*(_QWORD *)this + 280LL))(this, 1);
      v23 = 0;
      UserBuffFromCVar = (*(__int64 (__fastcall **)(CWbemObject *, const unsigned __int16 *, int *, int *))(*(_QWORD *)this + 864LL))(
                           this,
                           a2,
                           &v23,
                           a6);
      if ( UserBuffFromCVar >= 0 )
      {
        v13 = v23;
        if ( a5 )
          *a5 = v23;
        if ( (v13 & 0x2000) == 0 )
        {
          v14 = v13 & 0xFFF;
          CVar::CVar((CVar *)v26);
          UserBuffFromCVar = (*(__int64 (__fastcall **)(CWbemObject *, const unsigned __int16 *, _BYTE *))(*(_QWORD *)this + 776LL))(
                               this,
                               a2,
                               v26);
          if ( UserBuffFromCVar >= 0 )
          {
            IsNull = CVar::IsNull((CVar *)v26);
            *a7 = IsNull;
            if ( !IsNull )
              UserBuffFromCVar = CUntypedValue::LoadUserBuffFromCVar(v14, (struct CVar *)v26, a4, a8, a9);
          }
          CVar::~CVar((CVar *)v26);
LABEL_11:
          if ( UserBuffFromCVar >= 0 )
            goto LABEL_12;
          goto LABEL_15;
        }
        *a8 = 8;
        if ( a4 < 8 || !a9 )
        {
          UserBuffFromCVar = -2147217348;
          goto LABEL_11;
        }
        v19 = (struct IUnknown *)CWin32DefaultArena::WbemMemAlloc(0x40u);
        v25 = v19;
        if ( v19 )
          v20 = CWmiArray::CWmiArray(v19);
        else
          v20 = 0;
        if ( !v20 )
        {
          UserBuffFromCVar = -2147217402;
          goto LABEL_11;
        }
        UserBuffFromCVar = CWmiArray::InitializePropertyArray(v20, this, a2);
        if ( UserBuffFromCVar >= 0 )
        {
          UserBuffFromCVar = CWmiArray::QueryInterface(v20, &IID__IWmiArray, (void **)a9);
          goto LABEL_11;
        }
      }
LABEL_15:
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, UserBuffFromCVar);
LABEL_12:
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          176,
          WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids,
          (unsigned int)UserBuffFromCVar);
      }
      (*(void (__fastcall **)(CWbemObject *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
      return (unsigned int)UserBuffFromCVar;
    }
    v18 = GetMemLogObject();
    CMemoryLog::Write(v18, -2147217400);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749896LL);
    }
    result = 2147749896LL;
  }
  catch ( CX_MemoryException )
  {
    v21 = GetMemLogObject();
    CMemoryLog::Write(v21, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 177, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  catch ( CX_Exception )
  {
    v22 = GetMemLogObject();
    CMemoryLog::Write(v22, -2147217398);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 178, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749898LL);
    }
    return 2147749898LL;
  }
  return result;
}

```

## disassembly

```asm
0x180050080  push    rbx
0x180050082  push    rsi
0x180050083  push    rdi
0x180050084  push    r14
0x180050086  push    r15
0x180050088  sub     rsp, 70h
0x18005008c  mov     r14d, r9d
0x18005008f  mov     r15, rdx
0x180050092  mov     rsi, rcx
0x180050095  test    r8d, r8d
0x180050098  jnz     loc_1800501E6
0x18005009e  mov     [rsp+98h+var_60], rcx
0x1800500a3  mov     rax, [rcx]
0x1800500a6  lea     edx, [r8+1]
0x1800500aa  mov     rax, [rax+118h]
0x1800500b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500b6  nop
0x1800500b7  mov     [rsp+98h+var_64], 0
0x1800500bf  mov     rax, [rsi]
0x1800500c2  mov     r9, [rsp+98h+arg_28]
0x1800500ca  lea     r8, [rsp+98h+var_64]
0x1800500cf  mov     rdx, r15
0x1800500d2  mov     rcx, rsi
0x1800500d5  mov     rax, [rax+360h]
0x1800500dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500e1  mov     ebx, eax
0x1800500e3  mov     [rsp+98h+var_68], eax
0x1800500e7  test    eax, eax
0x1800500e9  js      loc_1800501D3
0x1800500ef  mov     rax, [rsp+98h+arg_20]
0x1800500f7  mov     edi, [rsp+98h+var_64]
0x1800500fb  test    rax, rax
0x1800500fe  jz      short loc_180050102
0x180050100  mov     [rax], edi
0x180050102  bt      edi, 0Dh
0x180050106  jb      loc_18005023C
0x18005010c  and     edi, 0FFFh
0x180050112  lea     rcx, [rsp+98h+var_50]
0x180050117  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x18005011d  nop
0x18005011e  mov     rax, [rsi]
0x180050121  lea     r8, [rsp+98h+var_50]
0x180050126  mov     rdx, r15
0x180050129  mov     rcx, rsi
0x18005012c  mov     rax, [rax+308h]
0x180050133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050138  mov     ebx, eax
0x18005013a  mov     [rsp+98h+var_68], eax
0x18005013e  test    eax, eax
0x180050140  js      short loc_180050185
0x180050142  lea     rcx, [rsp+98h+var_50]
0x180050147  call    cs:__imp_?IsNull@CVar@@QEAAHXZ; CVar::IsNull(void)
0x18005014d  mov     rdx, [rsp+98h+arg_30]
0x180050155  mov     [rdx], eax
0x180050157  test    eax, eax
0x180050159  jnz     short loc_180050185
0x18005015b  mov     rax, [rsp+98h+arg_40]
0x180050163  mov     [rsp+98h+var_78], rax; void *
0x180050168  mov     r9, [rsp+98h+arg_38]; unsigned int *
0x180050170  mov     r8d, r14d; unsigned int
0x180050173  lea     rdx, [rsp+98h+var_50]; struct CVar *
0x180050178  mov     ecx, edi; unsigned int
0x18005017a  call    ?LoadUserBuffFromCVar@CUntypedValue@@SAJKPEAVCVar@@KPEAKPEAX@Z; CUntypedValue::LoadUserBuffFromCVar(ulong,CVar *,ulong,ulong *,void *)
0x18005017f  mov     ebx, eax
0x180050181  mov     [rsp+98h+var_68], eax
0x180050185  lea     rcx, [rsp+98h+var_50]
0x18005018a  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180050190  test    ebx, ebx
0x180050192  js      short loc_1800501D3
0x180050194  lea     rax, WPP_GLOBAL_Control
0x18005019b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800501a2  cmp     rcx, rax
0x1800501a5  jz      short loc_1800501B1
0x1800501a7  test    byte ptr [rcx+1Ch], 1
0x1800501ab  jnz     loc_1800502D4
0x1800501b1  mov     rax, [rsi]
0x1800501b4  xor     edx, edx
0x1800501b6  mov     rcx, rsi
0x1800501b9  mov     rax, [rax+120h]
0x1800501c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800501c5  mov     eax, ebx
0x1800501c7  add     rsp, 70h
0x1800501cb  pop     r15
0x1800501cd  pop     r14
0x1800501cf  pop     rdi
0x1800501d0  pop     rsi
0x1800501d1  pop     rbx
0x1800501d2  retn
0x1800501d3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800501d9  mov     edx, ebx
0x1800501db  mov     rcx, rax
0x1800501de  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800501e4  jmp     short loc_180050194
0x1800501e6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800501ec  mov     ebx, 80041008h
0x1800501f1  mov     edx, ebx
0x1800501f3  mov     rcx, rax
0x1800501f6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800501fc  lea     rax, WPP_GLOBAL_Control
0x180050203  mov     rcx, cs:WPP_GLOBAL_Control
0x18005020a  cmp     rcx, rax
0x18005020d  jnz     short loc_180050213
0x18005020f  mov     eax, ebx
0x180050211  jmp     short loc_1800501C7
0x180050213  test    byte ptr [rcx+1Ch], 1
0x180050217  jz      short loc_18005020F
0x180050219  cmp     byte ptr [rcx+19h], 2
0x18005021d  jb      short loc_18005020F
0x18005021f  mov     edx, 0AFh
0x180050224  mov     r9d, 80041008h
0x18005022a  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x180050231  mov     rcx, [rcx+10h]
0x180050235  call    WPP_SF_d
0x18005023a  jmp     short loc_18005020F
0x18005023c  mov     rax, [rsp+98h+arg_38]
0x180050244  mov     dword ptr [rax], 8
0x18005024a  cmp     r14d, 8
0x18005024e  jb      short loc_1800502C6
0x180050250  mov     r14, [rsp+98h+arg_40]
0x180050258  test    r14, r14
0x18005025b  jz      short loc_1800502C6
0x18005025d  mov     ecx, 40h ; '@'
0x180050262  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180050268  mov     [rsp+98h+var_58], rax
0x18005026d  test    rax, rax
0x180050270  jz      short loc_18005027F
0x180050272  mov     rcx, rax; this
0x180050275  call    ??0CWmiArray@@QEAA@XZ; CWmiArray::CWmiArray(void)
0x18005027a  mov     rdi, rax
0x18005027d  jmp     short loc_180050281
0x18005027f  xor     edi, edi
0x180050281  test    rdi, rdi
0x180050284  jz      short loc_1800502BF
0x180050286  mov     r8, r15; unsigned __int16 *
0x180050289  mov     rdx, rsi; struct _IWmiObject *
0x18005028c  mov     rcx, rdi; this
0x18005028f  call    ?InitializePropertyArray@CWmiArray@@QEAAJPEAU_IWmiObject@@PEBG@Z; CWmiArray::InitializePropertyArray(_IWmiObject *,ushort const *)
0x180050294  mov     ebx, eax
0x180050296  mov     [rsp+98h+var_68], eax
0x18005029a  test    eax, eax
0x18005029c  js      loc_1800501D3
0x1800502a2  mov     r8, r14; void **
0x1800502a5  lea     rdx, IID__IWmiArray; struct _GUID *
0x1800502ac  mov     rcx, rdi; this
0x1800502af  call    ?QueryInterface@CWmiArray@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWmiArray::QueryInterface(_GUID const &,void * *)
0x1800502b4  mov     ebx, eax
0x1800502b6  mov     [rsp+98h+var_68], eax
0x1800502ba  jmp     loc_180050190
0x1800502bf  mov     ebx, 80041006h
0x1800502c4  jmp     short loc_1800502CB
0x1800502c6  mov     ebx, 8004103Ch
0x1800502cb  mov     [rsp+98h+var_68], ebx
0x1800502cf  jmp     loc_180050190
0x1800502d4  cmp     byte ptr [rcx+19h], 2
0x1800502d8  jb      loc_1800501B1
0x1800502de  mov     edx, 0B0h
0x1800502e3  mov     r9d, ebx
0x1800502e6  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x1800502ed  mov     rcx, [rcx+10h]
0x1800502f1  call    WPP_SF_d
0x1800502f6  jmp     loc_1800501B1
0x1800502fb  mov     eax, 80041006h
0x180050300  jmp     short loc_180050307
0x180050302  mov     eax, 8004100Ah
0x180050307  jmp     loc_1800501C7
```
