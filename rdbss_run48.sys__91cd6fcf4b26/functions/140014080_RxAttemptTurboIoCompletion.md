# RxAttemptTurboIoCompletion

- ea: `0x140014080`
- end: `0x14001452d`
- name: `RxAttemptTurboIoCompletion`
- size: `1197`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x14000a740`
- `0x14000f200`
- `0x140014080`
- `0x140016e70`
- `0x140017370`
- `0x14001ff7c`
- `0x140020104`
- `0x140020190`
- `0x14002540c`
- `0x140025d00`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001432c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001432c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400142e3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400142e3`

## pseudocode

```c
__int64 __fastcall RxAttemptTurboIoCompletion(__int64 a1, void (__fastcall *a2)(__int64), __int64 a3)
{
  int v3; // edi
  __int64 v5; // r14
  void (__fastcall *v6)(__int64); // rbp
  __int64 v8; // r15
  __int64 v9; // rcx
  void (__fastcall *v10)(__int64, void (__fastcall *)(__int64)); // rax
  __int64 v11; // rdi
  __int64 v12; // rcx
  void (__fastcall *v13)(__int64); // rax
  __int64 v14; // rdi
  KIRQL v15; // al
  _QWORD *v16; // rdx
  KIRQL v17; // r8
  _QWORD *v18; // rcx
  __int64 v19; // rax
  _QWORD *v20; // rdx
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rtt
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rtt
  unsigned __int64 v25; // rax

  v3 = *(_DWORD *)(a1 + 176);
  v5 = *(_QWORD *)(a1 + 40);
  v6 = a2;
  if ( v3 < 0
    || (unsigned __int8)(*(_BYTE *)(a1 + 32) - 3) > 1u
    || !*(_QWORD *)(*(_QWORD *)(a1 + 552) + 328LL)
    || (*(_DWORD *)(v5 + 16) & 1) == 0
    || (*(_DWORD *)(a1 + 536) & 7) != 0
    || (*(_BYTE *)(a1 + 522) & 9) != 8
    || (*(_DWORD *)(a1 + 120) & 0x202) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qdddddddd(
        WPP_GLOBAL_Control->AttachedDevice,
        (*(_WORD *)(a1 + 522) & 1) == 0,
        (*(_DWORD *)(a1 + 536) & 7) == 0,
        a1,
        *(_DWORD *)(v5 + 16) & 1,
        (*(unsigned __int16 *)(a1 + 522) >> 3) & 1,
        (*(_DWORD *)(a1 + 120) & 0x202) == 0,
        (*(_WORD *)(a1 + 522) & 1) == 0,
        (*(_DWORD *)(a1 + 536) & 7) == 0,
        *(_QWORD *)(*(_QWORD *)(a1 + 552) + 328LL) != 0,
        (unsigned __int8)(*(_BYTE *)(a1 + 32) - 3) <= 1u,
        v3 >= 0);
    }
    return 0;
  }
  v8 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 48LL);
  v9 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 352LL);
  if ( v9 )
  {
    v10 = *(void (__fastcall **)(__int64, void (__fastcall *)(__int64)))(v9 + 672);
    if ( v10 )
    {
      LOBYTE(a2) = 41;
      v10(a1, a2);
    }
  }
  v11 = *(_QWORD *)(*(_QWORD *)(a1 + 552) + 328LL);
  if ( !v11 || *(_QWORD *)v11 != v8 || !*(_BYTE *)(v11 + 24) || *(_DWORD *)(v11 + 28) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qddqq(
        WPP_GLOBAL_Control->AttachedDevice,
        *(unsigned __int8 *)(v11 + 24),
        a3,
        a1,
        *(unsigned __int8 *)(v11 + 24),
        *(_DWORD *)(v11 + 28),
        v8,
        *(_QWORD *)v11);
    }
    return 0;
  }
  if ( *(_DWORD *)(*(_QWORD *)(v11 + 8LL * *(unsigned __int16 *)(a1 + 440) + 32) + 8LL) > 0x200u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 30, &WPP_d414fc76462934e262300deaf9706329_Traceguids);
    }
    return 0;
  }
  if ( !*(_QWORD *)(a1 + 880) )
    __int2c();
  if ( !(unsigned __int8)RfsAcquireRundownProtectionEx() )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 28, &WPP_d414fc76462934e262300deaf9706329_Traceguids, a1);
    }
    return 0;
  }
  v12 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 352LL);
  if ( v12 )
  {
    v13 = *(void (__fastcall **)(__int64))(v12 + 680);
    if ( v13 )
      v13(a1);
  }
  RxDetachIrpFromRxContext(a1, v5);
  v6(a3);
  *(_QWORD *)(a1 + 544) = 0;
  *(_QWORD *)(a1 + 560) = 0;
  *(_QWORD *)(a1 + 568) = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qhDqDiqi(
      WPP_GLOBAL_Control->AttachedDevice,
      (MEMORY[0xFFFFF78000000008] - *(_QWORD *)(a1 + 24)) / 0x2710uLL,
      *(unsigned __int8 *)(a1 + 33),
      v5,
      *(unsigned __int8 *)(a1 + 32),
      *(unsigned __int8 *)(a1 + 33),
      a1,
      *(_DWORD *)(a1 + 176),
      *(_QWORD *)(a1 + 184),
      v8,
      (MEMORY[0xFFFFF78000000008] - *(_QWORD *)(a1 + 24)) / 0x2710uLL);
  }
  *(_QWORD *)(v5 + 56) = *(_QWORD *)(a1 + 184);
  *(_DWORD *)(v5 + 48) = *(_DWORD *)(a1 + 176);
  v14 = *(_QWORD *)(v11 + 8LL * *(unsigned __int16 *)(a1 + 440) + 32);
  v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v14);
  v16 = (_QWORD *)(a1 + 368);
  v17 = v15;
  if ( *(_BYTE *)(a1 + 32) == 3 )
  {
    v18 = *(_QWORD **)(v14 + 24);
    v19 = v14 + 16;
    if ( *v18 == v14 + 16 )
      goto LABEL_32;
LABEL_41:
    __fastfail(3u);
  }
  v18 = *(_QWORD **)(v14 + 40);
  v19 = v14 + 32;
  if ( *v18 != v14 + 32 )
    goto LABEL_41;
LABEL_32:
  *v16 = v19;
  *(_QWORD *)(a1 + 376) = v18;
  *v18 = v16;
  *(_QWORD *)(v19 + 8) = v16;
  ++*(_DWORD *)(v14 + 8);
  *(_DWORD *)(a1 + 120) |= 0x80000u;
  KeReleaseSpinLock((PKSPIN_LOCK)v14, v17);
  v20 = *(_QWORD **)(a1 + 880);
  _m_prefetchw(v20);
  v21 = *v20 & 0xFFFFFFFFFFFFFFFEuLL;
  if ( v21 < 2 || (v22 = *v20 & 0xFFFFFFFFFFFFFFFEuLL, v22 != _InterlockedCompareExchange64(v20, v21 - 2, v21)) )
  {
    _m_prefetchw(v20);
    v23 = *v20;
    while ( (v23 & 1) == 0 )
    {
      if ( v23 < 2 )
        __int2c();
      v24 = v23;
      v23 = _InterlockedCompareExchange64(v20, v23 - 2, v23);
      if ( v24 == v23 )
        return v5;
    }
    v25 = v23 & 0xFFFFFFFFFFFFFFFEuLL;
    if ( !v25 )
      __int2c();
    RfsDecrementRundownWaitBlockCount(v25, v20);
  }
  return v5;
}

```

