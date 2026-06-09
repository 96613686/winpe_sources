# CAbstractTransfer::SingleAsyncOpCompleted(CAbstractTransfer::PENDING_OP_DATA *)

- ea: `0x180042680`
- end: `0x180042a4f`
- name: `?SingleAsyncOpCompleted@CAbstractTransfer@@IEAAXPEAUPENDING_OP_DATA@1@@Z`
- size: `975`
- prototype: `void __fastcall(CAbstractTransfer *__hidden this, struct CAbstractTransfer::PENDING_OP_DATA *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180042560`

## callees

- `0x180034170`
- `0x180042680`
- `0x180055f50`
- `0x18009d024`
- `0x1800ab6e8`
- `0x1800ab7b0`
- `0x1800ab7fc`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800426be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800426be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042770`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042834`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042888`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800428bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042770`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042834`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042888`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800428bf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800427fa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800429a9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800427fa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800429a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAbstractTransfer::SingleAsyncOpCompleted(
        CAbstractTransfer *this,
        struct CAbstractTransfer::PENDING_OP_DATA *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  __int64 i; // r9
  struct _TP_WAIT *v6; // rdi
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  EVENT_LOG *v8; // rcx
  ComError *v9; // rax
  ComError *v10; // [rsp+30h] [rbp-88h] BYREF
  char v11[8]; // [rsp+38h] [rbp-80h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+40h] [rbp-78h]
  __int64 v13; // [rsp+48h] [rbp-70h] BYREF

  try
  {
    v11[0] = 0;
    v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
    lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 8);
    if ( *((_BYTE *)this + 48)
      && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v4);
    }
    EnterCriticalSection(v4);
    v11[0] = 1;
    if ( *((_BYTE *)this + 105) )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids);
        v8 = WPP_GLOBAL_Control;
      }
      if ( LOBYTE(lpCriticalSection[1].DebugInfo)
        && v8 != (EVENT_LOG *)&WPP_GLOBAL_Control
        && (*((_DWORD *)v8 + 7) & 0x100) != 0 )
      {
        WPP_SF_q(*((_QWORD *)v8 + 2), 16, &WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, lpCriticalSection);
      }
      LeaveCriticalSection(lpCriticalSection);
    }
    else
    {
      for ( i = 0; (int)i < *((_DWORD *)this + 27); i = (unsigned int)(i + 1) )
      {
        if ( *((_QWORD *)this + 3 * (int)i + 16) == *((_QWORD *)a2 + 1)
          && *((_QWORD *)this + 3 * (int)i + 17) == *((_QWORD *)a2 + 2) )
        {
          if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
          {
            WPP_SF_dq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              40,
              &WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids,
              i,
              *((_QWORD *)a2 + 1));
          }
          break;
        }
      }
      ++*((_DWORD *)this + 28);
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          41,
          &WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids,
          *((unsigned int *)this + 28),
          *((_DWORD *)this + 27));
      v6 = (struct _TP_WAIT *)*((_QWORD *)a2 + 2);
      *((_QWORD *)a2 + 2) = 0;
      if ( *((_DWORD *)this + 28) == *((_DWORD *)this + 27) )
      {
        *((_BYTE *)this + 106) = 0;
        *((_DWORD *)this + 27) = 0;
        if ( *((_BYTE *)this + 105) )
          CEvent::Set((CAbstractTransfer *)((char *)this + 64));
        else
          (*(void (__fastcall **)(CAbstractTransfer *, char *))(*(_QWORD *)this + 224LL))(this, v11);
        if ( v11[0] )
        {
          v11[0] = 0;
          CCritSec2::leave((CCritSec2 *)lpCriticalSection);
        }
        (*(void (__fastcall **)(CAbstractTransfer *))(*(_QWORD *)this + 40LL))(this);
        if ( v6 )
          CloseThreadpoolWait(v6);
        if ( v11[0] )
        {
          v7 = lpCriticalSection;
          if ( LOBYTE(lpCriticalSection[1].DebugInfo)
            && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WPP_SF_q(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              &WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids,
              lpCriticalSection);
          }
          LeaveCriticalSection(v7);
        }
      }
      else
      {
        v11[0] = 0;
        if ( LOBYTE(lpCriticalSection[1].DebugInfo)
          && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WPP_SF_q(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            &WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids,
            lpCriticalSection);
        }
        LeaveCriticalSection(lpCriticalSection);
        (*(void (__fastcall **)(CAbstractTransfer *))(*(_QWORD *)this + 40LL))(this);
        if ( v6 )
          CloseThreadpoolWait(v6);
      }
    }
  }
  catch ( ComError *v10 )
  {
    v9 = ComError::ComError((ComError *)&v13, v10);
    LogException(v9);
  }
}

