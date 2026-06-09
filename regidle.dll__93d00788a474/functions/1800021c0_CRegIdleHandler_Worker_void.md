# CRegIdleHandler::Worker(void)

- ea: `0x1800021c0`
- end: `0x180002315`
- name: `?Worker@CRegIdleHandler@@EEAAJXZ`
- size: `341`
- prototype: `__int64 __fastcall(CRegIdleHandler *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800021c0`
- `0x180002658`

## import_xrefs

- `ntdll!RtlGetSuiteMask` at `0x1800021e5`
- `ntdll!RtlGetSuiteMask` at `0x1800021e5`
- `ntdll!RtlImpersonateSelf` at `0x180002247`
- `ntdll!RtlImpersonateSelf` at `0x180002247`
- `ntdll!RtlNtStatusToDosError` at `0x180002213`
- `ntdll!RtlNtStatusToDosError` at `0x1800022cb`
- `ntdll!RtlNtStatusToDosError` at `0x180002213`
- `ntdll!RtlNtStatusToDosError` at `0x1800022cb`
- `ntdll!RtlAdjustPrivilege` at `0x180002266`
- `ntdll!RtlAdjustPrivilege` at `0x1800022a7`
- `ntdll!RtlAdjustPrivilege` at `0x180002266`
- `ntdll!RtlAdjustPrivilege` at `0x1800022a7`
- `ntdll!NtInitializeRegistry` at `0x18000228c`
- `ntdll!NtInitializeRegistry` at `0x18000228c`
- `ntdll!NtSetInformationThread` at `0x1800022ff`
- `ntdll!NtSetInformationThread` at `0x1800022ff`
- `ntdll!RtlGetNtSystemRoot` at `0x1800021fa`
- `ntdll!RtlGetNtSystemRoot` at `0x1800021fa`

## pseudocode

```c
__int64 __fastcall CRegIdleHandler::Worker(CRegIdleHandler *this)
{
  const wchar_t *NtSystemRoot; // rax
  int v3; // eax
  signed int v4; // eax
  unsigned int v5; // ebx
  NTSTATUS v6; // eax
  NTSTATUS v7; // edi
  NTSTATUS v8; // ecx
  signed int v9; // eax
  unsigned __int8 OldValue; // [rsp+48h] [rbp+10h] BYREF
  int v12; // [rsp+50h] [rbp+18h] BYREF
  __int64 ThreadInformation; // [rsp+58h] [rbp+20h] BYREF

  v12 = 0;
  ThreadInformation = 0;
  OldValue = 0;
  if ( (RtlGetSuiteMask() & 0x10000) != 0 )
    NtSystemRoot = L"C:\\data\\programs\\windowsapps";
  else
    NtSystemRoot = (const wchar_t *)RtlGetNtSystemRoot();
  v3 = RtlpQueryDiskSpacePolicy(NtSystemRoot, &v12);
  if ( v3 >= 0 )
  {
    if ( v12 <= 10 )
      return (unsigned int)-2147024846;
    v3 = RtlImpersonateSelf(SecurityImpersonation);
    if ( v3 >= 0 )
    {
      v6 = RtlAdjustPrivilege(0x11u, 1u, 1u, &OldValue);
      v7 = v6;
      if ( v6 >= 0 )
      {
        v5 = 0;
        while ( _InterlockedCompareExchange((volatile signed __int32 *)this + 9, 1, 1) != 1 && !v7 )
          v7 = NtInitializeRegistry(0x13E8u);
        RtlAdjustPrivilege(0x11u, OldValue, 1u, &OldValue);
        if ( !v7 || v7 == -2147483622 || v7 == -1073741431 || v7 == -1073741077 )
        {
LABEL_23:
          ThreadInformation = 0;
          NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
          return v5;
        }
        v8 = v7;
      }
      else
      {
        v8 = v6;
      }
      v9 = RtlNtStatusToDosError(v8);
      v5 = v9;
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      goto LABEL_23;
    }
  }
  v4 = RtlNtStatusToDosError(v3);
  v5 = v4;
  if ( v4 > 0 )
    return (unsigned __int16)v4 | 0x80070000;
  return v5;
}

```

## disassembly

