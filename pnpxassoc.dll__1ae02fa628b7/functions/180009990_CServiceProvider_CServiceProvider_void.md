# CServiceProvider::~CServiceProvider(void)

- ea: `0x180009990`
- end: `0x180009ab7`
- name: `??1CServiceProvider@@UEAA@XZ`
- size: `295`
- prototype: `void __fastcall(CServiceProvider *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180005470`
- `0x180005510`
- `0x1800055d0`

## callees

- `0x180009990`
- `0x18000bce4`
- `0x18000d09c`
- `0x18000d16c`
- `0x180014010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180009a3c`
- `KERNEL32!LeaveCriticalSection` at `0x180009a3c`
- `KERNEL32!EnterCriticalSection` at `0x1800099e4`
- `KERNEL32!EnterCriticalSection` at `0x1800099e4`
- `KERNEL32!DeleteCriticalSection` at `0x180009aa6`
- `KERNEL32!DeleteCriticalSection` at `0x180009aa6`

## pseudocode

```c
void __fastcall CServiceProvider::~CServiceProvider(CServiceProvider *this)
{
  _QWORD *v2; // rcx
  CPnpNotification *v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 26) )
  {
    EnterCriticalSection(&g_csGlobalLock);
    v3 = g_pPnpNotification;
    if ( g_pPnpNotification )
    {
      if ( *((_WORD *)this + 54) )
        CPnpNotification::Unsubscribe(g_pPnpNotification, (wchar_t *)this + 54);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&g_dwClientCount, 0xFFFFFFFF) == 1 )
        CPnpNotification::Uninitialize(v3);
      (*(void (__fastcall **)(CPnpNotification *))(*(_QWORD *)g_pPnpNotification + 16LL))(g_pPnpNotification);
      *((_DWORD *)this + 26) = 0;
    }
    LeaveCriticalSection(&g_csGlobalLock);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 4u )
    WPP_SF_sq(v2[2], 13, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  v4 = *((_QWORD *)this + 12);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_QWORD *)this + 11);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( *((_BYTE *)this + 80) )
  {
    *((_BYTE *)this + 80) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
  }
}

```

## disassembly

```asm
0x180009990  mov     [rsp+arg_0], rbx
0x180009995  push    rsi
0x180009996  sub     rsp, 30h
0x18000999a  mov     rbx, rcx
0x18000999d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099a4  lea     rsi, WPP_GLOBAL_Control
0x1800099ab  cmp     rcx, rsi
0x1800099ae  jz      short loc_1800099D7
0x1800099b0  cmp     byte ptr [rcx+19h], 4
0x1800099b4  jb      short loc_1800099D7
0x1800099b6  mov     rcx, [rcx+10h]
0x1800099ba  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x1800099c1  mov     edx, 0Ch
0x1800099c6  mov     [rsp+38h+var_18], rbx
0x1800099cb  call    WPP_SF_sq
0x1800099d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099d7  cmp     dword ptr [rbx+68h], 0
0x1800099db  jz      short loc_180009A49
0x1800099dd  lea     rcx, ?g_csGlobalLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800099e4  call    cs:__imp_EnterCriticalSection
0x1800099ea  mov     rcx, cs:?g_pPnpNotification@@3PEAVCPnpNotification@@EA; this
0x1800099f1  test    rcx, rcx
0x1800099f4  jz      short loc_180009A35
0x1800099f6  lea     rdx, [rbx+6Ch]; String1
0x1800099fa  xor     eax, eax
0x1800099fc  cmp     ax, [rdx]
0x1800099ff  jz      short loc_180009A06
0x180009a01  call    ?Unsubscribe@CPnpNotification@@QEAAJPEBG@Z; CPnpNotification::Unsubscribe(ushort const *)
0x180009a06  or      eax, 0FFFFFFFFh
0x180009a09  lock xadd cs:?g_dwClientCount@@3KA, eax; ulong g_dwClientCount
0x180009a11  cmp     eax, 1
0x180009a14  jnz     short loc_180009A1B
0x180009a16  call    ?Uninitialize@CPnpNotification@@QEAAXXZ; CPnpNotification::Uninitialize(void)
0x180009a1b  mov     rcx, cs:?g_pPnpNotification@@3PEAVCPnpNotification@@EA; CPnpNotification * g_pPnpNotification
0x180009a22  mov     rax, [rcx]
0x180009a25  mov     rax, [rax+10h]
0x180009a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a2e  mov     dword ptr [rbx+68h], 0
0x180009a35  lea     rcx, ?g_csGlobalLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180009a3c  call    cs:__imp_LeaveCriticalSection
0x180009a42  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a49  cmp     rcx, rsi
0x180009a4c  jz      short loc_180009A6E
0x180009a4e  cmp     byte ptr [rcx+19h], 4
0x180009a52  jb      short loc_180009A6E
0x180009a54  mov     rcx, [rcx+10h]
0x180009a58  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x180009a5f  mov     edx, 0Dh
0x180009a64  mov     [rsp+38h+var_18], rbx
0x180009a69  call    WPP_SF_sq
0x180009a6e  mov     rcx, [rbx+60h]
0x180009a72  test    rcx, rcx
0x180009a75  jz      short loc_180009A83
0x180009a77  mov     rax, [rcx]
0x180009a7a  mov     rax, [rax+10h]
0x180009a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a83  mov     rcx, [rbx+58h]
0x180009a87  test    rcx, rcx
0x180009a8a  jz      short loc_180009A98
0x180009a8c  mov     rax, [rcx]
0x180009a8f  mov     rax, [rax+10h]
0x180009a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a98  lea     rcx, [rbx+28h]; lpCriticalSection
0x180009a9c  cmp     byte ptr [rcx+28h], 0
0x180009aa0  jz      short loc_180009AAC
0x180009aa2  mov     byte ptr [rcx+28h], 0
0x180009aa6  call    cs:__imp_DeleteCriticalSection
0x180009aac  mov     rbx, [rsp+38h+arg_0]
0x180009ab1  add     rsp, 30h
0x180009ab5  pop     rsi
0x180009ab6  retn
```
