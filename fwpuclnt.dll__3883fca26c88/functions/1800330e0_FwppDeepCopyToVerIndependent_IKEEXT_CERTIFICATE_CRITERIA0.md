# FwppDeepCopyToVerIndependent_IKEEXT_CERTIFICATE_CRITERIA0

- ea: `0x1800330e0`
- end: `0x180033259`
- name: `FwppDeepCopyToVerIndependent_IKEEXT_CERTIFICATE_CRITERIA0`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180011680`

## callees

- `0x180006acc`
- `0x180006e40`
- `0x180007e38`
- `0x180011060`
- `0x180011500`
- `0x1800330e0`
- `0x1800332b4`
- `0x180033354`
- `0x180033404`
- `0x180037744`
- `0x180037760`

## string_xrefs

- `0x180033223`: `FwppAllocAndDeepCopyToVerIndependent_IKEEXT_CERT_EKUS0`
- `0x18003323c`: `FwppAllocAndDeepCopyToVerIndependent_IKEEXT_CERT_NAME0`
- `0x1800331fb`: `FwppDeepCopyToVerIndependent_IKEEXT_CERTIFICATE_CRITERIA0`
- `0x18003324b`: `FwppDeepCopyToVerIndependent_IKEEXT_CERTIFICATE_CRITERIA0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyToVerIndependent_IKEEXT_CERTIFICATE_CRITERIA0(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  __int64 v5; // r15
  __int64 v6; // r15
  __int64 v7; // rax
  const char *v9; // rdx

  if ( !a1 || !a2 )
  {
    v7 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyToVerIndependent_IKEEXT_CERTIFICATE_CRITERIA0", 3223453724LL);
LABEL_16:
    v4 = v7;
    if ( !v7 )
      return v4;
    goto LABEL_17;
  }
  v4 = FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB(a1, a2);
  if ( !v4 )
  {
    v4 = FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB(a1 + 16, a2 + 16);
    if ( !v4 )
    {
      v5 = *(_QWORD *)(a1 + 32);
      if ( v5 && a2 != -32 )
      {
        v4 = WfpPoolAllocNonPaged(0x10u);
        if ( v4 || (MEMORY[0] = 0, (v4 = FwppDeepCopyToVerIndependent_IKEEXT_CERT_EKUS0(v5, 0)) != 0) )
        {
          FwppDeepFree_IKEEXT_CERT_EKUS0(0);
          v9 = "FwppAllocAndDeepCopyToVerIndependent_IKEEXT_CERT_EKUS0";
LABEL_21:
          WfpReportError(v4, v9);
          goto LABEL_17;
        }
        *(_QWORD *)(a2 + 32) = 0;
      }
      v6 = *(_QWORD *)(a1 + 40);
      if ( !v6 || a2 == -40 )
        goto LABEL_15;
      v4 = WfpPoolAllocNonPaged(0x10u);
      if ( !v4 )
      {
        MEMORY[0] = 0;
        v4 = FwppDeepCopyToVerIndependent_IKEEXT_CERT_NAME0(v6, 0);
        if ( !v4 )
        {
          *(_QWORD *)(a2 + 40) = 0;
LABEL_15:
          v7 = FwppDeepCopyToVerIndependent_IKEEXT_CERT_FLAGS(a1 + 48, a2 + 48);
          goto LABEL_16;
        }
      }
      FwppDeepFree_IPSEC_AUTH_TRANSFORM0(0);
      v9 = "FwppAllocAndDeepCopyToVerIndependent_IKEEXT_CERT_NAME0";
      goto LABEL_21;
    }
  }
LABEL_17:
  FwppDeepFreeContentsOnly_IKEEXT_CERTIFICATE_CRITERIA0(a2);
  if ( v4 )
    WfpReportError(v4, "FwppDeepCopyToVerIndependent_IKEEXT_CERTIFICATE_CRITERIA0");
  return v4;
}

