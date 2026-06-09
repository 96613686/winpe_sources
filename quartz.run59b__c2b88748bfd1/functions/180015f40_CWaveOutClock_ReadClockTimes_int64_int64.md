# CWaveOutClock::ReadClockTimes(__int64 *,__int64 *)

- ea: `0x180015f40`
- end: `0x180016166`
- name: `?ReadClockTimes@CWaveOutClock@@IEAAXPEA_J0@Z`
- size: `550`
- prototype: `void __fastcall(CWaveOutClock *__hidden this, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800fc1dc`

## callees

- `0x180015f40`
- `0x1800161c0`
- `0x1800388a0`
- `0x18015e010`

## import_xrefs

- `KERNEL32!MulDiv` at `0x180016075`
- `KERNEL32!MulDiv` at `0x180016075`
- `KERNEL32!GetCurrentThread` at `0x180015f75`
- `KERNEL32!GetCurrentThread` at `0x180015f97`
- `KERNEL32!GetCurrentThread` at `0x180016132`
- `KERNEL32!GetCurrentThread` at `0x180015f75`
- `KERNEL32!GetCurrentThread` at `0x180015f97`
- `KERNEL32!GetCurrentThread` at `0x180016132`
- `KERNEL32!GetThreadPriority` at `0x180015f84`
- `KERNEL32!GetThreadPriority` at `0x180015f84`
- `KERNEL32!SetThreadPriority` at `0x180015fab`
- `KERNEL32!SetThreadPriority` at `0x180016143`
- `KERNEL32!SetThreadPriority` at `0x180015fab`
- `KERNEL32!SetThreadPriority` at `0x180016143`

## pseudocode

```c
void __fastcall CWaveOutClock::ReadClockTimes(CWaveOutClock *this, __int64 *a2, __int64 *a3)
{
  HANDLE CurrentThread; // rax
  int ThreadPriority; // esi
  HANDLE v8; // rax
  _QWORD *v9; // rcx
  int v10; // ebx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r14
  __int64 v15; // rbp
  __int64 v16; // rcx
  int v17; // ecx
  __int64 v18; // rcx
  __int64 v19; // rax
  HANDLE v20; // rax
  int nNumber[4]; // [rsp+30h] [rbp-58h] BYREF

  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  if ( ThreadPriority != 15 )
  {
    v8 = GetCurrentThread();
    SetThreadPriority(v8, 15);
  }
  v9 = (_QWORD *)((char *)this + 232);
  v10 = 50;
  do
  {
    if ( !v10-- )
      break;
    v12 = (*(__int64 (__fastcall **)(CWaveOutClock *))(*(_QWORD *)this + 32LL))(this);
    v13 = *((_QWORD *)this + 17);
    v14 = v12;
    if ( !*(_BYTE *)(v13 + 452) || !*((_DWORD *)this + 56) )
      goto LABEL_16;
    memset(nNumber, 0, 12);
    v15 = *(unsigned int *)(*(_QWORD *)(v13 + 280) + 576LL);
    nNumber[2] = 0;
    nNumber[0] = 4;
    (*(void (__fastcall **)(_QWORD, int *, __int64, _QWORD))(**(_QWORD **)(v13 + 248) + 24LL))(
      *(_QWORD *)(v13 + 248),
      nNumber,
      12,
      0);
    if ( nNumber[0] != 1 )
    {
      v17 = nNumber[1];
      goto LABEL_12;
    }
    if ( (_DWORD)v15 )
    {
      v17 = MulDiv(nNumber[1], v15, 1000);
      nNumber[1] = v17;
LABEL_12:
      if ( *(_DWORD *)(*((_QWORD *)this + 17) + 260LL) )
        v18 = *(_QWORD *)&nNumber[1] - *((_QWORD *)this + 19);
      else
        v18 = v17 - *((_DWORD *)this + 38);
      *((_QWORD *)this + 24) = *((_QWORD *)this + 22) + llMulDiv(v18, 10000000, v15, 0);
LABEL_16:
      v16 = *((_QWORD *)this + 24);
      goto LABEL_17;
    }
    v16 = 10000LL * (unsigned int)nNumber[1];
LABEL_17:
    *a3 = v16;
    v19 = (*(__int64 (__fastcall **)(CWaveOutClock *))(*(_QWORD *)this + 32LL))(this);
    *a2 = v19;
    v9 = (_QWORD *)((char *)this + 232);
  }
  while ( v19 - v14 > *((_QWORD *)this + 29) );
  if ( v10 <= 0 )
    *v9 *= 2LL;
  if ( ThreadPriority != 15 )
  {
    v20 = GetCurrentThread();
    SetThreadPriority(v20, ThreadPriority);
  }
}

```

## disassembly

