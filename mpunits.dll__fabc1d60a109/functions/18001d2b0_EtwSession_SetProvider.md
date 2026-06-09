# EtwSession_SetProvider

- ea: `0x18001d2b0`
- end: `0x18001d3cb`
- name: `EtwSession_SetProvider`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, loader_planting`

## callers

- `0x180019a20`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x18000ab88`
- `0x18000ac44`
- `0x18001d2b0`
- `0x180044880`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001d34b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001d34b`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x18001d30f`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x18001d30f`

## string_xrefs

- `0x18001d340`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall EtwSession_SetProvider(__int64 a1, __int64 a2, unsigned int a3)
{
  ULONG v3; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  ULONG v6; // ebx
  HMODULE ModuleHandleA; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-20h] BYREF

  LOBYTE(a3) = ~*(_BYTE *)(a2 + 49);
  v3 = EnableTraceEx2(
         *(_QWORD *)(a1 + 40),
         (LPCGUID)(a2 + 16),
         (a3 >> 3) & 1,
         *(_BYTE *)(a2 + 48),
         *(_QWORD *)(a2 + 56),
         0,
         0,
         0);
  *(_DWORD *)&EventDescriptor.Level = 4;
  EventDescriptor.Keyword = 1;
  v6 = v3;
  if ( v3 )
  {
    *(_DWORD *)&EventDescriptor.Id = 7;
    Etw_Trace1_int(&EventDescriptor, v3);
    EventDescriptor = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    *(_QWORD *)&EventDescriptor.Id = Intlstr_FormatString_FormatMessage(ModuleHandleA, 2039, v6);
    LOBYTE(EventDescriptor.Keyword) = 1;
    MI_ReportErrorDetails_ForCustomError(7, (int)L"ETW Normalizer", 0, 0);
    return 1;
  }
  else
  {
    *(_DWORD *)&EventDescriptor.Id = 10005;
    Etw_Trace0(&EventDescriptor, v4, v5);
    return 0;
  }
}

```

## disassembly

```asm
0x18001d2b0  mov     r11, rsp
0x18001d2b3  mov     [r11+18h], rbx
0x18001d2b7  mov     [r11+20h], rdi
0x18001d2bb  push    rbp
0x18001d2bc  mov     rbp, rsp
0x18001d2bf  sub     rsp, 60h
0x18001d2c3  mov     rax, cs:__security_cookie
0x18001d2ca  xor     rax, rsp
0x18001d2cd  mov     [rbp+var_10], rax
0x18001d2d1  mov     r8b, [rdx+31h]
0x18001d2d5  mov     r9, rdx
0x18001d2d8  mov     rcx, [rcx+28h]; TraceHandle
0x18001d2dc  not     r8b
0x18001d2df  mov     qword ptr [r11-30h], 0
0x18001d2e7  add     rdx, 10h; ProviderId
0x18001d2eb  shr     r8d, 3
0x18001d2ef  mov     rax, [r9+38h]
0x18001d2f3  and     r8d, 1; ControlCode
0x18001d2f7  mov     r9b, [r9+30h]; Level
0x18001d2fb  mov     [rsp+60h+Timeout], 0; Timeout
0x18001d303  mov     qword ptr [r11-40h], 0
0x18001d30b  mov     [r11-48h], rax
0x18001d30f  call    cs:__imp_EnableTraceEx2
0x18001d315  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x18001d31c  lea     rcx, [rbp+EventDescriptor]; EventDescriptor
0x18001d320  mov     [rbp+EventDescriptor.Keyword], 1
0x18001d328  mov     ebx, eax
0x18001d32a  test    eax, eax
0x18001d32c  jz      short loc_18001D39F
0x18001d32e  mov     edi, 7
0x18001d333  mov     edx, eax
0x18001d335  mov     dword ptr [rbp+EventDescriptor.Id], edi
0x18001d338  call    Etw_Trace1_int
0x18001d33d  xorps   xmm0, xmm0
0x18001d340  lea     rcx, ModuleName; "mpunits.dll"
0x18001d347  movups  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x18001d34b  call    cs:__imp_GetModuleHandleA
0x18001d351  mov     r8d, ebx
0x18001d354  mov     edx, 7F7h
0x18001d359  mov     rcx, rax
0x18001d35c  call    _Intlstr_FormatString_FormatMessage
0x18001d361  mov     qword ptr [rbp+EventDescriptor.Id], rax
0x18001d365  lea     r9, [rbp+EventDescriptor]
0x18001d369  mov     byte ptr [rbp+EventDescriptor.Keyword], 1
0x18001d36d  lea     r8d, [rdi-2]
0x18001d371  movaps  xmm0, xmmword ptr [rbp+EventDescriptor.Id]
0x18001d375  lea     rdx, aEtwNormalizer; "ETW Normalizer"
0x18001d37c  mov     [rsp+60h+var_38], 0; __int64
0x18001d385  mov     ecx, edi; int
0x18001d387  movdqa  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x18001d38c  mov     [rsp+60h+var_40], 0; __int64
0x18001d395  call    MI_ReportErrorDetails_ForCustomError
0x18001d39a  lea     eax, [rdi-6]
0x18001d39d  jmp     short loc_18001D3AD
0x18001d39f  mov     dword ptr [rbp+EventDescriptor.Id], 2715h
0x18001d3a6  call    Etw_Trace0
0x18001d3ab  xor     eax, eax
0x18001d3ad  mov     rcx, [rbp+var_10]
0x18001d3b1  xor     rcx, rsp; StackCookie
0x18001d3b4  call    __security_check_cookie
0x18001d3b9  lea     r11, [rsp+60h+var_s0]
0x18001d3be  mov     rbx, [r11+20h]
0x18001d3c2  mov     rdi, [r11+28h]
0x18001d3c6  mov     rsp, r11
0x18001d3c9  pop     rbp
0x18001d3ca  retn
```
