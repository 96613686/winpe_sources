# FwppDeepCopyToVerIndependent_IPSEC_SA0

- ea: `0x180034ba8`
- end: `0x180034d22`
- name: `FwppDeepCopyToVerIndependent_IPSEC_SA0`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180025b68`

## callees

- `0x180006e40`
- `0x180007e38`
- `0x180011500`
- `0x180023f10`
- `0x180023f9c`
- `0x180034ba8`
- `0x18003503c`
- `0x180035474`
- `0x180035d48`
- `0x180037118`
- `0x18003793c`

## string_xrefs

- `0x180034cc0`: `FwppAllocAndDeepCopyToVerIndependent_IPSEC_SA_CIPHER_INFORMATION0`
- `0x180034cdb`: `FwppDeepCopyToVerIndependent_IPSEC_SA0`
- `0x180034cfc`: `FwppDeepCopyToVerIndependent_IPSEC_SA0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyToVerIndependent_IPSEC_SA0(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rbp

  if ( !a1 || !a2 )
  {
    v4 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyToVerIndependent_IPSEC_SA0", 3223453724LL);
    goto LABEL_24;
  }
  v4 = FwppDeepCopyToVerIndependent_UINT32(a1, a2);
  if ( !v4 )
  {
    v4 = FwppDeepCopyToVerIndependent_IPSEC_TRANSFORM_TYPE(a1 + 4, a2 + 4);
    if ( !v4 )
    {
      if ( *(_DWORD *)(a1 + 4) == 1 || *(_DWORD *)(a1 + 4) == 2 )
        goto LABEL_10;
      if ( *(_DWORD *)(a1 + 4) != 3 )
      {
        if ( *(_DWORD *)(a1 + 4) == 4 )
        {
          v7 = *(_QWORD *)(a1 + 8);
          if ( !v7 )
            return v4;
          v6 = FwppAllocAndDeepCopyToVerIndependent_IPSEC_SA_AUTH_AND_CIPHER_INFORMATION0(v7, a2 + 8);
LABEL_12:
          v4 = v6;
          if ( !v6 )
            return v4;
          goto LABEL_25;
        }
        if ( *(_DWORD *)(a1 + 4) != 5 )
          return v4;
LABEL_10:
        v5 = *(_QWORD *)(a1 + 8);
        if ( !v5 )
          return v4;
        v6 = FwppAllocAndDeepCopyToVerIndependent_IPSEC_SA_AUTH_INFORMATION0(v5, a2 + 8);
        goto LABEL_12;
      }
      v8 = *(_QWORD *)(a1 + 8);
      if ( !v8 )
        return v4;
      if ( a2 != -8 )
      {
        v4 = WfpPoolAllocNonPaged(0x20u);
        if ( !v4 )
        {
          MEMORY[0] = 0;
          MEMORY[0x10] = 0;
          v4 = FwppDeepCopyToVerIndependent_IPSEC_SA_CIPHER_INFORMATION0(v8, 0);
          if ( !v4 )
          {
            *(_QWORD *)(a2 + 8) = 0;
            return v4;
          }
        }
        FwppDeepFree_IPSEC_SA_CIPHER_INFORMATION0(0);
        WfpReportError(v4, "FwppAllocAndDeepCopyToVerIndependent_IPSEC_SA_CIPHER_INFORMATION0");
        goto LABEL_25;
      }
      v4 = 0;
LABEL_24:
      if ( !v4 )
        return v4;
    }
  }
LABEL_25:
  FwppDeepFreeContentsOnly_IPSEC_SA0(a2);
  if ( v4 )
    WfpReportError(v4, "FwppDeepCopyToVerIndependent_IPSEC_SA0");
  return v4;
}

