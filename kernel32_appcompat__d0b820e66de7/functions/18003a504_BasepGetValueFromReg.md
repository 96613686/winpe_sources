# BasepGetValueFromReg

- ea: `0x18003a504`
- end: `0x18003a81a`
- name: `BasepGetValueFromReg`
- size: `790`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003a464`
- `0x18003c870`
- `0x180054128`

## callees

- `0x18003a504`
- `0x180082751`
- `0x1800827c0`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x18003a6a6`
- `ntdll!NtQueryValueKey` at `0x18003a769`
- `ntdll!NtQueryValueKey` at `0x18003a6a6`
- `ntdll!NtQueryValueKey` at `0x18003a769`
- `ntdll!NtOpenKey` at `0x18003a653`
- `ntdll!NtOpenKey` at `0x18003a653`
- `ntdll!NtClose` at `0x18003a5ce`
- `ntdll!NtClose` at `0x18003a5ce`
- `ntdll!RtlGetPersistedStateLocation` at `0x18003a59d`
- `ntdll!RtlGetPersistedStateLocation` at `0x18003a59d`
- `ntdll!RtlInitUnicodeString` at `0x18003a5b4`
- `ntdll!RtlInitUnicodeString` at `0x18003a613`
- `ntdll!RtlInitUnicodeString` at `0x18003a671`
- `ntdll!RtlInitUnicodeString` at `0x18003a5b4`
- `ntdll!RtlInitUnicodeString` at `0x18003a613`
- `ntdll!RtlInitUnicodeString` at `0x18003a671`
- `ntdll!RtlFreeHeap` at `0x18003a809`
- `ntdll!RtlFreeHeap` at `0x18003a809`
- `ntdll!RtlAllocateHeap` at `0x18003a72c`
- `ntdll!RtlAllocateHeap` at `0x18003a72c`

## string_xrefs

- `0x18003a58e`: `TargetNtPath`

## pseudocode

```c
__int64 __fastcall BasepGetValueFromReg(__int64 a1, const WCHAR *a2, const WCHAR *a3, char *a4, unsigned int *a5)
{
  _DWORD *Heap; // rbx
  char v8; // r12
  NTSTATUS PersistedStateLocation; // edi
  unsigned int v11; // eax
  unsigned int v12; // eax
  __int64 v13; // r9
  __int64 v14; // rax
  __int64 v15; // rdx
  ULONG ResultLength; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  _BYTE KeyValueInformation[128]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR SourceString[264]; // [rsp+120h] [rbp+20h] BYREF

  Heap = KeyValueInformation;
  Handle = 0;
  ResultLength = 0;
  v8 = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  ValueName = 0;
  if ( a1 )
  {
    PersistedStateLocation = RtlGetPersistedStateLocation(a1, L"TargetNtPath", a2, 0, SourceString, 520, 0);
    RtlInitUnicodeString(&DestinationString, SourceString);
    if ( PersistedStateLocation < 0 )
      goto LABEL_3;
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, a2);
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  PersistedStateLocation = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
  if ( PersistedStateLocation >= 0 )
  {
    RtlInitUnicodeString(&ValueName, a3);
    PersistedStateLocation = NtQueryValueKey(
                               Handle,
                               &ValueName,
                               KeyValueFullInformation,
                               KeyValueInformation,
                               0x80u,
                               &ResultLength);
    if ( PersistedStateLocation == -2147483643 )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, ResultLength);
      if ( !Heap )
        goto LABEL_3;
      v8 = 1;
      PersistedStateLocation = NtQueryValueKey(
                                 Handle,
                                 &ValueName,
                                 KeyValueFullInformation,
                                 Heap,
                                 ResultLength,
                                 &ResultLength);
    }
    if ( PersistedStateLocation < 0 )
      goto LABEL_3;
    if ( Heap[1] != 1 && Heap[1] != 2 )
    {
      if ( Heap[1] == 3 || Heap[1] == 4 )
      {
LABEL_18:
        v11 = Heap[3];
        if ( *a5 < v11 )
        {
          PersistedStateLocation = -2147483643;
        }
        else
        {
          memcpy_0(a4, (char *)Heap + (unsigned int)Heap[2], v11);
          v11 = Heap[3];
        }
LABEL_32:
        *a5 = v11;
        goto LABEL_3;
      }
      if ( Heap[1] != 7 )
      {
        if ( Heap[1] != 11 )
        {
          PersistedStateLocation = -1073741595;
          goto LABEL_3;
        }
        goto LABEL_18;
      }
    }
    v12 = Heap[3];
    if ( v12 >= 2 )
    {
      v13 = (unsigned int)Heap[2];
      v14 = v12 & 0xFFFFFFFE;
      v15 = (unsigned int)v14;
      Heap[3] = v14;
      if ( !*(_WORD *)((char *)Heap + v13 + v14 - 2) )
      {
        v15 = (unsigned int)(v14 - 2);
        Heap[3] = v15;
      }
      if ( *a5 >= (unsigned __int64)(v15 + 2) && a4 )
      {
        memcpy_0(a4, (char *)Heap + v13, (unsigned int)v15);
        *(_WORD *)&a4[Heap[3]] = 0;
        LODWORD(v15) = Heap[3];
      }
      else
      {
        PersistedStateLocation = -2147483643;
      }
      v11 = v15 + 2;
      goto LABEL_32;
    }
    PersistedStateLocation = -1073741772;
  }
LABEL_3:
  if ( Handle )
  {
    NtClose(Handle);
    Handle = 0;
  }
  if ( v8 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)PersistedStateLocation;
}

```

