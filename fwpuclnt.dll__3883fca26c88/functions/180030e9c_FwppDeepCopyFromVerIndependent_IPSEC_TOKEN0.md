# FwppDeepCopyFromVerIndependent_IPSEC_TOKEN0

- ea: `0x180030e9c`
- end: `0x180030fa1`
- name: `FwppDeepCopyFromVerIndependent_IPSEC_TOKEN0`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180025154`

## callees

- `0x1800071a8`
- `0x180007e38`
- `0x180011500`
- `0x1800120e0`
- `0x180030e9c`

## string_xrefs

- `0x180030f3e`: `FwppDeepCopyFromVerIndependent_IPSEC_TOKEN_PRINCIPAL`
- `0x180030f52`: `FwppDeepCopyFromVerIndependent_IPSEC_TOKEN_PRINCIPAL`
- `0x180030f69`: `FwppDeepCopyFromVerIndependent_IPSEC_TOKEN_MODE`
- `0x180030f81`: `FwppDeepCopyFromVerIndependent_IPSEC_TOKEN_MODE`
- `0x180030f15`: `FwppDeepCopyFromVerIndependent_IPSEC_TOKEN0`
- `0x180030f90`: `FwppDeepCopyFromVerIndependent_IPSEC_TOKEN0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_IPSEC_TOKEN0(DWORD *p_Attributes, struct _SID_AND_ATTRIBUTES *a2)
{
  DWORD *v3; // rsi
  DWORD *v4; // rax
  __int64 v5; // rax
  __int64 v6; // rbx
  __int64 v8; // rax
  const char *v9; // rdx

  v3 = p_Attributes;
  if ( !p_Attributes || !a2 )
  {
    v5 = WfpReportSysErrorAsNtStatus(p_Attributes, "FwppDeepCopyFromVerIndependent_IPSEC_TOKEN0", 3223453724LL);
LABEL_10:
    v6 = v5;
    if ( !v5 )
      return v6;
    goto LABEL_11;
  }
  LODWORD(a2->Sid) = *p_Attributes;
  v4 = p_Attributes + 1;
  if ( p_Attributes == (DWORD *)-4LL || (p_Attributes = (DWORD *)&a2->Sid + 1, a2 == (struct _SID_AND_ATTRIBUTES *)-4LL) )
  {
    v8 = WfpReportSysErrorAsNtStatus(p_Attributes, "FwppDeepCopyFromVerIndependent_IPSEC_TOKEN_PRINCIPAL", 3223453724LL);
    v6 = v8;
    if ( v8 )
    {
      v9 = "FwppDeepCopyFromVerIndependent_IPSEC_TOKEN_PRINCIPAL";
      goto LABEL_16;
    }
  }
  else
  {
    *p_Attributes = *v4;
  }
  if ( v3 != (DWORD *)-8LL )
  {
    p_Attributes = &a2->Attributes;
    if ( a2 != (struct _SID_AND_ATTRIBUTES *)-8LL )
    {
      *p_Attributes = v3[2];
LABEL_9:
      v5 = FwppDeepCopyFromVerIndependent_UINT64(v3 + 4, &a2[1]);
      goto LABEL_10;
    }
  }
  v8 = WfpReportSysErrorAsNtStatus(p_Attributes, "FwppDeepCopyFromVerIndependent_IPSEC_TOKEN_MODE", 3223453724LL);
  v6 = v8;
  if ( !v8 )
    goto LABEL_9;
  v9 = "FwppDeepCopyFromVerIndependent_IPSEC_TOKEN_MODE";
LABEL_16:
  WfpReportError(v8, v9);
LABEL_11:
  FeFreeGroupsCallback(a2);
  if ( v6 )
    WfpReportError(v6, "FwppDeepCopyFromVerIndependent_IPSEC_TOKEN0");
  return v6;
}

