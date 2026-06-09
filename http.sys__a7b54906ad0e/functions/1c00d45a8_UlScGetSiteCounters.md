# UlScGetSiteCounters

- ea: `0x1c00d45a8`
- end: `0x1c00d47bc`
- name: `UlScGetSiteCounters`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1c00d4410`

## callees

- `0x1c008f21c`
- `0x1c008f680`
- `0x1c008fd30`
- `0x1c00943e8`
- `0x1c00a8364`
- `0x1c00d45a8`
- `0x1c00d47c4`
- `0x1c00d489c`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00d4748`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00d4748`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c00d4607`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c00d4607`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00d4737`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00d4754`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00d4737`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00d4754`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1c00d472b`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1c00d472b`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00d464c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00d464c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00d45f2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00d4633`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00d45f2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00d4633`

## pseudocode

```c
__int64 __fastcall UlScGetSiteCounters(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, unsigned int *a5)
{
  unsigned int v5; // r14d
  __int64 v9; // rdi
  unsigned int *v10; // r15
  __int64 v11; // rbx
  __int64 v12; // rbx
  int ServerSessionFromId; // ebp
  unsigned int v14; // edx
  char *v15; // rax
  volatile __int32 *v16; // rsi
  unsigned int v17; // ecx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rdx
  PVOID P; // [rsp+80h] [rbp+8h] BYREF

  P = 0;
  v5 = a4;
  v9 = a3;
  v10 = a5;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
    WPP_SF_qqqLq(25, WPP_ec850f3529163e37ccd773c95acff141_Traceguids, a1, a2, a3, a4, a5);
  *v10 = 0;
  v11 = *(_QWORD *)(a1 + 56);
  KeEnterCriticalRegion();
  v12 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v11 + 1360), 0);
  ServerSessionFromId = UlGetServerSessionFromId(a1, a2, &P);
  if ( ServerSessionFromId >= 0 )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockSharedEx(*(_QWORD *)(a1 + 56) + 1400LL, 0);
    v14 = 72 * *((_DWORD *)P + 22);
    if ( a3 && v14 <= v5 )
    {
      v15 = (char *)P + 72;
      v16 = (volatile __int32 *)*((_QWORD *)P + 9);
      while ( v16 != (volatile __int32 *)v15 && v5 >= 0x48 )
      {
        UlCopyUrlGroupCounters(v16 + 4, v9);
        if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
          WPP_SF_q(23, WPP_ec850f3529163e37ccd773c95acff141_Traceguids, v16 - 2);
        _InterlockedExchange(v16 + 7, 0);
        v17 = **((_DWORD **)v16 + 4);
        if ( v17 )
        {
          v18 = 0;
          v19 = v17;
          do
          {
            v18 += 8;
            v20 = *(_QWORD *)(*((_QWORD *)v16 + 4) + v18);
            _InterlockedExchange((volatile __int32 *)(v20 + 16), 0);
            _InterlockedExchange((volatile __int32 *)(v20 + 20), 0);
            _InterlockedExchange((volatile __int32 *)(v20 + 24), 0);
            _InterlockedExchange64((volatile __int64 *)v20, 0);
            _InterlockedExchange64((volatile __int64 *)(v20 + 8), 0);
            --v19;
          }
          while ( v19 );
        }
        if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
          WPP_SF_(24, WPP_ec850f3529163e37ccd773c95acff141_Traceguids);
        v9 += 72;
        v16 = *(volatile __int32 **)v16;
        v5 -= 72;
        v15 = (char *)P + 72;
      }
    }
    else
    {
      *v10 = v14;
      ServerSessionFromId = -2147483643;
    }
    ExReleasePushLockSharedEx(*(_QWORD *)(a1 + 56) + 1400LL, 0);
    KeLeaveCriticalRegion();
  }
  ExReleaseCacheAwarePushLockSharedEx(v12, 0);
  KeLeaveCriticalRegion();
  if ( P )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 1, 0xFFFFFFFF) == 1 )
      UlFreeServerSession(P);
    P = 0;
  }
  if ( ServerSessionFromId >= 0 )
    *v10 = v9 - a3;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
    WPP_SF_qLd(26, WPP_ec850f3529163e37ccd773c95acff141_Traceguids, a3, *v10, ServerSessionFromId);
  return (unsigned int)ServerSessionFromId;
}