## disassembly

```asm
0x140014080  push    rbx
0x140014082  push    rbp
0x140014083  push    rsi
0x140014084  push    rdi
0x140014085  push    r14
0x140014087  push    r15
0x140014089  sub     rsp, 68h
0x14001408d  mov     edi, [rcx+0B0h]
0x140014093  mov     rsi, r8
0x140014096  mov     r14, [rcx+28h]
0x14001409a  mov     rbp, rdx
0x14001409d  mov     rbx, rcx
0x1400140a0  test    edi, edi
0x1400140a2  js      loc_140014459
0x1400140a8  movzx   eax, byte ptr [rcx+20h]
0x1400140ac  sub     al, 3
0x1400140ae  cmp     al, 1
0x1400140b0  ja      loc_140014459
0x1400140b6  mov     rax, [rcx+228h]
0x1400140bd  cmp     qword ptr [rax+148h], 0
0x1400140c5  jz      loc_140014459
0x1400140cb  mov     eax, [r14+10h]
0x1400140cf  test    al, 1
0x1400140d1  jz      loc_140014459
0x1400140d7  mov     eax, [rcx+218h]
0x1400140dd  test    al, 7
0x1400140df  jnz     loc_140014459
0x1400140e5  movzx   eax, byte ptr [rcx+20Ah]
0x1400140ec  and     al, 9
0x1400140ee  cmp     al, 8
0x1400140f0  jnz     loc_140014459
0x1400140f6  test    dword ptr [rcx+78h], 202h
0x1400140fd  jnz     loc_140014459
0x140014103  mov     rax, [rcx+30h]
0x140014107  mov     r15, [rax+30h]
0x14001410b  mov     rax, [rcx+50h]
0x14001410f  mov     rcx, [rax+160h]
0x140014116  test    rcx, rcx
0x140014119  jz      short loc_140014131
0x14001411b  mov     rax, [rcx+2A0h]
0x140014122  test    rax, rax
0x140014125  jz      short loc_140014131
0x140014127  mov     dl, 29h ; ')'
0x140014129  mov     rcx, rbx
0x14001412c  call    _guard_dispatch_icall
0x140014131  mov     rax, [rbx+228h]
0x140014138  mov     rdi, [rax+148h]
0x14001413f  test    rdi, rdi
0x140014142  jz      loc_1400143FE
0x140014148  cmp     [rdi], r15
0x14001414b  jnz     loc_1400143FE
0x140014151  cmp     byte ptr [rdi+18h], 0
0x140014155  jz      loc_1400143FE
0x14001415b  cmp     dword ptr [rdi+1Ch], 0
0x14001415f  jnz     loc_1400143FE
0x140014165  movzx   eax, word ptr [rbx+1B8h]
0x14001416c  mov     rcx, [rdi+rax*8+20h]
0x140014171  mov     r8d, [rcx+8]
0x140014175  cmp     r8d, 200h
0x14001417c  ja      loc_1400143AE
0x140014182  mov     rcx, [rbx+370h]
0x140014189  test    rcx, rcx
0x14001418c  jnz     short loc_140014190
0x14001418e  int     2Ch; Windows NT - assertion failure
0x140014190  call    RfsAcquireRundownProtectionEx
0x140014195  test    al, al
0x140014197  jnz     short loc_1400141E4
0x140014199  mov     rcx, cs:WPP_GLOBAL_Control
0x1400141a0  lea     rax, WPP_GLOBAL_Control
0x1400141a7  cmp     rcx, rax
0x1400141aa  jz      loc_14001451D
0x1400141b0  test    dword ptr [rcx+2Ch], 4000h
0x1400141b7  jz      loc_14001451D
0x1400141bd  cmp     byte ptr [rcx+29h], 1
0x1400141c1  jb      loc_14001451D
0x1400141c7  mov     rcx, [rcx+18h]
0x1400141cb  lea     r8, WPP_d414fc76462934e262300deaf9706329_Traceguids
0x1400141d2  mov     edx, 1Ch
0x1400141d7  mov     r9, rbx
0x1400141da  call    WPP_SF_q
0x1400141df  jmp     loc_14001451D
0x1400141e4  mov     rax, [rbx+50h]
0x1400141e8  mov     rcx, [rax+160h]
0x1400141ef  test    rcx, rcx
0x1400141f2  jz      short loc_140014208
0x1400141f4  mov     rax, [rcx+2A8h]
0x1400141fb  test    rax, rax
0x1400141fe  jz      short loc_140014208
0x140014200  mov     rcx, rbx
0x140014203  call    _guard_dispatch_icall
0x140014208  mov     rdx, r14
0x14001420b  mov     rcx, rbx
0x14001420e  call    RxDetachIrpFromRxContext
0x140014213  mov     rcx, rsi
0x140014216  mov     rax, rbp
0x140014219  call    _guard_dispatch_icall
0x14001421e  xor     esi, esi
0x140014220  mov     rdx, 0FFFFF78000000008h
0x14001422a  mov     [rbx+220h], rsi
0x140014231  mov     [rbx+230h], rsi
0x140014238  mov     [rbx+238h], rsi
0x14001423f  mov     rdx, [rdx]
0x140014242  mov     rcx, cs:WPP_GLOBAL_Control
0x140014249  lea     rax, WPP_GLOBAL_Control
0x140014250  cmp     rcx, rax
0x140014253  jz      short loc_1400142BF
0x140014255  test    dword ptr [rcx+2Ch], 4000h
0x14001425c  jz      short loc_1400142BF
0x14001425e  cmp     byte ptr [rcx+29h], 2
0x140014262  jb      short loc_1400142BF
0x140014264  sub     rdx, [rbx+18h]
0x140014268  mov     rax, 346DC5D63886594Bh
0x140014272  movzx   r9d, byte ptr [rbx+20h]
0x140014277  movzx   r8d, byte ptr [rbx+21h]
0x14001427c  mov     rcx, [rcx+18h]
0x140014280  mul     rdx
0x140014283  mov     rax, [rbx+0B8h]
0x14001428a  shr     rdx, 0Bh
0x14001428e  mov     [rsp+98h+var_48], rdx
0x140014293  mov     [rsp+98h+var_50], r15
0x140014298  mov     [rsp+98h+var_58], rax
0x14001429d  mov     eax, [rbx+0B0h]
0x1400142a3  mov     dword ptr [rsp+98h+var_60], eax
0x1400142a7  mov     [rsp+98h+var_68], rbx
0x1400142ac  mov     [rsp+98h+var_70], r8d
0x1400142b1  mov     word ptr [rsp+98h+var_78], r9w
0x1400142b7  mov     r9, r14
0x1400142ba  call    WPP_SF_qhDqDiqi
0x1400142bf  mov     rax, [rbx+0B8h]
0x1400142c6  mov     [r14+38h], rax
0x1400142ca  mov     eax, [rbx+0B0h]
0x1400142d0  mov     [r14+30h], eax
0x1400142d4  movzx   eax, word ptr [rbx+1B8h]
0x1400142db  mov     rdi, [rdi+rax*8+20h]
0x1400142e0  mov     rcx, rdi; SpinLock
0x1400142e3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400142ea  nop     dword ptr [rax+rax+00h]
0x1400142ef  cmp     byte ptr [rbx+20h], 3
0x1400142f3  lea     rdx, [rbx+170h]
0x1400142fa  movzx   r8d, al
0x1400142fe  jnz     short loc_140014379
0x140014300  mov     rcx, [rdi+18h]
0x140014304  lea     rax, [rdi+10h]
0x140014308  cmp     [rcx], rax
0x14001430b  jnz     short loc_140014386
0x14001430d  mov     [rdx], rax
0x140014310  mov     [rdx+8], rcx
0x140014314  mov     [rcx], rdx
0x140014317  mov     rcx, rdi; SpinLock
0x14001431a  mov     [rax+8], rdx
0x14001431e  movzx   edx, r8b; NewIrql
0x140014322  inc     dword ptr [rdi+8]
0x140014325  or      dword ptr [rbx+78h], 80000h
0x14001432c  call    cs:__imp_KeReleaseSpinLock
0x140014333  nop     dword ptr [rax+rax+00h]
0x140014338  mov     rdx, [rbx+370h]
0x14001433f  prefetchw byte ptr [rdx]
0x140014342  mov     rax, [rdx]
0x140014345  and     rax, 0FFFFFFFFFFFFFFFEh
0x140014349  cmp     rax, 2
0x14001434d  jb      short loc_14001435A
0x14001434f  lea     rcx, [rax-2]
0x140014353  lock cmpxchg [rdx], rcx
0x140014358  jz      short loc_14001439D
0x14001435a  prefetchw byte ptr [rdx]
0x14001435d  mov     rax, [rdx]
0x140014360  test    al, 1
0x140014362  jnz     short loc_14001438D
0x140014364  cmp     rax, 2
0x140014368  jnb     short loc_14001436C
0x14001436a  int     2Ch; Windows NT - assertion failure
0x14001436c  lea     rcx, [rax-2]
0x140014370  lock cmpxchg [rdx], rcx
0x140014375  jnz     short loc_140014360
0x140014377  jmp     short loc_14001439D
0x140014379  mov     rcx, [rdi+28h]
0x14001437d  lea     rax, [rdi+20h]
0x140014381  cmp     [rcx], rax
0x140014384  jz      short loc_14001430D
0x140014386  mov     ecx, 3
0x14001438b  int     29h; Win8: RtlFailFast(ecx)
0x14001438d  and     rax, 0FFFFFFFFFFFFFFFEh
0x140014391  jnz     short loc_140014395
0x140014393  int     2Ch; Windows NT - assertion failure
0x140014395  mov     rcx, rax
0x140014398  call    RfsDecrementRundownWaitBlockCount
0x14001439d  mov     rax, r14
0x1400143a0  add     rsp, 68h
0x1400143a4  pop     r15
0x1400143a6  pop     r14
0x1400143a8  pop     rdi
0x1400143a9  pop     rsi
0x1400143aa  pop     rbp
0x1400143ab  pop     rbx
0x1400143ac  retn
0x1400143ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400143b5  lea     rax, WPP_GLOBAL_Control
0x1400143bc  cmp     rcx, rax
0x1400143bf  jz      loc_14001451D
0x1400143c5  test    dword ptr [rcx+2Ch], 4000h
0x1400143cc  jz      loc_14001451D
0x1400143d2  cmp     byte ptr [rcx+29h], 1
0x1400143d6  jb      loc_14001451D
0x1400143dc  mov     rcx, [rcx+18h]
0x1400143e0  mov     edx, 1Eh
0x1400143e5  mov     [rsp+98h+var_78], r8d
0x1400143ea  mov     r9, rbx
0x1400143ed  lea     r8, WPP_d414fc76462934e262300deaf9706329_Traceguids
0x1400143f4  call    WPP_SF_qD
0x1400143f9  jmp     loc_14001451D
0x1400143fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140014405  lea     rax, WPP_GLOBAL_Control
0x14001440c  cmp     rcx, rax
0x14001440f  jz      loc_14001451D
0x140014415  test    dword ptr [rcx+2Ch], 4000h
0x14001441c  jz      loc_14001451D
0x140014422  cmp     byte ptr [rcx+29h], 1
0x140014426  jb      loc_14001451D
0x14001442c  mov     rax, [rdi]
0x14001442f  mov     r9, rbx
0x140014432  movzx   edx, byte ptr [rdi+18h]
0x140014436  mov     rcx, [rcx+18h]
0x14001443a  mov     [rsp+98h+var_60], rax
0x14001443f  mov     eax, [rdi+1Ch]
0x140014442  mov     [rsp+98h+var_68], r15
0x140014447  mov     [rsp+98h+var_70], eax
0x14001444b  mov     [rsp+98h+var_78], edx
0x14001444f  call    WPP_SF_qddqq
0x140014454  jmp     loc_14001451D
0x140014459  mov     rcx, cs:WPP_GLOBAL_Control
0x140014460  lea     rax, WPP_GLOBAL_Control
0x140014467  cmp     rcx, rax
0x14001446a  jz      loc_14001451D
0x140014470  test    dword ptr [rcx+2Ch], 4000h
0x140014477  jz      loc_14001451D
0x14001447d  cmp     byte ptr [rcx+29h], 1
0x140014481  jb      loc_14001451D
0x140014487  movzx   eax, byte ptr [rbx+20h]
0x14001448b  xor     esi, esi
0x14001448d  movzx   r11d, word ptr [rbx+20Ah]
0x140014495  sub     al, 3
0x140014497  mov     rcx, [rcx+18h]
0x14001449b  movzx   edx, r11w
0x14001449f  mov     r10d, esi
0x1400144a2  mov     r9d, esi
0x1400144a5  mov     r8d, esi
0x1400144a8  not     dx
0x1400144ab  not     edi
0x1400144ad  shr     edi, 1Fh
0x1400144b0  cmp     al, 1
0x1400144b2  mov     [rsp+98h+var_40], edi
0x1400144b6  mov     rax, [rbx+228h]
0x1400144bd  setbe   r10b
0x1400144c1  mov     dword ptr [rsp+98h+var_48], r10d
0x1400144c6  cmp     [rax+148h], rsi
0x1400144cd  mov     eax, [rbx+218h]
0x1400144d3  setnz   r9b
0x1400144d7  test    al, 7
0x1400144d9  mov     eax, [r14+10h]
0x1400144dd  setz    r8b
0x1400144e1  mov     dword ptr [rsp+98h+var_50], r9d
0x1400144e6  mov     dword ptr [rsp+98h+var_58], r8d
0x1400144eb  and     edx, 1
0x1400144ee  test    dword ptr [rbx+78h], 202h
0x1400144f5  mov     r9, rbx
0x1400144f8  mov     dword ptr [rsp+98h+var_60], edx
0x1400144fc  setz    sil
0x140014500  shr     r11d, 3
0x140014504  and     r11d, 1
0x140014508  mov     dword ptr [rsp+98h+var_68], esi
0x14001450c  and     eax, 1
0x14001450f  mov     [rsp+98h+var_70], r11d
0x140014514  mov     [rsp+98h+var_78], eax
0x140014518  call    WPP_SF_qdddddddd
0x14001451d  xor     eax, eax
0x14001451f  add     rsp, 68h
0x140014523  pop     r15
0x140014525  pop     r14
0x140014527  pop     rdi
0x140014528  pop     rsi
0x140014529  pop     rbp
0x14001452a  pop     rbx
0x14001452b  retn
```
