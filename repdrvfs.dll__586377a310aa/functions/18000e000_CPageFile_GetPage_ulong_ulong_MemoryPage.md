# CPageFile::GetPage(ulong,ulong,MemoryPage * *)

- ea: `0x18000e000`
- end: `0x18000e236`
- name: `?GetPage@CPageFile@@QEAAKKKPEAPEAVMemoryPage@@@Z`
- size: `566`
- prototype: `__int64 __fastcall(CPageFile *this, unsigned int, __int64, struct MemoryPage **)`
- caller_count: `7`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000bc10`
- `0x18000d7e0`
- `0x18000fa20`
- `0x1800136b8`
- `0x180020b38`
- `0x180028a74`
- `0x18002bfd0`

## callees

- `0x1800012b8`
- `0x18000e000`
- `0x18000e240`
- `0x18003d184`

## import_xrefs

- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18000e029`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18000e029`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000e0a4`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000e19d`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000e226`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000e0a4`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000e19d`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000e226`
- `wbemcomn!GetMemLogObject` at `0x18000e0e2`
- `wbemcomn!GetMemLogObject` at `0x18000e149`
- `wbemcomn!GetMemLogObject` at `0x18000e1ad`
- `wbemcomn!GetMemLogObject` at `0x18000e1d2`
- `wbemcomn!GetMemLogObject` at `0x18000e0e2`
- `wbemcomn!GetMemLogObject` at `0x18000e149`
- `wbemcomn!GetMemLogObject` at `0x18000e1ad`
- `wbemcomn!GetMemLogObject` at `0x18000e1d2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e0f0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e157`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e1b8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e1e0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e0f0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e157`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e1b8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e1e0`

## pseudocode

```c
__int64 __fastcall CPageFile::GetPage(CPageFile *this, unsigned int a2, __int64 a3, struct MemoryPage **a4)
{
  unsigned __int64 v5; // rsi
  __int64 v7; // r8
  unsigned int v8; // edx
  unsigned int v9; // ebx
  CMemoryLog *v11; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v13; // rax
  CMemoryLog *v14; // rax
  char v15; // [rsp+48h] [rbp+20h] BYREF

  v5 = a2;
  if ( a4 )
  {
    CInCritSec::CInCritSec((CInCritSec *)&v15, (struct _RTL_CRITICAL_SECTION *)((char *)this + 16));
    v7 = *((_QWORD *)this + 41);
    if ( v5 >= 0xAAAAAAAAAAAAAAABuLL * ((*((_QWORD *)this + 42) - v7) >> 3) )
    {
      CRepositoryCorruption::SetRepositoryCorrupted(3, 0, 0);
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, 2);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 2);
      }
      CInCritSec::~CInCritSec((CInCritSec *)&v15);
      return 2;
    }
    else
    {
      v8 = *(_DWORD *)(v7 + 24 * v5);
      if ( v8 > 0xFFFFFFFD )
      {
        CRepositoryCorruption::SetRepositoryCorrupted(3, 0, 0);
        v14 = GetMemLogObject();
        CMemoryLog::Write(v14, 4317);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 4317);
        }
        CInCritSec::~CInCritSec((CInCritSec *)&v15);
        return 4317;
      }
      else
      {
        v9 = CPageCache::Read((CPageFile *)((char *)this + 64), v8 & 0x3FFFFFFF, a4, v5);
        if ( v9 )
        {
          v13 = GetMemLogObject();
          CMemoryLog::Write(v13, v9);
        }
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, v9);
        }
        CInCritSec::~CInCritSec((CInCritSec *)&v15);
        return v9;
      }
    }
  }
  else
  {
    v11 = GetMemLogObject();
    CMemoryLog::Write(v11, 87);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 87);
    }
    return 87;
  }
}

