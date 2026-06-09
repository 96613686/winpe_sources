# SrvCryptGetKeyProperty

- ea: `0x1800041b0`
- end: `0x18000445c`
- name: `SrvCryptGetKeyProperty`
- size: `684`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _WORD *, __int64, int, __int64, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800041b0`
- `0x180004470`
- `0x1800048f0`
- `0x18000a520`
- `0x180019010`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x1800041e3`
- `ntdll!RtlEnterCriticalSection` at `0x1800041e3`
- `ntdll!RtlLeaveCriticalSection` at `0x18000421c`
- `ntdll!RtlLeaveCriticalSection` at `0x18000421c`

## string_xrefs

- `0x180004282`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180004343`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180004392`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000440a`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000443a`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x1800043e5`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvutils.c`

## pseudocode

```c
__int64 __fastcall SrvCryptGetKeyProperty(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _WORD *a4,
        __int64 a5,
        int a6,
        __int64 a7,
        int a8)
{
  int v11; // esi
  volatile signed __int64 *v12; // r14
  _QWORD *v13; // rax
  int v14; // edx
  int v15; // r8d
  __int64 v16; // rcx
  _WORD *v17; // rax
  int v18; // ebx
  int v20; // edx
  int v21; // r8d
  int v22; // eax
  unsigned int v23; // edi
  __int64 v24; // r9

  if ( a1 )
  {
    v11 = 0;
    v12 = 0;
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 104));
    v13 = *(_QWORD **)(a1 + 144);
    while ( v13 != (_QWORD *)(a1 + 144) )
    {
      v12 = v13 - 2;
      v13 = (_QWORD *)*v13;
      if ( *((_QWORD *)v12 + 6) == a3 )
      {
        if ( *(_DWORD *)v12 == 1145324615 )
        {
          _InterlockedIncrement64(v12 + 1);
          v11 = 1;
        }
        break;
      }
    }
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 104));
    if ( !v11 )
      v12 = 0;
    if ( v12 )
    {
      if ( a4 )
      {
        v16 = 64;
        v17 = a4;
        while ( *v17 )
        {
          ++v17;
          if ( !--v16 )
          {
            v18 = -2146893785;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v14,
                v15,
                (unsigned int)"Status",
                39,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
                8);
            goto LABEL_17;
          }
        }
        if ( !a7 )
        {
          v24 = 3343;
          goto LABEL_36;
        }
        v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _WORD *, __int64, int, __int64, int))(*((_QWORD *)v12 + 4)
                                                                                             + 80LL))(
                *(_QWORD *)(*((_QWORD *)v12 + 4) + 296LL),
                *((_QWORD *)v12 + 5),
                a4,
                a5,
                a6,
                a7,
                a8);
        if ( v18 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v20,
              v21,
              (unsigned int)"Status",
              v18,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
              34);
          v18 = NormalizeNteStatus((unsigned int)v18);
        }
      }
      else
      {
        v24 = 3329;
LABEL_36:
        v18 = -2146893785;
        DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v24);
      }
LABEL_17:
      if ( _InterlockedExchangeAdd64(v12 + 1, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
      {
        v22 = SrvFreeKey((PVOID)v12);
        v23 = v22;
        if ( v22 < 0 )
        {
          DebugTraceError(
            (unsigned int)v22,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvutils.c",
            740);
          if ( v18 >= 0 )
            return v23;
        }
      }
      return (unsigned int)v18;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          v15,
          (unsigned int)"Status",
          38,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          250);
      return 2148073510LL;
    }
  }
  else
  {
    DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 3313);
    return 2148073510LL;
  }
}

```

## disassembly

