# UlReceiveHttpRequest

- ea: `0x1c00a4250`
- end: `0x1c00a447d`
- name: `UlReceiveHttpRequest`
- size: `557`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x1c00097a0`
- `0x1c00a3f70`

## callees

- `0x1c0001c90`
- `0x1c000a0d0`
- `0x1c000fc68`
- `0x1c00298a0`
- `0x1c008f374`
- `0x1c008fae0`
- `0x1c00a4250`
- `0x1c00b0480`
- `0x1c00b2a2c`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00a42fb`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00a4423`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00a42fb`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00a4423`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c00a42bd`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c00a42bd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00a43e0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00a4406`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00deabc`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00deae2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00a43e0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00a4406`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00deabc`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00deae2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00a4377`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00a43a1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00a4377`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00a43a1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a4307`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a43ec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a4412`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a442f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00deac8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00deaee`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a4307`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a43ec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a4412`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a442f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00deac8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00deaee`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a42a8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a435d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a4383`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a42a8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a435d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a4383`

## pseudocode

```c
__int64 __fastcall UlReceiveHttpRequest(__int64 a1, __int64 a2, __int64 a3, IRP *a4)
{
  int v6; // ebp
  __int64 v8; // rdi
  __int64 v9; // rbp
  unsigned int v10; // eax
  unsigned int v11; // esi
  __int64 v13; // r8
  __int64 RequestFromId; // rax
  __int64 v15; // [rsp+30h] [rbp-28h] BYREF

  v6 = a2;
  v15 = 0;
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_iLqq(a1, a2, a1, (unsigned int)a2, a3, a4);
  v8 = *(_QWORD *)(a3 + 8);
  if ( *(_DWORD *)(a3 + 40) == 4 && v6 )
  {
    v11 = -1073741811;
  }
  else if ( a1 )
  {
    RequestFromId = UlGetRequestFromId(a1, a3);
    v15 = RequestFromId;
    if ( RequestFromId )
    {
      UlStopRequestQueueTimer(RequestFromId);
      a4->Tail.Overlay.CurrentStackLocation->Control |= 1u;
      UlCopyRequestToIrp(v15, a4, a3, 0, 0);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v15 + 48), 0xFFFFFFFF) == 1 )
        UlpQueueFreeHttpRequest(v15);
      v15 = 0;
      v11 = 259;
    }
    else
    {
      v11 = -1073741254;
    }
  }
  else
  {
    KeEnterCriticalRegion();
    v9 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v8 + 280), 0);
    if ( *(_BYTE *)(a3 + 4) )
    {
      v11 = -1073741816;
    }
    else
    {
      while ( 1 )
      {
        v10 = UlpRetrieveRequest(v8, a3, a4, &v15);
        v11 = v10;
        if ( v10 == 259 )
          break;
        if ( v10 == -1073741738 )
        {
          v11 = 259;
          break;
        }
        if ( v10 == -1073741536 )
          break;
        if ( v10 )
        {
          v11 = -1073741823;
          break;
        }
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(v15 + 1688, 0);
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(*(_QWORD *)(v15 + 1696) + 56LL, 0);
        LOBYTE(v13) = 1;
        if ( (unsigned __int8)UlpTransferRequestToCoupling(v15, a3, v13) )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v15 + 48));
          ExReleasePushLockExclusiveEx(*(_QWORD *)(v15 + 1696) + 56LL, 0);
          KeLeaveCriticalRegion();
          ExReleasePushLockExclusiveEx(v15 + 1688, 0);
          KeLeaveCriticalRegion();
          ExReleaseCacheAwarePushLockSharedEx(v9, 0);
          KeLeaveCriticalRegion();
          a4->Tail.Overlay.CurrentStackLocation->Control |= 1u;
          UlCopyRequestToIrp(v15, a4, a3, 0, 0);
          v11 = 259;
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v15 + 48), 0xFFFFFFFF) == 1 )
            UlpQueueFreeHttpRequest(v15);
          goto LABEL_8;
        }
        ExReleasePushLockExclusiveEx(*(_QWORD *)(v15 + 1696) + 56LL, 0);
        KeLeaveCriticalRegion();
        ExReleasePushLockExclusiveEx(v15 + 1688, 0);
        KeLeaveCriticalRegion();
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v15 + 48), 0xFFFFFFFF) == 1 )
          UlpQueueFreeHttpRequest(v15);
      }
    }
    ExReleaseCacheAwarePushLockSharedEx(v9, 0);
    KeLeaveCriticalRegion();
  }
LABEL_8:
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_D(190, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
  return v11;
}

```

