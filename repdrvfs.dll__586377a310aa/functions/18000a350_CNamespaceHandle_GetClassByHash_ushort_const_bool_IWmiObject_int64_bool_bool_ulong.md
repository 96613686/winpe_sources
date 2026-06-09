# CNamespaceHandle::GetClassByHash(ushort const *,bool,_IWmiObject * *,__int64 *,bool *,bool *,ulong)

- ea: `0x18000a350`
- end: `0x18000a9a4`
- name: `?GetClassByHash@CNamespaceHandle@@IEAAJPEBG_NPEAPEAU_IWmiObject@@PEA_JPEA_N4K@Z`
- size: `1620`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, char *, char, struct _IWmiObject **, __int64 *, bool *, bool *, unsigned int)`
- caller_count: `7`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180009b80`
- `0x18000a9b0`
- `0x18000b260`
- `0x1800178e0`
- `0x180021adc`
- `0x180032f08`
- `0x180035908`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18000a350`
- `0x180013f90`
- `0x1800178e0`
- `0x180048010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a437`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a4b5`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a437`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a4b5`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000a593`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000a59d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000a78d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000a797`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000a8c3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000a925`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000a92f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000a98c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000a996`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000a593`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000a59d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000a78d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000a797`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000a8c3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000a925`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000a92f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000a98c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000a996`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18000a39d`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18000a63a`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18000a65e`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18000a39d`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18000a63a`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18000a65e`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000a405`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000a6f4`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000a726`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000a756`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000a764`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000a7e5`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000a7f8`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000a405`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000a6f4`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000a726`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000a756`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000a764`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000a7e5`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000a7f8`
- `wbemcomn!GetMemLogObject` at `0x18000a872`
- `wbemcomn!GetMemLogObject` at `0x18000a8d4`
- `wbemcomn!GetMemLogObject` at `0x18000a940`
- `wbemcomn!GetMemLogObject` at `0x18000a872`
- `wbemcomn!GetMemLogObject` at `0x18000a8d4`
- `wbemcomn!GetMemLogObject` at `0x18000a940`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000a880`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000a8e2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000a94b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000a880`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000a8e2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000a94b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a6c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a6c9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000a85e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000a85e`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::GetClassByHash(
        CNamespaceHandle *this,
        char *a2,
        char a3,
        struct _IWmiObject **a4,
        __int64 *a5,
        bool *a6,
        bool *a7,
        unsigned int a8)
{
  __int64 v11; // rdi
  __int64 *v12; // r10
  __int64 *v13; // r9
  __int64 *v14; // rbx
  __int64 v15; // rax
  char *v16; // r8
  int v17; // ecx
  int v18; // edx
  bool *v19; // rbp
  bool *v20; // r14
  __int64 *v21; // r15
  unsigned __int16 *v22; // rax
  unsigned __int16 *v23; // rbx
  __int64 v24; // rax
  const unsigned __int16 *v25; // r8
  __int64 v26; // r9
  unsigned __int16 *v27; // rdx
  unsigned __int16 v28; // cx
  unsigned __int16 *v29; // rax
  unsigned __int16 *v30; // rax
  unsigned __int16 *v31; // rdi
  unsigned __int16 *v32; // rdx
  unsigned __int16 *v33; // r8
  unsigned int i; // ecx
  unsigned __int16 v35; // ax
  unsigned int v36; // ecx
  unsigned __int16 *v37; // rdx
  unsigned __int16 *v38; // r8
  unsigned __int16 v39; // ax
  int v40; // eax
  unsigned int v41; // esi
  const unsigned __int16 *v42; // rax
  int v43; // ecx
  int v44; // edx
  __int64 v45; // rbx
  __int64 v46; // rdi
  __int64 v47; // rcx
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rcx
  struct _IWmiObject *v53; // rbx
  CMemoryLog *v55; // rax
  CMemoryLog *v56; // rax
  CMemoryLog *MemLogObject; // rax
  struct _IWmiObject *v58; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v59[80]; // [rsp+48h] [rbp-50h] BYREF
  unsigned __int16 *v61; // [rsp+A8h] [rbp+10h] BYREF
  char v62; // [rsp+B0h] [rbp+18h]
  unsigned __int16 *v63; // [rsp+B8h] [rbp+20h] BYREF

  v62 = a3;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  v11 = *((_QWORD *)this + 11);
  CInCritSec::CInCritSec((CInCritSec *)v59, *(struct _RTL_CRITICAL_SECTION **)(v11 + 16));
  v12 = *(__int64 **)(v11 + 24);
  v13 = (__int64 *)v12[1];
  v14 = v12;
  if ( *((_BYTE *)v13 + 25) )
    goto LABEL_11;
  do
  {
    v15 = v13[4];
    v16 = &a2[-v15];
    do
    {
      v17 = *(unsigned __int16 *)&v16[v15];
      v18 = *(unsigned __int16 *)v15 - v17;
      if ( v18 )
        break;
      v15 += 2;
    }
    while ( v17 );
    if ( v18 >= 0 )
    {
      v14 = v13;
      v13 = (__int64 *)*v13;
    }
    else
    {
      v13 = (__int64 *)v13[2];
    }
  }
  while ( !*((_BYTE *)v13 + 25) );
  if ( v14 == v12 )
    goto LABEL_11;
  v42 = (const unsigned __int16 *)a2;
  do
  {
    v43 = *(const unsigned __int16 *)((char *)v42 + v14[4] - (_QWORD)a2);
    v44 = *v42 - v43;
    if ( v44 )
      break;
    ++v42;
  }
  while ( v43 );
  if ( v44 < 0 || (v45 = v14[5]) == 0 )
  {
LABEL_11:
    CInCritSec::~CInCritSec((CInCritSec *)v59);
    *a4 = 0;
    v19 = a7;
    v20 = a6;
    v21 = a5;
    goto LABEL_12;
  }
  v20 = a6;
  if ( a6 )
    *a6 = *(_BYTE *)(v45 + 336);
  v21 = a5;
  if ( a5 )
    *a5 = *(_QWORD *)(v45 + 328);
  v19 = a7;
  if ( a7 )
    *a7 = *(_BYTE *)(v45 + 337);
  CInCritSec::CInCritSec((CInCritSec *)&v61, *(struct _RTL_CRITICAL_SECTION **)(v11 + 16));
  if ( !*(_QWORD *)(v45 + 176) )
    goto LABEL_64;
  v46 = *(_QWORD *)(v11 + 16);
  CInCritSec::CInCritSec((CInCritSec *)&v63, (struct _RTL_CRITICAL_SECTION *)v46);
  v47 = *(_QWORD *)(v45 + 24);
  v48 = *(_QWORD *)(v45 + 16);
  if ( v47 )
    *(_QWORD *)(v47 + 16) = v48;
  if ( v48 )
    *(_QWORD *)(v48 + 24) = v47;
  v49 = *(_QWORD *)(v46 + 56);
  if ( v49 == v45 )
    *(_QWORD *)(v46 + 56) = *(_QWORD *)(v49 + 16);
  v50 = *(_QWORD *)(v46 + 48);
  if ( v50 == v45 )
    *(_QWORD *)(v46 + 48) = *(_QWORD *)(v50 + 24);
  *(_QWORD *)(v45 + 24) = 0;
  *(_QWORD *)(v45 + 16) = 0;
  *(_QWORD *)(v45 + 24) = *(_QWORD *)(v46 + 48);
  v51 = *(_QWORD *)(v46 + 48);
  if ( v51 )
    *(_QWORD *)(v51 + 16) = v45;
  *(_QWORD *)(v46 + 48) = v45;
  if ( !*(_QWORD *)(v46 + 56) )
    *(_QWORD *)(v46 + 56) = v45;
  *(_DWORD *)(v45 + 320) = GetTickCount();
  *(_DWORD *)(v45 + 324) = 4;
  if ( !*(_QWORD *)(v46 + 80) )
    CreateTimerQueueTimer(
      (PHANDLE)(v46 + 80),
      0,
      CForestCache::staticTimerCallback,
      (PVOID)v46,
      *(_DWORD *)(v46 + 68),
      *(_DWORD *)(v46 + 68),
      0x20u);
  CInCritSec::~CInCritSec((CInCritSec *)&v63);
  v52 = *(_QWORD *)(v45 + 176);
  if ( !v62 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 8LL))(v52);
    v53 = *(struct _IWmiObject **)(v45 + 176);
    CInCritSec::~CInCritSec((CInCritSec *)&v61);
    goto LABEL_65;
  }
  v63 = 0;
  if ( (*(int (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v52 + 96LL))(v52, &v63) >= 0 )
  {
    v58 = 0;
    (**(void (__fastcall ***)(unsigned __int16 *, GUID *, struct _IWmiObject **))v63)(v63, &IID__IWmiObject, &v58);
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v63 + 16LL))(v63);
    v53 = v58;
    CInCritSec::~CInCritSec((CInCritSec *)&v61);
  }
  else
  {
LABEL_64:
    CInCritSec::~CInCritSec((CInCritSec *)&v61);
    v53 = 0;
  }
LABEL_65:
  CInCritSec::~CInCritSec((CInCritSec *)v59);
  *a4 = v53;
  if ( v53 )
    return 0;
LABEL_12:
  if ( v20 )
    *v20 = 1;
  v22 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x2E6u);
  v23 = v22;
  v61 = v22;
  if ( v22 )
  {
    *v22 = 0;
    v24 = 2147483646;
    v25 = L"CD_";
    v26 = 371;
    v27 = v23;
    do
    {
      if ( !v24 )
        break;
      v28 = *v25;
      if ( !*v25 )
        break;
      ++v25;
      *v27++ = v28;
      --v24;
      --v26;
    }
    while ( v26 );
    v29 = v27 - 1;
    if ( v26 )
      v29 = v27;
    *v29 = 0;
    StringCchCatW(v23, 0x173u, (const unsigned __int16 *)a2);
    v30 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x2E6u);
    v31 = v30;
    v63 = v30;
    if ( v30 )
    {
      *v30 = 0;
      v32 = (unsigned __int16 *)*((_QWORD *)this + 7);
      v33 = v30;
      for ( i = 0; *v32; ++i )
      {
        if ( i >= 0x172 )
          break;
        v35 = *v32++;
        *v33++ = v35;
      }
      *v33 = 92;
      v36 = i + 1;
      v37 = v33 + 1;
      if ( v36 >= 0x173 )
        v37 = v33;
      if ( *v23 )
      {
        v38 = v23;
        do
        {
          if ( v36 >= 0x172 )
            break;
          v39 = *v38++;
          *v37++ = v39;
          ++v36;
        }
        while ( *v38 );
      }
      *v37 = 0;
      v40 = CNamespaceHandle::FileToClass((struct _RTL_CRITICAL_SECTION ***)this, v31, a4, v62, v21, v19, a8);
      v41 = v40;
      if ( v40 >= 0 )
      {
        CWin32DefaultArena::WbemMemFree(v31);
        CWin32DefaultArena::WbemMemFree(v23);
        return 0;
      }
      if ( v40 != -2147217406 )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, v41);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, v41);
        }
      }
      CWin32DefaultArena::WbemMemFree(v31);
      CWin32DefaultArena::WbemMemFree(v23);
      return v41;
    }
    else
    {
      v56 = GetMemLogObject();
      CMemoryLog::Write(v56, -2147217402);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          146,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          2147749894LL);
      }
      CWin32DefaultArena::WbemMemFree(0);
      CWin32DefaultArena::WbemMemFree(v23);
      return 2147749894LL;
    }
  }
  else
  {
    v55 = GetMemLogObject();
    CMemoryLog::Write(v55, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    CWin32DefaultArena::WbemMemFree(0);
    return 2147749894LL;
  }
}

```

