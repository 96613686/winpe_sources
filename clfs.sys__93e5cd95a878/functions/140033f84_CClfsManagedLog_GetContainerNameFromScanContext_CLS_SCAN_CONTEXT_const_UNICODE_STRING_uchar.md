# CClfsManagedLog::GetContainerNameFromScanContext(_CLS_SCAN_CONTEXT const &,_UNICODE_STRING &,uchar &)

- ea: `0x140033f84`
- end: `0x140034189`
- name: `?GetContainerNameFromScanContext@CClfsManagedLog@@AEAAJAEBU_CLS_SCAN_CONTEXT@@AEAU_UNICODE_STRING@@AEAE@Z`
- size: `517`
- prototype: `int(CClfsManagedLog *__hidden this, const struct _CLS_SCAN_CONTEXT *, struct _UNICODE_STRING *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140034e0c`
- `0x14006f1f4`

## callees

- `0x140018280`
- `0x140033f84`
- `0x14004bcc0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140034118`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003413e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140034118`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003413e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14003412b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14003412b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400340df`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400340f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140034164`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400340df`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400340f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140034164`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003403f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400340a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400340b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003414f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003403f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400340a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400340b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003414f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140034004`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140034025`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140034004`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140034025`

## pseudocode

```c
__int64 __fastcall CClfsManagedLog::GetContainerNameFromScanContext(
        PLOG_FILE_OBJECT *this,
        const struct _CLS_SCAN_CONTEXT *a2,
        struct _UNICODE_STRING *a3,
        unsigned __int8 *a4)
{
  PCLS_CONTAINER_INFORMATION pinfoContainer; // rdx
  unsigned __int8 v9; // di
  PVOID PoolWithTag; // rax
  wchar_t *Buffer; // rcx
  void *v12; // r15
  NTSTATUS ContainerName; // r14d
  UNICODE_STRING Destination; // [rsp+20h] [rbp-20h] BYREF
  UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF

  *a4 = 0;
  pinfoContainer = a2->pinfoContainer;
  *(_QWORD *)&Destination.Length = 0;
  Destination.Buffer = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  if ( pinfoContainer->FileNameActualLength == pinfoContainer->FileNameLength )
  {
    RtlInitUnicodeString(a3, pinfoContainer->FileName);
    v9 = 0;
  }
  else
  {
    v9 = 1;
    a3->Length = 2 * (LOWORD(pinfoContainer->FileNameActualLength) + 1);
    a3->MaximumLength = 2 * (LOWORD(a2->pinfoContainer->FileNameActualLength) + 1);
    a3->Buffer = (wchar_t *)ExAllocatePoolWithTag(
                              PagedPool,
                              2LL * (a2->pinfoContainer->FileNameActualLength + 1),
                              0x744D6C43u);
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, 2LL * (a2->pinfoContainer->FileNameActualLength + 1), 0x744D6C43u);
    Buffer = a3->Buffer;
    v12 = PoolWithTag;
    if ( !PoolWithTag )
    {
      ExFreePoolWithTag(Buffer, 0);
      ContainerName = -1073741670;
LABEL_6:
      a3->Buffer = 0;
      return (unsigned int)ContainerName;
    }
    memset(Buffer, 0, 2LL * (a2->pinfoContainer->FileNameActualLength + 1));
    memset(v12, 0, 2LL * (a2->pinfoContainer->FileNameActualLength + 1));
    ContainerName = ClfsGetContainerName(this[42], a2->pinfoContainer->LogicalContainerId, a3, 0);
    if ( ContainerName < 0 )
    {
      ExFreePoolWithTag(a3->Buffer, 0);
      ExFreePoolWithTag(v12, 0);
      goto LABEL_6;
    }
    RtlInitUnicodeString(&DestinationString, L"\\??\\");
    RtlInitUnicodeString(&Destination, (PCWSTR)v12);
    Destination.MaximumLength = 2 * (LOWORD(a2->pinfoContainer->FileNameActualLength) + 1);
    RtlCopyUnicodeString(&Destination, &DestinationString);
    RtlAppendUnicodeStringToString(&Destination, a3);
    RtlCopyUnicodeString(a3, &Destination);
    ExFreePoolWithTag(v12, 0);
  }
  *a4 = v9;
  return 0;
}

