# FIPfConflictTelemetryGetFileName

- ea: `0x14000f0b0`
- end: `0x14000f207`
- name: `FIPfConflictTelemetryGetFileName`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000f9b8`

## callees

- `0x140003920`
- `0x14000f0b0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14000f19e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000f19e`
- `FLTMGR!FltParseFileName` at `0x14000f10a`
- `FLTMGR!FltParseFileName` at `0x14000f10a`

## pseudocode

```c
__int64 __fastcall FIPfConflictTelemetryGetFileName(wchar_t *a1, __int16 a2, wchar_t **a3, int *a4)
{
  unsigned int v6; // ebx
  __int64 result; // rax
  wchar_t *Buffer; // rdx
  unsigned __int16 Length; // cx
  UNICODE_STRING FileName; // [rsp+20h] [rbp-69h] BYREF
  struct _UNICODE_STRING FinalComponent; // [rsp+30h] [rbp-59h] BYREF
  struct _UNICODE_STRING Extension; // [rsp+40h] [rbp-49h] BYREF
  struct _UNICODE_STRING Stream; // [rsp+50h] [rbp-39h] BYREF
  _DWORD v14[2]; // [rsp+60h] [rbp-29h] BYREF
  const wchar_t *v15; // [rsp+68h] [rbp-21h]
  int v16; // [rsp+70h] [rbp-19h]
  const wchar_t *v17; // [rsp+78h] [rbp-11h]
  int v18; // [rsp+80h] [rbp-9h]
  const wchar_t *v19; // [rsp+88h] [rbp-1h]
  int v20; // [rsp+90h] [rbp+7h]
  const wchar_t *v21; // [rsp+98h] [rbp+Fh]
  int v22; // [rsp+A0h] [rbp+17h]
  const wchar_t *v23; // [rsp+A8h] [rbp+1Fh]

  *(&FileName.MaximumLength + 2) = 0;
  FileName.Buffer = a1;
  FileName.Length = 2 * a2;
  *(_DWORD *)&FileName.MaximumLength = (unsigned __int16)(2 * a2);
  Extension = 0;
  Stream = 0;
  FinalComponent = 0;
  if ( FltParseFileName(&FileName, &Extension, &Stream, &FinalComponent) >= 0 && Extension.Buffer )
  {
    v14[0] = 524294;
    v15 = L"exe";
    v6 = 0;
    v16 = 524294;
    v17 = L"dll";
    v19 = L"sys";
    v21 = L"com";
    v23 = L"bat";
    v18 = 524294;
    v20 = 524294;
    v22 = 524294;
    while ( v6 < 5 )
    {
      if ( !RtlCompareUnicodeString((PCUNICODE_STRING)&v14[4 * v6], &Extension, 1u) )
      {
        result = 1;
        goto LABEL_9;
      }
      ++v6;
    }
  }
  result = 0;
LABEL_9:
  Buffer = FinalComponent.Buffer;
  if ( FinalComponent.Buffer )
  {
    Length = FinalComponent.Length;
  }
  else
  {
    result = 1;
    Buffer = L"\\";
    Length = 2;
  }
  if ( Stream.Buffer )
    Length -= Stream.Length;
  *a3 = Buffer;
  *a4 = Length >> 1;
  return result;
}

