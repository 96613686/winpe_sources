# FwppDeepCopyFromVerIndependent_IKEEXT_CERTIFICATE_AUTHENTICATION2

- ea: `0x18002d4dc`
- end: `0x18002d61f`
- name: `FwppDeepCopyFromVerIndependent_IKEEXT_CERTIFICATE_AUTHENTICATION2`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002d348`

## callees

- `0x180006acc`
- `0x180007e38`
- `0x180011500`
- `0x180024a74`
- `0x18002d4dc`
- `0x18002d860`
- `0x180036a78`

## string_xrefs

- `0x18002d5e6`: `FwppDeepCopyFromVerIndependent_IKEEXT_CERT_AUTH_FLAGS`
- `0x18002d5fa`: `FwppDeepCopyFromVerIndependent_IKEEXT_CERT_AUTH_FLAGS`
- `0x18002d5c3`: `FwppDeepCopyFromVerIndependent_IKEEXT_CERTIFICATE_AUTHENTICATION2`
- `0x18002d611`: `FwppDeepCopyFromVerIndependent_IKEEXT_CERTIFICATE_AUTHENTICATION2`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_IKEEXT_CERTIFICATE_AUTHENTICATION2(__int64 a1, _DWORD *a2)
{
  __int64 v4; // rdi
  __int64 v5; // rcx
  int v6; // ecx
  unsigned __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v10; // rax

  if ( !a1 || !a2 )
  {
    v8 = WfpReportSysErrorAsNtStatus(
           a1,
           "FwppDeepCopyFromVerIndependent_IKEEXT_CERTIFICATE_AUTHENTICATION2",
           3223453724LL);
LABEL_19:
    v4 = v8;
    if ( !v8 )
      return v4;
    goto LABEL_20;
  }
  v4 = ((__int64 (*)(void))FwppDeepCopyFromVerIndependent_IKEEXT_CERT_CONFIG_TYPE)();
  if ( !v4 )
  {
    if ( !*(_DWORD *)a1 || (unsigned int)(*(_DWORD *)a1 - 1) <= 1 )
    {
      v5 = *(_QWORD *)(a1 + 16);
      if ( v5 )
      {
        v4 = FwppArrayAllocAndDeepCopyFromVerIndependent_IKEEXT_CERTIFICATE_CRITERIA0(
               v5,
               *(unsigned int *)(a1 + 8),
               a2 + 4);
        if ( v4 )
          goto LABEL_20;
        a2[2] = *(_DWORD *)(a1 + 8);
      }
    }
    v4 = FwppDeepCopyFromVerIndependent_IKEEXT_CERT_CONFIG_TYPE(a1 + 24, a2 + 6);
    if ( !v4 )
    {
      v6 = *(_DWORD *)(a1 + 24);
      if ( !v6 || (v7 = (unsigned int)(v6 - 1), (unsigned int)v7 <= 1) )
      {
        v7 = *(_QWORD *)(a1 + 40);
        if ( v7 )
        {
          v4 = FwppArrayAllocAndDeepCopyFromVerIndependent_IKEEXT_CERTIFICATE_CRITERIA0(
                 v7,
                 *(unsigned int *)(a1 + 32),
                 a2 + 10);
          if ( v4 )
            goto LABEL_20;
          a2[8] = *(_DWORD *)(a1 + 32);
        }
      }
      if ( a1 != -48 )
      {
        v7 = (unsigned __int64)(a2 + 12);
        if ( a2 != (_DWORD *)-48LL )
        {
          *(_DWORD *)v7 = *(_DWORD *)(a1 + 48);
LABEL_18:
          v8 = FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB(a1 + 56, a2 + 14);
          goto LABEL_19;
        }
      }
      v10 = WfpReportSysErrorAsNtStatus(v7, "FwppDeepCopyFromVerIndependent_IKEEXT_CERT_AUTH_FLAGS", 3223453724LL);
      v4 = v10;
      if ( !v10 )
        goto LABEL_18;
      WfpReportError(v10, "FwppDeepCopyFromVerIndependent_IKEEXT_CERT_AUTH_FLAGS");
    }
  }
LABEL_20:
  FwppDeepFreeContentsOnly_IKEEXT_CERTIFICATE_AUTHENTICATION2(a2);
  if ( v4 )
    WfpReportError(v4, "FwppDeepCopyFromVerIndependent_IKEEXT_CERTIFICATE_AUTHENTICATION2");
  return v4;
}

```

## disassembly

