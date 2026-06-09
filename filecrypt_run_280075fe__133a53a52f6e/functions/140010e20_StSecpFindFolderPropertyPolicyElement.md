# StSecpFindFolderPropertyPolicyElement

- ea: `0x140010e20`
- end: `0x140010f7b`
- name: `StSecpFindFolderPropertyPolicyElement`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140010500`

## callees

- `0x140010e20`

## import_xrefs

- `ntoskrnl!FsRtlDissectName` at `0x140010e7b`
- `ntoskrnl!FsRtlDissectName` at `0x140010e9b`
- `ntoskrnl!FsRtlDissectName` at `0x140010f14`
- `ntoskrnl!FsRtlDissectName` at `0x140010f35`
- `ntoskrnl!FsRtlDissectName` at `0x140010e7b`
- `ntoskrnl!FsRtlDissectName` at `0x140010e9b`
- `ntoskrnl!FsRtlDissectName` at `0x140010f14`
- `ntoskrnl!FsRtlDissectName` at `0x140010f35`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140010ed2`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140010ed2`

## pseudocode

```c
__int64 __fastcall StSecpFindFolderPropertyPolicyElement(UNICODE_STRING *a1)
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

  v1 = g_StSecFolderPropertyCacheListHead;
  FirstName = 0;
  RemainingName = 0;
  v3 = -1;
  String2 = 0;
  v10 = 0;
  while ( 1 )
  {
    if ( (__int64 *)v1 == &g_StSecFolderPropertyCacheListHead )
      return 0;
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
          break;
        if ( String2.Length )
        {
          v3 = RtlCompareUnicodeString(&FirstName, &String2, 1u);
          if ( v3 )
            goto LABEL_7;
        }
        else
        {
          v3 = 0;
        }
        Path = RemainingName;
        FsRtlDissectName(&Path, &FirstName, &RemainingName);
        Path = v10;
        FsRtlDissectName(&Path, &String2, &v10);
        Buffer = FirstName.Buffer;
        if ( !FirstName.Buffer )
          goto LABEL_11;
      }
    }
    else
    {
LABEL_11:
      v5 = String2.Buffer;
    }
    if ( !v3 )
      break;
LABEL_7:
    v1 = *(_QWORD *)v1;
  }
  if ( !Buffer && v5 )
  {
    v3 = -1;
    goto LABEL_7;
  }
  return v1;
}

