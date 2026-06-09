# SIdxKeyTable::MapFromPage(void *,MemoryPage *)

- ea: `0x18000e920`
- end: `0x18000eed3`
- name: `?MapFromPage@SIdxKeyTable@@QEAAKPEAXPEAVMemoryPage@@@Z`
- size: `1459`
- prototype: `unsigned int __fastcall(SIdxKeyTable *__hidden this, void *, struct MemoryPage *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d7e0`
- `0x18000f130`

## callees

- `0x1800012b8`
- `0x18000e920`
- `0x18000fcf0`
- `0x18002b7b6`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000ea62`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000ea62`
- `wbemcomn!?GetArenaHeap@CWin32DefaultArena@@SAPEAXXZ` at `0x18000e9eb`
- `wbemcomn!?GetArenaHeap@CWin32DefaultArena@@SAPEAXXZ` at `0x18000ebd3`
- `wbemcomn!?GetArenaHeap@CWin32DefaultArena@@SAPEAXXZ` at `0x18000e9eb`
- `wbemcomn!?GetArenaHeap@CWin32DefaultArena@@SAPEAXXZ` at `0x18000ebd3`
- `wbemcomn!GetMemLogObject` at `0x18000ea0f`
- `wbemcomn!GetMemLogObject` at `0x18000ea7d`
- `wbemcomn!GetMemLogObject` at `0x18000eaf4`
- `wbemcomn!GetMemLogObject` at `0x18000ec03`
- `wbemcomn!GetMemLogObject` at `0x18000ed77`
- `wbemcomn!GetMemLogObject` at `0x18000edce`
- `wbemcomn!GetMemLogObject` at `0x18000ee17`
- `wbemcomn!GetMemLogObject` at `0x18000ea0f`
- `wbemcomn!GetMemLogObject` at `0x18000ea7d`
- `wbemcomn!GetMemLogObject` at `0x18000eaf4`
- `wbemcomn!GetMemLogObject` at `0x18000ec03`
- `wbemcomn!GetMemLogObject` at `0x18000ed77`
- `wbemcomn!GetMemLogObject` at `0x18000edce`
- `wbemcomn!GetMemLogObject` at `0x18000ee17`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ea1d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ea8b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000eb02`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ec11`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ed85`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000eddc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ee25`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ea1d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ea8b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000eb02`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ec11`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ed85`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000eddc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ee25`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000e955`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000e955`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e9fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ebe4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e9fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ebe4`

## pseudocode

```c
__int64 __fastcall SIdxKeyTable::MapFromPage(SIdxKeyTable *this, _DWORD *a2, struct MemoryPage *a3)
{
  __int64 v6; // rax
  char *v7; // rsi
  __int64 v8; // rcx
  __int64 v9; // rdi
  char *v10; // rdx
  char *v11; // rax
  char *v12; // rcx
  unsigned int v13; // eax
  unsigned __int16 *v14; // rsi
  SIZE_T v15; // rdi
  void *v16; // rax
  void *v17; // rax
  CMemoryLog *v18; // rax
  CVarObjHeap *v19; // rcx
  __int64 v21; // rdi
  _OWORD *v22; // rax
  _OWORD *v23; // rdx
  CMemoryLog *v24; // rax
  __int64 v25; // rdx
  CMemoryLog *v26; // rax
  bool v27; // zf
  unsigned __int16 *v28; // r15
  int *v29; // rcx
  int v30; // eax
  __int64 v31; // rax
  unsigned int *v32; // rdx
  char *v33; // rcx
  const void *v34; // rdi
  __int64 v35; // rcx
  unsigned int v36; // eax
  __int64 v37; // rax
  SIZE_T v38; // rdi
  void *ArenaHeap; // rax
  unsigned int *v40; // rax
  void *v41; // rcx
  CMemoryLog *v42; // rax
  LPVOID v43; // rax
  __int64 v44; // rcx
  LPVOID v45; // rax
  SIZE_T v46; // rcx
  LPVOID v47; // rax
  _DWORD *v48; // rdx
  unsigned __int64 v49; // r8
  __int64 v50; // rax
  char *v51; // rdi
  __int64 v52; // r8
  char *v53; // rdi
  __int64 v54; // rax
  void *v55; // rcx
  CMemoryLog *v56; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v58; // rax

  if ( a2 )
  {
    if ( a3 )
    {
      *((_QWORD *)this + 9) = a3;
      if ( *(_QWORD *)a3 != 0x504F4F4E4E4F4F50LL || (unsigned int)(*((_DWORD *)a3 + 2) - 1) > 0xFFF )
        DebugBreak();
      _InterlockedIncrement((volatile signed __int32 *)a3 + 2);
    }
    if ( *a2 == 44236 )
    {
      *((_DWORD *)this + 1) = a2[1];
      *((_DWORD *)this + 2) = a2[3];
      v6 = (unsigned int)a2[4];
      v7 = (char *)(a2 + 5);
      v8 = (unsigned int)v6;
      *((_DWORD *)this + 3) = v6;
      if ( (unsigned int)v6 <= 0x100 )
        v8 = 256;
      *((_DWORD *)this + 6) = v8;
      if ( *((_QWORD *)this + 9) )
      {
        v9 = (unsigned int)v6;
        *((_QWORD *)this + 4) = v7;
        v10 = &v7[4 * v6];
        *((_QWORD *)this + 5) = v10;
        v11 = &v10[4 * (unsigned int)(v6 + 1)];
        *((_QWORD *)this + 2) = v11;
        v12 = &v11[2 * v9];
      }
      else
      {
        v43 = _BtrMemAlloc(4 * v8);
        v44 = (unsigned int)(*((_DWORD *)this + 6) + 1);
        *((_QWORD *)this + 4) = v43;
        v45 = _BtrMemAlloc(4 * v44);
        v46 = 2LL * *((unsigned int *)this + 6);
        *((_QWORD *)this + 5) = v45;
        v47 = _BtrMemAlloc(v46);
        v27 = *((_QWORD *)this + 4) == 0;
        *((_QWORD *)this + 2) = v47;
        if ( v27 || (v48 = (_DWORD *)*((_QWORD *)this + 5)) == 0 || !v47 )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, 8);
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            return 8;
          }
          v25 = 81;
          goto LABEL_23;
        }
        if ( ((unsigned __int8)v48 & 4) != 0 )
        {
          *v48 = -1;
          v49 = 256;
          ++v48;
        }
        else
        {
          v49 = 257;
        }
        memset(v48, 0xFFu, 8 * (v49 >> 1));
        if ( (v49 & 1) != 0 )
          v48[v49 - 1] = -1;
        memcpy_0(*((void **)this + 4), v7, 4LL * *((unsigned int *)this + 3));
        v50 = *((unsigned int *)this + 3);
        v51 = &v7[4 * v50];
        memcpy_0(*((void **)this + 5), v51, 4LL * (unsigned int)(v50 + 1));
        v52 = *((unsigned int *)this + 3);
        v53 = &v51[4 * (unsigned int)(v52 + 1)];
        memcpy_0(*((void **)this + 2), v53, 2 * v52);
        v12 = &v53[2 * *((unsigned int *)this + 3)];
      }
      v13 = *(unsigned __int16 *)v12;
      v14 = (unsigned __int16 *)(v12 + 2);
      *((_DWORD *)this + 15) = v13;
      if ( v13 <= 0x200 )
        v13 = 512;
      *((_DWORD *)this + 14) = v13;
      if ( *((_QWORD *)this + 9) )
      {
        *((_QWORD *)this + 6) = v14;
      }
      else
      {
        _InterlockedIncrement(&g_lAllocs);
        v15 = 2LL * v13;
        v16 = (void *)((__int64 (*)(void))CWin32DefaultArena::GetArenaHeap)();
        v17 = HeapAlloc(v16, 8u, v15);
        *((_QWORD *)this + 6) = v17;
        if ( !v17 )
        {
          v18 = GetMemLogObject();
          CMemoryLog::Write(v18, 8);
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            return 8;
          }
          v25 = 82;
LABEL_23:
          WPP_SF_d(*((_QWORD *)v19 + 2), v25, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 8);
          return 8;
        }
        memcpy_0(v17, v14, 2LL * *((unsigned int *)this + 15));
      }
      v21 = *((unsigned int *)this + 15);
      v22 = CWin32DefaultArena::WbemMemAlloc(0x30u);
      v23 = v22;
      if ( !v22 )
      {
        *((_QWORD *)this + 8) = 0;
        v24 = GetMemLogObject();
        CMemoryLog::Write(v24, 8);
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return 8;
        }
        v25 = 83;
        goto LABEL_23;
      }
      v27 = *((_QWORD *)this + 9) == 0;
      *v22 = 0;
      v22[1] = 0;
      v22[2] = 0;
      *((_BYTE *)v22 + 40) = v27;
      *((_QWORD *)this + 8) = v22;
      *(_DWORD *)v22 = v14[v21];
      v28 = &v14[v21 + 1];
      v29 = (int *)*((_QWORD *)this + 8);
      v30 = *v29;
      if ( (unsigned int)*v29 <= 0x100 )
        v30 = 256;
      v29[4] = v30;
      v31 = *((_QWORD *)this + 8);
      if ( *((_QWORD *)this + 9) )
      {
        *(_QWORD *)(v31 + 8) = v28;
      }
      else
      {
        v38 = 2LL * *(unsigned int *)(v31 + 16);
        _InterlockedIncrement(&g_lAllocs);
        ArenaHeap = (void *)CWin32DefaultArena::GetArenaHeap(v29, v23);
        *(_QWORD *)(*((_QWORD *)this + 8) + 8LL) = HeapAlloc(ArenaHeap, 8u, v38);
        v40 = (unsigned int *)*((_QWORD *)this + 8);
        v41 = (void *)*((_QWORD *)v40 + 1);
        if ( !v41 )
        {
          v42 = GetMemLogObject();
          CMemoryLog::Write(v42, 8);
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            return 8;
          }
          v25 = 84;
          goto LABEL_23;
        }
        memcpy_0(v41, v28, 2LL * *v40);
      }
      v32 = (unsigned int *)*((_QWORD *)this + 8);
      v33 = (char *)&v28[*v32];
      v34 = v33 + 2;
      v32[9] = *(unsigned __int16 *)v33;
      v35 = *((_QWORD *)this + 8);
      v36 = *(_DWORD *)(v35 + 36);
      if ( v36 <= 0x2200 )
        v36 = 8704;
      *(_DWORD *)(v35 + 32) = v36;
      v37 = *((_QWORD *)this + 8);
      if ( *((_QWORD *)this + 9) )
      {
        *(_QWORD *)(v37 + 24) = v34;
        return 0;
      }
      else
      {
        *(_QWORD *)(*((_QWORD *)this + 8) + 24LL) = _BtrMemAlloc(*(unsigned int *)(v37 + 32));
        v54 = *((_QWORD *)this + 8);
        v55 = *(void **)(v54 + 24);
        if ( !v55 )
        {
          v56 = GetMemLogObject();
          CMemoryLog::Write(v56, 8);
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            return 8;
          }
          v25 = 85;
          goto LABEL_23;
        }
        memcpy_0(v55, v34, *(unsigned int *)(v54 + 36));
        return 0;
      }
    }
    else
    {
      v26 = GetMemLogObject();
      CMemoryLog::Write(v26, 11);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 11);
      }
      return 11;
    }
  }
  else
  {
    v58 = GetMemLogObject();
    CMemoryLog::Write(v58, 87);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 87);
    }
    return 87;
  }
}