```

## disassembly

```asm
0x1c00d45a8  mov     rax, rsp
0x1c00d45ab  mov     [rax+10h], rbx
0x1c00d45af  push    rbp
0x1c00d45b0  push    rsi
0x1c00d45b1  push    rdi
0x1c00d45b2  push    r12
0x1c00d45b4  push    r13
0x1c00d45b6  push    r14
0x1c00d45b8  push    r15
0x1c00d45ba  sub     rsp, 40h
0x1c00d45be  and     qword ptr [rax+8], 0
0x1c00d45c3  mov     r14d, r9d
0x1c00d45c6  mov     r12, r8
0x1c00d45c9  mov     rsi, rdx
0x1c00d45cc  mov     r13, rcx
0x1c00d45cf  mov     rdi, r8
0x1c00d45d2  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c00d45dc  mov     r15, [rsp+78h+arg_20]
0x1c00d45e4  jnz     loc_1C00FC62A
0x1c00d45ea  and     dword ptr [r15], 0
0x1c00d45ee  mov     rbx, [r13+38h]
0x1c00d45f2  call    cs:__imp_KeEnterCriticalRegion
0x1c00d45f9  nop     dword ptr [rax+rax+00h]
0x1c00d45fe  mov     rcx, [rbx+550h]
0x1c00d4605  xor     edx, edx
0x1c00d4607  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1c00d460e  nop     dword ptr [rax+rax+00h]
0x1c00d4613  lea     r8, [rsp+78h+P]
0x1c00d461b  mov     rdx, rsi
0x1c00d461e  mov     rcx, r13
0x1c00d4621  mov     rbx, rax
0x1c00d4624  call    UlGetServerSessionFromId
0x1c00d4629  mov     ebp, eax
0x1c00d462b  test    eax, eax
0x1c00d462d  js      loc_1C00D4743
0x1c00d4633  call    cs:__imp_KeEnterCriticalRegion
0x1c00d463a  nop     dword ptr [rax+rax+00h]
0x1c00d463f  mov     rcx, [r13+38h]
0x1c00d4643  xor     edx, edx
0x1c00d4645  add     rcx, 578h
0x1c00d464c  call    cs:__imp_ExAcquirePushLockSharedEx
0x1c00d4653  nop     dword ptr [rax+rax+00h]
0x1c00d4658  mov     rax, [rsp+78h+P]
0x1c00d4660  mov     ecx, [rax+58h]
0x1c00d4663  lea     edx, [rcx+rcx*8]
0x1c00d4666  shl     edx, 3
0x1c00d4669  test    r12, r12
0x1c00d466c  jz      loc_1C00FC688
0x1c00d4672  cmp     edx, r14d
0x1c00d4675  ja      loc_1C00FC688
0x1c00d467b  add     rax, 48h ; 'H'
0x1c00d467f  mov     rsi, [rax]
0x1c00d4682  cmp     rsi, rax
0x1c00d4685  jz      loc_1C00D471E
0x1c00d468b  cmp     r14d, 48h ; 'H'
0x1c00d468f  jb      loc_1C00D471E
0x1c00d4695  lea     rcx, [rsi+10h]
0x1c00d4699  mov     rdx, rdi
0x1c00d469c  call    UlCopyUrlGroupCounters
0x1c00d46a1  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c00d46ab  jnz     loc_1C00FC656
0x1c00d46b1  xor     eax, eax
0x1c00d46b3  xchg    eax, [rsi+1Ch]
0x1c00d46b6  mov     rax, [rsi+20h]
0x1c00d46ba  mov     ecx, [rax]
0x1c00d46bc  test    ecx, ecx
0x1c00d46be  jz      short loc_1C00D46F2
0x1c00d46c0  xor     r8d, r8d
0x1c00d46c3  mov     r9d, ecx
0x1c00d46c6  mov     rax, [rsi+20h]
0x1c00d46ca  lea     r8, [r8+8]
0x1c00d46ce  xor     ecx, ecx
0x1c00d46d0  mov     rdx, [rax+r8]
0x1c00d46d4  xor     eax, eax
0x1c00d46d6  xchg    eax, [rdx+10h]
0x1c00d46d9  xor     eax, eax
0x1c00d46db  xchg    eax, [rdx+14h]
0x1c00d46de  xor     eax, eax
0x1c00d46e0  xchg    eax, [rdx+18h]
0x1c00d46e3  xchg    rcx, [rdx]
0x1c00d46e6  xor     eax, eax
0x1c00d46e8  xchg    rax, [rdx+8]
0x1c00d46ec  sub     r9, 1
0x1c00d46f0  jnz     short loc_1C00D46C6
0x1c00d46f2  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c00d46fc  jnz     loc_1C00FC671
0x1c00d4702  mov     rax, [rsp+78h+P]
0x1c00d470a  add     rdi, 48h ; 'H'
0x1c00d470e  mov     rsi, [rsi]
0x1c00d4711  add     r14d, 0FFFFFFB8h
0x1c00d4715  add     rax, 48h ; 'H'
0x1c00d4719  jmp     loc_1C00D4682
0x1c00d471e  mov     rcx, [r13+38h]
0x1c00d4722  xor     edx, edx
0x1c00d4724  add     rcx, 578h
0x1c00d472b  call    cs:__imp_ExReleasePushLockSharedEx
0x1c00d4732  nop     dword ptr [rax+rax+00h]
0x1c00d4737  call    cs:__imp_KeLeaveCriticalRegion
0x1c00d473e  nop     dword ptr [rax+rax+00h]
0x1c00d4743  xor     edx, edx
0x1c00d4745  mov     rcx, rbx
0x1c00d4748  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1c00d474f  nop     dword ptr [rax+rax+00h]
0x1c00d4754  call    cs:__imp_KeLeaveCriticalRegion
0x1c00d475b  nop     dword ptr [rax+rax+00h]
0x1c00d4760  mov     rcx, [rsp+78h+P]
0x1c00d4768  test    rcx, rcx
0x1c00d476b  jz      short loc_1C00D4787
0x1c00d476d  or      eax, 0FFFFFFFFh
0x1c00d4770  lock xadd [rcx+4], eax
0x1c00d4775  cmp     eax, 1
0x1c00d4778  jz      loc_1C00FC695
0x1c00d477e  and     [rsp+78h+P], 0
0x1c00d4787  test    ebp, ebp
0x1c00d4789  js      short loc_1C00D4791
0x1c00d478b  sub     edi, r12d
0x1c00d478e  mov     [r15], edi
0x1c00d4791  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c00d479b  jnz     loc_1C00FC6A8
0x1c00d47a1  mov     rbx, [rsp+78h+arg_8]
0x1c00d47a9  mov     eax, ebp
0x1c00d47ab  add     rsp, 40h
0x1c00d47af  pop     r15
0x1c00d47b1  pop     r14
0x1c00d47b3  pop     r13
0x1c00d47b5  pop     r12
0x1c00d47b7  pop     rdi
0x1c00d47b8  pop     rsi
0x1c00d47b9  pop     rbp
0x1c00d47ba  retn
0x1c00fc62a  mov     [rsp+78h+var_48], r15
0x1c00fc62f  lea     rdx, WPP_ec850f3529163e37ccd773c95acff141_Traceguids
0x1c00fc636  mov     [rsp+78h+var_50], r14d
0x1c00fc63b  mov     ecx, 19h
0x1c00fc640  mov     r9, rsi
0x1c00fc643  mov     [rsp+78h+var_58], r12
0x1c00fc648  mov     r8, r13
0x1c00fc64b  call    WPP_SF_qqqLq
0x1c00fc650  nop
0x1c00fc651  jmp     loc_1C00D45EA
0x1c00fc656  mov     ecx, 17h
0x1c00fc65b  lea     r8, [rsi-8]
0x1c00fc65f  lea     rdx, WPP_ec850f3529163e37ccd773c95acff141_Traceguids
0x1c00fc666  call    WPP_SF_q
0x1c00fc66b  nop
0x1c00fc66c  jmp     loc_1C00D46B1
0x1c00fc671  mov     ecx, 18h
0x1c00fc676  lea     rdx, WPP_ec850f3529163e37ccd773c95acff141_Traceguids
0x1c00fc67d  call    WPP_SF_
0x1c00fc682  nop
0x1c00fc683  jmp     loc_1C00D4702
0x1c00fc688  mov     [r15], edx
0x1c00fc68b  mov     ebp, 80000005h
0x1c00fc690  jmp     loc_1C00D471E
0x1c00fc695  mov     rcx, [rsp+78h+P]; P
0x1c00fc69d  call    UlFreeServerSession
0x1c00fc6a2  nop
0x1c00fc6a3  jmp     loc_1C00D477E
0x1c00fc6a8  mov     r9d, [r15]
0x1c00fc6ab  lea     rdx, WPP_ec850f3529163e37ccd773c95acff141_Traceguids
0x1c00fc6b2  mov     ecx, 1Ah
0x1c00fc6b7  mov     dword ptr [rsp+78h+var_58], ebp
0x1c00fc6bb  mov     r8, r12
0x1c00fc6be  call    WPP_SF_qLd
0x1c00fc6c3  nop
0x1c00fc6c4  jmp     loc_1C00D47A1
```
