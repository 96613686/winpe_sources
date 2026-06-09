# DevicePresenceChallengeOnCompleteStub(void *,long)

- ea: `0x180022434`
- end: `0x18002261e`
- name: `?DevicePresenceChallengeOnCompleteStub@@YAJPEAXJ@Z`
- size: `490`
- prototype: `__int64 __fastcall(char *, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001ac04`
- `0x18001b24c`
- `0x18005d350`
- `0x1800649a0`

## callees

- `0x180007500`
- `0x180022434`
- `0x18002394c`
- `0x180025eb0`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022457`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022457`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022478`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800224de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022570`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022478`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800224de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022570`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180022565`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180022565`

## pseudocode

```c
__int64 __fastcall DevicePresenceChallengeOnCompleteStub(char *a1, int a2)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  unsigned int v4; // edi
  int v5; // edx
  int v6; // r8d
  int v7; // edx
  int v8; // r8d
  RPC_STATUS v9; // ebp
  int v10; // edx
  int v11; // r8d
  int Reply; // [rsp+68h] [rbp+10h] BYREF

  Reply = a2;
  v3 = (struct _RTL_CRITICAL_SECTION *)(a1 + 232);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 232));
  if ( *((_DWORD *)a1 + 55) )
  {
    v4 = -2147416294;
    *((_DWORD *)a1 + 55) = 0;
    LeaveCriticalSection(v3);
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v5,
        v6,
        36,
        &WPP_f2e0a728fe33339f22cf999e8124d653_Traceguids,
        *((_QWORD *)a1 + 9),
        26);
LABEL_19:
    (*(void (__fastcall **)(char *))(*(_QWORD *)a1 + 16LL))(a1);
    return v4;
  }
  if ( !*((_DWORD *)a1 + 56) )
  {
    v4 = 0;
    if ( *((_DWORD *)a1 + 72) )
    {
      CChallengeContext::UnsubscribeForNotifications(*((struct _RPC_ASYNC_STATE **)a1 + 6));
      (*(void (__fastcall **)(char *))(*(_QWORD *)a1 + 16LL))(a1);
    }
    *((_DWORD *)a1 + 56) = 1;
    v9 = RpcAsyncCompleteCall(*((PRPC_ASYNC_STATE *)a1 + 6), &Reply);
    LeaveCriticalSection(v3);
    if ( v9 && v9 != 1818 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v10,
          v11,
          38,
          &WPP_f2e0a728fe33339f22cf999e8124d653_Traceguids,
          v9);
      if ( v9 < 0 )
        v4 = v9;
      else
        v4 = (unsigned __int16)v9 | 0x80010000;
    }
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v10,
        v11,
        39,
        &WPP_f2e0a728fe33339f22cf999e8124d653_Traceguids,
        *((_QWORD *)a1 + 9),
        v4);
    goto LABEL_19;
  }
  v4 = -2147418113;
  LeaveCriticalSection(v3);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v7,
      v8,
      37,
      &WPP_f2e0a728fe33339f22cf999e8124d653_Traceguids,
      *((_QWORD *)a1 + 9),
      255);
  return v4;
}

```

## disassembly

