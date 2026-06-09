# StSecpFindSecurityDescriptorPolicyElement

- ea: `0x140010cb0`
- end: `0x140010e17`
- name: `StSecpFindSecurityDescriptorPolicyElement`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140010890`

## callees

- `0x140010cb0`

## import_xrefs

- `ntoskrnl!FsRtlDissectName` at `0x140010d0c`
- `ntoskrnl!FsRtlDissectName` at `0x140010d2c`
- `ntoskrnl!FsRtlDissectName` at `0x140010da6`
- `ntoskrnl!FsRtlDissectName` at `0x140010dc7`
- `ntoskrnl!FsRtlDissectName` at `0x140010d0c`
- `ntoskrnl!FsRtlDissectName` at `0x140010d2c`
- `ntoskrnl!FsRtlDissectName` at `0x140010da6`
- `ntoskrnl!FsRtlDissectName` at `0x140010dc7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140010d64`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140010d64`

## pseudocode

```c
__int64 __fastcall StSecpFindSecurityDescriptorPolicyElement(UNICODE_STRING *a1)
{
  __int64 v1; // rbx
  LONG v3; // edi
  PWSTR Buffer; // rcx
  PWSTR v5; // rax
  UNICODE_STRING String2; // [rsp+20h] [rbp-58h] BYREF
  struct _UNICODE_STRING FirstName; // [rsp+30h] [rbp-48h] BYREF
  struct _UNICODE_STRING RemainingName; // [rsp+40h] [rbp-38h] BYREF
  struct _UNICODE_STRING v10; // [rsp+50h] [rbp-28h] BYREF
  UNICODE_STRING Path; // [rsp+60h] [rbp-18h] BYREF

  v1 = g_StSecSecurityDescriptorCacheListHead;
  FirstName = 0;
  RemainingName = 0;
  v3 = -1;
  String2 = 0;
  v10 = 0;
  while ( (__int64 *)v1 != &g_StSecSecurityDescriptorCacheListHead )
  {
    Path = *a1;
    FsRtlDissectName(&Path, &FirstName, &RemainingName);
    Path = *(UNICODE_STRING *)(v1 + 16);
    FsRtlDissectName(&Path, &String2, &v10);
    Buffer = FirstName.Buffer;
    if ( FirstName.Buffer )
    {
      while ( 1 )
      {
        v5 = String2.Buffer;
        if ( !String2.Buffer )
          goto LABEL_12;
        if ( !String2.Length )
          goto LABEL_9;
        v3 = RtlCompareUnicodeString(&FirstName, &String2, 1u);
        if ( v3 )
          break;
LABEL_10:
        Path = RemainingName;
        FsRtlDissectName(&Path, &FirstName, &RemainingName);
        Path = v10;
        FsRtlDissectName(&Path, &String2, &v10);
        Buffer = FirstName.Buffer;
        if ( !FirstName.Buffer )
          goto LABEL_11;
      }
      if ( *String2.Buffer != 60 || String2.Buffer[((unsigned __int64)String2.Length >> 1) - 1] != 62 )
        goto LABEL_13;
LABEL_9:
      v3 = 0;
      goto LABEL_10;
    }
LABEL_11:
    v5 = String2.Buffer;
LABEL_12:
    if ( !v3 )
    {
      if ( Buffer || !v5 )
        return v1;
      v3 = -1;
    }
LABEL_13:
    v1 = *(_QWORD *)v1;
  }
  return 0;
}

```

## disassembly

