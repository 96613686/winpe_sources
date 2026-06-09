# BasepInitializeApphelpGlobals

- ea: `0x18002eafc`
- end: `0x18002ee66`
- name: `BasepInitializeApphelpGlobals`
- size: `874`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002e5a0`
- `0x18002e610`
- `0x18006fc40`
- `0x18006fe90`
- `0x180070100`

## callees

- `0x18002eafc`
- `0x1800700b4`
- `0x18007a840`

## import_xrefs

- `ntdll!LdrLoadDll` at `0x18002ec48`
- `ntdll!LdrLoadDll` at `0x18002ec48`
- `ntdll!RtlAppendUnicodeToString` at `0x18002ec12`
- `ntdll!RtlAppendUnicodeToString` at `0x18002ec12`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18002ec2a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18002ec2a`
- `ntdll!LdrGetProcedureAddress` at `0x18002ec83`
- `ntdll!LdrGetProcedureAddress` at `0x18002eca7`
- `ntdll!LdrGetProcedureAddress` at `0x18002eccb`
- `ntdll!LdrGetProcedureAddress` at `0x18002ecef`
- `ntdll!LdrGetProcedureAddress` at `0x18002ed13`
- `ntdll!LdrGetProcedureAddress` at `0x18002ed37`
- `ntdll!LdrGetProcedureAddress` at `0x18002ed5b`
- `ntdll!LdrGetProcedureAddress` at `0x18002ed7f`
- `ntdll!LdrGetProcedureAddress` at `0x18002ec83`
- `ntdll!LdrGetProcedureAddress` at `0x18002eca7`
- `ntdll!LdrGetProcedureAddress` at `0x18002eccb`
- `ntdll!LdrGetProcedureAddress` at `0x18002ecef`
- `ntdll!LdrGetProcedureAddress` at `0x18002ed13`
- `ntdll!LdrGetProcedureAddress` at `0x18002ed37`
- `ntdll!LdrGetProcedureAddress` at `0x18002ed5b`
- `ntdll!LdrGetProcedureAddress` at `0x18002ed7f`
- `ntdll!LdrAddRefDll` at `0x18002ec5f`
- `ntdll!LdrAddRefDll` at `0x18002ec5f`
- `ntdll!wcslen` at `0x18002ebdc`
- `ntdll!wcslen` at `0x18002ebdc`
- `ntdll!RtlEncodeSystemPointer` at `0x18002ed94`
- `ntdll!RtlEncodeSystemPointer` at `0x18002edad`
- `ntdll!RtlEncodeSystemPointer` at `0x18002edc6`
- `ntdll!RtlEncodeSystemPointer` at `0x18002eddf`
- `ntdll!RtlEncodeSystemPointer` at `0x18002edf8`
- `ntdll!RtlEncodeSystemPointer` at `0x18002ee11`
- `ntdll!RtlEncodeSystemPointer` at `0x18002ee2a`
- `ntdll!RtlEncodeSystemPointer` at `0x18002ee43`
- `ntdll!RtlEncodeSystemPointer` at `0x18002ed94`
- `ntdll!RtlEncodeSystemPointer` at `0x18002edad`
- `ntdll!RtlEncodeSystemPointer` at `0x18002edc6`
- `ntdll!RtlEncodeSystemPointer` at `0x18002eddf`
- `ntdll!RtlEncodeSystemPointer` at `0x18002edf8`
- `ntdll!RtlEncodeSystemPointer` at `0x18002ee11`
- `ntdll!RtlEncodeSystemPointer` at `0x18002ee2a`
- `ntdll!RtlEncodeSystemPointer` at `0x18002ee43`

## pseudocode

