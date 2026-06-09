# FwppDeepCopyFromVerIndependent_IKEEXT_PROPOSAL0

- ea: `0x18002efc8`
- end: `0x18002f0c0`
- name: `FwppDeepCopyFromVerIndependent_IKEEXT_PROPOSAL0`
- size: `248`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024d68`
- `0x18002f184`
- `0x18002f2d8`

## callees

- `0x180007e38`
- `0x18000d870`
- `0x180011500`
- `0x1800120e0`
- `0x18002da74`
- `0x18002e360`
- `0x18002efc8`

## string_xrefs

- `0x18002f087`: `FwppDeepCopyFromVerIndependent_IKEEXT_DH_GROUP`
- `0x18002f09b`: `FwppDeepCopyFromVerIndependent_IKEEXT_DH_GROUP`
- `0x18002f05e`: `FwppDeepCopyFromVerIndependent_IKEEXT_PROPOSAL0`
- `0x18002f0b2`: `FwppDeepCopyFromVerIndependent_IKEEXT_PROPOSAL0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyFromVerIndependent_IKEEXT_PROPOSAL0(__int64 a1, struct _SID_AND_ATTRIBUTES *a2)
{
  __int64 v4; // rbx
  _DWORD *v5; // rcx
  __int64 v6; // rax
  __int64 v8; // rax

  if ( !a1 || !a2 )
  {
    v6 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyFromVerIndependent_IKEEXT_PROPOSAL0", 3223453724LL);
LABEL_10:
    v4 = v6;
    if ( !v6 )
      return v4;
    goto LABEL_11;
  }
  v4 = FwppDeepCopyFromVerIndependent_IKEEXT_CIPHER_ALGORITHM0();
  if ( !v4 )
  {
    v4 = FwppDeepCopyFromVerIndependent_IKEEXT_INTEGRITY_ALGORITHM0(a1 + 12, &a2->Attributes + 1);
    if ( !v4 )
    {
      v4 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 16, &a2[1]);
      if ( !v4 )
      {
        if ( a1 != -20 )
        {
          v5 = (_DWORD *)&a2[1].Sid + 1;
          if ( a2 != (struct _SID_AND_ATTRIBUTES *)-20LL )
          {
            *v5 = *(_DWORD *)(a1 + 20);
LABEL_9:
            v6 = FwppDeepCopyFromVerIndependent_UINT32(a1 + 24, &a2[1].Attributes);
            goto LABEL_10;
          }
        }
        v8 = WfpReportSysErrorAsNtStatus(v5, "FwppDeepCopyFromVerIndependent_IKEEXT_DH_GROUP", 3223453724LL);
        v4 = v8;
        if ( !v8 )
          goto LABEL_9;
        WfpReportError(v8, "FwppDeepCopyFromVerIndependent_IKEEXT_DH_GROUP");
      }
    }
  }
LABEL_11:
  FeFreeGroupsCallback(a2);
  if ( v4 )
    WfpReportError(v4, "FwppDeepCopyFromVerIndependent_IKEEXT_PROPOSAL0");
  return v4;
}

```

## disassembly

```asm
0x18002efc8  mov     [rsp+arg_0], rbx
0x18002efcd  mov     [rsp+arg_8], rsi
0x18002efd2  push    rdi
0x18002efd3  sub     rsp, 20h
0x18002efd7  mov     rdi, rdx
0x18002efda  mov     rsi, rcx
0x18002efdd  test    rcx, rcx
0x18002efe0  jz      loc_18002F0AC
0x18002efe6  test    rdx, rdx
0x18002efe9  jz      loc_18002F0AC
0x18002efef  call    FwppDeepCopyFromVerIndependent_IKEEXT_CIPHER_ALGORITHM0
0x18002eff4  mov     rbx, rax
0x18002eff7  test    rax, rax
0x18002effa  jnz     short loc_18002F051
0x18002effc  lea     rdx, [rdi+0Ch]
0x18002f000  lea     rcx, [rsi+0Ch]
0x18002f004  call    FwppDeepCopyFromVerIndependent_IKEEXT_INTEGRITY_ALGORITHM0
0x18002f009  mov     rbx, rax
0x18002f00c  test    rax, rax
0x18002f00f  jnz     short loc_18002F051
0x18002f011  lea     rdx, [rdi+10h]
0x18002f015  lea     rcx, [rsi+10h]
0x18002f019  call    FwppDeepCopyFromVerIndependent_UINT32
0x18002f01e  mov     rbx, rax
0x18002f021  test    rax, rax
0x18002f024  jnz     short loc_18002F051
0x18002f026  lea     rax, [rsi+14h]
0x18002f02a  test    rax, rax
0x18002f02d  jz      short loc_18002F081
0x18002f02f  lea     rcx, [rdi+14h]
0x18002f033  test    rcx, rcx
0x18002f036  jz      short loc_18002F081
0x18002f038  mov     eax, [rax]
0x18002f03a  mov     [rcx], eax
0x18002f03c  lea     rdx, [rdi+18h]
0x18002f040  lea     rcx, [rsi+18h]
0x18002f044  call    FwppDeepCopyFromVerIndependent_UINT32
0x18002f049  mov     rbx, rax
0x18002f04c  test    rax, rax
0x18002f04f  jz      short loc_18002F06D
0x18002f051  mov     rcx, rdi; pSidAttrArray
0x18002f054  call    FeFreeGroupsCallback
0x18002f059  test    rbx, rbx
0x18002f05c  jz      short loc_18002F06D
0x18002f05e  lea     rdx, aFwppdeepcopyfr_135; "FwppDeepCopyFromVerIndependent_IKEEXT_P"...
0x18002f065  mov     rcx, rbx
0x18002f068  call    WfpReportError
0x18002f06d  mov     rsi, [rsp+28h+arg_8]
0x18002f072  mov     rax, rbx
0x18002f075  mov     rbx, [rsp+28h+arg_0]
0x18002f07a  add     rsp, 20h
0x18002f07e  pop     rdi
0x18002f07f  retn
0x18002f081  mov     r8d, 0C022001Ch
0x18002f087  lea     rdx, aFwppdeepcopyfr_63; "FwppDeepCopyFromVerIndependent_IKEEXT_D"...
0x18002f08e  call    WfpReportSysErrorAsNtStatus
0x18002f093  mov     rbx, rax
0x18002f096  test    rax, rax
0x18002f099  jz      short loc_18002F03C
0x18002f09b  lea     rdx, aFwppdeepcopyfr_63; "FwppDeepCopyFromVerIndependent_IKEEXT_D"...
0x18002f0a2  mov     rcx, rax
0x18002f0a5  call    WfpReportError
0x18002f0aa  jmp     short loc_18002F051
0x18002f0ac  mov     r8d, 0C022001Ch
0x18002f0b2  lea     rdx, aFwppdeepcopyfr_135; "FwppDeepCopyFromVerIndependent_IKEEXT_P"...
0x18002f0b9  call    WfpReportSysErrorAsNtStatus
0x18002f0be  jmp     short loc_18002F049
```