```asm
0x180015f40  push    rsi
0x180015f42  sub     rsp, 80h
0x180015f49  mov     rax, cs:__security_cookie
0x180015f50  xor     rax, rsp
0x180015f53  mov     [rsp+88h+var_48], rax
0x180015f58  mov     [rsp+88h+var_10], rbx
0x180015f5d  mov     [rsp+88h+var_20], rdi
0x180015f62  mov     rdi, rcx
0x180015f65  mov     [rsp+88h+var_28], r12
0x180015f6a  mov     r12, r8
0x180015f6d  mov     [rsp+88h+var_38], r15
0x180015f72  mov     r15, rdx
0x180015f75  call    cs:__imp_GetCurrentThread
0x180015f7c  nop     dword ptr [rax+rax+00h]
0x180015f81  mov     rcx, rax; hThread
0x180015f84  call    cs:__imp_GetThreadPriority
0x180015f8b  nop     dword ptr [rax+rax+00h]
0x180015f90  mov     esi, eax
0x180015f92  cmp     eax, 0Fh
0x180015f95  jz      short loc_180015FB7
0x180015f97  call    cs:__imp_GetCurrentThread
0x180015f9e  nop     dword ptr [rax+rax+00h]
0x180015fa3  mov     rcx, rax; hThread
0x180015fa6  mov     edx, 0Fh; nPriority
0x180015fab  call    cs:__imp_SetThreadPriority
0x180015fb2  nop     dword ptr [rax+rax+00h]
0x180015fb7  mov     [rsp+88h+var_18], rbp
0x180015fbc  lea     rcx, [rdi+0E8h]
0x180015fc3  mov     [rsp+88h+var_30], r14
0x180015fc8  mov     ebx, 32h ; '2'
0x180015fcd  mov     eax, ebx
0x180015fcf  dec     ebx
0x180015fd1  test    eax, eax
0x180015fd3  jz      loc_180016102
0x180015fd9  mov     rax, [rdi]
0x180015fdc  mov     rcx, rdi
0x180015fdf  mov     rax, [rax+20h]
0x180015fe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fe8  mov     rdx, [rdi+88h]
0x180015fef  mov     r14, rax
0x180015ff2  cmp     byte ptr [rdx+1C4h], 0
0x180015ff9  jz      loc_1800160D2
0x180015fff  cmp     dword ptr [rdi+0E0h], 0
0x180016006  jz      loc_1800160D2
0x18001600c  xor     eax, eax
0x18001600e  xor     r9d, r9d
0x180016011  mov     qword ptr [rsp+88h+nNumber], rax
0x180016016  mov     r8d, 0Ch
0x18001601c  mov     [rsp+88h+var_50], eax
0x180016020  mov     rcx, [rdx+118h]
0x180016027  mov     ebp, [rcx+240h]
0x18001602d  mov     [rsp+88h+var_50], eax
0x180016031  mov     [rsp+88h+nNumber], 4
0x180016039  mov     rcx, [rdx+0F8h]
0x180016040  lea     rdx, [rsp+88h+nNumber]
0x180016045  mov     rax, [rcx]
0x180016048  mov     rax, [rax+18h]
0x18001604c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016051  cmp     [rsp+88h+nNumber], 1
0x180016056  jnz     short loc_180016089
0x180016058  test    ebp, ebp
0x18001605a  jnz     short loc_180016069
0x18001605c  mov     eax, [rsp+88h+nNumber+4]
0x180016060  imul    rcx, rax, 2710h
0x180016067  jmp     short loc_1800160D9
0x180016069  mov     ecx, [rsp+88h+nNumber+4]; nNumber
0x18001606d  mov     r8d, 3E8h; nDenominator
0x180016073  mov     edx, ebp; nNumerator
0x180016075  call    cs:__imp_MulDiv
0x18001607c  nop     dword ptr [rax+rax+00h]
0x180016081  mov     ecx, eax
0x180016083  mov     [rsp+88h+nNumber+4], eax
0x180016087  jmp     short loc_18001608D
0x180016089  mov     ecx, [rsp+88h+nNumber+4]
0x18001608d  mov     rax, [rdi+88h]
0x180016094  cmp     dword ptr [rax+104h], 0
0x18001609b  jz      short loc_1800160AB
0x18001609d  mov     rcx, qword ptr [rsp+88h+nNumber+4]
0x1800160a2  sub     rcx, [rdi+98h]
0x1800160a9  jmp     short loc_1800160B4
0x1800160ab  sub     ecx, [rdi+98h]
0x1800160b1  movsxd  rcx, ecx; __int64
0x1800160b4  mov     r8, rbp; __int64
0x1800160b7  xor     r9d, r9d; __int64
0x1800160ba  mov     edx, 989680h; __int64
0x1800160bf  call    ?llMulDiv@@YA_J_J000@Z; llMulDiv(__int64,__int64,__int64,__int64)
0x1800160c4  add     rax, [rdi+0B0h]
0x1800160cb  mov     [rdi+0C0h], rax
0x1800160d2  mov     rcx, [rdi+0C0h]
0x1800160d9  mov     [r12], rcx
0x1800160dd  mov     rcx, rdi
0x1800160e0  mov     rax, [rdi]
0x1800160e3  mov     rax, [rax+20h]
0x1800160e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160ec  mov     [r15], rax
0x1800160ef  lea     rcx, [rdi+0E8h]
0x1800160f6  sub     rax, r14
0x1800160f9  cmp     rax, [rcx]
0x1800160fc  jg      loc_180015FCD
0x180016102  mov     r15, [rsp+88h+var_38]
0x180016107  test    ebx, ebx
0x180016109  mov     rbx, [rsp+88h+var_10]
0x18001610e  mov     r14, [rsp+88h+var_30]
0x180016113  mov     r12, [rsp+88h+var_28]
0x180016118  mov     rdi, [rsp+88h+var_20]
0x18001611d  mov     rbp, [rsp+88h+var_18]
0x180016122  jg      short loc_18001612D
0x180016124  mov     rax, [rcx]
0x180016127  add     rax, rax
0x18001612a  mov     [rcx], rax
0x18001612d  cmp     esi, 0Fh
0x180016130  jz      short loc_18001614F
0x180016132  call    cs:__imp_GetCurrentThread
0x180016139  nop     dword ptr [rax+rax+00h]
0x18001613e  mov     rcx, rax; hThread
0x180016141  mov     edx, esi; nPriority
0x180016143  call    cs:__imp_SetThreadPriority
0x18001614a  nop     dword ptr [rax+rax+00h]
0x18001614f  mov     rcx, [rsp+88h+var_48]
0x180016154  xor     rcx, rsp; StackCookie
0x180016157  call    __security_check_cookie
0x18001615c  add     rsp, 80h
0x180016163  pop     rsi
0x180016164  retn
```
