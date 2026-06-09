# BfeSidValidate

- ea: `0x1800475d0`
- end: `0x18004761b`
- name: `BfeSidValidate`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800471fc`

## callees

- `0x180007e38`
- `0x180011500`
- `0x1800475d0`

## import_xrefs

- `ntdll!RtlValidSid` at `0x1800475d8`
- `ntdll!RtlValidSid` at `0x1800475d8`

## string_xrefs

- `0x1800475ee`: `BfeSidValidate`
- `0x180047602`: `BfeSidValidate`

## pseudocode

```c
__int64 __fastcall BfeSidValidate(void *a1)
{
  __int64 v1; // rbx
  __int64 v2; // rcx
  __int64 v3; // rax

  v1 = 0;
  if ( !RtlValidSid(a1) )
  {
    v3 = WfpReportSysErrorAsNtStatus(v2, "BfeSidValidate", 3221225592LL);
    v1 = v3;
    if ( v3 )
      WfpReportError(v3, "BfeSidValidate");
  }
  return v1;
}

```

## disassembly

```asm
0x1800475d0  push    rbx
0x1800475d2  sub     rsp, 20h
0x1800475d6  xor     ebx, ebx
0x1800475d8  call    cs:__imp_RtlValidSid
0x1800475df  nop     dword ptr [rax+rax+00h]
0x1800475e4  test    al, al
0x1800475e6  jnz     short loc_180047611
0x1800475e8  mov     r8d, 0C0000078h
0x1800475ee  lea     rdx, aBfesidvalidate; "BfeSidValidate"
0x1800475f5  call    WfpReportSysErrorAsNtStatus
0x1800475fa  mov     rbx, rax
0x1800475fd  test    rax, rax
0x180047600  jz      short loc_180047611
0x180047602  lea     rdx, aBfesidvalidate; "BfeSidValidate"
0x180047609  mov     rcx, rax
0x18004760c  call    WfpReportError
0x180047611  mov     rax, rbx
0x180047614  add     rsp, 20h
0x180047618  pop     rbx
0x180047619  retn
```
