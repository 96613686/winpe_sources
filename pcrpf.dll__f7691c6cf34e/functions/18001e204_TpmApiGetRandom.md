# TpmApiGetRandom

- ea: `0x18001e204`
- end: `0x18001e2db`
- name: `TpmApiGetRandom`
- size: `215`
- prototype: `__int64 __fastcall(ULONG cbBuffer, PUCHAR pbBuffer)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001d940`

## callees

- `0x18001e204`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001e256`
- `ntdll!RtlNtStatusToDosError` at `0x18001e291`
- `ntdll!RtlNtStatusToDosError` at `0x18001e256`
- `ntdll!RtlNtStatusToDosError` at `0x18001e291`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001e248`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001e248`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001e2bc`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001e2bc`
- `bcrypt!BCryptGenRandom` at `0x18001e283`
- `bcrypt!BCryptGenRandom` at `0x18001e283`

## pseudocode

```c
__int64 __fastcall TpmApiGetRandom(ULONG cbBuffer, PUCHAR pbBuffer)
{
  BCRYPT_ALG_HANDLE v4; // rcx
  signed int v5; // ebx
  NTSTATUS v6; // eax
  signed int v7; // eax
  NTSTATUS v8; // eax
  signed int v9; // eax
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp+18h] BYREF

  v4 = 0;
  phAlgorithm = 0;
  if ( cbBuffer )
  {
    if ( !pbBuffer )
      return (unsigned int)-2144796413;
    v6 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RNG", 0, 0);
    v7 = RtlNtStatusToDosError(v6);
    v5 = v7;
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    v4 = phAlgorithm;
    if ( v5 >= 0 )
    {
      v8 = BCryptGenRandom(phAlgorithm, pbBuffer, cbBuffer, 0);
      v9 = RtlNtStatusToDosError(v8);
      v5 = v9;
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      v4 = phAlgorithm;
    }
  }
  else
  {
    v5 = 0;
  }
  if ( v4 )
    BCryptCloseAlgorithmProvider(v4, 0);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001e204  mov     [rsp+arg_0], rbx
0x18001e209  mov     [rsp+arg_8], rsi
0x18001e20e  push    rdi
0x18001e20f  sub     rsp, 20h
0x18001e213  mov     esi, ecx
0x18001e215  mov     rdi, rdx
0x18001e218  xor     ecx, ecx; hAlgorithm
0x18001e21a  mov     [rsp+28h+phAlgorithm], rcx
0x18001e21f  test    esi, esi
0x18001e221  jz      loc_18001E2B3
0x18001e227  test    rdx, rdx
0x18001e22a  jnz     short loc_18001E236
0x18001e22c  mov     ebx, 80290103h
0x18001e231  jmp     loc_18001E2C8
0x18001e236  xor     r9d, r9d; dwFlags
0x18001e239  lea     rdx, aRng; "RNG"
0x18001e240  xor     r8d, r8d; pszImplementation
0x18001e243  lea     rcx, [rsp+28h+phAlgorithm]; phAlgorithm
0x18001e248  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001e24f  nop     dword ptr [rax+rax+00h]
0x18001e254  mov     ecx, eax; Status
0x18001e256  call    cs:__imp_RtlNtStatusToDosError
0x18001e25d  nop     dword ptr [rax+rax+00h]
0x18001e262  mov     ebx, eax
0x18001e264  test    eax, eax
0x18001e266  jle     short loc_18001E271
0x18001e268  movzx   ebx, ax
0x18001e26b  or      ebx, 80070000h
0x18001e271  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x18001e276  test    ebx, ebx
0x18001e278  js      short loc_18001E2B5
0x18001e27a  xor     r9d, r9d; dwFlags
0x18001e27d  mov     r8d, esi; cbBuffer
0x18001e280  mov     rdx, rdi; pbBuffer
0x18001e283  call    cs:__imp_BCryptGenRandom
0x18001e28a  nop     dword ptr [rax+rax+00h]
0x18001e28f  mov     ecx, eax; Status
0x18001e291  call    cs:__imp_RtlNtStatusToDosError
0x18001e298  nop     dword ptr [rax+rax+00h]
0x18001e29d  mov     ebx, eax
0x18001e29f  test    eax, eax
0x18001e2a1  jle     short loc_18001E2AC
0x18001e2a3  movzx   ebx, ax
0x18001e2a6  or      ebx, 80070000h
0x18001e2ac  mov     rcx, [rsp+28h+phAlgorithm]
0x18001e2b1  jmp     short loc_18001E2B5
0x18001e2b3  xor     ebx, ebx
0x18001e2b5  test    rcx, rcx
0x18001e2b8  jz      short loc_18001E2C8
0x18001e2ba  xor     edx, edx; dwFlags
0x18001e2bc  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18001e2c3  nop     dword ptr [rax+rax+00h]
0x18001e2c8  mov     rsi, [rsp+28h+arg_8]
0x18001e2cd  mov     eax, ebx
0x18001e2cf  mov     rbx, [rsp+28h+arg_0]
0x18001e2d4  add     rsp, 20h
0x18001e2d8  pop     rdi
0x18001e2d9  retn
```
