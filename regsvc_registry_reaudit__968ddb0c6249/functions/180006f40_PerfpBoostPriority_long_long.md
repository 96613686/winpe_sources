# PerfpBoostPriority(long,long *)

- ea: `0x180006f40`
- end: `0x180006fc2`
- name: `?PerfpBoostPriority@@YAEJPEAJ@Z`
- size: `130`
- prototype: `unsigned __int8 __fastcall(int, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001520`

## callees

- `0x180006f40`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x180006fad`
- `ntdll!NtSetInformationThread` at `0x180006fad`
- `ntdll!NtQueryInformationThread` at `0x180006f80`
- `ntdll!NtQueryInformationThread` at `0x180006f80`

## pseudocode

```c
bool __fastcall PerfpBoostPriority(__int64 a1, int *a2)
{
  int v4; // [rsp+30h] [rbp-48h] BYREF
  _OWORD ThreadInformation[2]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v6; // [rsp+58h] [rbp-20h]

  v4 = 15;
  memset(ThreadInformation, 0, sizeof(ThreadInformation));
  v6 = 0;
  if ( NtQueryInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadBasicInformation, ThreadInformation, 0x30u, 0) < 0
    || SDWORD2(v6) >= v4 )
  {
    return 0;
  }
  *a2 = DWORD2(v6);
  return NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPriority, &v4, 4u) >= 0;
}

```

## disassembly

```asm
0x180006f40  push    rbx
0x180006f42  sub     rsp, 70h
0x180006f46  xorps   xmm0, xmm0
0x180006f49  mov     [rsp+78h+var_48], 0Fh
0x180006f51  mov     rbx, rdx
0x180006f54  mov     [rsp+78h+ReturnLength], 0; ReturnLength
0x180006f5d  xor     edx, edx; ThreadInformationClass
0x180006f5f  lea     r8, [rsp+78h+ThreadInformation]; ThreadInformation
0x180006f64  mov     r9d, 30h ; '0'; ThreadInformationLength
0x180006f6a  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180006f71  movups  [rsp+78h+ThreadInformation], xmm0
0x180006f76  movups  [rsp+78h+var_30], xmm0
0x180006f7b  movups  [rsp+78h+var_20], xmm0
0x180006f80  call    cs:__imp_NtQueryInformationThread
0x180006f86  test    eax, eax
0x180006f88  js      short loc_180006FBA
0x180006f8a  mov     eax, dword ptr [rsp+78h+var_20+8]
0x180006f8e  cmp     eax, [rsp+78h+var_48]
0x180006f92  jge     short loc_180006FBA
0x180006f94  mov     r9d, 4; ThreadInformationLength
0x180006f9a  mov     [rbx], eax
0x180006f9c  lea     r8, [rsp+78h+var_48]; ThreadInformation
0x180006fa1  mov     edx, 2; ThreadInformationClass
0x180006fa6  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180006fad  call    cs:__imp_NtSetInformationThread
0x180006fb3  shr     eax, 1Fh
0x180006fb6  xor     al, 1
0x180006fb8  jmp     short loc_180006FBC
0x180006fba  xor     al, al
0x180006fbc  add     rsp, 70h
0x180006fc0  pop     rbx
0x180006fc1  retn
```