```asm
0x1800041b0  push    rbx
0x1800041b2  push    rdi
0x1800041b3  push    r15
0x1800041b5  sub     rsp, 40h
0x1800041b9  mov     r15, r9
0x1800041bc  mov     rbx, r8
0x1800041bf  mov     rdi, rcx
0x1800041c2  test    rcx, rcx
0x1800041c5  jz      loc_180004404
0x1800041cb  mov     [rsp+58h+arg_8], rbp
0x1800041d0  add     rcx, 68h ; 'h'; CriticalSection
0x1800041d4  mov     [rsp+58h+arg_10], rsi
0x1800041d9  xor     esi, esi
0x1800041db  mov     [rsp+58h+arg_18], r14
0x1800041e0  xor     r14d, r14d
0x1800041e3  call    cs:__imp_RtlEnterCriticalSection
0x1800041e9  lea     rdx, [rdi+90h]
0x1800041f0  mov     rax, [rdx]
0x1800041f3  cmp     rax, rdx
0x1800041f6  jz      short loc_180004218
0x1800041f8  lea     r14, [rax-10h]
0x1800041fc  mov     rax, [rax]
0x1800041ff  cmp     [r14+30h], rbx
0x180004203  jnz     short loc_1800041F3
0x180004205  cmp     dword ptr [r14], 44444447h
0x18000420c  jnz     short loc_180004218
0x18000420e  lock inc qword ptr [r14+8]
0x180004213  mov     esi, 1
0x180004218  lea     rcx, [rdi+68h]; CriticalSection
0x18000421c  call    cs:__imp_RtlLeaveCriticalSection
0x180004222  mov     rbp, [rsp+58h+arg_8]
0x180004227  xor     eax, eax
0x180004229  test    esi, esi
0x18000422b  mov     rsi, [rsp+58h+arg_10]
0x180004230  cmovz   r14, rax
0x180004234  test    r14, r14
0x180004237  jz      loc_180004375
0x18000423d  test    r15, r15
0x180004240  jz      loc_18000442C
0x180004246  mov     ecx, 40h ; '@'
0x18000424b  mov     rax, r15
0x18000424e  xchg    ax, ax
0x180004250  cmp     word ptr [rax], 0
0x180004254  jz      short loc_1800042D1
0x180004256  add     rax, 2
0x18000425a  sub     rcx, 1
0x18000425e  jnz     short loc_180004250
0x180004260  mov     ebx, 80090027h
0x180004265  mov     rcx, cs:WPP_GLOBAL_Control
0x18000426c  lea     rax, WPP_GLOBAL_Control
0x180004273  cmp     rcx, rax
0x180004276  jz      short loc_1800042AA
0x180004278  test    byte ptr [rcx+1Ch], 1
0x18000427c  jz      short loc_1800042AA
0x18000427e  mov     rcx, [rcx+10h]
0x180004282  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004289  mov     [rsp+58h+var_28], 0D08h
0x180004291  lea     r9, aStatus; "Status"
0x180004298  mov     [rsp+58h+var_30], rax
0x18000429d  mov     [rsp+58h+var_38], 80090027h
0x1800042a5  call    WPP_SF_sDsd
0x1800042aa  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800042b1  lock xadd [r14+8], rax
0x1800042b7  cmp     rax, 1
0x1800042bb  jz      loc_1800043CD
0x1800042c1  mov     r14, [rsp+58h+arg_18]
0x1800042c6  mov     eax, ebx
0x1800042c8  add     rsp, 40h
0x1800042cc  pop     r15
0x1800042ce  pop     rdi
0x1800042cf  pop     rbx
0x1800042d0  retn
0x1800042d1  mov     r8, [rsp+58h+arg_30]
0x1800042d9  test    r8, r8
0x1800042dc  jz      loc_180004434
0x1800042e2  mov     rcx, [r14+20h]
0x1800042e6  mov     edx, [rsp+58h+arg_38]
0x1800042ed  mov     r9, [rsp+58h+arg_20]
0x1800042f5  mov     [rsp+58h+var_28], edx
0x1800042f9  mov     edx, [rsp+58h+arg_28]
0x180004300  mov     rax, [rcx+50h]
0x180004304  mov     rcx, [rcx+128h]
0x18000430b  mov     [rsp+58h+var_30], r8
0x180004310  mov     r8, r15
0x180004313  mov     [rsp+58h+var_38], edx
0x180004317  mov     rdx, [r14+28h]
0x18000431b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004320  mov     ebx, eax
0x180004322  test    eax, eax
0x180004324  jz      short loc_1800042AA
0x180004326  mov     rcx, cs:WPP_GLOBAL_Control
0x18000432d  lea     rax, WPP_GLOBAL_Control
0x180004334  cmp     rcx, rax
0x180004337  jz      short loc_180004367
0x180004339  test    byte ptr [rcx+1Ch], 1
0x18000433d  jz      short loc_180004367
0x18000433f  mov     rcx, [rcx+10h]
0x180004343  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000434a  mov     [rsp+58h+var_28], 0D22h
0x180004352  lea     r9, aStatus; "Status"
0x180004359  mov     [rsp+58h+var_30], rax
0x18000435e  mov     [rsp+58h+var_38], ebx
0x180004362  call    WPP_SF_sDsd
0x180004367  mov     ecx, ebx
0x180004369  call    NormalizeNteStatus
0x18000436e  mov     ebx, eax
0x180004370  jmp     loc_1800042AA
0x180004375  mov     rcx, cs:WPP_GLOBAL_Control
0x18000437c  lea     rax, WPP_GLOBAL_Control
0x180004383  cmp     rcx, rax
0x180004386  jz      short loc_1800043BA
0x180004388  test    byte ptr [rcx+1Ch], 1
0x18000438c  jz      short loc_1800043BA
0x18000438e  mov     rcx, [rcx+10h]
0x180004392  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004399  mov     [rsp+58h+var_28], 0CFAh
0x1800043a1  lea     r9, aStatus; "Status"
0x1800043a8  mov     [rsp+58h+var_30], rax
0x1800043ad  mov     [rsp+58h+var_38], 80090026h
0x1800043b5  call    WPP_SF_sDsd
0x1800043ba  mov     r14, [rsp+58h+arg_18]
0x1800043bf  mov     eax, 80090026h
0x1800043c4  add     rsp, 40h
0x1800043c8  pop     r15
0x1800043ca  pop     rdi
0x1800043cb  pop     rbx
0x1800043cc  retn
0x1800043cd  mov     rcx, r14; P
0x1800043d0  call    SrvFreeKey
0x1800043d5  mov     edi, eax
0x1800043d7  test    eax, eax
0x1800043d9  jns     loc_1800042C1
0x1800043df  mov     r9d, 2E4h
0x1800043e5  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800043ec  lea     rdx, aStatus; "Status"
0x1800043f3  mov     ecx, eax
0x1800043f5  call    DebugTraceError
0x1800043fa  test    ebx, ebx
0x1800043fc  cmovns  ebx, edi
0x1800043ff  jmp     loc_1800042C1
0x180004404  mov     r9d, 0CF1h
0x18000440a  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004411  lea     rdx, aStatus; "Status"
0x180004418  mov     ecx, 80090026h
0x18000441d  call    DebugTraceError
0x180004422  mov     eax, 80090026h
0x180004427  jmp     loc_1800042C8
0x18000442c  mov     r9d, 0D01h
0x180004432  jmp     short loc_18000443A
0x180004434  mov     r9d, 0D0Fh
0x18000443a  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004441  mov     ecx, 80090027h
0x180004446  lea     rdx, aStatus; "Status"
0x18000444d  mov     ebx, 80090027h
0x180004452  call    DebugTraceError
0x180004457  jmp     loc_1800042AA
```