```asm
0x1800021c0  mov     rax, rsp
0x1800021c3  mov     [rax+8], rbx
0x1800021c7  push    rsi
0x1800021c8  push    rdi
0x1800021c9  push    r14
0x1800021cb  sub     rsp, 20h
0x1800021cf  mov     rsi, rcx
0x1800021d2  mov     dword ptr [rax+18h], 0
0x1800021d9  mov     qword ptr [rax+20h], 0
0x1800021e1  mov     byte ptr [rax+10h], 0
0x1800021e5  call    cs:__imp_RtlGetSuiteMask
0x1800021eb  bt      eax, 10h
0x1800021ef  jnb     short loc_1800021FA
0x1800021f1  lea     rax, aCDataProgramsW; "C:\\data\\programs\\windowsapps"
0x1800021f8  jmp     short loc_180002200
0x1800021fa  call    cs:__imp_RtlGetNtSystemRoot
0x180002200  lea     rdx, [rsp+38h+arg_10]
0x180002205  mov     rcx, rax
0x180002208  call    RtlpQueryDiskSpacePolicy
0x18000220d  test    eax, eax
0x18000220f  jns     short loc_180002231
0x180002211  mov     ecx, eax; Status
0x180002213  call    cs:__imp_RtlNtStatusToDosError
0x180002219  mov     ebx, eax
0x18000221b  test    eax, eax
0x18000221d  jle     loc_180002305
0x180002223  movzx   ebx, ax
0x180002226  or      ebx, 80070000h
0x18000222c  jmp     loc_180002305
0x180002231  cmp     [rsp+38h+arg_10], 0Ah
0x180002236  jg      short loc_180002242
0x180002238  mov     ebx, 80070032h
0x18000223d  jmp     loc_180002305
0x180002242  mov     ecx, 2; ImpersonationLevel
0x180002247  call    cs:__imp_RtlImpersonateSelf
0x18000224d  test    eax, eax
0x18000224f  js      short loc_180002211
0x180002251  mov     r14d, 1
0x180002257  lea     r9, [rsp+38h+OldValue]; OldValue
0x18000225c  mov     r8b, r14b; ForThread
0x18000225f  mov     dl, r14b; NewValue
0x180002262  lea     ecx, [r14+10h]; Privilege
0x180002266  call    cs:__imp_RtlAdjustPrivilege
0x18000226c  mov     edi, eax
0x18000226e  test    eax, eax
0x180002270  jns     short loc_180002276
0x180002272  mov     ecx, eax
0x180002274  jmp     short loc_1800022CB
0x180002276  xor     ebx, ebx
0x180002278  mov     eax, r14d
0x18000227b  lock cmpxchg [rsi+24h], r14d
0x180002281  jz      short loc_180002296
0x180002283  test    edi, edi
0x180002285  jnz     short loc_180002296
0x180002287  mov     ecx, 13E8h; Flag
0x18000228c  call    cs:__imp_NtInitializeRegistry
0x180002292  mov     edi, eax
0x180002294  jmp     short loc_180002278
0x180002296  mov     dl, [rsp+38h+OldValue]; NewValue
0x18000229a  lea     r9, [rsp+38h+OldValue]; OldValue
0x18000229f  mov     r8b, r14b; ForThread
0x1800022a2  mov     ecx, 11h; Privilege
0x1800022a7  call    cs:__imp_RtlAdjustPrivilege
0x1800022ad  test    edi, edi
0x1800022af  jz      short loc_1800022E0
0x1800022b1  cmp     edi, 8000001Ah
0x1800022b7  jz      short loc_1800022E0
0x1800022b9  cmp     edi, 0C0000189h
0x1800022bf  jz      short loc_1800022E0
0x1800022c1  cmp     edi, 0C00002EBh
0x1800022c7  jz      short loc_1800022E0
0x1800022c9  mov     ecx, edi; Status
0x1800022cb  call    cs:__imp_RtlNtStatusToDosError
0x1800022d1  mov     ebx, eax
0x1800022d3  test    eax, eax
0x1800022d5  jle     short loc_1800022E0
0x1800022d7  movzx   ebx, ax
0x1800022da  or      ebx, 80070000h
0x1800022e0  mov     r9d, 8; ThreadInformationLength
0x1800022e6  mov     [rsp+38h+ThreadInformation], 0
0x1800022ef  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x1800022f4  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800022fb  lea     edx, [r9-3]; ThreadInformationClass
0x1800022ff  call    cs:__imp_NtSetInformationThread
0x180002305  mov     eax, ebx
0x180002307  mov     rbx, [rsp+38h+arg_0]
0x18000230c  add     rsp, 20h
0x180002310  pop     r14
0x180002312  pop     rdi
0x180002313  pop     rsi
0x180002314  retn
```