```

## disassembly

```asm
0x180042680  mov     [rsp+arg_8], rbx
0x180042685  mov     [rsp+arg_10], rsi
0x18004268a  push    rdi
0x18004268b  push    r14
0x18004268d  push    r15
0x18004268f  sub     rsp, 0A0h
0x180042696  mov     rsi, rdx
0x180042699  mov     rbx, rcx
0x18004269c  mov     [rsp+0B8h+var_80], 0
0x1800426a1  lea     rdi, [rcx+8]
0x1800426a5  mov     [rsp+0B8h+lpCriticalSection], rdi
0x1800426aa  cmp     byte ptr [rdi+28h], 0
0x1800426ae  jnz     loc_1800428CA
0x1800426b4  lea     r14, WPP_GLOBAL_Control
0x1800426bb  mov     rcx, rdi; lpCriticalSection
0x1800426be  call    cs:__imp_EnterCriticalSection
0x1800426c4  mov     al, 1
0x1800426c6  mov     [rsp+0B8h+var_80], al
0x1800426ca  cmp     byte ptr [rbx+69h], 0
0x1800426ce  jnz     loc_180042805
0x1800426d4  xor     r15d, r15d
0x1800426d7  mov     r9d, r15d
0x1800426da  cmp     r9d, [rbx+6Ch]
0x1800426de  jl      loc_180042790
0x1800426e4  inc     dword ptr [rbx+70h]
0x1800426e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800426ee  cmp     rcx, r14
0x1800426f1  jnz     loc_18004283F
0x1800426f7  mov     rdi, [rsi+10h]
0x1800426fb  mov     [rsi+10h], r15
0x1800426ff  mov     eax, [rbx+6Ch]
0x180042702  cmp     [rbx+70h], eax
0x180042705  jnz     loc_180042871
0x18004270b  mov     [rbx+6Ah], r15b
0x18004270f  mov     [rbx+6Ch], r15d
0x180042713  cmp     [rbx+69h], r15b
0x180042717  jnz     loc_1800429EE
0x18004271d  mov     rax, [rbx]
0x180042720  lea     rdx, [rsp+0B8h+var_80]
0x180042725  mov     rcx, rbx
0x180042728  mov     rax, [rax+0E0h]
0x18004272f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042734  cmp     [rsp+0B8h+var_80], r15b
0x180042739  jnz     loc_1800429FC
0x18004273f  mov     rax, [rbx]
0x180042742  mov     rcx, rbx
0x180042745  mov     rax, [rax+28h]
0x180042749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004274e  test    rdi, rdi
0x180042751  jnz     loc_1800427F7
0x180042757  cmp     [rsp+0B8h+var_80], 0
0x18004275c  jz      short loc_180042777
0x18004275e  mov     rbx, [rsp+0B8h+lpCriticalSection]
0x180042763  cmp     byte ptr [rbx+28h], 0
0x180042767  jnz     loc_180042A10
0x18004276d  mov     rcx, rbx; lpCriticalSection
0x180042770  call    cs:__imp_LeaveCriticalSection
0x180042776  nop
0x180042777  lea     r11, [rsp+0B8h+var_18]
0x18004277f  mov     rbx, [r11+28h]
0x180042783  mov     rsi, [r11+30h]
0x180042787  mov     rsp, r11
0x18004278a  pop     r15
0x18004278c  pop     r14
0x18004278e  pop     rdi
0x18004278f  retn
0x180042790  movsxd  rax, r9d
0x180042793  lea     rcx, [rax+rax*2]
0x180042797  mov     r8, [rsi+8]
0x18004279b  cmp     [rbx+rcx*8+80h], r8
0x1800427a3  jnz     loc_180042964
0x1800427a9  mov     rax, [rsi+10h]
0x1800427ad  cmp     [rbx+rcx*8+88h], rax
0x1800427b5  jnz     loc_180042964
0x1800427bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800427c2  cmp     rcx, r14
0x1800427c5  jz      loc_1800426E4
0x1800427cb  test    dword ptr [rcx+1Ch], 800h
0x1800427d2  jz      loc_1800426E4
0x1800427d8  mov     edx, 28h ; '('
0x1800427dd  mov     [rsp+0B8h+var_98], r8
0x1800427e2  lea     r8, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids
0x1800427e9  mov     rcx, [rcx+10h]
0x1800427ed  call    WPP_SF_dq
0x1800427f2  jmp     loc_1800426E4
0x1800427f7  mov     rcx, rdi; pwa
0x1800427fa  call    cs:__imp_CloseThreadpoolWait
0x180042800  jmp     loc_180042757
0x180042805  mov     rcx, cs:WPP_GLOBAL_Control
0x18004280c  cmp     rcx, r14
0x18004280f  jz      short loc_18004281E
0x180042811  test    dword ptr [rcx+1Ch], 800h
0x180042818  jnz     loc_18004290B
0x18004281e  test    al, al
0x180042820  jz      short loc_18004283A
0x180042822  mov     rbx, [rsp+0B8h+lpCriticalSection]
0x180042827  cmp     byte ptr [rbx+28h], 0
0x18004282b  jnz     loc_180042931
0x180042831  mov     rcx, rbx; lpCriticalSection
0x180042834  call    cs:__imp_LeaveCriticalSection
0x18004283a  jmp     loc_180042777
0x18004283f  test    dword ptr [rcx+1Ch], 800h
0x180042846  jz      loc_1800426F7
0x18004284c  mov     edx, 29h ; ')'
0x180042851  mov     eax, [rbx+6Ch]
0x180042854  mov     dword ptr [rsp+0B8h+var_98], eax
0x180042858  mov     r9d, [rbx+70h]
0x18004285c  lea     r8, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids
0x180042863  mov     rcx, [rcx+10h]
0x180042867  call    WPP_SF_Dd
0x18004286c  jmp     loc_1800426F7
0x180042871  mov     [rsp+0B8h+var_80], r15b
0x180042876  mov     rsi, [rsp+0B8h+lpCriticalSection]
0x18004287b  cmp     [rsi+28h], r15b
0x18004287f  jnz     loc_18004296C
0x180042885  mov     rcx, rsi; lpCriticalSection
0x180042888  call    cs:__imp_LeaveCriticalSection
0x18004288e  mov     rax, [rbx]
0x180042891  mov     rcx, rbx
0x180042894  mov     rax, [rax+28h]
0x180042898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004289d  test    rdi, rdi
0x1800428a0  jnz     loc_1800429A6
0x1800428a6  cmp     [rsp+0B8h+var_80], 0
0x1800428ab  jz      short loc_1800428C5
0x1800428ad  mov     rbx, [rsp+0B8h+lpCriticalSection]
0x1800428b2  cmp     byte ptr [rbx+28h], 0
0x1800428b6  jnz     loc_1800429B4
0x1800428bc  mov     rcx, rbx; lpCriticalSection
0x1800428bf  call    cs:__imp_LeaveCriticalSection
0x1800428c5  jmp     loc_180042777
0x1800428ca  lea     r14, WPP_GLOBAL_Control
0x1800428d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800428d8  cmp     rcx, r14
0x1800428db  jz      loc_1800426BB
0x1800428e1  test    dword ptr [rcx+1Ch], 100h
0x1800428e8  jz      loc_1800426BB
0x1800428ee  mov     edx, 0Fh
0x1800428f3  mov     r9, rdi
0x1800428f6  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x1800428fd  mov     rcx, [rcx+10h]
0x180042901  call    WPP_SF_q
0x180042906  jmp     loc_1800426BB
0x18004290b  mov     edx, 27h ; '''
0x180042910  lea     r8, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids
0x180042917  mov     rcx, [rcx+10h]
0x18004291b  call    WPP_SF_
0x180042920  movzx   eax, [rsp+0B8h+var_80]
0x180042925  mov     rcx, cs:WPP_GLOBAL_Control
0x18004292c  jmp     loc_18004281E
0x180042931  cmp     rcx, r14
0x180042934  jz      loc_180042831
0x18004293a  test    dword ptr [rcx+1Ch], 100h
0x180042941  jz      loc_180042831
0x180042947  mov     edx, 10h
0x18004294c  mov     r9, rbx
0x18004294f  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x180042956  mov     rcx, [rcx+10h]
0x18004295a  call    WPP_SF_q
0x18004295f  jmp     loc_180042831
0x180042964  inc     r9d
0x180042967  jmp     loc_1800426DA
0x18004296c  mov     rcx, cs:WPP_GLOBAL_Control
0x180042973  cmp     rcx, r14
0x180042976  jz      loc_180042885
0x18004297c  test    dword ptr [rcx+1Ch], 100h
0x180042983  jz      loc_180042885
0x180042989  mov     edx, 10h
0x18004298e  mov     r9, rsi
0x180042991  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x180042998  mov     rcx, [rcx+10h]
0x18004299c  call    WPP_SF_q
0x1800429a1  jmp     loc_180042885
0x1800429a6  mov     rcx, rdi; pwa
0x1800429a9  call    cs:__imp_CloseThreadpoolWait
0x1800429af  jmp     loc_1800428A6
0x1800429b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800429bb  cmp     rcx, r14
0x1800429be  jz      loc_1800428BC
0x1800429c4  test    dword ptr [rcx+1Ch], 100h
0x1800429cb  jz      loc_1800428BC
0x1800429d1  mov     edx, 10h
0x1800429d6  mov     r9, rbx
0x1800429d9  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x1800429e0  mov     rcx, [rcx+10h]
0x1800429e4  call    WPP_SF_q
0x1800429e9  jmp     loc_1800428BC
0x1800429ee  lea     rcx, [rbx+40h]; this
0x1800429f2  call    ?Set@CEvent@@QEAAXXZ; CEvent::Set(void)
0x1800429f7  jmp     loc_180042734
0x1800429fc  mov     [rsp+0B8h+var_80], r15b
0x180042a01  mov     rcx, [rsp+0B8h+lpCriticalSection]; this
0x180042a06  call    ?leave@CCritSec2@@QEAAXXZ; CCritSec2::leave(void)
0x180042a0b  jmp     loc_18004273F
0x180042a10  mov     rcx, cs:WPP_GLOBAL_Control
0x180042a17  cmp     rcx, r14
0x180042a1a  jz      loc_18004276D
0x180042a20  test    dword ptr [rcx+1Ch], 100h
0x180042a27  jz      loc_18004276D
0x180042a2d  mov     edx, 10h
0x180042a32  mov     r9, rbx
0x180042a35  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x180042a3c  mov     rcx, [rcx+10h]
0x180042a40  call    WPP_SF_q
0x180042a45  jmp     loc_18004276D
0x180042a4a  jmp     loc_180042777
```
