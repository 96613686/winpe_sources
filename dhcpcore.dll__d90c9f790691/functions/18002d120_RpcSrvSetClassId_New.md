# RpcSrvSetClassId_New

- ea: `0x18002d120`
- end: `0x18002d3a1`
- name: `RpcSrvSetClassId_New`
- size: `641`
- prototype: `__int64 __fastcall(_WORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation`

## callers

- `0x18002ce90`

## callees

- `0x180001c48`
- `0x1800020d0`
- `0x1800021c0`
- `0x180002498`
- `0x180002534`
- `0x18000a654`
- `0x18000eb7c`
- `0x18001ee9c`
- `0x1800251a4`
- `0x18002d120`
- `0x180040eb4`
- `0x180041224`
- `0x180047e30`
- `0x18004a868`
- `0x18004d1a0`
- `0x18004d4c0`
- `0x18004e160`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002d2eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002d2eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002d1e8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002d1e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002d219`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002d219`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002d298`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002d298`

## pseudocode

```c
__int64 __fastcall RpcSrvSetClassId_New(_WORD *a1, __int64 a2, __int64 a3)
{
  CRpcWatchDog *v6; // rcx
  unsigned int v7; // esi
  int v8; // r8d
  unsigned int v9; // edi
  const void *v10; // r14
  unsigned int v11; // eax
  CRpcWatchDog *v12; // rcx
  RTL_SRWLOCK *v13; // rbx
  int v14; // r15d
  int v15; // r8d
  __int64 v16; // rcx
  PVOID Ptr; // rdx
  __int64 v18; // rax
  __int128 v20; // [rsp+30h] [rbp-30h] BYREF
  _OWORD v21[2]; // [rsp+40h] [rbp-20h] BYREF
  RTL_SRWLOCK *v22; // [rsp+A8h] [rbp+48h] BYREF

  v22 = 0;
  memset(v21, 0, sizeof(v21));
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_qq(1028, 126, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, a2, a3);
  v7 = RpcValidateRequests(a1);
  if ( !v7 )
  {
    *(_QWORD *)&v21[0] = RpcSrvSetClassId;
    CRpcWatchDog::AddEntry(v6, (struct _WatchDogEntry *)v21, v8);
    if ( !a3 || (v9 = *(_DWORD *)(a3 + 16)) == 0 || (v10 = *(const void **)(a3 + 8)) == 0 )
    {
      v9 = 0;
      v10 = 0;
    }
    v11 = DhcpFindAndRefContext(a2, &v22);
    v13 = v22;
    v7 = v11;
    if ( !v11 )
    {
      v14 = 0;
      AcquireSRWLockShared(v22 + 84);
      if ( v9 == LODWORD(v13[93].Ptr) && (!v9 || !memcmp_0(v13[92].Ptr, v10, v9)) )
        v14 = 1;
      ReleaseSRWLockShared(v13 + 84);
      if ( !v14 )
      {
        if ( (xmmword_1800616A0 & 0x10) != 0 )
        {
          v20 = (unsigned __int64)v10;
          if ( v10 )
          {
            WORD4(v20) = -1;
            if ( v9 <= 0xFFFF )
              WORD4(v20) = v9;
          }
          else
          {
            WORD4(v20) = 0;
          }
          WPP_SF_Jd_HEX_((_DWORD)v12, 127, v15, v13[3].Ptr, v9, (__int64)&v20);
        }
        v7 = LockDhcpContext(v13, 1);
        if ( !v7 )
        {
          AcquireSRWLockExclusive(v13 + 84);
          Ptr = v13[92].Ptr;
          if ( Ptr )
          {
            DhcpDelClass(v16, Ptr, LODWORD(v13[93].Ptr));
            v13[92].Ptr = 0;
            LODWORD(v13[93].Ptr) = v7;
          }
          if ( v9 )
          {
            v18 = DhcpAddClass(v16, v10, v9);
            v13[92].Ptr = (PVOID)v18;
            if ( v18 )
              LODWORD(v13[93].Ptr) = v9;
          }
          ReleaseSRWLockExclusive(v13 + 84);
          if ( LODWORD(v13[99].Ptr) )
          {
            if ( HIDWORD(v13[247].Ptr) )
              DhcpCancelDAD(v13);
            ScheduleWakeUp(v13, 0);
          }
          UnlockDhcpContext(v13);
        }
      }
    }
    if ( v13 )
    {
      if ( (xmmword_1800616A0 & 0x10) != 0 )
        WPP_SF_q(1028, 128, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v13[3].Ptr);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v13[2], 0xFFFFFFFF) == 1 )
        DhcpDestroyContextEx(v13);
    }
    CRpcWatchDog::RemoveEntry(v12, (struct _WatchDogEntry *)v21);
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 129, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18002d120  mov     [rsp-28h+arg_0], rbx
0x18002d125  mov     [rsp-28h+arg_8], rsi
0x18002d12a  push    rbp
0x18002d12b  push    rdi
0x18002d12c  push    r12
0x18002d12e  push    r14
0x18002d130  push    r15
0x18002d132  mov     rbp, rsp
0x18002d135  sub     rsp, 60h
0x18002d139  xorps   xmm0, xmm0
0x18002d13c  mov     [rbp+arg_18], 0
0x18002d144  movups  [rbp+var_20], xmm0
0x18002d148  mov     rbx, r8
0x18002d14b  mov     r15, rdx
0x18002d14e  movups  [rbp+var_10], xmm0
0x18002d152  mov     rdi, rcx
0x18002d155  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002d15c  jz      short loc_18002D17C
0x18002d15e  mov     edx, 7Eh ; '~'
0x18002d163  mov     [rsp+60h+var_40], rbx
0x18002d168  mov     ecx, 404h
0x18002d16d  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002d174  mov     r9, r15
0x18002d177  call    WPP_SF_qq
0x18002d17c  mov     edx, 4
0x18002d181  mov     rcx, rdi
0x18002d184  call    RpcValidateRequests
0x18002d189  mov     esi, eax
0x18002d18b  test    eax, eax
0x18002d18d  jnz     loc_18002D364
0x18002d193  lea     rax, RpcSrvSetClassId
0x18002d19a  lea     rdx, [rbp+var_20]; struct _WatchDogEntry *
0x18002d19e  mov     qword ptr [rbp+var_20], rax
0x18002d1a2  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x18002d1a7  test    rbx, rbx
0x18002d1aa  jz      short loc_18002D1BC
0x18002d1ac  mov     edi, [rbx+10h]
0x18002d1af  test    edi, edi
0x18002d1b1  jz      short loc_18002D1BC
0x18002d1b3  mov     r14, [rbx+8]
0x18002d1b7  test    r14, r14
0x18002d1ba  jnz     short loc_18002D1C1
0x18002d1bc  xor     edi, edi
0x18002d1be  xor     r14d, r14d
0x18002d1c1  lea     rdx, [rbp+arg_18]
0x18002d1c5  mov     rcx, r15
0x18002d1c8  call    DhcpFindAndRefContext
0x18002d1cd  mov     rbx, [rbp+arg_18]
0x18002d1d1  mov     esi, eax
0x18002d1d3  test    eax, eax
0x18002d1d5  jnz     loc_18002D31E
0x18002d1db  lea     r12, [rbx+2A0h]
0x18002d1e2  xor     r15d, r15d
0x18002d1e5  mov     rcx, r12; SRWLock
0x18002d1e8  call    cs:__imp_AcquireSRWLockShared
0x18002d1ee  cmp     edi, [rbx+2E8h]
0x18002d1f4  jnz     short loc_18002D216
0x18002d1f6  test    edi, edi
0x18002d1f8  jz      short loc_18002D210
0x18002d1fa  mov     rcx, [rbx+2E0h]; Buf1
0x18002d201  mov     rdx, r14; Buf2
0x18002d204  mov     r8d, edi; Size
0x18002d207  call    memcmp_0
0x18002d20c  test    eax, eax
0x18002d20e  jnz     short loc_18002D216
0x18002d210  mov     r15d, 1
0x18002d216  mov     rcx, r12; SRWLock
0x18002d219  call    cs:__imp_ReleaseSRWLockShared
0x18002d21f  test    r15d, r15d
0x18002d222  jnz     loc_18002D31E
0x18002d228  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002d22f  jz      short loc_18002D27E
0x18002d231  xorps   xmm0, xmm0
0x18002d234  movups  [rbp+var_30], xmm0
0x18002d238  mov     qword ptr [rbp+var_30], r14
0x18002d23c  test    r14, r14
0x18002d23f  jnz     short loc_18002D249
0x18002d241  xor     eax, eax
0x18002d243  mov     word ptr [rbp+var_30+8], ax
0x18002d247  jmp     short loc_18002D25A
0x18002d249  mov     eax, 0FFFFh
0x18002d24e  mov     word ptr [rbp+var_30+8], ax
0x18002d252  cmp     edi, eax
0x18002d254  ja      short loc_18002D25A
0x18002d256  mov     word ptr [rbp+var_30+8], di
0x18002d25a  movaps  xmm0, [rbp+var_30]
0x18002d25e  lea     rax, [rbp+var_30]
0x18002d262  movdqa  [rbp+var_30], xmm0
0x18002d267  mov     edx, 7Fh
0x18002d26c  mov     r9, [rbx+18h]
0x18002d270  mov     [rsp+60h+var_38], rax
0x18002d275  mov     dword ptr [rsp+60h+var_40], edi
0x18002d279  call    WPP_SF_Jd_HEX_
0x18002d27e  mov     edx, 1
0x18002d283  mov     rcx, rbx
0x18002d286  call    LockDhcpContext
0x18002d28b  mov     esi, eax
0x18002d28d  test    eax, eax
0x18002d28f  jnz     loc_18002D31E
0x18002d295  mov     rcx, r12; SRWLock
0x18002d298  call    cs:__imp_AcquireSRWLockExclusive
0x18002d29e  mov     rdx, [rbx+2E0h]
0x18002d2a5  test    rdx, rdx
0x18002d2a8  jz      short loc_18002D2C7
0x18002d2aa  mov     r8d, [rbx+2E8h]
0x18002d2b1  call    DhcpDelClass
0x18002d2b6  mov     qword ptr [rbx+2E0h], 0
0x18002d2c1  mov     [rbx+2E8h], esi
0x18002d2c7  test    edi, edi
0x18002d2c9  jz      short loc_18002D2E8
0x18002d2cb  mov     r8d, edi
0x18002d2ce  mov     rdx, r14
0x18002d2d1  call    DhcpAddClass
0x18002d2d6  mov     [rbx+2E0h], rax
0x18002d2dd  test    rax, rax
0x18002d2e0  jz      short loc_18002D2E8
0x18002d2e2  mov     [rbx+2E8h], edi
0x18002d2e8  mov     rcx, r12; SRWLock
0x18002d2eb  call    cs:__imp_ReleaseSRWLockExclusive
0x18002d2f1  mov     eax, [rbx+318h]
0x18002d2f7  test    eax, eax
0x18002d2f9  jz      short loc_18002D316
0x18002d2fb  cmp     dword ptr [rbx+7BCh], 0
0x18002d302  jz      short loc_18002D30C
0x18002d304  mov     rcx, rbx
0x18002d307  call    DhcpCancelDAD
0x18002d30c  xor     edx, edx
0x18002d30e  mov     rcx, rbx
0x18002d311  call    ScheduleWakeUp
0x18002d316  mov     rcx, rbx
0x18002d319  call    UnlockDhcpContext
0x18002d31e  test    rbx, rbx
0x18002d321  jz      short loc_18002D35B
0x18002d323  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002d32a  jz      short loc_18002D346
0x18002d32c  mov     r9, [rbx+18h]
0x18002d330  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002d337  mov     edx, 80h
0x18002d33c  mov     ecx, 404h
0x18002d341  call    WPP_SF_q
0x18002d346  or      eax, 0FFFFFFFFh
0x18002d349  lock xadd [rbx+10h], eax
0x18002d34e  cmp     eax, 1
0x18002d351  jnz     short loc_18002D35B
0x18002d353  mov     rcx, rbx
0x18002d356  call    DhcpDestroyContextEx
0x18002d35b  lea     rdx, [rbp+var_20]; struct _WatchDogEntry *
0x18002d35f  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18002d364  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002d36b  jz      short loc_18002D386
0x18002d36d  mov     edx, 81h
0x18002d372  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002d379  mov     ecx, 404h
0x18002d37e  mov     r9d, esi
0x18002d381  call    WPP_SF_D
0x18002d386  lea     r11, [rsp+60h+var_s0]
0x18002d38b  mov     eax, esi
0x18002d38d  mov     rbx, [r11+30h]
0x18002d391  mov     rsi, [r11+38h]
0x18002d395  mov     rsp, r11
0x18002d398  pop     r15
0x18002d39a  pop     r14
0x18002d39c  pop     r12
0x18002d39e  pop     rdi
0x18002d39f  pop     rbp
0x18002d3a0  retn
```