## disassembly

```asm
0x18003a504  push    rbp
0x18003a506  push    rbx
0x18003a507  push    rsi
0x18003a508  push    rdi
0x18003a509  push    r12
0x18003a50b  push    r13
0x18003a50d  push    r14
0x18003a50f  push    r15
0x18003a511  lea     rbp, [rsp-248h]
0x18003a519  sub     rsp, 348h
0x18003a520  mov     rax, cs:__security_cookie
0x18003a527  xor     rax, rsp
0x18003a52a  mov     [rbp+280h+var_50], rax
0x18003a531  mov     rsi, [rbp+280h+arg_20]
0x18003a538  lea     rbx, [rbp+280h+KeyValueInformation]
0x18003a53c  xor     r13d, r13d
0x18003a53f  xorps   xmm0, xmm0
0x18003a542  xor     eax, eax
0x18003a544  mov     [rsp+380h+Handle], r13
0x18003a549  mov     [rsp+380h+var_340], r13d
0x18003a54e  xorps   xmm1, xmm1
0x18003a551  mov     r14, r9
0x18003a554  mov     r15, r8
0x18003a557  mov     r12b, r13b
0x18003a55a  movups  xmmword ptr [rbp+280h+ObjectAttributes.ObjectName], xmm0
0x18003a55e  movups  xmmword ptr [rbp+280h+ObjectAttributes+1Ch], xmm0
0x18003a562  movups  xmmword ptr [rsp+380h+ObjectAttributes.Length], xmm0
0x18003a567  movups  xmmword ptr [rsp+380h+DestinationString.Length], xmm0
0x18003a56c  movups  xmmword ptr [rsp+380h+ValueName.Length], xmm1
0x18003a571  test    rcx, rcx
0x18003a574  jz      loc_18003A60E
0x18003a57a  mov     [rsp+380h+var_350], r13
0x18003a57f  lea     rax, [rbp+280h+SourceString]
0x18003a583  mov     r8, rdx
0x18003a586  mov     dword ptr [rsp+380h+ResultLength], 208h
0x18003a58e  lea     rdx, aTargetntpath; "TargetNtPath"
0x18003a595  mov     qword ptr [rsp+380h+Length], rax
0x18003a59a  xor     r9d, r9d
0x18003a59d  call    cs:__imp_RtlGetPersistedStateLocation
0x18003a5a4  nop     dword ptr [rax+rax+00h]
0x18003a5a9  lea     rdx, [rbp+280h+SourceString]; SourceString
0x18003a5ad  mov     edi, eax
0x18003a5af  lea     rcx, [rsp+380h+DestinationString]; DestinationString
0x18003a5b4  call    cs:__imp_RtlInitUnicodeString
0x18003a5bb  nop     dword ptr [rax+rax+00h]
0x18003a5c0  test    edi, edi
0x18003a5c2  jns     short loc_18003A61F
0x18003a5c4  mov     rcx, [rsp+380h+Handle]; Handle
0x18003a5c9  test    rcx, rcx
0x18003a5cc  jz      short loc_18003A5DF
0x18003a5ce  call    cs:__imp_NtClose
0x18003a5d5  nop     dword ptr [rax+rax+00h]
0x18003a5da  mov     [rsp+380h+Handle], r13
0x18003a5df  test    r12b, r12b
0x18003a5e2  jnz     loc_18003A7F7
0x18003a5e8  mov     eax, edi
0x18003a5ea  mov     rcx, [rbp+280h+var_50]
0x18003a5f1  xor     rcx, rsp; StackCookie
0x18003a5f4  call    __security_check_cookie
0x18003a5f9  add     rsp, 348h
0x18003a600  pop     r15
0x18003a602  pop     r14
0x18003a604  pop     r13
0x18003a606  pop     r12
0x18003a608  pop     rdi
0x18003a609  pop     rsi
0x18003a60a  pop     rbx
0x18003a60b  pop     rbp
0x18003a60c  retn
0x18003a60e  lea     rcx, [rsp+380h+DestinationString]; DestinationString
0x18003a613  call    cs:__imp_RtlInitUnicodeString
0x18003a61a  nop     dword ptr [rax+rax+00h]
0x18003a61f  lea     rax, [rsp+380h+DestinationString]
0x18003a624  mov     [rsp+380h+ObjectAttributes.Length], 30h ; '0'
0x18003a62c  xorps   xmm0, xmm0
0x18003a62f  mov     [rbp+280h+ObjectAttributes.ObjectName], rax
0x18003a633  lea     r8, [rsp+380h+ObjectAttributes]; ObjectAttributes
0x18003a638  mov     [rsp+380h+ObjectAttributes.RootDirectory], r13
0x18003a63d  mov     edx, 20019h; DesiredAccess
0x18003a642  mov     [rbp+280h+ObjectAttributes.Attributes], 40h ; '@'
0x18003a649  lea     rcx, [rsp+380h+Handle]; KeyHandle
0x18003a64e  movdqu  xmmword ptr [rbp+280h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003a653  call    cs:__imp_NtOpenKey
0x18003a65a  nop     dword ptr [rax+rax+00h]
0x18003a65f  mov     edi, eax
0x18003a661  test    eax, eax
0x18003a663  js      loc_18003A5C4
0x18003a669  mov     rdx, r15; SourceString
0x18003a66c  lea     rcx, [rsp+380h+ValueName]; DestinationString
0x18003a671  call    cs:__imp_RtlInitUnicodeString
0x18003a678  nop     dword ptr [rax+rax+00h]
0x18003a67d  mov     rcx, [rsp+380h+Handle]; KeyHandle
0x18003a682  lea     rax, [rsp+380h+var_340]
0x18003a687  mov     [rsp+380h+ResultLength], rax; ResultLength
0x18003a68c  lea     r9, [rbp+280h+KeyValueInformation]; KeyValueInformation
0x18003a690  mov     r15d, 1
0x18003a696  mov     [rsp+380h+Length], 80h; Length
0x18003a69e  mov     r8d, r15d; KeyValueInformationClass
0x18003a6a1  lea     rdx, [rsp+380h+ValueName]; ValueName
0x18003a6a6  call    cs:__imp_NtQueryValueKey
0x18003a6ad  nop     dword ptr [rax+rax+00h]
0x18003a6b2  mov     edi, eax
0x18003a6b4  cmp     eax, 80000005h
0x18003a6b9  jz      short loc_18003A718
0x18003a6bb  test    edi, edi
0x18003a6bd  js      loc_18003A5C4
0x18003a6c3  mov     ecx, [rbx+4]
0x18003a6c6  sub     ecx, r15d
0x18003a6c9  jz      loc_18003A78D
0x18003a6cf  sub     ecx, r15d
0x18003a6d2  jz      loc_18003A78D
0x18003a6d8  sub     ecx, r15d
0x18003a6db  jz      short loc_18003A6F4
0x18003a6dd  sub     ecx, r15d
0x18003a6e0  jz      short loc_18003A6F4
0x18003a6e2  sub     ecx, 3
0x18003a6e5  jz      loc_18003A78D
0x18003a6eb  cmp     ecx, 4
0x18003a6ee  jnz     loc_18003A77C
0x18003a6f4  mov     eax, [rbx+0Ch]
0x18003a6f7  cmp     [rsi], eax
0x18003a6f9  jb      loc_18003A786
0x18003a6ff  mov     edx, [rbx+8]
0x18003a702  mov     r8d, eax; Size
0x18003a705  add     rdx, rbx; Src
0x18003a708  mov     rcx, r14; void *
0x18003a70b  call    memcpy_0
0x18003a710  mov     eax, [rbx+0Ch]
0x18003a713  jmp     loc_18003A7E6
0x18003a718  mov     rcx, gs:60h
0x18003a721  xor     edx, edx; Flags
0x18003a723  mov     r8d, [rsp+380h+var_340]; Size
0x18003a728  mov     rcx, [rcx+30h]; HeapHandle
0x18003a72c  call    cs:__imp_RtlAllocateHeap
0x18003a733  nop     dword ptr [rax+rax+00h]
0x18003a738  mov     rbx, rax
0x18003a73b  test    rax, rax
0x18003a73e  jz      loc_18003A5C4
0x18003a744  mov     ecx, [rsp+380h+var_340]
0x18003a748  lea     rax, [rsp+380h+var_340]
0x18003a74d  mov     [rsp+380h+ResultLength], rax; ResultLength
0x18003a752  lea     rdx, [rsp+380h+ValueName]; ValueName
0x18003a757  mov     [rsp+380h+Length], ecx; Length
0x18003a75b  mov     r9, rbx; KeyValueInformation
0x18003a75e  mov     rcx, [rsp+380h+Handle]; KeyHandle
0x18003a763  mov     r8d, r15d; KeyValueInformationClass
0x18003a766  mov     r12b, r15b
0x18003a769  call    cs:__imp_NtQueryValueKey
0x18003a770  nop     dword ptr [rax+rax+00h]
0x18003a775  mov     edi, eax
0x18003a777  jmp     loc_18003A6BB
0x18003a77c  mov     edi, 0C00000E5h
0x18003a781  jmp     loc_18003A5C4
0x18003a786  mov     edi, 80000005h
0x18003a78b  jmp     short loc_18003A7E6
0x18003a78d  mov     eax, [rbx+0Ch]
0x18003a790  cmp     eax, 2
0x18003a793  jb      short loc_18003A7ED
0x18003a795  mov     r9d, [rbx+8]
0x18003a799  and     eax, 0FFFFFFFEh
0x18003a79c  mov     edx, eax
0x18003a79e  add     rax, r9
0x18003a7a1  mov     [rbx+0Ch], edx
0x18003a7a4  cmp     [rax+rbx-2], r13w
0x18003a7aa  jnz     short loc_18003A7B2
0x18003a7ac  add     edx, 0FFFFFFFEh
0x18003a7af  mov     [rbx+0Ch], edx
0x18003a7b2  mov     eax, [rsi]
0x18003a7b4  lea     rcx, [rdx+2]
0x18003a7b8  mov     r8d, edx; Size
0x18003a7bb  cmp     rax, rcx
0x18003a7be  jb      short loc_18003A7DE
0x18003a7c0  test    r14, r14
0x18003a7c3  jz      short loc_18003A7DE
0x18003a7c5  lea     rdx, [r9+rbx]; Src
0x18003a7c9  mov     rcx, r14; void *
0x18003a7cc  call    memcpy_0
0x18003a7d1  mov     ecx, [rbx+0Ch]
0x18003a7d4  mov     [rcx+r14], r13w
0x18003a7d9  mov     edx, [rbx+0Ch]
0x18003a7dc  jmp     short loc_18003A7E3
0x18003a7de  mov     edi, 80000005h
0x18003a7e3  lea     eax, [rdx+2]
0x18003a7e6  mov     [rsi], eax
0x18003a7e8  jmp     loc_18003A5C4
0x18003a7ed  mov     edi, 0C0000034h
0x18003a7f2  jmp     loc_18003A5C4
0x18003a7f7  mov     rcx, gs:60h
0x18003a800  mov     r8, rbx; P
0x18003a803  xor     edx, edx; Flags
0x18003a805  mov     rcx, [rcx+30h]; HeapHandle
0x18003a809  call    cs:__imp_RtlFreeHeap
0x18003a810  nop     dword ptr [rax+rax+00h]
0x18003a815  jmp     loc_18003A5E8
```
