# CFICache::GetFontInfoFromFaceName(short,CFontOptions const &,CCharFlags *,FONTINFO_FLAGS *)

- ea: `0x180010e6c`
- end: `0x18001102a`
- name: `?GetFontInfoFromFaceName@CFICache@@SAJFAEBVCFontOptions@@PEAVCCharFlags@@PEATFONTINFO_FLAGS@@@Z`
- size: `446`
- prototype: `static int(__int16, const struct CFontOptions *, struct CCharFlags *, union FONTINFO_FLAGS *)`
- caller_count: `20`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c7f8`
- `0x18001ce7c`
- `0x180027500`
- `0x18003098c`
- `0x180032968`
- `0x180045018`
- `0x18009c09c`
- `0x1800aa25c`
- `0x1800aa9f0`
- `0x1800aaf6c`
- `0x1800abcf0`
- `0x1800b49c4`
- `0x1800b6598`
- `0x1800cd63c`
- `0x1800f7048`
- `0x18010348c`
- `0x18013a794`
- `0x18017d50c`
- `0x18017da00`
- `0x1801e112c`

## callees

- `0x180010e6c`
- `0x180011030`
- `0x180057560`
- `0x18005912c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010fcf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010fcf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010fb4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010fb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010f47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010fdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010f47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010fdb`

## pseudocode

```c
__int64 __fastcall CFICache::GetFontInfoFromFaceName(
        __int16 a1,
        const struct CFontOptions *a2,
        struct CCharFlags *a3,
        union FONTINFO_FLAGS *a4)
{
  __int64 v4; // rbp
  unsigned int v8; // esi
  char v9; // al
  int v11; // r14d
  _DWORD *LockTelemetry; // rax
  RTL_SRWLOCK *v13; // rax
  RTL_SRWLOCK *Lock; // rax
  __int64 v15; // rax
  _OWORD v16[5]; // [rsp+30h] [rbp-58h] BYREF
  __int16 v17; // [rsp+90h] [rbp+8h] BYREF

  v4 = a1;
  if ( a1 < 0 || a1 >= CFICache::_cFontInfo + 70 )
  {
    if ( a3 )
    {
      *(_QWORD *)a3 = 0;
      *((_QWORD *)a3 + 1) = 0;
    }
    if ( a4 )
      *(_WORD *)a4 = 0;
    return 2147942487LL;
  }
  else
  {
    v16[0] = 0u;
    v8 = 1;
    v17 = 0;
    if ( a1 >= 70 )
    {
      v11 = (int)CLockSharedData::LockOwner;
      if ( (_DWORD)CLockSharedData::LockOwner && v11 == GetCurrentThreadId() )
      {
        LockTelemetry = (_DWORD *)CLock::GetLockTelemetry(0);
        ++*LockTelemetry;
      }
      else
      {
        Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
        AcquireSRWLockExclusive(Lock);
        LODWORD(CLockSharedData::LockOwner) = GetCurrentThreadId();
        v15 = CLock::GetLockTelemetry(0);
        ++*(_DWORD *)(v15 + 4);
      }
      ++g_cFCLock;
      CFICache::GetFontInfoFromFaceNameHelper(
        (struct FONTINFO *)CFICache::_pFontInfo + 2 * v4 - 140,
        v4,
        a2,
        (union FONTINFO_FLAGS *)&v17,
        (struct CCharFlags *)v16);
      --g_cFCLock;
      if ( (int)CLockSharedData::LockTelemetry > 0 )
      {
        LODWORD(CLockSharedData::LockTelemetry) = (_DWORD)CLockSharedData::LockTelemetry - 1;
      }
      else
      {
        LODWORD(CLockSharedData::LockOwner) = 0;
        v13 = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
        ReleaseSRWLockExclusive(v13);
      }
    }
    else
    {
      CFICache::GetFontInfoFromFaceNameHelper(
        (FONTINFO *)((char *)&CFICache::_PredefFontInfo + 48 * a1),
        a1,
        a2,
        (union FONTINFO_FLAGS *)&v17,
        (struct CCharFlags *)v16);
    }
    if ( a3 )
      *(_OWORD *)a3 = v16[0];
    v9 = v17;
    if ( a4 )
      *(_WORD *)a4 = v17;
    if ( v16[0] != 0 && (v9 & 2) == 0 )
      return 0;
    return v8;
  }
}

