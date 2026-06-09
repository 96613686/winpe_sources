# CServiceCallback::TelemetryAssertTriggered(unsigned __int64,unsigned __int64,uint,uint)

- ea: `0x18000a540`
- end: `0x18000a606`
- name: `?TelemetryAssertTriggered@CServiceCallback@@EEBAJ_K0II@Z`
- size: `198`
- prototype: `__int64 __fastcall(CServiceCallback *this, __int64, unsigned __int64, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180003290`
- `0x18000a540`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000a55c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000a55c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a590`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a590`

## string_xrefs

- `0x18000a56e`: `onecore\enduser\deliveryoptimization\servicecallback\servicecallback.cpp`
- `0x18000a54c`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall CServiceCallback::TelemetryAssertTriggered(
        CServiceCallback *this,
        __int64 a2,
        unsigned __int64 a3,
        unsigned int a4,
        unsigned int a5)
{
  HMODULE ModuleHandleA; // rax
  __int64 v9; // rdx
  FARPROC ProcAddress; // rdx
  _QWORD v12[2]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v13; // [rsp+30h] [rbp-38h]
  __int128 v14; // [rsp+40h] [rbp-28h]
  __int64 v15; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  ModuleHandleA = GetModuleHandleA("ntdll.dll");
  if ( !ModuleHandleA )
  {
    v9 = 82;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (int)"onecore\\enduser\\deliveryoptimization\\servicecallback\\servicecallback.cpp",
      (const char *)0x80004001LL);
    return 2147500033LL;
  }
  ProcAddress = GetProcAddress(ModuleHandleA, "MicrosoftTelemetryAssertTriggeredUM");
  if ( !ProcAddress )
  {
    v9 = 85;
    goto LABEL_3;
  }
  v15 = 1;
  v12[0] = 11;
  v12[1] = a2;
  v13 = a3;
  v14 = 0;
  if ( a4 != -1 || (BYTE8(v13) = 0, a5 != -1) )
    BYTE8(v13) = 1;
  *(_QWORD *)&v14 = 0;
  *((_QWORD *)&v14 + 1) = __PAIR64__(a5, a4);
  ((void (__fastcall *)(_QWORD *))ProcAddress)(v12);
  return 0;
}

```

## disassembly

```asm
0x18000a540  push    rbp
0x18000a542  push    rbx
0x18000a543  push    rsi
0x18000a544  push    rdi
0x18000a545  mov     rbp, rsp
0x18000a548  sub     rsp, 68h
0x18000a54c  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000a553  mov     ebx, r9d
0x18000a556  mov     rdi, r8
0x18000a559  mov     rsi, rdx
0x18000a55c  call    cs:__imp_GetModuleHandleA
0x18000a562  test    rax, rax
0x18000a565  jnz     short loc_18000A586
0x18000a567  lea     edx, [rax+52h]; void *
0x18000a56a  mov     rcx, [rbp+20h]; this
0x18000a56e  lea     r8, aOnecoreEnduser; "onecore\\enduser\\deliveryoptimization"...
0x18000a575  mov     ebx, 80004001h
0x18000a57a  mov     r9d, ebx; char *
0x18000a57d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a582  mov     eax, ebx
0x18000a584  jmp     short loc_18000A5FD
0x18000a586  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18000a58d  mov     rcx, rax; hModule
0x18000a590  call    cs:__imp_GetProcAddress
0x18000a596  mov     rdx, rax
0x18000a599  test    rax, rax
0x18000a59c  jnz     short loc_18000A5A3
0x18000a59e  lea     edx, [rax+55h]
0x18000a5a1  jmp     short loc_18000A56A
0x18000a5a3  xorps   xmm0, xmm0
0x18000a5a6  xor     eax, eax
0x18000a5a8  movups  [rbp+var_48], xmm0
0x18000a5ac  mov     [rbp+var_18], rax
0x18000a5b0  or      ecx, 0FFFFFFFFh
0x18000a5b3  mov     eax, [rbp+arg_20]
0x18000a5b6  mov     dword ptr [rbp+var_48], 0Bh
0x18000a5bd  mov     qword ptr [rbp+var_48+8], rsi
0x18000a5c1  mov     byte ptr [rbp+var_18], 1
0x18000a5c5  movups  [rbp+var_38], xmm0
0x18000a5c9  mov     qword ptr [rbp+var_38], rdi
0x18000a5cd  movups  [rbp+var_28], xmm0
0x18000a5d1  cmp     ebx, ecx
0x18000a5d3  jnz     short loc_18000A5DD
0x18000a5d5  mov     byte ptr [rbp+var_38+8], 0
0x18000a5d9  cmp     eax, ecx
0x18000a5db  jz      short loc_18000A5E1
0x18000a5dd  mov     byte ptr [rbp+var_38+8], 1
0x18000a5e1  mov     dword ptr [rbp+var_28+0Ch], eax
0x18000a5e4  lea     rcx, [rbp+var_48]
0x18000a5e8  mov     rax, rdx
0x18000a5eb  mov     qword ptr [rbp+var_28], 0
0x18000a5f3  mov     dword ptr [rbp+var_28+8], ebx
0x18000a5f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5fb  xor     eax, eax
0x18000a5fd  add     rsp, 68h
0x18000a601  pop     rdi
0x18000a602  pop     rsi
0x18000a603  pop     rbx
0x18000a604  pop     rbp
0x18000a605  retn
```
