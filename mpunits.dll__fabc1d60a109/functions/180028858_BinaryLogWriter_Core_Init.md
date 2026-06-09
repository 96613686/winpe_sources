# BinaryLogWriter_Core_Init

- ea: `0x180028858`
- end: `0x180028940`
- name: `BinaryLogWriter_Core_Init`
- size: `232`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180026010`
- `0x18002a5d0`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x18000ac44`
- `0x180028858`
- `0x180044842`
- `0x180044880`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800288d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800288d6`
- `mibincodec!MI_Application_NewSerializer_Binary` at `0x180028898`
- `mibincodec!MI_Application_NewSerializer_Binary` at `0x180028898`

## string_xrefs

- `0x1800288cb`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall BinaryLogWriter_Core_Init(_DWORD *a1)
{
  int v2; // eax
  HMODULE ModuleHandleA; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-20h] BYREF

  memset_0(a1 + 1, 0, 0x54u);
  *a1 = -1;
  v2 = MI_Application_NewSerializer_Binary(0, 4, 0, a1 + 8);
  if ( !v2 )
    return 0;
  *(_DWORD *)&EventDescriptor.Id = 10101;
  EventDescriptor.Keyword = 1;
  *(_DWORD *)&EventDescriptor.Level = 4;
  Etw_Trace1_int(&EventDescriptor, v2);
  EventDescriptor = 0;
  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  *(_QWORD *)&EventDescriptor.Id = Intlstr_GetString_LoadString(ModuleHandleA, 2020);
  LOBYTE(EventDescriptor.Keyword) = 0;
  MI_ReportErrorDetails_ForCustomError(31, (int)L"BinaryLogger", 0, 0);
  return 1;
}

```

## disassembly

```asm
0x180028858  mov     [rsp-8+arg_8], rbx
0x18002885d  push    rbp
0x18002885e  mov     rbp, rsp
0x180028861  sub     rsp, 50h
0x180028865  mov     rax, cs:__security_cookie
0x18002886c  xor     rax, rsp
0x18002886f  mov     [rbp+var_10], rax
0x180028873  xor     edx, edx; Val
0x180028875  mov     rbx, rcx
0x180028878  add     rcx, 4; void *
0x18002887c  lea     r8d, [rdx+54h]; Size
0x180028880  call    memset_0
0x180028885  xor     r8d, r8d
0x180028888  mov     dword ptr [rbx], 0FFFFFFFFh
0x18002888e  lea     r9, [rbx+20h]
0x180028892  xor     ecx, ecx
0x180028894  lea     edx, [r8+4]
0x180028898  call    cs:__imp_MI_Application_NewSerializer_Binary
0x18002889e  test    eax, eax
0x1800288a0  jz      loc_180028927
0x1800288a6  mov     ebx, 1
0x1800288ab  mov     dword ptr [rbp+EventDescriptor.Id], 2775h
0x1800288b2  mov     edx, eax
0x1800288b4  mov     [rbp+EventDescriptor.Keyword], rbx
0x1800288b8  lea     rcx, [rbp+EventDescriptor]; EventDescriptor
0x1800288bc  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x1800288c3  call    Etw_Trace1_int
0x1800288c8  xorps   xmm0, xmm0
0x1800288cb  lea     rcx, ModuleName; "mpunits.dll"
0x1800288d2  movups  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x1800288d6  call    cs:__imp_GetModuleHandleA
0x1800288dc  mov     rcx, rax
0x1800288df  mov     edx, 7E4h
0x1800288e4  call    _Intlstr_GetString_LoadString
0x1800288e9  mov     qword ptr [rbp+EventDescriptor.Id], rax
0x1800288ed  lea     r9, [rbp+EventDescriptor]
0x1800288f1  mov     byte ptr [rbp+EventDescriptor.Keyword], 0
0x1800288f5  lea     r8d, [rbx+14h]
0x1800288f9  movaps  xmm0, xmmword ptr [rbp+EventDescriptor.Id]
0x1800288fd  lea     rdx, aBinarylogger; "BinaryLogger"
0x180028904  mov     [rsp+50h+var_28], 0; __int64
0x18002890d  lea     ecx, [rbx+1Eh]; int
0x180028910  movdqa  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x180028915  mov     [rsp+50h+var_30], 0; __int64
0x18002891e  call    MI_ReportErrorDetails_ForCustomError
0x180028923  mov     eax, ebx
0x180028925  jmp     short loc_180028929
0x180028927  xor     eax, eax
0x180028929  mov     rcx, [rbp+var_10]
0x18002892d  xor     rcx, rsp; StackCookie
0x180028930  call    __security_check_cookie
0x180028935  mov     rbx, [rsp+50h+arg_8]
0x18002893a  add     rsp, 50h
0x18002893e  pop     rbp
0x18002893f  retn
```
