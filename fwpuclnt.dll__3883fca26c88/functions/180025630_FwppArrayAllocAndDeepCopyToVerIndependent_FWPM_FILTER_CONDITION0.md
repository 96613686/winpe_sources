# FwppArrayAllocAndDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0

- ea: `0x180025630`
- end: `0x18002576b`
- name: `FwppArrayAllocAndDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0`
- size: `315`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180029e74`

## callees

- `0x180006e40`
- `0x180007e38`
- `0x1800114a4`
- `0x180011500`
- `0x18001346a`
- `0x180025630`
- `0x180026244`
- `0x18003231c`

## string_xrefs

- `0x1800256e9`: `FwppDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0`
- `0x180025701`: `FwppDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0`
- `0x180025724`: `FwppArrayAllocAndDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0`
- `0x180025747`: `FwppArrayAllocAndDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0`

## pseudocode

```c
__int64 __fastcall FwppArrayAllocAndDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0(
        __int64 a1,
        unsigned int a2,
        _QWORD *a3)
{
  char *v3; // rdi
  __int64 v4; // rsi
  __int64 v8; // rbx
  unsigned int v9; // edi
  size_t v10; // r8
  __int64 v11; // r8
  char *v12; // rdx
  __int64 v13; // rax
  size_t Size; // [rsp+50h] [rbp+8h] BYREF
  void *v16; // [rsp+68h] [rbp+20h]

  v3 = 0;
  v4 = 0;
  v16 = 0;
  LODWORD(Size) = 0;
  if ( !a1 || !a3 )
  {
    v8 = WfpReportSysErrorAsNtStatus(
           a1,
           "FwppArrayAllocAndDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0",
           3223453724LL);
    if ( !v8 )
      return v8;
    goto LABEL_17;
  }
  v8 = WfpUINT32Multiply(a2, 40, &Size);
  if ( v8 )
  {
LABEL_17:
    FwppArrayDeepFree_FWPM_FILTER_CONDITION0(v3, (unsigned int)v4);
    if ( v8 )
      WfpReportError(v8, "FwppArrayAllocAndDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0");
    return v8;
  }
  v9 = Size;
  v8 = WfpPoolAllocNonPaged((unsigned int)Size);
  if ( v8 )
  {
    v3 = (char *)v16;
    goto LABEL_17;
  }
  v10 = v9;
  v3 = (char *)v16;
  memset_0(v16, 0, v10);
  while ( (unsigned int)v4 < a2 )
  {
    v11 = a1 + 40 * v4;
    if ( v11 && (v12 = &v3[40 * v4]) != 0 )
    {
      *(_OWORD *)v12 = *(_OWORD *)v11;
      *((_DWORD *)v12 + 4) = *(_DWORD *)(v11 + 16);
      v13 = FwppDeepCopyToVerIndependent_FWP_CONDITION_VALUE0(v11 + 24, (__int64)(v12 + 24));
    }
    else
    {
      v13 = WfpReportSysErrorAsNtStatus(5 * v4, "FwppDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0", 3223453724LL);
    }
    v8 = v13;
    if ( v13 )
    {
      WfpReportError(v13, "FwppDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0");
      goto LABEL_17;
    }
    v4 = (unsigned int)(v4 + 1);
  }
  *a3 = v3;
  return v8;
}