```

## disassembly

```asm
0x140010e20  push    rbp
0x140010e22  push    rbx
0x140010e23  push    rsi
0x140010e24  push    rdi
0x140010e25  push    r14
0x140010e27  push    r15
0x140010e29  mov     rbp, rsp
0x140010e2c  sub     rsp, 78h
0x140010e30  mov     rbx, cs:g_StSecFolderPropertyCacheListHead
0x140010e37  lea     r15, g_StSecFolderPropertyCacheListHead
0x140010e3e  xorps   xmm0, xmm0
0x140010e41  xorps   xmm1, xmm1
0x140010e44  movups  xmmword ptr [rbp+FirstName.Length], xmm0
0x140010e48  mov     r14, rcx
0x140010e4b  xor     esi, esi
0x140010e4d  movups  xmmword ptr [rbp+RemainingName.Length], xmm1
0x140010e51  mov     edi, 0FFFFFFFFh
0x140010e56  movups  xmmword ptr [rbp+String2.Length], xmm0
0x140010e5a  movups  xmmword ptr [rbp+var_28.Length], xmm1
0x140010e5e  cmp     rbx, r15
0x140010e61  jz      loc_140010EEC
0x140010e67  movups  xmm0, xmmword ptr [r14]
0x140010e6b  lea     r8, [rbp+RemainingName]; RemainingName
0x140010e6f  lea     rdx, [rbp+FirstName]; FirstName
0x140010e73  lea     rcx, [rbp+Path]; Path
0x140010e77  movaps  xmmword ptr [rbp+Path.Length], xmm0
0x140010e7b  call    cs:__imp_FsRtlDissectName
0x140010e82  nop     dword ptr [rax+rax+00h]
0x140010e87  movups  xmm0, xmmword ptr [rbx+10h]
0x140010e8b  lea     r8, [rbp+var_28]; RemainingName
0x140010e8f  lea     rdx, [rbp+String2]; FirstName
0x140010e93  lea     rcx, [rbp+Path]; Path
0x140010e97  movaps  xmmword ptr [rbp+Path.Length], xmm0
0x140010e9b  call    cs:__imp_FsRtlDissectName
0x140010ea2  nop     dword ptr [rax+rax+00h]
0x140010ea7  mov     rcx, [rbp+FirstName.Buffer]
0x140010eab  test    rcx, rcx
0x140010eae  jz      loc_140010F4E
0x140010eb4  mov     rax, [rbp+String2.Buffer]
0x140010eb8  test    rax, rax
0x140010ebb  jz      loc_140010F52
0x140010ec1  cmp     [rbp+String2.Length], si
0x140010ec5  jz      short loc_140010EFD
0x140010ec7  mov     r8b, 1; CaseInSensitive
0x140010eca  lea     rdx, [rbp+String2]; String2
0x140010ece  lea     rcx, [rbp+FirstName]; String1
0x140010ed2  call    cs:__imp_RtlCompareUnicodeString
0x140010ed9  nop     dword ptr [rax+rax+00h]
0x140010ede  mov     edi, eax
0x140010ee0  test    eax, eax
0x140010ee2  jz      short loc_140010EFF
0x140010ee4  mov     rbx, [rbx]
0x140010ee7  jmp     loc_140010E5E
0x140010eec  mov     rax, rsi
0x140010eef  add     rsp, 78h
0x140010ef3  pop     r15
0x140010ef5  pop     r14
0x140010ef7  pop     rdi
0x140010ef8  pop     rsi
0x140010ef9  pop     rbx
0x140010efa  pop     rbp
0x140010efb  retn
0x140010efd  xor     edi, edi
0x140010eff  movaps  xmm0, xmmword ptr [rbp+RemainingName.Length]
0x140010f03  lea     r8, [rbp+RemainingName]; RemainingName
0x140010f07  lea     rdx, [rbp+FirstName]; FirstName
0x140010f0b  movdqa  xmmword ptr [rbp+Path.Length], xmm0
0x140010f10  lea     rcx, [rbp+Path]; Path
0x140010f14  call    cs:__imp_FsRtlDissectName
0x140010f1b  nop     dword ptr [rax+rax+00h]
0x140010f20  movaps  xmm0, xmmword ptr [rbp+var_28.Length]
0x140010f24  lea     r8, [rbp+var_28]; RemainingName
0x140010f28  lea     rdx, [rbp+String2]; FirstName
0x140010f2c  movdqa  xmmword ptr [rbp+Path.Length], xmm0
0x140010f31  lea     rcx, [rbp+Path]; Path
0x140010f35  call    cs:__imp_FsRtlDissectName
0x140010f3c  nop     dword ptr [rax+rax+00h]
0x140010f41  mov     rcx, [rbp+FirstName.Buffer]
0x140010f45  test    rcx, rcx
0x140010f48  jnz     loc_140010EB4
0x140010f4e  mov     rax, [rbp+String2.Buffer]
0x140010f52  test    edi, edi
0x140010f54  jnz     short loc_140010EE4
0x140010f56  test    rcx, rcx
0x140010f59  jz      short loc_140010F6C
0x140010f5b  mov     rax, rbx
0x140010f5e  add     rsp, 78h
0x140010f62  pop     r15
0x140010f64  pop     r14
0x140010f66  pop     rdi
0x140010f67  pop     rsi
0x140010f68  pop     rbx
0x140010f69  pop     rbp
0x140010f6a  retn
0x140010f6c  test    rax, rax
0x140010f6f  jz      short loc_140010F5B
0x140010f71  mov     edi, 0FFFFFFFFh
0x140010f76  jmp     loc_140010EE4
```
