# IsNullPrinterDriver(void *,ushort const *,int *)

- ea: `0x180019c1c`
- end: `0x180019dd3`
- name: `?IsNullPrinterDriver@@YAJPEAXPEBGPEAH@Z`
- size: `439`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001e4f0`
- `0x1800217e0`

## callees

- `0x18000d57c`
- `0x18000d624`
- `0x180018d18`
- `0x180019c1c`
- `0x18001f094`
- `0x180034f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180019cd7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180019cd7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019cf1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019cf1`
- `SETUPAPI!SetupFindFirstLineW` at `0x180019c76`
- `SETUPAPI!SetupFindFirstLineW` at `0x180019c76`

## string_xrefs

- `0x180019d69`: `Invalid Argument: hInf=%p, pcszInstallSectionName=%ws, pbIsNullDriver=%p`
- `0x180019d16`: `The driver installed from %ws is a null driver.`

## pseudocode

```c
__int64 __fastcall IsNullPrinterDriver(char *a1, const unsigned __int16 *a2, int *a3)
{
  signed int v5; // ebx
  int LastErrorAsHResult; // eax
  const unsigned __int16 *v7; // r9
  struct _INFCONTEXT Context; // [rsp+58h] [rbp-18h] BYREF
  __int64 v10; // [rsp+90h] [rbp+20h] BYREF
  int v11; // [rsp+A8h] [rbp+38h]

  if ( (unsigned __int64)(a1 - 1) > 0xFFFFFFFFFFFFFFFDuLL || !a2 || !a3 )
  {
    v5 = -2147024809;
    ClassInstallerTelemetry::WriteDbgTraceError(
      "IsNullPrinterDriver",
      L"Invalid Argument: hInf=%p, pcszInstallSectionName=%ws, pbIsNullDriver=%p",
      a1,
      a2,
      a3);
    SplLogPrinterSetupEvent(
      &SETUP_PARSEINF_FAILED,
      L"IsNullPrinterDriver",
      L"Invalid argument",
      0,
      0,
      0,
      0,
      0,
      0x57u,
      0x80070057);
    return (unsigned int)v5;
  }
  *a3 = 0;
  memset(&Context, 0, sizeof(Context));
  if ( SetupFindFirstLineW(a1, a2, L"NullPrinterDriver", &Context) )
  {
    v5 = 0;
  }
  else
  {
    LastErrorAsHResult = GetLastErrorAsHResult();
    v5 = LastErrorAsHResult;
    if ( LastErrorAsHResult < 0 )
    {
      if ( (_WORD)LastErrorAsHResult != 258 )
        return (unsigned int)v5;
      v5 = 0;
      goto LABEL_15;
    }
  }
  v11 = 0;
  LODWORD(v10) = 0;
  InfGetString(&Context, 1u, (__int64)&v10);
  if ( !(_DWORD)v10 || (v5 = GetLastErrorAsHResult(), v5 >= 0) )
  {
    if ( !(unsigned int)_o__wcsicmp(0, L"TRUE") )
      *a3 = 1;
  }
  if ( v5 >= 0 )
  {
LABEL_15:
    if ( *a3 )
      ClassInstallerTelemetry::WriteDbgTraceInfo(
        "IsNullPrinterDriver",
        L"The driver installed from %ws is a null driver.",
        a2);
    v7 = L"Yes (Null Driver)";
    if ( !*a3 )
      v7 = L"Not a null driver";
    SplLogPrinterSetupEvent(
      &SETUP_PARSEINF_SUCCEEDED,
      L"IsNullPrinterDriver",
      L"Null Driver flag in additional info",
      v7,
      0,
      0,
      0,
      0,
      0,
      v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180019c1c  mov     [rsp-18h+arg_8], rbx
0x180019c21  mov     [rsp-18h+arg_10], rdi
0x180019c26  push    rbp
0x180019c27  push    r14
0x180019c29  push    r15
0x180019c2b  mov     rbp, rsp
0x180019c2e  sub     rsp, 70h
0x180019c32  lea     rax, [rcx-1]
0x180019c36  xor     r15d, r15d
0x180019c39  mov     rdi, r8
0x180019c3c  mov     r14, rdx
0x180019c3f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019c43  ja      loc_180019D57
0x180019c49  test    rdx, rdx
0x180019c4c  jz      loc_180019D57
0x180019c52  test    r8, r8
0x180019c55  jz      loc_180019D57
0x180019c5b  mov     [r8], r15d
0x180019c5e  lea     r9, [rbp+Context]; Context
0x180019c62  xorps   xmm0, xmm0
0x180019c65  lea     r8, aNullprinterdri; "NullPrinterDriver"
0x180019c6c  xor     eax, eax
0x180019c6e  movups  xmmword ptr [rbp+Context.Inf], xmm0
0x180019c72  mov     qword ptr [rbp+Context.Section], rax
0x180019c76  call    cs:__imp_SetupFindFirstLineW
0x180019c7c  test    eax, eax
0x180019c7e  jz      short loc_180019C85
0x180019c80  mov     ebx, r15d
0x180019c83  jmp     short loc_180019C90
0x180019c85  call    GetLastErrorAsHResult
0x180019c8a  mov     ebx, eax
0x180019c8c  test    eax, eax
0x180019c8e  js      short loc_180019D01
0x180019c90  lea     rax, [rbp+arg_0]
0x180019c94  mov     [rbp+hMem], r15
0x180019c98  lea     r9, [rbp+arg_18]
0x180019c9c  mov     [rsp+70h+var_50], rax; __int64
0x180019ca1  lea     r8, [rbp+hMem]
0x180019ca5  mov     [rbp+arg_18], r15d
0x180019ca9  mov     edx, 1; FieldIndex
0x180019cae  mov     dword ptr [rbp+arg_0], r15d
0x180019cb2  lea     rcx, [rbp+Context]; Context
0x180019cb6  call    InfGetString
0x180019cbb  cmp     dword ptr [rbp+arg_0], r15d
0x180019cbf  jz      short loc_180019CCC
0x180019cc1  call    GetLastErrorAsHResult
0x180019cc6  mov     ebx, eax
0x180019cc8  test    eax, eax
0x180019cca  js      short loc_180019CE7
0x180019ccc  mov     rcx, [rbp+hMem]
0x180019cd0  lea     rdx, aTrue_0; "TRUE"
0x180019cd7  call    cs:__imp__o__wcsicmp
0x180019cdd  test    eax, eax
0x180019cdf  jnz     short loc_180019CE7
0x180019ce1  mov     dword ptr [rdi], 1
0x180019ce7  cmp     [rbp+hMem], r15
0x180019ceb  jz      short loc_180019CF7
0x180019ced  mov     rcx, [rbp+hMem]; hMem
0x180019cf1  call    cs:__imp_LocalFree
0x180019cf7  test    ebx, ebx
0x180019cf9  js      loc_180019DBB
0x180019cff  jmp     short loc_180019D0E
0x180019d01  cmp     ax, 102h
0x180019d05  jnz     loc_180019DBB
0x180019d0b  mov     ebx, r15d
0x180019d0e  cmp     [rdi], r15d
0x180019d11  jz      short loc_180019D29
0x180019d13  mov     r8, r14
0x180019d16  lea     rdx, aTheDriverInsta; "The driver installed from %ws is a null"...
0x180019d1d  lea     rcx, aIsnullprinterd; "IsNullPrinterDriver"
0x180019d24  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180019d29  cmp     [rdi], r15d
0x180019d2c  lea     rax, aNotANullDriver; "Not a null driver"
0x180019d33  lea     r9, aYesNullDriver; "Yes (Null Driver)"
0x180019d3a  mov     [rsp+70h+var_28], ebx
0x180019d3e  cmovz   r9, rax
0x180019d42  mov     [rsp+70h+var_30], r15d
0x180019d47  lea     r8, aNullDriverFlag; "Null Driver flag in additional info"
0x180019d4e  lea     rcx, SETUP_PARSEINF_SUCCEEDED
0x180019d55  jmp     short loc_180019D9B
0x180019d57  mov     r8, rcx
0x180019d5a  mov     [rsp+70h+var_50], rdi
0x180019d5f  lea     rcx, aIsnullprinterd; "IsNullPrinterDriver"
0x180019d66  mov     r9, r14
0x180019d69  lea     rdx, aInvalidArgumen_9; "Invalid Argument: hInf=%p, pcszInstallS"...
0x180019d70  mov     ebx, 80070057h
0x180019d75  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180019d7a  mov     [rsp+70h+var_28], 80070057h; unsigned int
0x180019d82  lea     r8, aInvalidArgumen_1; "Invalid argument"
0x180019d89  mov     [rsp+70h+var_30], 57h ; 'W'; unsigned int
0x180019d91  lea     rcx, SETUP_PARSEINF_FAILED; struct _EVENT_DESCRIPTOR *
0x180019d98  xor     r9d, r9d; unsigned __int16 *
0x180019d9b  mov     [rsp+70h+var_38], r15; unsigned __int16 *
0x180019da0  lea     rdx, aIsnullprinterd_0; "IsNullPrinterDriver"
0x180019da7  mov     [rsp+70h+var_40], r15; unsigned __int16 *
0x180019dac  mov     [rsp+70h+var_48], r15; unsigned __int16 *
0x180019db1  mov     [rsp+70h+var_50], r15; unsigned __int16 *
0x180019db6  call    ?SplLogPrinterSetupEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111KK@Z; SplLogPrinterSetupEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180019dbb  lea     r11, [rsp+70h+var_s0]
0x180019dc0  mov     eax, ebx
0x180019dc2  mov     rbx, [r11+28h]
0x180019dc6  mov     rdi, [r11+30h]
0x180019dca  mov     rsp, r11
0x180019dcd  pop     r15
0x180019dcf  pop     r14
0x180019dd1  pop     rbp
0x180019dd2  retn
```