```

## disassembly

```asm
0x180034ba8  mov     [rsp+arg_8], rbx
0x180034bad  mov     [rsp+arg_10], rbp
0x180034bb2  push    rsi
0x180034bb3  push    rdi
0x180034bb4  push    r14
0x180034bb6  sub     rsp, 20h
0x180034bba  mov     rsi, rdx
0x180034bbd  mov     rdi, rcx
0x180034bc0  test    rcx, rcx
0x180034bc3  jz      loc_180034CD5
0x180034bc9  test    rdx, rdx
0x180034bcc  jz      loc_180034CD5
0x180034bd2  call    FwppDeepCopyToVerIndependent_UINT32
0x180034bd7  mov     rbx, rax
0x180034bda  test    rax, rax
0x180034bdd  jnz     loc_180034CEF
0x180034be3  lea     rdx, [rsi+4]
0x180034be7  lea     rcx, [rdi+4]
0x180034beb  call    FwppDeepCopyToVerIndependent_IPSEC_TRANSFORM_TYPE
0x180034bf0  mov     rbx, rax
0x180034bf3  test    rax, rax
0x180034bf6  jnz     loc_180034CEF
0x180034bfc  mov     ecx, [rdi+4]
0x180034bff  sub     ecx, 1
0x180034c02  jz      short loc_180034C1C
0x180034c04  sub     ecx, 1
0x180034c07  jz      short loc_180034C1C
0x180034c09  sub     ecx, 1
0x180034c0c  jz      short loc_180034C5B
0x180034c0e  sub     ecx, 1
0x180034c11  jz      short loc_180034C43
0x180034c13  cmp     ecx, 1
0x180034c16  jnz     loc_180034D0B
0x180034c1c  mov     rcx, [rdi+8]
0x180034c20  test    rcx, rcx
0x180034c23  jz      loc_180034D0B
0x180034c29  lea     rdx, [rsi+8]
0x180034c2d  call    FwppAllocAndDeepCopyToVerIndependent_IPSEC_SA_AUTH_INFORMATION0
0x180034c32  mov     rbx, rax
0x180034c35  test    rax, rax
0x180034c38  jnz     loc_180034CEF
0x180034c3e  jmp     loc_180034D0B
0x180034c43  mov     rcx, [rdi+8]
0x180034c47  test    rcx, rcx
0x180034c4a  jz      loc_180034D0B
0x180034c50  lea     rdx, [rsi+8]
0x180034c54  call    FwppAllocAndDeepCopyToVerIndependent_IPSEC_SA_AUTH_AND_CIPHER_INFORMATION0
0x180034c59  jmp     short loc_180034C32
0x180034c5b  mov     rbp, [rdi+8]
0x180034c5f  test    rbp, rbp
0x180034c62  jz      loc_180034D0B
0x180034c68  lea     r14, [rsi+8]
0x180034c6c  mov     [rsp+38h+arg_0], 0
0x180034c75  test    r14, r14
0x180034c78  jz      short loc_180034CD1
0x180034c7a  lea     r8, [rsp+38h+arg_0]
0x180034c7f  mov     ecx, 20h ; ' '; dwBytes
0x180034c84  call    WfpPoolAllocNonPaged
0x180034c89  mov     rdi, [rsp+38h+arg_0]
0x180034c8e  mov     rbx, rax
0x180034c91  test    rax, rax
0x180034c94  jnz     short loc_180034CB8
0x180034c96  xorps   xmm0, xmm0
0x180034c99  mov     rdx, rdi
0x180034c9c  movups  xmmword ptr [rdi], xmm0
0x180034c9f  mov     rcx, rbp
0x180034ca2  movups  xmmword ptr [rdi+10h], xmm0
0x180034ca6  call    FwppDeepCopyToVerIndependent_IPSEC_SA_CIPHER_INFORMATION0
0x180034cab  mov     rbx, rax
0x180034cae  test    rax, rax
0x180034cb1  jnz     short loc_180034CB8
0x180034cb3  mov     [r14], rdi
0x180034cb6  jmp     short loc_180034D0B
0x180034cb8  mov     rcx, rdi
0x180034cbb  call    FwppDeepFree_IPSEC_SA_CIPHER_INFORMATION0
0x180034cc0  lea     rdx, aFwppallocandde_75; "FwppAllocAndDeepCopyToVerIndependent_IP"...
0x180034cc7  mov     rcx, rbx
0x180034cca  call    WfpReportError
0x180034ccf  jmp     short loc_180034CEF
0x180034cd1  xor     ebx, ebx
0x180034cd3  jmp     short loc_180034CEA
0x180034cd5  mov     r8d, 0C022001Ch
0x180034cdb  lea     rdx, aFwppdeepcopyto_84; "FwppDeepCopyToVerIndependent_IPSEC_SA0"
0x180034ce2  call    WfpReportSysErrorAsNtStatus
0x180034ce7  mov     rbx, rax
0x180034cea  test    rbx, rbx
0x180034ced  jz      short loc_180034D0B
0x180034cef  mov     rcx, rsi
0x180034cf2  call    FwppDeepFreeContentsOnly_IPSEC_SA0
0x180034cf7  test    rbx, rbx
0x180034cfa  jz      short loc_180034D0B
0x180034cfc  lea     rdx, aFwppdeepcopyto_84; "FwppDeepCopyToVerIndependent_IPSEC_SA0"
0x180034d03  mov     rcx, rbx
0x180034d06  call    WfpReportError
0x180034d0b  mov     rbp, [rsp+38h+arg_10]
0x180034d10  mov     rax, rbx
0x180034d13  mov     rbx, [rsp+38h+arg_8]
0x180034d18  add     rsp, 20h
0x180034d1c  pop     r14
0x180034d1e  pop     rdi
0x180034d1f  pop     rsi
0x180034d20  retn
```
