# FwppDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY1

- ea: `0x1800302a4`
- end: `0x180030372`
- name: `FwppDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY1`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180022cf0`

## callees

- `0x180007e38`
- `0x180011500`
- `0x180024680`
- `0x1800302a4`
- `0x18003708c`

## string_xrefs

- `0x180030303`: `FwppDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY_FLAGS`
- `0x180030317`: `FwppDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY_FLAGS`
- `0x18003032e`: `FwppDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY1`
- `0x18003034f`: `FwppDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY1`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY1(unsigned int *a1, unsigned int *a2)
{
  _DWORD *v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rax

  if ( !a1 || !a2 )
  {
    v5 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY1", 3223453724LL);
    if ( !v5 )
      return v5;
    goto LABEL_12;
  }
  v4 = (_DWORD *)*((_QWORD *)a1 + 1);
  if ( v4 )
  {
    v5 = FwppArrayAllocAndDeepCopyFromVerIndependent_GUID(v4, *a1, a2 + 2);
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
  v6 = WfpReportSysErrorAsNtStatus(v4, "FwppDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY_FLAGS", 3223453724LL);
  v5 = v6;
  if ( !v6 )
    return v5;
  WfpReportError(v6, "FwppDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY_FLAGS");
LABEL_12:
  FwppDeepFreeContentsOnly_IPSEC_KEYING_POLICY1(a2);
  if ( v5 )
    WfpReportError(v5, "FwppDeepCopyFromVerIndependent_IPSEC_KEYING_POLICY1");
  return v5;
}

```

## disassembly

```asm
0x1800302a4  mov     [rsp+arg_0], rbx
0x1800302a9  mov     [rsp+arg_8], rsi
0x1800302ae  push    rdi
0x1800302af  sub     rsp, 20h
0x1800302b3  mov     rsi, rdx
0x1800302b6  mov     rdi, rcx
0x1800302b9  test    rcx, rcx
0x1800302bc  jz      short loc_180030328
0x1800302be  test    rdx, rdx
0x1800302c1  jz      short loc_180030328
0x1800302c3  mov     rcx, [rcx+8]
0x1800302c7  test    rcx, rcx
0x1800302ca  jz      short loc_1800302E3
0x1800302cc  lea     r8, [rdx+8]
0x1800302d0  mov     edx, [rdi]
0x1800302d2  call    FwppArrayAllocAndDeepCopyFromVerIndependent_GUID
0x1800302d7  mov     rbx, rax
0x1800302da  test    rax, rax
0x1800302dd  jnz     short loc_180030342
0x1800302df  mov     eax, [rdi]
0x1800302e1  mov     [rsi], eax
0x1800302e3  lea     rax, [rdi+10h]
0x1800302e7  test    rax, rax
0x1800302ea  jz      short loc_1800302FD
0x1800302ec  lea     rcx, [rsi+10h]
0x1800302f0  test    rcx, rcx
0x1800302f3  jz      short loc_1800302FD
0x1800302f5  mov     eax, [rax]
0x1800302f7  xor     ebx, ebx
0x1800302f9  mov     [rcx], eax
0x1800302fb  jmp     short loc_18003035E
0x1800302fd  mov     r8d, 0C022001Ch
0x180030303  lea     rdx, aFwppdeepcopyfr_45; "FwppDeepCopyFromVerIndependent_IPSEC_KE"...
0x18003030a  call    WfpReportSysErrorAsNtStatus
0x18003030f  mov     rbx, rax
0x180030312  test    rax, rax
0x180030315  jz      short loc_18003035E
0x180030317  lea     rdx, aFwppdeepcopyfr_45; "FwppDeepCopyFromVerIndependent_IPSEC_KE"...
0x18003031e  mov     rcx, rax
0x180030321  call    WfpReportError
0x180030326  jmp     short loc_180030342
0x180030328  mov     r8d, 0C022001Ch
0x18003032e  lea     rdx, aFwppdeepcopyfr_49; "FwppDeepCopyFromVerIndependent_IPSEC_KE"...
0x180030335  call    WfpReportSysErrorAsNtStatus
0x18003033a  mov     rbx, rax
0x18003033d  test    rax, rax
0x180030340  jz      short loc_18003035E
0x180030342  mov     rcx, rsi
0x180030345  call    FwppDeepFreeContentsOnly_IPSEC_KEYING_POLICY1
0x18003034a  test    rbx, rbx
0x18003034d  jz      short loc_18003035E
0x18003034f  lea     rdx, aFwppdeepcopyfr_49; "FwppDeepCopyFromVerIndependent_IPSEC_KE"...
0x180030356  mov     rcx, rbx
0x180030359  call    WfpReportError
0x18003035e  mov     rsi, [rsp+28h+arg_8]
0x180030363  mov     rax, rbx
0x180030366  mov     rbx, [rsp+28h+arg_0]
0x18003036b  add     rsp, 20h
0x18003036f  pop     rdi
0x180030370  retn
```
