# WfpAleProcessTokenReference

- ea: `0x140179a60`
- end: `0x140179cba`
- name: `WfpAleProcessTokenReference`
- size: `602`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14011b2f8`

## callees

- `0x1400541c0`
- `0x1400b9ed8`
- `0x1400b9fa8`
- `0x1400bac20`
- `0x1400be690`
- `0x140179a60`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!KeUnstackDetachProcess` at `0x140179c4a`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140179c4a`
- `ntoskrnl!ZwDuplicateToken` at `0x140179ba7`
- `ntoskrnl!ZwDuplicateToken` at `0x140179ba7`
- `ntoskrnl!KeStackAttachProcess` at `0x140179b78`
- `ntoskrnl!KeStackAttachProcess` at `0x140179b78`
- `ntoskrnl!ZwOpenProcess` at `0x140179b05`
- `ntoskrnl!ZwOpenProcess` at `0x140179b05`
- `ntoskrnl!ZwClose` at `0x140179c35`
- `ntoskrnl!ZwClose` at `0x140179c73`
- `ntoskrnl!ZwClose` at `0x140179c35`
- `ntoskrnl!ZwClose` at `0x140179c73`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140179b54`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140179b54`
- `ntoskrnl!ObfDereferenceObject` at `0x140179c5e`
- `ntoskrnl!ObfDereferenceObject` at `0x140179c5e`

## string_xrefs

- `0x140179bb7`: `ZwDuplicateToken`
- `0x140179c84`: `WfpAleProcessTokenReference`
- `0x140179b17`: `ZwOpenProcess`

## pseudocode

```c
__int64 __fastcall WfpAleProcessTokenReference(unsigned int *a1, _QWORD *a2)
{
  void *v2; // rbx
  char v4; // r14
  unsigned int v5; // eax
  __int64 v6; // rcx
  PVOID v7; // rdi
  const char *v8; // rdx
  __int64 inserted; // rbx
  __int64 v10; // rsi
  char v12[8]; // [rsp+30h] [rbp-79h] BYREF
  void *NewTokenHandle; // [rsp+38h] [rbp-71h] BYREF
  void *ProcessHandle; // [rsp+40h] [rbp-69h] BYREF
  PVOID Object; // [rsp+48h] [rbp-61h] BYREF
  __int64 v16; // [rsp+50h] [rbp-59h] BYREF
  _QWORD v17[2]; // [rsp+58h] [rbp-51h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-41h] BYREF
  _CLIENT_ID ClientId; // [rsp+98h] [rbp-11h] BYREF
  _KAPC_STATE ApcState; // [rsp+A8h] [rbp-1h] BYREF

  v2 = (void *)*((_QWORD *)a1 + 1);
  ProcessHandle = 0;
  NewTokenHandle = 0;
  v16 = 0;
  ClientId.UniqueProcess = (HANDLE)*a1;
  *a2 = ALE_LUID_NULL;
  v4 = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  v12[0] = 1;
  memset(&ApcState, 0, sizeof(ApcState));
  ClientId.UniqueThread = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwOpenProcess(&ProcessHandle, 0x400u, &ObjectAttributes, &ClientId);
  if ( v5 )
  {
    v7 = 0;
    v8 = "ZwOpenProcess";
LABEL_3:
    inserted = WfpReportSysErrorAsNtStatus(v6, v8, v5);
    goto LABEL_12;
  }
  Object = 0;
  v5 = ObReferenceObjectByHandle(ProcessHandle, 0x400u, 0, 0, &Object, 0);
  v7 = Object;
  if ( v5 )
  {
    v8 = "_ObReferenceObjectByHandle";
    goto LABEL_3;
  }
  KeStackAttachProcess((PRKPROCESS)Object, &ApcState);
  v4 = 1;
  v5 = ZwDuplicateToken(v2, 0xF01FFu, &ObjectAttributes, 0, TokenPrimary, &NewTokenHandle);
  if ( v5 )
  {
    v8 = "ZwDuplicateToken";
    goto LABEL_3;
  }
  v17[0] = ALE_LUID_NULL;
  v17[1] = ALE_LUID_NULL;
  inserted = WfpAleCaptureTokenIdByHandle(NewTokenHandle);
  if ( !inserted )
  {
    inserted = WfpAleAcquireTokenInformationFromToken(
                 0,
                 (_DWORD)NewTokenHandle,
                 (unsigned int)v17,
                 (unsigned int)&v16,
                 (__int64)v12);
    if ( !inserted )
    {
      v10 = v16;
      inserted = WfpAleInsertTokenInformationByUserTokenIdIfNeeded(v16);
      if ( !inserted )
        *a2 = *(_QWORD *)(v10 + 20);
    }
  }
LABEL_12:
  if ( NewTokenHandle && v12[0] )
    ZwClose(NewTokenHandle);
  if ( v4 )
    KeUnstackDetachProcess(&ApcState);
  if ( v7 )
    ObfDereferenceObject(v7);
  if ( ProcessHandle )
    ZwClose(ProcessHandle);
  if ( inserted )
    WfpReportError(inserted, "WfpAleProcessTokenReference");
  return inserted;
}

