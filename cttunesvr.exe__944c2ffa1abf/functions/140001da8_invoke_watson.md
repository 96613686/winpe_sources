# _invoke_watson

- ea: `0x140001da8`
- end: `0x140001e8d`
- name: `_invoke_watson`
- size: `229`
- prototype: `void __cdecl __noreturn(const wchar_t *Expression, const wchar_t *FunctionName, const wchar_t *FileName, unsigned int LineNo, uintptr_t Reserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001d9c`

## callees

- `0x140001da8`
- `0x1400065f0`

## import_xrefs

- `KERNEL32!OutputDebugStringA` at `0x140001e67`
- `KERNEL32!OutputDebugStringA` at `0x140001e67`
- `KERNEL32!RtlVirtualUnwind` at `0x140001e42`
- `KERNEL32!RtlVirtualUnwind` at `0x140001e42`
- `KERNEL32!RtlLookupFunctionEntry` at `0x140001e03`
- `KERNEL32!RtlLookupFunctionEntry` at `0x140001e03`
- `KERNEL32!RtlCaptureContext` at `0x140001dee`
- `KERNEL32!RtlCaptureContext` at `0x140001dee`

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
  struct _IMAGE_RUNTIME_FUNCTION_ENTRY *v6; // rax
  unsigned __int64 ImageBase; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 EstablisherFrame; // [rsp+48h] [rbp-B8h] BYREF
  PVOID HandlerData; // [rsp+50h] [rbp-B0h] BYREF
  struct _CONTEXT ContextRecord; // [rsp+60h] [rbp-A0h] BYREF
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
0x140001da8  mov     [rsp-8+arg_0], rbx
0x140001dad  push    rbp
0x140001dae  lea     rbp, [rsp-440h]
0x140001db6  sub     rsp, 540h
0x140001dbd  mov     rax, cs:__security_cookie
0x140001dc4  xor     rax, rsp
0x140001dc7  mov     [rbp+440h+var_10], rax
0x140001dce  lea     rcx, [rsp+540h+ContextRecord]; ContextRecord
0x140001dd3  mov     [rsp+540h+var_4F8], 0
0x140001ddc  mov     [rsp+540h+var_4F0], 0
0x140001de5  mov     [rsp+540h+ImageBase], 0
0x140001dee  call    cs:__imp_RtlCaptureContext
0x140001df4  mov     rbx, [rbp+440h+ContextRecord.Rip]
0x140001df8  lea     rdx, [rsp+540h+ImageBase]; ImageBase
0x140001dfd  mov     rcx, rbx; ControlPc
0x140001e00  xor     r8d, r8d; HistoryTable
0x140001e03  call    cs:__imp_RtlLookupFunctionEntry
0x140001e09  test    rax, rax
0x140001e0c  jz      short loc_140001E4A
0x140001e0e  mov     rdx, [rsp+540h+ImageBase]; ImageBase
0x140001e13  lea     rcx, [rsp+540h+var_4F8]
0x140001e18  mov     [rsp+540h+ContextPointers], 0; ContextPointers
0x140001e21  mov     r9, rax; FunctionEntry
0x140001e24  mov     [rsp+540h+EstablisherFrame], rcx; EstablisherFrame
0x140001e29  mov     r8, rbx; ControlPc
0x140001e2c  lea     rcx, [rsp+540h+var_4F0]
0x140001e31  mov     [rsp+540h+HandlerData], rcx; HandlerData
0x140001e36  lea     rcx, [rsp+540h+ContextRecord]
0x140001e3b  mov     [rsp+540h+var_520], rcx; ContextRecord
0x140001e40  xor     ecx, ecx; HandlerType
0x140001e42  call    cs:__imp_RtlVirtualUnwind
0x140001e48  jmp     short loc_140001E60
0x140001e4a  mov     rax, [rbp+448h]
0x140001e51  mov     [rbp+440h+ContextRecord.Rip], rax
0x140001e55  lea     rax, [rbp+448h]
0x140001e5c  mov     [rbp+440h+ContextRecord.Rsp], rax
0x140001e60  lea     rcx, OutputString; "Invalid parameter passed to C runtime f"...
0x140001e67  call    cs:__imp_OutputDebugStringA
0x140001e6d  mov     rcx, [rbp+440h+var_10]
0x140001e74  xor     rcx, rsp; StackCookie
0x140001e77  call    __security_check_cookie
0x140001e7c  mov     rbx, [rsp+540h+arg_0]
0x140001e84  add     rsp, 540h
0x140001e8b  pop     rbp
0x140001e8c  retn
```
