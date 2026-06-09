# CPowerManager::CPowerManager(ITpThreadManager *)

- ea: `0x18003981c`
- end: `0x180039b1d`
- name: `??0CPowerManager@@QEAA@PEAUITpThreadManager@@@Z`
- size: `769`
- prototype: `CPowerManager *__fastcall(CPowerManager *__hidden this, struct ITpThreadManager *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180117ad0`

## callees

- `0x18003981c`
- `0x180146090`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionEx` at `0x180039861`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1800398a4`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1800398d3`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180039861`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1800398a4`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1800398d3`
- `KERNEL32!GetTickCount64` at `0x180039a7b`
- `KERNEL32!GetTickCount64` at `0x180039a7b`
- `KERNEL32!CloseHandle` at `0x180039991`
- `KERNEL32!CloseHandle` at `0x1800399c7`
- `KERNEL32!CloseHandle` at `0x180039a45`
- `KERNEL32!CloseHandle` at `0x180039a66`
- `KERNEL32!CloseHandle` at `0x180039991`
- `KERNEL32!CloseHandle` at `0x1800399c7`
- `KERNEL32!CloseHandle` at `0x180039a45`
- `KERNEL32!CloseHandle` at `0x180039a66`
- `KERNEL32!CreateEventW` at `0x180039975`
- `KERNEL32!CreateEventW` at `0x1800399ab`
- `KERNEL32!CreateEventW` at `0x180039975`
- `KERNEL32!CreateEventW` at `0x1800399ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CPowerManager *__fastcall CPowerManager::CPowerManager(CPowerManager *this, struct ITpThreadManager *a2)
{
  HANDLE EventW; // rbx
  void *v5; // rcx
  HANDLE v6; // rbx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  volatile __int64 *v10; // rdx
  __int64 v11; // r8

  *(_QWORD *)this = &CPowerManager::`vftable'{for `ITpPowerManagerInternal'};
  *((_QWORD *)this + 1) = &CPowerManager::`vftable'{for `ITpPowerManagerDebug'};
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 56), 0, 0);
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 62) = 0;
  *((_QWORD *)this + 63) = 0;
  *((_QWORD *)this + 65) = 0;
  *((_QWORD *)this + 66) = 0;
  *((_QWORD *)this + 69) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)this + 14, 0, 0);
  *((_QWORD *)this + 75) = 0;
  *((_QWORD *)this + 76) = 0;
  *((_QWORD *)this + 77) = 0;
  *((_QWORD *)this + 78) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 632), 0, 0);
  *((_QWORD *)this + 84) = 0;
  *((_QWORD *)this + 85) = 0;
  *((_QWORD *)this + 86) = 0;
  *((_QWORD *)this + 92) = 0;
  *((_QWORD *)this + 93) = 0;
  *((_QWORD *)this + 94) = 0x8000000000000000uLL;
  *((_QWORD *)this + 95) = 0;
  *((_QWORD *)this + 96) = 0;
  *((_DWORD *)this + 4) = 1;
  *((_QWORD *)this + 20) = a2;
  (*(void (__fastcall **)(struct ITpThreadManager *))(*(_QWORD *)a2 + 8LL))(a2);
  *((_DWORD *)this + 100) = 0;
  *((_DWORD *)this + 24) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  v5 = (void *)*((_QWORD *)this + 22);
  if ( v5 )
  {
    *((_QWORD *)this + 22) = 0;
    CloseHandle(v5);
  }
  *((_QWORD *)this + 22) = EventW;
  v6 = CreateEventW(0, 1, 0, 0);
  v7 = (void *)*((_QWORD *)this + 23);
  if ( v7 )
  {
    *((_QWORD *)this + 23) = 0;
    CloseHandle(v7);
  }
  *((_QWORD *)this + 23) = v6;
  *((_QWORD *)this + 21) = 0;
  *((_DWORD *)this + 102) = 4149;
  *((_BYTE *)this + 412) = 0;
  *((_QWORD *)this + 52) = -1;
  *((_QWORD *)this + 53) = -1;
  *((_QWORD *)this + 54) = -1;
  *((_BYTE *)this + 404) = 0;
  *(_OWORD *)((char *)this + 440) = *(_OWORD *)((char *)this + 408);
  *(_OWORD *)((char *)this + 456) = *(_OWORD *)((char *)this + 424);
  *((_QWORD *)this + 59) = 0;
  v8 = (void *)*((_QWORD *)this + 62);
  if ( v8 )
  {
    *((_QWORD *)this + 62) = 0;
    CloseHandle(v8);
  }
  *((_QWORD *)this + 62) = 0;
  v9 = (void *)*((_QWORD *)this + 63);
  if ( v9 )
  {
    *((_QWORD *)this + 63) = 0;
    CloseHandle(v9);
  }
  *((_QWORD *)this + 63) = 0;
  *((_QWORD *)this + 64) = 0;
  *((_QWORD *)this + 68) = GetTickCount64();
  *((_BYTE *)this + 728) = 0;
  *((_BYTE *)this + 696) = 0;
  *((_BYTE *)this + 697) = 0;
  *((_QWORD *)this + 88) = 0x7FFFFFFFFFFFFFFFLL;
  *((_QWORD *)this + 89) = 0;
  *((_QWORD *)this + 90) = 0;
  v10 = (volatile __int64 *)((char *)this + 296);
  v11 = 13;
  do
  {
    _InterlockedExchange64(v10 - 13, 0);
    _InterlockedExchange64(v10++, 0);
    --v11;
  }
  while ( v11 );
  _InterlockedExchange64((volatile __int64 *)this + 34, *((_QWORD *)this + 68));
  _InterlockedExchange64((volatile __int64 *)this + 36, *((_QWORD *)this + 68));
  *((_QWORD *)this + 67) = 0;
  *((_QWORD *)this + 99) = 0;
  return this;
}