```

## disassembly

```asm
0x180025630  mov     rax, rsp
0x180025633  mov     [rax+10h], rbx
0x180025637  push    rbp
0x180025638  push    rsi
0x180025639  push    rdi
0x18002563a  push    r14
0x18002563c  push    r15
0x18002563e  sub     rsp, 20h
0x180025642  xor     edi, edi
0x180025644  xor     esi, esi
0x180025646  mov     [rax+20h], rdi
0x18002564a  mov     r14, r8
0x18002564d  mov     [rax+8], edi
0x180025650  mov     ebp, edx
0x180025652  mov     r15, rcx
0x180025655  test    rcx, rcx
0x180025658  jz      loc_18002571E
0x18002565e  test    r8, r8
0x180025661  jz      loc_18002571E
0x180025667  lea     r8, [rax+8]
0x18002566b  mov     ecx, ebp
0x18002566d  lea     edx, [rdi+28h]
0x180025670  call    WfpUINT32Multiply
0x180025675  mov     rbx, rax
0x180025678  test    rax, rax
0x18002567b  jnz     loc_180025738
0x180025681  mov     edi, dword ptr [rsp+48h+Size]
0x180025685  lea     r8, [rsp+48h+arg_18]
0x18002568a  mov     ecx, edi; dwBytes
0x18002568c  call    WfpPoolAllocNonPaged
0x180025691  mov     rbx, rax
0x180025694  test    rax, rax
0x180025697  jnz     short loc_180025717
0x180025699  mov     r8d, edi; Size
0x18002569c  xor     edx, edx; Val
0x18002569e  mov     rdi, [rsp+48h+arg_18]
0x1800256a3  mov     rcx, rdi; void *
0x1800256a6  call    memset_0
0x1800256ab  cmp     esi, ebp
0x1800256ad  jnb     short loc_180025712
0x1800256af  lea     rcx, [rsi+rsi*4]
0x1800256b3  lea     r8, [r15+rcx*8]
0x1800256b7  test    r8, r8
0x1800256ba  jz      short loc_1800256E3
0x1800256bc  lea     rdx, [rdi+rcx*8]
0x1800256c0  test    rdx, rdx
0x1800256c3  jz      short loc_1800256E3
0x1800256c5  movups  xmm0, xmmword ptr [r8]
0x1800256c9  lea     rcx, [r8+18h]
0x1800256cd  movdqu  xmmword ptr [rdx], xmm0
0x1800256d1  mov     eax, [r8+10h]
0x1800256d5  mov     [rdx+10h], eax
0x1800256d8  add     rdx, 18h
0x1800256dc  call    FwppDeepCopyToVerIndependent_FWP_CONDITION_VALUE0
0x1800256e1  jmp     short loc_1800256F5
0x1800256e3  mov     r8d, 0C022001Ch
0x1800256e9  lea     rdx, aFwppdeepcopyto_28; "FwppDeepCopyToVerIndependent_FWPM_FILTE"...
0x1800256f0  call    WfpReportSysErrorAsNtStatus
0x1800256f5  mov     rbx, rax
0x1800256f8  test    rax, rax
0x1800256fb  jnz     short loc_180025701
0x1800256fd  inc     esi
0x1800256ff  jmp     short loc_1800256AB
0x180025701  lea     rdx, aFwppdeepcopyto_28; "FwppDeepCopyToVerIndependent_FWPM_FILTE"...
0x180025708  mov     rcx, rbx
0x18002570b  call    WfpReportError
0x180025710  jmp     short loc_180025738
0x180025712  mov     [r14], rdi
0x180025715  jmp     short loc_180025756
0x180025717  mov     rdi, [rsp+48h+arg_18]
0x18002571c  jmp     short loc_180025738
0x18002571e  mov     r8d, 0C022001Ch
0x180025724  lea     rdx, aFwpparrayalloc_5; "FwppArrayAllocAndDeepCopyToVerIndepende"...
0x18002572b  call    WfpReportSysErrorAsNtStatus
0x180025730  mov     rbx, rax
0x180025733  test    rax, rax
0x180025736  jz      short loc_180025756
0x180025738  mov     edx, esi
0x18002573a  mov     rcx, rdi
0x18002573d  call    FwppArrayDeepFree_FWPM_FILTER_CONDITION0
0x180025742  test    rbx, rbx
0x180025745  jz      short loc_180025756
0x180025747  lea     rdx, aFwpparrayalloc_5; "FwppArrayAllocAndDeepCopyToVerIndepende"...
0x18002574e  mov     rcx, rbx
0x180025751  call    WfpReportError
0x180025756  mov     rax, rbx
0x180025759  mov     rbx, [rsp+48h+arg_8]
0x18002575e  add     rsp, 20h
0x180025762  pop     r15
0x180025764  pop     r14
0x180025766  pop     rdi
0x180025767  pop     rsi
0x180025768  pop     rbp
0x180025769  retn
```
