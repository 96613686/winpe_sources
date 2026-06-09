# FwppDeepCopyFromVerIndependent_FWPM_FILTER0

- ea: `0x180029e74`
- end: `0x18002a08e`
- name: `FwppDeepCopyFromVerIndependent_FWPM_FILTER0`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180021190`

## callees

- `0x180006acc`
- `0x1800071a8`
- `0x180007e38`
- `0x180011500`
- `0x1800220b0`
- `0x180025630`
- `0x180029ba0`
- `0x180029dd8`
- `0x180029e74`
- `0x18002ce70`
- `0x18002d0d8`
- `0x180035f94`

## string_xrefs

- `0x180029fc0`: `FwppDeepCopyFromVerIndependent_FWPM_FILTER_FLAGS`
- `0x180029fd8`: `FwppDeepCopyFromVerIndependent_FWPM_FILTER_FLAGS`
- `0x180029ff4`: `FwppDeepCopyFromVerIndependent_FWPM_FILTER0`
- `0x18002a080`: `FwppDeepCopyFromVerIndependent_FWPM_FILTER0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_FWPM_FILTER0(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  _DWORD *v5; // rcx
  _DWORD *v6; // r14
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v14; // rcx
  __int64 v15; // rax

  if ( !a1 || !a2 )
  {
    v15 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyFromVerIndependent_FWPM_FILTER0", 3223453724LL);
LABEL_31:
    v4 = v15;
    if ( !v15 )
      return v4;
    goto LABEL_22;
  }
  v4 = ((__int64 (*)(void))FwppDeepCopyFromVerIndependent_GUID)();
  if ( !v4 )
  {
    v4 = FwppDeepCopyFromVerIndependent_FWPM_DISPLAY_DATA0(a1 + 16, a2 + 16);
    if ( !v4 )
    {
      v6 = (_DWORD *)(a1 + 32);
      if ( a1 == -32 || (v5 = (_DWORD *)(a2 + 32), a2 == -32) )
      {
        v12 = WfpReportSysErrorAsNtStatus(v5, "FwppDeepCopyFromVerIndependent_FWPM_FILTER_FLAGS", 3223453724LL);
        v4 = v12;
        if ( v12 )
        {
          WfpReportError(v12, "FwppDeepCopyFromVerIndependent_FWPM_FILTER_FLAGS");
          goto LABEL_22;
        }
      }
      else
      {
        *v5 = *v6;
      }
      v7 = *(_QWORD *)(a1 + 40);
      if ( v7 )
      {
        v4 = FwppAllocAndDeepCopyFromVerIndependent_GUID(v7, a2 + 40);
        if ( v4 )
          goto LABEL_22;
      }
      v4 = FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB(a1 + 48, a2 + 48);
      if ( v4 )
        goto LABEL_22;
      v4 = FwppDeepCopyFromVerIndependent_GUID(a1 + 64, a2 + 64);
      if ( v4 )
        goto LABEL_22;
      v4 = FwppDeepCopyFromVerIndependent_GUID(a1 + 80, a2 + 80);
      if ( v4 )
        goto LABEL_22;
      v4 = FwppDeepCopyFromVerIndependent_FWP_VALUE0(a1 + 96, a2 + 96);
      if ( v4 )
        goto LABEL_22;
      v8 = *(_QWORD *)(a1 + 120);
      if ( v8 )
      {
        v4 = FwppArrayAllocAndDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0(v8, *(unsigned int *)(a1 + 112), a2 + 120);
        if ( v4 )
          goto LABEL_22;
        *(_DWORD *)(a2 + 112) = *(_DWORD *)(a1 + 112);
      }
      v4 = FwppDeepCopyFromVerIndependent_FWPM_ACTION0(a1 + 128, a2 + 128);
      if ( !v4 )
      {
        v9 = a2 + 152;
        v10 = a1 + 152;
        v11 = (*(_BYTE *)v6 & 4) != 0
            ? FwppDeepCopyFromVerIndependent_GUID(v10, v9)
            : FwppDeepCopyFromVerIndependent_UINT64(v10, v9);
        v4 = v11;
        if ( !v11 )
        {
          v14 = *(_QWORD *)(a1 + 168);
          if ( !v14 || (v4 = FwppAllocAndDeepCopyFromVerIndependent_GUID(v14, a2 + 168)) == 0 )
          {
            v4 = FwppDeepCopyFromVerIndependent_UINT64(a1 + 176, a2 + 176);
            if ( !v4 )
            {
              v15 = FwppDeepCopyFromVerIndependent_FWP_VALUE0(a1 + 184, a2 + 184);
              goto LABEL_31;
            }
          }
        }
      }
    }
  }
LABEL_22:
  FwppDeepFreeContentsOnly_FWPM_FILTER0(a2);
  if ( v4 )
    WfpReportError(v4, "FwppDeepCopyFromVerIndependent_FWPM_FILTER0");
  return v4;
}

