# FwppDeepCopyToVerIndependent_IPSEC_KEYING_POLICY1

- ea: `0x1800349a0`
- end: `0x180034a6e`
- name: `FwppDeepCopyToVerIndependent_IPSEC_KEYING_POLICY1`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180023e00`

## callees

- `0x180007e38`
- `0x180011500`
- `0x180025774`
- `0x1800349a0`
- `0x18003708c`

## string_xrefs

- `0x1800349ff`: `FwppDeepCopyToVerIndependent_IPSEC_KEYING_POLICY_FLAGS`
- `0x180034a13`: `FwppDeepCopyToVerIndependent_IPSEC_KEYING_POLICY_FLAGS`
- `0x180034a2a`: `FwppDeepCopyToVerIndependent_IPSEC_KEYING_POLICY1`
- `0x180034a4b`: `FwppDeepCopyToVerIndependent_IPSEC_KEYING_POLICY1`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyToVerIndependent_IPSEC_KEYING_POLICY1(unsigned int *a1, unsigned int *a2)
{
  _DWORD *v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rax

  if ( !a1 || !a2 )
  {
    v5 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyToVerIndependent_IPSEC_KEYING_POLICY1", 3223453724LL);
    if ( !v5 )
      return v5;
    goto LABEL_12;
  }
  v4 = (_DWORD *)*((_QWORD *)a1 + 1);
  if ( v4 )
  {
    v5 = FwppArrayAllocAndDeepCopyToVerIndependent_GUID(v4, *a1, a2 + 2);
    if ( v5 )
      goto LABEL_12;
    *a2 = *a1;
  }
  if ( a1 != (unsigned int *)-16LL )
  {
    v4 = a2 + 4;
    if ( a2 != (unsigned int *)-16LL )
    {
      v5 = 0;
      *v4 = a1[4];
      return v5;
    }
  }
  v6 = WfpReportSysErrorAsNtStatus(v4, "FwppDeepCopyToVerIndependent_IPSEC_KEYING_POLICY_FLAGS", 3223453724LL);
  v5 = v6;
  if ( !v6 )
    return v5;
  WfpReportError(v6, "FwppDeepCopyToVerIndependent_IPSEC_KEYING_POLICY_FLAGS");
LABEL_12:
  FwppDeepFreeContentsOnly_IPSEC_KEYING_POLICY1(a2);
  if ( v5 )
    WfpReportError(v5, "FwppDeepCopyToVerIndependent_IPSEC_KEYING_POLICY1");
  return v5;
}

```

## disassembly

```asm
0x1800349a0  mov     [rsp+arg_0], rbx
0x1800349a5  mov     [rsp+arg_8], rsi
0x1800349aa  push    rdi
0x1800349ab  sub     rsp, 20h
0x1800349af  mov     rsi, rdx
0x1800349b2  mov     rdi, rcx
0x1800349b5  test    rcx, rcx
0x1800349b8  jz      short loc_180034A24
0x1800349ba  test    rdx, rdx
0x1800349bd  jz      short loc_180034A24
0x1800349bf  mov     rcx, [rcx+8]
0x1800349c3  test    rcx, rcx
0x1800349c6  jz      short loc_1800349DF
0x1800349c8  lea     r8, [rdx+8]
0x1800349cc  mov     edx, [rdi]
0x1800349ce  call    FwppArrayAllocAndDeepCopyToVerIndependent_GUID
0x1800349d3  mov     rbx, rax
0x1800349d6  test    rax, rax
0x1800349d9  jnz     short loc_180034A3E
0x1800349db  mov     eax, [rdi]
0x1800349dd  mov     [rsi], eax
0x1800349df  lea     rax, [rdi+10h]
0x1800349e3  test    rax, rax
0x1800349e6  jz      short loc_1800349F9
0x1800349e8  lea     rcx, [rsi+10h]
0x1800349ec  test    rcx, rcx
0x1800349ef  jz      short loc_1800349F9
0x1800349f1  mov     eax, [rax]
0x1800349f3  xor     ebx, ebx
0x1800349f5  mov     [rcx], eax
0x1800349f7  jmp     short loc_180034A5A
0x1800349f9  mov     r8d, 0C022001Ch
0x1800349ff  lea     rdx, aFwppdeepcopyto_81; "FwppDeepCopyToVerIndependent_IPSEC_KEYI"...
0x180034a06  call    WfpReportSysErrorAsNtStatus
0x180034a0b  mov     rbx, rax
0x180034a0e  test    rax, rax
0x180034a11  jz      short loc_180034A5A
0x180034a13  lea     rdx, aFwppdeepcopyto_81; "FwppDeepCopyToVerIndependent_IPSEC_KEYI"...
0x180034a1a  mov     rcx, rax
0x180034a1d  call    WfpReportError
0x180034a22  jmp     short loc_180034A3E
0x180034a24  mov     r8d, 0C022001Ch
0x180034a2a  lea     rdx, aFwppdeepcopyto_36; "FwppDeepCopyToVerIndependent_IPSEC_KEYI"...
0x180034a31  call    WfpReportSysErrorAsNtStatus
0x180034a36  mov     rbx, rax
0x180034a39  test    rax, rax
0x180034a3c  jz      short loc_180034A5A
0x180034a3e  mov     rcx, rsi
0x180034a41  call    FwppDeepFreeContentsOnly_IPSEC_KEYING_POLICY1
0x180034a46  test    rbx, rbx
0x180034a49  jz      short loc_180034A5A
0x180034a4b  lea     rdx, aFwppdeepcopyto_36; "FwppDeepCopyToVerIndependent_IPSEC_KEYI"...
0x180034a52  mov     rcx, rbx
0x180034a55  call    WfpReportError
0x180034a5a  mov     rsi, [rsp+28h+arg_8]
0x180034a5f  mov     rax, rbx
0x180034a62  mov     rbx, [rsp+28h+arg_0]
0x180034a67  add     rsp, 20h
0x180034a6b  pop     rdi
0x180034a6c  retn
```
