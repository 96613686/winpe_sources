# ReleaseControl

- ea: `0x1400d8e60`
- end: `0x1400d92c7`
- name: `ReleaseControl`
- size: `1127`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x1400d87d0`
- `0x1400d89f0`
- `0x1400d8a80`
- `0x1400d8aa8`
- `0x1400eb300`

## callees

- `0x14000b998`
- `0x14002a4e4`
- `0x14002aa38`
- `0x1400d0af0`
- `0x1400d0b64`
- `0x1400d8e60`
- `0x1400d93d0`
- `0x1400dbd50`
- `0x1400dbdd0`
- `0x1400e65a0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d8ef4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d9210`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d8ef4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400d9210`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d900a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d91f4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d900a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d91f4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d8fac`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d9141`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d8fac`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d9141`
- `ntoskrnl!IoFreeMdl` at `0x1400d90c4`
- `ntoskrnl!IoFreeMdl` at `0x1400d90c4`
- `ntoskrnl!KeBugCheckEx` at `0x1400d916f`
- `ntoskrnl!KeBugCheckEx` at `0x1400d9191`
- `ntoskrnl!KeBugCheckEx` at `0x1400d91b4`
- `ntoskrnl!KeBugCheckEx` at `0x1400d91d6`
- `ntoskrnl!KeBugCheckEx` at `0x1400d9274`
- `ntoskrnl!KeBugCheckEx` at `0x1400d9296`
- `ntoskrnl!KeBugCheckEx` at `0x1400d92ba`
- `ntoskrnl!KeBugCheckEx` at `0x1400d916f`
- `ntoskrnl!KeBugCheckEx` at `0x1400d9191`
- `ntoskrnl!KeBugCheckEx` at `0x1400d91b4`
- `ntoskrnl!KeBugCheckEx` at `0x1400d91d6`
- `ntoskrnl!KeBugCheckEx` at `0x1400d9274`
- `ntoskrnl!KeBugCheckEx` at `0x1400d9296`
- `ntoskrnl!KeBugCheckEx` at `0x1400d92ba`

## pseudocode

