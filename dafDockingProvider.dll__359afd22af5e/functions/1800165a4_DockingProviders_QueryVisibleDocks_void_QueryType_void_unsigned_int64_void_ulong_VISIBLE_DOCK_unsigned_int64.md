# DockingProviders::QueryVisibleDocks(void *,_QueryType,void (*)(unsigned __int64,void *,ulong,_VISIBLE_DOCK *),unsigned __int64 *)

- ea: `0x1800165a4`
- end: `0x180016a28`
- name: `?QueryVisibleDocks@DockingProviders@@QEAAJPEAXW4_QueryType@@P6AX_K0KPEAU_VISIBLE_DOCK@@@ZPEA_K@Z`
- size: `1156`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, struct _RTL_CRITICAL_SECTION **)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18000c970`
- `0x180019260`

## callees

- `0x180001124`
- `0x1800014d0`
- `0x180001ef4`
- `0x180001f28`
- `0x18000c308`
- `0x18000c348`
- `0x18000d460`
- `0x1800165a4`
- `0x180017854`
- `0x18001ca70`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001664f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001664f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180016682`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180016682`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800169a5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800169e1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800169a5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800169e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001676f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800167d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001676f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800167d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016948`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016974`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016948`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016974`

## pseudocode

```c
__int64 __fastcall DockingProviders::QueryVisibleDocks(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        struct _RTL_CRITICAL_SECTION **a5)
{
  struct _RTL_CRITICAL_SECTION **v6; // r13
  struct _RTL_CRITICAL_SECTION *v7; // rax
  struct _RTL_CRITICAL_SECTION *v8; // rdi
  unsigned int v9; // ebx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rax
  int v13; // esi
  __int64 v14; // r15
  int v15; // r12d
  _QWORD *v16; // r10
  unsigned int v17; // r13d
  __int64 v18; // rax
  __int64 v19; // rbp
  __int64 v20; // rbx
  signed int v21; // eax
  __int64 v22; // r8
  signed int v23; // ebx
  __int64 v24; // rcx
  bool v25; // sf
  signed int v26; // eax
  __int64 v28; // [rsp+30h] [rbp-88h] BYREF
  __int64 v29; // [rsp+38h] [rbp-80h]
  __int64 v30; // [rsp+40h] [rbp-78h]
  struct _RTL_CRITICAL_SECTION **v31; // [rsp+48h] [rbp-70h]
  struct _RTL_CRITICAL_SECTION *v32; // [rsp+50h] [rbp-68h]
  __int64 v33; // [rsp+58h] [rbp-60h] BYREF
  char v34; // [rsp+60h] [rbp-58h]

  v30 = a4;
  LODWORD(v28) = a3;
  v29 = a2;
  v6 = a5;
  v31 = a5;
  if ( (unsigned int)dword_180026010 > 5
    && (qword_180026020 & 0x200000000000LL) != 0
    && (qword_180026028 & 0x200000000000LL) == qword_180026028 )
  {
    tlgWriteTransfer_EventWriteTransfer(&dword_180026010, byte_180021F8D, 0, 0, 2, &v33);
  }
  v33 = a1;
  AcquireSRWLockShared((PSRWLOCK)a1);
  v34 = 1;
  v7 = (struct _RTL_CRITICAL_SECTION *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  v32 = v7;
  if ( v7 )
  {
    v9 = *(_DWORD *)(a1 + 16);
    InitializeCriticalSection(v7);
    LODWORD(v8[1].DebugInfo) = 0;
    HIDWORD(v8[1].DebugInfo) = v9;
    LODWORD(v8[1].SpinCount) = 0;
    v10 = 8LL * v9;
    if ( !is_mul_ok(v9, 8u) )
      v10 = -1;
    *(_QWORD *)&v8[1].LockCount = operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
    v11 = 8LL * HIDWORD(v8[1].DebugInfo);
    if ( !is_mul_ok(HIDWORD(v8[1].DebugInfo), 8u) )
      v11 = -1;
    v8[1].OwningThread = operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
    v12 = 8LL * HIDWORD(v8[1].DebugInfo);
    if ( !is_mul_ok(HIDWORD(v8[1].DebugInfo), 8u) )
      v12 = -1;
    v8[1].LockSemaphore = operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
  }
  else
  {
    v8 = 0;
  }
  v32 = v8;
  if ( v8 && *(_QWORD *)&v8[1].LockCount && v8[1].OwningThread && v8[1].LockSemaphore )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, v8);
    }
    *a5 = 0;
    v13 = 0;
    v14 = 0;
    v15 = 0;
    EnterCriticalSection(v8);
    if ( *(_DWORD *)(a1 + 16) )
    {
      v16 = WPP_GLOBAL_Control;
      v17 = v28;
      while ( 1 )
      {
        v28 = 0;
        v18 = *(_QWORD *)(a1 + 24);
        v19 = *(_QWORD *)(v18 + 8 * v14);
        if ( !*(_QWORD *)(v19 + 104) )
          break;
        if ( v16 != &WPP_GLOBAL_Control && *((_BYTE *)v16 + 25) >= 4u && (*((_BYTE *)v16 + 28) & 1) != 0 )
          WPP_SF_qD(v16[2], 18, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, v19, v17);
        v21 = (*(__int64 (__fastcall **)(struct _RTL_CRITICAL_SECTION *, _QWORD, __int64 (__fastcall *)(char, LPCRITICAL_SECTION), __int64 *))(v19 + 104))(
                v8,
                v17,
                ScanAdapter,
                &v28);
        v23 = v21;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v24 = 0;
          if ( !v21 )
            v24 = v28;
          WPP_SF_qDq(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v22, v19, v21, v24);
          v16 = WPP_GLOBAL_Control;
        }
        v25 = v23 < 0;
        if ( v23 > 0 )
        {
          v23 = (unsigned __int16)v23 | 0x80070000;
          v25 = v23 < 0;
        }
        if ( !v25 )
          goto LABEL_29;
        v26 = v23;
        if ( v13 < 0 )
          v26 = v13;
        v13 = v26;
        if ( v16 == &WPP_GLOBAL_Control || !*((_BYTE *)v16 + 25) || (*((_BYTE *)v16 + 28) & 1) == 0 )
          goto LABEL_56;
        WPP_SF_qD(v16[2], 74, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, v8, v23);
LABEL_55:
        v16 = WPP_GLOBAL_Control;
LABEL_56:
        v14 = (unsigned int)(v14 + 1);
        if ( (unsigned int)v14 >= *(_DWORD *)(a1 + 16) )
        {
          v6 = v31;
          goto LABEL_58;
        }
      }
      if ( v16 != &WPP_GLOBAL_Control && *((_BYTE *)v16 + 25) && (*((_BYTE *)v16 + 28) & 1) != 0 )
        WPP_SF_q(v16[2], 17, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, *(_QWORD *)(v18 + 8 * v14));