```asm
0x140010cb0  push    rbp
0x140010cb2  push    rbx
0x140010cb3  push    rsi
0x140010cb4  push    rdi
0x140010cb5  push    r14
0x140010cb7  push    r15
0x140010cb9  mov     rbp, rsp
0x140010cbc  sub     rsp, 78h
0x140010cc0  mov     rbx, cs:g_StSecSecurityDescriptorCacheListHead
0x140010cc7  lea     r15, g_StSecSecurityDescriptorCacheListHead
0x140010cce  xorps   xmm0, xmm0
0x140010cd1  xorps   xmm1, xmm1
0x140010cd4  movups  xmmword ptr [rbp+FirstName.Length], xmm0
0x140010cd8  mov     rsi, rcx
0x140010cdb  xor     r14d, r14d
0x140010cde  movups  xmmword ptr [rbp+RemainingName.Length], xmm1
0x140010ce2  mov     edi, 0FFFFFFFFh
0x140010ce7  movups  xmmword ptr [rbp+String2.Length], xmm0
0x140010ceb  movups  xmmword ptr [rbp+var_28.Length], xmm1
0x140010cef  nop
0x140010cf0  cmp     rbx, r15
0x140010cf3  jz      loc_140010E12
0x140010cf9  movups  xmm0, xmmword ptr [rsi]
0x140010cfc  lea     r8, [rbp+RemainingName]; RemainingName
0x140010d00  lea     rdx, [rbp+FirstName]; FirstName
0x140010d04  lea     rcx, [rbp+Path]; Path
0x140010d08  movaps  xmmword ptr [rbp+Path.Length], xmm0
0x140010d0c  call    cs:__imp_FsRtlDissectName
0x140010d13  nop     dword ptr [rax+rax+00h]
0x140010d18  movups  xmm0, xmmword ptr [rbx+10h]
0x140010d1c  lea     r8, [rbp+var_28]; RemainingName
0x140010d20  lea     rdx, [rbp+String2]; FirstName
0x140010d24  lea     rcx, [rbp+Path]; Path
0x140010d28  movaps  xmmword ptr [rbp+Path.Length], xmm0
0x140010d2c  call    cs:__imp_FsRtlDissectName
0x140010d33  nop     dword ptr [rax+rax+00h]
0x140010d38  mov     rcx, [rbp+FirstName.Buffer]
0x140010d3c  test    rcx, rcx
0x140010d3f  jz      loc_140010DE0
0x140010d45  mov     rax, [rbp+String2.Buffer]
0x140010d49  test    rax, rax
0x140010d4c  jz      loc_140010DE4
0x140010d52  cmp     [rbp+String2.Length], r14w
0x140010d57  jz      short loc_140010D8F
0x140010d59  mov     r8b, 1; CaseInSensitive
0x140010d5c  lea     rdx, [rbp+String2]; String2
0x140010d60  lea     rcx, [rbp+FirstName]; String1
0x140010d64  call    cs:__imp_RtlCompareUnicodeString
0x140010d6b  nop     dword ptr [rax+rax+00h]
0x140010d70  mov     edi, eax
0x140010d72  test    eax, eax
0x140010d74  jz      short loc_140010D91
0x140010d76  mov     rcx, [rbp+String2.Buffer]
0x140010d7a  cmp     word ptr [rcx], 3Ch ; '<'
0x140010d7e  jnz     short loc_140010DE8
0x140010d80  movzx   eax, [rbp+String2.Length]
0x140010d84  shr     rax, 1
0x140010d87  cmp     word ptr [rcx+rax*2-2], 3Eh ; '>'
0x140010d8d  jnz     short loc_140010DE8
0x140010d8f  xor     edi, edi
0x140010d91  movaps  xmm0, xmmword ptr [rbp+RemainingName.Length]
0x140010d95  lea     r8, [rbp+RemainingName]; RemainingName
0x140010d99  lea     rdx, [rbp+FirstName]; FirstName
0x140010d9d  movdqa  xmmword ptr [rbp+Path.Length], xmm0
0x140010da2  lea     rcx, [rbp+Path]; Path
0x140010da6  call    cs:__imp_FsRtlDissectName
0x140010dad  nop     dword ptr [rax+rax+00h]
0x140010db2  movaps  xmm0, xmmword ptr [rbp+var_28.Length]
0x140010db6  lea     r8, [rbp+var_28]; RemainingName
0x140010dba  lea     rdx, [rbp+String2]; FirstName
0x140010dbe  movdqa  xmmword ptr [rbp+Path.Length], xmm0
0x140010dc3  lea     rcx, [rbp+Path]; Path
0x140010dc7  call    cs:__imp_FsRtlDissectName
0x140010dce  nop     dword ptr [rax+rax+00h]
0x140010dd3  mov     rcx, [rbp+FirstName.Buffer]
0x140010dd7  test    rcx, rcx
0x140010dda  jnz     loc_140010D45
0x140010de0  mov     rax, [rbp+String2.Buffer]
0x140010de4  test    edi, edi
0x140010de6  jz      short loc_140010DF0
0x140010de8  mov     rbx, [rbx]
0x140010deb  jmp     loc_140010CF0
0x140010df0  test    rcx, rcx
0x140010df3  jz      short loc_140010E06
0x140010df5  mov     rax, rbx
0x140010df8  add     rsp, 78h
0x140010dfc  pop     r15
0x140010dfe  pop     r14
0x140010e00  pop     rdi
0x140010e01  pop     rsi
0x140010e02  pop     rbx
0x140010e03  pop     rbp
0x140010e04  retn
0x140010e06  test    rax, rax
0x140010e09  jz      short loc_140010DF5
0x140010e0b  mov     edi, 0FFFFFFFFh
0x140010e10  jmp     short loc_140010DE8
0x140010e12  mov     rax, r14
0x140010e15  jmp     short loc_140010DF8
```
