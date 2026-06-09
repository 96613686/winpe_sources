# UcpOpenClientSession

- ea: `0x1c0153bdc`
- end: `0x1c0153ddf`
- name: `UcpOpenClientSession`
- size: `515`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c0057788`

## callees

- `0x1c0057c10`
- `0x1c008f374`
- `0x1c009e6f8`
- `0x1c00a5768`
- `0x1c0153300`
- `0x1c01535dc`
- `0x1c0153aec`
- `0x1c0153bdc`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c0153d08`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c0153d4b`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c0153d08`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c0153d4b`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c0153cc4`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c0153cc4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c0153d25`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c0153d68`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c0153d25`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c0153d68`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0153c74`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0153c74`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0153d14`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0153d31`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0153d57`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0153d74`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0153d14`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0153d31`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0153d57`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0153d74`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0153c5c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0153cb4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0153c5c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0153cb4`

## pseudocode

```c
__int64 __fastcall UcpOpenClientSession(
        __int64 a1,
        __int64 a2,
        struct _ACCESS_STATE *a3,
        ACCESS_MASK a4,
        __int64 a5,
        PVOID *a6)
{
  volatile signed __int32 *v6; // r10
  PVOID *v11; // r14
  __int64 v12; // r15
  int v13; // ebx
  __int64 v14; // rbp
  __int64 ClientSession; // rdi
  PVOID P; // [rsp+78h] [rbp+10h] BYREF

  v6 = 0;
  P = 0;
  v11 = a6;
  v12 = a5;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x10000000) != 0 )
  {
    WPP_SF_qZqDqq(a1, a2, a1, a2, (char)a3, a4, a5, (char)a6);
    v6 = (volatile signed __int32 *)P;
  }
  *v11 = 0;
  if ( *(_QWORD *)(a2 + 8) )
  {
    KeEnterCriticalRegion();
    v14 = a1 + 7624;
    ExAcquirePushLockExclusiveEx(a1 + 7624, 0);
    ClientSession = UcpFindClientSession(a1, a2);
    if ( ClientSession )
    {
      v13 = UcpAllocateClientSessionContext(v12, &P);
      if ( v13 >= 0 )
      {
        KeEnterCriticalRegion();
        ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(ClientSession + 112));
        v13 = UlAccessCheck(
                *(PSECURITY_DESCRIPTOR *)(ClientSession + 8),
                a3,
                a4,
                *(_BYTE *)(v12 + 64),
                *(_QWORD *)(a2 + 8),
                0);
        if ( v13 >= 0 )
        {
          UcpCoupleSessionContextAndSession(P, ClientSession);
          ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(ClientSession + 112));
          KeLeaveCriticalRegion();
          ExReleasePushLockExclusiveEx(v14, 0);
          KeLeaveCriticalRegion();
          *v11 = P;
          goto LABEL_14;
        }
        ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(ClientSession + 112));
        KeLeaveCriticalRegion();
      }
    }
    else
    {
      v13 = -1073741772;
    }
    ExReleasePushLockExclusiveEx(v14, 0);
    KeLeaveCriticalRegion();
    v6 = (volatile signed __int32 *)P;
  }
  else
  {
    v13 = -1073741811;
  }
  if ( !v6 )
    goto LABEL_15;
  _InterlockedDecrement(v6);
  UcpFreeClientSessionContext(P);
LABEL_14:
  P = 0;
LABEL_15:
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x10000000) != 0 )
    WPP_SF_D(23, WPP_f62b8c1d254e300ad0c1fbfd2cbd38f2_Traceguids);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1c0153bdc  mov     rax, rsp
