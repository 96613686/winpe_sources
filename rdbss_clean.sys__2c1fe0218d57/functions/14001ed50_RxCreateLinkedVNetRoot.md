# RxCreateLinkedVNetRoot

- ea: `0x14001ed50`
- end: `0x14001efaf`
- name: `RxCreateLinkedVNetRoot`
- size: `607`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation`

## callees

- `0x14001ed50`
- `0x14001f28c`
- `0x14001f598`
- `0x1400221f4`
- `0x140022524`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001ee68`
- `ntoskrnl!ExAllocatePool2` at `0x14001ee68`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001eea3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001eea3`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001eeb6`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001eed3`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001eeb6`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001eed3`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14001ef49`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14001ef49`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ef88`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ef88`
- `ntoskrnl!RtlCopyLuid` at `0x14001eda0`
- `ntoskrnl!RtlCopyLuid` at `0x14001ef63`
- `ntoskrnl!RtlCopyLuid` at `0x14001eda0`
- `ntoskrnl!RtlCopyLuid` at `0x14001ef63`

## pseudocode

```c
__int64 __fastcall RxCreateLinkedVNetRoot(__int64 a1, __int64 a2, UNICODE_STRING *a3, struct _LUID *a4)
{
  int v7; // ebx
  char v8; // r15
  unsigned __int16 *v9; // r12
  unsigned __int16 *v10; // rcx
  int v11; // edx
  int v12; // ecx
  unsigned int v13; // r14d
  __int64 v14; // rdx
  const UNICODE_STRING *v15; // rdx
  struct _LUID v17; // [rsp+30h] [rbp-20h] BYREF
  void *v18; // [rsp+38h] [rbp-18h] BYREF
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  struct _LUID DestinationLuid; // [rsp+98h] [rbp+48h] BYREF
  PLUID v21; // [rsp+A8h] [rbp+58h]

  v21 = a4;
  *(_QWORD *)&DestinationString.Length = 0;
  v17 = 0;
  DestinationLuid = 0;
  v18 = 0;
  DestinationString.Buffer = 0;
  if ( !RxEnableLinkedConnections )
  {
    v7 = 0;
    RtlCopyLuid(&DestinationLuid, (PLUID)(a2 + 72));
LABEL_27:
    RtlCopyLuid(v21, &DestinationLuid);
    goto LABEL_28;
  }
  v7 = RxImpersonateLinkedToken(&v18, &v17, &DestinationLuid);
  if ( v7 < 0 )
    goto LABEL_28;
  if ( v17 == DestinationLuid || *(_QWORD *)(a2 + 432) )
    goto LABEL_27;
  if ( *(_DWORD *)(a2 + 72) == *(_DWORD *)(a2 + 80) && *(_DWORD *)(a2 + 76) == *(_DWORD *)(a2 + 84) )
  {
    v8 = 1;
  }
  else
  {
    v8 = 0;
    if ( !a3->Length )
      goto LABEL_27;
  }
  v9 = (unsigned __int16 *)(a2 + 224);
  v10 = *(unsigned __int16 **)(*(_QWORD *)(a1 + 72) + 80LL);
  v11 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 80) + 360LL);
  if ( v10 )
    v12 = v11 + *v9 + *v10;
  else
    v12 = v11 + *v9;
  v13 = v12 + 2;
  if ( (unsigned int)(v12 + 2) >= 0xFFFE )
  {
    v7 = -1073741811;
    goto LABEL_28;
  }
  DestinationString.Buffer = (wchar_t *)ExAllocatePool2(258, v13, 1934456914);
  if ( !DestinationString.Buffer )
  {
    v7 = -1073741670;
    goto LABEL_28;
  }
  v14 = *(_QWORD *)(a1 + 80);
  DestinationString.MaximumLength = v13;
  DestinationString.Length = 0;
  RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(v14 + 360));
  RtlAppendUnicodeStringToString(&DestinationString, (PCUNICODE_STRING)(a2 + 224));
  v15 = *(const UNICODE_STRING **)(*(_QWORD *)(a1 + 72) + 80LL);
  if ( v15 )
    RtlAppendUnicodeStringToString(&DestinationString, v15);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_ZqZ(
      WPP_GLOBAL_Control->AttachedDevice,
      12,
      (unsigned int)&WPP_e01a4f2c5ae23c78cfc8b6f416d17e00_Traceguids,
      (_DWORD)a3,
      a2,
      (__int64)&DestinationString);
  }
  if ( !v8 || (v7 = RxpCreateLinkedTreeConnect(a2, &DestinationString), v7 >= 0) )
  {
    if ( !a3->Length )
      goto LABEL_27;
    v7 = IoCreateSymbolicLink(a3, &DestinationString);
    if ( v7 >= 0 )
      goto LABEL_27;
  }