```

## disassembly

```asm
0x140179a60  mov     [rsp-8+arg_10], rbx
0x140179a65  push    rbp
0x140179a66  push    rsi
0x140179a67  push    rdi
0x140179a68  push    r14
0x140179a6a  push    r15
0x140179a6c  lea     rbp, [rsp-37h]
0x140179a71  sub     rsp, 0E0h
0x140179a78  mov     rax, cs:__security_cookie
0x140179a7f  xor     rax, rsp
0x140179a82  mov     [rbp+57h+var_28], rax
0x140179a86  mov     rbx, [rcx+8]
0x140179a8a  lea     r9, [rbp+57h+ClientId]; ClientId
0x140179a8e  xor     eax, eax
0x140179a90  mov     [rbp+57h+ProcessHandle], 0
0x140179a98  xorps   xmm0, xmm0
0x140179a9b  mov     [rbp+57h+NewTokenHandle], rax
0x140179a9f  mov     [rbp+57h+var_B0], rax
0x140179aa3  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140179aa7  mov     eax, [rcx]
0x140179aa9  mov     r15, rdx
0x140179aac  mov     [rbp+57h+ClientId.UniqueProcess], rax
0x140179ab0  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x140179ab4  mov     rax, cs:ALE_LUID_NULL
0x140179abb  mov     edi, 400h
0x140179ac0  mov     [rdx], rax
0x140179ac3  xor     r14b, r14b
0x140179ac6  mov     edx, edi; DesiredAccess
0x140179ac8  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140179ad0  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 200h
0x140179ad8  mov     [rbp+57h+var_D0], 1
0x140179adc  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink], xmm0
0x140179ae0  mov     [rbp+57h+ClientId.UniqueThread], 0
0x140179ae8  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink+10h], xmm0
0x140179aec  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140179af4  movups  xmmword ptr [rbp+57h+ApcState.Process], xmm0
0x140179af8  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x140179b00  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140179b05  call    cs:__imp_ZwOpenProcess
0x140179b0c  nop     dword ptr [rax+rax+00h]
0x140179b11  test    eax, eax
0x140179b13  jz      short loc_140179B2E
0x140179b15  xor     edi, edi
0x140179b17  lea     rdx, aZwopenprocess; "ZwOpenProcess"
0x140179b1e  mov     r8d, eax
0x140179b21  call    WfpReportSysErrorAsNtStatus
0x140179b26  mov     rbx, rax
0x140179b29  jmp     loc_140179C26
0x140179b2e  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x140179b32  lea     rax, [rbp+57h+var_B8]
0x140179b36  mov     [rsp+100h+HandleInformation], 0; HandleInformation
0x140179b3f  xor     r9d, r9d; AccessMode
0x140179b42  xor     r8d, r8d; ObjectType
0x140179b45  mov     [rsp+100h+Object], rax; Object
0x140179b4a  mov     edx, edi; DesiredAccess
0x140179b4c  mov     [rbp+57h+var_B8], 0
0x140179b54  call    cs:__imp_ObReferenceObjectByHandle
0x140179b5b  nop     dword ptr [rax+rax+00h]
0x140179b60  mov     rdi, [rbp+57h+var_B8]
0x140179b64  test    eax, eax
0x140179b66  jz      short loc_140179B71
0x140179b68  lea     rdx, aObreferenceobj; "_ObReferenceObjectByHandle"
0x140179b6f  jmp     short loc_140179B1E
0x140179b71  lea     rdx, [rbp+57h+ApcState]; ApcState
0x140179b75  mov     rcx, rdi; PROCESS
0x140179b78  call    cs:__imp_KeStackAttachProcess
0x140179b7f  nop     dword ptr [rax+rax+00h]
0x140179b84  lea     rax, [rbp+57h+NewTokenHandle]
0x140179b88  xor     r9d, r9d; EffectiveOnly
0x140179b8b  mov     [rsp+100h+HandleInformation], rax; NewTokenHandle
0x140179b90  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140179b94  mov     edx, 0F01FFh; DesiredAccess
0x140179b99  mov     dword ptr [rsp+100h+Object], 1; TokenType
0x140179ba1  mov     rcx, rbx; ExistingTokenHandle
0x140179ba4  mov     r14b, 1
0x140179ba7  call    cs:__imp_ZwDuplicateToken
0x140179bae  nop     dword ptr [rax+rax+00h]
0x140179bb3  test    eax, eax
0x140179bb5  jz      short loc_140179BC3
0x140179bb7  lea     rdx, aZwduplicatetok; "ZwDuplicateToken"
0x140179bbe  jmp     loc_140179B1E
0x140179bc3  mov     rax, cs:ALE_LUID_NULL
0x140179bca  lea     rdx, [rbp+57h+var_A8]
0x140179bce  mov     rcx, [rbp+57h+NewTokenHandle]; TokenHandle
0x140179bd2  mov     [rbp+57h+var_A8], rax
0x140179bd6  mov     [rbp+57h+var_A0], rax
0x140179bda  call    WfpAleCaptureTokenIdByHandle
0x140179bdf  mov     rbx, rax
0x140179be2  test    rax, rax
0x140179be5  jnz     short loc_140179C26
0x140179be7  mov     rdx, [rbp+57h+NewTokenHandle]
0x140179beb  lea     rax, [rbp+57h+var_D0]
0x140179bef  lea     r9, [rbp+57h+var_B0]
0x140179bf3  mov     [rsp+100h+Object], rax
0x140179bf8  lea     r8, [rbp+57h+var_A8]
0x140179bfc  xor     ecx, ecx
0x140179bfe  call    WfpAleAcquireTokenInformationFromToken
0x140179c03  mov     rbx, rax
0x140179c06  test    rax, rax
0x140179c09  jnz     short loc_140179C26
0x140179c0b  mov     rsi, [rbp+57h+var_B0]
0x140179c0f  mov     rcx, rsi
0x140179c12  call    WfpAleInsertTokenInformationByUserTokenIdIfNeeded
0x140179c17  mov     rbx, rax
0x140179c1a  test    rax, rax
0x140179c1d  jnz     short loc_140179C26
0x140179c1f  mov     rax, [rsi+14h]
0x140179c23  mov     [r15], rax
0x140179c26  mov     rcx, [rbp+57h+NewTokenHandle]; Handle
0x140179c2a  test    rcx, rcx
0x140179c2d  jz      short loc_140179C41
0x140179c2f  cmp     [rbp+57h+var_D0], 0
0x140179c33  jz      short loc_140179C41
0x140179c35  call    cs:__imp_ZwClose
0x140179c3c  nop     dword ptr [rax+rax+00h]
0x140179c41  test    r14b, r14b
0x140179c44  jz      short loc_140179C56
0x140179c46  lea     rcx, [rbp+57h+ApcState]; ApcState
0x140179c4a  call    cs:__imp_KeUnstackDetachProcess
0x140179c51  nop     dword ptr [rax+rax+00h]
0x140179c56  test    rdi, rdi
0x140179c59  jz      short loc_140179C6A
0x140179c5b  mov     rcx, rdi; Object
0x140179c5e  call    cs:__imp_ObfDereferenceObject
0x140179c65  nop     dword ptr [rax+rax+00h]
0x140179c6a  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x140179c6e  test    rcx, rcx
0x140179c71  jz      short loc_140179C7F
0x140179c73  call    cs:__imp_ZwClose
0x140179c7a  nop     dword ptr [rax+rax+00h]
0x140179c7f  test    rbx, rbx
0x140179c82  jz      short loc_140179C93
0x140179c84  lea     rdx, aWfpaleprocesst; "WfpAleProcessTokenReference"
0x140179c8b  mov     rcx, rbx
0x140179c8e  call    WfpReportError
0x140179c93  mov     rax, rbx
0x140179c96  mov     rcx, [rbp+57h+var_28]
0x140179c9a  xor     rcx, rsp; StackCookie
0x140179c9d  call    __security_check_cookie
0x140179ca2  mov     rbx, [rsp+100h+arg_10]
0x140179caa  add     rsp, 0E0h
0x140179cb1  pop     r15
0x140179cb3  pop     r14
0x140179cb5  pop     rdi
0x140179cb6  pop     rsi
0x140179cb7  pop     rbp
0x140179cb8  retn
```
