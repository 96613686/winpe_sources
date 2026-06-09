# LsapDbFindNextSidWithRight(void *,ulong *,_LUID *,ulong *,_LSAPR_SID * *)

- ea: `0x18007a9cc`
- end: `0x18007b017`
- name: `?LsapDbFindNextSidWithRight@@YAJPEAXPEAKPEAU_LUID@@1PEAPEAU_LSAPR_SID@@@Z`
- size: `1611`
- prototype: `__int64 __fastcall(void *, unsigned int *, struct _LUID *, unsigned int *, struct _LSAPR_SID **)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007a7e8`

## callees

- `0x18000c300`
- `0x180016f70`
- `0x18007a9cc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007abf1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007af64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007abf1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007af64`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007ad6b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007af21`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007ad6b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007af21`
- `ntdll!RtlFreeHeap` at `0x18007ac80`
- `ntdll!RtlFreeHeap` at `0x18007af99`
- `ntdll!RtlFreeHeap` at `0x18007ac80`
- `ntdll!RtlFreeHeap` at `0x18007af99`
- `ntdll!RtlpNtOpenKey` at `0x18007aa76`
- `ntdll!RtlpNtOpenKey` at `0x18007ad0a`
- `ntdll!RtlpNtOpenKey` at `0x18007aed7`
- `ntdll!RtlpNtOpenKey` at `0x18007aa76`
- `ntdll!RtlpNtOpenKey` at `0x18007ad0a`
- `ntdll!RtlpNtOpenKey` at `0x18007aed7`
- `ntdll!RtlpNtEnumerateSubKey` at `0x18007aab8`
- `ntdll!RtlpNtEnumerateSubKey` at `0x18007aab8`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18007ab24`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18007ac55`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18007acba`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18007ae40`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18007ae82`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18007ab24`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18007ac55`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18007acba`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18007ae40`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18007ae82`
- `ntdll!RtlpNtQueryValueKey` at `0x18007ad4a`
- `ntdll!RtlpNtQueryValueKey` at `0x18007ad95`
- `ntdll!RtlpNtQueryValueKey` at `0x18007af03`
- `ntdll!RtlpNtQueryValueKey` at `0x18007af4b`
- `ntdll!RtlpNtQueryValueKey` at `0x18007ad4a`
- `ntdll!RtlpNtQueryValueKey` at `0x18007ad95`
- `ntdll!RtlpNtQueryValueKey` at `0x18007af03`
- `ntdll!RtlpNtQueryValueKey` at `0x18007af4b`
- `ntdll!RtlAllocateHeap` at `0x18007ab03`
- `ntdll!RtlAllocateHeap` at `0x18007ac34`
- `ntdll!RtlAllocateHeap` at `0x18007ae1f`
- `ntdll!RtlAllocateHeap` at `0x18007ab03`
- `ntdll!RtlAllocateHeap` at `0x18007ac34`
- `ntdll!RtlAllocateHeap` at `0x18007ae1f`
- `ntdll!RtlFreeUnicodeString` at `0x18007b006`
- `ntdll!RtlFreeUnicodeString` at `0x18007b006`
- `ntdll!NtClose` at `0x18007ab75`
- `ntdll!NtClose` at `0x18007ab9c`
- `ntdll!NtClose` at `0x18007ade2`
- `ntdll!NtClose` at `0x18007ab75`
- `ntdll!NtClose` at `0x18007ab9c`
- `ntdll!NtClose` at `0x18007ade2`
- `ntdll!RtlAppendUnicodeToString` at `0x18007ab45`
- `ntdll!RtlAppendUnicodeToString` at `0x18007ac9d`
- `ntdll!RtlAppendUnicodeToString` at `0x18007ae61`
- `ntdll!RtlAppendUnicodeToString` at `0x18007ab45`
- `ntdll!RtlAppendUnicodeToString` at `0x18007ac9d`
- `ntdll!RtlAppendUnicodeToString` at `0x18007ae61`

## pseudocode

