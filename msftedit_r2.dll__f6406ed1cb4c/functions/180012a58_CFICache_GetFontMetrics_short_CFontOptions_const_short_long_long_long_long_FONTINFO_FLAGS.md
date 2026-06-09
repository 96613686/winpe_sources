# CFICache::GetFontMetrics(short,CFontOptions const &,short,long,long &,long &,long &,FONTINFO_FLAGS &)

- ea: `0x180012a58`
- end: `0x180012c3f`
- name: `?GetFontMetrics@CFICache@@SAHFAEBVCFontOptions@@FJAEAJ11AEATFONTINFO_FLAGS@@@Z`
- size: `487`
- prototype: `static int(__int16, const struct CFontOptions *, __int16, int, int *, int *, int *, union FONTINFO_FLAGS *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180127944`
- `0x18018e0c0`

## callees

- `0x18000f430`
- `0x180011030`
- `0x180012a58`
- `0x180055b34`
- `0x180057560`
- `0x18005912c`
- `0x18005921c`
- `0x18017d460`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012b7b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012b7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012b15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012b87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012b15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012b87`

## pseudocode

```c
__int64 __fastcall CFICache::GetFontMetrics(
        __int16 a1,
        const struct CFontOptions *a2,
        __int16 a3,
        int a4,
        int *a5,
        int *a6,
        int *a7,
        union FONTINFO_FLAGS *a8)
{
  int v8; // ebx
  int v9; // r12d
  unsigned __int16 v12; // ax
  int v14; // edi
  _DWORD *LockTelemetry; // rax
  RTL_SRWLOCK *Lock; // rax
  __int64 v17; // rax
  unsigned __int16 FontEMSquare; // ax
  int v19; // ebx
  int v20; // edi
  int v21; // r11d
  int v22; // r11d
  int v23; // r11d
  unsigned __int16 v24[2]; // [rsp+30h] [rbp-28h] BYREF
  unsigned __int16 v25[2]; // [rsp+34h] [rbp-24h] BYREF
  _QWORD v26[4]; // [rsp+38h] [rbp-20h] BYREF
  unsigned __int16 v27; // [rsp+A0h] [rbp+48h] BYREF

  v8 = a1;
  v9 = a3;
  if ( a1 < 0 || a1 >= CFICache::_cFontInfo + 70 )
    return 0;
  v26[0] = 0;
  v26[1] = 0;
  v27 = 0;
  if ( a1 >= 70 )
  {
    v14 = (int)CLockSharedData::LockOwner;
    *(_DWORD *)v25 = 0;
    if ( (_DWORD)CLockSharedData::LockOwner && v14 == GetCurrentThreadId() )
    {
      LockTelemetry = (_DWORD *)CLock::GetLockTelemetry(0);
      ++*LockTelemetry;
    }
    else
    {
      Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
      AcquireSRWLockExclusive(Lock);
      LODWORD(CLockSharedData::LockOwner) = GetCurrentThreadId();
      v17 = CLock::GetLockTelemetry(0);
      ++*(_DWORD *)(v17 + 4);
    }
    ++g_cFCLock;
    CFICache::GetFontInfoFromFaceNameHelper(
      (struct FONTINFO *)CFICache::_pFontInfo + 2 * v8 - 140,
      v8,
      a2,
      (union FONTINFO_FLAGS *)&v27,
      (struct CCharFlags *)v26);
    --g_cFCLock;
    CWriteLock::~CWriteLock((CWriteLock *)v25);
  }
  else
  {
    CFICache::GetFontInfoFromFaceNameHelper(
      (FONTINFO *)((char *)&CFICache::_PredefFontInfo + 48 * a1),
      a1,
      a2,
      (union FONTINFO_FLAGS *)&v27,
      (struct CCharFlags *)v26);
  }
  v12 = v27;
  *(_WORD *)a8 = v27;
  if ( (v12 & 0x100) == 0 && (v12 & 0x2000) == 0 )
    return 0;
  v25[0] = 0;
  v24[0] = 0;
  v27 = 0;
  CFICache::GetFontInfoMetrics(v8, v25, v24, &v27);
  FontEMSquare = CFICache::GetFontEMSquare(v8);
  v19 = v27;
  v20 = v24[0];
  v21 = FontEMSquare;
  if ( a4 == 914400 )
    a4 = 635;
  else
    v21 = 1440 * FontEMSquare;
  *a5 = CW32System::MulDivFunc(v25[0], a4 * v9, v21);
  *a6 = CW32System::MulDivFunc(v20, a4 * v9, v22);
  *a7 = CW32System::MulDivFunc(v19, a4 * v9, v23);
  return 1;
}