```

## disassembly

```asm
0x1800330e0  push    rbx
0x1800330e2  push    rbp
0x1800330e3  push    rsi
0x1800330e4  push    rdi
0x1800330e5  push    r14
0x1800330e7  push    r15
0x1800330e9  sub     rsp, 28h
0x1800330ed  mov     rdi, rdx
0x1800330f0  mov     rsi, rcx
0x1800330f3  test    rcx, rcx
0x1800330f6  jz      loc_180033245
0x1800330fc  test    rdx, rdx
0x1800330ff  jz      loc_180033245
0x180033105  call    FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x18003310a  mov     rbx, rax
0x18003310d  test    rax, rax
0x180033110  jnz     loc_1800331EE
0x180033116  lea     rdx, [rdi+10h]
0x18003311a  lea     rcx, [rsi+10h]
0x18003311e  call    FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x180033123  mov     rbx, rax
0x180033126  test    rax, rax
0x180033129  jnz     loc_1800331EE
0x18003312f  mov     r15, [rsi+20h]
0x180033133  test    r15, r15
0x180033136  jz      short loc_180033185
0x180033138  lea     r14, [rdi+20h]
0x18003313c  mov     [rsp+58h+arg_0], rax
0x180033141  test    r14, r14
0x180033144  jz      short loc_180033185
0x180033146  lea     r8, [rsp+58h+arg_0]
0x18003314b  lea     ecx, [rax+10h]; dwBytes
0x18003314e  call    WfpPoolAllocNonPaged
0x180033153  mov     rbp, [rsp+58h+arg_0]
0x180033158  mov     rbx, rax
0x18003315b  test    rax, rax
0x18003315e  jnz     loc_18003321B
0x180033164  xorps   xmm0, xmm0
0x180033167  mov     rdx, rbp
0x18003316a  mov     rcx, r15
0x18003316d  movups  xmmword ptr [rbp+0], xmm0
0x180033171  call    FwppDeepCopyToVerIndependent_IKEEXT_CERT_EKUS0
0x180033176  mov     rbx, rax
0x180033179  test    rax, rax
0x18003317c  jnz     loc_18003321B
0x180033182  mov     [r14], rbp
0x180033185  mov     r15, [rsi+28h]
0x180033189  test    r15, r15
0x18003318c  jz      short loc_1800331D9
0x18003318e  lea     r14, [rdi+28h]
0x180033192  mov     [rsp+58h+arg_0], 0
0x18003319b  test    r14, r14
0x18003319e  jz      short loc_1800331D9
0x1800331a0  lea     r8, [rsp+58h+arg_0]
0x1800331a5  mov     ecx, 10h; dwBytes
0x1800331aa  call    WfpPoolAllocNonPaged
0x1800331af  mov     rbp, [rsp+58h+arg_0]
0x1800331b4  mov     rbx, rax
0x1800331b7  test    rax, rax
0x1800331ba  jnz     short loc_180033234
0x1800331bc  xorps   xmm0, xmm0
0x1800331bf  mov     rdx, rbp
0x1800331c2  mov     rcx, r15
0x1800331c5  movups  xmmword ptr [rbp+0], xmm0
0x1800331c9  call    FwppDeepCopyToVerIndependent_IKEEXT_CERT_NAME0
0x1800331ce  mov     rbx, rax
0x1800331d1  test    rax, rax
0x1800331d4  jnz     short loc_180033234
0x1800331d6  mov     [r14], rbp
0x1800331d9  lea     rdx, [rdi+30h]
0x1800331dd  lea     rcx, [rsi+30h]
0x1800331e1  call    FwppDeepCopyToVerIndependent_IKEEXT_CERT_FLAGS
0x1800331e6  mov     rbx, rax
0x1800331e9  test    rax, rax
0x1800331ec  jz      short loc_18003320A
0x1800331ee  mov     rcx, rdi
0x1800331f1  call    FwppDeepFreeContentsOnly_IKEEXT_CERTIFICATE_CRITERIA0
0x1800331f6  test    rbx, rbx
0x1800331f9  jz      short loc_18003320A
0x1800331fb  lea     rdx, aFwppdeepcopyto_34; "FwppDeepCopyToVerIndependent_IKEEXT_CER"...
0x180033202  mov     rcx, rbx
0x180033205  call    WfpReportError
0x18003320a  mov     rax, rbx
0x18003320d  add     rsp, 28h
0x180033211  pop     r15
0x180033213  pop     r14
0x180033215  pop     rdi
0x180033216  pop     rsi
0x180033217  pop     rbp
0x180033218  pop     rbx
0x180033219  retn
0x18003321b  mov     rcx, rbp
0x18003321e  call    FwppDeepFree_IKEEXT_CERT_EKUS0
0x180033223  lea     rdx, aFwppallocandde_26; "FwppAllocAndDeepCopyToVerIndependent_IK"...
0x18003322a  mov     rcx, rbx
0x18003322d  call    WfpReportError
0x180033232  jmp     short loc_1800331EE
0x180033234  mov     rcx, rbp
0x180033237  call    FwppDeepFree_IPSEC_AUTH_TRANSFORM0
0x18003323c  lea     rdx, aFwppallocandde_17; "FwppAllocAndDeepCopyToVerIndependent_IK"...
0x180033243  jmp     short loc_18003322A
0x180033245  mov     r8d, 0C022001Ch
0x18003324b  lea     rdx, aFwppdeepcopyto_34; "FwppDeepCopyToVerIndependent_IKEEXT_CER"...
0x180033252  call    WfpReportSysErrorAsNtStatus
0x180033257  jmp     short loc_1800331E6
```