## disassembly

```asm
0x1c00a4250  push    rsi
0x1c00a4252  sub     rsp, 50h
0x1c00a4256  mov     [rsp+58h+arg_0], rbx
0x1c00a425b  mov     rsi, rcx
0x1c00a425e  mov     [rsp+58h+arg_8], rbp
0x1c00a4263  mov     rbx, r8
0x1c00a4266  mov     [rsp+58h+arg_18], rdi
0x1c00a426b  mov     ebp, edx
0x1c00a426d  mov     [rsp+58h+var_10], r14
0x1c00a4272  mov     r14, r9
0x1c00a4275  mov     [rsp+58h+var_28], 0
0x1c00a427e  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a4284  test    al, al
0x1c00a4286  js      loc_1C00DE9FC
0x1c00a428c  cmp     dword ptr [rbx+28h], 4
0x1c00a4290  mov     rdi, [rbx+8]
0x1c00a4294  jz      loc_1C00DEA17
0x1c00a429a  mov     [rsp+58h+var_18], r15
0x1c00a429f  test    rsi, rsi
0x1c00a42a2  jnz     loc_1C00DEA29
0x1c00a42a8  call    cs:__imp_KeEnterCriticalRegion
0x1c00a42af  nop     dword ptr [rax+rax+00h]
0x1c00a42b4  mov     rcx, [rdi+118h]
0x1c00a42bb  xor     edx, edx
0x1c00a42bd  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1c00a42c4  nop     dword ptr [rax+rax+00h]
0x1c00a42c9  mov     rbp, rax
0x1c00a42cc  cmp     [rbx+4], sil
0x1c00a42d0  jnz     loc_1C00DEAA7
0x1c00a42d6  lea     r15d, [rsi-1]
0x1c00a42da  lea     r9, [rsp+58h+var_28]
0x1c00a42df  mov     r8, r14
0x1c00a42e2  mov     rdx, rbx
0x1c00a42e5  mov     rcx, rdi
0x1c00a42e8  call    UlpRetrieveRequest
0x1c00a42ed  mov     esi, eax
0x1c00a42ef  cmp     eax, 103h
0x1c00a42f4  jnz     short loc_1C00A4343
0x1c00a42f6  xor     edx, edx
0x1c00a42f8  mov     rcx, rbp
0x1c00a42fb  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1c00a4302  nop     dword ptr [rax+rax+00h]
0x1c00a4307  call    cs:__imp_KeLeaveCriticalRegion
0x1c00a430e  nop     dword ptr [rax+rax+00h]
0x1c00a4313  mov     r15, [rsp+58h+var_18]
0x1c00a4318  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a431e  mov     r14, [rsp+58h+var_10]
0x1c00a4323  mov     rdi, [rsp+58h+arg_18]
0x1c00a4328  mov     rbp, [rsp+58h+arg_8]
0x1c00a432d  mov     rbx, [rsp+58h+arg_0]
0x1c00a4332  test    al, al
0x1c00a4334  js      loc_1C00DEB44
0x1c00a433a  mov     eax, esi
0x1c00a433c  add     rsp, 50h
0x1c00a4340  pop     rsi
0x1c00a4341  retn
0x1c00a4343  cmp     eax, 0C0000056h
0x1c00a4348  jz      loc_1C00DEB3A
0x1c00a434e  cmp     eax, 0C0000120h
0x1c00a4353  jz      short loc_1C00A42F6
0x1c00a4355  test    eax, eax
0x1c00a4357  jnz     loc_1C00DEB30
0x1c00a435d  call    cs:__imp_KeEnterCriticalRegion
0x1c00a4364  nop     dword ptr [rax+rax+00h]
0x1c00a4369  mov     rcx, [rsp+58h+var_28]
0x1c00a436e  xor     edx, edx
0x1c00a4370  add     rcx, 698h
0x1c00a4377  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c00a437e  nop     dword ptr [rax+rax+00h]
0x1c00a4383  call    cs:__imp_KeEnterCriticalRegion
0x1c00a438a  nop     dword ptr [rax+rax+00h]
0x1c00a438f  mov     rax, [rsp+58h+var_28]
0x1c00a4394  xor     edx, edx
0x1c00a4396  mov     rcx, [rax+6A0h]
0x1c00a439d  add     rcx, 38h ; '8'
0x1c00a43a1  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c00a43a8  nop     dword ptr [rax+rax+00h]
0x1c00a43ad  mov     rcx, [rsp+58h+var_28]
0x1c00a43b2  mov     r8b, 1
0x1c00a43b5  mov     rdx, rbx
0x1c00a43b8  call    UlpTransferRequestToCoupling
0x1c00a43bd  xor     edx, edx
0x1c00a43bf  test    al, al
0x1c00a43c1  mov     rax, [rsp+58h+var_28]
0x1c00a43c6  jz      loc_1C00DEAB1
0x1c00a43cc  lock inc dword ptr [rax+30h]
0x1c00a43d0  mov     rax, [rsp+58h+var_28]
0x1c00a43d5  mov     rcx, [rax+6A0h]
0x1c00a43dc  add     rcx, 38h ; '8'
0x1c00a43e0  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00a43e7  nop     dword ptr [rax+rax+00h]
0x1c00a43ec  call    cs:__imp_KeLeaveCriticalRegion
0x1c00a43f3  nop     dword ptr [rax+rax+00h]
0x1c00a43f8  mov     rcx, [rsp+58h+var_28]
0x1c00a43fd  xor     edx, edx
0x1c00a43ff  add     rcx, 698h
0x1c00a4406  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00a440d  nop     dword ptr [rax+rax+00h]
0x1c00a4412  call    cs:__imp_KeLeaveCriticalRegion
0x1c00a4419  nop     dword ptr [rax+rax+00h]
0x1c00a441e  xor     edx, edx
0x1c00a4420  mov     rcx, rbp
0x1c00a4423  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1c00a442a  nop     dword ptr [rax+rax+00h]
0x1c00a442f  call    cs:__imp_KeLeaveCriticalRegion
0x1c00a4436  nop     dword ptr [rax+rax+00h]
0x1c00a443b  mov     rax, [r14+0B8h]
0x1c00a4442  xor     r9d, r9d
0x1c00a4445  mov     r8, rbx
0x1c00a4448  mov     byte ptr [rsp+58h+var_38], 0
0x1c00a444d  mov     rdx, r14
0x1c00a4450  or      byte ptr [rax+3], 1
0x1c00a4454  mov     rcx, [rsp+58h+var_28]
0x1c00a4459  call    UlCopyRequestToIrp
0x1c00a445e  mov     rax, [rsp+58h+var_28]
0x1c00a4463  mov     esi, 103h
0x1c00a4468  lock xadd [rax+30h], r15d
0x1c00a446e  cmp     r15d, 1
0x1c00a4472  jnz     loc_1C00A4313
0x1c00a4478  jmp     loc_1C00DEB20
0x1c00de9fc  mov     [rsp+58h+var_30], r14
0x1c00dea01  mov     r9d, ebp
0x1c00dea04  mov     r8, rsi
0x1c00dea07  mov     [rsp+58h+var_38], rbx
0x1c00dea0c  call    WPP_SF_iLqq
0x1c00dea11  nop
0x1c00dea12  jmp     loc_1C00A428C
0x1c00dea17  test    ebp, ebp
0x1c00dea19  jz      loc_1C00A429A
0x1c00dea1f  mov     esi, 0C000000Dh
0x1c00dea24  jmp     loc_1C00A4318
0x1c00dea29  mov     rdx, rbx
0x1c00dea2c  mov     rcx, rsi
0x1c00dea2f  call    UlGetRequestFromId
0x1c00dea34  mov     [rsp+58h+var_28], rax
0x1c00dea39  test    rax, rax
0x1c00dea3c  jnz     short loc_1C00DEA48
0x1c00dea3e  mov     esi, 0C000023Ah
0x1c00dea43  jmp     loc_1C00A4313
0x1c00dea48  mov     rcx, rax
0x1c00dea4b  call    UlStopRequestQueueTimer
0x1c00dea50  mov     rax, [r14+0B8h]
0x1c00dea57  xor     r9d, r9d
0x1c00dea5a  mov     r8, rbx
0x1c00dea5d  mov     byte ptr [rsp+58h+var_38], 0
0x1c00dea62  mov     rdx, r14
0x1c00dea65  or      byte ptr [rax+3], 1
0x1c00dea69  mov     rcx, [rsp+58h+var_28]
0x1c00dea6e  call    UlCopyRequestToIrp
0x1c00dea73  mov     rax, [rsp+58h+var_28]
0x1c00dea78  mov     r15d, 0FFFFFFFFh
0x1c00dea7e  lock xadd [rax+30h], r15d
0x1c00dea84  cmp     r15d, 1
0x1c00dea88  jnz     short loc_1C00DEA94
0x1c00dea8a  mov     rcx, [rsp+58h+var_28]
0x1c00dea8f  call    UlpQueueFreeHttpRequest
0x1c00dea94  mov     [rsp+58h+var_28], 0
0x1c00dea9d  mov     esi, 103h
0x1c00deaa2  jmp     loc_1C00A4313
0x1c00deaa7  mov     esi, 0C0000008h
0x1c00deaac  jmp     loc_1C00A42F6
0x1c00deab1  mov     rcx, [rax+6A0h]
0x1c00deab8  add     rcx, 38h ; '8'
0x1c00deabc  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00deac3  nop     dword ptr [rax+rax+00h]
0x1c00deac8  call    cs:__imp_KeLeaveCriticalRegion
0x1c00deacf  nop     dword ptr [rax+rax+00h]
0x1c00dead4  mov     rcx, [rsp+58h+var_28]
0x1c00dead9  xor     edx, edx
0x1c00deadb  add     rcx, 698h
0x1c00deae2  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00deae9  nop     dword ptr [rax+rax+00h]
0x1c00deaee  call    cs:__imp_KeLeaveCriticalRegion
0x1c00deaf5  nop     dword ptr [rax+rax+00h]
0x1c00deafa  mov     rcx, [rsp+58h+var_28]
0x1c00deaff  mov     eax, r15d
0x1c00deb02  lock xadd [rcx+30h], eax
0x1c00deb07  cmp     eax, 1
0x1c00deb0a  jnz     loc_1C00A42DA
0x1c00deb10  mov     rcx, [rsp+58h+var_28]
0x1c00deb15  call    UlpQueueFreeHttpRequest
0x1c00deb1a  nop
0x1c00deb1b  jmp     loc_1C00A42DA
0x1c00deb20  mov     rcx, [rsp+58h+var_28]
0x1c00deb25  call    UlpQueueFreeHttpRequest
0x1c00deb2a  nop
0x1c00deb2b  jmp     loc_1C00A4313
0x1c00deb30  mov     esi, 0C0000001h
0x1c00deb35  jmp     loc_1C00A42F6
0x1c00deb3a  mov     esi, 103h
0x1c00deb3f  jmp     loc_1C00A42F6
0x1c00deb44  mov     ecx, 0BEh
0x1c00deb49  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00deb50  mov     r8d, esi
0x1c00deb53  call    WPP_SF_D
0x1c00deb58  nop
0x1c00deb59  jmp     loc_1C00A433A
```