0x1c0153bdf  mov     [rax+8], rbx
0x1c0153be3  mov     [rax+18h], rbp
0x1c0153be7  mov     [rax+20h], rsi
0x1c0153beb  push    rdi
0x1c0153bec  push    r12
0x1c0153bee  push    r13
0x1c0153bf0  push    r14
0x1c0153bf2  push    r15
0x1c0153bf4  sub     rsp, 40h
0x1c0153bf8  xor     r10d, r10d
0x1c0153bfb  mov     r12d, r9d
0x1c0153bfe  mov     [rax+10h], r10
0x1c0153c02  mov     r13, r8
0x1c0153c05  mov     rsi, rdx
0x1c0153c08  mov     rbx, rcx
0x1c0153c0b  test    dword ptr cs:WPP_MAIN_CB.Queue, 10000000h
0x1c0153c15  mov     r14, [rsp+68h+arg_28]
0x1c0153c1d  mov     r15, [rsp+68h+arg_20]
0x1c0153c25  jz      short loc_1C0153C47
0x1c0153c27  mov     [rax-30h], r14
0x1c0153c2b  mov     [rax-38h], r15
0x1c0153c2f  mov     [rax-40h], r9d
0x1c0153c33  mov     r9, rdx
0x1c0153c36  mov     [rax-48h], r8
0x1c0153c3a  mov     r8, rcx
0x1c0153c3d  call    WPP_SF_qZqDqq
0x1c0153c42  mov     r10, [rsp+68h+P]
0x1c0153c47  and     qword ptr [r14], 0
0x1c0153c4b  cmp     qword ptr [rsi+8], 0
0x1c0153c50  jnz     short loc_1C0153C5C
0x1c0153c52  mov     ebx, 0C000000Dh
0x1c0153c57  jmp     loc_1C0153D85
0x1c0153c5c  call    cs:__imp_KeEnterCriticalRegion
0x1c0153c63  nop     dword ptr [rax+rax+00h]
0x1c0153c68  lea     rbp, [rbx+1DC8h]
0x1c0153c6f  xor     edx, edx
0x1c0153c71  mov     rcx, rbp
0x1c0153c74  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c0153c7b  nop     dword ptr [rax+rax+00h]
0x1c0153c80  mov     rdx, rsi
0x1c0153c83  mov     rcx, rbx
0x1c0153c86  call    UcpFindClientSession
0x1c0153c8b  mov     rdi, rax
0x1c0153c8e  test    rax, rax
0x1c0153c91  jnz     short loc_1C0153C9D
0x1c0153c93  mov     ebx, 0C0000034h
0x1c0153c98  jmp     loc_1C0153D63
0x1c0153c9d  lea     rdx, [rsp+68h+P]
0x1c0153ca2  mov     rcx, r15
0x1c0153ca5  call    UcpAllocateClientSessionContext
0x1c0153caa  mov     ebx, eax
0x1c0153cac  test    eax, eax
0x1c0153cae  js      loc_1C0153D63
0x1c0153cb4  call    cs:__imp_KeEnterCriticalRegion
0x1c0153cbb  nop     dword ptr [rax+rax+00h]
0x1c0153cc0  mov     rcx, [rdi+70h]
0x1c0153cc4  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1c0153ccb  nop     dword ptr [rax+rax+00h]
0x1c0153cd0  mov     rax, [rsi+8]
0x1c0153cd4  mov     r8d, r12d; DesiredAccess
0x1c0153cd7  mov     r9b, [r15+40h]; AccessMode
0x1c0153cdb  mov     rdx, r13; AccessState
0x1c0153cde  mov     rcx, [rdi+8]; SecurityDescriptor
0x1c0153ce2  mov     [rsp+68h+var_40], 0; char
0x1c0153ce7  mov     [rsp+68h+var_48], rax; __int64
0x1c0153cec  call    UlAccessCheck
0x1c0153cf1  mov     ebx, eax
0x1c0153cf3  test    eax, eax
0x1c0153cf5  js      short loc_1C0153D47
0x1c0153cf7  mov     rcx, [rsp+68h+P]
0x1c0153cfc  mov     rdx, rdi
0x1c0153cff  call    UcpCoupleSessionContextAndSession
0x1c0153d04  mov     rcx, [rdi+70h]
0x1c0153d08  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1c0153d0f  nop     dword ptr [rax+rax+00h]
0x1c0153d14  call    cs:__imp_KeLeaveCriticalRegion
0x1c0153d1b  nop     dword ptr [rax+rax+00h]
0x1c0153d20  xor     edx, edx
0x1c0153d22  mov     rcx, rbp
0x1c0153d25  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c0153d2c  nop     dword ptr [rax+rax+00h]
0x1c0153d31  call    cs:__imp_KeLeaveCriticalRegion
0x1c0153d38  nop     dword ptr [rax+rax+00h]
0x1c0153d3d  mov     rax, [rsp+68h+P]
0x1c0153d42  mov     [r14], rax
0x1c0153d45  jmp     short loc_1C0153D98
0x1c0153d47  mov     rcx, [rdi+70h]
0x1c0153d4b  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1c0153d52  nop     dword ptr [rax+rax+00h]
0x1c0153d57  call    cs:__imp_KeLeaveCriticalRegion
0x1c0153d5e  nop     dword ptr [rax+rax+00h]
0x1c0153d63  xor     edx, edx
0x1c0153d65  mov     rcx, rbp
0x1c0153d68  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c0153d6f  nop     dword ptr [rax+rax+00h]
0x1c0153d74  call    cs:__imp_KeLeaveCriticalRegion
0x1c0153d7b  nop     dword ptr [rax+rax+00h]
0x1c0153d80  mov     r10, [rsp+68h+P]
0x1c0153d85  test    r10, r10
0x1c0153d88  jz      short loc_1C0153D9E
0x1c0153d8a  lock dec dword ptr [r10]
0x1c0153d8e  mov     rcx, [rsp+68h+P]; P
0x1c0153d93  call    UcpFreeClientSessionContext
0x1c0153d98  and     [rsp+68h+P], 0
0x1c0153d9e  test    dword ptr cs:WPP_MAIN_CB.Queue, 10000000h
0x1c0153da8  jz      short loc_1C0153DBE
0x1c0153daa  mov     ecx, 17h
0x1c0153daf  lea     rdx, WPP_f62b8c1d254e300ad0c1fbfd2cbd38f2_Traceguids
0x1c0153db6  mov     r8d, ebx
0x1c0153db9  call    WPP_SF_D
0x1c0153dbe  lea     r11, [rsp+68h+var_28]
0x1c0153dc3  mov     eax, ebx
0x1c0153dc5  mov     rbx, [r11+30h]
0x1c0153dc9  mov     rbp, [r11+40h]
0x1c0153dcd  mov     rsi, [r11+48h]
0x1c0153dd1  mov     rsp, r11
0x1c0153dd4  pop     r15
0x1c0153dd6  pop     r14
0x1c0153dd8  pop     r13
0x1c0153dda  pop     r12
0x1c0153ddc  pop     rdi
0x1c0153ddd  retn
```
