# CWbemClasslessInstancePacket::SetObjectMemory(CWbemInstance *,uchar *,ulong)

- ea: `0x18001ac00`
- end: `0x18001b298`
- name: `?SetObjectMemory@CWbemClasslessInstancePacket@@MEAAJPEAVCWbemInstance@@PEAEK@Z`
- size: `1688`
- prototype: `__int64 __fastcall(CWbemClasslessInstancePacket *__hidden this, struct CWbemInstance *, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18001aaa0`
- `0x18001ac00`
- `0x18001b2a0`
- `0x18001b4bc`
- `0x18001c1b0`
- `0x18001cb00`
- `0x18001e1b0`
- `0x180037120`
- `0x18006fa4c`
- `0x180091966`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18001afe2`
- `wbemcomn!GetMemLogObject` at `0x18001aff8`
- `wbemcomn!GetMemLogObject` at `0x18001b072`
- `wbemcomn!GetMemLogObject` at `0x18001b12d`
- `wbemcomn!GetMemLogObject` at `0x18001b1d7`
- `wbemcomn!GetMemLogObject` at `0x18001afe2`
- `wbemcomn!GetMemLogObject` at `0x18001aff8`
- `wbemcomn!GetMemLogObject` at `0x18001b072`
- `wbemcomn!GetMemLogObject` at `0x18001b12d`
- `wbemcomn!GetMemLogObject` at `0x18001b1d7`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18001acfb`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18001acfb`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18001ac74`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18001ac74`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001afed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b003`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b080`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b138`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b1e2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001afed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b003`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b080`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b138`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001b1e2`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001af19`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001b023`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001b10f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001b26b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001af19`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001b023`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001b10f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001b26b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CWbemClasslessInstancePacket::SetObjectMemory(
        CWbemClasslessInstancePacket *this,
        struct CWbemInstance *a2,
        const unsigned __int16 *a3,
        int a4)
{
  unsigned __int64 v4; // r12
  struct CWbemInstance *v5; // r15
  __int64 v7; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // rdi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // r13
  struct _RTL_CRITICAL_SECTION *CriticalSection; // rdi
  PRTL_CRITICAL_SECTION_DEBUG v11; // rsi
  int v12; // edi
  __int64 v13; // rsi
  __int64 v14; // rdi
  __int64 v15; // rcx
  unsigned __int64 v16; // r13
  const unsigned __int16 *v17; // rax
  __int64 v18; // r15
  __int64 v19; // rax
  unsigned __int8 *v20; // rcx
  unsigned __int8 *v22; // rcx
  unsigned __int64 v23; // rdx
  unsigned __int8 *v24; // r13
  __int64 v25; // rax
  CMemoryLog *v26; // rax
  CMemoryLog *v27; // rax
  CMemoryLog *v28; // rax
  CMemoryLog *v29; // rax
  CMemoryLog *v30; // rax
  CMemoryLog *MemLogObject; // rax
  __int128 v32; // [rsp+20h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+30h] [rbp-98h]
  char pExceptionObject; // [rsp+38h] [rbp-90h] BYREF
  __int64 v35; // [rsp+40h] [rbp-88h] BYREF
  __int64 v36; // [rsp+48h] [rbp-80h]
  int v37; // [rsp+50h] [rbp-78h] BYREF
  int v38; // [rsp+54h] [rbp-74h] BYREF
  __int64 v39; // [rsp+58h] [rbp-70h] BYREF
  __int64 v40; // [rsp+60h] [rbp-68h]
  __int64 v41; // [rsp+68h] [rbp-60h]
  __int128 Buf2; // [rsp+70h] [rbp-58h] BYREF
  _BYTE v43[72]; // [rsp+80h] [rbp-48h] BYREF

  v4 = a4;
  v5 = a2;
  v7 = 0;
  v39 = 0;
  v35 = 0;
  v32 = 0;
  v33 = 0;
  try
  {
    std::vector<EmbeddedObj,wbem_allocator<EmbeddedObj>>::_Reallocate(&v32, 2);
  }
  catch ( CX_MemoryException )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids, 2147749894LL);
    }
    if ( (_QWORD)v32 )
    {
      CWin32DefaultArena::WbemMemFree((void *)v32);
      v32 = 0;
      v33 = 0;
    }
    return 2147749894LL;
  }
  v8 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 5);
  Buf2 = *(_OWORD *)(*((_QWORD *)this + 3) + 8LL);
  CInCritSec::CInCritSec((CInCritSec *)v43, v8);
  DebugInfo = v8[1].DebugInfo;
  CriticalSection = DebugInfo->CriticalSection;
  v11 = DebugInfo;
  if ( BYTE1(CriticalSection->LockSemaphore) )
    goto LABEL_42;
  do
  {
    if ( memcmp_0(&CriticalSection->SpinCount, &Buf2, 0x10u) < 0 )
    {
      CriticalSection = (struct _RTL_CRITICAL_SECTION *)CriticalSection->OwningThread;
    }
    else
    {
      v11 = (PRTL_CRITICAL_SECTION_DEBUG)CriticalSection;
      CriticalSection = (struct _RTL_CRITICAL_SECTION *)CriticalSection->DebugInfo;
    }
  }
  while ( !BYTE1(CriticalSection->LockSemaphore) );
  if ( v11 == DebugInfo || memcmp_0(&Buf2, &v11->EntryCount, 0x10u) < 0 )
  {
LABEL_42:
    v12 = -2147217406;
  }
  else
  {
    v7 = *(_QWORD *)&v11[1].Type;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
    v12 = 0;
  }
  CInCritSec::~CInCritSec((CInCritSec *)v43);
  if ( v12 < 0 )
  {
    v26 = GetMemLogObject();
    CMemoryLog::Write(v26, v12);
  }
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_6039d850a549361afdc48cca3ddd98df_Traceguids,
      (unsigned int)v12);
  }
  if ( v12 < 0 )
  {
    v27 = GetMemLogObject();
    CMemoryLog::Write(v27, v12);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
        (unsigned int)v12);
    }
  }
  else
  {
    v36 = v7;
    v12 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v7)(v7, &IID__IWmiObject, &v39);
    if ( v12 < 0 )
    {
      v30 = GetMemLogObject();
      CMemoryLog::Write(v30, v12);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
          (unsigned int)v12);
      }
    }
    else
    {
      v13 = v39;
      v40 = v39;
      v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v39 + 528LL))(v39, 0, &v35);
      if ( v12 >= 0 )
      {
        v14 = v35;
        v41 = v35;
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v35 + 600LL))(v35) )
        {
          v28 = GetMemLogObject();
          CMemoryLog::Write(v28, -2147217393);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              38,
              WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
              2147749903LL);
          }
          if ( v14 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          v41 = 0;
          if ( v13 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          v40 = 0;
          if ( v7 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
          v36 = 0;
          if ( (_QWORD)v32 )
          {
            CWin32DefaultArena::WbemMemFree((void *)v32);
            v32 = 0;
            v33 = 0;
          }
          return 2147749903LL;
        }
        else
        {
          if ( !v4 )
            throw (CX_Exception *)&pExceptionObject;
          v15 = v35;
          *(_QWORD *)&Buf2 = v35;
          v16 = 1;
          v17 = a3;
          if ( (*(_BYTE *)a3 & 4) != 0 )
          {
            v18 = (int)CCompressedString::ValidateSize((CCompressedString *)((char *)a3 + 1), a4 - 1) + 1LL;
            v16 = v18 + (int)CCompressedString::ValidateSize((CCompressedString *)((char *)a3 + v18), a4 - (int)v18);
            v5 = a2;
            v17 = a3;
            v15 = Buf2;
          }
          if ( a4 < 0 )
          {
            v37 = 534;
            throw (SafeIntException *)&v37;
          }
          if ( v4 < v16 )
          {
            v38 = 534;
            throw (SafeIntException *)&v38;
          }
          v19 = CInstancePart::ValidateBuffer(
                  (unsigned __int8 *)v17 + v16,
                  v4 - v16,
                  (int **)(v15 + 400),
                  (__int64)&v32);
          SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(&Buf2, v16, v19);
          while ( (_QWORD)v32 != *((_QWORD *)&v32 + 1) )
          {
            v22 = *(unsigned __int8 **)(*((_QWORD *)&v32 + 1) - 16LL);
            v23 = *(_QWORD *)(*((_QWORD *)&v32 + 1) - 16LL + 8);
            *((_QWORD *)&v32 + 1) -= 16LL;
            CEmbeddedObject::ValidateBuffer(v22, v23);
          }
          *((_DWORD *)v5 + 42) = a4;
          *((_QWORD *)v5 + 9) = a3;
          if ( (*(_BYTE *)a3 & 4) != 0 )
          {
            v24 = (unsigned __int8 *)a3 + 1;
            *((_QWORD *)v5 + 10) = (char *)a3 + 1;
            if ( *((_BYTE *)a3 + 1) == 1 )
            {
              v20 = &v24[(int)(2 * (CCompressedString::fast_wcslen(a3 + 1) + 1) + 1)];
            }
            else
            {
              v25 = -1;
              do
                ++v25;
              while ( v24[v25 + 1] );
              v20 = &v24[(int)v25 + 2];
            }
          }
          else
          {
            *((_QWORD *)v5 + 10) = 0;
            v20 = 0;
          }
          *((_QWORD *)v5 + 11) = v20;
          *((_DWORD *)v5 + 15) = 3;
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids, 0);
          }
          if ( v14 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          v41 = 0;
          if ( v13 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          v40 = 0;
          if ( v7 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
          v36 = 0;
          if ( (_QWORD)v32 )
          {
            CWin32DefaultArena::WbemMemFree((void *)v32);
            v32 = 0;
            v33 = 0;
          }
          return 0;
        }
      }
      v29 = GetMemLogObject();
      CMemoryLog::Write(v29, v12);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
          (unsigned int)v12);
      }
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      v40 = 0;
    }
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v36 = 0;
  }
  if ( (_QWORD)v32 )
  {
    CWin32DefaultArena::WbemMemFree((void *)v32);
    v32 = 0;
    v33 = 0;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001ac00  mov     [rsp+arg_18], r9d
0x18001ac05  mov     [rsp+arg_10], r8
0x18001ac0a  mov     [rsp+arg_8], rdx
0x18001ac0f  push    rbx
0x18001ac10  push    rsi
0x18001ac11  push    rdi
0x18001ac12  push    r12
0x18001ac14  push    r13
0x18001ac16  push    r14
0x18001ac18  push    r15
0x18001ac1a  sub     rsp, 90h
0x18001ac21  movsxd  r12, r9d
0x18001ac24  mov     r15, rdx
0x18001ac27  mov     rsi, rcx
0x18001ac2a  xor     r14d, r14d
0x18001ac2d  mov     ebx, r14d
0x18001ac30  mov     [rsp+0C8h+var_70], r14
0x18001ac35  mov     [rsp+0C8h+var_88], r14
0x18001ac3a  xorps   xmm0, xmm0
0x18001ac3d  movdqu  [rsp+0C8h+var_A8], xmm0
0x18001ac43  mov     [rsp+0C8h+var_98], r14
0x18001ac48  mov     edx, 2
0x18001ac4d  lea     rcx, [rsp+0C8h+var_A8]
0x18001ac52  call    ?_Reallocate@?$vector@UEmbeddedObj@@V?$wbem_allocator@UEmbeddedObj@@@@@std@@IEAAX_K@Z; std::vector<EmbeddedObj,wbem_allocator<EmbeddedObj>>::_Reallocate(unsigned __int64)
0x18001ac57  nop
0x18001ac58  mov     rdi, [rsi+28h]
0x18001ac5c  mov     rax, [rsi+18h]
0x18001ac60  movups  xmm0, xmmword ptr [rax+8]
0x18001ac64  movups  [rsp+0C8h+Buf2], xmm0
0x18001ac69  mov     rdx, rdi
0x18001ac6c  lea     rcx, [rsp+0C8h+var_48]
0x18001ac74  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18001ac7a  nop
0x18001ac7b  mov     r13, [rdi+28h]
0x18001ac7f  mov     rdi, [r13+8]
0x18001ac83  mov     rsi, r13
0x18001ac86  cmp     byte ptr [rdi+19h], 0
0x18001ac8a  jnz     loc_18001AF9D
0x18001ac90  lea     rcx, [rdi+20h]; Buf1
0x18001ac94  mov     r8d, 10h; Size
0x18001ac9a  lea     rdx, [rsp+0C8h+Buf2]; Buf2
0x18001ac9f  call    memcmp_0
0x18001aca4  test    eax, eax
0x18001aca6  js      loc_18001AFA7
0x18001acac  mov     rsi, rdi
0x18001acaf  mov     rdi, [rdi]
0x18001acb2  cmp     byte ptr [rdi+19h], 0
0x18001acb6  jz      short loc_18001AC90
0x18001acb8  cmp     rsi, r13
0x18001acbb  jz      loc_18001AF9D
0x18001acc1  lea     rdx, [rsi+20h]; Buf2
0x18001acc5  mov     r8d, 10h; Size
0x18001accb  lea     rcx, [rsp+0C8h+Buf2]; Buf1
0x18001acd0  call    memcmp_0
0x18001acd5  test    eax, eax
0x18001acd7  js      loc_18001AF9D
0x18001acdd  mov     rbx, [rsi+30h]
0x18001ace1  mov     rax, [rbx]
0x18001ace4  mov     rcx, rbx
0x18001ace7  mov     rax, [rax+8]
0x18001aceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acf0  mov     edi, r14d
0x18001acf3  lea     rcx, [rsp+0C8h+var_48]
0x18001acfb  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18001ad01  test    edi, edi
0x18001ad03  js      loc_18001AFE2
0x18001ad09  lea     r13, WPP_GLOBAL_Control
0x18001ad10  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad17  cmp     rcx, r13
0x18001ad1a  jz      short loc_18001AD26
0x18001ad1c  test    byte ptr [rcx+1Ch], 1
0x18001ad20  jnz     loc_18001B21D
0x18001ad26  test    edi, edi
0x18001ad28  js      loc_18001AFF8
0x18001ad2e  mov     [rsp+0C8h+var_80], rbx
0x18001ad33  mov     rax, [rbx]
0x18001ad36  lea     r8, [rsp+0C8h+var_70]
0x18001ad3b  lea     rdx, IID__IWmiObject
0x18001ad42  mov     rcx, rbx
0x18001ad45  mov     rax, [rax]
0x18001ad48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad4d  mov     edi, eax
0x18001ad4f  test    eax, eax
0x18001ad51  js      loc_18001B1D7
0x18001ad57  mov     rsi, [rsp+0C8h+var_70]
0x18001ad5c  mov     [rsp+0C8h+var_68], rsi
0x18001ad61  mov     rcx, [rsp+0C8h+var_70]
0x18001ad66  mov     rax, [rcx]
0x18001ad69  lea     r8, [rsp+0C8h+var_88]
0x18001ad6e  xor     edx, edx
0x18001ad70  mov     rax, [rax+210h]
0x18001ad77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad7c  mov     edi, eax
0x18001ad7e  test    eax, eax
0x18001ad80  js      loc_18001B12D
0x18001ad86  mov     rdi, [rsp+0C8h+var_88]
0x18001ad8b  mov     [rsp+0C8h+var_60], rdi
0x18001ad90  mov     rcx, [rsp+0C8h+var_88]
0x18001ad95  mov     rax, [rcx]
0x18001ad98  mov     rax, [rax+258h]
0x18001ad9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ada4  test    eax, eax
0x18001ada6  jnz     loc_18001B072
0x18001adac  cmp     r12, 1
0x18001adb0  jb      loc_18001AFD0
0x18001adb6  mov     rcx, [rsp+0C8h+var_88]
0x18001adbb  mov     qword ptr [rsp+0C8h+Buf2], rcx
0x18001adc0  mov     r13d, 1
0x18001adc6  mov     rax, [rsp+0C8h+arg_10]
0x18001adce  test    byte ptr [rax], 4
0x18001add1  jz      short loc_18001AE1F
0x18001add3  mov     r13d, [rsp+0C8h+arg_18]
0x18001addb  lea     edx, [r13-1]; int
0x18001addf  lea     rcx, [rax+1]; this
0x18001ade3  call    ?ValidateSize@CCompressedString@@QEBAHH@Z; CCompressedString::ValidateSize(int)
0x18001ade8  movsxd  r15, eax
0x18001adeb  inc     r15
0x18001adee  mov     edx, r13d
0x18001adf1  sub     edx, r15d; int
0x18001adf4  mov     rcx, [rsp+0C8h+arg_10]
0x18001adfc  add     rcx, r15; this
0x18001adff  call    ?ValidateSize@CCompressedString@@QEBAHH@Z; CCompressedString::ValidateSize(int)
0x18001ae04  movsxd  r13, eax
0x18001ae07  add     r13, r15
0x18001ae0a  mov     r15, [rsp+0C8h+arg_8]
0x18001ae12  mov     rax, [rsp+0C8h+arg_10]
0x18001ae1a  mov     rcx, qword ptr [rsp+0C8h+Buf2]
0x18001ae1f  cmp     [rsp+0C8h+arg_18], 0
0x18001ae27  jl      loc_18001B058
0x18001ae2d  cmp     r12, r13
0x18001ae30  jb      loc_18001B03E
0x18001ae36  sub     r12, r13
0x18001ae39  lea     r8, [rcx+190h]; struct CClassPart *
0x18001ae40  lea     rcx, [rax+r13]; unsigned __int8 *
0x18001ae44  lea     r9, [rsp+0C8h+var_A8]
0x18001ae49  mov     rdx, r12; pExceptionObject
0x18001ae4c  call    ?ValidateBuffer@CInstancePart@@SA_KPEAE_KAEAVCClassPart@@AEAV?$vector@UEmbeddedObj@@V?$wbem_allocator@UEmbeddedObj@@@@@std@@@Z; CInstancePart::ValidateBuffer(uchar *,unsigned __int64,CClassPart &,std::vector<EmbeddedObj,wbem_allocator<EmbeddedObj>> &)
0x18001ae51  mov     r8, rax
0x18001ae54  mov     rdx, r13
0x18001ae57  lea     rcx, [rsp+0C8h+Buf2]
0x18001ae5c  call    ??$MixedSizeAddition@_K@?$SafeInt@_K@@CA?AV0@V0@_K@Z; SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(SafeInt<unsigned __int64>,unsigned __int64)
0x18001ae61  mov     rax, qword ptr [rsp+0C8h+var_A8+8]
0x18001ae66  cmp     qword ptr [rsp+0C8h+var_A8], rax
0x18001ae6b  jnz     loc_18001AF42
0x18001ae71  mov     eax, [rsp+0C8h+arg_18]
0x18001ae78  mov     [r15+0A8h], eax
0x18001ae7f  mov     rax, [rsp+0C8h+arg_10]
0x18001ae87  mov     [r15+48h], rax
0x18001ae8b  test    byte ptr [rax], 4
0x18001ae8e  jnz     loc_18001AF61
0x18001ae94  mov     [r15+50h], r14
0x18001ae98  mov     rcx, r14
0x18001ae9b  mov     [r15+58h], rcx
0x18001ae9f  mov     dword ptr [r15+3Ch], 3
0x18001aea7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aeae  lea     rax, WPP_GLOBAL_Control
0x18001aeb5  cmp     rcx, rax
0x18001aeb8  jz      short loc_18001AEC4
0x18001aeba  test    byte ptr [rcx+1Ch], 1
0x18001aebe  jnz     loc_18001B244
0x18001aec4  test    rdi, rdi
0x18001aec7  jz      short loc_18001AED8
0x18001aec9  mov     rax, [rdi]
0x18001aecc  mov     rcx, rdi
0x18001aecf  mov     rax, [rax+10h]
0x18001aed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aed8  mov     [rsp+0C8h+var_60], r14
0x18001aedd  test    rsi, rsi
0x18001aee0  jz      short loc_18001AEF1
0x18001aee2  mov     rax, [rsi]
0x18001aee5  mov     rcx, rsi
0x18001aee8  mov     rax, [rax+10h]
0x18001aeec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aef1  mov     [rsp+0C8h+var_68], r14
0x18001aef6  test    rbx, rbx
0x18001aef9  jz      short loc_18001AF0A
0x18001aefb  mov     rax, [rbx]
0x18001aefe  mov     rcx, rbx
0x18001af01  mov     rax, [rax+10h]
0x18001af05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af0a  mov     [rsp+0C8h+var_80], r14
0x18001af0f  mov     rcx, qword ptr [rsp+0C8h+var_A8]
0x18001af14  test    rcx, rcx
0x18001af17  jz      short loc_18001AF2D
0x18001af19  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001af1f  xorps   xmm0, xmm0
0x18001af22  movdqu  [rsp+0C8h+var_A8], xmm0
0x18001af28  mov     [rsp+0C8h+var_98], r14
0x18001af2d  xor     eax, eax
0x18001af2f  add     rsp, 90h
0x18001af36  pop     r15
0x18001af38  pop     r14
0x18001af3a  pop     r13
0x18001af3c  pop     r12
0x18001af3e  pop     rdi
0x18001af3f  pop     rsi
0x18001af40  pop     rbx
0x18001af41  retn
0x18001af42  add     rax, 0FFFFFFFFFFFFFFF0h
0x18001af46  mov     rcx, [rax]
0x18001af49  mov     rdx, [rax+8]
0x18001af4d  mov     qword ptr [rsp+0C8h+var_A8+8], rax
0x18001af52  lea     r8, [rsp+0C8h+var_A8]
0x18001af57  call    ?ValidateBuffer@CEmbeddedObject@@SAXPEAE_KAEAV?$vector@UEmbeddedObj@@V?$wbem_allocator@UEmbeddedObj@@@@@std@@@Z; CEmbeddedObject::ValidateBuffer(uchar *,unsigned __int64,std::vector<EmbeddedObj,wbem_allocator<EmbeddedObj>> &)
0x18001af5c  jmp     loc_18001AE61
0x18001af61  lea     r13, [rax+1]
0x18001af65  mov     [r15+50h], r13
0x18001af69  cmp     byte ptr [r13+0], 1
0x18001af6e  jz      short loc_18001AFB0
0x18001af70  mov     ecx, 1
0x18001af75  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001af7c  nop     dword ptr [rax+00h]
0x18001af80  inc     rax
0x18001af83  cmp     byte ptr [rax+r13+1], 0
0x18001af89  jnz     short loc_18001AF80
0x18001af8b  inc     eax
0x18001af8d  imul    eax, ecx
0x18001af90  inc     eax
0x18001af92  movsxd  rcx, eax
0x18001af95  add     rcx, r13
0x18001af98  jmp     loc_18001AE9B
0x18001af9d  mov     edi, 80041002h
0x18001afa2  jmp     loc_18001ACF3
0x18001afa7  mov     rdi, [rdi+10h]
0x18001afab  jmp     loc_18001ACB2
0x18001afb0  lea     rcx, [r13+1]; unsigned __int16 *
0x18001afb4  call    ?fast_wcslen@CCompressedString@@SAHPEBG@Z; CCompressedString::fast_wcslen(ushort const *)
0x18001afb9  mov     ecx, 2
0x18001afbe  inc     eax
0x18001afc0  imul    eax, ecx
0x18001afc3  inc     eax
0x18001afc5  movsxd  rcx, eax
0x18001afc8  add     rcx, r13
0x18001afcb  jmp     loc_18001AE9B
0x18001afd0  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18001afd7  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18001afdc  call    _CxxThrowException_0
0x18001afe2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001afe8  mov     edx, edi
0x18001afea  mov     rcx, rax
0x18001afed  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001aff3  jmp     loc_18001AD09
0x18001aff8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001affe  mov     edx, edi
0x18001b000  mov     rcx, rax
0x18001b003  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001b009  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b010  cmp     rcx, r13
0x18001b013  jnz     loc_18001B1A6
0x18001b019  mov     rcx, qword ptr [rsp+0C8h+var_A8]
0x18001b01e  test    rcx, rcx
0x18001b021  jz      short loc_18001B037
0x18001b023  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001b029  xorps   xmm0, xmm0
0x18001b02c  movdqu  [rsp+0C8h+var_A8], xmm0
0x18001b032  mov     [rsp+0C8h+var_98], r14
0x18001b037  mov     eax, edi
0x18001b039  jmp     loc_18001AF2F
0x18001b03e  mov     [rsp+0C8h+var_74], 216h
0x18001b046  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x18001b04d  lea     rcx, [rsp+0C8h+var_74]; pExceptionObject
0x18001b052  call    _CxxThrowException_0
0x18001b058  mov     [rsp+0C8h+var_78], 216h
0x18001b060  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x18001b067  lea     rcx, [rsp+0C8h+var_78]; pExceptionObject
0x18001b06c  call    _CxxThrowException_0
0x18001b072  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001b078  mov     edx, 8004100Fh
0x18001b07d  mov     rcx, rax
0x18001b080  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001b086  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b08d  cmp     rcx, r13
0x18001b090  jz      short loc_18001B0BA
0x18001b092  test    byte ptr [rcx+1Ch], 1
0x18001b096  jz      short loc_18001B0BA
0x18001b098  cmp     byte ptr [rcx+19h], 2
0x18001b09c  jb      short loc_18001B0BA
0x18001b09e  mov     edx, 26h ; '&'
0x18001b0a3  mov     r9d, 8004100Fh
0x18001b0a9  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x18001b0b0  mov     rcx, [rcx+10h]
0x18001b0b4  call    WPP_SF_d
0x18001b0b9  nop
0x18001b0ba  test    rdi, rdi
0x18001b0bd  jz      short loc_18001B0CE
0x18001b0bf  mov     rax, [rdi]
0x18001b0c2  mov     rcx, rdi
0x18001b0c5  mov     rax, [rax+10h]
0x18001b0c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0ce  mov     [rsp+0C8h+var_60], r14
0x18001b0d3  test    rsi, rsi
0x18001b0d6  jz      short loc_18001B0E7
0x18001b0d8  mov     rax, [rsi]
0x18001b0db  mov     rcx, rsi
0x18001b0de  mov     rax, [rax+10h]
0x18001b0e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0e7  mov     [rsp+0C8h+var_68], r14
0x18001b0ec  test    rbx, rbx
0x18001b0ef  jz      short loc_18001B100
0x18001b0f1  mov     rax, [rbx]
  ... truncated ...
```
