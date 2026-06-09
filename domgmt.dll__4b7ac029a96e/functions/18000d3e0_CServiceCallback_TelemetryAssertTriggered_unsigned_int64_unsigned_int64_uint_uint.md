# CServiceCallback::TelemetryAssertTriggered(unsigned __int64,unsigned __int64,uint,uint)

- ea: `0x18000d3e0`
- end: `0x18000d4a6`
- name: `?TelemetryAssertTriggered@CServiceCallback@@EEBAJ_K0II@Z`
- size: `198`
- prototype: `__int64 __fastcall(CServiceCallback *this, __int64, unsigned __int64, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180005964`
- `0x18000d3e0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d430`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d430`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000d3fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18000d3fc`

## string_xrefs

- `0x18000d3ec`: `ntdll.dll`
- `0x18000d40e`: `onecore\enduser\deliveryoptimization\servicecallback\servicecallback.cpp`

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
0x18000d3e0  push    rbp
0x18000d3e2  push    rbx
0x18000d3e3  push    rsi
0x18000d3e4  push    rdi
0x18000d3e5  mov     rbp, rsp
0x18000d3e8  sub     rsp, 68h
0x18000d3ec  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000d3f3  mov     ebx, r9d
0x18000d3f6  mov     rdi, r8
0x18000d3f9  mov     rsi, rdx
0x18000d3fc  call    cs:__imp_GetModuleHandleA
0x18000d402  test    rax, rax
0x18000d405  jnz     short loc_18000D426
0x18000d407  lea     edx, [rax+52h]; void *
0x18000d40a  mov     rcx, [rbp+20h]; this
0x18000d40e  lea     r8, aOnecoreEnduser; "onecore\\enduser\\deliveryoptimization"...
0x18000d415  mov     ebx, 80004001h
0x18000d41a  mov     r9d, ebx; char *
0x18000d41d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d422  mov     eax, ebx
0x18000d424  jmp     short loc_18000D49D
0x18000d426  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18000d42d  mov     rcx, rax; hModule
0x18000d430  call    cs:__imp_GetProcAddress
0x18000d436  mov     rdx, rax
0x18000d439  test    rax, rax
0x18000d43c  jnz     short loc_18000D443
0x18000d43e  lea     edx, [rax+55h]
0x18000d441  jmp     short loc_18000D40A
0x18000d443  xorps   xmm0, xmm0
0x18000d446  xor     eax, eax
0x18000d448  movups  [rbp+var_48], xmm0
0x18000d44c  mov     [rbp+var_18], rax
0x18000d450  or      ecx, 0FFFFFFFFh
0x18000d453  mov     eax, [rbp+arg_20]
0x18000d456  mov     dword ptr [rbp+var_48], 0Bh
0x18000d45d  mov     qword ptr [rbp+var_48+8], rsi
0x18000d461  mov     byte ptr [rbp+var_18], 1
0x18000d465  movups  [rbp+var_38], xmm0
0x18000d469  mov     qword ptr [rbp+var_38], rdi
0x18000d46d  movups  [rbp+var_28], xmm0
0x18000d471  cmp     ebx, ecx
0x18000d473  jnz     short loc_18000D47D
0x18000d475  mov     byte ptr [rbp+var_38+8], 0
0x18000d479  cmp     eax, ecx
0x18000d47b  jz      short loc_18000D481
0x18000d47d  mov     byte ptr [rbp+var_38+8], 1
0x18000d481  mov     dword ptr [rbp+var_28+0Ch], eax
0x18000d484  lea     rcx, [rbp+var_48]
0x18000d488  mov     rax, rdx
0x18000d48b  mov     qword ptr [rbp+var_28], 0
0x18000d493  mov     dword ptr [rbp+var_28+8], ebx
0x18000d496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d49b  xor     eax, eax
0x18000d49d  add     rsp, 68h
0x18000d4a1  pop     rdi
0x18000d4a2  pop     rsi
0x18000d4a3  pop     rbx
0x18000d4a4  pop     rbp
0x18000d4a5  retn
```