```

## disassembly

```asm
0x180010e6c  mov     r11, rsp
0x180010e6f  push    rbx
0x180010e70  push    rbp
0x180010e71  push    rsi
0x180010e72  push    rdi
0x180010e73  push    r12
0x180010e75  push    r13
0x180010e77  push    r14
0x180010e79  push    r15
0x180010e7b  sub     rsp, 48h
0x180010e7f  movsx   rbp, cx
0x180010e83  xor     r13d, r13d
0x180010e86  mov     rdi, r9
0x180010e89  mov     rbx, r8
0x180010e8c  mov     r12, rdx
0x180010e8f  test    bp, bp
0x180010e92  js      loc_180011009
0x180010e98  movsx   eax, cs:?_cFontInfo@CFICache@@0FA; short CFICache::_cFontInfo
0x180010e9f  lea     ecx, [r13+46h]
0x180010ea3  add     eax, ecx
0x180010ea5  cmp     ebp, eax
0x180010ea7  jge     loc_180011009
0x180010ead  mov     [r11-58h], r13
0x180010eb1  lea     esi, [rcx-45h]
0x180010eb4  mov     [r11-50h], r13
0x180010eb8  mov     [r11+8], r13w
0x180010ebd  cmp     bp, cx
0x180010ec0  jge     short loc_180010F3B
0x180010ec2  lea     rax, ?_PredefFontInfo@CFICache@@0PAUFONTINFO@@A; FONTINFO near * CFICache::_PredefFontInfo
0x180010ec9  mov     r8, rdx; struct CFontOptions *
0x180010ecc  lea     rcx, ds:0[rbp*2]
0x180010ed4  movzx   edx, bp; __int16
0x180010ed7  add     rcx, rbp
0x180010eda  lea     r9, [r11+8]; union FONTINFO_FLAGS *
0x180010ede  shl     rcx, 4
0x180010ee2  add     rcx, rax; struct FONTINFO *
0x180010ee5  lea     rax, [r11-58h]
0x180010ee9  mov     [r11-68h], rax
0x180010eed  call    ?GetFontInfoFromFaceNameHelper@CFICache@@CAXAEAUFONTINFO@@FAEBVCFontOptions@@AEATFONTINFO_FLAGS@@AEAVCCharFlags@@@Z; CFICache::GetFontInfoFromFaceNameHelper(FONTINFO &,short,CFontOptions const &,FONTINFO_FLAGS &,CCharFlags &)
0x180010ef2  test    rbx, rbx
0x180010ef5  jz      short loc_180010F00
0x180010ef7  movups  xmm0, [rsp+88h+var_58]
0x180010efc  movdqu  xmmword ptr [rbx], xmm0
0x180010f00  movzx   eax, [rsp+88h+arg_0]
0x180010f08  test    rdi, rdi
0x180010f0b  jz      short loc_180010F10
0x180010f0d  mov     [rdi], ax
0x180010f10  cmp     qword ptr [rsp+88h+var_58], r13
0x180010f15  jz      short loc_180010F20
0x180010f17  test    al, 2
0x180010f19  jnz     short loc_180010F27
0x180010f1b  mov     esi, r13d
0x180010f1e  jmp     short loc_180010F27
0x180010f20  cmp     qword ptr [rsp+88h+var_58+8], r13
0x180010f25  jnz     short loc_180010F17
0x180010f27  mov     eax, esi
0x180010f29  add     rsp, 48h
0x180010f2d  pop     r15
0x180010f2f  pop     r14
0x180010f31  pop     r13
0x180010f33  pop     r12
0x180010f35  pop     rdi
0x180010f36  pop     rsi
0x180010f37  pop     rbp
0x180010f38  pop     rbx
0x180010f39  retn
0x180010f3b  mov     r14d, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x180010f42  test    r14d, r14d
0x180010f45  jz      short loc_180010FC5
0x180010f47  call    cs:__imp_GetCurrentThreadId
0x180010f4e  nop     dword ptr [rax+rax+00h]
0x180010f53  cmp     r14d, eax
0x180010f56  jnz     short loc_180010FC5
0x180010f58  xor     ecx, ecx
0x180010f5a  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x180010f5f  add     [rax], esi
0x180010f61  add     cs:?g_cFCLock@@3JA, esi; long g_cFCLock
0x180010f67  lea     rax, [rbp-46h]
0x180010f6b  imul    rcx, rax, 38h ; '8'
0x180010f6f  lea     rax, [rsp+88h+var_58]
0x180010f74  mov     r8, r12; struct CFontOptions *
0x180010f77  add     rcx, cs:?_pFontInfo@CFICache@@0PEAUFONTINFOEX@@EA; struct FONTINFO *
0x180010f7e  lea     r9, [rsp+88h+arg_0]; union FONTINFO_FLAGS *
0x180010f86  movzx   edx, bp; __int16
0x180010f89  mov     [rsp+88h+var_68], rax; struct CCharFlags *
0x180010f8e  call    ?GetFontInfoFromFaceNameHelper@CFICache@@CAXAEAUFONTINFO@@FAEBVCFontOptions@@AEATFONTINFO_FLAGS@@AEAVCCharFlags@@@Z; CFICache::GetFontInfoFromFaceNameHelper(FONTINFO &,short,CFontOptions const &,FONTINFO_FLAGS &,CCharFlags &)
0x180010f93  sub     cs:?g_cFCLock@@3JA, esi; long g_cFCLock
0x180010f99  mov     eax, cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x180010f9f  test    eax, eax
0x180010fa1  jg      short loc_180010FFC
0x180010fa3  xor     ecx, ecx
0x180010fa5  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, r13d; uint near * CLockSharedData::LockOwner
0x180010fac  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x180010fb1  mov     rcx, rax; SRWLock
0x180010fb4  call    cs:__imp_ReleaseSRWLockExclusive
0x180010fbb  nop     dword ptr [rax+rax+00h]
0x180010fc0  jmp     loc_180010EF2
0x180010fc5  xor     ecx, ecx
0x180010fc7  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x180010fcc  mov     rcx, rax; SRWLock
0x180010fcf  call    cs:__imp_AcquireSRWLockExclusive
0x180010fd6  nop     dword ptr [rax+rax+00h]
0x180010fdb  call    cs:__imp_GetCurrentThreadId
0x180010fe2  nop     dword ptr [rax+rax+00h]
0x180010fe7  xor     ecx, ecx
0x180010fe9  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x180010fef  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x180010ff4  add     [rax+4], esi
0x180010ff7  jmp     loc_180010F61
0x180010ffc  dec     eax
0x180010ffe  mov     cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A, eax; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x180011004  jmp     loc_180010EF2
0x180011009  test    rbx, rbx
0x18001100c  jz      short loc_180011015
0x18001100e  mov     [r8], r13
0x180011011  mov     [r8+8], r13
0x180011015  test    rdi, rdi
0x180011018  jnz     short loc_180011024
0x18001101a  mov     eax, 80070057h
0x18001101f  jmp     loc_180010F29
0x180011024  mov     [r9], r13w
0x180011028  jmp     short loc_18001101A
```