LABEL_29:
      v20 = v28;
      EnterCriticalSection(v8);
      if ( LODWORD(v8[1].DebugInfo) >= HIDWORD(v8[1].DebugInfo) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25)
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            69,
            &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids,
            v8,
            HIDWORD(v8[1].DebugInfo));
        }
      }
      else
      {
        *(_QWORD *)(*(_QWORD *)&v8[1].LockCount + 8LL * LODWORD(v8[1].DebugInfo)) = v20;
        *((_QWORD *)v8[1].OwningThread + LODWORD(v8[1].DebugInfo)) = v29;
        *((_QWORD *)v8[1].LockSemaphore + (unsigned int)LODWORD(v8[1].DebugInfo)++) = v30;
      }
      LeaveCriticalSection(v8);
      ++v15;
      goto LABEL_55;
    }
LABEL_58:
    LeaveCriticalSection(v8);
    if ( v15 )
    {
      *v6 = v8;
      v13 = 0;
    }
    else
    {
      operator delete(*(void **)&v8[1].LockCount);
      operator delete(v8[1].OwningThread);
      operator delete(v8[1].LockSemaphore);
      DeleteCriticalSection(v8);
      operator delete(v8);
      if ( v13 >= 0 )
        v13 = -2147024637;
    }
  }
  else
  {
    if ( v8 )
    {
      operator delete(*(void **)&v8[1].LockCount);
      operator delete(v8[1].OwningThread);
      operator delete(v8[1].LockSemaphore);
      DeleteCriticalSection(v8);
      operator delete(v8);
    }
    v13 = -2147024882;
  }
  ReadLock::~ReadLock((ReadLock *)&v33);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800165a4  mov     [rsp+arg_8], rbx