```c
__int64 __fastcall ReleaseControl(__int64 a1, unsigned int *a2)
{
  __int64 result; // rax
  unsigned int v5; // r12d
  __int64 v6; // r15
  ULONG_PTR v7; // rcx
  _QWORD **v8; // rdi
  _QWORD *v9; // rbx
  _QWORD *v10; // rax
  char i; // al
  __int64 v12; // rax
  ULONG_PTR v13; // rbx
  ULONG_PTR BugCheckParameter4; // rax
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rdi
  KIRQL v18; // al
  __int64 v19; // rdx
  ULONG_PTR v20; // r9
  unsigned __int8 v21; // dl
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rcx
  unsigned __int64 v25; // r9
  __int64 v26; // rdx
  unsigned int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rax
  unsigned int v30; // eax
  struct _MDL *v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // rdx
  KIRQL v36; // al

  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)a2 + 25);
  if ( (int)result < 0 )
    KeBugCheckEx(0x120u, 0xBu, (ULONG_PTR)a2, 0, (int)result);
  if ( (int)result <= 0 )
  {
    LOBYTE(v5) = 0;
    v6 = *(_QWORD *)a2;
    if ( *(_QWORD *)a2 )
      v5 = a2[21];
    if ( a2[40] )
      KeBugCheckEx(0x120u, 0xCu, (ULONG_PTR)a2, 0, a2[40]);
    if ( *((unsigned int **)a2 + 21) != a2 + 42 )
      KeBugCheckEx(0x120u, 0xCu, (ULONG_PTR)a2, 0, 0);
    v7 = *((_QWORD *)a2 + 23);
    if ( v7 )
    {
      FveWorkItemCleanup(v7);
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(*(_QWORD *)(a1 + 8) + 352LL), *((PVOID *)a2 + 23));
      *((_QWORD *)a2 + 23) = 0;
    }
    v8 = (_QWORD **)(a2 + 36);
    while ( 1 )
    {
      v9 = *v8;
      if ( *v8 == v8 )
        break;
      if ( (_QWORD **)v9[1] != v8 || (v10 = (_QWORD *)*v9, *(_QWORD **)(*v9 + 8LL) != v9) )
        __fastfail(3u);
      *v8 = v10;
      v10[1] = v8;
      FveWorkItemCleanup((ULONG_PTR)v9);
      ReleaseSubWorkItem(a1, v9);
    }
    for ( i = *((_BYTE *)a2 + 92); i; i = *((_BYTE *)a2 + 92) )
    {
      v12 = (unsigned __int8)(i - 1);
      *((_BYTE *)a2 + 92) = v12;
      v13 = (ULONG_PTR)&a2[48 * v12 + 78];
      BugCheckParameter4 = *(_QWORD *)&a2[48 * v12 + 82];
      if ( a2 != (unsigned int *)BugCheckParameter4 )
        KeBugCheckEx(0x120u, 0xCu, (ULONG_PTR)a2, v13, BugCheckParameter4);
      v15 = *(_QWORD *)(v13 + 32);
      v16 = *(_QWORD *)(v15 + 24);
      if ( v16 != v13 && v16 )
        KeBugCheckEx(0x120u, 0xCu, v13, 0, *(_QWORD *)(v15 + 24));
      v17 = *(_QWORD *)(a1 + 8);
      v18 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v13 + 152));
      v19 = *(unsigned __int8 *)(v13 + 191);
      v20 = *(unsigned __int8 *)(v19 + v13 + 176);
      if ( !*(_BYTE *)(33 * v20 + v17 + 1672) )
        KeBugCheckEx(0x120u, 0xBu, v13, v20, 0x20u);
      v21 = v19 + 1;
      *(_BYTE *)(v13 + 191) = v21;
      if ( v21 >= 0xFu )
      {
        *(_BYTE *)(v13 + 191) = 0;
        v21 = 0;
      }
      *(_BYTE *)(v21 + v13 + 176) = 32;
      KeReleaseSpinLock((PKSPIN_LOCK)(v13 + 152), v18);
      v22 = *(_QWORD *)(v13 + 48);
      if ( v22 )
      {
        v23 = *(_QWORD *)(v13 + 56);
        v24 = *(_QWORD *)(v13 + 16);
        v25 = MEMORY[0xFFFFF78000000008] - v22;
        if ( v23 )
        {
          v26 = *(_QWORD *)(v13 + 64);
          if ( v26 )
          {
            _InterlockedAdd64((volatile signed __int64 *)(v24 + 32), v26 - v23);
            v27 = *(_DWORD *)(v13 + 88);
            if ( v27 )
              _InterlockedAdd((volatile signed __int32 *)(v24 + 40), v27);
          }
        }
        v28 = *(_QWORD *)(v13 + 72);
        if ( v28 )
        {
          v29 = *(_QWORD *)(v13 + 80);
          if ( v29 )
          {
            _InterlockedAdd64((volatile signed __int64 *)(v24 + 24), v29 - v28);
            v30 = *(_DWORD *)(v13 + 92);
            if ( v30 )
              _InterlockedAdd((volatile signed __int32 *)(v24 + 44), v30);
          }
        }
        _InterlockedAdd64((volatile signed __int64 *)(v24 + 16), v25);
        *(_QWORD *)(v13 + 48) = 0;
        *(_QWORD *)(v13 + 56) = 0;
        *(_QWORD *)(v13 + 64) = 0;
        *(_QWORD *)(v13 + 72) = 0;
        *(_QWORD *)(v13 + 80) = 0;
        *(_QWORD *)(v13 + 88) = 0;
      }
      FveWorkItemCleanup(*(_QWORD *)(v13 + 32));
      ReleaseSubWorkItem(a1, *(_QWORD *)(v13 + 32));
      ReleaseSubIrp(a1, *(_QWORD *)(v13 + 40));
      v31 = *(struct _MDL **)(v13 + 112);
      if ( v31 )
      {
        IoFreeMdl(v31);
        *(_QWORD *)(v13 + 112) = 0;
      }
      ReleaseShadowBuffer(a1, *(_QWORD *)(v13 + 96) & 0xFFFFFFFFFFFFFFFCuLL, *(_DWORD *)(v13 + 96) & 3);
      if ( (unsigned int)Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline(v33, v32, v34) )
      {
        FveHwAccelReleaseDescriptor(a1, *(_QWORD *)(v13 + 160));
        v35 = *(_QWORD *)(v13 + 168);
        *(_QWORD *)(v13 + 160) = 0;
        FveHwAccelReleaseWorkRequest(a1, v35);
        *(_QWORD *)(v13 + 168) = 0;
      }
    }
    if ( a2 == *(unsigned int **)(a1 + 2040) )
    {
      v36 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 2032));
      if ( !*(_BYTE *)(a1 + 2048) )
        KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
      *(_BYTE *)(a1 + 2048) = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 2032), v36);
    }
    else
    {
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(*(_QWORD *)(a1 + 8) + 9248LL), a2);
    }
    if ( v6 )
      FvepInformRundownFinishedWithDisk(a1, v6, v5);
    return FvepReleaseRemoveLock(a1 + 56);
  }
  return result;
}

```