```asm
0x180022434  mov     [rsp+arg_0], rbx
0x180022439  mov     [rsp+arg_10], rbp
0x18002243e  mov     [rsp+Reply], edx
0x180022442  push    rsi
0x180022443  push    rdi
0x180022444  push    r14
0x180022446  sub     rsp, 40h
0x18002244a  mov     rbx, rcx
0x18002244d  lea     rsi, [rcx+0E8h]
0x180022454  mov     rcx, rsi; lpCriticalSection
0x180022457  call    cs:__imp_EnterCriticalSection
0x18002245d  cmp     dword ptr [rbx+0DCh], 0
0x180022464  jz      short loc_1800224CD
0x180022466  mov     edi, 8001071Ah
0x18002246b  mov     dword ptr [rbx+0DCh], 0
0x180022475  mov     rcx, rsi; lpCriticalSection
0x180022478  call    cs:__imp_LeaveCriticalSection
0x18002247e  lea     rsi, WPP_RECORDER_INITIALIZED
0x180022485  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x18002248c  jz      short loc_1800224C1
0x18002248e  mov     r9d, 24h ; '$'; int
0x180022494  mov     dword ptr [rsp+58h+var_28], 8001071Ah; char
0x18002249c  mov     rax, [rbx+48h]
0x1800224a0  mov     qword ptr [rsp+58h+var_30], rax; __int64
0x1800224a5  lea     r14, WPP_f2e0a728fe33339f22cf999e8124d653_Traceguids
0x1800224ac  mov     [rsp+58h+MessageGuid], r14; MessageGuid
0x1800224b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800224b8  mov     rcx, [rcx+28h]; int
0x1800224bc  call    WPP_RECORDER_SF_Sd
0x1800224c1  mov     rax, [rbx]
0x1800224c4  mov     rax, [rax+10h]
0x1800224c8  jmp     loc_180022601
0x1800224cd  cmp     dword ptr [rbx+0E0h], 0
0x1800224d4  jz      short loc_180022530
0x1800224d6  mov     edi, 8000FFFFh
0x1800224db  mov     rcx, rsi; lpCriticalSection
0x1800224de  call    cs:__imp_LeaveCriticalSection
0x1800224e4  lea     rsi, WPP_RECORDER_INITIALIZED
0x1800224eb  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1800224f2  jz      loc_180022609
0x1800224f8  mov     r9d, 25h ; '%'; int
0x1800224fe  mov     dword ptr [rsp+58h+var_28], 8000FFFFh; char
0x180022506  mov     rax, [rbx+48h]
0x18002250a  mov     qword ptr [rsp+58h+var_30], rax; __int64
0x18002250f  lea     r14, WPP_f2e0a728fe33339f22cf999e8124d653_Traceguids
0x180022516  mov     [rsp+58h+MessageGuid], r14; MessageGuid
0x18002251b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022522  mov     rcx, [rcx+28h]; int
0x180022526  call    WPP_RECORDER_SF_Sd
0x18002252b  jmp     loc_180022609
0x180022530  xor     edi, edi
0x180022532  cmp     [rbx+120h], edi
0x180022538  jz      short loc_180022552
0x18002253a  mov     rcx, [rbx+30h]; struct _RPC_ASYNC_STATE *
0x18002253e  call    ?UnsubscribeForNotifications@CChallengeContext@@SAXPEAU_RPC_ASYNC_STATE@@@Z; CChallengeContext::UnsubscribeForNotifications(_RPC_ASYNC_STATE *)
0x180022543  mov     rax, [rbx]
0x180022546  mov     rcx, rbx
0x180022549  mov     rax, [rax+10h]
0x18002254d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022552  mov     dword ptr [rbx+0E0h], 1
0x18002255c  lea     rdx, [rsp+58h+Reply]; Reply
0x180022561  mov     rcx, [rbx+30h]; pAsync
0x180022565  call    cs:__imp_RpcAsyncCompleteCall
0x18002256b  mov     ebp, eax
0x18002256d  mov     rcx, rsi; lpCriticalSection
0x180022570  call    cs:__imp_LeaveCriticalSection
0x180022576  lea     rsi, WPP_RECORDER_INITIALIZED
0x18002257d  lea     r14, WPP_f2e0a728fe33339f22cf999e8124d653_Traceguids
0x180022584  test    ebp, ebp
0x180022586  jz      short loc_1800225C9
0x180022588  cmp     ebp, 71Ah
0x18002258e  jz      short loc_1800225C9
0x180022590  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180022597  jz      short loc_1800225B8
0x180022599  mov     r9d, 26h ; '&'; int
0x18002259f  mov     dword ptr [rsp+58h+var_30], ebp; char
0x1800225a3  mov     [rsp+58h+MessageGuid], r14; MessageGuid
0x1800225a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800225af  mov     rcx, [rcx+28h]; int
0x1800225b3  call    WPP_RECORDER_SF_D
0x1800225b8  test    ebp, ebp
0x1800225ba  js      short loc_1800225C7
0x1800225bc  movzx   edi, bp
0x1800225bf  or      edi, 80010000h
0x1800225c5  jmp     short loc_1800225C9
0x1800225c7  mov     edi, ebp
0x1800225c9  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1800225d0  jz      short loc_1800225FA
0x1800225d2  mov     r9d, 27h ; '''; int
0x1800225d8  mov     dword ptr [rsp+58h+var_28], edi; char
0x1800225dc  mov     rax, [rbx+48h]
0x1800225e0  mov     qword ptr [rsp+58h+var_30], rax; __int64
0x1800225e5  mov     [rsp+58h+MessageGuid], r14; MessageGuid
0x1800225ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800225f1  mov     rcx, [rcx+28h]; int
0x1800225f5  call    WPP_RECORDER_SF_Sd
0x1800225fa  mov     rcx, [rbx]
0x1800225fd  mov     rax, [rcx+10h]
0x180022601  mov     rcx, rbx
0x180022604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022609  mov     eax, edi
0x18002260b  mov     rbx, [rsp+58h+arg_0]
0x180022610  mov     rbp, [rsp+58h+arg_10]
0x180022615  add     rsp, 40h
0x180022619  pop     r14
0x18002261b  pop     rdi
0x18002261c  pop     rsi
0x18002261d  retn
```