```

## disassembly

```asm
0x14000f0b0  push    rbp
0x14000f0b2  push    rbx
0x14000f0b3  push    rsi
0x14000f0b4  push    rdi
0x14000f0b5  lea     rbp, [rsp-3Fh]
0x14000f0ba  sub     rsp, 0C8h
0x14000f0c1  mov     rax, cs:__security_cookie
0x14000f0c8  xor     rax, rsp
0x14000f0cb  mov     [rbp+57h+var_30], rax
0x14000f0cf  add     dx, dx
0x14000f0d2  xorps   xmm1, xmm1
0x14000f0d5  movups  xmmword ptr [rbp+57h+FileName.Length], xmm1
0x14000f0d9  mov     [rbp+57h+FileName.Buffer], rcx
0x14000f0dd  mov     rsi, r9
0x14000f0e0  xorps   xmm0, xmm0
0x14000f0e3  mov     [rbp+57h+FileName.Length], dx
0x14000f0e7  mov     [rbp+57h+FileName.MaximumLength], dx
0x14000f0eb  lea     rcx, [rbp+57h+FileName]; FileName
0x14000f0ef  mov     rdi, r8
0x14000f0f2  lea     rdx, [rbp+57h+Extension]; Extension
0x14000f0f6  lea     r9, [rbp+57h+FinalComponent]; FinalComponent
0x14000f0fa  lea     r8, [rbp+57h+Stream]; Stream
0x14000f0fe  movups  xmmword ptr [rbp+57h+Extension.Length], xmm0
0x14000f102  movups  xmmword ptr [rbp+57h+Stream.Length], xmm1
0x14000f106  movups  xmmword ptr [rbp+57h+FinalComponent.Length], xmm0
0x14000f10a  call    cs:__imp_FltParseFileName
0x14000f111  nop     dword ptr [rax+rax+00h]
0x14000f116  test    eax, eax
0x14000f118  js      loc_14000F1B9
0x14000f11e  cmp     [rbp+57h+Extension.Buffer], 0
0x14000f123  jz      loc_14000F1B9
0x14000f129  lea     rax, aExe; "exe"
0x14000f130  mov     [rbp+57h+var_80], 80006h
0x14000f137  mov     [rbp+57h+var_78], rax
0x14000f13b  xor     ebx, ebx
0x14000f13d  lea     rax, aDll; "dll"
0x14000f144  mov     [rbp+57h+var_70], 80006h
0x14000f14b  mov     [rbp+57h+var_68], rax
0x14000f14f  lea     rax, aSys; "sys"
0x14000f156  mov     [rbp+57h+var_58], rax
0x14000f15a  lea     rax, aCom; "com"
0x14000f161  mov     [rbp+57h+var_48], rax
0x14000f165  lea     rax, aBat; "bat"
0x14000f16c  mov     [rbp+57h+var_38], rax
0x14000f170  mov     [rbp+57h+var_60], 80006h
0x14000f177  mov     [rbp+57h+var_50], 80006h
0x14000f17e  mov     [rbp+57h+var_40], 80006h
0x14000f185  cmp     ebx, 5
0x14000f188  jnb     short loc_14000F1B9
0x14000f18a  mov     eax, ebx
0x14000f18c  lea     rcx, [rbp+57h+var_80]
0x14000f190  shl     rax, 4
0x14000f194  lea     rdx, [rbp+57h+Extension]; String2
0x14000f198  add     rcx, rax; String1
0x14000f19b  mov     r8b, 1; CaseInSensitive
0x14000f19e  call    cs:__imp_RtlCompareUnicodeString
0x14000f1a5  nop     dword ptr [rax+rax+00h]
0x14000f1aa  test    eax, eax
0x14000f1ac  jz      short loc_14000F1B2
0x14000f1ae  inc     ebx
0x14000f1b0  jmp     short loc_14000F185
0x14000f1b2  mov     eax, 1
0x14000f1b7  jmp     short loc_14000F1BB
0x14000f1b9  xor     eax, eax
0x14000f1bb  mov     rdx, [rbp+57h+FinalComponent.Buffer]
0x14000f1bf  test    rdx, rdx
0x14000f1c2  jz      short loc_14000F1CA
0x14000f1c4  movzx   ecx, [rbp+57h+FinalComponent.Length]
0x14000f1c8  jmp     short loc_14000F1D9
0x14000f1ca  mov     eax, 1
0x14000f1cf  lea     rdx, asc_1400061F0; "\\"
0x14000f1d6  lea     ecx, [rax+1]
0x14000f1d9  cmp     [rbp+57h+Stream.Buffer], 0
0x14000f1de  jz      short loc_14000F1E4
0x14000f1e0  sub     cx, [rbp+57h+Stream.Length]
0x14000f1e4  movzx   ecx, cx
0x14000f1e7  shr     ecx, 1
0x14000f1e9  mov     [rdi], rdx
0x14000f1ec  mov     [rsi], ecx
0x14000f1ee  mov     rcx, [rbp+57h+var_30]
0x14000f1f2  xor     rcx, rsp; StackCookie
0x14000f1f5  call    __security_check_cookie
0x14000f1fa  add     rsp, 0C8h
0x14000f201  pop     rdi
0x14000f202  pop     rsi
0x14000f203  pop     rbx
0x14000f204  pop     rbp
0x14000f205  retn
```
