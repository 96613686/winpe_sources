# RxSidFromRxContext

- ea: `0x14006e620`
- end: `0x14006e7bd`
- name: `RxSidFromRxContext`
- size: `413`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140016e20`
- `0x14006e620`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006e6d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e72d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e6d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e72d`
- `ntoskrnl!SeQueryInformationToken` at `0x14006e68d`
- `ntoskrnl!SeQueryInformationToken` at `0x14006e68d`
- `ntoskrnl!SeLockSubjectContext` at `0x14006e662`
- `ntoskrnl!SeLockSubjectContext` at `0x14006e662`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14006e6e1`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14006e6e1`
- `ntoskrnl!RtlCopySid` at `0x14006e6bf`
- `ntoskrnl!RtlCopySid` at `0x14006e6bf`

## pseudocode

```c
__int64 __fastcall RxSidFromRxContext(__int64 a1, void *a2)
{
  char v2; // al
  __int64 v4; // rbx
  struct _SECURITY_SUBJECT_CONTEXT *v5; // rbx
  PACCESS_TOKEN ClientToken; // rcx
  NTSTATUS v7; // edi
  ULONG v8; // ecx
  PVOID TokenInformation; // [rsp+30h] [rbp+8h] BYREF

  v2 = *(_BYTE *)(a1 + 32);
  if ( !v2 )
  {
    v4 = *(_QWORD *)(a1 + 544);
    if ( v4 )
    {
      v5 = (struct _SECURITY_SUBJECT_CONTEXT *)(*(_QWORD *)(v4 + 8) + 32LL);
      goto LABEL_4;
    }
LABEL_21:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, &WPP_b27d4ea20cf23c7ef3650225eec88b96_Traceguids, 3221225485LL);
    }
    return 3221225711LL;
  }
  if ( v2 != 6 && (v2 != 12 || *(_BYTE *)(a1 + 33) != 1) || !*(_BYTE *)(a1 + 478) )
    goto LABEL_21;
  v5 = (struct _SECURITY_SUBJECT_CONTEXT *)(a1 + 480);
LABEL_4:
  if ( v5 )
  {
    SeLockSubjectContext(v5);
    ClientToken = v5->ClientToken;
    if ( !v5->ClientToken )
      ClientToken = v5->PrimaryToken;
    TokenInformation = 0;
    v7 = SeQueryInformationToken(ClientToken, TokenUser, &TokenInformation);
    if ( v7 >= 0 )
    {
      v8 = 4 * *(unsigned __int8 *)(*(_QWORD *)TokenInformation + 1LL) + 8;
      if ( v8 <= 0x44 )
      {
        RtlCopySid(v8, a2, *(PSID *)TokenInformation);
        ExFreePoolWithTag(TokenInformation, 0);
LABEL_10:
        SeUnlockSubjectContext(v5);
        return (unsigned int)v7;
      }
      v7 = -2147483643;
      ExFreePoolWithTag(TokenInformation, 0);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        16,
        &WPP_b27d4ea20cf23c7ef3650225eec88b96_Traceguids,
        (unsigned int)v7);
    }
    goto LABEL_10;
  }
  return 3221225711LL;
}

```

## disassembly

