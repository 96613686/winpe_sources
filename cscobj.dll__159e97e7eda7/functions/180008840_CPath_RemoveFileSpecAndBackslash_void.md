# CPath::RemoveFileSpecAndBackslash(void)

- ea: `0x180008840`
- end: `0x1800088aa`
- name: `?RemoveFileSpecAndBackslash@CPath@@QEAAJXZ`
- size: `106`
- prototype: `__int64 __fastcall(CPath *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x1800020a0`
- `0x180003ca0`
- `0x180004028`
- `0x18001057c`
- `0x180011e38`

## callees

- `0x180008840`
- `0x1800102a8`

## import_xrefs

- `ntdll!RtlpApplyLengthFunction` at `0x180008862`
- `ntdll!RtlpApplyLengthFunction` at `0x18000888a`
- `ntdll!RtlpApplyLengthFunction` at `0x180008862`
- `ntdll!RtlpApplyLengthFunction` at `0x18000888a`
- `ntdll!RtlGetLengthWithoutLastFullDosOrNtPathElement` at `0x18000884a`
- `ntdll!RtlGetLengthWithoutTrailingPathSeperators` at `0x180008879`

## pseudocode

```c
__int64 __fastcall CPath::RemoveFileSpecAndBackslash(CPath *this)
{
  char *v1; // rdi
  NTSTATUS v2; // eax
  int v3; // ebx
  NTSTATUS v4; // eax

  v1 = (char *)this + 520;
  v2 = RtlpApplyLengthFunction(0, 0x38u, (char *)this + 520, RtlGetLengthWithoutLastFullDosOrNtPathElement);
  if ( v2 >= 0 || (v3 = ResultFromNtStatus(v2), v3 >= 0) )
  {
    v3 = 0;
    v4 = RtlpApplyLengthFunction(0, 0x38u, v1, RtlGetLengthWithoutTrailingPathSeperators);
    if ( v4 < 0 )
      return (unsigned int)ResultFromNtStatus(v4);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180008840  mov     [rsp+arg_0], rbx
0x180008845  push    rdi
0x180008846  sub     rsp, 20h
0x18000884a  mov     r9, cs:__imp_RtlGetLengthWithoutLastFullDosOrNtPathElement; LengthFunction
0x180008851  lea     rdi, [rcx+208h]
0x180008858  mov     r8, rdi; UnicodeStringOrUnicodeStringBuffer
0x18000885b  mov     edx, 38h ; '8'; Type
0x180008860  xor     ecx, ecx; Flags
0x180008862  call    cs:__imp_RtlpApplyLengthFunction
0x180008868  test    eax, eax
0x18000886a  jns     short loc_180008879
0x18000886c  mov     ecx, eax; int
0x18000886e  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x180008873  mov     ebx, eax
0x180008875  test    eax, eax
0x180008877  js      short loc_18000889D
0x180008879  mov     r9, cs:__imp_RtlGetLengthWithoutTrailingPathSeperators; LengthFunction
0x180008880  xor     ebx, ebx
0x180008882  mov     r8, rdi; UnicodeStringOrUnicodeStringBuffer
0x180008885  xor     ecx, ecx; Flags
0x180008887  lea     edx, [rbx+38h]; Type
0x18000888a  call    cs:__imp_RtlpApplyLengthFunction
0x180008890  test    eax, eax
0x180008892  jns     short loc_18000889D
0x180008894  mov     ecx, eax; int
0x180008896  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x18000889b  mov     ebx, eax
0x18000889d  mov     eax, ebx
0x18000889f  mov     rbx, [rsp+28h+arg_0]
0x1800088a4  add     rsp, 20h
0x1800088a8  pop     rdi
0x1800088a9  retn
```