```

## disassembly

```asm
0x18000e000  mov     [rsp+arg_0], rbx
0x18000e005  mov     [rsp+arg_8], rsi
0x18000e00a  push    rdi
0x18000e00b  sub     rsp, 20h
0x18000e00f  mov     rdi, r9
0x18000e012  mov     esi, edx
0x18000e014  mov     rbx, rcx
0x18000e017  test    r9, r9
0x18000e01a  jz      loc_18000E0E2
0x18000e020  lea     rdx, [rcx+10h]
0x18000e024  lea     rcx, [rsp+28h+arg_18]
0x18000e029  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18000e02f  nop
0x18000e030  mov     r8, [rbx+148h]
0x18000e037  mov     rax, [rbx+150h]
0x18000e03e  sub     rax, r8
0x18000e041  sar     rax, 3
0x18000e045  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18000e04f  imul    rax, rdx
0x18000e053  cmp     rsi, rax
0x18000e056  jnb     loc_18000E13A
0x18000e05c  lea     rdx, [rsi+rsi*2]
0x18000e060  mov     edx, [r8+rdx*8]
0x18000e064  cmp     edx, 0FFFFFFFDh
0x18000e067  ja      loc_18000E1C3
0x18000e06d  and     edx, 3FFFFFFFh; unsigned int
0x18000e073  lea     rcx, [rbx+40h]; this
0x18000e077  mov     r9d, esi; unsigned int
0x18000e07a  mov     r8, rdi; struct MemoryPage **
0x18000e07d  call    ?Read@CPageCache@@QEAAKKPEAPEAVMemoryPage@@K@Z; CPageCache::Read(ulong,MemoryPage * *,ulong)
0x18000e082  mov     ebx, eax
0x18000e084  test    eax, eax
0x18000e086  jnz     loc_18000E1AD
0x18000e08c  lea     rax, WPP_GLOBAL_Control
0x18000e093  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e09a  cmp     rcx, rax
0x18000e09d  jnz     short loc_18000E0BC
0x18000e09f  lea     rcx, [rsp+28h+arg_18]
0x18000e0a4  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18000e0aa  mov     eax, ebx
0x18000e0ac  mov     rbx, [rsp+28h+arg_0]
0x18000e0b1  mov     rsi, [rsp+28h+arg_8]
0x18000e0b6  add     rsp, 20h
0x18000e0ba  pop     rdi
0x18000e0bb  retn
0x18000e0bc  test    byte ptr [rcx+1Ch], 1
0x18000e0c0  jz      short loc_18000E09F
0x18000e0c2  cmp     byte ptr [rcx+19h], 2
0x18000e0c6  jb      short loc_18000E09F
0x18000e0c8  mov     edx, 4Eh ; 'N'
0x18000e0cd  mov     r9d, ebx
0x18000e0d0  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18000e0d7  mov     rcx, [rcx+10h]
0x18000e0db  call    WPP_SF_d
0x18000e0e0  jmp     short loc_18000E09F
0x18000e0e2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000e0e8  mov     edx, 57h ; 'W'
0x18000e0ed  mov     rcx, rax
0x18000e0f0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000e0f6  lea     rax, WPP_GLOBAL_Control
0x18000e0fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e104  cmp     rcx, rax
0x18000e107  jz      short loc_18000E130
0x18000e109  test    byte ptr [rcx+1Ch], 1
0x18000e10d  jz      short loc_18000E130
0x18000e10f  cmp     byte ptr [rcx+19h], 2
0x18000e113  jb      short loc_18000E130
0x18000e115  mov     edx, 4Bh ; 'K'
0x18000e11a  mov     r9d, 57h ; 'W'
0x18000e120  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18000e127  mov     rcx, [rcx+10h]
0x18000e12b  call    WPP_SF_d
0x18000e130  mov     eax, 57h ; 'W'
0x18000e135  jmp     loc_18000E0AC
0x18000e13a  xor     r8d, r8d; unsigned int
0x18000e13d  xor     edx, edx; bool
0x18000e13f  mov     ecx, 3; int
0x18000e144  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x18000e149  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000e14f  mov     edx, 2
0x18000e154  mov     rcx, rax
0x18000e157  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000e15d  lea     rax, WPP_GLOBAL_Control
0x18000e164  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e16b  cmp     rcx, rax
0x18000e16e  jz      short loc_18000E198
0x18000e170  test    byte ptr [rcx+1Ch], 1
0x18000e174  jz      short loc_18000E198
0x18000e176  cmp     byte ptr [rcx+19h], 2
0x18000e17a  jb      short loc_18000E198
0x18000e17c  mov     edx, 4Ch ; 'L'
0x18000e181  mov     r9d, 2
0x18000e187  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18000e18e  mov     rcx, [rcx+10h]
0x18000e192  call    WPP_SF_d
0x18000e197  nop
0x18000e198  lea     rcx, [rsp+28h+arg_18]
0x18000e19d  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18000e1a3  mov     eax, 2
0x18000e1a8  jmp     loc_18000E0AC
0x18000e1ad  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000e1b3  mov     edx, ebx
0x18000e1b5  mov     rcx, rax
0x18000e1b8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000e1be  jmp     loc_18000E08C
0x18000e1c3  xor     r8d, r8d; unsigned int
0x18000e1c6  xor     edx, edx; bool
0x18000e1c8  mov     ecx, 3; int
0x18000e1cd  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x18000e1d2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000e1d8  mov     edx, 10DDh
0x18000e1dd  mov     rcx, rax
0x18000e1e0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000e1e6  lea     rax, WPP_GLOBAL_Control
0x18000e1ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1f4  cmp     rcx, rax
0x18000e1f7  jz      short loc_18000E221
0x18000e1f9  test    byte ptr [rcx+1Ch], 1
0x18000e1fd  jz      short loc_18000E221
0x18000e1ff  cmp     byte ptr [rcx+19h], 2
0x18000e203  jb      short loc_18000E221
0x18000e205  mov     edx, 4Dh ; 'M'
0x18000e20a  mov     r9d, 10DDh
0x18000e210  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18000e217  mov     rcx, [rcx+10h]
0x18000e21b  call    WPP_SF_d
0x18000e220  nop
0x18000e221  lea     rcx, [rsp+28h+arg_18]
0x18000e226  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18000e22c  mov     eax, 10DDh
0x18000e231  jmp     loc_18000E0AC
```