```c
__int64 __fastcall LsapDbFindNextSidWithRight(
        void *a1,
        unsigned int *a2,
        struct _LUID *a3,
        unsigned int *a4,
        struct _LSAPR_SID **a5)
{
  unsigned int *v8; // r15
  __int64 v9; // rdx
  NTSTATUS appended; // ebx
  const UNICODE_STRING *v11; // rdx
  NTSTATUS v13; // eax
  unsigned int *v14; // rax
  unsigned int i; // ecx
  struct _LSAPR_SID *v16; // rax
  struct _LSAPR_SID *v17; // rdi
  struct _UNICODE_STRING Destination; // [rsp+38h] [rbp-51h] BYREF
  ULONG v19; // [rsp+48h] [rbp-41h] BYREF
  HANDLE v20; // [rsp+50h] [rbp-39h] BYREF
  HANDLE KeyHandle; // [rsp+58h] [rbp-31h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+60h] [rbp-29h] BYREF
  struct _UNICODE_STRING SubKeyName; // [rsp+70h] [rbp-19h] BYREF
  HANDLE Handle; // [rsp+80h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-1h] BYREF
  ULONG DataLength; // [rsp+E8h] [rbp+5Fh] BYREF
  int v27; // [rsp+ECh] [rbp+63h]

  v27 = HIDWORD(a1);
  v19 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DataLength = 0;
  *(_QWORD *)&SubKeyName.Length = 0;
  *(_QWORD *)&UnicodeString.Length = 0;
  *(_QWORD *)&Destination.Length = 0;
  KeyHandle = 0;
  v20 = 0;
  Handle = 0;
  v8 = 0;
  SubKeyName.Buffer = 0;
  UnicodeString.Buffer = 0;
  Destination.Buffer = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = (HANDLE)*((_QWORD *)LsapDbHandle + 12);
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)qword_18019F5A0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  appended = RtlpNtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0);
  if ( appended < 0 )
  {
    KeyHandle = 0;
    goto LABEL_10;
  }
  *(_DWORD *)&SubKeyName.Length = 0x1000000;
  SubKeyName.Buffer = (PWSTR)LsapAllocate(256);
  if ( !SubKeyName.Buffer )
    goto LABEL_9;
  appended = RtlpNtEnumerateSubKey(KeyHandle, &SubKeyName, *a2, 0);
  if ( appended < 0 )
    goto LABEL_10;
  if ( a3 )
  {
    Destination.Length = 0;
    Destination.MaximumLength = stru_18019E820.Length + SubKeyName.Length + 2;
    Destination.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.MaximumLength);
    if ( Destination.Buffer )
    {
      appended = RtlAppendUnicodeStringToString(&Destination, &SubKeyName);
      if ( appended >= 0 )
      {
        appended = RtlAppendUnicodeToString(&Destination, L"\\");
        if ( appended >= 0 )
        {
          v11 = &stru_18019E820;
          goto LABEL_32;
        }
      }
LABEL_28:
      if ( Destination.Buffer )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.Buffer);
        Destination.Buffer = 0;
      }
      goto LABEL_33;
    }
LABEL_61:
    appended = -1073741670;
    goto LABEL_28;
  }
  if ( !a4 )
    goto LABEL_48;
  Destination.Length = 0;
  Destination.MaximumLength = stru_18019E9F0.Length + SubKeyName.Length + 2;
  Destination.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.MaximumLength);
  if ( !Destination.Buffer )
    goto LABEL_61;
  appended = RtlAppendUnicodeStringToString(&Destination, &SubKeyName);
  if ( appended < 0 )
    goto LABEL_28;
  appended = RtlAppendUnicodeToString(&Destination, L"\\");
  if ( appended < 0 )
    goto LABEL_28;
  v11 = &stru_18019E9F0;
LABEL_32:
  appended = RtlAppendUnicodeStringToString(&Destination, v11);
  if ( appended < 0 )
    goto LABEL_28;
LABEL_33:
  if ( appended < 0 )
    goto LABEL_10;
  ObjectAttributes.RootDirectory = KeyHandle;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &Destination;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v13 = RtlpNtOpenKey(&Handle, 0x20019u, &ObjectAttributes, 0);
  appended = v13;
  if ( v13 < 0 )
  {
    if ( v13 == -1073741772 )
    {
      ++*a2;
      appended = 262;
    }
    goto LABEL_37;
  }
  DataLength = 0;
  appended = RtlpNtQueryValueKey(Handle, 0, 0, &DataLength, 0);
  if ( appended != -2147483643 )
    goto LABEL_10;
  v14 = (unsigned int *)LocalAlloc(0x40u, DataLength);
  v8 = v14;
  if ( !v14 )
  {
LABEL_9:
    appended = -1073741670;
    goto LABEL_10;
  }
  appended = RtlpNtQueryValueKey(Handle, 0, v14, &DataLength, 0);
  if ( appended < 0 )
    goto LABEL_10;
  if ( a3 )
  {
    for ( i = 0; i < *v8; ++i )
    {
      v9 = 3LL * i;
      if ( v8[3 * i + 2] == a3->LowPart && v8[3 * i + 3] == a3->HighPart )
        goto LABEL_48;
    }
    goto LABEL_46;
  }
  if ( !a4 || (*v8 & *a4) == 0 )
  {
LABEL_46:
    appended = 262;
LABEL_47:
    ++*a2;
    goto LABEL_10;
  }
LABEL_48:
  UnicodeString.Length = 0;
  UnicodeString.MaximumLength = stru_18019E830.Length + SubKeyName.Length + 2;
  UnicodeString.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, UnicodeString.MaximumLength);
  if ( !UnicodeString.Buffer )
  {
    appended = -1073741670;
    goto LABEL_58;
  }
  appended = RtlAppendUnicodeStringToString(&UnicodeString, &SubKeyName);
  if ( appended < 0
    || (appended = RtlAppendUnicodeToString(&UnicodeString, L"\\"), appended < 0)
    || (appended = RtlAppendUnicodeStringToString(&UnicodeString, &stru_18019E830), appended < 0) )
  {
LABEL_58:
    if ( UnicodeString.Buffer )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, UnicodeString.Buffer);
      UnicodeString.Buffer = 0;
    }
  }
  if ( appended < 0 )
    goto LABEL_10;
  ObjectAttributes.RootDirectory = KeyHandle;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &UnicodeString;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  appended = RtlpNtOpenKey(&v20, 0x20019u, &ObjectAttributes, 0);
  if ( appended < 0 )
  {
LABEL_37:
    v20 = 0;
    goto LABEL_10;
  }
  v19 = 0;
  appended = RtlpNtQueryValueKey(v20, 0, 0, &v19, 0);
  if ( appended != -2147483643 )
    goto LABEL_10;
  v16 = (struct _LSAPR_SID *)LocalAlloc(0x40u, v19);
  v17 = v16;
  if ( !v16 )
    goto LABEL_9;
  appended = RtlpNtQueryValueKey(v20, 0, v16, &v19, 0);
  if ( appended >= 0 )
  {
    *a5 = v17;
    goto LABEL_47;
  }
  LocalFree(v17);
  *a5 = 0;
LABEL_10:
  if ( Handle )
    NtClose(Handle);
  if ( v8 )
    LocalFree(v8);
  if ( v20 )
    NtClose(v20);
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( SubKeyName.Buffer )
    LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)SubKeyName.Buffer, (void *)v9);
  if ( Destination.Buffer )
    LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)Destination.Buffer, (void *)v9);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18007a9cc  mov     rax, rsp
0x18007a9cf  mov     [rax+10h], rbx
0x18007a9d3  mov     [rax+18h], rdi
0x18007a9d7  mov     [rax+8], rcx
0x18007a9db  push    rbp
0x18007a9dc  push    r12
0x18007a9de  push    r13
0x18007a9e0  push    r14
0x18007a9e2  push    r15
0x18007a9e4  lea     rbp, [rax-57h]
0x18007a9e8  sub     rsp, 0B0h
0x18007a9ef  mov     rax, cs:?LsapDbHandle@@3PEAXEA; void * LsapDbHandle
0x18007a9f6  xor     r13d, r13d
0x18007a9f9  xorps   xmm0, xmm0
0x18007a9fc  mov     [rbp+4Fh+var_90], r13d
0x18007aa00  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x18007aa04  mov     [rbp+4Fh+DataLength], r13d
0x18007aa08  mov     rdi, r9
0x18007aa0b  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x18007aa0f  mov     qword ptr [rbp+4Fh+SubKeyName.Length], r13
0x18007aa13  mov     r12, r8
0x18007aa16  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18007aa1a  mov     qword ptr [rbp+4Fh+UnicodeString.Length], r13
0x18007aa1e  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18007aa22  mov     qword ptr [rbp+4Fh+Destination.Length], r13
0x18007aa26  mov     r14, rdx
0x18007aa29  mov     [rbp+4Fh+KeyHandle], r13
0x18007aa2d  xor     r9d, r9d; Unused
0x18007aa30  mov     [rbp+4Fh+var_88], r13
0x18007aa34  mov     edx, 20019h; DesiredAccess
0x18007aa39  mov     [rbp+4Fh+Handle], r13
0x18007aa3d  mov     r15d, r13d
0x18007aa40  mov     [rbp+4Fh+SubKeyName.Buffer], r13
0x18007aa44  mov     [rbp+4Fh+UnicodeString.Buffer], r13
0x18007aa48  mov     [rbp+4Fh+Destination.Buffer], r13
0x18007aa4c  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18007aa53  mov     rcx, [rax+60h]
0x18007aa57  lea     rax, qword_18019F5A0
0x18007aa5e  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rcx
0x18007aa62  lea     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x18007aa66  mov     [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x18007aa6d  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x18007aa71  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18007aa76  call    cs:__imp_RtlpNtOpenKey
0x18007aa7d  nop     dword ptr [rax+rax+00h]
0x18007aa82  mov     ebx, eax
0x18007aa84  test    eax, eax
0x18007aa86  js      loc_18007AFAE
0x18007aa8c  mov     ecx, 100h
0x18007aa91  mov     dword ptr [rbp+4Fh+SubKeyName.Length], 1000000h
0x18007aa98  call    LsapAllocate
0x18007aa9d  mov     [rbp+4Fh+SubKeyName.Buffer], rax
0x18007aaa1  test    rax, rax
0x18007aaa4  jz      loc_18007AB67
0x18007aaaa  mov     r8d, [r14]; Index
0x18007aaad  lea     rdx, [rbp+4Fh+SubKeyName]; SubKeyName
0x18007aab1  mov     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x18007aab5  xor     r9d, r9d; Unused
0x18007aab8  call    cs:__imp_RtlpNtEnumerateSubKey
0x18007aabf  nop     dword ptr [rax+rax+00h]
0x18007aac4  mov     ebx, eax
0x18007aac6  test    eax, eax
0x18007aac8  js      loc_18007AB6C
0x18007aace  test    r12, r12
0x18007aad1  jz      loc_18007ABFF
0x18007aad7  movzx   eax, [rbp+4Fh+SubKeyName.Length]
0x18007aadb  xor     edx, edx; Flags
0x18007aadd  mov     [rbp+4Fh+Destination.Length], r13w
0x18007aae2  add     ax, 2
0x18007aae6  add     ax, cs:stru_18019E820.Length
0x18007aaed  movzx   r8d, ax; Size
0x18007aaf1  mov     [rbp+4Fh+Destination.MaximumLength], r8w
0x18007aaf6  mov     rcx, gs:60h
0x18007aaff  mov     rcx, [rcx+30h]; HeapHandle
0x18007ab03  call    cs:__imp_RtlAllocateHeap
0x18007ab0a  nop     dword ptr [rax+rax+00h]
0x18007ab0f  mov     [rbp+4Fh+Destination.Buffer], rax
0x18007ab13  test    rax, rax
0x18007ab16  jz      loc_18007AFB7
0x18007ab1c  lea     rdx, [rbp+4Fh+SubKeyName]; Source
0x18007ab20  lea     rcx, [rbp+4Fh+Destination]; Destination
0x18007ab24  call    cs:__imp_RtlAppendUnicodeStringToString
0x18007ab2b  nop     dword ptr [rax+rax+00h]
0x18007ab30  mov     ebx, eax
0x18007ab32  test    eax, eax
0x18007ab34  js      loc_18007AC67
0x18007ab3a  lea     rdx, Source; "\\"
0x18007ab41  lea     rcx, [rbp+4Fh+Destination]; Destination
0x18007ab45  call    cs:__imp_RtlAppendUnicodeToString
0x18007ab4c  nop     dword ptr [rax+rax+00h]
0x18007ab51  mov     ebx, eax
0x18007ab53  test    eax, eax
0x18007ab55  js      loc_18007AC67
0x18007ab5b  lea     rdx, stru_18019E820
0x18007ab62  jmp     loc_18007ACB6
0x18007ab67  mov     ebx, 0C000009Ah
0x18007ab6c  mov     rcx, [rbp+4Fh+Handle]; Handle
0x18007ab70  test    rcx, rcx
0x18007ab73  jz      short loc_18007AB81
0x18007ab75  call    cs:__imp_NtClose
0x18007ab7c  nop     dword ptr [rax+rax+00h]
0x18007ab81  test    r15, r15
0x18007ab84  jnz     short loc_18007ABEE
0x18007ab86  mov     rcx, [rbp+4Fh+var_88]; Handle
0x18007ab8a  test    rcx, rcx
0x18007ab8d  jnz     loc_18007ADE2
0x18007ab93  mov     rcx, [rbp+4Fh+KeyHandle]; Handle
0x18007ab97  test    rcx, rcx
0x18007ab9a  jz      short loc_18007ABA8
0x18007ab9c  call    cs:__imp_NtClose
0x18007aba3  nop     dword ptr [rax+rax+00h]
0x18007aba8  cmp     [rbp+4Fh+UnicodeString.Buffer], r13
0x18007abac  jnz     loc_18007B002
0x18007abb2  mov     rcx, [rbp+4Fh+SubKeyName.Buffer]; struct _RTL_BALANCED_NODE *
0x18007abb6  test    rcx, rcx
0x18007abb9  jz      short loc_18007ABC0
0x18007abbb  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18007abc0  mov     rcx, [rbp+4Fh+Destination.Buffer]; struct _RTL_BALANCED_NODE *
0x18007abc4  test    rcx, rcx
0x18007abc7  jz      short loc_18007ABCE
0x18007abc9  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18007abce  lea     r11, [rsp+0D0h+var_20]
0x18007abd6  mov     eax, ebx
0x18007abd8  mov     rbx, [r11+38h]
0x18007abdc  mov     rdi, [r11+40h]
0x18007abe0  mov     rsp, r11
0x18007abe3  pop     r15
0x18007abe5  pop     r14
0x18007abe7  pop     r13
0x18007abe9  pop     r12
0x18007abeb  pop     rbp
0x18007abec  retn
0x18007abee  mov     rcx, r15; hMem
0x18007abf1  call    cs:__imp_LocalFree
0x18007abf8  nop     dword ptr [rax+rax+00h]
0x18007abfd  jmp     short loc_18007AB86
0x18007abff  test    rdi, rdi
0x18007ac02  jz      loc_18007ADF3
0x18007ac08  movzx   eax, [rbp+4Fh+SubKeyName.Length]
0x18007ac0c  xor     edx, edx; Flags
0x18007ac0e  mov     [rbp+4Fh+Destination.Length], r13w
0x18007ac13  add     ax, 2
0x18007ac17  add     ax, cs:stru_18019E9F0.Length
0x18007ac1e  movzx   r8d, ax; Size
0x18007ac22  mov     [rbp+4Fh+Destination.MaximumLength], r8w
0x18007ac27  mov     rcx, gs:60h
0x18007ac30  mov     rcx, [rcx+30h]; HeapHandle
0x18007ac34  call    cs:__imp_RtlAllocateHeap
0x18007ac3b  nop     dword ptr [rax+rax+00h]
0x18007ac40  mov     [rbp+4Fh+Destination.Buffer], rax
0x18007ac44  test    rax, rax
0x18007ac47  jz      loc_18007AFB7
0x18007ac4d  lea     rdx, [rbp+4Fh+SubKeyName]; Source
0x18007ac51  lea     rcx, [rbp+4Fh+Destination]; Destination
0x18007ac55  call    cs:__imp_RtlAppendUnicodeStringToString
0x18007ac5c  nop     dword ptr [rax+rax+00h]
0x18007ac61  mov     ebx, eax
0x18007ac63  test    eax, eax
0x18007ac65  jns     short loc_18007AC92
0x18007ac67  cmp     [rbp+4Fh+Destination.Buffer], r13
0x18007ac6b  jz      short loc_18007ACCC
0x18007ac6d  mov     rcx, gs:60h
0x18007ac76  xor     edx, edx; Flags
0x18007ac78  mov     r8, [rbp+4Fh+Destination.Buffer]; P
0x18007ac7c  mov     rcx, [rcx+30h]; HeapHandle
0x18007ac80  call    cs:__imp_RtlFreeHeap
0x18007ac87  nop     dword ptr [rax+rax+00h]
0x18007ac8c  mov     [rbp+4Fh+Destination.Buffer], r13
0x18007ac90  jmp     short loc_18007ACCC
0x18007ac92  lea     rdx, Source; "\\"
0x18007ac99  lea     rcx, [rbp+4Fh+Destination]; Destination
0x18007ac9d  call    cs:__imp_RtlAppendUnicodeToString
0x18007aca4  nop     dword ptr [rax+rax+00h]
0x18007aca9  mov     ebx, eax
0x18007acab  test    eax, eax
0x18007acad  js      short loc_18007AC67
0x18007acaf  lea     rdx, stru_18019E9F0; Source
0x18007acb6  lea     rcx, [rbp+4Fh+Destination]; Destination
0x18007acba  call    cs:__imp_RtlAppendUnicodeStringToString
0x18007acc1  nop     dword ptr [rax+rax+00h]
0x18007acc6  mov     ebx, eax
0x18007acc8  test    eax, eax
0x18007acca  js      short loc_18007AC67
0x18007accc  test    ebx, ebx
0x18007acce  js      loc_18007AB6C
0x18007acd4  mov     rax, [rbp+4Fh+KeyHandle]
0x18007acd8  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18007acdc  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rax
0x18007ace0  lea     rcx, [rbp+4Fh+Handle]; KeyHandle
0x18007ace4  lea     rax, [rbp+4Fh+Destination]
0x18007ace8  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18007acef  xorps   xmm0, xmm0
0x18007acf2  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x18007acf6  xor     r9d, r9d; Unused
0x18007acf9  mov     [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x18007ad00  mov     edx, 20019h; DesiredAccess
0x18007ad05  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18007ad0a  call    cs:__imp_RtlpNtOpenKey
0x18007ad11  nop     dword ptr [rax+rax+00h]
0x18007ad16  mov     ebx, eax
0x18007ad18  test    eax, eax
0x18007ad1a  jns     short loc_18007AD34
0x18007ad1c  cmp     eax, 0C0000034h
0x18007ad21  jnz     short loc_18007AD2B
0x18007ad23  inc     dword ptr [r14]
0x18007ad26  mov     ebx, 106h
0x18007ad2b  mov     [rbp+4Fh+var_88], r13
0x18007ad2f  jmp     loc_18007AB6C
0x18007ad34  mov     rcx, [rbp+4Fh+Handle]; KeyHandle
0x18007ad38  lea     r9, [rbp+4Fh+DataLength]; DataLength
0x18007ad3c  xor     r8d, r8d; Data
0x18007ad3f  mov     [rbp+4Fh+DataLength], r13d
0x18007ad43  xor     edx, edx; Type
0x18007ad45  mov     qword ptr [rsp+0D0h+Unused], r13; Unused
0x18007ad4a  call    cs:__imp_RtlpNtQueryValueKey
0x18007ad51  nop     dword ptr [rax+rax+00h]
0x18007ad56  mov     ebx, eax
0x18007ad58  cmp     eax, 80000005h
0x18007ad5d  jnz     loc_18007AB6C
0x18007ad63  mov     edx, [rbp+4Fh+DataLength]; uBytes
0x18007ad66  mov     ecx, 40h ; '@'; uFlags
0x18007ad6b  call    cs:__imp_LocalAlloc
0x18007ad72  nop     dword ptr [rax+rax+00h]
0x18007ad77  mov     r15, rax
0x18007ad7a  test    rax, rax
0x18007ad7d  jz      loc_18007AB67
0x18007ad83  mov     rcx, [rbp+4Fh+Handle]; KeyHandle
0x18007ad87  lea     r9, [rbp+4Fh+DataLength]; DataLength
0x18007ad8b  mov     r8, rax; Data
0x18007ad8e  mov     qword ptr [rsp+0D0h+Unused], r13; Unused
0x18007ad93  xor     edx, edx; Type
0x18007ad95  call    cs:__imp_RtlpNtQueryValueKey
0x18007ad9c  nop     dword ptr [rax+rax+00h]
0x18007ada1  mov     ebx, eax
0x18007ada3  test    eax, eax
0x18007ada5  js      loc_18007AB6C
0x18007adab  test    r12, r12
0x18007adae  jz      loc_18007AFD6
0x18007adb4  mov     ecx, r13d
0x18007adb7  cmp     ecx, [r15]
0x18007adba  jnb     short loc_18007ADD5
0x18007adbc  mov     eax, ecx
0x18007adbe  lea     rdx, [rax+rax*2]
0x18007adc2  mov     eax, [r12]
0x18007adc6  cmp     [r15+rdx*4+8], eax
0x18007adcb  jz      loc_18007AFC1
0x18007add1  inc     ecx
0x18007add3  jmp     short loc_18007ADB7
0x18007add5  mov     ebx, 106h
0x18007adda  inc     dword ptr [r14]
0x18007addd  jmp     loc_18007AB6C
0x18007ade2  call    cs:__imp_NtClose
0x18007ade9  nop     dword ptr [rax+rax+00h]
0x18007adee  jmp     loc_18007AB93
0x18007adf3  movzx   eax, [rbp+4Fh+SubKeyName.Length]
0x18007adf7  xor     edx, edx; Flags
0x18007adf9  mov     [rbp+4Fh+UnicodeString.Length], r13w
0x18007adfe  add     ax, 2
0x18007ae02  add     ax, cs:stru_18019E830.Length
0x18007ae09  movzx   r8d, ax; Size
0x18007ae0d  mov     [rbp+4Fh+UnicodeString.MaximumLength], r8w
0x18007ae12  mov     rcx, gs:60h
0x18007ae1b  mov     rcx, [rcx+30h]; HeapHandle
0x18007ae1f  call    cs:__imp_RtlAllocateHeap
0x18007ae26  nop     dword ptr [rax+rax+00h]
0x18007ae2b  mov     [rbp+4Fh+UnicodeString.Buffer], rax
0x18007ae2f  test    rax, rax
0x18007ae32  jz      loc_18007AFEF
0x18007ae38  lea     rdx, [rbp+4Fh+SubKeyName]; Source
0x18007ae3c  lea     rcx, [rbp+4Fh+UnicodeString]; Destination
0x18007ae40  call    cs:__imp_RtlAppendUnicodeStringToString
0x18007ae47  nop     dword ptr [rax+rax+00h]
0x18007ae4c  mov     ebx, eax
0x18007ae4e  test    eax, eax
0x18007ae50  js      loc_18007AF7C
0x18007ae56  lea     rdx, Source; "\\"
0x18007ae5d  lea     rcx, [rbp+4Fh+UnicodeString]; Destination
0x18007ae61  call    cs:__imp_RtlAppendUnicodeToString
0x18007ae68  nop     dword ptr [rax+rax+00h]
0x18007ae6d  mov     ebx, eax
0x18007ae6f  test    eax, eax
0x18007ae71  js      loc_18007AF7C
0x18007ae77  lea     rdx, stru_18019E830; Source
0x18007ae7e  lea     rcx, [rbp+4Fh+UnicodeString]; Destination
0x18007ae82  call    cs:__imp_RtlAppendUnicodeStringToString
0x18007ae89  nop     dword ptr [rax+rax+00h]
0x18007ae8e  mov     ebx, eax
0x18007ae90  test    eax, eax
0x18007ae92  js      loc_18007AF7C
0x18007ae98  test    ebx, ebx
0x18007ae9a  js      loc_18007AB6C
0x18007aea0  mov     rax, [rbp+4Fh+KeyHandle]
0x18007aea4  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18007aea8  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rax
0x18007aeac  lea     rcx, [rbp+4Fh+var_88]; KeyHandle
0x18007aeb0  lea     rax, [rbp+4Fh+UnicodeString]
0x18007aeb4  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x18007aebb  xorps   xmm0, xmm0
0x18007aebe  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x18007aec2  mov     edi, 40h ; '@'
  ... truncated ...
```