```c
__int64 BasepInitializeApphelpGlobals()
{
  bool v0; // zf
  int v1; // eax
  NTSTATUS appended; // ebx
  PVOID BaseAddress; // [rsp+20h] [rbp-E0h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+28h] [rbp-D8h] BYREF
  PVOID ProcedureAddress; // [rsp+38h] [rbp-C8h] BYREF
  PVOID Pointer; // [rsp+40h] [rbp-C0h] BYREF
  PVOID v8; // [rsp+48h] [rbp-B8h] BYREF
  PVOID v9; // [rsp+50h] [rbp-B0h] BYREF
  PVOID v10; // [rsp+58h] [rbp-A8h] BYREF
  PVOID v11; // [rsp+60h] [rbp-A0h] BYREF
  PVOID v12; // [rsp+68h] [rbp-98h] BYREF
  PVOID v13; // [rsp+70h] [rbp-90h] BYREF
  char v14; // [rsp+80h] [rbp-80h] BYREF

  BaseAddress = 0;
  Destination = 0;
  ProcedureAddress = 0;
  Pointer = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v0 = (unsigned int)Feature_ApphelpPfnLoadMemoryBarrier__private_IsEnabledDeviceUsageNoInline() == 0;
  v1 = gApphelpGlobals;
  if ( v0 )
  {
    if ( gApphelpGlobals == 1 )
      return 0;
  }
  else
  {
    if ( gApphelpGlobals == 1 )
      return 0;
    v1 = gApphelpGlobals;
  }
  if ( v1 == -1 )
  {
    appended = -1073741823;
  }
  else if ( 2 * (unsigned int)wcslen((const wchar_t *)0x7FFE0030) + 44 <= 0x208 )
  {
    *(_DWORD *)&Destination.Length = 34078720;
    Destination.Buffer = (PWSTR)&v14;
    appended = RtlAppendUnicodeToString(&Destination, (PCWSTR)0x7FFE0030);
    if ( appended >= 0 )
    {
      appended = RtlAppendUnicodeStringToString(&Destination, &stru_18007EE30);
      if ( appended >= 0 )
      {
        appended = LdrLoadDll(0, 0, &Destination, &BaseAddress);
        if ( appended >= 0 )
        {
          appended = LdrAddRefDll(1u, BaseAddress);
          if ( appended >= 0 )
          {
            appended = LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&Name, 0, &ProcedureAddress);
            if ( appended >= 0 )
            {
              appended = LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&stru_18007EE10, 0, &Pointer);
              if ( appended >= 0 )
              {
                appended = LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&stru_18007EE20, 0, &v8);
                if ( appended >= 0 )
                {
                  appended = LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&stru_18007EDF0, 0, &v9);
                  if ( appended >= 0 )
                  {
                    appended = LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&stru_18007EE00, 0, &v10);
                    if ( appended >= 0 )
                    {
                      appended = LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&stru_18007EDD0, 0, &v11);
                      if ( appended >= 0 )
                      {
                        appended = LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&stru_18007EDE0, 0, &v12);
                        if ( appended >= 0 )
                        {
                          appended = LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&stru_18007EDC0, 0, &v13);
                          if ( appended >= 0 )
                          {
                            _InterlockedCompareExchange64(
                              (volatile signed __int64 *)&qword_1800B6050,
                              (signed __int64)RtlEncodeSystemPointer(ProcedureAddress),
                              0);
                            _InterlockedCompareExchange64(
                              (volatile signed __int64 *)&::Pointer,
                              (signed __int64)RtlEncodeSystemPointer(Pointer),
                              0);
                            _InterlockedCompareExchange64(
                              (volatile signed __int64 *)&qword_1800B6060,
                              (signed __int64)RtlEncodeSystemPointer(v8),
                              0);
                            _InterlockedCompareExchange64(
                              (volatile signed __int64 *)&qword_1800B6068,
                              (signed __int64)RtlEncodeSystemPointer(v9),
                              0);
                            _InterlockedCompareExchange64(
                              (volatile signed __int64 *)&qword_1800B6070,
                              (signed __int64)RtlEncodeSystemPointer(v10),
                              0);
                            _InterlockedCompareExchange64(
                              (volatile signed __int64 *)&qword_1800B6078,
                              (signed __int64)RtlEncodeSystemPointer(v11),
                              0);
                            _InterlockedCompareExchange64(
                              (volatile signed __int64 *)&qword_1800B6080,
                              (signed __int64)RtlEncodeSystemPointer(v12),
                              0);
                            _InterlockedCompareExchange64(
                              (volatile signed __int64 *)&qword_1800B6088,
                              (signed __int64)RtlEncodeSystemPointer(v13),
                              0);
                            _InterlockedCompareExchange(&gApphelpGlobals, 1, 0);
                            return (unsigned int)appended;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    appended = -1073741789;
  }
  _InterlockedCompareExchange(&gApphelpGlobals, -1, 0);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18002eafc  push    rbp
0x18002eafe  push    rbx
0x18002eaff  push    rsi
0x18002eb00  push    rdi
0x18002eb01  lea     rbp, [rsp-1A8h]
0x18002eb09  sub     rsp, 2A8h
0x18002eb10  mov     rax, cs:__security_cookie
0x18002eb17  xor     rax, rsp
0x18002eb1a  mov     [rbp+1C0h+var_30], rax
0x18002eb21  xorps   xmm0, xmm0
0x18002eb24  mov     [rsp+2C0h+BaseAddress], 0
0x18002eb2d  movups  xmmword ptr [rsp+2C0h+Destination.Length], xmm0
0x18002eb32  mov     [rsp+2C0h+ProcedureAddress], 0
0x18002eb3b  mov     [rsp+2C0h+Pointer], 0
0x18002eb44  mov     [rsp+2C0h+var_278], 0
0x18002eb4d  mov     [rsp+2C0h+var_270], 0
0x18002eb56  mov     [rsp+2C0h+var_268], 0
0x18002eb5f  mov     [rsp+2C0h+var_260], 0
0x18002eb68  mov     [rsp+2C0h+var_258], 0
0x18002eb71  mov     [rsp+2C0h+var_250], 0
0x18002eb7a  call    Feature_ApphelpPfnLoadMemoryBarrier__private_IsEnabledDeviceUsageNoInline
0x18002eb7f  test    eax, eax
0x18002eb81  mov     edi, 1
0x18002eb86  mov     eax, cs:gApphelpGlobals
0x18002eb8c  jz      short loc_18002EBCF
0x18002eb8e  cmp     eax, edi
0x18002eb90  jnz     short loc_18002EB96
0x18002eb92  xor     ebx, ebx
0x18002eb94  jmp     short loc_18002EBB2
0x18002eb96  mov     eax, cs:gApphelpGlobals
0x18002eb9c  or      esi, 0FFFFFFFFh
0x18002eb9f  cmp     eax, esi
0x18002eba1  jnz     short loc_18002EBD5
0x18002eba3  mov     ebx, 0C0000001h
0x18002eba8  xor     eax, eax
0x18002ebaa  lock cmpxchg cs:gApphelpGlobals, esi
0x18002ebb2  mov     eax, ebx
0x18002ebb4  mov     rcx, [rbp+1C0h+var_30]
0x18002ebbb  xor     rcx, rsp; StackCookie
0x18002ebbe  call    __security_check_cookie
0x18002ebc3  add     rsp, 2A8h
0x18002ebca  pop     rdi
0x18002ebcb  pop     rsi
0x18002ebcc  pop     rbx
0x18002ebcd  pop     rbp
0x18002ebce  retn
0x18002ebcf  cmp     eax, edi
0x18002ebd1  jnz     short loc_18002EB9C
0x18002ebd3  jmp     short loc_18002EB92
0x18002ebd5  mov     ebx, 7FFE0030h
0x18002ebda  mov     ecx, ebx; String
0x18002ebdc  call    cs:__imp_wcslen
0x18002ebe2  mov     ecx, 208h
0x18002ebe7  lea     eax, ds:2Ch[rax*2]
0x18002ebee  cmp     eax, ecx
0x18002ebf0  jbe     short loc_18002EBF9
0x18002ebf2  mov     ebx, 0C0000023h
0x18002ebf7  jmp     short loc_18002EBA8
0x18002ebf9  lea     rax, [rbp+1C0h+var_240]
0x18002ebfd  mov     dword ptr [rsp+2C0h+Destination.Length], 2080000h
0x18002ec05  mov     rdx, rbx; Source
0x18002ec08  mov     [rsp+2C0h+Destination.Buffer], rax
0x18002ec0d  lea     rcx, [rsp+2C0h+Destination]; Destination
0x18002ec12  call    cs:__imp_RtlAppendUnicodeToString
0x18002ec18  mov     ebx, eax
0x18002ec1a  test    eax, eax
0x18002ec1c  js      short loc_18002EBA8
0x18002ec1e  lea     rdx, stru_18007EE30; Source
0x18002ec25  lea     rcx, [rsp+2C0h+Destination]; Destination
0x18002ec2a  call    cs:__imp_RtlAppendUnicodeStringToString
0x18002ec30  mov     ebx, eax
0x18002ec32  test    eax, eax
0x18002ec34  js      loc_18002EBA8
0x18002ec3a  lea     r9, [rsp+2C0h+BaseAddress]; BaseAddress
0x18002ec3f  xor     edx, edx; LoadFlags
0x18002ec41  lea     r8, [rsp+2C0h+Destination]; Name
0x18002ec46  xor     ecx, ecx; SearchPath
0x18002ec48  call    cs:__imp_LdrLoadDll
0x18002ec4e  mov     ebx, eax
0x18002ec50  test    eax, eax
0x18002ec52  js      loc_18002EBA8
0x18002ec58  mov     rdx, [rsp+2C0h+BaseAddress]; BaseAddress
0x18002ec5d  mov     ecx, edi; Flags
0x18002ec5f  call    cs:__imp_LdrAddRefDll
0x18002ec65  mov     ebx, eax
0x18002ec67  test    eax, eax
0x18002ec69  js      loc_18002EBA8
0x18002ec6f  mov     rcx, [rsp+2C0h+BaseAddress]; BaseAddress
0x18002ec74  lea     r9, [rsp+2C0h+ProcedureAddress]; ProcedureAddress
0x18002ec79  xor     r8d, r8d; Ordinal
0x18002ec7c  lea     rdx, Name; Name
0x18002ec83  call    cs:__imp_LdrGetProcedureAddress
0x18002ec89  mov     ebx, eax
0x18002ec8b  test    eax, eax
0x18002ec8d  js      loc_18002EBA8
0x18002ec93  mov     rcx, [rsp+2C0h+BaseAddress]; BaseAddress
0x18002ec98  lea     r9, [rsp+2C0h+Pointer]; ProcedureAddress
0x18002ec9d  xor     r8d, r8d; Ordinal
0x18002eca0  lea     rdx, stru_18007EE10; Name
0x18002eca7  call    cs:__imp_LdrGetProcedureAddress
0x18002ecad  mov     ebx, eax
0x18002ecaf  test    eax, eax
0x18002ecb1  js      loc_18002EBA8
0x18002ecb7  mov     rcx, [rsp+2C0h+BaseAddress]; BaseAddress
0x18002ecbc  lea     r9, [rsp+2C0h+var_278]; ProcedureAddress
0x18002ecc1  xor     r8d, r8d; Ordinal
0x18002ecc4  lea     rdx, stru_18007EE20; Name
0x18002eccb  call    cs:__imp_LdrGetProcedureAddress
0x18002ecd1  mov     ebx, eax
0x18002ecd3  test    eax, eax
0x18002ecd5  js      loc_18002EBA8
0x18002ecdb  mov     rcx, [rsp+2C0h+BaseAddress]; BaseAddress
0x18002ece0  lea     r9, [rsp+2C0h+var_270]; ProcedureAddress
0x18002ece5  xor     r8d, r8d; Ordinal
0x18002ece8  lea     rdx, stru_18007EDF0; Name
0x18002ecef  call    cs:__imp_LdrGetProcedureAddress
0x18002ecf5  mov     ebx, eax
0x18002ecf7  test    eax, eax
0x18002ecf9  js      loc_18002EBA8
0x18002ecff  mov     rcx, [rsp+2C0h+BaseAddress]; BaseAddress
0x18002ed04  lea     r9, [rsp+2C0h+var_268]; ProcedureAddress
0x18002ed09  xor     r8d, r8d; Ordinal
0x18002ed0c  lea     rdx, stru_18007EE00; Name
0x18002ed13  call    cs:__imp_LdrGetProcedureAddress
0x18002ed19  mov     ebx, eax
0x18002ed1b  test    eax, eax
0x18002ed1d  js      loc_18002EBA8
0x18002ed23  mov     rcx, [rsp+2C0h+BaseAddress]; BaseAddress
0x18002ed28  lea     r9, [rsp+2C0h+var_260]; ProcedureAddress
0x18002ed2d  xor     r8d, r8d; Ordinal
0x18002ed30  lea     rdx, stru_18007EDD0; Name
0x18002ed37  call    cs:__imp_LdrGetProcedureAddress
0x18002ed3d  mov     ebx, eax
0x18002ed3f  test    eax, eax
0x18002ed41  js      loc_18002EBA8
0x18002ed47  mov     rcx, [rsp+2C0h+BaseAddress]; BaseAddress
0x18002ed4c  lea     r9, [rsp+2C0h+var_258]; ProcedureAddress
0x18002ed51  xor     r8d, r8d; Ordinal
0x18002ed54  lea     rdx, stru_18007EDE0; Name
0x18002ed5b  call    cs:__imp_LdrGetProcedureAddress
0x18002ed61  mov     ebx, eax
0x18002ed63  test    eax, eax
0x18002ed65  js      loc_18002EBA8
0x18002ed6b  mov     rcx, [rsp+2C0h+BaseAddress]; BaseAddress
0x18002ed70  lea     r9, [rsp+2C0h+var_250]; ProcedureAddress
0x18002ed75  xor     r8d, r8d; Ordinal
0x18002ed78  lea     rdx, stru_18007EDC0; Name
0x18002ed7f  call    cs:__imp_LdrGetProcedureAddress
0x18002ed85  mov     ebx, eax
0x18002ed87  test    eax, eax
0x18002ed89  js      loc_18002EBA8
0x18002ed8f  mov     rcx, [rsp+2C0h+ProcedureAddress]; Pointer
0x18002ed94  call    cs:__imp_RtlEncodeSystemPointer
0x18002ed9a  mov     rcx, rax
0x18002ed9d  xor     eax, eax
0x18002ed9f  lock cmpxchg cs:qword_1800B6050, rcx
0x18002eda8  mov     rcx, [rsp+2C0h+Pointer]; Pointer
0x18002edad  call    cs:__imp_RtlEncodeSystemPointer
0x18002edb3  mov     rcx, rax
0x18002edb6  xor     eax, eax
0x18002edb8  lock cmpxchg cs:Pointer, rcx
0x18002edc1  mov     rcx, [rsp+2C0h+var_278]; Pointer
0x18002edc6  call    cs:__imp_RtlEncodeSystemPointer
0x18002edcc  mov     rcx, rax
0x18002edcf  xor     eax, eax
0x18002edd1  lock cmpxchg cs:qword_1800B6060, rcx
0x18002edda  mov     rcx, [rsp+2C0h+var_270]; Pointer
0x18002eddf  call    cs:__imp_RtlEncodeSystemPointer
0x18002ede5  mov     rcx, rax
0x18002ede8  xor     eax, eax
0x18002edea  lock cmpxchg cs:qword_1800B6068, rcx
0x18002edf3  mov     rcx, [rsp+2C0h+var_268]; Pointer
0x18002edf8  call    cs:__imp_RtlEncodeSystemPointer
0x18002edfe  mov     rcx, rax
0x18002ee01  xor     eax, eax
0x18002ee03  lock cmpxchg cs:qword_1800B6070, rcx
0x18002ee0c  mov     rcx, [rsp+2C0h+var_260]; Pointer
0x18002ee11  call    cs:__imp_RtlEncodeSystemPointer
0x18002ee17  mov     rcx, rax
0x18002ee1a  xor     eax, eax
0x18002ee1c  lock cmpxchg cs:qword_1800B6078, rcx
0x18002ee25  mov     rcx, [rsp+2C0h+var_258]; Pointer
0x18002ee2a  call    cs:__imp_RtlEncodeSystemPointer
0x18002ee30  mov     rcx, rax
0x18002ee33  xor     eax, eax
0x18002ee35  lock cmpxchg cs:qword_1800B6080, rcx
0x18002ee3e  mov     rcx, [rsp+2C0h+var_250]; Pointer
0x18002ee43  call    cs:__imp_RtlEncodeSystemPointer
0x18002ee49  mov     rcx, rax
0x18002ee4c  xor     eax, eax
0x18002ee4e  lock cmpxchg cs:qword_1800B6088, rcx
0x18002ee57  xor     eax, eax
0x18002ee59  lock cmpxchg cs:gApphelpGlobals, edi
0x18002ee61  jmp     loc_18002EBB2
```
