# UlWaitForDisconnect

- ea: `0x1c00d39c8`
- end: `0x1c00d3be8`
- name: `UlWaitForDisconnect`
- size: `544`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1c00d38a0`

## callees

- `0x1c0002f68`
- `0x1c001683c`
- `0x1c0016860`
- `0x1c001691c`
- `0x1c001a5f0`
- `0x1c00495b4`
- `0x1c008f374`
- `0x1c0090ec0`
- `0x1c00af030`
- `0x1c00d39c8`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00d3b5a`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00d3b5a`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c00d3a93`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c00d3a93`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00d3b3d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00d3b77`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00d3b3d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00d3b77`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00d3a3e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00d3adc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00d3a3e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00d3adc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00d3b49`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00d3b66`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00d3b83`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00d3b49`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00d3b66`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00d3b83`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00d3a26`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00d3a7e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00d3ac6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00d3a26`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00d3a7e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00d3ac6`

## pseudocode

```c
__int64 __fastcall UlWaitForDisconnect(__int64 a1, __int64 a2, unsigned __int8 a3, __int64 a4)
{
  __int64 v6; // r13
  int v9; // ebx
  __int64 v10; // rax
  __int64 v11; // r15
  volatile signed __int32 *v12; // rcx
  int v13; // eax
  PVOID v14; // rcx
  __int64 v16; // rcx
  PVOID P; // [rsp+40h] [rbp-10h] BYREF
  __int64 v18; // [rsp+48h] [rbp-8h] BYREF

  P = 0;
  v18 = 0;
  v6 = *(_QWORD *)(a1 + 8);
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
  {
    if ( a2 )
      v16 = *(_QWORD *)(a2 + 24);
    else
      v16 = 0;
    WPP_SF_qqilq(v16, a2, a1, a2, v16, a3, a4);
  }
  v9 = UlAllocateGrip(&v18, a4);
  if ( v9 >= 0 )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(a2 + 464, 0);
    v10 = *(_QWORD *)(a2 + 456);
    if ( v10 && *(_QWORD *)(v10 + 1728) == a1 )
    {
      if ( !a3 || (*(_BYTE *)(a2 + 520) & 0x50) != 0x50 )
      {
        if ( (*(_DWORD *)(a2 + 520) & 8) != 0 )
        {
          if ( a3 )
            v9 = -1073741300;
        }
        else
        {
          KeEnterCriticalRegion();
          v11 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v6 + 280), 0);
          if ( *(_BYTE *)(a1 + 5) )
          {
            v9 = -1073741436;
          }
          else
          {
            v9 = UlpOpenCoupling(a2, v6, &P);
            if ( v9 >= 0 )
            {
              KeEnterCriticalRegion();
              ExAcquirePushLockExclusiveEx((char *)P + 56, 0);
              v12 = (volatile signed __int32 *)P;
              if ( *((_BYTE *)P + 64) )
              {
                v9 = -1073741436;
              }
              else
              {
                *(_QWORD *)(a4 + 120) = P;
                _InterlockedIncrement(v12);
                UlAttachGrip(&v18);
                v13 = UlSiqEnqueueIrp((PKSPIN_LOCK)P + 14);
                v12 = (volatile signed __int32 *)P;
                v9 = v13;
                if ( v13 < 0 )
                {
                  *(_QWORD *)(a4 + 120) = 0;
                  if ( _InterlockedExchangeAdd(v12, 0xFFFFFFFF) == 1 )
                    UlpFreeCoupling((PVOID)v12);
                  UlDetachGrip(&v18, a4);
                  v12 = (volatile signed __int32 *)P;
                }
                else
                {
                  *(_DWORD *)(a2 + 520) |= 0x20u;
                  v9 = 259;
                }
              }
              ExReleasePushLockExclusiveEx(v12 + 14, 0);
              KeLeaveCriticalRegion();
            }
          }
          ExReleaseCacheAwarePushLockSharedEx(v11, 0);
          KeLeaveCriticalRegion();
        }
      }
    }
    else
    {
      v9 = -1073741692;
    }
    ExReleasePushLockExclusiveEx(a2 + 464, 0);
    KeLeaveCriticalRegion();
  }
  v14 = P;
  if ( P )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)P, 0xFFFFFFFF) == 1 )
      UlpFreeCoupling(v14);
    P = 0;
  }
  UlFreeGrip(&v18);
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_D(206, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1c00d39c8  mov     [rsp-28h+arg_8], rbx
0x1c00d39cd  mov     [rsp-28h+arg_10], rsi
0x1c00d39d2  mov     [rsp-28h+arg_18], rdi
0x1c00d39d7  push    rbp
0x1c00d39d8  push    r12
0x1c00d39da  push    r13
0x1c00d39dc  push    r14
0x1c00d39de  push    r15
0x1c00d39e0  mov     rbp, rsp
0x1c00d39e3  sub     rsp, 50h
0x1c00d39e7  and     [rbp+P], 0
0x1c00d39ec  mov     rsi, r9
0x1c00d39ef  and     [rbp+var_8], 0
0x1c00d39f4  mov     rdi, rdx
0x1c00d39f7  mov     r13, [rcx+8]
0x1c00d39fb  mov     r14, rcx
0x1c00d39fe  movzx   r15d, r8b
0x1c00d3a02  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00d3a08  test    al, al
0x1c00d3a0a  js      loc_1C00FC062
0x1c00d3a10  mov     rdx, rsi
0x1c00d3a13  lea     rcx, [rbp+var_8]
0x1c00d3a17  call    UlAllocateGrip
0x1c00d3a1c  mov     ebx, eax
0x1c00d3a1e  test    eax, eax
0x1c00d3a20  js      loc_1C00D3B8F
0x1c00d3a26  call    cs:__imp_KeEnterCriticalRegion
0x1c00d3a2d  nop     dword ptr [rax+rax+00h]
0x1c00d3a32  lea     r12, [rdi+1D0h]
0x1c00d3a39  xor     edx, edx
0x1c00d3a3b  mov     rcx, r12
0x1c00d3a3e  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c00d3a45  nop     dword ptr [rax+rax+00h]
0x1c00d3a4a  mov     rax, [rdi+1C8h]
0x1c00d3a51  test    rax, rax
0x1c00d3a54  jz      loc_1C00FC0F9
0x1c00d3a5a  cmp     [rax+6C0h], r14
0x1c00d3a61  jnz     loc_1C00FC0F9
0x1c00d3a67  test    r15b, r15b
0x1c00d3a6a  jnz     loc_1C00FC08F
0x1c00d3a70  mov     eax, [rdi+208h]
0x1c00d3a76  test    al, 8
0x1c00d3a78  jnz     loc_1C00FC0A5
0x1c00d3a7e  call    cs:__imp_KeEnterCriticalRegion
0x1c00d3a85  nop     dword ptr [rax+rax+00h]
0x1c00d3a8a  mov     rcx, [r13+118h]
0x1c00d3a91  xor     edx, edx
0x1c00d3a93  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1c00d3a9a  nop     dword ptr [rax+rax+00h]
0x1c00d3a9f  cmp     byte ptr [r14+5], 0
0x1c00d3aa4  mov     r15, rax
0x1c00d3aa7  jnz     loc_1C00FC0B8
0x1c00d3aad  lea     r8, [rbp+P]
0x1c00d3ab1  mov     rdx, r13
0x1c00d3ab4  mov     rcx, rdi
0x1c00d3ab7  call    UlpOpenCoupling
0x1c00d3abc  mov     ebx, eax
0x1c00d3abe  test    eax, eax
0x1c00d3ac0  js      loc_1C00D3B55
0x1c00d3ac6  call    cs:__imp_KeEnterCriticalRegion
0x1c00d3acd  nop     dword ptr [rax+rax+00h]
0x1c00d3ad2  mov     rcx, [rbp+P]
0x1c00d3ad6  xor     edx, edx
0x1c00d3ad8  add     rcx, 38h ; '8'
0x1c00d3adc  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c00d3ae3  nop     dword ptr [rax+rax+00h]
0x1c00d3ae8  mov     rcx, [rbp+P]
0x1c00d3aec  cmp     byte ptr [rcx+40h], 0
0x1c00d3af0  jnz     loc_1C00FC0C2
0x1c00d3af6  mov     [rsi+78h], rcx
0x1c00d3afa  lock inc dword ptr [rcx]
0x1c00d3afd  lea     rcx, [rbp+var_8]
0x1c00d3b01  call    UlAttachGrip
0x1c00d3b06  mov     rcx, [rbp+P]
0x1c00d3b0a  lea     r8, UlpCancelWaitForDisconnectIrp
0x1c00d3b11  add     rcx, 70h ; 'p'; SpinLock
0x1c00d3b15  mov     rdx, rsi
0x1c00d3b18  call    UlSiqEnqueueIrp
0x1c00d3b1d  mov     rcx, [rbp+P]; P
0x1c00d3b21  mov     ebx, eax
0x1c00d3b23  test    eax, eax
0x1c00d3b25  js      loc_1C00FC0CC
0x1c00d3b2b  or      dword ptr [rdi+208h], 20h
0x1c00d3b32  mov     ebx, 103h
0x1c00d3b37  add     rcx, 38h ; '8'
0x1c00d3b3b  xor     edx, edx
0x1c00d3b3d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00d3b44  nop     dword ptr [rax+rax+00h]
0x1c00d3b49  call    cs:__imp_KeLeaveCriticalRegion
0x1c00d3b50  nop     dword ptr [rax+rax+00h]
0x1c00d3b55  xor     edx, edx
0x1c00d3b57  mov     rcx, r15
0x1c00d3b5a  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1c00d3b61  nop     dword ptr [rax+rax+00h]
0x1c00d3b66  call    cs:__imp_KeLeaveCriticalRegion
0x1c00d3b6d  nop     dword ptr [rax+rax+00h]
0x1c00d3b72  xor     edx, edx
0x1c00d3b74  mov     rcx, r12
0x1c00d3b77  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c00d3b7e  nop     dword ptr [rax+rax+00h]
0x1c00d3b83  call    cs:__imp_KeLeaveCriticalRegion
0x1c00d3b8a  nop     dword ptr [rax+rax+00h]
0x1c00d3b8f  mov     rcx, [rbp+P]; P
0x1c00d3b93  test    rcx, rcx
0x1c00d3b96  jz      short loc_1C00D3BB0
0x1c00d3b98  or      eax, 0FFFFFFFFh
0x1c00d3b9b  lock xadd [rcx], eax
0x1c00d3b9f  cmp     eax, 1
0x1c00d3ba2  jnz     short loc_1C00D3BAB
0x1c00d3ba4  xor     edx, edx
0x1c00d3ba6  call    UlpFreeCoupling
0x1c00d3bab  and     [rbp+P], 0
0x1c00d3bb0  lea     rcx, [rbp+var_8]
0x1c00d3bb4  call    UlFreeGrip
0x1c00d3bb9  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00d3bbf  test    al, al
0x1c00d3bc1  js      loc_1C00FC103
0x1c00d3bc7  lea     r11, [rsp+50h+var_s0]
0x1c00d3bcc  mov     eax, ebx
0x1c00d3bce  mov     rbx, [r11+38h]
0x1c00d3bd2  mov     rsi, [r11+40h]
0x1c00d3bd6  mov     rdi, [r11+48h]
0x1c00d3bda  mov     rsp, r11
0x1c00d3bdd  pop     r15
0x1c00d3bdf  pop     r14
0x1c00d3be1  pop     r13
0x1c00d3be3  pop     r12
0x1c00d3be5  pop     rbp
0x1c00d3be6  retn
0x1c00fc062  test    rdi, rdi
0x1c00fc065  jz      short loc_1C00FC06D
0x1c00fc067  mov     rcx, [rdx+18h]
0x1c00fc06b  jmp     short loc_1C00FC06F
0x1c00fc06d  xor     ecx, ecx
0x1c00fc06f  mov     [rsp+50h+var_20], rsi
0x1c00fc074  mov     r9, rdi
0x1c00fc077  mov     [rsp+50h+var_28], r15d
0x1c00fc07c  mov     r8, r14
0x1c00fc07f  mov     [rsp+50h+var_30], rcx
0x1c00fc084  call    WPP_SF_qqilq
0x1c00fc089  nop
0x1c00fc08a  jmp     loc_1C00D3A10
0x1c00fc08f  mov     eax, [rdi+208h]
0x1c00fc095  and     eax, 50h
0x1c00fc098  cmp     al, 50h ; 'P'
0x1c00fc09a  jz      loc_1C00D3B72
0x1c00fc0a0  jmp     loc_1C00D3A70
0x1c00fc0a5  test    r15b, r15b
0x1c00fc0a8  jz      loc_1C00D3B72
0x1c00fc0ae  mov     ebx, 0C000020Ch
0x1c00fc0b3  jmp     loc_1C00D3B72
0x1c00fc0b8  mov     ebx, 0C0000184h
0x1c00fc0bd  jmp     loc_1C00D3B55
0x1c00fc0c2  mov     ebx, 0C0000184h
0x1c00fc0c7  jmp     loc_1C00D3B37
0x1c00fc0cc  and     qword ptr [rsi+78h], 0
0x1c00fc0d1  or      eax, 0FFFFFFFFh
0x1c00fc0d4  lock xadd [rcx], eax
0x1c00fc0d8  cmp     eax, 1
0x1c00fc0db  jnz     short loc_1C00FC0E4
0x1c00fc0dd  xor     edx, edx
0x1c00fc0df  call    UlpFreeCoupling
0x1c00fc0e4  mov     rdx, rsi
0x1c00fc0e7  lea     rcx, [rbp+var_8]
0x1c00fc0eb  call    UlDetachGrip
0x1c00fc0f0  mov     rcx, [rbp+P]
0x1c00fc0f4  jmp     loc_1C00D3B37
0x1c00fc0f9  mov     ebx, 0C0000084h
0x1c00fc0fe  jmp     loc_1C00D3B72
0x1c00fc103  mov     ecx, 0CEh
0x1c00fc108  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00fc10f  mov     r8d, ebx
0x1c00fc112  call    WPP_SF_D
0x1c00fc117  nop
0x1c00fc118  jmp     loc_1C00D3BC7
```
