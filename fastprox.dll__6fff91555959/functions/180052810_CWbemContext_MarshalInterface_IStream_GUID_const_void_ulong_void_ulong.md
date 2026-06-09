# CWbemContext::MarshalInterface(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x180052810`
- end: `0x180052a27`
- name: `?MarshalInterface@CWbemContext@@UEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `535`
- prototype: `int(CWbemContext *__hidden this, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180037120`
- `0x180052810`
- `0x180052a30`
- `0x18009e010`

## import_xrefs

- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800528cc`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800528cc`
- `wbemcomn!GetMemLogObject` at `0x180052903`
- `wbemcomn!GetMemLogObject` at `0x180052944`
- `wbemcomn!GetMemLogObject` at `0x180052985`
- `wbemcomn!GetMemLogObject` at `0x1800529cd`
- `wbemcomn!GetMemLogObject` at `0x180052903`
- `wbemcomn!GetMemLogObject` at `0x180052944`
- `wbemcomn!GetMemLogObject` at `0x180052985`
- `wbemcomn!GetMemLogObject` at `0x1800529cd`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18005288d`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800528bd`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18005288d`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800528bd`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800528f2`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800528f2`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18005282b`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18005282b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005290f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005294f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052990`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800529d8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005290f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005294f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052990`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800529d8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWbemContext::MarshalInterface(
        struct _RTL_CRITICAL_SECTION *this,
        struct IStream *a2,
        const struct _GUID *a3,
        void *a4)
{
  int v6; // ebx
  CFlexArray *p_SpinCount; // rbp
  int i; // edi
  CWbemContext::CContextObj *v9; // rax
  CMemoryLog *v11; // rax
  CWbemRefreshingSvc *v12; // r10
  __int64 v13; // rdx
  __int64 v14; // rcx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v16; // rax
  CMemoryLog *v17; // rax
  int v18; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v19[48]; // [rsp+38h] [rbp-30h] BYREF

  CInCritSec::CInCritSec((CInCritSec *)v19, this + 4);
  v6 = ((__int64 (__fastcall *)(struct IStream *, LONG *, __int64))a2->lpVtbl->Write)(a2, &this[3].LockCount, 4);
  if ( v6 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v6);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_9;
    }
    v13 = 84;
LABEL_14:
    v14 = *((_QWORD *)v12 + 2);
LABEL_27:
    WPP_SF_d(v14, v13, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids, (unsigned int)v6);
    goto LABEL_9;
  }
  v6 = ((__int64 (__fastcall *)(struct IStream *, HANDLE, _QWORD, _QWORD))a2->lpVtbl->Write)(
         a2,
         this[3].OwningThread,
         (unsigned int)(16 * this[3].LockCount),
         0);
  if ( v6 < 0 )
  {
    v16 = GetMemLogObject();
    CMemoryLog::Write(v16, v6);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_9;
    }
    v13 = 85;
    goto LABEL_14;
  }
  p_SpinCount = (CFlexArray *)&this->SpinCount;
  v18 = CFlexArray::Size(p_SpinCount);
  v6 = ((__int64 (__fastcall *)(struct IStream *, int *, __int64))a2->lpVtbl->Write)(a2, &v18, 4);
  if ( v6 < 0 )
  {
    v11 = GetMemLogObject();
    CMemoryLog::Write(v11, v6);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_9;
    }
    v13 = 86;
    goto LABEL_14;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= CFlexArray::Size(p_SpinCount) )
    {
      v6 = 0;
      goto LABEL_9;
    }
    v9 = (CWbemContext::CContextObj *)CFlexArray::GetAt(p_SpinCount, i);
    v6 = CWbemContext::CContextObj::Marshal(v9, a2);
    if ( v6 < 0 )
      break;
  }
  v17 = GetMemLogObject();
  CMemoryLog::Write(v17, v6);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = 87;
    v14 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    goto LABEL_27;
  }
LABEL_9:
  CInCritSec::~CInCritSec((CInCritSec *)v19);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180052810  push    rbx
