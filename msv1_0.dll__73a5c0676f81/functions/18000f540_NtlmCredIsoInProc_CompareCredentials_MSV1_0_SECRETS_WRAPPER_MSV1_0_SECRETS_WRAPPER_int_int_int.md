# NtlmCredIsoInProc::CompareCredentials(_MSV1_0_SECRETS_WRAPPER *,_MSV1_0_SECRETS_WRAPPER *,int *,int *,int *)

- ea: `0x18000f540`
- end: `0x18000f5b6`
- name: `?CompareCredentials@NtlmCredIsoInProc@@UEAAJPEAU_MSV1_0_SECRETS_WRAPPER@@0PEAH11@Z`
- size: `118`
- prototype: `__int64 __fastcall(NtlmCredIsoInProc *__hidden this, struct _MSV1_0_SECRETS_WRAPPER *, struct _MSV1_0_SECRETS_WRAPPER *, int *, int *, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000f540`
- `0x180055548`

## import_xrefs

- `NtlmShared!MsvpCompareCredentials` at `0x18000f564`
- `NtlmShared!MsvpCompareCredentials` at `0x18000f564`

## string_xrefs

- `0x18000f59b`: `NtlmCredIsoInProc::CompareCredentials`

## pseudocode

```c
__int64 __fastcall NtlmCredIsoInProc::CompareCredentials(
        NtlmCredIsoInProc *this,
        struct _MSV1_0_SECRETS_WRAPPER *a2,
        struct _MSV1_0_SECRETS_WRAPPER *a3,
        int *a4,
        int *a5,
        int *a6)
{
  int v6; // r8d

  MsvpCompareCredentials(a2, a3, a4, a5, a6);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_sds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      v6,
      (unsigned int)"NtlmCredIsoInProc::CompareCredentials",
      63,
      (__int64)"NtlmSuccess");
  return 0;
}

```

## disassembly

```asm
0x18000f540  push    rbx
0x18000f542  sub     rsp, 30h
0x18000f546  mov     rax, [rsp+38h+arg_28]
0x18000f54b  mov     r10, r9
0x18000f54e  mov     r9, [rsp+38h+arg_20]
0x18000f553  mov     r11, r8
0x18000f556  mov     rcx, rdx
0x18000f559  mov     [rsp+38h+var_18], rax
0x18000f55e  mov     r8, r10
0x18000f561  mov     rdx, r11
0x18000f564  call    cs:__imp_MsvpCompareCredentials
0x18000f56a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f571  lea     rax, WPP_GLOBAL_Control
0x18000f578  cmp     rcx, rax
0x18000f57b  jz      short loc_18000F583
0x18000f57d  test    byte ptr [rcx+1Ch], 8
0x18000f581  jnz     short loc_18000F58B
0x18000f583  xor     eax, eax
0x18000f585  add     rsp, 30h
0x18000f589  pop     rbx
0x18000f58a  retn
0x18000f58b  mov     rcx, [rcx+10h]
0x18000f58f  lea     rax, aNtlmsuccess; "NtlmSuccess"
0x18000f596  mov     [rsp+38h+var_10], rax
0x18000f59b  lea     r9, aNtlmcredisoinp_4; "NtlmCredIsoInProc::CompareCredentials"
0x18000f5a2  mov     edx, 0Eh
0x18000f5a7  mov     dword ptr [rsp+38h+var_18], 13Fh
0x18000f5af  call    WPP_SF_sds
0x18000f5b4  jmp     short loc_18000F583
```
