# FwppDeepCopyToVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1

- ea: `0x180033ef0`
- end: `0x180033fa9`
- name: `FwppDeepCopyToVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180032e5c`
- `0x180032f4c`

## callees

- `0x180006acc`
- `0x180007e38`
- `0x180011500`
- `0x180033ef0`
- `0x180036b80`

## string_xrefs

- `0x180033f3a`: `FwppDeepCopyToVerIndependent_IKEEXT_PSK_FLAGS`
- `0x180033f4e`: `FwppDeepCopyToVerIndependent_IKEEXT_PSK_FLAGS`
- `0x180033f65`: `FwppDeepCopyToVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1`
- `0x180033f86`: `FwppDeepCopyToVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyToVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1(__int64 a1, __int64 a2)
{
  _DWORD *v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rax

  if ( a1 && a2 )
  {
    v5 = FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB(a1, a2);
    if ( !v5 )
    {
      if ( a1 != -16 )
      {
        v4 = (_DWORD *)(a2 + 16);
        if ( a2 != -16 )
        {
          *v4 = *(_DWORD *)(a1 + 16);
          return v5;
        }
      }
      v6 = WfpReportSysErrorAsNtStatus(v4, "FwppDeepCopyToVerIndependent_IKEEXT_PSK_FLAGS", 3223453724LL);
      v5 = v6;
      if ( !v6 )
        return v5;
      WfpReportError(v6, "FwppDeepCopyToVerIndependent_IKEEXT_PSK_FLAGS");
    }
  }
  else
  {
    v5 = WfpReportSysErrorAsNtStatus(
           a1,
           "FwppDeepCopyToVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1",
           3223453724LL);
    if ( !v5 )
      return v5;
  }
  FwppDeepFreeContentsOnly_IKEEXT_PRESHARED_KEY_AUTHENTICATION0(a2);
  if ( v5 )
    WfpReportError(v5, "FwppDeepCopyToVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1");
  return v5;
}

```

## disassembly

```asm
0x180033ef0  mov     [rsp+arg_0], rbx
0x180033ef5  mov     [rsp+arg_8], rsi
0x180033efa  push    rdi
0x180033efb  sub     rsp, 20h
0x180033eff  mov     rdi, rdx
0x180033f02  mov     rsi, rcx
0x180033f05  test    rcx, rcx
0x180033f08  jz      short loc_180033F5F
0x180033f0a  test    rdx, rdx
0x180033f0d  jz      short loc_180033F5F
0x180033f0f  call    FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x180033f14  mov     rbx, rax
0x180033f17  test    rax, rax
0x180033f1a  jnz     short loc_180033F79
0x180033f1c  lea     rax, [rsi+10h]
0x180033f20  test    rax, rax
0x180033f23  jz      short loc_180033F34
0x180033f25  lea     rcx, [rdi+10h]
0x180033f29  test    rcx, rcx
0x180033f2c  jz      short loc_180033F34
0x180033f2e  mov     eax, [rax]
0x180033f30  mov     [rcx], eax
0x180033f32  jmp     short loc_180033F95
0x180033f34  mov     r8d, 0C022001Ch
0x180033f3a  lea     rdx, aFwppdeepcopyto_40; "FwppDeepCopyToVerIndependent_IKEEXT_PSK"...
0x180033f41  call    WfpReportSysErrorAsNtStatus
0x180033f46  mov     rbx, rax
0x180033f49  test    rax, rax
0x180033f4c  jz      short loc_180033F95
0x180033f4e  lea     rdx, aFwppdeepcopyto_40; "FwppDeepCopyToVerIndependent_IKEEXT_PSK"...
0x180033f55  mov     rcx, rax
0x180033f58  call    WfpReportError
0x180033f5d  jmp     short loc_180033F79
0x180033f5f  mov     r8d, 0C022001Ch
0x180033f65  lea     rdx, aFwppdeepcopyto_77; "FwppDeepCopyToVerIndependent_IKEEXT_PRE"...
0x180033f6c  call    WfpReportSysErrorAsNtStatus
0x180033f71  mov     rbx, rax
0x180033f74  test    rax, rax
0x180033f77  jz      short loc_180033F95
0x180033f79  mov     rcx, rdi
0x180033f7c  call    FwppDeepFreeContentsOnly_IKEEXT_PRESHARED_KEY_AUTHENTICATION0
0x180033f81  test    rbx, rbx
0x180033f84  jz      short loc_180033F95
0x180033f86  lea     rdx, aFwppdeepcopyto_77; "FwppDeepCopyToVerIndependent_IKEEXT_PRE"...
0x180033f8d  mov     rcx, rbx
0x180033f90  call    WfpReportError
0x180033f95  mov     rsi, [rsp+28h+arg_8]
0x180033f9a  mov     rax, rbx
0x180033f9d  mov     rbx, [rsp+28h+arg_0]
0x180033fa2  add     rsp, 20h
0x180033fa6  pop     rdi
0x180033fa7  retn
```