## disassembly

```asm
0x18000a350  mov     [rsp+arg_10], r8b
0x18000a355  mov     [rsp+arg_0], rcx
0x18000a35a  push    rbx
0x18000a35b  push    rbp
0x18000a35c  push    rsi
0x18000a35d  push    rdi
0x18000a35e  push    r12
0x18000a360  push    r13
0x18000a362  push    r14
0x18000a364  push    r15
0x18000a366  sub     rsp, 58h
0x18000a36a  mov     r13, r9
0x18000a36d  mov     r12, rdx
0x18000a370  mov     rbx, rcx
0x18000a373  lea     rax, WPP_GLOBAL_Control
0x18000a37a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a381  cmp     rcx, rax
0x18000a384  jz      short loc_18000A390
0x18000a386  test    byte ptr [rcx+1Ch], 1
0x18000a38a  jnz     loc_18000A805
0x18000a390  mov     rdi, [rbx+58h]
0x18000a394  mov     rdx, [rdi+10h]
0x18000a398  lea     rcx, [rsp+98h+var_50]
0x18000a39d  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18000a3a3  nop
0x18000a3a4  mov     r10, [rdi+18h]
0x18000a3a8  mov     r9, [r10+8]
0x18000a3ac  mov     rbx, r10
0x18000a3af  cmp     byte ptr [r9+19h], 0
0x18000a3b4  jnz     short loc_18000A400
0x18000a3b6  nop     word ptr [rax+rax+00000000h]
0x18000a3c0  mov     rax, [r9+20h]
0x18000a3c4  mov     r8, r12
0x18000a3c7  sub     r8, rax
0x18000a3ca  nop     word ptr [rax+rax+00h]
0x18000a3d0  movzx   edx, word ptr [rax]
0x18000a3d3  movzx   ecx, word ptr [rax+r8]
0x18000a3d8  sub     edx, ecx
0x18000a3da  jnz     short loc_18000A3E4
0x18000a3dc  add     rax, 2
0x18000a3e0  test    ecx, ecx
0x18000a3e2  jnz     short loc_18000A3D0
0x18000a3e4  test    edx, edx
0x18000a3e6  jns     loc_18000A5AB
0x18000a3ec  mov     r9, [r9+10h]
0x18000a3f0  cmp     byte ptr [r9+19h], 0
0x18000a3f5  jz      short loc_18000A3C0
0x18000a3f7  cmp     rbx, r10
0x18000a3fa  jnz     loc_18000A5B6
0x18000a400  lea     rcx, [rsp+98h+var_50]
0x18000a405  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18000a40b  xor     esi, esi
0x18000a40d  mov     [r13+0], rsi
0x18000a411  mov     rbp, [rsp+98h+arg_30]
0x18000a419  mov     r14, [rsp+98h+arg_28]
0x18000a421  mov     r15, [rsp+98h+arg_20]
0x18000a429  test    r14, r14
0x18000a42c  jnz     loc_18000A869
0x18000a432  mov     ecx, 2E6h
0x18000a437  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000a43d  mov     rbx, rax
0x18000a440  mov     [rsp+98h+arg_8], rax
0x18000a448  test    rax, rax
0x18000a44b  jz      short loc_18000A450
0x18000a44d  mov     [rax], si
0x18000a450  test    rbx, rbx
0x18000a453  jz      loc_18000A872
0x18000a459  mov     eax, 7FFFFFFEh
0x18000a45e  lea     r8, aCd_0; "CD_"
0x18000a465  mov     r9d, 173h
0x18000a46b  mov     rdx, rbx
0x18000a46e  xchg    ax, ax
0x18000a470  test    rax, rax
0x18000a473  jz      short loc_18000A492
0x18000a475  movzx   ecx, word ptr [r8]
0x18000a479  test    cx, cx
0x18000a47c  jz      short loc_18000A492
0x18000a47e  add     r8, 2
0x18000a482  mov     [rdx], cx
0x18000a485  add     rdx, 2
0x18000a489  dec     rax
0x18000a48c  sub     r9, 1
0x18000a490  jnz     short loc_18000A470
0x18000a492  lea     rax, [rdx-2]
0x18000a496  test    r9, r9
0x18000a499  cmovnz  rax, rdx
0x18000a49d  mov     [rax], si
0x18000a4a0  mov     r8, r12; unsigned __int16 *
0x18000a4a3  mov     edx, 173h; unsigned __int64
0x18000a4a8  mov     rcx, rbx; unsigned __int16 *
0x18000a4ab  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a4b0  mov     ecx, 2E6h
0x18000a4b5  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000a4bb  mov     rdi, rax
0x18000a4be  mov     [rsp+98h+arg_18], rax
0x18000a4c6  test    rax, rax
0x18000a4c9  jz      short loc_18000A4CE
0x18000a4cb  mov     [rax], si
0x18000a4ce  test    rdi, rdi
0x18000a4d1  jz      loc_18000A8D4
0x18000a4d7  mov     r10, [rsp+98h+arg_0]
0x18000a4df  mov     rdx, [r10+38h]
0x18000a4e3  mov     r8, rdi
0x18000a4e6  mov     ecx, esi
0x18000a4e8  cmp     word ptr [rdx], 0
0x18000a4ec  jz      short loc_18000A50D
0x18000a4ee  cmp     ecx, 172h
0x18000a4f4  jnb     short loc_18000A50D
0x18000a4f6  movzx   eax, word ptr [rdx]
0x18000a4f9  add     rdx, 2
0x18000a4fd  mov     [r8], ax
0x18000a501  add     r8, 2
0x18000a505  inc     ecx
0x18000a507  cmp     word ptr [rdx], 0
0x18000a50b  jnz     short loc_18000A4EE
0x18000a50d  mov     word ptr [r8], 5Ch ; '\'
0x18000a513  inc     ecx
0x18000a515  lea     rdx, [r8+2]
0x18000a519  cmp     ecx, 173h
0x18000a51f  cmovnb  rdx, r8
0x18000a523  cmp     word ptr [rbx], 0
0x18000a527  jz      short loc_18000A54C
0x18000a529  mov     r8, rbx
0x18000a52c  cmp     ecx, 172h
0x18000a532  jnb     short loc_18000A54C
0x18000a534  movzx   eax, word ptr [r8]
0x18000a538  add     r8, 2
0x18000a53c  mov     [rdx], ax
0x18000a53f  add     rdx, 2
0x18000a543  inc     ecx
0x18000a545  cmp     word ptr [r8], 0
0x18000a54a  jnz     short loc_18000A52C
0x18000a54c  mov     [rdx], si
0x18000a54f  mov     eax, [rsp+98h+arg_38]
0x18000a556  mov     [rsp+98h+Flags], eax; unsigned int
0x18000a55a  mov     qword ptr [rsp+98h+Period], rbp; bool *
0x18000a55f  mov     qword ptr [rsp+98h+DueTime], r15; __int64 *
0x18000a564  movzx   r9d, [rsp+98h+arg_10]; bool
0x18000a56d  mov     r8, r13; struct _IWmiObject **
0x18000a570  mov     rdx, rdi; unsigned __int16 *
0x18000a573  mov     rcx, r10; this
0x18000a576  call    ?FileToClass@CNamespaceHandle@@IEAAJPEBGPEAPEAU_IWmiObject@@_NPEA_JPEA_NK@Z; CNamespaceHandle::FileToClass(ushort const *,_IWmiObject * *,bool,__int64 *,bool *,ulong)
0x18000a57b  mov     esi, eax
0x18000a57d  test    eax, eax
0x18000a57f  jns     loc_18000A78A
0x18000a585  cmp     eax, 80041002h
0x18000a58a  jnz     loc_18000A940
0x18000a590  mov     rcx, rdi
0x18000a593  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000a599  nop
0x18000a59a  mov     rcx, rbx
0x18000a59d  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000a5a3  nop
0x18000a5a4  mov     eax, esi
0x18000a5a6  jmp     loc_18000A779
0x18000a5ab  mov     rbx, r9
0x18000a5ae  mov     r9, [r9]
0x18000a5b1  jmp     loc_18000A3F0
0x18000a5b6  mov     rax, r12
0x18000a5b9  mov     r8, [rbx+20h]
0x18000a5bd  sub     r8, r12
0x18000a5c0  movzx   edx, word ptr [rax]
0x18000a5c3  movzx   ecx, word ptr [rax+r8]
0x18000a5c8  sub     edx, ecx
0x18000a5ca  jnz     short loc_18000A5D4
0x18000a5cc  add     rax, 2
0x18000a5d0  test    ecx, ecx
0x18000a5d2  jnz     short loc_18000A5C0
0x18000a5d4  test    edx, edx
0x18000a5d6  js      loc_18000A400
0x18000a5dc  mov     rbx, [rbx+28h]
0x18000a5e0  test    rbx, rbx
0x18000a5e3  jz      loc_18000A400
0x18000a5e9  mov     r14, [rsp+98h+arg_28]
0x18000a5f1  test    r14, r14
0x18000a5f4  jz      short loc_18000A600
0x18000a5f6  movzx   eax, byte ptr [rbx+150h]
0x18000a5fd  mov     [r14], al
0x18000a600  mov     r15, [rsp+98h+arg_20]
0x18000a608  test    r15, r15
0x18000a60b  jz      short loc_18000A617
0x18000a60d  mov     rax, [rbx+148h]
0x18000a614  mov     [r15], rax
0x18000a617  mov     rbp, [rsp+98h+arg_30]
0x18000a61f  test    rbp, rbp
0x18000a622  jz      short loc_18000A62E
0x18000a624  movzx   eax, byte ptr [rbx+151h]
0x18000a62b  mov     [rbp+0], al
0x18000a62e  mov     rdx, [rdi+10h]
0x18000a632  lea     rcx, [rsp+98h+arg_8]
0x18000a63a  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18000a640  nop
0x18000a641  cmp     qword ptr [rbx+0B0h], 0
0x18000a649  jz      loc_18000A7F0
0x18000a64f  mov     rdi, [rdi+10h]
0x18000a653  mov     rdx, rdi
0x18000a656  lea     rcx, [rsp+98h+arg_18]
0x18000a65e  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18000a664  mov     rcx, [rbx+18h]
0x18000a668  mov     rax, [rbx+10h]
0x18000a66c  test    rcx, rcx
0x18000a66f  jz      short loc_18000A675
0x18000a671  mov     [rcx+10h], rax
0x18000a675  test    rax, rax
0x18000a678  jz      short loc_18000A67E
0x18000a67a  mov     [rax+18h], rcx
0x18000a67e  mov     rax, [rdi+38h]
0x18000a682  cmp     rax, rbx
0x18000a685  jz      loc_18000A829
0x18000a68b  mov     rax, [rdi+30h]
0x18000a68f  cmp     rax, rbx
0x18000a692  jnz     short loc_18000A69C
0x18000a694  mov     rax, [rax+18h]
0x18000a698  mov     [rdi+30h], rax
0x18000a69c  xor     esi, esi
0x18000a69e  mov     [rbx+18h], rsi
0x18000a6a2  mov     [rbx+10h], rsi
0x18000a6a6  mov     rax, [rdi+30h]
0x18000a6aa  mov     [rbx+18h], rax
0x18000a6ae  mov     rax, [rdi+30h]
0x18000a6b2  test    rax, rax
0x18000a6b5  jz      short loc_18000A6BB
0x18000a6b7  mov     [rax+10h], rbx
0x18000a6bb  mov     [rdi+30h], rbx
0x18000a6bf  cmp     [rdi+38h], rsi
0x18000a6c3  jz      loc_18000A836
0x18000a6c9  call    cs:__imp_GetTickCount
0x18000a6cf  mov     [rbx+140h], eax
0x18000a6d5  mov     dword ptr [rbx+144h], 4
0x18000a6df  lea     rcx, [rdi+50h]; phNewTimer
0x18000a6e3  cmp     [rcx], rsi
0x18000a6e6  jz      loc_18000A83F
0x18000a6ec  lea     rcx, [rsp+98h+arg_18]
0x18000a6f4  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18000a6fa  mov     rcx, [rbx+0B0h]
0x18000a701  cmp     [rsp+98h+arg_10], sil
0x18000a709  jnz     short loc_18000A72E
0x18000a70b  mov     rax, [rcx]
0x18000a70e  mov     rax, [rax+8]
0x18000a712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a717  mov     rbx, [rbx+0B0h]
0x18000a71e  lea     rcx, [rsp+98h+arg_8]
0x18000a726  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18000a72c  jmp     short loc_18000A75F
0x18000a72e  mov     [rsp+98h+arg_18], rsi
0x18000a736  mov     rax, [rcx]
0x18000a739  lea     rdx, [rsp+98h+arg_18]
0x18000a741  mov     rax, [rax+60h]
0x18000a745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a74a  test    eax, eax
0x18000a74c  jns     short loc_18000A7A0
0x18000a74e  lea     rcx, [rsp+98h+arg_8]
0x18000a756  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18000a75c  mov     rbx, rsi
0x18000a75f  lea     rcx, [rsp+98h+var_50]
0x18000a764  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18000a76a  mov     [r13+0], rbx
0x18000a76e  test    rbx, rbx
0x18000a771  jz      loc_18000A429
0x18000a777  xor     eax, eax
0x18000a779  add     rsp, 58h
0x18000a77d  pop     r15
0x18000a77f  pop     r14
0x18000a781  pop     r13
0x18000a783  pop     r12
0x18000a785  pop     rdi
0x18000a786  pop     rsi
0x18000a787  pop     rbp
0x18000a788  pop     rbx
0x18000a789  retn
0x18000a78a  mov     rcx, rdi
0x18000a78d  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000a793  nop
0x18000a794  mov     rcx, rbx
0x18000a797  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000a79d  nop
0x18000a79e  jmp     short loc_18000A777
0x18000a7a0  mov     [rsp+98h+var_58], rsi
0x18000a7a5  mov     rcx, [rsp+98h+arg_18]
0x18000a7ad  mov     rax, [rcx]
0x18000a7b0  lea     r8, [rsp+98h+var_58]
0x18000a7b5  lea     rdx, IID__IWmiObject
0x18000a7bc  mov     rax, [rax]
0x18000a7bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7c4  mov     rcx, [rsp+98h+arg_18]
0x18000a7cc  mov     rax, [rcx]
0x18000a7cf  mov     rax, [rax+10h]
0x18000a7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7d8  mov     rbx, [rsp+98h+var_58]
0x18000a7dd  lea     rcx, [rsp+98h+arg_8]
0x18000a7e5  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18000a7eb  jmp     loc_18000A75F
0x18000a7f0  lea     rcx, [rsp+98h+arg_8]
0x18000a7f8  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18000a7fe  xor     esi, esi
0x18000a800  jmp     loc_18000A75C
0x18000a805  cmp     byte ptr [rcx+19h], 5
0x18000a809  jb      loc_18000A390
0x18000a80f  mov     edx, 8Fh
0x18000a814  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
  ... truncated ...
```
