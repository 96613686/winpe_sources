# _invoke_watson

- ea: `0x180001c2c`
- end: `0x180001d11`
- name: `_invoke_watson`
- size: `229`
- prototype: `void __cdecl __noreturn(const wchar_t *Expression, const wchar_t *FunctionName, const wchar_t *FileName, unsigned int LineNo, uintptr_t Reserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001c20`

## callees

- `0x180001c2c`
- `0x180006030`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x180001c87`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlLookupFunctionEntry` at `0x180001c87`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x180001cc6`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlVirtualUnwind` at `0x180001cc6`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180001c72`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180001c72`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ceb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ceb`

## pseudocode

```c
void __cdecl __noreturn invoke_watson(
        const wchar_t *Expression,
        const wchar_t *FunctionName,
        const wchar_t *FileName,
        unsigned int LineNo,
        uintptr_t Reserved)
{
  ULONG64 Rip; // rbx
  struct _RUNTIME_FUNCTION *v6; // rax
  unsigned __int64 ImageBase; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+48h] [rbp-B8h] BYREF
  PVOID HandlerData; // [rsp+50h] [rbp-B0h] BYREF
  CONTEXT ContextRecord; // [rsp+60h] [rbp-A0h] BYREF
  DWORD64 retaddr; // [rsp+548h] [rbp+448h] BYREF

  EstablisherFrame = 0;
  HandlerData = 0;
  ImageBase = 0;
  RtlCaptureContext(&ContextRecord);
  Rip = ContextRecord.Rip;
  v6 = RtlLookupFunctionEntry(ContextRecord.Rip, &ImageBase, 0);
  if ( v6 )
  {
    RtlVirtualUnwind(0, ImageBase, Rip, v6, &ContextRecord, &HandlerData, &EstablisherFrame, 0);
  }
  else
  {
    ContextRecord.Rip = retaddr;
    ContextRecord.Rsp = (DWORD64)&retaddr;
  }
  OutputDebugStringA("Invalid parameter passed to C runtime function.\n");
}

```

## disassembly

```asm
0x180001c2c  mov     [rsp-8+arg_0], rbx
0x180001c31  push    rbp
0x180001c32  lea     rbp, [rsp-440h]
0x180001c3a  sub     rsp, 540h
0x180001c41  mov     rax, cs:__security_cookie
0x180001c48  xor     rax, rsp
0x180001c4b  mov     [rbp+440h+var_10], rax
0x180001c52  lea     rcx, [rsp+540h+ContextRecord]; ContextRecord
0x180001c57  mov     [rsp+540h+var_4F8], 0
0x180001c60  mov     [rsp+540h+var_4F0], 0
0x180001c69  mov     [rsp+540h+ImageBase], 0
0x180001c72  call    cs:__imp_RtlCaptureContext
0x180001c78  mov     rbx, [rbp+440h+ContextRecord.Rip]
0x180001c7c  lea     rdx, [rsp+540h+ImageBase]; ImageBase
0x180001c81  mov     rcx, rbx; ControlPc
0x180001c84  xor     r8d, r8d; HistoryTable
0x180001c87  call    cs:__imp_RtlLookupFunctionEntry
0x180001c8d  test    rax, rax
0x180001c90  jz      short loc_180001CCE
0x180001c92  mov     rdx, [rsp+540h+ImageBase]; ImageBase
0x180001c97  lea     rcx, [rsp+540h+var_4F8]
0x180001c9c  mov     [rsp+540h+ContextPointers], 0; ContextPointers
0x180001ca5  mov     r9, rax; FunctionEntry
0x180001ca8  mov     [rsp+540h+EstablisherFrame], rcx; EstablisherFrame
0x180001cad  mov     r8, rbx; ControlPc
0x180001cb0  lea     rcx, [rsp+540h+var_4F0]
0x180001cb5  mov     [rsp+540h+HandlerData], rcx; HandlerData
0x180001cba  lea     rcx, [rsp+540h+ContextRecord]
0x180001cbf  mov     [rsp+540h+var_520], rcx; ContextRecord
0x180001cc4  xor     ecx, ecx; HandlerType
0x180001cc6  call    cs:__imp_RtlVirtualUnwind
0x180001ccc  jmp     short loc_180001CE4
0x180001cce  mov     rax, [rbp+448h]
0x180001cd5  mov     [rbp+440h+ContextRecord.Rip], rax
0x180001cd9  lea     rax, [rbp+448h]
0x180001ce0  mov     [rbp+440h+ContextRecord.Rsp], rax
0x180001ce4  lea     rcx, OutputString; "Invalid parameter passed to C runtime f"...
0x180001ceb  call    cs:__imp_OutputDebugStringA
0x180001cf1  mov     rcx, [rbp+440h+var_10]
0x180001cf8  xor     rcx, rsp; StackCookie
0x180001cfb  call    __security_check_cookie
0x180001d00  mov     rbx, [rsp+540h+arg_0]
0x180001d08  add     rsp, 540h
0x180001d0f  pop     rbp
0x180001d10  retn
```