```

## disassembly

```asm
0x18003981c  mov     [rsp+arg_0], rbx
0x180039821  mov     [rsp+arg_8], rsi
0x180039826  push    rdi
0x180039827  sub     rsp, 20h
0x18003982b  mov     rbx, rdx
0x18003982e  mov     rdi, rcx
0x180039831  lea     rax, ??_7CPowerManager@@6BITpPowerManagerInternal@@@; const CPowerManager::`vftable'{for `ITpPowerManagerInternal'}
0x180039838  mov     [rcx], rax
0x18003983b  lea     rax, ??_7CPowerManager@@6BITpPowerManagerDebug@@@; const CPowerManager::`vftable'{for `ITpPowerManagerDebug'}
0x180039842  mov     [rcx+8], rax
0x180039846  xor     esi, esi
0x180039848  mov     [rcx+18h], rsi
0x18003984c  mov     [rcx+20h], rsi
0x180039850  mov     [rcx+28h], rsi
0x180039854  mov     [rcx+30h], rsi
0x180039858  add     rcx, 38h ; '8'; lpCriticalSection
0x18003985c  xor     r8d, r8d; Flags
0x18003985f  xor     edx, edx; dwSpinCount
0x180039861  call    cs:__imp_InitializeCriticalSectionEx
0x180039867  mov     [rdi+0B0h], rsi
0x18003986e  mov     [rdi+0B8h], rsi
0x180039875  mov     [rdi+1F0h], rsi
0x18003987c  mov     [rdi+1F8h], rsi
0x180039883  mov     [rdi+208h], rsi
0x18003988a  mov     [rdi+210h], rsi
0x180039891  mov     [rdi+228h], rsi
0x180039898  lea     rcx, [rdi+230h]; lpCriticalSection
0x18003989f  xor     r8d, r8d; Flags
0x1800398a2  xor     edx, edx; dwSpinCount
0x1800398a4  call    cs:__imp_InitializeCriticalSectionEx
0x1800398aa  nop
0x1800398ab  mov     [rdi+258h], rsi
0x1800398b2  mov     [rdi+260h], rsi
0x1800398b9  mov     [rdi+268h], rsi
0x1800398c0  mov     [rdi+270h], rsi
0x1800398c7  lea     rcx, [rdi+278h]; lpCriticalSection
0x1800398ce  xor     r8d, r8d; Flags
0x1800398d1  xor     edx, edx; dwSpinCount
0x1800398d3  call    cs:__imp_InitializeCriticalSectionEx
0x1800398d9  mov     [rdi+2A0h], rsi
0x1800398e0  mov     [rdi+2A8h], rsi
0x1800398e7  mov     [rdi+2B0h], rsi
0x1800398ee  mov     [rdi+2E0h], rsi
0x1800398f5  mov     [rdi+2E8h], rsi
0x1800398fc  mov     rax, 8000000000000000h
0x180039906  mov     [rdi+2F0h], rax
0x18003990d  mov     [rdi+2F8h], rsi
0x180039914  mov     [rdi+300h], rsi
0x18003991b  mov     dword ptr [rdi+10h], 1
0x180039922  mov     [rdi+0A0h], rbx
0x180039929  mov     rax, [rbx]
0x18003992c  mov     rcx, rbx
0x18003992f  mov     rax, [rax+8]
0x180039933  call    cs:__guard_dispatch_icall_fptr
0x180039939  mov     [rdi+190h], esi
0x18003993f  mov     [rdi+60h], esi
0x180039942  mov     [rdi+68h], rsi
0x180039946  mov     [rdi+70h], rsi
0x18003994a  mov     [rdi+78h], rsi
0x18003994e  mov     [rdi+80h], rsi
0x180039955  mov     [rdi+88h], rsi
0x18003995c  mov     [rdi+90h], rsi
0x180039963  mov     [rdi+98h], rsi
0x18003996a  xor     r9d, r9d; lpName
0x18003996d  xor     r8d, r8d; bInitialState
0x180039970  lea     edx, [rsi+1]; bManualReset
0x180039973  xor     ecx, ecx; lpEventAttributes
0x180039975  call    cs:__imp_CreateEventW
0x18003997b  mov     rbx, rax
0x18003997e  mov     rcx, [rdi+0B0h]; hObject
0x180039985  test    rcx, rcx
0x180039988  jz      short loc_180039998
0x18003998a  mov     [rdi+0B0h], rsi
0x180039991  call    cs:__imp_CloseHandle
0x180039997  nop
0x180039998  mov     [rdi+0B0h], rbx
0x18003999f  xor     r9d, r9d; lpName
0x1800399a2  xor     r8d, r8d; bInitialState
0x1800399a5  lea     edx, [r9+1]; bManualReset
0x1800399a9  xor     ecx, ecx; lpEventAttributes
0x1800399ab  call    cs:__imp_CreateEventW
0x1800399b1  mov     rbx, rax
0x1800399b4  mov     rcx, [rdi+0B8h]; hObject
0x1800399bb  test    rcx, rcx
0x1800399be  jz      short loc_1800399D0
0x1800399c0  mov     [rdi+0B8h], rsi
0x1800399c7  call    cs:__imp_CloseHandle
0x1800399cd  nop
0x1800399ce  xchg    ax, ax
0x1800399d0  mov     [rdi+0B8h], rbx
0x1800399d7  mov     [rdi+0A8h], rsi
0x1800399de  mov     dword ptr [rdi+198h], 1035h
0x1800399e8  mov     [rdi+19Ch], sil
0x1800399ef  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800399f3  mov     [rdi+1A0h], rax
0x1800399fa  mov     [rdi+1A8h], rax
0x180039a01  mov     [rdi+1B0h], rax
0x180039a08  mov     [rdi+194h], sil
0x180039a0f  movups  xmm0, xmmword ptr [rdi+198h]
0x180039a16  movups  xmmword ptr [rdi+1B8h], xmm0
0x180039a1d  movups  xmm1, xmmword ptr [rdi+1A8h]
0x180039a24  movups  xmmword ptr [rdi+1C8h], xmm1
0x180039a2b  mov     [rdi+1D8h], rsi
0x180039a32  mov     rcx, [rdi+1F0h]; hObject
0x180039a39  test    rcx, rcx
0x180039a3c  jz      short loc_180039A4C
0x180039a3e  mov     [rdi+1F0h], rsi
0x180039a45  call    cs:__imp_CloseHandle
0x180039a4b  nop
0x180039a4c  mov     [rdi+1F0h], rsi
0x180039a53  mov     rcx, [rdi+1F8h]; hObject
0x180039a5a  test    rcx, rcx
0x180039a5d  jz      short loc_180039A6D
0x180039a5f  mov     [rdi+1F8h], rsi
0x180039a66  call    cs:__imp_CloseHandle
0x180039a6c  nop
0x180039a6d  mov     [rdi+1F8h], rsi
0x180039a74  mov     [rdi+200h], rsi
0x180039a7b  call    cs:__imp_GetTickCount64
0x180039a81  mov     [rdi+220h], rax
0x180039a88  mov     [rdi+2D8h], sil
0x180039a8f  mov     [rdi+2B8h], sil
0x180039a96  mov     [rdi+2B9h], sil
0x180039a9d  mov     rax, 7FFFFFFFFFFFFFFFh
0x180039aa7  mov     [rdi+2C0h], rax
0x180039aae  mov     [rdi+2C8h], rsi
0x180039ab5  mov     [rdi+2D0h], rsi
0x180039abc  lea     rdx, [rdi+128h]
0x180039ac3  mov     r8d, 0Dh
0x180039ac9  mov     rax, rsi
0x180039acc  xchg    rax, [rdx-68h]
0x180039ad0  mov     rcx, rsi
0x180039ad3  xchg    rcx, [rdx]
0x180039ad6  lea     rdx, [rdx+8]
0x180039ada  sub     r8, 1
0x180039ade  jnz     short loc_180039AC9
0x180039ae0  mov     rax, [rdi+220h]
0x180039ae7  xchg    rax, [rdi+110h]
0x180039aee  mov     rax, [rdi+220h]
0x180039af5  xchg    rax, [rdi+120h]
0x180039afc  mov     [rdi+218h], rsi
0x180039b03  mov     [rdi+318h], rsi
0x180039b0a  mov     rax, rdi
0x180039b0d  mov     rbx, [rsp+28h+arg_0]
0x180039b12  mov     rsi, [rsp+28h+arg_8]
0x180039b17  add     rsp, 20h
0x180039b1b  pop     rdi
0x180039b1c  retn
```
