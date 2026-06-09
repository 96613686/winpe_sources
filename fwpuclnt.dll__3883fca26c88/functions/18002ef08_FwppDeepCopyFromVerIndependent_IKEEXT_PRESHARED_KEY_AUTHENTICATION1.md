# FwppDeepCopyFromVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1

- ea: `0x18002ef08`
- end: `0x18002efc1`
- name: `FwppDeepCopyFromVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1`
- size: `185`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180022798`
- `0x18002d258`
- `0x18002d348`

## callees

- `0x180006acc`
- `0x180007e38`
- `0x180011500`
- `0x18002ef08`
- `0x180036b80`

## string_xrefs

- `0x18002ef52`: `FwppDeepCopyFromVerIndependent_IKEEXT_PSK_FLAGS`
- `0x18002ef66`: `FwppDeepCopyFromVerIndependent_IKEEXT_PSK_FLAGS`
- `0x18002ef7d`: `FwppDeepCopyFromVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1`
- `0x18002ef9e`: `FwppDeepCopyFromVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1(__int64 a1, __int64 a2)
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
      v6 = WfpReportSysErrorAsNtStatus(v4, "FwppDeepCopyFromVerIndependent_IKEEXT_PSK_FLAGS", 3223453724LL);
      v5 = v6;
      if ( !v6 )
        return v5;
      WfpReportError(v6, "FwppDeepCopyFromVerIndependent_IKEEXT_PSK_FLAGS");
    }
  }
  else
  {
    v5 = WfpReportSysErrorAsNtStatus(
           a1,
           "FwppDeepCopyFromVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1",
           3223453724LL);
    if ( !v5 )
      return v5;
  }
  FwppDeepFreeContentsOnly_IKEEXT_PRESHARED_KEY_AUTHENTICATION0(a2);
  if ( v5 )
    WfpReportError(v5, "FwppDeepCopyFromVerIndependent_IKEEXT_PRESHARED_KEY_AUTHENTICATION1");
  return v5;
}

```

## disassembly

```asm
0x18002ef08  mov     [rsp+arg_0], rbx
0x18002ef0d  mov     [rsp+arg_8], rsi
0x18002ef12  push    rdi
0x18002ef13  sub     rsp, 20h
0x18002ef17  mov     rdi, rdx
0x18002ef1a  mov     rsi, rcx
0x18002ef1d  test    rcx, rcx
0x18002ef20  jz      short loc_18002EF77
0x18002ef22  test    rdx, rdx
0x18002ef25  jz      short loc_18002EF77
0x18002ef27  call    FwppDeepCopyToVerIndependent_FWP_BYTE_BLOB
0x18002ef2c  mov     rbx, rax
0x18002ef2f  test    rax, rax
0x18002ef32  jnz     short loc_18002EF91
0x18002ef34  lea     rax, [rsi+10h]
0x18002ef38  test    rax, rax
0x18002ef3b  jz      short loc_18002EF4C
0x18002ef3d  lea     rcx, [rdi+10h]
0x18002ef41  test    rcx, rcx
0x18002ef44  jz      short loc_18002EF4C
0x18002ef46  mov     eax, [rax]
0x18002ef48  mov     [rcx], eax
0x18002ef4a  jmp     short loc_18002EFAD
0x18002ef4c  mov     r8d, 0C022001Ch
0x18002ef52  lea     rdx, aFwppdeepcopyfr_148; "FwppDeepCopyFromVerIndependent_IKEEXT_P"...
0x18002ef59  call    WfpReportSysErrorAsNtStatus
0x18002ef5e  mov     rbx, rax
0x18002ef61  test    rax, rax
0x18002ef64  jz      short loc_18002EFAD
0x18002ef66  lea     rdx, aFwppdeepcopyfr_148; "FwppDeepCopyFromVerIndependent_IKEEXT_P"...
0x18002ef6d  mov     rcx, rax
0x18002ef70  call    WfpReportError
0x18002ef75  jmp     short loc_18002EF91
0x18002ef77  mov     r8d, 0C022001Ch
0x18002ef7d  lea     rdx, aFwppdeepcopyfr_82; "FwppDeepCopyFromVerIndependent_IKEEXT_P"...
0x18002ef84  call    WfpReportSysErrorAsNtStatus
0x18002ef89  mov     rbx, rax
0x18002ef8c  test    rax, rax
0x18002ef8f  jz      short loc_18002EFAD
0x18002ef91  mov     rcx, rdi
0x18002ef94  call    FwppDeepFreeContentsOnly_IKEEXT_PRESHARED_KEY_AUTHENTICATION0
0x18002ef99  test    rbx, rbx
0x18002ef9c  jz      short loc_18002EFAD
0x18002ef9e  lea     rdx, aFwppdeepcopyfr_82; "FwppDeepCopyFromVerIndependent_IKEEXT_P"...
0x18002efa5  mov     rcx, rbx
0x18002efa8  call    WfpReportError
0x18002efad  mov     rsi, [rsp+28h+arg_8]
0x18002efb2  mov     rax, rbx
0x18002efb5  mov     rbx, [rsp+28h+arg_0]
0x18002efba  add     rsp, 20h
0x18002efbe  pop     rdi
0x18002efbf  retn
```