```

## disassembly

```asm
0x180030e9c  mov     [rsp+arg_0], rbx
0x180030ea1  mov     [rsp+arg_8], rsi
0x180030ea6  push    rdi
0x180030ea7  sub     rsp, 20h
0x180030eab  mov     rdi, rdx
0x180030eae  mov     rsi, rcx
0x180030eb1  test    rcx, rcx
0x180030eb4  jz      loc_180030F8A
0x180030eba  test    rdx, rdx
0x180030ebd  jz      loc_180030F8A
0x180030ec3  mov     eax, [rcx]
0x180030ec5  mov     [rdx], eax
0x180030ec7  lea     rax, [rcx+4]
0x180030ecb  test    rax, rax
0x180030ece  jz      short loc_180030F38
0x180030ed0  lea     rcx, [rdx+4]
0x180030ed4  test    rcx, rcx
0x180030ed7  jz      short loc_180030F38
0x180030ed9  mov     eax, [rax]
0x180030edb  mov     [rcx], eax
0x180030edd  lea     rax, [rsi+8]
0x180030ee1  test    rax, rax
0x180030ee4  jz      short loc_180030F63
0x180030ee6  lea     rcx, [rdi+8]
0x180030eea  test    rcx, rcx
0x180030eed  jz      short loc_180030F63
0x180030eef  mov     eax, [rax]
0x180030ef1  mov     [rcx], eax
0x180030ef3  lea     rdx, [rdi+10h]
0x180030ef7  lea     rcx, [rsi+10h]
0x180030efb  call    FwppDeepCopyFromVerIndependent_UINT64
0x180030f00  mov     rbx, rax
0x180030f03  test    rax, rax
0x180030f06  jz      short loc_180030F24
0x180030f08  mov     rcx, rdi; pSidAttrArray
0x180030f0b  call    FeFreeGroupsCallback
0x180030f10  test    rbx, rbx
0x180030f13  jz      short loc_180030F24
0x180030f15  lea     rdx, aFwppdeepcopyfr_51; "FwppDeepCopyFromVerIndependent_IPSEC_TO"...
0x180030f1c  mov     rcx, rbx
0x180030f1f  call    WfpReportError
0x180030f24  mov     rsi, [rsp+28h+arg_8]
0x180030f29  mov     rax, rbx
0x180030f2c  mov     rbx, [rsp+28h+arg_0]
0x180030f31  add     rsp, 20h
0x180030f35  pop     rdi
0x180030f36  retn
0x180030f38  mov     r8d, 0C022001Ch
0x180030f3e  lea     rdx, aFwppdeepcopyfr_42; "FwppDeepCopyFromVerIndependent_IPSEC_TO"...
0x180030f45  call    WfpReportSysErrorAsNtStatus
0x180030f4a  mov     rbx, rax
0x180030f4d  test    rax, rax
0x180030f50  jz      short loc_180030EDD
0x180030f52  lea     rdx, aFwppdeepcopyfr_42; "FwppDeepCopyFromVerIndependent_IPSEC_TO"...
0x180030f59  mov     rcx, rax
0x180030f5c  call    WfpReportError
0x180030f61  jmp     short loc_180030F08
0x180030f63  mov     r8d, 0C022001Ch
0x180030f69  lea     rdx, aFwppdeepcopyfr_134; "FwppDeepCopyFromVerIndependent_IPSEC_TO"...
0x180030f70  call    WfpReportSysErrorAsNtStatus
0x180030f75  mov     rbx, rax
0x180030f78  test    rax, rax
0x180030f7b  jz      loc_180030EF3
0x180030f81  lea     rdx, aFwppdeepcopyfr_134; "FwppDeepCopyFromVerIndependent_IPSEC_TO"...
0x180030f88  jmp     short loc_180030F59
0x180030f8a  mov     r8d, 0C022001Ch
0x180030f90  lea     rdx, aFwppdeepcopyfr_51; "FwppDeepCopyFromVerIndependent_IPSEC_TO"...
0x180030f97  call    WfpReportSysErrorAsNtStatus
0x180030f9c  jmp     loc_180030F00
```