LABEL_28:
  if ( v18 )
    RxRevert();
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14001ed50  mov     [rsp-38h+arg_0], rbx
0x14001ed55  mov     [rsp-38h+arg_18], r9
0x14001ed5a  push    rbp
0x14001ed5b  push    rsi
0x14001ed5c  push    rdi
0x14001ed5d  push    r12
0x14001ed5f  push    r13
0x14001ed61  push    r14
0x14001ed63  push    r15
0x14001ed65  mov     rbp, rsp
0x14001ed68  sub     rsp, 50h
0x14001ed6c  xor     r14d, r14d
0x14001ed6f  mov     rsi, r8
0x14001ed72  cmp     cs:RxEnableLinkedConnections, r14b
0x14001ed79  mov     rdi, rdx
0x14001ed7c  mov     r13, rcx
0x14001ed7f  mov     qword ptr [rbp+DestinationString.Length], r14
0x14001ed83  mov     [rbp+var_20], r14
0x14001ed87  mov     qword ptr [rbp+DestinationLuid.LowPart], r14
0x14001ed8b  mov     [rbp+var_18], r14
0x14001ed8f  mov     [rbp+DestinationString.Buffer], r14
0x14001ed93  jnz     short loc_14001EDB1
0x14001ed95  add     rdx, 48h ; 'H'; SourceLuid
0x14001ed99  lea     rcx, [rbp+DestinationLuid]; DestinationLuid
0x14001ed9d  mov     ebx, r14d
0x14001eda0  call    cs:__imp_RtlCopyLuid
0x14001eda7  nop     dword ptr [rax+rax+00h]
0x14001edac  jmp     loc_14001EF5B
0x14001edb1  lea     r8, [rbp+DestinationLuid]
0x14001edb5  lea     rdx, [rbp+var_20]
0x14001edb9  lea     rcx, [rbp+var_18]
0x14001edbd  call    RxImpersonateLinkedToken
0x14001edc2  mov     ebx, eax
0x14001edc4  test    eax, eax
0x14001edc6  js      loc_14001EF6F
0x14001edcc  mov     ecx, [rbp+DestinationLuid.LowPart]
0x14001edcf  cmp     dword ptr [rbp+var_20], ecx
0x14001edd2  jnz     short loc_14001EDE0
0x14001edd4  mov     ecx, [rbp+DestinationLuid.HighPart]
0x14001edd7  cmp     dword ptr [rbp+var_20+4], ecx
0x14001edda  jz      loc_14001EF5B
0x14001ede0  cmp     [rdi+1B0h], r14
0x14001ede7  jnz     loc_14001EF5B
0x14001eded  mov     eax, [rdi+50h]
0x14001edf0  cmp     [rdi+48h], eax
0x14001edf3  jnz     short loc_14001EE02
0x14001edf5  mov     eax, [rdi+54h]
0x14001edf8  cmp     [rdi+4Ch], eax
0x14001edfb  jnz     short loc_14001EE02
0x14001edfd  mov     r15b, 1
0x14001ee00  jmp     short loc_14001EE0F
0x14001ee02  mov     r15b, r14b
0x14001ee05  cmp     [rsi], r14w
0x14001ee09  jz      loc_14001EF5B
0x14001ee0f  mov     rax, [r13+48h]
0x14001ee13  lea     r12, [rdi+0E0h]
0x14001ee1a  mov     rcx, [rax+50h]
0x14001ee1e  mov     rax, [r13+50h]
0x14001ee22  movzx   edx, word ptr [rax+168h]
0x14001ee29  test    rcx, rcx
0x14001ee2c  jnz     short loc_14001EE37
0x14001ee2e  movzx   ecx, word ptr [r12]
0x14001ee33  add     ecx, edx
0x14001ee35  jmp     short loc_14001EE43
0x14001ee37  movzx   eax, word ptr [r12]
0x14001ee3c  movzx   ecx, word ptr [rcx]
0x14001ee3f  add     eax, edx
0x14001ee41  add     ecx, eax
0x14001ee43  lea     r14d, [rcx+2]
0x14001ee47  cmp     r14d, 0FFFEh
0x14001ee4e  jb      short loc_14001EE5A
0x14001ee50  mov     ebx, 0C000000Dh
0x14001ee55  jmp     loc_14001EF6F
0x14001ee5a  mov     edx, r14d
0x14001ee5d  mov     ecx, 102h
0x14001ee62  mov     r8d, 734D7852h
0x14001ee68  call    cs:__imp_ExAllocatePool2
0x14001ee6f  nop     dword ptr [rax+rax+00h]
0x14001ee74  mov     [rbp+DestinationString.Buffer], rax
0x14001ee78  test    rax, rax
0x14001ee7b  jnz     short loc_14001EE87
0x14001ee7d  mov     ebx, 0C000009Ah
0x14001ee82  jmp     loc_14001EF6F
0x14001ee87  mov     rdx, [r13+50h]
0x14001ee8b  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001ee8f  mov     [rbp+DestinationString.MaximumLength], r14w
0x14001ee94  add     rdx, 168h; SourceString
0x14001ee9b  xor     r14d, r14d
0x14001ee9e  mov     [rbp+DestinationString.Length], r14w
0x14001eea3  call    cs:__imp_RtlCopyUnicodeString
0x14001eeaa  nop     dword ptr [rax+rax+00h]
0x14001eeaf  mov     rdx, r12; Source
0x14001eeb2  lea     rcx, [rbp+DestinationString]; Destination
0x14001eeb6  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001eebd  nop     dword ptr [rax+rax+00h]
0x14001eec2  mov     rax, [r13+48h]
0x14001eec6  mov     rdx, [rax+50h]; Source
0x14001eeca  test    rdx, rdx
0x14001eecd  jz      short loc_14001EEDF
0x14001eecf  lea     rcx, [rbp+DestinationString]; Destination
0x14001eed3  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001eeda  nop     dword ptr [rax+rax+00h]
0x14001eedf  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eee6  lea     rax, WPP_GLOBAL_Control
0x14001eeed  cmp     rcx, rax
0x14001eef0  jz      short loc_14001EF25
0x14001eef2  mov     eax, [rcx+2Ch]
0x14001eef5  test    al, al
0x14001eef7  jns     short loc_14001EF25
0x14001eef9  cmp     byte ptr [rcx+29h], 2
0x14001eefd  jb      short loc_14001EF25
0x14001eeff  mov     rcx, [rcx+18h]
0x14001ef03  lea     rax, [rbp+DestinationString]
0x14001ef07  mov     [rsp+50h+var_28], rax
0x14001ef0c  lea     r8, WPP_e01a4f2c5ae23c78cfc8b6f416d17e00_Traceguids
0x14001ef13  mov     edx, 0Ch
0x14001ef18  mov     [rsp+50h+var_30], rdi
0x14001ef1d  mov     r9, rsi
0x14001ef20  call    WPP_SF_ZqZ
0x14001ef25  test    r15b, r15b
0x14001ef28  jz      short loc_14001EF3C
0x14001ef2a  lea     rdx, [rbp+DestinationString]
0x14001ef2e  mov     rcx, rdi
0x14001ef31  call    RxpCreateLinkedTreeConnect
0x14001ef36  mov     ebx, eax
0x14001ef38  test    eax, eax
0x14001ef3a  js      short loc_14001EF6F
0x14001ef3c  cmp     [rsi], r14w
0x14001ef40  jz      short loc_14001EF5B
0x14001ef42  lea     rdx, [rbp+DestinationString]; DeviceName
0x14001ef46  mov     rcx, rsi; SymbolicLinkName
0x14001ef49  call    cs:__imp_IoCreateSymbolicLink
0x14001ef50  nop     dword ptr [rax+rax+00h]
0x14001ef55  mov     ebx, eax
0x14001ef57  test    eax, eax
0x14001ef59  js      short loc_14001EF6F
0x14001ef5b  mov     rcx, [rbp+arg_18]; DestinationLuid
0x14001ef5f  lea     rdx, [rbp+DestinationLuid]; SourceLuid
0x14001ef63  call    cs:__imp_RtlCopyLuid
0x14001ef6a  nop     dword ptr [rax+rax+00h]
0x14001ef6f  mov     rcx, [rbp+var_18]
0x14001ef73  test    rcx, rcx
0x14001ef76  jz      short loc_14001EF7D
0x14001ef78  call    RxRevert
0x14001ef7d  mov     rcx, [rbp+DestinationString.Buffer]; P
0x14001ef81  test    rcx, rcx
0x14001ef84  jz      short loc_14001EF94
0x14001ef86  xor     edx, edx; Tag
0x14001ef88  call    cs:__imp_ExFreePoolWithTag
0x14001ef8f  nop     dword ptr [rax+rax+00h]
0x14001ef94  mov     eax, ebx
0x14001ef96  mov     rbx, [rsp+50h+arg_0]
0x14001ef9e  add     rsp, 50h
0x14001efa2  pop     r15
0x14001efa4  pop     r14
0x14001efa6  pop     r13
0x14001efa8  pop     r12
0x14001efaa  pop     rdi
0x14001efab  pop     rsi
0x14001efac  pop     rbp
0x14001efad  retn
```