0x1800165a9  push    rbp
0x1800165aa  push    rsi
0x1800165ab  push    rdi
0x1800165ac  push    r12
0x1800165ae  push    r13
0x1800165b0  push    r14
0x1800165b2  push    r15
0x1800165b4  sub     rsp, 80h
0x1800165bb  mov     rax, cs:__security_cookie
0x1800165c2  xor     rax, rsp
0x1800165c5  mov     [rsp+0B8h+var_40], rax
0x1800165ca  mov     [rsp+0B8h+var_78], r9
0x1800165cf  mov     dword ptr [rsp+0B8h+var_88], r8d
0x1800165d4  mov     [rsp+0B8h+var_80], rdx
0x1800165d9  mov     r14, rcx
0x1800165dc  mov     r13, [rsp+0B8h+arg_20]
0x1800165e4  mov     [rsp+0B8h+var_70], r13
0x1800165e9  mov     eax, cs:dword_180026010
0x1800165ef  cmp     eax, 5
0x1800165f2  jbe     short loc_180016647
0x1800165f4  mov     r10, cs:qword_180026028
0x1800165fb  mov     rax, cs:qword_180026020
0x180016602  mov     rcx, 200000000000h
0x18001660c  test    rcx, rax
0x18001660f  jz      short loc_180016647
0x180016611  mov     rax, r10
0x180016614  and     rax, rcx
0x180016617  cmp     rax, r10
0x18001661a  jnz     short loc_180016647
0x18001661c  lea     rax, [rsp+0B8h+var_60]
0x180016621  mov     [rsp+0B8h+var_90], rax
0x180016626  mov     [rsp+0B8h+var_98], 2
0x18001662e  xor     r9d, r9d
0x180016631  xor     r8d, r8d
0x180016634  lea     rdx, byte_180021F8D
0x18001663b  lea     rcx, dword_180026010
0x180016642  call    _tlgWriteTransfer_EventWriteTransfer
0x180016647  mov     [rsp+0B8h+var_60], r14
0x18001664c  mov     rcx, r14; SRWLock
0x18001664f  call    cs:__imp_AcquireSRWLockShared
0x180016655  mov     [rsp+0B8h+var_58], 1
0x18001665a  lea     rbp, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180016661  mov     rdx, rbp; struct std::nothrow_t *
0x180016664  mov     ecx, 50h ; 'P'; unsigned __int64
0x180016669  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001666e  mov     rdi, rax
0x180016671  mov     [rsp+0B8h+var_68], rax
0x180016676  test    rax, rax
0x180016679  jz      short loc_1800166F4
0x18001667b  mov     ebx, [r14+10h]
0x18001667f  mov     rcx, rax; lpCriticalSection
0x180016682  call    cs:__imp_InitializeCriticalSection
0x180016688  mov     dword ptr [rdi+28h], 0
0x18001668f  mov     [rdi+2Ch], ebx
0x180016692  mov     dword ptr [rdi+48h], 0
0x180016699  mov     ecx, ebx
0x18001669b  mov     ebx, 8
0x1800166a0  mov     eax, ebx
0x1800166a2  mul     rcx
0x1800166a5  lea     rsi, [rbx-9]
0x1800166a9  cmovb   rax, rsi
0x1800166ad  mov     rdx, rbp; struct std::nothrow_t *
0x1800166b0  mov     rcx, rax; unsigned __int64
0x1800166b3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800166b8  mov     [rdi+30h], rax
0x1800166bc  mov     ecx, [rdi+2Ch]
0x1800166bf  mov     eax, ebx
0x1800166c1  mul     rcx
0x1800166c4  cmovb   rax, rsi
0x1800166c8  mov     rdx, rbp; struct std::nothrow_t *
0x1800166cb  mov     rcx, rax; unsigned __int64
0x1800166ce  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800166d3  mov     [rdi+38h], rax
0x1800166d7  mov     ecx, [rdi+2Ch]
0x1800166da  mov     eax, ebx
0x1800166dc  mul     rcx
0x1800166df  cmovb   rax, rsi
0x1800166e3  mov     rdx, rbp; struct std::nothrow_t *
0x1800166e6  mov     rcx, rax; unsigned __int64
0x1800166e9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800166ee  mov     [rdi+40h], rax
0x1800166f2  jmp     short loc_1800166F6
0x1800166f4  xor     edi, edi
0x1800166f6  mov     [rsp+0B8h+var_68], rdi
0x1800166fb  test    rdi, rdi
0x1800166fe  jz      loc_1800169BE
0x180016704  cmp     qword ptr [rdi+30h], 0
0x180016709  jz      loc_1800169BE
0x18001670f  cmp     qword ptr [rdi+38h], 0
0x180016714  jz      loc_1800169BE
0x18001671a  cmp     qword ptr [rdi+40h], 0
0x18001671f  jz      loc_1800169BE
0x180016725  lea     rbx, WPP_GLOBAL_Control
0x18001672c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016733  cmp     rcx, rbx
0x180016736  jz      short loc_18001675C
0x180016738  cmp     byte ptr [rcx+19h], 3
0x18001673c  jb      short loc_18001675C
0x18001673e  test    byte ptr [rcx+1Ch], 1
0x180016742  jz      short loc_18001675C
0x180016744  mov     edx, 49h ; 'I'
0x180016749  mov     r9, rdi
0x18001674c  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x180016753  mov     rcx, [rcx+10h]
0x180016757  call    WPP_SF_q
0x18001675c  mov     qword ptr [r13+0], 0
0x180016764  xor     esi, esi
0x180016766  xor     r15d, r15d
0x180016769  xor     r12d, r12d
0x18001676c  mov     rcx, rdi; lpCriticalSection
0x18001676f  call    cs:__imp_EnterCriticalSection
0x180016775  cmp     [r14+10h], esi
0x180016779  jbe     loc_180016971
0x18001677f  mov     r10, cs:WPP_GLOBAL_Control
0x180016786  mov     r13d, dword ptr [rsp+0B8h+var_88]
0x18001678b  mov     [rsp+0B8h+var_88], 0
0x180016794  mov     rax, [r14+18h]
0x180016798  mov     rbp, [rax+r15*8]
0x18001679c  cmp     qword ptr [rbp+68h], 0
0x1800167a1  jnz     short loc_18001681B
0x1800167a3  cmp     r10, rbx
0x1800167a6  jz      short loc_1800167CE
0x1800167a8  cmp     byte ptr [r10+19h], 1
0x1800167ad  jb      short loc_1800167CE
0x1800167af  test    byte ptr [r10+1Ch], 1
0x1800167b4  jz      short loc_1800167CE
0x1800167b6  mov     edx, 11h
0x1800167bb  mov     r9, rbp
0x1800167be  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x1800167c5  mov     rcx, [r10+10h]
0x1800167c9  call    WPP_SF_q
0x1800167ce  mov     rbx, [rsp+0B8h+var_88]
0x1800167d3  mov     rcx, rdi; lpCriticalSection
0x1800167d6  call    cs:__imp_EnterCriticalSection
0x1800167dc  mov     eax, [rdi+2Ch]
0x1800167df  cmp     [rdi+28h], eax
0x1800167e2  jnb     loc_18001690A
0x1800167e8  mov     ecx, [rdi+28h]
0x1800167eb  mov     rax, [rdi+30h]
0x1800167ef  mov     [rax+rcx*8], rbx
0x1800167f3  mov     ecx, [rdi+28h]
0x1800167f6  mov     rax, [rdi+38h]
0x1800167fa  mov     rdx, [rsp+0B8h+var_80]
0x1800167ff  mov     [rax+rcx*8], rdx
0x180016803  mov     ecx, [rdi+28h]
0x180016806  mov     rax, [rdi+40h]
0x18001680a  mov     rdx, [rsp+0B8h+var_78]
0x18001680f  mov     [rax+rcx*8], rdx
0x180016813  inc     dword ptr [rdi+28h]
0x180016816  jmp     loc_180016945
0x18001681b  cmp     r10, rbx
0x18001681e  jz      short loc_18001684B
0x180016820  cmp     byte ptr [r10+19h], 4
0x180016825  jb      short loc_18001684B
0x180016827  test    byte ptr [r10+1Ch], 1
0x18001682c  jz      short loc_18001684B
0x18001682e  mov     edx, 12h
0x180016833  mov     [rsp+0B8h+var_98], r13d
0x180016838  mov     r9, rbp
0x18001683b  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x180016842  mov     rcx, [r10+10h]
0x180016846  call    WPP_SF_qD
0x18001684b  lea     r9, [rsp+0B8h+var_88]
0x180016850  lea     r8, ScanAdapter
0x180016857  mov     edx, r13d
0x18001685a  mov     rcx, rdi
0x18001685d  mov     rax, [rbp+68h]
0x180016861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016866  mov     ebx, eax
0x180016868  mov     r10, cs:WPP_GLOBAL_Control
0x18001686f  lea     rcx, WPP_GLOBAL_Control
0x180016876  cmp     r10, rcx
0x180016879  jz      short loc_1800168BB
0x18001687b  cmp     byte ptr [r10+19h], 4
0x180016880  jb      short loc_1800168BB
0x180016882  test    byte ptr [r10+1Ch], 1
0x180016887  jz      short loc_1800168BB
0x180016889  xor     ecx, ecx
0x18001688b  test    eax, eax
0x18001688d  cmovz   rcx, [rsp+0B8h+var_88]
0x180016893  mov     edx, 13h
0x180016898  mov     [rsp+0B8h+var_90], rcx
0x18001689d  mov     [rsp+0B8h+var_98], eax
0x1800168a1  mov     r9, rbp
0x1800168a4  mov     rcx, [r10+10h]
0x1800168a8  call    WPP_SF_qDq
0x1800168ad  mov     r10, cs:WPP_GLOBAL_Control
0x1800168b4  lea     rcx, WPP_GLOBAL_Control
0x1800168bb  test    ebx, ebx
0x1800168bd  jle     short loc_1800168CA
0x1800168bf  movzx   ebx, bx
0x1800168c2  or      ebx, 80070000h
0x1800168c8  test    ebx, ebx
0x1800168ca  jns     loc_1800167CE
0x1800168d0  mov     eax, ebx
0x1800168d2  test    esi, esi
0x1800168d4  cmovs   eax, esi
0x1800168d7  mov     esi, eax
0x1800168d9  cmp     r10, rcx
0x1800168dc  jz      short loc_180016958
0x1800168de  cmp     byte ptr [r10+19h], 1
0x1800168e3  jb      short loc_180016958
0x1800168e5  test    byte ptr [r10+1Ch], 1
0x1800168ea  jz      short loc_180016958
0x1800168ec  mov     edx, 4Ah ; 'J'
0x1800168f1  mov     [rsp+0B8h+var_98], ebx
0x1800168f5  mov     r9, rdi
0x1800168f8  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x1800168ff  mov     rcx, [r10+10h]
0x180016903  call    WPP_SF_qD
0x180016908  jmp     short loc_180016951
0x18001690a  mov     rcx, cs:WPP_GLOBAL_Control
0x180016911  lea     rdx, WPP_GLOBAL_Control
0x180016918  cmp     rcx, rdx
0x18001691b  jz      short loc_180016945
0x18001691d  cmp     byte ptr [rcx+19h], 1
0x180016921  jb      short loc_180016945
0x180016923  test    byte ptr [rcx+1Ch], 1
0x180016927  jz      short loc_180016945
0x180016929  mov     edx, 45h ; 'E'
0x18001692e  mov     [rsp+0B8h+var_98], eax
0x180016932  mov     r9, rdi
0x180016935  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x18001693c  mov     rcx, [rcx+10h]
0x180016940  call    WPP_SF_qD
0x180016945  mov     rcx, rdi; lpCriticalSection
0x180016948  call    cs:__imp_LeaveCriticalSection
0x18001694e  inc     r12d
0x180016951  mov     r10, cs:WPP_GLOBAL_Control
0x180016958  inc     r15d
0x18001695b  cmp     r15d, [r14+10h]
0x18001695f  lea     rbx, WPP_GLOBAL_Control
0x180016966  jb      loc_18001678B
0x18001696c  mov     r13, [rsp+0B8h+var_70]
0x180016971  mov     rcx, rdi; lpCriticalSection
0x180016974  call    cs:__imp_LeaveCriticalSection
0x18001697a  test    r12d, r12d
0x18001697d  jz      short loc_180016987
0x18001697f  mov     [r13+0], rdi
0x180016983  xor     esi, esi
0x180016985  jmp     short loc_1800169F4
0x180016987  mov     rcx, [rdi+30h]; Block
0x18001698b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016990  mov     rcx, [rdi+38h]; Block
0x180016994  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016999  mov     rcx, [rdi+40h]; Block
0x18001699d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800169a2  mov     rcx, rdi; lpCriticalSection
0x1800169a5  call    cs:__imp_DeleteCriticalSection
0x1800169ab  mov     rcx, rdi; Block
0x1800169ae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800169b3  test    esi, esi
0x1800169b5  js      short loc_1800169F4
0x1800169b7  mov     esi, 80070103h
0x1800169bc  jmp     short loc_1800169F4
0x1800169be  test    rdi, rdi
0x1800169c1  jz      short loc_1800169EF
0x1800169c3  mov     rcx, [rdi+30h]; Block
0x1800169c7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800169cc  mov     rcx, [rdi+38h]; Block
0x1800169d0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800169d5  mov     rcx, [rdi+40h]; Block
0x1800169d9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800169de  mov     rcx, rdi; lpCriticalSection
0x1800169e1  call    cs:__imp_DeleteCriticalSection
0x1800169e7  mov     rcx, rdi; Block
0x1800169ea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800169ef  mov     esi, 8007000Eh
0x1800169f4  lea     rcx, [rsp+0B8h+var_60]; this
0x1800169f9  call    ??1ReadLock@@QEAA@XZ; ReadLock::~ReadLock(void)
0x1800169fe  mov     eax, esi
0x180016a00  mov     rcx, [rsp+0B8h+var_40]
0x180016a05  xor     rcx, rsp; StackCookie
0x180016a08  call    __security_check_cookie
0x180016a0d  mov     rbx, [rsp+0B8h+arg_8]
0x180016a15  add     rsp, 80h
0x180016a1c  pop     r15
0x180016a1e  pop     r14
0x180016a20  pop     r13
0x180016a22  pop     r12
0x180016a24  pop     rdi
0x180016a25  pop     rsi
0x180016a26  pop     rbp
0x180016a27  retn
```
