# SrvCryptFreeKey

- ea: `0x1800023b0`
- end: `0x18000259c`
- name: `SrvCryptFreeKey`
- size: `492`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800023b0`
- `0x180003cf0`
- `0x180004470`
- `0x18000a520`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x1800023d9`
- `ntdll!RtlEnterCriticalSection` at `0x180002434`
- `ntdll!RtlEnterCriticalSection` at `0x1800023d9`
- `ntdll!RtlEnterCriticalSection` at `0x180002434`
- `ntdll!RtlLeaveCriticalSection` at `0x180002413`
- `ntdll!RtlLeaveCriticalSection` at `0x18000247a`
- `ntdll!RtlLeaveCriticalSection` at `0x180002413`
- `ntdll!RtlLeaveCriticalSection` at `0x18000247a`

## string_xrefs

- `0x1800024f5`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180002536`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180002573`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x1800024af`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvutils.c`
- `0x1800024da`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvutils.c`

## pseudocode

```c
__int64 __fastcall SrvCryptFreeKey(__int64 a1, int a2, __int64 a3)
{
  volatile signed __int64 *v5; // rbx
  int v6; // r14d
  _QWORD *v7; // rax
  __int64 v8; // rdx
  volatile signed __int64 **v9; // rcx
  unsigned int v10; // ebx
  int v12; // eax
  int v13; // eax

  if ( a1 )
  {
    v5 = 0;
    v6 = 0;
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 104));
    v7 = *(_QWORD **)(a1 + 144);
    while ( v7 != (_QWORD *)(a1 + 144) )
    {
      v5 = v7 - 2;
      v7 = (_QWORD *)*v7;
      if ( *((_QWORD *)v5 + 6) == a3 )
      {
        if ( *(_DWORD *)v5 == 1145324615 )
        {
          *(_DWORD *)v5 = 1145307143;
          v6 = 1;
        }
        break;
      }
    }
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 104));
    if ( !v6 )
      v5 = 0;
    if ( v5 )
    {
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 104));
      v8 = *((_QWORD *)v5 + 2);
      if ( *(volatile signed __int64 **)(v8 + 8) != v5 + 2
        || (v9 = (volatile signed __int64 **)*((_QWORD *)v5 + 3), *v9 != v5 + 2) )
      {
        __fastfail(3u);
      }
      *v9 = (volatile signed __int64 *)v8;
      *(_QWORD *)(v8 + 8) = v9;
      if ( _InterlockedExchangeAdd64(v5 + 1, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
      {
        v12 = SrvFreeKey((PVOID)v5);
        if ( v12 < 0 )
          DebugTraceError(
            (unsigned int)v12,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvutils.c",
            740);
      }
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 104));
      if ( _InterlockedExchangeAdd64(v5 + 1, 0xFFFFFFFFFFFFFFFFuLL) == 1
        && (v13 = SrvFreeKey((PVOID)v5), v10 = v13, v13 < 0) )
      {
        DebugTraceError(
          (unsigned int)v13,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvutils.c",
          740);
        DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 1942);
      }
      else
      {
        return 0;
      }
    }
    else
    {
      v10 = -2146893786;
      DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 1917);
    }
    return v10;
  }
  v10 = -2146893786;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return v10;
  WPP_SF_sDsd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    a2,
    (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
    (unsigned int)"Status",
    38,
    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
    110);
  return 2148073510LL;
}

