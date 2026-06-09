# FwppDeepCopyToVerIndependent_IPSEC_TOKEN0

- ea: `0x1800351f4`
- end: `0x1800352f9`
- name: `FwppDeepCopyToVerIndependent_IPSEC_TOKEN0`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180025d60`

## callees

- `0x180007e38`
- `0x180011500`
- `0x1800120e0`
- `0x1800351f4`
- `0x180035d9c`

## string_xrefs

- `0x180035296`: `FwppDeepCopyToVerIndependent_IPSEC_TOKEN_PRINCIPAL`
- `0x1800352aa`: `FwppDeepCopyToVerIndependent_IPSEC_TOKEN_PRINCIPAL`
- `0x1800352c1`: `FwppDeepCopyToVerIndependent_IPSEC_TOKEN_MODE`
- `0x1800352d9`: `FwppDeepCopyToVerIndependent_IPSEC_TOKEN_MODE`
- `0x18003526d`: `FwppDeepCopyToVerIndependent_IPSEC_TOKEN0`
- `0x1800352e8`: `FwppDeepCopyToVerIndependent_IPSEC_TOKEN0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyToVerIndependent_IPSEC_TOKEN0(DWORD *p_Attributes, struct _SID_AND_ATTRIBUTES *a2)
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
    v5 = WfpReportSysErrorAsNtStatus(p_Attributes, "FwppDeepCopyToVerIndependent_IPSEC_TOKEN0", 3223453724LL);
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
    v8 = WfpReportSysErrorAsNtStatus(p_Attributes, "FwppDeepCopyToVerIndependent_IPSEC_TOKEN_PRINCIPAL", 3223453724LL);
    v6 = v8;
    if ( v8 )
    {
      v9 = "FwppDeepCopyToVerIndependent_IPSEC_TOKEN_PRINCIPAL";
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
      v5 = FwppDeepCopyToVerIndependent_UINT64(v3 + 4, &a2[1]);
      goto LABEL_10;
    }
  }
  v8 = WfpReportSysErrorAsNtStatus(p_Attributes, "FwppDeepCopyToVerIndependent_IPSEC_TOKEN_MODE", 3223453724LL);
  v6 = v8;
  if ( !v8 )
    goto LABEL_9;
  v9 = "FwppDeepCopyToVerIndependent_IPSEC_TOKEN_MODE";
LABEL_16:
  WfpReportError(v8, v9);
LABEL_11:
  FeFreeGroupsCallback(a2);
  if ( v6 )
    WfpReportError(v6, "FwppDeepCopyToVerIndependent_IPSEC_TOKEN0");
  return v6;
}

```

## disassembly

```asm
0x1800351f4  mov     [rsp+arg_0], rbx
0x1800351f9  mov     [rsp+arg_8], rsi
0x1800351fe  push    rdi
0x1800351ff  sub     rsp, 20h
0x180035203  mov     rdi, rdx
0x180035206  mov     rsi, rcx
0x180035209  test    rcx, rcx
0x18003520c  jz      loc_1800352E2
0x180035212  test    rdx, rdx
0x180035215  jz      loc_1800352E2
0x18003521b  mov     eax, [rcx]
0x18003521d  mov     [rdx], eax
0x18003521f  lea     rax, [rcx+4]
0x180035223  test    rax, rax
0x180035226  jz      short loc_180035290
0x180035228  lea     rcx, [rdx+4]
0x18003522c  test    rcx, rcx
0x18003522f  jz      short loc_180035290
0x180035231  mov     eax, [rax]
0x180035233  mov     [rcx], eax
0x180035235  lea     rax, [rsi+8]
0x180035239  test    rax, rax
0x18003523c  jz      short loc_1800352BB
0x18003523e  lea     rcx, [rdi+8]
0x180035242  test    rcx, rcx
0x180035245  jz      short loc_1800352BB
0x180035247  mov     eax, [rax]
0x180035249  mov     [rcx], eax
0x18003524b  lea     rdx, [rdi+10h]
0x18003524f  lea     rcx, [rsi+10h]
0x180035253  call    FwppDeepCopyToVerIndependent_UINT64
0x180035258  mov     rbx, rax
0x18003525b  test    rax, rax
0x18003525e  jz      short loc_18003527C
0x180035260  mov     rcx, rdi; pSidAttrArray
0x180035263  call    FeFreeGroupsCallback
0x180035268  test    rbx, rbx
0x18003526b  jz      short loc_18003527C
0x18003526d  lea     rdx, aFwppdeepcopyto_23; "FwppDeepCopyToVerIndependent_IPSEC_TOKE"...
0x180035274  mov     rcx, rbx
0x180035277  call    WfpReportError
0x18003527c  mov     rsi, [rsp+28h+arg_8]
0x180035281  mov     rax, rbx
0x180035284  mov     rbx, [rsp+28h+arg_0]
0x180035289  add     rsp, 20h
0x18003528d  pop     rdi
0x18003528e  retn
0x180035290  mov     r8d, 0C022001Ch
0x180035296  lea     rdx, aFwppdeepcopyto_14; "FwppDeepCopyToVerIndependent_IPSEC_TOKE"...
0x18003529d  call    WfpReportSysErrorAsNtStatus
0x1800352a2  mov     rbx, rax
0x1800352a5  test    rax, rax
0x1800352a8  jz      short loc_180035235
0x1800352aa  lea     rdx, aFwppdeepcopyto_14; "FwppDeepCopyToVerIndependent_IPSEC_TOKE"...
0x1800352b1  mov     rcx, rax
0x1800352b4  call    WfpReportError
0x1800352b9  jmp     short loc_180035260
0x1800352bb  mov     r8d, 0C022001Ch
0x1800352c1  lea     rdx, aFwppdeepcopyto_115; "FwppDeepCopyToVerIndependent_IPSEC_TOKE"...
0x1800352c8  call    WfpReportSysErrorAsNtStatus
0x1800352cd  mov     rbx, rax
0x1800352d0  test    rax, rax
0x1800352d3  jz      loc_18003524B
0x1800352d9  lea     rdx, aFwppdeepcopyto_115; "FwppDeepCopyToVerIndependent_IPSEC_TOKE"...
0x1800352e0  jmp     short loc_1800352B1
0x1800352e2  mov     r8d, 0C022001Ch
0x1800352e8  lea     rdx, aFwppdeepcopyto_23; "FwppDeepCopyToVerIndependent_IPSEC_TOKE"...
0x1800352ef  call    WfpReportSysErrorAsNtStatus
0x1800352f4  jmp     loc_180035258
```
