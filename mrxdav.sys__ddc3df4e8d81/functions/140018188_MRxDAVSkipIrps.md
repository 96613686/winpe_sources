# MRxDAVSkipIrps

- ea: `0x140018188`
- end: `0x14001831e`
- name: `MRxDAVSkipIrps`
- size: `406`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140017310`

## callees

- `0x1400067a0`
- `0x140018188`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x1400181c1`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400182a8`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400181c1`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400182a8`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400181d0`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400181d0`
- `ntoskrnl!RtlMultiByteToUnicodeN` at `0x140018203`
- `ntoskrnl!RtlMultiByteToUnicodeN` at `0x140018203`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140018230`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400182c8`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400182e3`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140018230`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400182c8`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400182e3`

## pseudocode

```c
__int64 __fastcall MRxDAVSkipIrps(__int64 a1, unsigned __int16 *a2, int a3)
{
  PEPROCESS CurrentProcess; // rax
  const CHAR *ProcessImageFileName; // rax
  unsigned __int64 v7; // rax
  __int64 v8; // rdx
  ULONG BytesInUnicodeString; // [rsp+30h] [rbp-29h] BYREF
  UNICODE_STRING v11; // [rsp+38h] [rbp-21h] BYREF
  UNICODE_STRING String1; // [rsp+48h] [rbp-11h] BYREF
  UNICODE_STRING String2; // [rsp+58h] [rbp-1h] BYREF
  UNICODE_STRING v14; // [rsp+68h] [rbp+Fh] BYREF
  WCHAR UnicodeString[8]; // [rsp+78h] [rbp+1Fh] BYREF
  _BYTE v16[28]; // [rsp+88h] [rbp+2Fh] BYREF

  BytesInUnicodeString = 0;
  String1 = 0;
  CurrentProcess = IoGetCurrentProcess();
  ProcessImageFileName = (const CHAR *)PsGetProcessImageFileName(CurrentProcess);
  memset(v16, 0, sizeof(v16));
  *(_OWORD *)UnicodeString = 0;
  RtlMultiByteToUnicodeN(UnicodeString, 0x2Cu, &BytesInUnicodeString, ProcessImageFileName, 0x10u);
  String1.Buffer = UnicodeString;
  String1.MaximumLength = BytesInUnicodeString;
  String1.Length = BytesInUnicodeString;
  if ( RtlCompareUnicodeString(&String1, &uniSvcHost, 1u) )
    return 3221225473LL;
  if ( a3 )
    return 0;
  *(_QWORD *)&String2.Length = 393222;
  String2.Buffer = L"exe";
  *(_QWORD *)&v14.Length = 393222;
  v14.Buffer = L"dll";
  v7 = *a2;
  v11 = 0;
  if ( (unsigned int)v7 <= 8 )
    return 3221225473LL;
  v8 = *((_QWORD *)a2 + 1);
  if ( *(_WORD *)(v8 + 2 * (v7 >> 1) - 8) != 46 )
    return 3221225473LL;
  *(_DWORD *)&v11.Length = 393222;
  v11.Buffer = (PWSTR)(v8 + 2 * (((unsigned __int64)(unsigned int)v7 - 6) >> 1));
  if ( (PEPROCESS)MRxDAVWebclientProcess != IoGetCurrentProcess()
    || RtlCompareUnicodeString(&v11, &String2, 1u) && RtlCompareUnicodeString(&v11, &v14, 1u) )
  {
    return 3221225473LL;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x140018188  mov     [rsp-8+arg_0], rbx
0x14001818d  mov     [rsp-8+arg_10], rdi
0x140018192  push    rbp
0x140018193  lea     rbp, [rsp-57h]
0x140018198  sub     rsp, 0B0h
0x14001819f  mov     rax, cs:__security_cookie
0x1400181a6  xor     rax, rsp
0x1400181a9  mov     [rbp+57h+var_8], rax
0x1400181ad  xorps   xmm0, xmm0
0x1400181b0  mov     [rbp+57h+BytesInUnicodeString], 0
0x1400181b7  movups  xmmword ptr [rbp+57h+String1.Length], xmm0
0x1400181bb  mov     edi, r8d
0x1400181be  mov     rbx, rdx
0x1400181c1  call    cs:__imp_IoGetCurrentProcess
0x1400181c8  nop     dword ptr [rax+rax+00h]
0x1400181cd  mov     rcx, rax
0x1400181d0  call    cs:__imp_PsGetProcessImageFileName
0x1400181d7  nop     dword ptr [rax+rax+00h]
0x1400181dc  xorps   xmm0, xmm0
0x1400181df  mov     [rsp+0B0h+BytesInMultiByteString], 10h; BytesInMultiByteString
0x1400181e7  movups  xmmword ptr [rbp+57h+var_28], xmm0
0x1400181eb  mov     r9, rax; MultiByteString
0x1400181ee  lea     r8, [rbp+57h+BytesInUnicodeString]; BytesInUnicodeString
0x1400181f2  mov     edx, 2Ch ; ','; MaxBytesInUnicodeString
0x1400181f7  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x1400181fb  movups  xmmword ptr [rbp+57h+var_28+0Ch], xmm0
0x1400181ff  movups  xmmword ptr [rbp+57h+UnicodeString], xmm0
0x140018203  call    cs:__imp_RtlMultiByteToUnicodeN
0x14001820a  nop     dword ptr [rax+rax+00h]
0x14001820f  lea     rax, [rbp+57h+UnicodeString]
0x140018213  mov     r8b, 1; CaseInSensitive
0x140018216  mov     [rbp+57h+String1.Buffer], rax
0x14001821a  lea     rdx, uniSvcHost; String2
0x140018221  mov     eax, [rbp+57h+BytesInUnicodeString]
0x140018224  lea     rcx, [rbp+57h+String1]; String1
0x140018228  mov     [rbp+57h+String1.MaximumLength], ax
0x14001822c  mov     [rbp+57h+String1.Length], ax
0x140018230  call    cs:__imp_RtlCompareUnicodeString
0x140018237  nop     dword ptr [rax+rax+00h]
0x14001823c  test    eax, eax
0x14001823e  jnz     loc_1400182F7
0x140018244  test    edi, edi
0x140018246  jnz     loc_1400182F3
0x14001824c  lea     rax, aExe; "exe"
0x140018253  mov     qword ptr [rbp+57h+String2.Length], 60006h
0x14001825b  mov     [rbp+57h+String2.Buffer], rax
0x14001825f  xorps   xmm0, xmm0
0x140018262  lea     rax, aDll; "dll"
0x140018269  mov     qword ptr [rbp+57h+var_48.Length], 60006h
0x140018271  mov     [rbp+57h+var_48.Buffer], rax
0x140018275  movzx   eax, word ptr [rbx]
0x140018278  movups  xmmword ptr [rbp+57h+var_78.Length], xmm0
0x14001827c  cmp     eax, 8
0x14001827f  jbe     short loc_1400182F7
0x140018281  mov     rdx, [rbx+8]
0x140018285  mov     ecx, eax
0x140018287  shr     rax, 1
0x14001828a  cmp     word ptr [rdx+rax*2-8], 2Eh ; '.'
0x140018290  jnz     short loc_1400182F7
0x140018292  lea     rax, [rcx-6]
0x140018296  mov     dword ptr [rbp+57h+var_78.Length], 60006h
0x14001829d  shr     rax, 1
0x1400182a0  lea     rax, [rdx+rax*2]
0x1400182a4  mov     [rbp+57h+var_78.Buffer], rax
0x1400182a8  call    cs:__imp_IoGetCurrentProcess
0x1400182af  nop     dword ptr [rax+rax+00h]
0x1400182b4  cmp     cs:MRxDAVWebclientProcess, rax
0x1400182bb  jnz     short loc_1400182F7
0x1400182bd  mov     r8b, 1; CaseInSensitive
0x1400182c0  lea     rdx, [rbp+57h+String2]; String2
0x1400182c4  lea     rcx, [rbp+57h+var_78]; String1
0x1400182c8  call    cs:__imp_RtlCompareUnicodeString
0x1400182cf  nop     dword ptr [rax+rax+00h]
0x1400182d4  test    eax, eax
0x1400182d6  jz      short loc_1400182F3
0x1400182d8  mov     r8b, 1; CaseInSensitive
0x1400182db  lea     rdx, [rbp+57h+var_48]; String2
0x1400182df  lea     rcx, [rbp+57h+var_78]; String1
0x1400182e3  call    cs:__imp_RtlCompareUnicodeString
0x1400182ea  nop     dword ptr [rax+rax+00h]
0x1400182ef  test    eax, eax
0x1400182f1  jnz     short loc_1400182F7
0x1400182f3  xor     eax, eax
0x1400182f5  jmp     short loc_1400182FC
0x1400182f7  mov     eax, 0C0000001h
0x1400182fc  mov     rcx, [rbp+57h+var_8]
0x140018300  xor     rcx, rsp; StackCookie
0x140018303  call    __security_check_cookie
0x140018308  lea     r11, [rsp+0B0h+var_s0]
0x140018310  mov     rbx, [r11+10h]
0x140018314  mov     rdi, [r11+20h]
0x140018318  mov     rsp, r11
0x14001831b  pop     rbp
0x14001831c  retn
```
