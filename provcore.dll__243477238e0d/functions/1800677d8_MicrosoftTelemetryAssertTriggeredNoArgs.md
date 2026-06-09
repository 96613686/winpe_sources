# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x1800677d8`
- end: `0x18006787a`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `65`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d178`
- `0x18000d1d4`
- `0x18000d2a8`
- `0x180014148`
- `0x180014488`
- `0x1800149bc`
- `0x1800156fc`
- `0x180015aa4`
- `0x180017d2c`
- `0x180019b70`
- `0x180020d20`
- `0x180020e70`
- `0x180020f9c`
- `0x18002108c`
- `0x180021320`
- `0x180023088`
- `0x1800284cc`
- `0x18002cbd0`
- `0x18002de40`
- `0x18002de64`
- `0x18002de9c`
- `0x18002dec0`
- `0x18002e26c`
- `0x18002e4c8`
- `0x180034b90`
- `0x180037890`
- `0x180038794`
- `0x180038cac`
- `0x180039710`
- `0x18003c304`
- `0x18003c4d0`
- `0x18003c704`
- `0x18003d1c4`
- `0x18003db44`
- `0x18003deac`
- `0x18003e8fc`
- `0x18004d9b8`
- `0x18004dab0`
- `0x18004db9c`
- `0x18004dc88`
- `0x18004dd7c`
- `0x18004de70`
- `0x18004df64`
- `0x180050698`
- `0x180053f30`
- `0x180054530`
- `0x1800547b0`
- `0x180056d20`
- `0x1800577dc`
- `0x180068d5c`

## callees

- `0x1800677d8`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800677f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800677f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180067813`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180067813`

## string_xrefs

- `0x1800677ed`: `ntdll.dll`

## pseudocode

```c
int MicrosoftTelemetryAssertTriggeredNoArgs()
{
  FARPROC ProcAddress; // rax
  _MicrosoftTelemetryAssertArgs args; // [rsp+20h] [rbp-40h] BYREF
  unsigned __int64 retaddr; // [rsp+68h] [rbp+8h]
  HINSTANCE__ *ntDLL; // [rsp+70h] [rbp+10h] BYREF

  ntDLL = 0;
  LODWORD(ProcAddress) = GetModuleHandleExA(2u, "ntdll.dll", &ntDLL);
  if ( (_DWORD)ProcAddress )
  {
    if ( ntDLL )
    {
      ProcAddress = GetProcAddress(ntDLL, "MicrosoftTelemetryAssertTriggeredUM");
      if ( ProcAddress )
      {
        *(_DWORD *)&args.DumpNeeded = 1;
        *(&args.Version + 1) = 0;
        args.ImageBase = (unsigned __int64)&_ImageBase;
        *(_QWORD *)&args.HasArgs = 0;
        args.ReturnAddress = retaddr;
        args.Dword1 = -1;
        args.Dword2 = -1;
        args.Version = 11;
        args.OriginatingBinary = 0;
        LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_MicrosoftTelemetryAssertArgs *))ProcAddress)(&args);
      }
    }
  }
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x1800677d8  push    rbp
0x1800677da  mov     rbp, rsp
0x1800677dd  sub     rsp, 60h
0x1800677e1  lea     r8, [rbp+ntDLL]; phModule
0x1800677e5  mov     [rbp+ntDLL], 0
0x1800677ed  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x1800677f4  mov     ecx, 2; dwFlags
0x1800677f9  call    cs:__imp_GetModuleHandleExA
0x1800677ff  test    eax, eax
0x180067801  jz      short loc_180067874
0x180067803  mov     rcx, [rbp+ntDLL]; hModule
0x180067807  test    rcx, rcx
0x18006780a  jz      short loc_180067874
0x18006780c  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180067813  call    cs:__imp_GetProcAddress
0x180067819  mov     rdx, rax
0x18006781c  test    rax, rax
0x18006781f  jz      short loc_180067874
0x180067821  xor     eax, eax
0x180067823  lea     rcx, [rbp+args]
0x180067827  mov     dword ptr [rbp+args.DumpNeeded], eax
0x18006782a  xorps   xmm0, xmm0
0x18006782d  movups  xmmword ptr [rbp+args.OriginatingBinary], xmm0
0x180067831  lea     rax, __ImageBase
0x180067838  movups  xmmword ptr [rbp+args.Version], xmm0
0x18006783c  mov     [rbp+args.ImageBase], rax
0x180067840  mov     rax, [rbp+8]
0x180067844  movups  xmmword ptr [rbp+args.ReturnAddress], xmm0
0x180067848  mov     [rbp+args.ReturnAddress], rax
0x18006784c  or      eax, 0FFFFFFFFh
0x18006784f  mov     [rbp+args.Dword1], eax
0x180067852  mov     [rbp+args.Dword2], eax
0x180067855  mov     rax, rdx
0x180067858  mov     [rbp+args.Version], 0Bh
0x18006785f  mov     [rbp+args.DumpNeeded], 1
0x180067863  mov     [rbp+args.HasArgs], 0
0x180067867  mov     [rbp+args.OriginatingBinary], 0
0x18006786f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067874  add     rsp, 60h
0x180067878  pop     rbp
0x180067879  retn
```