```

## disassembly

```asm
0x180012a58  push    rbp
0x180012a5a  push    rbx
0x180012a5b  push    rsi
0x180012a5c  push    rdi
0x180012a5d  push    r12
0x180012a5f  push    r13
0x180012a61  push    r14
0x180012a63  push    r15
0x180012a65  mov     rbp, rsp
0x180012a68  sub     rsp, 58h
0x180012a6c  movsx   rbx, cx
0x180012a70  xor     r13d, r13d
0x180012a73  movsx   r12d, r8w
0x180012a77  mov     r14d, r9d
0x180012a7a  mov     r15, rdx
0x180012a7d  test    bx, bx
0x180012a80  js      short loc_180012AF3
0x180012a82  movsx   eax, cs:?_cFontInfo@CFICache@@0FA; short CFICache::_cFontInfo
0x180012a89  lea     ecx, [r13+46h]
0x180012a8d  add     eax, ecx
0x180012a8f  cmp     ebx, eax
0x180012a91  jge     short loc_180012AF3
0x180012a93  mov     [rbp+var_20], r13
0x180012a97  mov     [rbp+var_18], r13
0x180012a9b  mov     [rbp+arg_0], r13w
0x180012aa0  cmp     bx, cx
0x180012aa3  jge     short loc_180012B07
0x180012aa5  lea     rax, ?_PredefFontInfo@CFICache@@0PAUFONTINFO@@A; FONTINFO near * CFICache::_PredefFontInfo
0x180012aac  mov     r8, rdx; struct CFontOptions *
0x180012aaf  lea     rcx, [rbx+rbx*2]
0x180012ab3  movzx   edx, bx; __int16
0x180012ab6  shl     rcx, 4
0x180012aba  lea     r9, [rbp+arg_0]; union FONTINFO_FLAGS *
0x180012abe  add     rcx, rax; struct FONTINFO *
0x180012ac1  lea     rax, [rbp+var_20]
0x180012ac5  mov     [rsp+58h+var_38], rax; struct CCharFlags *
0x180012aca  call    ?GetFontInfoFromFaceNameHelper@CFICache@@CAXAEAUFONTINFO@@FAEBVCFontOptions@@AEATFONTINFO_FLAGS@@AEAVCCharFlags@@@Z; CFICache::GetFontInfoFromFaceNameHelper(FONTINFO &,short,CFontOptions const &,FONTINFO_FLAGS &,CCharFlags &)
0x180012acf  movzx   eax, [rbp+arg_0]
0x180012ad3  bt      ax, 8
0x180012ad8  mov     rcx, [rbp+arg_38]
0x180012adf  mov     [rcx], ax
0x180012ae2  jb      loc_180012BA5
0x180012ae8  bt      ax, 0Dh
0x180012aed  jb      loc_180012BA5
0x180012af3  xor     eax, eax
0x180012af5  add     rsp, 58h
0x180012af9  pop     r15
0x180012afb  pop     r14
0x180012afd  pop     r13
0x180012aff  pop     r12
0x180012b01  pop     rdi
0x180012b02  pop     rsi
0x180012b03  pop     rbx
0x180012b04  pop     rbp
0x180012b05  retn
0x180012b07  mov     edi, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x180012b0d  mov     dword ptr [rbp+var_24], r13d
0x180012b11  test    edi, edi
0x180012b13  jz      short loc_180012B71
0x180012b15  call    cs:__imp_GetCurrentThreadId
0x180012b1c  nop     dword ptr [rax+rax+00h]
0x180012b21  cmp     edi, eax
0x180012b23  jnz     short loc_180012B71
0x180012b25  xor     ecx, ecx
0x180012b27  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x180012b2c  inc     dword ptr [rax]
0x180012b2e  inc     cs:?g_cFCLock@@3JA; long g_cFCLock
0x180012b34  lea     eax, [rbx-46h]
0x180012b37  movsxd  rcx, eax
0x180012b3a  lea     r9, [rbp+arg_0]; union FONTINFO_FLAGS *
0x180012b3e  imul    rcx, 38h ; '8'
0x180012b42  lea     rax, [rbp+var_20]
0x180012b46  mov     r8, r15; struct CFontOptions *
0x180012b49  add     rcx, cs:?_pFontInfo@CFICache@@0PEAUFONTINFOEX@@EA; struct FONTINFO *
0x180012b50  movzx   edx, bx; __int16
0x180012b53  mov     [rsp+58h+var_38], rax; struct CCharFlags *
0x180012b58  call    ?GetFontInfoFromFaceNameHelper@CFICache@@CAXAEAUFONTINFO@@FAEBVCFontOptions@@AEATFONTINFO_FLAGS@@AEAVCCharFlags@@@Z; CFICache::GetFontInfoFromFaceNameHelper(FONTINFO &,short,CFontOptions const &,FONTINFO_FLAGS &,CCharFlags &)
0x180012b5d  dec     cs:?g_cFCLock@@3JA; long g_cFCLock
0x180012b63  lea     rcx, [rbp+var_24]; this
0x180012b67  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x180012b6c  jmp     loc_180012ACF
0x180012b71  xor     ecx, ecx
0x180012b73  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x180012b78  mov     rcx, rax; SRWLock
0x180012b7b  call    cs:__imp_AcquireSRWLockExclusive
0x180012b82  nop     dword ptr [rax+rax+00h]
0x180012b87  call    cs:__imp_GetCurrentThreadId
0x180012b8e  nop     dword ptr [rax+rax+00h]
0x180012b93  xor     ecx, ecx
0x180012b95  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x180012b9b  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x180012ba0  inc     dword ptr [rax+4]
0x180012ba3  jmp     short loc_180012B2E
0x180012ba5  lea     r9, [rbp+arg_0]; unsigned __int16 *
0x180012ba9  mov     [rbp+var_24], r13w
0x180012bae  lea     r8, [rbp+var_28]; unsigned __int16 *
0x180012bb2  mov     [rbp+var_28], r13w
0x180012bb7  lea     rdx, [rbp+var_24]; unsigned __int16 *
0x180012bbb  mov     [rbp+arg_0], r13w
0x180012bc0  movzx   ecx, bx; __int16
0x180012bc3  call    ?GetFontInfoMetrics@CFICache@@SAXFAEAG00@Z; CFICache::GetFontInfoMetrics(short,ushort &,ushort &,ushort &)
0x180012bc8  movzx   ecx, bx; __int16
0x180012bcb  mov     esi, r12d
0x180012bce  call    ?GetFontEMSquare@CFICache@@SAGF@Z; CFICache::GetFontEMSquare(short)
0x180012bd3  movzx   ebx, [rbp+arg_0]
0x180012bd7  movzx   edi, [rbp+var_28]
0x180012bdb  movzx   ecx, [rbp+var_24]; int
0x180012bdf  movzx   r11d, ax
0x180012be3  cmp     r14d, 0DF3E0h
0x180012bea  jnz     short loc_180012BF4
0x180012bec  mov     r14d, 27Bh
0x180012bf2  jmp     short loc_180012BFB
0x180012bf4  imul    r11d, 5A0h
0x180012bfb  imul    esi, r14d
0x180012bff  mov     r8d, r11d; int
0x180012c02  mov     edx, esi; int
0x180012c04  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x180012c09  mov     r9, [rbp+arg_20]
0x180012c0d  mov     r8d, r11d; int
0x180012c10  mov     edx, esi; int
0x180012c12  mov     ecx, edi; int
0x180012c14  mov     [r9], eax
0x180012c17  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x180012c1c  mov     r9, [rbp+arg_28]
0x180012c20  mov     r8d, r11d; int
0x180012c23  mov     edx, esi; int
0x180012c25  mov     ecx, ebx; int
0x180012c27  mov     [r9], eax
0x180012c2a  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x180012c2f  mov     rcx, [rbp+arg_30]
0x180012c33  mov     [rcx], eax
0x180012c35  mov     eax, 1
0x180012c3a  jmp     loc_180012AF5
```