```

## disassembly

```asm
0x180029e74  push    rbx
0x180029e76  push    rsi
0x180029e77  push    rdi
0x180029e78  push    r14
0x180029e7a  sub     rsp, 28h
0x180029e7e  mov     rsi, rdx
0x180029e81  mov     rdi, rcx
0x180029e84  test    rcx, rcx
0x180029e87  jz      loc_18002A07A
0x180029e8d  test    rdx, rdx
0x180029e90  jz      loc_18002A07A
0x180029e96  call    FwppDeepCopyFromVerIndependent_GUID
0x180029e9b  mov     rbx, rax
0x180029e9e  test    rax, rax
0x180029ea1  jnz     loc_180029FE7
0x180029ea7  lea     rdx, [rsi+10h]
0x180029eab  lea     rcx, [rdi+10h]
0x180029eaf  call    FwppDeepCopyFromVerIndependent_FWPM_DISPLAY_DATA0
0x180029eb4  mov     rbx, rax
0x180029eb7  test    rax, rax
0x180029eba  jnz     loc_180029FE7
0x180029ec0  lea     r14, [rdi+20h]
0x180029ec4  test    r14, r14
0x180029ec7  jz      loc_180029FBA
0x180029ecd  lea     rcx, [rsi+20h]
0x180029ed1  test    rcx, rcx
0x180029ed4  jz      loc_180029FBA
0x180029eda  mov     eax, [r14]
0x180029edd  mov     [rcx], eax
0x180029edf  mov     rcx, [rdi+28h]
0x180029ee3  test    rcx, rcx
0x180029ee6  jz      short loc_180029EFD
0x180029ee8  lea     rdx, [rsi+28h]
0x180029eec  call    FwppAllocAndDeepCopyFromVerIndependent_GUID
0x180029ef1  mov     rbx, rax
0x180029ef4  test    rax, rax
0x180029ef7  jnz     loc_180029FE7
0x180029efd  lea     rdx, [rsi+30h]
0x180029f01  lea     rcx, [rdi+30h]
0x180029f05  call    FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x180029f0a  mov     rbx, rax
0x180029f0d  test    rax, rax
0x180029f10  jnz     loc_180029FE7
0x180029f16  lea     rdx, [rsi+40h]
0x180029f1a  lea     rcx, [rdi+40h]
0x180029f1e  call    FwppDeepCopyFromVerIndependent_GUID
0x180029f23  mov     rbx, rax
0x180029f26  test    rax, rax
0x180029f29  jnz     loc_180029FE7
0x180029f2f  lea     rdx, [rsi+50h]
0x180029f33  lea     rcx, [rdi+50h]
0x180029f37  call    FwppDeepCopyFromVerIndependent_GUID
0x180029f3c  mov     rbx, rax
0x180029f3f  test    rax, rax
0x180029f42  jnz     loc_180029FE7
0x180029f48  lea     rdx, [rsi+60h]
0x180029f4c  lea     rcx, [rdi+60h]
0x180029f50  call    FwppDeepCopyFromVerIndependent_FWP_VALUE0
0x180029f55  mov     rbx, rax
0x180029f58  test    rax, rax
0x180029f5b  jnz     loc_180029FE7
0x180029f61  mov     rcx, [rdi+78h]
0x180029f65  test    rcx, rcx
0x180029f68  jz      short loc_180029F84
0x180029f6a  mov     edx, [rdi+70h]
0x180029f6d  lea     r8, [rsi+78h]
0x180029f71  call    FwppArrayAllocAndDeepCopyToVerIndependent_FWPM_FILTER_CONDITION0
0x180029f76  mov     rbx, rax
0x180029f79  test    rax, rax
0x180029f7c  jnz     short loc_180029FE7
0x180029f7e  mov     eax, [rdi+70h]
0x180029f81  mov     [rsi+70h], eax
0x180029f84  lea     rdx, [rsi+80h]
0x180029f8b  lea     rcx, [rdi+80h]
0x180029f92  call    FwppDeepCopyFromVerIndependent_FWPM_ACTION0
0x180029f97  mov     rbx, rax
0x180029f9a  test    rax, rax
0x180029f9d  jnz     short loc_180029FE7
0x180029f9f  test    byte ptr [r14], 4
0x180029fa3  lea     rdx, [rsi+98h]
0x180029faa  lea     rcx, [rdi+98h]
0x180029fb1  jz      short loc_18002A011
0x180029fb3  call    FwppDeepCopyFromVerIndependent_GUID
0x180029fb8  jmp     short loc_18002A016
0x180029fba  mov     r8d, 0C022001Ch
0x180029fc0  lea     rdx, aFwppdeepcopyfr_106; "FwppDeepCopyFromVerIndependent_FWPM_FIL"...
0x180029fc7  call    WfpReportSysErrorAsNtStatus
0x180029fcc  mov     rbx, rax
0x180029fcf  test    rax, rax
0x180029fd2  jz      loc_180029EDF
0x180029fd8  lea     rdx, aFwppdeepcopyfr_106; "FwppDeepCopyFromVerIndependent_FWPM_FIL"...
0x180029fdf  mov     rcx, rax
0x180029fe2  call    WfpReportError
0x180029fe7  mov     rcx, rsi
0x180029fea  call    FwppDeepFreeContentsOnly_FWPM_FILTER0
0x180029fef  test    rbx, rbx
0x180029ff2  jz      short loc_18002A003
0x180029ff4  lea     rdx, aFwppdeepcopyfr_116; "FwppDeepCopyFromVerIndependent_FWPM_FIL"...
0x180029ffb  mov     rcx, rbx
0x180029ffe  call    WfpReportError
0x18002a003  mov     rax, rbx
0x18002a006  add     rsp, 28h
0x18002a00a  pop     r14
0x18002a00c  pop     rdi
0x18002a00d  pop     rsi
0x18002a00e  pop     rbx
0x18002a00f  retn
0x18002a011  call    FwppDeepCopyFromVerIndependent_UINT64
0x18002a016  mov     rbx, rax
0x18002a019  test    rax, rax
0x18002a01c  jnz     short loc_180029FE7
0x18002a01e  mov     rcx, [rdi+0A8h]
0x18002a025  test    rcx, rcx
0x18002a028  jz      short loc_18002A03E
0x18002a02a  lea     rdx, [rsi+0A8h]
0x18002a031  call    FwppAllocAndDeepCopyFromVerIndependent_GUID
0x18002a036  mov     rbx, rax
0x18002a039  test    rax, rax
0x18002a03c  jnz     short loc_180029FE7
0x18002a03e  lea     rdx, [rsi+0B0h]
0x18002a045  lea     rcx, [rdi+0B0h]
0x18002a04c  call    FwppDeepCopyFromVerIndependent_UINT64
0x18002a051  mov     rbx, rax
0x18002a054  test    rax, rax
0x18002a057  jnz     short loc_180029FE7
0x18002a059  lea     rdx, [rsi+0B8h]
0x18002a060  lea     rcx, [rdi+0B8h]
0x18002a067  call    FwppDeepCopyFromVerIndependent_FWP_VALUE0
0x18002a06c  mov     rbx, rax
0x18002a06f  test    rax, rax
0x18002a072  jnz     loc_180029FE7
0x18002a078  jmp     short loc_18002A003
0x18002a07a  mov     r8d, 0C022001Ch
0x18002a080  lea     rdx, aFwppdeepcopyfr_116; "FwppDeepCopyFromVerIndependent_FWPM_FIL"...
0x18002a087  call    WfpReportSysErrorAsNtStatus
0x18002a08c  jmp     short loc_18002A06C
```