## disassembly

```asm
0x1400d8e60  push    rbp
0x1400d8e62  push    rsi
0x1400d8e63  sub     rsp, 48h
0x1400d8e67  mov     rsi, rdx
0x1400d8e6a  mov     rbp, rcx
0x1400d8e6d  mov     eax, 0FFFFFFFFh
0x1400d8e72  lock xadd [rdx+64h], eax
0x1400d8e77  sub     eax, 1
0x1400d8e7a  js      loc_1400D92A3
0x1400d8e80  test    eax, eax
0x1400d8e82  jg      loc_1400D9257
0x1400d8e88  mov     [rsp+58h+arg_10], r12
0x1400d8e8d  mov     [rsp+58h+var_18], r13
0x1400d8e92  xor     r13d, r13d
0x1400d8e95  mov     [rsp+58h+var_28], r15
0x1400d8e9a  mov     r12d, r13d
0x1400d8e9d  mov     r15, [rdx]
0x1400d8ea0  test    r15, r15
0x1400d8ea3  jz      short loc_1400D8EA9
0x1400d8ea5  mov     r12d, [rdx+54h]
0x1400d8ea9  mov     eax, [rdx+0A0h]
0x1400d8eaf  test    eax, eax
0x1400d8eb1  jnz     loc_1400D9281
0x1400d8eb7  lea     rax, [rdx+0A8h]
0x1400d8ebe  cmp     [rax], rax
0x1400d8ec1  jnz     loc_1400D925F
0x1400d8ec7  mov     rcx, [rdx+0B8h]; BugCheckParameter2
0x1400d8ece  mov     [rsp+58h+arg_0], rbx
0x1400d8ed3  mov     [rsp+58h+arg_8], rdi
0x1400d8ed8  test    rcx, rcx
0x1400d8edb  jz      short loc_1400D8F07
0x1400d8edd  call    FveWorkItemCleanup
0x1400d8ee2  mov     rcx, [rbp+8]
0x1400d8ee6  mov     rdx, [rsi+0B8h]; Entry
0x1400d8eed  mov     rcx, [rcx+160h]; Lookaside
0x1400d8ef4  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400d8efb  nop     dword ptr [rax+rax+00h]
0x1400d8f00  mov     [rsi+0B8h], r13
0x1400d8f07  lea     rdi, [rsi+90h]
0x1400d8f0e  xchg    ax, ax
0x1400d8f10  mov     rbx, [rdi]
0x1400d8f13  cmp     rbx, rdi
0x1400d8f16  jz      short loc_1400D8F4A
0x1400d8f18  cmp     [rbx+8], rdi
0x1400d8f1c  jnz     short loc_1400D8F43
0x1400d8f1e  mov     rax, [rbx]
0x1400d8f21  cmp     [rax+8], rbx
0x1400d8f25  jnz     short loc_1400D8F43
0x1400d8f27  mov     [rdi], rax
0x1400d8f2a  mov     rcx, rbx; BugCheckParameter2
0x1400d8f2d  mov     [rax+8], rdi
0x1400d8f31  call    FveWorkItemCleanup
0x1400d8f36  mov     rdx, rbx
0x1400d8f39  mov     rcx, rbp
0x1400d8f3c  call    ReleaseSubWorkItem
0x1400d8f41  jmp     short loc_1400D8F10
0x1400d8f43  mov     ecx, 3
0x1400d8f48  int     29h; Win8: RtlFailFast(ecx)
0x1400d8f4a  movzx   eax, byte ptr [rsi+5Ch]
0x1400d8f4e  mov     [rsp+58h+var_20], r14
0x1400d8f53  test    al, al
0x1400d8f55  jz      loc_1400D912D
0x1400d8f5b  nop     dword ptr [rax+rax+00h]
0x1400d8f60  dec     al
0x1400d8f62  lea     rbx, [rsi+138h]
0x1400d8f69  movzx   eax, al
0x1400d8f6c  mov     [rsi+5Ch], al
0x1400d8f6f  lea     rcx, [rax+rax*2]
0x1400d8f73  shl     rcx, 6
0x1400d8f77  add     rbx, rcx
0x1400d8f7a  mov     rax, [rcx+rsi+148h]
0x1400d8f82  cmp     rsi, rax
0x1400d8f85  jnz     loc_1400D91C1
0x1400d8f8b  mov     rax, [rbx+20h]
0x1400d8f8f  mov     rcx, [rax+18h]
0x1400d8f93  cmp     rcx, rbx
0x1400d8f96  jz      short loc_1400D8FA1
0x1400d8f98  test    rcx, rcx
0x1400d8f9b  jnz     loc_1400D917C
0x1400d8fa1  mov     rdi, [rbp+8]
0x1400d8fa5  lea     rcx, [rbx+98h]; SpinLock
0x1400d8fac  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400d8fb3  nop     dword ptr [rax+rax+00h]
0x1400d8fb8  movzx   edx, byte ptr [rbx+0BFh]
0x1400d8fbf  movzx   r8d, al
0x1400d8fc3  movzx   r9d, byte ptr [rdx+rbx+0B0h]; BugCheckParameter3
0x1400d8fcc  imul    rcx, r9, 21h ; '!'
0x1400d8fd0  cmp     [rcx+rdi+688h], r13b
0x1400d8fd8  jz      loc_1400D919E
0x1400d8fde  inc     dl
0x1400d8fe0  mov     [rbx+0BFh], dl
0x1400d8fe6  cmp     dl, 0Fh
0x1400d8fe9  jb      short loc_1400D8FF4
0x1400d8feb  mov     [rbx+0BFh], r13b
0x1400d8ff2  xor     dl, dl
0x1400d8ff4  movzx   eax, dl
0x1400d8ff7  lea     rcx, [rbx+98h]; SpinLock
0x1400d8ffe  movzx   edx, r8b; NewIrql
0x1400d9002  mov     byte ptr [rax+rbx+0B0h], 20h ; ' '
0x1400d900a  call    cs:__imp_KeReleaseSpinLock
0x1400d9011  nop     dword ptr [rax+rax+00h]
0x1400d9016  mov     rdx, [rbx+30h]
0x1400d901a  test    rdx, rdx
0x1400d901d  jz      short loc_1400D909A
0x1400d901f  mov     rax, ds:0FFFFF78000000008h
0x1400d9029  mov     r8, [rbx+38h]
0x1400d902d  mov     r9, rax
0x1400d9030  mov     rcx, [rbx+10h]
0x1400d9034  sub     r9, rdx
0x1400d9037  test    r8, r8
0x1400d903a  jz      short loc_1400D9058
0x1400d903c  mov     rdx, [rbx+40h]
0x1400d9040  test    rdx, rdx
0x1400d9043  jz      short loc_1400D9058
0x1400d9045  sub     rdx, r8
0x1400d9048  lock add [rcx+20h], rdx
0x1400d904d  mov     eax, [rbx+58h]
0x1400d9050  test    eax, eax
0x1400d9052  jz      short loc_1400D9058
0x1400d9054  lock add [rcx+28h], eax
0x1400d9058  mov     rdx, [rbx+48h]
0x1400d905c  test    rdx, rdx
0x1400d905f  jz      short loc_1400D907D
0x1400d9061  mov     rax, [rbx+50h]
0x1400d9065  test    rax, rax
0x1400d9068  jz      short loc_1400D907D
0x1400d906a  sub     rax, rdx
0x1400d906d  lock add [rcx+18h], rax
0x1400d9072  mov     eax, [rbx+5Ch]
0x1400d9075  test    eax, eax
0x1400d9077  jz      short loc_1400D907D
0x1400d9079  lock add [rcx+2Ch], eax
0x1400d907d  lock add [rcx+10h], r9
0x1400d9082  mov     [rbx+30h], r13
0x1400d9086  mov     [rbx+38h], r13
0x1400d908a  mov     [rbx+40h], r13
0x1400d908e  mov     [rbx+48h], r13
0x1400d9092  mov     [rbx+50h], r13
0x1400d9096  mov     [rbx+58h], r13
0x1400d909a  mov     rcx, [rbx+20h]; BugCheckParameter2
0x1400d909e  call    FveWorkItemCleanup
0x1400d90a3  mov     rdx, [rbx+20h]
0x1400d90a7  mov     rcx, rbp
0x1400d90aa  call    ReleaseSubWorkItem
0x1400d90af  mov     rdx, [rbx+28h]
0x1400d90b3  mov     rcx, rbp
0x1400d90b6  call    ReleaseSubIrp
0x1400d90bb  mov     rcx, [rbx+70h]; Mdl
0x1400d90bf  test    rcx, rcx
0x1400d90c2  jz      short loc_1400D90D4
0x1400d90c4  call    cs:__imp_IoFreeMdl
0x1400d90cb  nop     dword ptr [rax+rax+00h]
0x1400d90d0  mov     [rbx+70h], r13
0x1400d90d4  mov     r8d, [rbx+60h]
0x1400d90d8  mov     rcx, rbp
0x1400d90db  mov     rdx, [rbx+60h]
0x1400d90df  and     r8d, 3
0x1400d90e3  and     rdx, 0FFFFFFFFFFFFFFFCh
0x1400d90e7  call    ReleaseShadowBuffer
0x1400d90ec  call    Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline
0x1400d90f1  test    eax, eax
0x1400d90f3  jz      short loc_1400D9121
0x1400d90f5  mov     rdx, [rbx+0A0h]
0x1400d90fc  mov     rcx, rbp
0x1400d90ff  call    FveHwAccelReleaseDescriptor
0x1400d9104  mov     rdx, [rbx+0A8h]
0x1400d910b  mov     rcx, rbp
0x1400d910e  mov     [rbx+0A0h], r13
0x1400d9115  call    FveHwAccelReleaseWorkRequest
0x1400d911a  mov     [rbx+0A8h], r13
0x1400d9121  movzx   eax, byte ptr [rsi+5Ch]
0x1400d9125  test    al, al
0x1400d9127  jnz     loc_1400D8F60
0x1400d912d  cmp     rsi, [rbp+7F8h]
0x1400d9134  jnz     loc_1400D9202
0x1400d913a  lea     rcx, [rbp+7F0h]; SpinLock
0x1400d9141  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400d9148  nop     dword ptr [rax+rax+00h]
0x1400d914d  cmp     [rbp+800h], r13b
0x1400d9154  jnz     loc_1400D91E3
0x1400d915a  xor     r9d, r9d; BugCheckParameter3
0x1400d915d  mov     [rsp+58h+BugCheckParameter4], r13; BugCheckParameter4
0x1400d9162  xor     r8d, r8d; BugCheckParameter2
0x1400d9165  mov     edx, 0Ch; BugCheckParameter1
0x1400d916a  mov     ecx, 120h; BugCheckCode
0x1400d916f  call    cs:__imp_KeBugCheckEx
0x1400d917c  mov     [rsp+58h+BugCheckParameter4], rcx; BugCheckParameter4
0x1400d9181  xor     r9d, r9d; BugCheckParameter3
0x1400d9184  mov     ecx, 120h; BugCheckCode
0x1400d9189  mov     r8, rbx; BugCheckParameter2
0x1400d918c  mov     edx, 0Ch; BugCheckParameter1
0x1400d9191  call    cs:__imp_KeBugCheckEx
0x1400d919e  mov     r8, rbx; BugCheckParameter2
0x1400d91a1  mov     [rsp+58h+BugCheckParameter4], 20h ; ' '; BugCheckParameter4
0x1400d91aa  mov     edx, 0Bh; BugCheckParameter1
0x1400d91af  mov     ecx, 120h; BugCheckCode
0x1400d91b4  call    cs:__imp_KeBugCheckEx
0x1400d91c1  mov     r9, rbx; BugCheckParameter3
0x1400d91c4  mov     [rsp+58h+BugCheckParameter4], rax; BugCheckParameter4
0x1400d91c9  mov     r8, rsi; BugCheckParameter2
0x1400d91cc  mov     edx, 0Ch; BugCheckParameter1
0x1400d91d1  mov     ecx, 120h; BugCheckCode
0x1400d91d6  call    cs:__imp_KeBugCheckEx
0x1400d91e3  movzx   edx, al; NewIrql
0x1400d91e6  mov     [rbp+800h], r13b
0x1400d91ed  lea     rcx, [rbp+7F0h]; SpinLock
0x1400d91f4  call    cs:__imp_KeReleaseSpinLock
0x1400d91fb  nop     dword ptr [rax+rax+00h]
0x1400d9200  jmp     short loc_1400D921C
0x1400d9202  mov     rcx, [rbp+8]
0x1400d9206  mov     rdx, rsi; Entry
0x1400d9209  mov     rcx, [rcx+2420h]; Lookaside
0x1400d9210  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400d9217  nop     dword ptr [rax+rax+00h]
0x1400d921c  test    r15, r15
0x1400d921f  jz      short loc_1400D9230
0x1400d9221  movzx   r8d, r12b
0x1400d9225  mov     rdx, r15
0x1400d9228  mov     rcx, rbp
0x1400d922b  call    FvepInformRundownFinishedWithDisk
0x1400d9230  lea     rcx, [rbp+38h]; BugCheckParameter2
0x1400d9234  call    FvepReleaseRemoveLock
0x1400d9239  mov     r14, [rsp+58h+var_20]
0x1400d923e  mov     rdi, [rsp+58h+arg_8]
0x1400d9243  mov     rbx, [rsp+58h+arg_0]
0x1400d9248  mov     r12, [rsp+58h+arg_10]
0x1400d924d  mov     r13, [rsp+58h+var_18]
0x1400d9252  mov     r15, [rsp+58h+var_28]
0x1400d9257  add     rsp, 48h
0x1400d925b  pop     rsi
0x1400d925c  pop     rbp
0x1400d925d  retn
0x1400d925f  xor     r9d, r9d; BugCheckParameter3
0x1400d9262  mov     [rsp+58h+BugCheckParameter4], r13; BugCheckParameter4
0x1400d9267  mov     r8, rsi; BugCheckParameter2
0x1400d926a  mov     edx, 0Ch; BugCheckParameter1
0x1400d926f  mov     ecx, 120h; BugCheckCode
0x1400d9274  call    cs:__imp_KeBugCheckEx
0x1400d9281  xor     r9d, r9d; BugCheckParameter3
0x1400d9284  mov     [rsp+58h+BugCheckParameter4], rax; BugCheckParameter4
0x1400d9289  mov     r8, rsi; BugCheckParameter2
0x1400d928c  mov     edx, 0Ch; BugCheckParameter1
0x1400d9291  mov     ecx, 120h; BugCheckCode
0x1400d9296  call    cs:__imp_KeBugCheckEx
0x1400d92a3  cdqe
0x1400d92a5  xor     r9d, r9d; BugCheckParameter3
0x1400d92a8  mov     r8, rsi; BugCheckParameter2
0x1400d92ab  mov     [rsp+58h+BugCheckParameter4], rax; BugCheckParameter4
0x1400d92b0  mov     edx, 0Bh; BugCheckParameter1
0x1400d92b5  mov     ecx, 120h; BugCheckCode
0x1400d92ba  call    cs:__imp_KeBugCheckEx
```
