# UlpAuthenticateRequestCompletion

- ea: `0x1c0117670`
- end: `0x1c011791d`
- name: `UlpAuthenticateRequestCompletion`
- size: `685`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1c0006870`
- `0x1c000fc68`
- `0x1c002e5e4`
- `0x1c002e650`
- `0x1c002f598`
- `0x1c002fb6c`
- `0x1c008f21c`
- `0x1c008f680`
- `0x1c008fd84`
- `0x1c00ad390`
- `0x1c0117670`
- `0x1c01392d4`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1c01178a3`
- `ntoskrnl!IofCompleteRequest` at `0x1c01178a3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c011771e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c011782e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c011771e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c011782e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c01176e7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c01176e7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c011772a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c011783a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c011772a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c011783a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c01176cf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c01176cf`

## pseudocode

```c
__int64 __fastcall UlpAuthenticateRequestCompletion(__int64 a1, int a2)
{
  int Request; // r15d
  bool v4; // si
  __int64 v6; // rdi
  bool v7; // cl
  char IsRequestFromProxy; // al
  _QWORD *v9; // rcx
  __int64 v10; // rax
  __int64 result; // rax
  _QWORD v12[2]; // [rsp+30h] [rbp-10h] BYREF

  Request = 0;
  v4 = 0;
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_qdP(144, WPP_95173837b5773721cd51a44381a2b960_Traceguids, a1, (unsigned int)a2);
  v6 = *(_QWORD *)(a1 + 24);
  v12[1] = v12;
  v12[0] = v12;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v6 + 464, 0);
  *(_BYTE *)(a1 + 2424) = 0;
  if ( (*(_DWORD *)(v6 + 520) & 2) != 0 )
  {
    UlCleanupSecurityContext(*(_QWORD *)(v6 + 960), 0, v6 + 680);
    ExReleasePushLockExclusiveEx(v6 + 464, 0);
    KeLeaveCriticalRegion();
    goto LABEL_31;
  }
  if ( a2 < 0 )
    goto LABEL_37;
  if ( a2 == 259 )
  {
    UlpSendAuthChallenge(v6);
    goto LABEL_13;
  }
  ++*(_DWORD *)(a1 + 2732);
  Request = UlpDeliverHttpRequest(v6, v12);
  if ( Request < 0 || (Request = UlpParseNextRequest(v6, 0, v12), Request < 0) )
  {
LABEL_37:
    if ( !*(_DWORD *)(a1 + 1852) )
      UlSetErrorCode(a1, 20, *(_QWORD *)(a1 + 1328));
    UlSendErrorResponse(v6);
    if ( Request < 0 )
      goto LABEL_22;
  }
LABEL_13:
  v4 = a2 == 259;
  if ( a2 >= 0 )
  {
    if ( *(_BYTE *)(v6 + 709) && !*(_BYTE *)(a1 + 1450)
      || (v7 = a2 == 259, *(_BYTE *)(v6 + 710)) && (*(_BYTE *)(a1 + 1451) & 1) != 0 )
    {
      IsRequestFromProxy = UlpIsRequestFromProxy(a1);
      v7 = a2 == 259;
      if ( !IsRequestFromProxy )
        v7 = 1;
    }
    v4 = v7;
    if ( *(_BYTE *)(v6 + 711) )
      v4 = 1;
  }
LABEL_22:
  UlCleanupSecurityContext(*(_QWORD *)(v6 + 960), v4, v6 + 680);
  ExReleasePushLockExclusiveEx(v6 + 464, 0);
  KeLeaveCriticalRegion();
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_q(265, WPP_95173837b5773721cd51a44381a2b960_Traceguids, v12);
  while ( 1 )
  {
    v9 = (_QWORD *)v12[0];
    if ( (_QWORD *)v12[0] == v12 )
      break;
    if ( *(_QWORD **)(v12[0] + 8LL) != v12 || (v10 = *(_QWORD *)v12[0], *(_QWORD *)(*(_QWORD *)v12[0] + 8LL) != v12[0]) )
      __fastfail(3u);
    v12[0] = *(_QWORD *)v12[0];
    *(_QWORD *)(v10 + 8) = v12;
    *v9 = 0;
    v9[1] = 0;
    IofCompleteRequest((PIRP)(v9 - 21), 0);
  }
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_(266, WPP_95173837b5773721cd51a44381a2b960_Traceguids);
LABEL_31:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 48), 0xFFFFFFFF) == 1 )
    UlpQueueFreeHttpRequest(a1);
  result = LODWORD(WPP_MAIN_CB.Queue.ListEntry.Flink);
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    return WPP_SF_(145, WPP_95173837b5773721cd51a44381a2b960_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1c0117670  mov     [rsp-28h+arg_8], rbx
0x1c0117675  mov     [rsp-28h+arg_10], rsi
0x1c011767a  push    rbp
0x1c011767b  push    rdi
0x1c011767c  push    r12
0x1c011767e  push    r14
0x1c0117680  push    r15
0x1c0117682  mov     rbp, rsp
0x1c0117685  sub     rsp, 40h
0x1c0117689  xor     r15d, r15d
0x1c011768c  mov     r14d, edx
0x1c011768f  xor     sil, sil
0x1c0117692  mov     rbx, rcx
0x1c0117695  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c011769b  test    al, al
0x1c011769d  jns     short loc_1C01176BB
0x1c011769f  mov     [rsp+40h+var_20], r8
0x1c01176a4  mov     r9d, edx
0x1c01176a7  mov     r8, rbx
0x1c01176aa  lea     rdx, WPP_95173837b5773721cd51a44381a2b960_Traceguids
0x1c01176b1  mov     ecx, 90h
0x1c01176b6  call    WPP_SF_qdP
0x1c01176bb  mov     rdi, [rbx+18h]
0x1c01176bf  lea     rax, [rbp+var_10]
0x1c01176c3  mov     [rbp+var_8], rax
0x1c01176c7  lea     rax, [rbp+var_10]
0x1c01176cb  mov     [rbp+var_10], rax
0x1c01176cf  call    cs:__imp_KeEnterCriticalRegion
0x1c01176d6  nop     dword ptr [rax+rax+00h]
0x1c01176db  lea     r12, [rdi+1D0h]
0x1c01176e2  xor     edx, edx
0x1c01176e4  mov     rcx, r12
0x1c01176e7  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c01176ee  nop     dword ptr [rax+rax+00h]
0x1c01176f3  mov     [rbx+978h], sil
0x1c01176fa  mov     eax, [rdi+208h]
0x1c0117700  test    al, 2
0x1c0117702  jz      short loc_1C011773B
0x1c0117704  mov     rcx, [rdi+3C0h]
0x1c011770b  lea     r8, [rdi+2A8h]
0x1c0117712  xor     edx, edx
0x1c0117714  call    UlCleanupSecurityContext
0x1c0117719  xor     edx, edx
0x1c011771b  mov     rcx, r12
0x1c011771e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c0117725  nop     dword ptr [rax+rax+00h]
0x1c011772a  call    cs:__imp_KeLeaveCriticalRegion
0x1c0117731  nop     dword ptr [rax+rax+00h]
0x1c0117736  jmp     loc_1C01178D3
0x1c011773b  mov     eax, 1
0x1c0117740  test    r14d, r14d
0x1c0117743  js      short loc_1C0117783
0x1c0117745  mov     rcx, rdi
0x1c0117748  cmp     r14d, 103h
0x1c011774f  jnz     short loc_1C0117758
0x1c0117751  call    UlpSendAuthChallenge
0x1c0117756  jmp     short loc_1C01177AD
0x1c0117758  add     [rbx+0AACh], eax
0x1c011775e  lea     rdx, [rbp+var_10]
0x1c0117762  call    UlpDeliverHttpRequest
0x1c0117767  mov     r15d, eax
0x1c011776a  test    eax, eax
0x1c011776c  js      short loc_1C0117783
0x1c011776e  lea     r8, [rbp+var_10]
0x1c0117772  xor     edx, edx
0x1c0117774  mov     rcx, rdi
0x1c0117777  call    UlpParseNextRequest
0x1c011777c  mov     r15d, eax
0x1c011777f  test    eax, eax
0x1c0117781  jns     short loc_1C01177AD
0x1c0117783  cmp     dword ptr [rbx+73Ch], 0
0x1c011778a  jnz     short loc_1C01177A0
0x1c011778c  mov     r8, [rbx+530h]
0x1c0117793  mov     edx, 14h
0x1c0117798  mov     rcx, rbx
0x1c011779b  call    UlSetErrorCode
0x1c01177a0  mov     rcx, rdi
0x1c01177a3  call    UlSendErrorResponse
0x1c01177a8  test    r15d, r15d
0x1c01177ab  js      short loc_1C0117812
0x1c01177ad  cmp     r14d, 103h
0x1c01177b4  setz    sil
0x1c01177b8  test    r14d, r14d
0x1c01177bb  js      short loc_1C0117812
0x1c01177bd  cmp     byte ptr [rdi+2C5h], 0
0x1c01177c4  jz      short loc_1C01177CF
0x1c01177c6  cmp     byte ptr [rbx+5AAh], 0
0x1c01177cd  jz      short loc_1C01177EC
0x1c01177cf  cmp     byte ptr [rdi+2C6h], 0
0x1c01177d6  mov     cl, sil
0x1c01177d9  mov     r14d, 1
0x1c01177df  jz      short loc_1C0117804
0x1c01177e1  test    [rbx+5ABh], r14b
0x1c01177e8  jz      short loc_1C0117804
0x1c01177ea  jmp     short loc_1C01177F2
0x1c01177ec  mov     r14d, 1
0x1c01177f2  mov     rcx, rbx
0x1c01177f5  call    UlpIsRequestFromProxy
0x1c01177fa  test    al, al
0x1c01177fc  movzx   ecx, sil
0x1c0117800  cmovz   ecx, r14d
0x1c0117804  cmp     byte ptr [rdi+2C7h], 0
0x1c011780b  movzx   esi, cl
0x1c011780e  cmovnz  esi, r14d
0x1c0117812  mov     rcx, [rdi+3C0h]
0x1c0117819  lea     r8, [rdi+2A8h]
0x1c0117820  movzx   edx, sil
0x1c0117824  call    UlCleanupSecurityContext
0x1c0117829  xor     edx, edx
0x1c011782b  mov     rcx, r12
0x1c011782e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c0117835  nop     dword ptr [rax+rax+00h]
0x1c011783a  call    cs:__imp_KeLeaveCriticalRegion
0x1c0117841  nop     dword ptr [rax+rax+00h]
0x1c0117846  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c011784c  test    al, al
0x1c011784e  jns     short loc_1C0117865
0x1c0117850  mov     ecx, 109h
0x1c0117855  lea     r8, [rbp+var_10]
0x1c0117859  lea     rdx, WPP_95173837b5773721cd51a44381a2b960_Traceguids
0x1c0117860  call    WPP_SF_q
0x1c0117865  mov     rcx, [rbp+var_10]
0x1c0117869  lea     rax, [rbp+var_10]
0x1c011786d  cmp     rcx, rax
0x1c0117870  jz      short loc_1C01178B8
0x1c0117872  lea     rax, [rbp+var_10]
0x1c0117876  cmp     [rcx+8], rax
0x1c011787a  jnz     short loc_1C01178B1
0x1c011787c  mov     rax, [rcx]
0x1c011787f  cmp     [rax+8], rcx
0x1c0117883  jnz     short loc_1C01178B1
0x1c0117885  mov     [rbp+var_10], rax
0x1c0117889  lea     rdx, [rbp+var_10]
0x1c011788d  mov     [rax+8], rdx
0x1c0117891  xor     edx, edx; PriorityBoost
0x1c0117893  and     qword ptr [rcx], 0
0x1c0117897  and     qword ptr [rcx+8], 0
0x1c011789c  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x1c01178a3  call    cs:__imp_IofCompleteRequest
0x1c01178aa  nop     dword ptr [rax+rax+00h]
0x1c01178af  jmp     short loc_1C0117865
0x1c01178b1  mov     ecx, 3
0x1c01178b6  int     29h; Win8: RtlFailFast(ecx)
0x1c01178b8  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c01178be  test    al, al
0x1c01178c0  jns     short loc_1C01178D3
0x1c01178c2  mov     ecx, 10Ah
0x1c01178c7  lea     rdx, WPP_95173837b5773721cd51a44381a2b960_Traceguids
0x1c01178ce  call    WPP_SF_
0x1c01178d3  or      eax, 0FFFFFFFFh
0x1c01178d6  lock xadd [rbx+30h], eax
0x1c01178db  cmp     eax, 1
0x1c01178de  jnz     short loc_1C01178E8
0x1c01178e0  mov     rcx, rbx
0x1c01178e3  call    UlpQueueFreeHttpRequest
0x1c01178e8  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c01178ee  test    al, al
0x1c01178f0  jns     short loc_1C0117903
0x1c01178f2  mov     ecx, 91h
0x1c01178f7  lea     rdx, WPP_95173837b5773721cd51a44381a2b960_Traceguids
0x1c01178fe  call    WPP_SF_
0x1c0117903  lea     r11, [rsp+40h+var_s0]
0x1c0117908  mov     rbx, [r11+38h]
0x1c011790c  mov     rsi, [r11+40h]
0x1c0117910  mov     rsp, r11
0x1c0117913  pop     r15
0x1c0117915  pop     r14
0x1c0117917  pop     r12
0x1c0117919  pop     rdi
0x1c011791a  pop     rbp
0x1c011791b  retn
```