```asm
0x14006e620  mov     [rsp+arg_10], rbx
0x14006e625  push    rsi
0x14006e626  sub     rsp, 20h
0x14006e62a  movzx   eax, byte ptr [rcx+20h]
0x14006e62e  mov     rsi, rdx
0x14006e631  test    al, al
0x14006e633  jnz     loc_14006E700
0x14006e639  mov     rbx, [rcx+220h]
0x14006e640  test    rbx, rbx
0x14006e643  jz      loc_14006E778
0x14006e649  mov     rbx, [rbx+8]
0x14006e64d  add     rbx, 20h ; ' '
0x14006e651  test    rbx, rbx
0x14006e654  jz      loc_14006E7B3
0x14006e65a  mov     rcx, rbx; SubjectContext
0x14006e65d  mov     [rsp+28h+arg_8], rdi
0x14006e662  call    cs:__imp_SeLockSubjectContext
0x14006e669  nop     dword ptr [rax+rax+00h]
0x14006e66e  mov     rcx, [rbx]
0x14006e671  test    rcx, rcx
0x14006e674  jnz     short loc_14006E67A
0x14006e676  mov     rcx, [rbx+10h]; Token
0x14006e67a  lea     r8, [rsp+28h+TokenInformation]; TokenInformation
0x14006e67f  mov     [rsp+28h+TokenInformation], 0
0x14006e688  mov     edx, 1; TokenInformationClass
0x14006e68d  call    cs:__imp_SeQueryInformationToken
0x14006e694  nop     dword ptr [rax+rax+00h]
0x14006e699  mov     edi, eax
0x14006e69b  test    eax, eax
0x14006e69d  js      loc_14006E739
0x14006e6a3  mov     rax, [rsp+28h+TokenInformation]
0x14006e6a8  mov     r8, [rax]; SourceSid
0x14006e6ab  movzx   ecx, byte ptr [r8+1]
0x14006e6b0  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x14006e6b7  cmp     ecx, 44h ; 'D'
0x14006e6ba  ja      short loc_14006E723
0x14006e6bc  mov     rdx, rsi; DestinationSid
0x14006e6bf  call    cs:__imp_RtlCopySid
0x14006e6c6  nop     dword ptr [rax+rax+00h]
0x14006e6cb  mov     rcx, [rsp+28h+TokenInformation]; P
0x14006e6d0  xor     edx, edx; Tag
0x14006e6d2  call    cs:__imp_ExFreePoolWithTag
0x14006e6d9  nop     dword ptr [rax+rax+00h]
0x14006e6de  mov     rcx, rbx; SubjectContext
0x14006e6e1  call    cs:__imp_SeUnlockSubjectContext
0x14006e6e8  nop     dword ptr [rax+rax+00h]
0x14006e6ed  mov     eax, edi
0x14006e6ef  mov     rdi, [rsp+28h+arg_8]
0x14006e6f4  mov     rbx, [rsp+28h+arg_10]
0x14006e6f9  add     rsp, 20h
0x14006e6fd  pop     rsi
0x14006e6fe  retn
0x14006e700  cmp     al, 6
0x14006e702  jz      short loc_14006E70E
0x14006e704  cmp     al, 0Ch
0x14006e706  jnz     short loc_14006E778
0x14006e708  cmp     byte ptr [rcx+21h], 1
0x14006e70c  jnz     short loc_14006E778
0x14006e70e  cmp     byte ptr [rcx+1DEh], 0
0x14006e715  jz      short loc_14006E778
0x14006e717  lea     rbx, [rcx+1E0h]
0x14006e71e  jmp     loc_14006E651
0x14006e723  xor     edx, edx; Tag
0x14006e725  mov     rcx, rax; P
0x14006e728  mov     edi, 80000005h
0x14006e72d  call    cs:__imp_ExFreePoolWithTag
0x14006e734  nop     dword ptr [rax+rax+00h]
0x14006e739  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e740  lea     rax, WPP_GLOBAL_Control
0x14006e747  cmp     rcx, rax
0x14006e74a  jz      short loc_14006E6DE
0x14006e74c  test    dword ptr [rcx+2Ch], 1000h
0x14006e753  jz      short loc_14006E6DE
0x14006e755  cmp     byte ptr [rcx+29h], 2
0x14006e759  jb      short loc_14006E6DE
0x14006e75b  mov     rcx, [rcx+18h]
0x14006e75f  lea     r8, WPP_b27d4ea20cf23c7ef3650225eec88b96_Traceguids
0x14006e766  mov     edx, 10h
0x14006e76b  mov     r9d, edi
0x14006e76e  call    WPP_SF_d
0x14006e773  jmp     loc_14006E6DE
0x14006e778  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e77f  lea     rax, WPP_GLOBAL_Control
0x14006e786  cmp     rcx, rax
0x14006e789  jz      short loc_14006E7B3
0x14006e78b  mov     eax, [rcx+2Ch]
0x14006e78e  test    al, 1
0x14006e790  jz      short loc_14006E7B3
0x14006e792  cmp     byte ptr [rcx+29h], 1
0x14006e796  jb      short loc_14006E7B3
0x14006e798  mov     rcx, [rcx+18h]
0x14006e79c  lea     r8, WPP_b27d4ea20cf23c7ef3650225eec88b96_Traceguids
0x14006e7a3  mov     edx, 11h
0x14006e7a8  mov     r9d, 0C000000Dh
0x14006e7ae  call    WPP_SF_d
0x14006e7b3  mov     eax, 0C00000EFh
0x14006e7b8  jmp     loc_14006E6F4
```
