# NlpDeletePrimaryCredential

- ea: `0x18000ceb0`
- end: `0x18000cf82`
- name: `NlpDeletePrimaryCredential`
- size: `210`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000b890`
- `0x18000c000`
- `0x18001a470`
- `0x18004704c`

## callees

- `0x18000ceb0`
- `0x180055548`
- `0x1800555f8`
- `0x18006d010`

## import_xrefs

- `ntdll!RtlInitString` at `0x18000cecd`
- `ntdll!RtlInitString` at `0x18000cecd`

## string_xrefs

- `0x18000cf3d`: `NlpDeletePrimaryCredential`
- `0x18000cf67`: `NlpDeletePrimaryCredential`

## pseudocode

```c
__int64 __fastcall NlpDeletePrimaryCredential(__int64 a1)
{
  int v2; // ebx
  int v3; // r8d
  struct _STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF

  DestinationString = 0;
  RtlInitString(&DestinationString, "Primary");
  v2 = ((__int64 (__fastcall *)(__int64, _QWORD, struct _STRING *))qword_180088230)(
         a1,
         (unsigned int)MspAuthenticationPackageId,
         &DestinationString);
  if ( v2 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_sds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        v3,
        (unsigned int)"NlpDeletePrimaryCredential",
        1,
        (__int64)"NtlmSuccess");
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sdsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)&WPP_GLOBAL_Control,
      v3,
      (unsigned int)"NlpDeletePrimaryCredential",
      1,
      (__int64)"NtlmFailure",
      v2);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000ceb0  push    rbx
0x18000ceb2  sub     rsp, 50h
0x18000ceb6  mov     rbx, rcx
0x18000ceb9  lea     rdx, SourceString; "Primary"
0x18000cec0  xorps   xmm0, xmm0
0x18000cec3  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x18000cec8  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x18000cecd  call    cs:__imp_RtlInitString
0x18000ced3  mov     edx, cs:MspAuthenticationPackageId
0x18000ced9  lea     r8, [rsp+58h+DestinationString]
0x18000cede  mov     rax, cs:qword_180088230
0x18000cee5  mov     rcx, rbx
0x18000cee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ceed  mov     ebx, eax
0x18000ceef  test    eax, eax
0x18000cef1  jns     short loc_18000CF14
0x18000cef3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cefa  lea     rdx, WPP_GLOBAL_Control
0x18000cf01  cmp     rcx, rdx
0x18000cf04  jz      short loc_18000CF0C
0x18000cf06  test    byte ptr [rcx+1Ch], 1
0x18000cf0a  jnz     short loc_18000CF58
0x18000cf0c  mov     eax, ebx
0x18000cf0e  add     rsp, 50h
0x18000cf12  pop     rbx
0x18000cf13  retn
0x18000cf14  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf1b  lea     rdx, WPP_GLOBAL_Control
0x18000cf22  cmp     rcx, rdx
0x18000cf25  jz      short loc_18000CF0C
0x18000cf27  test    byte ptr [rcx+1Ch], 8
0x18000cf2b  jz      short loc_18000CF0C
0x18000cf2d  mov     rcx, [rcx+10h]
0x18000cf31  lea     rax, aNtlmsuccess; "NtlmSuccess"
0x18000cf38  mov     [rsp+58h+var_30], rax
0x18000cf3d  lea     r9, aNlpdeleteprima; "NlpDeletePrimaryCredential"
0x18000cf44  mov     edx, 0Eh
0x18000cf49  mov     [rsp+58h+var_38], 0A01h
0x18000cf51  call    WPP_SF_sds
0x18000cf56  jmp     short loc_18000CF0C
0x18000cf58  mov     rcx, [rcx+10h]
0x18000cf5c  lea     rax, aNtlmfailure; "NtlmFailure"
0x18000cf63  mov     [rsp+58h+var_28], ebx
0x18000cf67  lea     r9, aNlpdeleteprima; "NlpDeletePrimaryCredential"
0x18000cf6e  mov     [rsp+58h+var_30], rax
0x18000cf73  mov     [rsp+58h+var_38], 0A01h
0x18000cf7b  call    WPP_SF_sdsD
0x18000cf80  jmp     short loc_18000CF0C
```