```

## disassembly

```asm
0x18000e920  push    rbx
0x18000e922  push    rsi
0x18000e923  push    rdi
0x18000e924  sub     rsp, 20h
0x18000e928  mov     rdi, r8
0x18000e92b  mov     rsi, rdx
0x18000e92e  mov     rbx, rcx
0x18000e931  test    rdx, rdx
0x18000e934  jz      loc_18000EE17
0x18000e93a  mov     [rsp+38h+arg_10], r14
0x18000e93f  test    r8, r8
0x18000e942  jz      short loc_18000E95F
0x18000e944  mov     [rcx+48h], r8
0x18000e948  cmp     dword ptr [r8], 4E4F4F50h
0x18000e94f  jz      loc_18000EAD0
0x18000e955  call    cs:__imp_DebugBreak
0x18000e95b  lock inc dword ptr [rdi+8]
0x18000e95f  cmp     dword ptr [rsi], 0ACCCh
0x18000e965  jnz     loc_18000EAF4
0x18000e96b  mov     eax, [rsi+4]
0x18000e96e  mov     [rbx+4], eax
0x18000e971  mov     eax, [rsi+0Ch]
0x18000e974  mov     [rsp+38h+arg_0], rbp
0x18000e979  mov     ebp, 100h
0x18000e97e  mov     [rbx+8], eax
0x18000e981  mov     eax, [rsi+10h]
0x18000e984  add     rsi, 14h
0x18000e988  cmp     eax, ebp
0x18000e98a  mov     [rsp+38h+arg_18], r15
0x18000e98f  mov     ecx, eax
0x18000e991  mov     [rbx+0Ch], eax
0x18000e994  cmovbe  ecx, ebp
0x18000e997  mov     [rbx+18h], ecx
0x18000e99a  cmp     qword ptr [rbx+48h], 0
0x18000e99f  jz      loc_18000EC4C
0x18000e9a5  mov     edi, eax
0x18000e9a7  mov     [rbx+20h], rsi
0x18000e9ab  lea     rdx, [rsi+rax*4]
0x18000e9af  inc     eax
0x18000e9b1  mov     [rbx+28h], rdx
0x18000e9b5  lea     rax, [rdx+rax*4]
0x18000e9b9  mov     [rbx+10h], rax
0x18000e9bd  lea     rcx, [rax+rdi*2]
0x18000e9c1  movzx   eax, word ptr [rcx]
0x18000e9c4  lea     rsi, [rcx+2]
0x18000e9c8  mov     ecx, 200h
0x18000e9cd  mov     [rbx+3Ch], eax
0x18000e9d0  cmp     eax, ecx
0x18000e9d2  cmovbe  eax, ecx
0x18000e9d5  mov     [rbx+38h], eax
0x18000e9d8  cmp     qword ptr [rbx+48h], 0
0x18000e9dd  jnz     short loc_18000EA56
0x18000e9df  lock inc cs:?g_lAllocs@@3JA; long g_lAllocs
0x18000e9e6  mov     edi, eax
0x18000e9e8  add     rdi, rdi
0x18000e9eb  call    cs:__imp_?GetArenaHeap@CWin32DefaultArena@@SAPEAXXZ; CWin32DefaultArena::GetArenaHeap(void)
0x18000e9f1  mov     r8, rdi; dwBytes
0x18000e9f4  mov     edx, 8; dwFlags
0x18000e9f9  mov     rcx, rax; hHeap
0x18000e9fc  call    cs:__imp_HeapAlloc
0x18000ea02  mov     [rbx+30h], rax
0x18000ea06  test    rax, rax
0x18000ea09  jnz     loc_18000ED4D
0x18000ea0f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000ea15  mov     rcx, rax
0x18000ea18  mov     edx, 8
0x18000ea1d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000ea23  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea2a  lea     rax, WPP_GLOBAL_Control
0x18000ea31  cmp     rcx, rax
0x18000ea34  jnz     loc_18000EEB5
0x18000ea3a  mov     eax, 8
0x18000ea3f  mov     rbp, [rsp+38h+arg_0]
0x18000ea44  mov     r15, [rsp+38h+arg_18]
0x18000ea49  mov     r14, [rsp+38h+arg_10]
0x18000ea4e  add     rsp, 20h
0x18000ea52  pop     rdi
0x18000ea53  pop     rsi
0x18000ea54  pop     rbx
0x18000ea55  retn
0x18000ea56  mov     [rbx+30h], rsi
0x18000ea5a  mov     edi, [rbx+3Ch]
0x18000ea5d  mov     ecx, 30h ; '0'
0x18000ea62  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000ea68  mov     [rsp+38h+arg_8], rax
0x18000ea6d  mov     rdx, rax
0x18000ea70  test    rax, rax
0x18000ea73  jnz     loc_18000EB31
0x18000ea79  mov     [rbx+40h], rax
0x18000ea7d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000ea83  mov     rcx, rax
0x18000ea86  mov     edx, 8
0x18000ea8b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000ea91  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea98  lea     rax, WPP_GLOBAL_Control
0x18000ea9f  cmp     rcx, rax
0x18000eaa2  jz      short loc_18000EA3A
0x18000eaa4  test    byte ptr [rcx+1Ch], 1
0x18000eaa8  jz      short loc_18000EA3A
0x18000eaaa  cmp     byte ptr [rcx+19h], 2
0x18000eaae  jb      short loc_18000EA3A
0x18000eab0  mov     edx, 53h ; 'S'
0x18000eab5  mov     rcx, [rcx+10h]
0x18000eab9  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000eac0  mov     r9d, 8
0x18000eac6  call    WPP_SF_d
0x18000eacb  jmp     loc_18000EA3A
0x18000ead0  cmp     dword ptr [r8+4], 504F4F4Eh
0x18000ead8  jnz     loc_18000E955
0x18000eade  mov     eax, [r8+8]
0x18000eae2  dec     eax
0x18000eae4  cmp     eax, 0FFFh
0x18000eae9  jbe     loc_18000E95B
0x18000eaef  jmp     loc_18000E955
0x18000eaf4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000eafa  mov     rcx, rax
0x18000eafd  mov     edx, 0Bh
0x18000eb02  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000eb08  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb0f  lea     rax, WPP_GLOBAL_Control
0x18000eb16  cmp     rcx, rax
0x18000eb19  jnz     loc_18000EE6F
0x18000eb1f  mov     r14, [rsp+38h+arg_10]
0x18000eb24  mov     eax, 0Bh
0x18000eb29  add     rsp, 20h
0x18000eb2d  pop     rdi
0x18000eb2e  pop     rsi
0x18000eb2f  pop     rbx
0x18000eb30  retn
0x18000eb31  cmp     qword ptr [rbx+48h], 0
0x18000eb36  xorps   xmm0, xmm0
0x18000eb39  movups  xmmword ptr [rax], xmm0
0x18000eb3c  setz    cl
0x18000eb3f  movups  xmmword ptr [rax+10h], xmm0
0x18000eb43  movups  xmmword ptr [rax+20h], xmm0
0x18000eb47  mov     [rax+28h], cl
0x18000eb4a  mov     [rbx+40h], rdx
0x18000eb4e  test    rdx, rdx
0x18000eb51  jz      loc_18000EA7D
0x18000eb57  movzx   eax, word ptr [rsi+rdi*2]
0x18000eb5b  lea     r15, [rdi+1]
0x18000eb5f  mov     [rdx], eax
0x18000eb61  lea     r15, [rsi+r15*2]
0x18000eb65  mov     rcx, [rbx+40h]
0x18000eb69  mov     eax, [rcx]
0x18000eb6b  cmp     eax, ebp
0x18000eb6d  cmovbe  eax, ebp
0x18000eb70  mov     [rcx+10h], eax
0x18000eb73  cmp     qword ptr [rbx+48h], 0
0x18000eb78  mov     rax, [rbx+40h]
0x18000eb7c  jz      short loc_18000EBC6
0x18000eb7e  mov     [rax+8], r15
0x18000eb82  mov     rdx, [rbx+40h]
0x18000eb86  mov     eax, [rdx]
0x18000eb88  lea     rcx, [r15+rax*2]
0x18000eb8c  movzx   eax, word ptr [r15+rax*2]
0x18000eb91  lea     rdi, [rcx+2]
0x18000eb95  mov     [rdx+24h], eax
0x18000eb98  mov     edx, 2200h
0x18000eb9d  mov     rcx, [rbx+40h]
0x18000eba1  mov     eax, [rcx+24h]
0x18000eba4  cmp     eax, edx
0x18000eba6  cmovbe  eax, edx
0x18000eba9  mov     [rcx+20h], eax
0x18000ebac  cmp     qword ptr [rbx+48h], 0
0x18000ebb1  mov     rax, [rbx+40h]
0x18000ebb5  jz      loc_18000ED1D
0x18000ebbb  mov     [rax+18h], rdi
0x18000ebbf  xor     eax, eax
0x18000ebc1  jmp     loc_18000EA3F
0x18000ebc6  mov     edi, [rax+10h]
0x18000ebc9  add     rdi, rdi
0x18000ebcc  lock inc cs:?g_lAllocs@@3JA; long g_lAllocs
0x18000ebd3  call    cs:__imp_?GetArenaHeap@CWin32DefaultArena@@SAPEAXXZ; CWin32DefaultArena::GetArenaHeap(void)
0x18000ebd9  mov     r8, rdi; dwBytes
0x18000ebdc  mov     edx, 8; dwFlags
0x18000ebe1  mov     rcx, rax; hHeap
0x18000ebe4  call    cs:__imp_HeapAlloc
0x18000ebea  mov     rcx, [rbx+40h]
0x18000ebee  mov     [rcx+8], rax
0x18000ebf2  mov     rax, [rbx+40h]
0x18000ebf6  mov     rcx, [rax+8]; void *
0x18000ebfa  test    rcx, rcx
0x18000ebfd  jnz     loc_18000ED64
0x18000ec03  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000ec09  mov     rcx, rax
0x18000ec0c  mov     edx, 8
0x18000ec11  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000ec17  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec1e  lea     rax, WPP_GLOBAL_Control
0x18000ec25  cmp     rcx, rax
0x18000ec28  jz      loc_18000EA3A
0x18000ec2e  test    byte ptr [rcx+1Ch], 1
0x18000ec32  jz      loc_18000EA3A
0x18000ec38  cmp     byte ptr [rcx+19h], 2
0x18000ec3c  jb      loc_18000EA3A
0x18000ec42  mov     edx, 54h ; 'T'
0x18000ec47  jmp     loc_18000EAB5
0x18000ec4c  shl     rcx, 2; unsigned __int64
0x18000ec50  call    ?_BtrMemAlloc@@YAPEAX_K@Z; _BtrMemAlloc(unsigned __int64)
0x18000ec55  mov     ecx, [rbx+18h]
0x18000ec58  inc     ecx
0x18000ec5a  mov     [rbx+20h], rax
0x18000ec5e  shl     rcx, 2; unsigned __int64
0x18000ec62  call    ?_BtrMemAlloc@@YAPEAX_K@Z; _BtrMemAlloc(unsigned __int64)
0x18000ec67  mov     ecx, [rbx+18h]
0x18000ec6a  add     rcx, rcx; unsigned __int64
0x18000ec6d  mov     [rbx+28h], rax
0x18000ec71  call    ?_BtrMemAlloc@@YAPEAX_K@Z; _BtrMemAlloc(unsigned __int64)
0x18000ec76  cmp     qword ptr [rbx+20h], 0
0x18000ec7b  mov     [rbx+10h], rax
0x18000ec7f  jz      loc_18000EDCE
0x18000ec85  mov     rdx, [rbx+28h]
0x18000ec89  test    rdx, rdx
0x18000ec8c  jz      loc_18000EDCE
0x18000ec92  test    rax, rax
0x18000ec95  jz      loc_18000EDCE
0x18000ec9b  test    dl, 4
0x18000ec9e  jnz     loc_18000EEA3
0x18000eca4  mov     r8d, 101h
0x18000ecaa  mov     rcx, r8
0x18000ecad  mov     rdi, rdx
0x18000ecb0  shr     rcx, 1
0x18000ecb3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000ecba  rep stosq
0x18000ecbd  test    r8b, 1
0x18000ecc1  jnz     loc_18000EDC0
0x18000ecc7  mov     r8d, [rbx+0Ch]
0x18000eccb  mov     rdx, rsi; Src
0x18000ecce  mov     rcx, [rbx+20h]; void *
0x18000ecd2  shl     r8, 2; Size
0x18000ecd6  call    memcpy_0
0x18000ecdb  mov     eax, [rbx+0Ch]
0x18000ecde  mov     rcx, [rbx+28h]; void *
0x18000ece2  lea     rdi, [rsi+rax*4]
0x18000ece6  lea     r8d, [rax+1]
0x18000ecea  mov     rdx, rdi; Src
0x18000eced  shl     r8, 2; Size
0x18000ecf1  call    memcpy_0
0x18000ecf6  mov     r8d, [rbx+0Ch]
0x18000ecfa  mov     rcx, [rbx+10h]; void *
0x18000ecfe  lea     eax, [r8+1]
0x18000ed02  add     r8, r8; Size
0x18000ed05  lea     rdi, [rdi+rax*4]
0x18000ed09  mov     rdx, rdi; Src
0x18000ed0c  call    memcpy_0
0x18000ed11  mov     eax, [rbx+0Ch]
0x18000ed14  lea     rcx, [rdi+rax*2]
0x18000ed18  jmp     loc_18000E9C1
0x18000ed1d  mov     ecx, [rax+20h]; unsigned __int64
0x18000ed20  call    ?_BtrMemAlloc@@YAPEAX_K@Z; _BtrMemAlloc(unsigned __int64)
0x18000ed25  mov     rcx, [rbx+40h]
0x18000ed29  mov     [rcx+18h], rax
0x18000ed2d  mov     rax, [rbx+40h]
0x18000ed31  mov     rcx, [rax+18h]; void *
0x18000ed35  test    rcx, rcx
0x18000ed38  jz      short loc_18000ED77
0x18000ed3a  mov     r8d, [rax+24h]; Size
0x18000ed3e  mov     rdx, rdi; Src
0x18000ed41  call    memcpy_0
0x18000ed46  xor     eax, eax
0x18000ed48  jmp     loc_18000EA3F
0x18000ed4d  mov     r8d, [rbx+3Ch]
0x18000ed51  mov     rdx, rsi; Src
0x18000ed54  add     r8, r8; Size
0x18000ed57  mov     rcx, rax; void *
0x18000ed5a  call    memcpy_0
0x18000ed5f  jmp     loc_18000EA5A
0x18000ed64  mov     r8d, [rax]
0x18000ed67  mov     rdx, r15; Src
0x18000ed6a  add     r8, r8; Size
0x18000ed6d  call    memcpy_0
0x18000ed72  jmp     loc_18000EB82
0x18000ed77  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000ed7d  mov     rcx, rax
0x18000ed80  mov     edx, 8
0x18000ed85  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000ed8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed92  lea     rax, WPP_GLOBAL_Control
0x18000ed99  cmp     rcx, rax
0x18000ed9c  jz      loc_18000EA3A
0x18000eda2  test    byte ptr [rcx+1Ch], 1
0x18000eda6  jz      loc_18000EA3A
0x18000edac  cmp     byte ptr [rcx+19h], 2
0x18000edb0  jb      loc_18000EA3A
0x18000edb6  mov     edx, 55h ; 'U'
0x18000edbb  jmp     loc_18000EAB5
0x18000edc0  mov     dword ptr [rdx+r8*4-4], 0FFFFFFFFh
0x18000edc9  jmp     loc_18000ECC7
0x18000edce  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000edd4  mov     rcx, rax
0x18000edd7  mov     edx, 8
0x18000eddc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000ede2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ede9  lea     rax, WPP_GLOBAL_Control
0x18000edf0  cmp     rcx, rax
0x18000edf3  jz      loc_18000EA3A
0x18000edf9  test    byte ptr [rcx+1Ch], 1
0x18000edfd  jz      loc_18000EA3A
0x18000ee03  cmp     byte ptr [rcx+19h], 2
  ... truncated ...
```
