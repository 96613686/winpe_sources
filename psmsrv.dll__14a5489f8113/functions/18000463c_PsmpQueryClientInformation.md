# PsmpQueryClientInformation

- ea: `0x18000463c`
- end: `0x180004723`
- name: `PsmpQueryClientInformation`
- size: `231`
- prototype: `NTSTATUS __fastcall(HANDLE ProcessHandle, HANDLE TokenHandle, _DWORD *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180003ec8`
- `0x1800043d8`

## callees

- `0x18000463c`
- `0x18001b7e0`
- `0x18001c10c`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x1800046a2`
- `ntdll!NtQueryInformationProcess` at `0x1800046a2`
- `ntdll!NtQueryInformationToken` at `0x1800046c8`
- `ntdll!NtQueryInformationToken` at `0x1800046c8`

## pseudocode

```c
NTSTATUS __fastcall PsmpQueryClientInformation(HANDLE ProcessHandle, HANDLE TokenHandle, _DWORD *a3, __int64 a4)
{
  NTSTATUS result; // eax
  NTSTATUS InformationToken; // edx
  __int64 v10; // rcx
  int v11; // eax
  int ProcessInformation; // [rsp+30h] [rbp-A8h] BYREF
  ULONG ReturnLength[3]; // [rsp+34h] [rbp-A4h] BYREF
  _QWORD TokenInformation[12]; // [rsp+40h] [rbp-98h] BYREF

  ReturnLength[0] = 0;
  ProcessInformation = 0;
  memset_0(TokenInformation, 0, 0x58u);
  result = NtQueryInformationProcess(ProcessHandle, ProcessSessionInformation, &ProcessInformation, 4u, 0);
  if ( result >= 0 )
  {
    InformationToken = NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x58u, ReturnLength);
    if ( InformationToken >= 0 )
    {
      v10 = TokenInformation[0];
      v11 = ProcessInformation;
      *(_OWORD *)a4 = *(_OWORD *)TokenInformation[0];
      *(_OWORD *)(a4 + 16) = *(_OWORD *)(v10 + 16);
      *(_OWORD *)(a4 + 32) = *(_OWORD *)(v10 + 32);
      *(_OWORD *)(a4 + 48) = *(_OWORD *)(v10 + 48);
      *(_DWORD *)(a4 + 64) = *(_DWORD *)(v10 + 64);
      *a3 = v11;
    }
    return InformationToken;
  }
  return result;
}

```

## disassembly

```asm
0x18000463c  push    rbx
0x18000463e  push    rsi
0x18000463f  push    rdi
0x180004640  push    r14
0x180004642  sub     rsp, 0B8h
0x180004649  mov     rax, cs:__security_cookie
0x180004650  xor     rax, rsp
0x180004653  mov     [rsp+0D8h+var_38], rax
0x18000465b  mov     rsi, rdx
0x18000465e  mov     [rsp+0D8h+var_A4], 0
0x180004666  xor     edx, edx; Val
0x180004668  mov     [rsp+0D8h+ProcessInformation], 0
0x180004670  mov     r14, r8
0x180004673  mov     rbx, rcx
0x180004676  lea     rcx, [rsp+0D8h+TokenInformation]; void *
0x18000467b  mov     rdi, r9
0x18000467e  lea     r8d, [rdx+58h]; Size
0x180004682  call    memset_0
0x180004687  mov     r9d, 4; ProcessInformationLength
0x18000468d  mov     [rsp+0D8h+ReturnLength], 0; ReturnLength
0x180004696  lea     r8, [rsp+0D8h+ProcessInformation]; ProcessInformation
0x18000469b  mov     rcx, rbx; ProcessHandle
0x18000469e  lea     edx, [r9+14h]; ProcessInformationClass
0x1800046a2  call    cs:__imp_NtQueryInformationProcess
0x1800046a8  test    eax, eax
0x1800046aa  js      short loc_180004706
0x1800046ac  mov     r9d, 58h ; 'X'; TokenInformationLength
0x1800046b2  lea     rax, [rsp+0D8h+var_A4]
0x1800046b7  lea     r8, [rsp+0D8h+TokenInformation]; TokenInformation
0x1800046bc  mov     [rsp+0D8h+ReturnLength], rax; ReturnLength
0x1800046c1  mov     rcx, rsi; TokenHandle
0x1800046c4  lea     edx, [r9-57h]; TokenInformationClass
0x1800046c8  call    cs:__imp_NtQueryInformationToken
0x1800046ce  mov     edx, eax
0x1800046d0  test    eax, eax
0x1800046d2  js      short loc_180004704
0x1800046d4  mov     rcx, [rsp+0D8h+TokenInformation]
0x1800046d9  mov     eax, [rsp+0D8h+ProcessInformation]
0x1800046dd  movups  xmm0, xmmword ptr [rcx]
0x1800046e0  movups  xmmword ptr [rdi], xmm0
0x1800046e3  movups  xmm1, xmmword ptr [rcx+10h]
0x1800046e7  movups  xmmword ptr [rdi+10h], xmm1
0x1800046eb  movups  xmm0, xmmword ptr [rcx+20h]
0x1800046ef  movups  xmmword ptr [rdi+20h], xmm0
0x1800046f3  movups  xmm1, xmmword ptr [rcx+30h]
0x1800046f7  movups  xmmword ptr [rdi+30h], xmm1
0x1800046fb  mov     ecx, [rcx+40h]
0x1800046fe  mov     [rdi+40h], ecx
0x180004701  mov     [r14], eax
0x180004704  mov     eax, edx
0x180004706  mov     rcx, [rsp+0D8h+var_38]
0x18000470e  xor     rcx, rsp; StackCookie
0x180004711  call    __security_check_cookie
0x180004716  add     rsp, 0B8h
0x18000471d  pop     r14
0x18000471f  pop     rdi
0x180004720  pop     rsi
0x180004721  pop     rbx
0x180004722  retn
```