0x180052812  push    rbp
0x180052813  push    rsi
0x180052814  push    rdi
0x180052815  sub     rsp, 48h
0x180052819  mov     rsi, rdx
0x18005281c  mov     rbp, rcx
0x18005281f  lea     rdx, [rcx+0A0h]
0x180052826  lea     rcx, [rsp+68h+var_30]
0x18005282b  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180052831  nop
0x180052832  lea     rdi, [rbp+80h]
0x180052839  mov     rax, [rsi]
0x18005283c  xor     r9d, r9d
0x18005283f  lea     r8d, [r9+4]
0x180052843  mov     rdx, rdi
0x180052846  mov     rcx, rsi
0x180052849  mov     rax, [rax+20h]
0x18005284d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052852  mov     ebx, eax
0x180052854  test    eax, eax
0x180052856  js      loc_180052944
0x18005285c  mov     rax, [rsi]
0x18005285f  mov     r8d, [rdi]
0x180052862  shl     r8d, 4
0x180052866  xor     r9d, r9d
0x180052869  mov     rdx, [rbp+88h]
0x180052870  mov     rcx, rsi
0x180052873  mov     rax, [rax+20h]
0x180052877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005287c  mov     ebx, eax
0x18005287e  test    eax, eax
0x180052880  js      loc_180052985
0x180052886  add     rbp, 20h ; ' '
0x18005288a  mov     rcx, rbp
0x18005288d  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180052893  mov     [rsp+68h+var_38], eax
0x180052897  mov     rax, [rsi]
0x18005289a  xor     r9d, r9d
0x18005289d  lea     r8d, [r9+4]
0x1800528a1  lea     rdx, [rsp+68h+var_38]
0x1800528a6  mov     rcx, rsi
0x1800528a9  mov     rax, [rax+20h]
0x1800528ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800528b2  mov     ebx, eax
0x1800528b4  test    eax, eax
0x1800528b6  js      short loc_180052903
0x1800528b8  xor     edi, edi
0x1800528ba  mov     rcx, rbp
0x1800528bd  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x1800528c3  cmp     edi, eax
0x1800528c5  jge     short loc_1800528EB
0x1800528c7  mov     edx, edi
0x1800528c9  mov     rcx, rbp
0x1800528cc  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x1800528d2  mov     rdx, rsi; struct IStream *
0x1800528d5  mov     rcx, rax; this
0x1800528d8  call    ?Marshal@CContextObj@CWbemContext@@QEAAJPEAUIStream@@@Z; CWbemContext::CContextObj::Marshal(IStream *)
0x1800528dd  mov     ebx, eax
0x1800528df  test    eax, eax
0x1800528e1  js      loc_1800529CD
0x1800528e7  inc     edi
0x1800528e9  jmp     short loc_1800528BA
0x1800528eb  xor     ebx, ebx
0x1800528ed  lea     rcx, [rsp+68h+var_30]
0x1800528f2  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x1800528f8  mov     eax, ebx
0x1800528fa  add     rsp, 48h
0x1800528fe  pop     rdi
0x1800528ff  pop     rsi
0x180052900  pop     rbp
0x180052901  pop     rbx
0x180052902  retn
0x180052903  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180052909  nop
0x18005290a  mov     edx, ebx
0x18005290c  mov     rcx, rax
0x18005290f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180052915  lea     rcx, WPP_GLOBAL_Control
0x18005291c  mov     r10, cs:WPP_GLOBAL_Control
0x180052923  cmp     r10, rcx
0x180052926  jz      short loc_1800528ED
0x180052928  test    byte ptr [r10+1Ch], 1
0x18005292d  jz      short loc_1800528ED
0x18005292f  cmp     byte ptr [r10+19h], 2
0x180052934  jb      short loc_1800528ED
0x180052936  mov     edx, 56h ; 'V'
0x18005293b  mov     rcx, [r10+10h]
0x18005293f  jmp     loc_180052A12
0x180052944  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005294a  mov     edx, ebx
0x18005294c  mov     rcx, rax
0x18005294f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180052955  lea     rcx, WPP_GLOBAL_Control
0x18005295c  mov     r10, cs:WPP_GLOBAL_Control
0x180052963  cmp     r10, rcx
0x180052966  jz      short loc_1800528ED
0x180052968  test    byte ptr [r10+1Ch], 1
0x18005296d  jz      loc_1800528ED
0x180052973  cmp     byte ptr [r10+19h], 2
0x180052978  jb      loc_1800528ED
0x18005297e  mov     edx, 54h ; 'T'
0x180052983  jmp     short loc_18005293B
0x180052985  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005298b  mov     edx, ebx
0x18005298d  mov     rcx, rax
0x180052990  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180052996  lea     rcx, WPP_GLOBAL_Control
0x18005299d  mov     r10, cs:WPP_GLOBAL_Control
0x1800529a4  cmp     r10, rcx
0x1800529a7  jz      loc_1800528ED
0x1800529ad  test    byte ptr [r10+1Ch], 1
0x1800529b2  jz      loc_1800528ED
0x1800529b8  cmp     byte ptr [r10+19h], 2
0x1800529bd  jb      loc_1800528ED
0x1800529c3  mov     edx, 55h ; 'U'
0x1800529c8  jmp     loc_18005293B
0x1800529cd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800529d3  mov     edx, ebx
0x1800529d5  mov     rcx, rax
0x1800529d8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800529de  lea     rcx, WPP_GLOBAL_Control
0x1800529e5  mov     rax, cs:WPP_GLOBAL_Control
0x1800529ec  cmp     rax, rcx
0x1800529ef  jz      loc_1800528ED
0x1800529f5  test    byte ptr [rax+1Ch], 1
0x1800529f9  jz      loc_1800528ED
0x1800529ff  cmp     byte ptr [rax+19h], 2
0x180052a03  jb      loc_1800528ED
0x180052a09  mov     edx, 57h ; 'W'
0x180052a0e  mov     rcx, [rax+10h]
0x180052a12  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x180052a19  mov     r9d, ebx
0x180052a1c  call    WPP_SF_d
0x180052a21  jmp     loc_1800528ED
```