```

## disassembly

```asm
0x140033f84  push    rbp
0x140033f86  push    rbx
0x140033f87  push    rsi
0x140033f88  push    rdi
0x140033f89  push    r12
0x140033f8b  push    r14
0x140033f8d  push    r15
0x140033f8f  mov     rbp, rsp
0x140033f92  sub     rsp, 40h
0x140033f96  xor     eax, eax
0x140033f98  mov     rsi, rdx
0x140033f9b  mov     [r9], al
0x140033f9e  mov     r12, r9
0x140033fa1  mov     rdx, [rdx+30h]
0x140033fa5  mov     rbx, r8
0x140033fa8  mov     qword ptr [rbp+Destination.Length], rax
0x140033fac  mov     r14, rcx
0x140033faf  mov     [rbp+Destination.Buffer], rax
0x140033fb3  mov     qword ptr [rbp+DestinationString.Length], rax
0x140033fb7  mov     [rbp+DestinationString.Buffer], rax
0x140033fbb  mov     eax, [rdx+2Ch]
0x140033fbe  cmp     [rdx+28h], eax
0x140033fc1  jz      loc_14003415D
0x140033fc7  movzx   eax, word ptr [rdx+28h]
0x140033fcb  mov     edi, 1
0x140033fd0  add     ax, di
0x140033fd3  mov     r15d, 744D6C43h
0x140033fd9  add     ax, ax
0x140033fdc  mov     [r8], ax
0x140033fe0  mov     rax, [rsi+30h]
0x140033fe4  movzx   ecx, word ptr [rax+28h]
0x140033fe8  add     cx, di
0x140033feb  add     cx, cx
0x140033fee  mov     [r8+2], cx
0x140033ff3  mov     r8d, r15d; Tag
0x140033ff6  mov     rax, [rsi+30h]
0x140033ffa  mov     ecx, edi; PoolType
0x140033ffc  mov     edx, [rax+28h]
0x140033fff  add     edx, edi
0x140034001  add     rdx, rdx; NumberOfBytes
0x140034004  call    cs:__imp_ExAllocatePoolWithTag
0x14003400b  nop     dword ptr [rax+rax+00h]
0x140034010  mov     [rbx+8], rax
0x140034014  mov     r8d, r15d; Tag
0x140034017  mov     rax, [rsi+30h]
0x14003401b  mov     ecx, edi; PoolType
0x14003401d  mov     edx, [rax+28h]
0x140034020  add     edx, edi
0x140034022  add     rdx, rdx; NumberOfBytes
0x140034025  call    cs:__imp_ExAllocatePoolWithTag
0x14003402c  nop     dword ptr [rax+rax+00h]
0x140034031  mov     rcx, [rbx+8]; void *
0x140034035  xor     edx, edx; Val
0x140034037  mov     r15, rax
0x14003403a  test    rax, rax
0x14003403d  jnz     short loc_140034053
0x14003403f  call    cs:__imp_ExFreePoolWithTag
0x140034046  nop     dword ptr [rax+rax+00h]
0x14003404b  mov     r14d, 0C000009Ah
0x140034051  jmp     short loc_1400340C4
0x140034053  mov     rax, [rsi+30h]
0x140034057  mov     r8d, [rax+28h]
0x14003405b  add     r8d, edi
0x14003405e  add     r8, r8; Size
0x140034061  call    memset
0x140034066  mov     rax, [rsi+30h]
0x14003406a  xor     edx, edx; Val
0x14003406c  mov     rcx, r15; void *
0x14003406f  mov     r8d, [rax+28h]
0x140034073  add     r8d, edi
0x140034076  add     r8, r8; Size
0x140034079  call    memset
0x14003407e  mov     rdx, [rsi+30h]
0x140034082  xor     r9d, r9d; pcActualLenContainerName
0x140034085  mov     rcx, [r14+150h]; plfoLog
0x14003408c  mov     r8, rbx; puszContainerName
0x14003408f  mov     edx, [rdx+238h]; cidLogicalContainer
0x140034095  call    ClfsGetContainerName
0x14003409a  mov     r14d, eax
0x14003409d  test    eax, eax
0x14003409f  jns     short loc_1400340D4
0x1400340a1  mov     rcx, [rbx+8]; P
0x1400340a5  xor     edx, edx; Tag
0x1400340a7  call    cs:__imp_ExFreePoolWithTag
0x1400340ae  nop     dword ptr [rax+rax+00h]
0x1400340b3  xor     edx, edx; Tag
0x1400340b5  mov     rcx, r15; P
0x1400340b8  call    cs:__imp_ExFreePoolWithTag
0x1400340bf  nop     dword ptr [rax+rax+00h]
0x1400340c4  mov     qword ptr [rbx+8], 0
0x1400340cc  mov     eax, r14d
0x1400340cf  jmp     loc_140034179
0x1400340d4  lea     rdx, asc_14001C860; "\\??\\"
0x1400340db  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400340df  call    cs:__imp_RtlInitUnicodeString
0x1400340e6  nop     dword ptr [rax+rax+00h]
0x1400340eb  mov     rdx, r15; SourceString
0x1400340ee  lea     rcx, [rbp+Destination]; DestinationString
0x1400340f2  call    cs:__imp_RtlInitUnicodeString
0x1400340f9  nop     dword ptr [rax+rax+00h]
0x1400340fe  mov     rax, [rsi+30h]
0x140034102  lea     rdx, [rbp+DestinationString]; SourceString
0x140034106  movzx   ecx, word ptr [rax+28h]
0x14003410a  add     cx, di
0x14003410d  add     cx, cx
0x140034110  mov     [rbp+Destination.MaximumLength], cx
0x140034114  lea     rcx, [rbp+Destination]; DestinationString
0x140034118  call    cs:__imp_RtlCopyUnicodeString
0x14003411f  nop     dword ptr [rax+rax+00h]
0x140034124  mov     rdx, rbx; Source
0x140034127  lea     rcx, [rbp+Destination]; Destination
0x14003412b  call    cs:__imp_RtlAppendUnicodeStringToString
0x140034132  nop     dword ptr [rax+rax+00h]
0x140034137  lea     rdx, [rbp+Destination]; SourceString
0x14003413b  mov     rcx, rbx; DestinationString
0x14003413e  call    cs:__imp_RtlCopyUnicodeString
0x140034145  nop     dword ptr [rax+rax+00h]
0x14003414a  xor     edx, edx; Tag
0x14003414c  mov     rcx, r15; P
0x14003414f  call    cs:__imp_ExFreePoolWithTag
0x140034156  nop     dword ptr [rax+rax+00h]
0x14003415b  jmp     short loc_140034173
0x14003415d  add     rdx, 30h ; '0'; SourceString
0x140034161  mov     rcx, rbx; DestinationString
0x140034164  call    cs:__imp_RtlInitUnicodeString
0x14003416b  nop     dword ptr [rax+rax+00h]
0x140034170  xor     dil, dil
0x140034173  mov     [r12], dil
0x140034177  xor     eax, eax
0x140034179  add     rsp, 40h
0x14003417d  pop     r15
0x14003417f  pop     r14
0x140034181  pop     r12
0x140034183  pop     rdi
0x140034184  pop     rsi
0x140034185  pop     rbx
0x140034186  pop     rbp
0x140034187  retn
```
