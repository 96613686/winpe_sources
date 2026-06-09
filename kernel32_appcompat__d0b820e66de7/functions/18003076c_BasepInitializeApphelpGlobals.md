# BasepInitializeApphelpGlobals

- ea: `0x18003076c`
- end: `0x180030b59`
- name: `BasepInitializeApphelpGlobals`
- size: `1005`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800301d0`
- `0x180030250`
- `0x18007771c`
- `0x180077764`
- `0x180077d20`

## callees

- `0x18003076c`
- `0x180077cd8`
- `0x1800827c0`

## import_xrefs

- `ntdll!LdrLoadDll` at `0x1800308cf`
- `ntdll!LdrLoadDll` at `0x1800308cf`
- `ntdll!RtlAppendUnicodeToString` at `0x180030889`
- `ntdll!RtlAppendUnicodeToString` at `0x180030889`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800308ab`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800308ab`
- `ntdll!LdrGetProcedureAddress` at `0x180030916`
- `ntdll!LdrGetProcedureAddress` at `0x180030940`
- `ntdll!LdrGetProcedureAddress` at `0x18003096a`
- `ntdll!LdrGetProcedureAddress` at `0x180030994`
- `ntdll!LdrGetProcedureAddress` at `0x1800309be`
- `ntdll!LdrGetProcedureAddress` at `0x1800309e8`
- `ntdll!LdrGetProcedureAddress` at `0x180030a12`
- `ntdll!LdrGetProcedureAddress` at `0x180030a3c`
- `ntdll!LdrGetProcedureAddress` at `0x180030916`
- `ntdll!LdrGetProcedureAddress` at `0x180030940`
- `ntdll!LdrGetProcedureAddress` at `0x18003096a`
- `ntdll!LdrGetProcedureAddress` at `0x180030994`
- `ntdll!LdrGetProcedureAddress` at `0x1800309be`
- `ntdll!LdrGetProcedureAddress` at `0x1800309e8`
- `ntdll!LdrGetProcedureAddress` at `0x180030a12`
- `ntdll!LdrGetProcedureAddress` at `0x180030a3c`
- `ntdll!LdrAddRefDll` at `0x1800308ec`
- `ntdll!LdrAddRefDll` at `0x1800308ec`
- `ntdll!wcslen` at `0x18003084d`
- `ntdll!wcslen` at `0x18003084d`
- `ntdll!RtlEncodeSystemPointer` at `0x180030a57`
- `ntdll!RtlEncodeSystemPointer` at `0x180030a76`
- `ntdll!RtlEncodeSystemPointer` at `0x180030a95`
- `ntdll!RtlEncodeSystemPointer` at `0x180030ab4`
- `ntdll!RtlEncodeSystemPointer` at `0x180030ad3`
- `ntdll!RtlEncodeSystemPointer` at `0x180030af2`
- `ntdll!RtlEncodeSystemPointer` at `0x180030b11`
- `ntdll!RtlEncodeSystemPointer` at `0x180030b30`
- `ntdll!RtlEncodeSystemPointer` at `0x180030a57`
- `ntdll!RtlEncodeSystemPointer` at `0x180030a76`
- `ntdll!RtlEncodeSystemPointer` at `0x180030a95`
- `ntdll!RtlEncodeSystemPointer` at `0x180030ab4`
- `ntdll!RtlEncodeSystemPointer` at `0x180030ad3`
- `ntdll!RtlEncodeSystemPointer` at `0x180030af2`
- `ntdll!RtlEncodeSystemPointer` at `0x180030b11`
- `ntdll!RtlEncodeSystemPointer` at `0x180030b30`

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
      appended = RtlAppendUnicodeStringToString(&Destination, &stru_180086E40);
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
              appended = LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&stru_180086E30, 0, &Pointer);
              if ( appended >= 0 )
              {
                appended = LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&stru_180086E00, 0, &v8);
                if ( appended >= 0 )
                {
                  appended = LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&stru_180086E10, 0, &v9);
                  if ( appended >= 0 )
                  {
                    appended = LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&stru_180086DE0, 0, &v10);
                    if ( appended >= 0 )
                    {
                      appended = LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&stru_180086DF0, 0, &v11);
                      if ( appended >= 0 )
                      {
                        appended = LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&stru_180086DC0, 0, &v12);
                        if ( appended >= 0 )
                        {
                          appended = LdrGetProcedureAddress(BaseAddress, (PANSI_STRING)&stru_180086DD0, 0, &v13);
                          if ( appended >= 0 )
                          {
                            _InterlockedCompareExchange64(
                              (volatile signed __int64 *)&qword_1800BE050,
                              (signed __int64)RtlEncodeSystemPointer(ProcedureAddress),
                              0);
                            _InterlockedCompareExchange64(
                              (volatile signed __int64 *)&::Pointer,
                              (signed __int64)RtlEncodeSystemPointer(Pointer),
                              0);
                            _InterlockedCompareExchange64(
                              (volatile signed __int64 *)&qword_1800BE060,
                              (signed __int64)RtlEncodeSystemPointer(v8),
                              0);
                            _InterlockedCompareExchange64(
                              (volatile signed __int64 *)&qword_1800BE068,
                              (signed __int64)RtlEncodeSystemPointer(v9),
                              0);
                            _InterlockedCompareExchange64(
                              (volatile signed __int64 *)&qword_1800BE070,
                              (signed __int64)RtlEncodeSystemPointer(v10),
                              0);
                            _InterlockedCompareExchange64(
                              (volatile signed __int64 *)&qword_1800BE078,
                              (signed __int64)RtlEncodeSystemPointer(v11),
                              0);
                            _InterlockedCompareExchange64(
                              (volatile signed __int64 *)&qword_1800BE080,
                              (signed __int64)RtlEncodeSystemPointer(v12),
                              0);
                            _InterlockedCompareExchange64(
                              (volatile signed __int64 *)&qword_1800BE088,
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
0x18003076c  push    rbp
0x18003076e  push    rbx
0x18003076f  push    rsi
0x180030770  push    rdi
0x180030771  lea     rbp, [rsp-1A8h]
0x180030779  sub     rsp, 2A8h
0x180030780  mov     rax, cs:__security_cookie
0x180030787  xor     rax, rsp
0x18003078a  mov     [rbp+1C0h+var_30], rax
0x180030791  xorps   xmm0, xmm0
0x180030794  mov     [rsp+2C0h+BaseAddress], 0
0x18003079d  movups  xmmword ptr [rsp+2C0h+Destination.Length], xmm0
0x1800307a2  mov     [rsp+2C0h+ProcedureAddress], 0
0x1800307ab  mov     [rsp+2C0h+Pointer], 0
0x1800307b4  mov     [rsp+2C0h+var_278], 0
0x1800307bd  mov     [rsp+2C0h+var_270], 0
0x1800307c6  mov     [rsp+2C0h+var_268], 0
0x1800307cf  mov     [rsp+2C0h+var_260], 0
0x1800307d8  mov     [rsp+2C0h+var_258], 0
0x1800307e1  mov     [rsp+2C0h+var_250], 0
0x1800307ea  call    Feature_ApphelpPfnLoadMemoryBarrier__private_IsEnabledDeviceUsageNoInline
0x1800307ef  test    eax, eax
0x1800307f1  mov     edi, 1
0x1800307f6  mov     eax, cs:gApphelpGlobals
0x1800307fc  jz      short loc_180030840
0x1800307fe  cmp     eax, edi
0x180030800  jnz     short loc_180030806
0x180030802  xor     ebx, ebx
0x180030804  jmp     short loc_180030822
0x180030806  mov     eax, cs:gApphelpGlobals
0x18003080c  or      esi, 0FFFFFFFFh
0x18003080f  cmp     eax, esi
0x180030811  jnz     short loc_180030846
0x180030813  mov     ebx, 0C0000001h
0x180030818  xor     eax, eax
0x18003081a  lock cmpxchg cs:gApphelpGlobals, esi
0x180030822  mov     eax, ebx
0x180030824  mov     rcx, [rbp+1C0h+var_30]
0x18003082b  xor     rcx, rsp; StackCookie
0x18003082e  call    __security_check_cookie
0x180030833  add     rsp, 2A8h
0x18003083a  pop     rdi
0x18003083b  pop     rsi
0x18003083c  pop     rbx
0x18003083d  pop     rbp
0x18003083e  retn
0x180030840  cmp     eax, edi
0x180030842  jnz     short loc_18003080C
0x180030844  jmp     short loc_180030802
0x180030846  mov     ebx, 7FFE0030h
0x18003084b  mov     ecx, ebx; String
0x18003084d  call    cs:__imp_wcslen
0x180030854  nop     dword ptr [rax+rax+00h]
0x180030859  mov     ecx, 208h
0x18003085e  lea     eax, ds:2Ch[rax*2]
0x180030865  cmp     eax, ecx
0x180030867  jbe     short loc_180030870
0x180030869  mov     ebx, 0C0000023h
0x18003086e  jmp     short loc_180030818
0x180030870  lea     rax, [rbp+1C0h+var_240]
0x180030874  mov     dword ptr [rsp+2C0h+Destination.Length], 2080000h
0x18003087c  mov     rdx, rbx; Source
0x18003087f  mov     [rsp+2C0h+Destination.Buffer], rax
0x180030884  lea     rcx, [rsp+2C0h+Destination]; Destination
0x180030889  call    cs:__imp_RtlAppendUnicodeToString
0x180030890  nop     dword ptr [rax+rax+00h]
0x180030895  mov     ebx, eax
0x180030897  test    eax, eax
0x180030899  js      loc_180030818
0x18003089f  lea     rdx, stru_180086E40; Source
0x1800308a6  lea     rcx, [rsp+2C0h+Destination]; Destination
0x1800308ab  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800308b2  nop     dword ptr [rax+rax+00h]
0x1800308b7  mov     ebx, eax
0x1800308b9  test    eax, eax
0x1800308bb  js      loc_180030818
0x1800308c1  lea     r9, [rsp+2C0h+BaseAddress]; BaseAddress
0x1800308c6  xor     edx, edx; LoadFlags
0x1800308c8  lea     r8, [rsp+2C0h+Destination]; Name
0x1800308cd  xor     ecx, ecx; SearchPath
0x1800308cf  call    cs:__imp_LdrLoadDll
0x1800308d6  nop     dword ptr [rax+rax+00h]
0x1800308db  mov     ebx, eax
0x1800308dd  test    eax, eax
0x1800308df  js      loc_180030818
0x1800308e5  mov     rdx, [rsp+2C0h+BaseAddress]; BaseAddress
0x1800308ea  mov     ecx, edi; Flags
0x1800308ec  call    cs:__imp_LdrAddRefDll
0x1800308f3  nop     dword ptr [rax+rax+00h]
0x1800308f8  mov     ebx, eax
0x1800308fa  test    eax, eax
0x1800308fc  js      loc_180030818
0x180030902  mov     rcx, [rsp+2C0h+BaseAddress]; BaseAddress
0x180030907  lea     r9, [rsp+2C0h+ProcedureAddress]; ProcedureAddress
0x18003090c  xor     r8d, r8d; Ordinal
0x18003090f  lea     rdx, Name; Name
0x180030916  call    cs:__imp_LdrGetProcedureAddress
0x18003091d  nop     dword ptr [rax+rax+00h]
0x180030922  mov     ebx, eax
0x180030924  test    eax, eax
0x180030926  js      loc_180030818
0x18003092c  mov     rcx, [rsp+2C0h+BaseAddress]; BaseAddress
0x180030931  lea     r9, [rsp+2C0h+Pointer]; ProcedureAddress
0x180030936  xor     r8d, r8d; Ordinal
0x180030939  lea     rdx, stru_180086E30; Name
0x180030940  call    cs:__imp_LdrGetProcedureAddress
0x180030947  nop     dword ptr [rax+rax+00h]
0x18003094c  mov     ebx, eax
0x18003094e  test    eax, eax
0x180030950  js      loc_180030818
0x180030956  mov     rcx, [rsp+2C0h+BaseAddress]; BaseAddress
0x18003095b  lea     r9, [rsp+2C0h+var_278]; ProcedureAddress
0x180030960  xor     r8d, r8d; Ordinal
0x180030963  lea     rdx, stru_180086E00; Name
0x18003096a  call    cs:__imp_LdrGetProcedureAddress
0x180030971  nop     dword ptr [rax+rax+00h]
0x180030976  mov     ebx, eax
0x180030978  test    eax, eax
0x18003097a  js      loc_180030818
0x180030980  mov     rcx, [rsp+2C0h+BaseAddress]; BaseAddress
0x180030985  lea     r9, [rsp+2C0h+var_270]; ProcedureAddress
0x18003098a  xor     r8d, r8d; Ordinal
0x18003098d  lea     rdx, stru_180086E10; Name
0x180030994  call    cs:__imp_LdrGetProcedureAddress
0x18003099b  nop     dword ptr [rax+rax+00h]
0x1800309a0  mov     ebx, eax
0x1800309a2  test    eax, eax
0x1800309a4  js      loc_180030818
0x1800309aa  mov     rcx, [rsp+2C0h+BaseAddress]; BaseAddress
0x1800309af  lea     r9, [rsp+2C0h+var_268]; ProcedureAddress
0x1800309b4  xor     r8d, r8d; Ordinal
0x1800309b7  lea     rdx, stru_180086DE0; Name
0x1800309be  call    cs:__imp_LdrGetProcedureAddress
0x1800309c5  nop     dword ptr [rax+rax+00h]
0x1800309ca  mov     ebx, eax
0x1800309cc  test    eax, eax
0x1800309ce  js      loc_180030818
0x1800309d4  mov     rcx, [rsp+2C0h+BaseAddress]; BaseAddress
0x1800309d9  lea     r9, [rsp+2C0h+var_260]; ProcedureAddress
0x1800309de  xor     r8d, r8d; Ordinal
0x1800309e1  lea     rdx, stru_180086DF0; Name
0x1800309e8  call    cs:__imp_LdrGetProcedureAddress
0x1800309ef  nop     dword ptr [rax+rax+00h]
0x1800309f4  mov     ebx, eax
0x1800309f6  test    eax, eax
0x1800309f8  js      loc_180030818
0x1800309fe  mov     rcx, [rsp+2C0h+BaseAddress]; BaseAddress
0x180030a03  lea     r9, [rsp+2C0h+var_258]; ProcedureAddress
0x180030a08  xor     r8d, r8d; Ordinal
0x180030a0b  lea     rdx, stru_180086DC0; Name
0x180030a12  call    cs:__imp_LdrGetProcedureAddress
0x180030a19  nop     dword ptr [rax+rax+00h]
0x180030a1e  mov     ebx, eax
0x180030a20  test    eax, eax
0x180030a22  js      loc_180030818
0x180030a28  mov     rcx, [rsp+2C0h+BaseAddress]; BaseAddress
0x180030a2d  lea     r9, [rsp+2C0h+var_250]; ProcedureAddress
0x180030a32  xor     r8d, r8d; Ordinal
0x180030a35  lea     rdx, stru_180086DD0; Name
0x180030a3c  call    cs:__imp_LdrGetProcedureAddress
0x180030a43  nop     dword ptr [rax+rax+00h]
0x180030a48  mov     ebx, eax
0x180030a4a  test    eax, eax
0x180030a4c  js      loc_180030818
0x180030a52  mov     rcx, [rsp+2C0h+ProcedureAddress]; Pointer
0x180030a57  call    cs:__imp_RtlEncodeSystemPointer
0x180030a5e  nop     dword ptr [rax+rax+00h]
0x180030a63  mov     rcx, rax
0x180030a66  xor     eax, eax
0x180030a68  lock cmpxchg cs:qword_1800BE050, rcx
0x180030a71  mov     rcx, [rsp+2C0h+Pointer]; Pointer
0x180030a76  call    cs:__imp_RtlEncodeSystemPointer
0x180030a7d  nop     dword ptr [rax+rax+00h]
0x180030a82  mov     rcx, rax
0x180030a85  xor     eax, eax
0x180030a87  lock cmpxchg cs:Pointer, rcx
0x180030a90  mov     rcx, [rsp+2C0h+var_278]; Pointer
0x180030a95  call    cs:__imp_RtlEncodeSystemPointer
0x180030a9c  nop     dword ptr [rax+rax+00h]
0x180030aa1  mov     rcx, rax
0x180030aa4  xor     eax, eax
0x180030aa6  lock cmpxchg cs:qword_1800BE060, rcx
0x180030aaf  mov     rcx, [rsp+2C0h+var_270]; Pointer
0x180030ab4  call    cs:__imp_RtlEncodeSystemPointer
0x180030abb  nop     dword ptr [rax+rax+00h]
0x180030ac0  mov     rcx, rax
0x180030ac3  xor     eax, eax
0x180030ac5  lock cmpxchg cs:qword_1800BE068, rcx
0x180030ace  mov     rcx, [rsp+2C0h+var_268]; Pointer
0x180030ad3  call    cs:__imp_RtlEncodeSystemPointer
0x180030ada  nop     dword ptr [rax+rax+00h]
0x180030adf  mov     rcx, rax
0x180030ae2  xor     eax, eax
0x180030ae4  lock cmpxchg cs:qword_1800BE070, rcx
0x180030aed  mov     rcx, [rsp+2C0h+var_260]; Pointer
0x180030af2  call    cs:__imp_RtlEncodeSystemPointer
0x180030af9  nop     dword ptr [rax+rax+00h]
0x180030afe  mov     rcx, rax
0x180030b01  xor     eax, eax
0x180030b03  lock cmpxchg cs:qword_1800BE078, rcx
0x180030b0c  mov     rcx, [rsp+2C0h+var_258]; Pointer
0x180030b11  call    cs:__imp_RtlEncodeSystemPointer
0x180030b18  nop     dword ptr [rax+rax+00h]
0x180030b1d  mov     rcx, rax
0x180030b20  xor     eax, eax
0x180030b22  lock cmpxchg cs:qword_1800BE080, rcx
0x180030b2b  mov     rcx, [rsp+2C0h+var_250]; Pointer
0x180030b30  call    cs:__imp_RtlEncodeSystemPointer
0x180030b37  nop     dword ptr [rax+rax+00h]
0x180030b3c  mov     rcx, rax
0x180030b3f  xor     eax, eax
0x180030b41  lock cmpxchg cs:qword_1800BE088, rcx
0x180030b4a  xor     eax, eax
0x180030b4c  lock cmpxchg cs:gApphelpGlobals, edi
0x180030b54  jmp     loc_180030822
```