```asm
0x18002d4dc  push    rbx
0x18002d4de  push    rsi
0x18002d4df  push    rdi
0x18002d4e0  push    r14
0x18002d4e2  sub     rsp, 28h
0x18002d4e6  mov     rsi, rdx
0x18002d4e9  mov     rbx, rcx
0x18002d4ec  test    rcx, rcx
0x18002d4ef  jz      loc_18002D60B
0x18002d4f5  test    rdx, rdx
0x18002d4f8  jz      loc_18002D60B
0x18002d4fe  call    FwppDeepCopyFromVerIndependent_IKEEXT_CERT_CONFIG_TYPE
0x18002d503  mov     rdi, rax
0x18002d506  test    rax, rax
0x18002d509  jnz     loc_18002D5B6
0x18002d50f  mov     ecx, [rbx]
0x18002d511  test    ecx, ecx
0x18002d513  jz      short loc_18002D51F
0x18002d515  sub     ecx, 1
0x18002d518  jz      short loc_18002D51F
0x18002d51a  cmp     ecx, 1
0x18002d51d  jnz     short loc_18002D542
0x18002d51f  mov     rcx, [rbx+10h]
0x18002d523  test    rcx, rcx
0x18002d526  jz      short loc_18002D542
0x18002d528  mov     edx, [rbx+8]
0x18002d52b  lea     r8, [rsi+10h]
0x18002d52f  call    FwppArrayAllocAndDeepCopyFromVerIndependent_IKEEXT_CERTIFICATE_CRITERIA0
0x18002d534  mov     rdi, rax
0x18002d537  test    rax, rax
0x18002d53a  jnz     short loc_18002D5B6
0x18002d53c  mov     eax, [rbx+8]
0x18002d53f  mov     [rsi+8], eax
0x18002d542  lea     rdx, [rsi+18h]
0x18002d546  lea     rcx, [rbx+18h]
0x18002d54a  call    FwppDeepCopyFromVerIndependent_IKEEXT_CERT_CONFIG_TYPE
0x18002d54f  mov     rdi, rax
0x18002d552  test    rax, rax
0x18002d555  jnz     short loc_18002D5B6
0x18002d557  mov     ecx, [rbx+18h]
0x18002d55a  test    ecx, ecx
0x18002d55c  jz      short loc_18002D568
0x18002d55e  sub     ecx, 1
0x18002d561  jz      short loc_18002D568
0x18002d563  cmp     ecx, 1
0x18002d566  jnz     short loc_18002D58B
0x18002d568  mov     rcx, [rbx+28h]
0x18002d56c  test    rcx, rcx
0x18002d56f  jz      short loc_18002D58B
0x18002d571  mov     edx, [rbx+20h]
0x18002d574  lea     r8, [rsi+28h]
0x18002d578  call    FwppArrayAllocAndDeepCopyFromVerIndependent_IKEEXT_CERTIFICATE_CRITERIA0
0x18002d57d  mov     rdi, rax
0x18002d580  test    rax, rax
0x18002d583  jnz     short loc_18002D5B6
0x18002d585  mov     eax, [rbx+20h]
0x18002d588  mov     [rsi+20h], eax
0x18002d58b  lea     rax, [rbx+30h]
0x18002d58f  test    rax, rax
0x18002d592  jz      short loc_18002D5E0
0x18002d594  lea     rcx, [rsi+30h]
0x18002d598  test    rcx, rcx
0x18002d59b  jz      short loc_18002D5E0
0x18002d59d  mov     eax, [rax]
0x18002d59f  mov     [rcx], eax
0x18002d5a1  lea     rdx, [rsi+38h]
0x18002d5a5  lea     rcx, [rbx+38h]
0x18002d5a9  call    FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x18002d5ae  mov     rdi, rax
0x18002d5b1  test    rax, rax
0x18002d5b4  jz      short loc_18002D5D2
0x18002d5b6  mov     rcx, rsi
0x18002d5b9  call    FwppDeepFreeContentsOnly_IKEEXT_CERTIFICATE_AUTHENTICATION2
0x18002d5be  test    rdi, rdi
0x18002d5c1  jz      short loc_18002D5D2
0x18002d5c3  lea     rdx, aFwppdeepcopyfr_74; "FwppDeepCopyFromVerIndependent_IKEEXT_C"...
0x18002d5ca  mov     rcx, rdi
0x18002d5cd  call    WfpReportError
0x18002d5d2  mov     rax, rdi
0x18002d5d5  add     rsp, 28h
0x18002d5d9  pop     r14
0x18002d5db  pop     rdi
0x18002d5dc  pop     rsi
0x18002d5dd  pop     rbx
0x18002d5de  retn
0x18002d5e0  mov     r8d, 0C022001Ch
0x18002d5e6  lea     rdx, aFwppdeepcopyfr_37; "FwppDeepCopyFromVerIndependent_IKEEXT_C"...
0x18002d5ed  call    WfpReportSysErrorAsNtStatus
0x18002d5f2  mov     rdi, rax
0x18002d5f5  test    rax, rax
0x18002d5f8  jz      short loc_18002D5A1
0x18002d5fa  lea     rdx, aFwppdeepcopyfr_37; "FwppDeepCopyFromVerIndependent_IKEEXT_C"...
0x18002d601  mov     rcx, rax
0x18002d604  call    WfpReportError
0x18002d609  jmp     short loc_18002D5B6
0x18002d60b  mov     r8d, 0C022001Ch
0x18002d611  lea     rdx, aFwppdeepcopyfr_74; "FwppDeepCopyFromVerIndependent_IKEEXT_C"...
0x18002d618  call    WfpReportSysErrorAsNtStatus
0x18002d61d  jmp     short loc_18002D5AE
```