```

## disassembly

```asm
0x1800023b0  mov     [rsp+arg_10], rbx
0x1800023b5  push    rbp
0x1800023b6  push    rsi
0x1800023b7  push    rdi
0x1800023b8  sub     rsp, 40h
0x1800023bc  mov     rdi, r8
0x1800023bf  mov     rsi, rcx
0x1800023c2  test    rcx, rcx
0x1800023c5  jz      loc_18000250C
0x1800023cb  mov     [rsp+58h+arg_8], r14
0x1800023d0  xor     ebx, ebx
0x1800023d2  xor     r14d, r14d
0x1800023d5  add     rcx, 68h ; 'h'; CriticalSection
0x1800023d9  call    cs:__imp_RtlEnterCriticalSection
0x1800023df  lea     rcx, [rsi+90h]
0x1800023e6  mov     rax, [rcx]
0x1800023e9  cmp     rax, rcx
0x1800023ec  jz      short loc_18000240F
0x1800023ee  lea     rbx, [rax-10h]
0x1800023f2  mov     rax, [rax]
0x1800023f5  cmp     [rbx+30h], rdi
0x1800023f9  jnz     short loc_1800023E9
0x1800023fb  cmp     dword ptr [rbx], 44444447h
0x180002401  jnz     short loc_18000240F
0x180002403  mov     dword ptr [rbx], 44440007h
0x180002409  mov     r14d, 1
0x18000240f  lea     rcx, [rsi+68h]; CriticalSection
0x180002413  call    cs:__imp_RtlLeaveCriticalSection
0x180002419  xor     eax, eax
0x18000241b  test    r14d, r14d
0x18000241e  mov     r14, [rsp+58h+arg_8]
0x180002423  cmovz   rbx, rax
0x180002427  test    rbx, rbx
0x18000242a  jz      loc_18000256D
0x180002430  lea     rcx, [rsi+68h]; CriticalSection
0x180002434  call    cs:__imp_RtlEnterCriticalSection
0x18000243a  mov     rdx, [rbx+10h]
0x18000243e  lea     rax, [rbx+10h]
0x180002442  cmp     [rdx+8], rax
0x180002446  jnz     loc_180002595
0x18000244c  mov     rcx, [rax+8]
0x180002450  cmp     [rcx], rax
0x180002453  jnz     loc_180002595
0x180002459  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180002460  mov     [rcx], rdx
0x180002463  mov     rax, rdi
0x180002466  mov     [rdx+8], rcx
0x18000246a  lock xadd [rbx+8], rax
0x180002470  cmp     rax, 1
0x180002474  jz      short loc_18000249D
0x180002476  lea     rcx, [rsi+68h]; CriticalSection
0x18000247a  call    cs:__imp_RtlLeaveCriticalSection
0x180002480  lock xadd [rbx+8], rdi
0x180002486  cmp     rdi, 1
0x18000248a  jz      short loc_1800024C6
0x18000248c  xor     ebx, ebx
0x18000248e  mov     eax, ebx
0x180002490  mov     rbx, [rsp+58h+arg_10]
0x180002495  add     rsp, 40h
0x180002499  pop     rdi
0x18000249a  pop     rsi
0x18000249b  pop     rbp
0x18000249c  retn
0x18000249d  mov     rcx, rbx; P
0x1800024a0  call    SrvFreeKey
0x1800024a5  test    eax, eax
0x1800024a7  jns     short loc_180002476
0x1800024a9  mov     r9d, 2E4h
0x1800024af  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800024b6  lea     rdx, aStatus; "Status"
0x1800024bd  mov     ecx, eax
0x1800024bf  call    DebugTraceError
0x1800024c4  jmp     short loc_180002476
0x1800024c6  mov     rcx, rbx; P
0x1800024c9  call    SrvFreeKey
0x1800024ce  mov     ebx, eax
0x1800024d0  test    eax, eax
0x1800024d2  jns     short loc_18000248C
0x1800024d4  mov     r9d, 2E4h
0x1800024da  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800024e1  lea     rdx, aStatus; "Status"
0x1800024e8  mov     ecx, eax
0x1800024ea  call    DebugTraceError
0x1800024ef  mov     r9d, 796h
0x1800024f5  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800024fc  lea     rdx, aStatus; "Status"
0x180002503  mov     ecx, ebx
0x180002505  call    DebugTraceError
0x18000250a  jmp     short loc_18000248E
0x18000250c  mov     ebx, 80090026h
0x180002511  mov     rcx, cs:WPP_GLOBAL_Control
0x180002518  lea     rax, WPP_GLOBAL_Control
0x18000251f  cmp     rcx, rax
0x180002522  jz      loc_18000248E
0x180002528  test    byte ptr [rcx+1Ch], 1
0x18000252c  jz      loc_18000248E
0x180002532  mov     rcx, [rcx+10h]
0x180002536  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000253d  mov     [rsp+58h+var_28], 76Eh
0x180002545  lea     r9, aStatus; "Status"
0x18000254c  mov     [rsp+58h+var_30], r8
0x180002551  mov     [rsp+58h+var_38], 80090026h
0x180002559  call    WPP_SF_sDsd
0x18000255e  mov     eax, ebx
0x180002560  mov     rbx, [rsp+58h+arg_10]
0x180002565  add     rsp, 40h
0x180002569  pop     rdi
0x18000256a  pop     rsi
0x18000256b  pop     rbp
0x18000256c  retn
0x18000256d  mov     r9d, 77Dh
0x180002573  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000257a  lea     rdx, aStatus; "Status"
0x180002581  mov     ecx, 80090026h
0x180002586  mov     ebx, 80090026h
0x18000258b  call    DebugTraceError
0x180002590  jmp     loc_18000248E
0x180002595  mov     ecx, 3
0x18000259a  int     29h; Win8: RtlFailFast(ecx)
```
