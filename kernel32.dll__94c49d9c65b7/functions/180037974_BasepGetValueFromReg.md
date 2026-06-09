# BasepGetValueFromReg

- ea: `0x180037974`
- end: `0x180037c45`
- name: `BasepGetValueFromReg`
- size: `721`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800378d4`
- `0x180039820`
- `0x18004f13c`

## callees

- `0x180037974`
- `0x18007a7d1`
- `0x18007a840`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x180037af1`
- `ntdll!NtQueryValueKey` at `0x180037ba0`
- `ntdll!NtQueryValueKey` at `0x180037af1`
- `ntdll!NtQueryValueKey` at `0x180037ba0`
- `ntdll!NtOpenKey` at `0x180037aaa`
- `ntdll!NtOpenKey` at `0x180037aaa`
- `ntdll!NtClose` at `0x180037a32`
- `ntdll!NtClose` at `0x180037a32`
- `ntdll!RtlGetPersistedStateLocation` at `0x180037a0d`
- `ntdll!RtlGetPersistedStateLocation` at `0x180037a0d`
- `ntdll!RtlInitUnicodeString` at `0x180037a1e`
- `ntdll!RtlInitUnicodeString` at `0x180037a70`
- `ntdll!RtlInitUnicodeString` at `0x180037ac2`
- `ntdll!RtlInitUnicodeString` at `0x180037a1e`
- `ntdll!RtlInitUnicodeString` at `0x180037a70`
- `ntdll!RtlInitUnicodeString` at `0x180037ac2`
- `ntdll!RtlFreeHeap` at `0x180037c3a`
- `ntdll!RtlFreeHeap` at `0x180037c3a`
- `ntdll!RtlAllocateHeap` at `0x180037b69`
- `ntdll!RtlAllocateHeap` at `0x180037b69`

## string_xrefs

- `0x1800379fe`: `TargetNtPath`

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
0x180037974  push    rbp
0x180037976  push    rbx
0x180037977  push    rsi
0x180037978  push    rdi
0x180037979  push    r12
0x18003797b  push    r13
0x18003797d  push    r14
0x18003797f  push    r15
0x180037981  lea     rbp, [rsp-248h]
0x180037989  sub     rsp, 348h
0x180037990  mov     rax, cs:__security_cookie
0x180037997  xor     rax, rsp
0x18003799a  mov     [rbp+280h+var_50], rax
0x1800379a1  mov     rsi, [rbp+280h+arg_20]
0x1800379a8  lea     rbx, [rbp+280h+KeyValueInformation]
0x1800379ac  xor     r13d, r13d
0x1800379af  xorps   xmm0, xmm0
0x1800379b2  xor     eax, eax
0x1800379b4  mov     [rsp+380h+Handle], r13
0x1800379b9  mov     [rsp+380h+var_340], r13d
0x1800379be  xorps   xmm1, xmm1
0x1800379c1  mov     r14, r9
0x1800379c4  mov     r15, r8
0x1800379c7  mov     r12b, r13b
0x1800379ca  movups  xmmword ptr [rbp+280h+ObjectAttributes.ObjectName], xmm0
0x1800379ce  movups  xmmword ptr [rbp+280h+ObjectAttributes+1Ch], xmm0
0x1800379d2  movups  xmmword ptr [rsp+380h+ObjectAttributes.Length], xmm0
0x1800379d7  movups  xmmword ptr [rsp+380h+DestinationString.Length], xmm0
0x1800379dc  movups  xmmword ptr [rsp+380h+ValueName.Length], xmm1
0x1800379e1  test    rcx, rcx
0x1800379e4  jz      loc_180037A6B
0x1800379ea  mov     [rsp+380h+var_350], r13
0x1800379ef  lea     rax, [rbp+280h+SourceString]
0x1800379f3  mov     r8, rdx
0x1800379f6  mov     dword ptr [rsp+380h+ResultLength], 208h
0x1800379fe  lea     rdx, aTargetntpath; "TargetNtPath"
0x180037a05  mov     qword ptr [rsp+380h+Length], rax
0x180037a0a  xor     r9d, r9d
0x180037a0d  call    cs:__imp_RtlGetPersistedStateLocation
0x180037a13  lea     rdx, [rbp+280h+SourceString]; SourceString
0x180037a17  mov     edi, eax
0x180037a19  lea     rcx, [rsp+380h+DestinationString]; DestinationString
0x180037a1e  call    cs:__imp_RtlInitUnicodeString
0x180037a24  test    edi, edi
0x180037a26  jns     short loc_180037A76
0x180037a28  mov     rcx, [rsp+380h+Handle]; Handle
0x180037a2d  test    rcx, rcx
0x180037a30  jz      short loc_180037A3D
0x180037a32  call    cs:__imp_NtClose
0x180037a38  mov     [rsp+380h+Handle], r13
0x180037a3d  test    r12b, r12b
0x180037a40  jnz     loc_180037C28
0x180037a46  mov     eax, edi
0x180037a48  mov     rcx, [rbp+280h+var_50]
0x180037a4f  xor     rcx, rsp; StackCookie
0x180037a52  call    __security_check_cookie
0x180037a57  add     rsp, 348h
0x180037a5e  pop     r15
0x180037a60  pop     r14
0x180037a62  pop     r13
0x180037a64  pop     r12
0x180037a66  pop     rdi
0x180037a67  pop     rsi
0x180037a68  pop     rbx
0x180037a69  pop     rbp
0x180037a6a  retn
0x180037a6b  lea     rcx, [rsp+380h+DestinationString]; DestinationString
0x180037a70  call    cs:__imp_RtlInitUnicodeString
0x180037a76  lea     rax, [rsp+380h+DestinationString]
0x180037a7b  mov     [rsp+380h+ObjectAttributes.Length], 30h ; '0'
0x180037a83  xorps   xmm0, xmm0
0x180037a86  mov     [rbp+280h+ObjectAttributes.ObjectName], rax
0x180037a8a  lea     r8, [rsp+380h+ObjectAttributes]; ObjectAttributes
0x180037a8f  mov     [rsp+380h+ObjectAttributes.RootDirectory], r13
0x180037a94  mov     edx, 20019h; DesiredAccess
0x180037a99  mov     [rbp+280h+ObjectAttributes.Attributes], 40h ; '@'
0x180037aa0  lea     rcx, [rsp+380h+Handle]; KeyHandle
0x180037aa5  movdqu  xmmword ptr [rbp+280h+ObjectAttributes.SecurityDescriptor], xmm0
0x180037aaa  call    cs:__imp_NtOpenKey
0x180037ab0  mov     edi, eax
0x180037ab2  test    eax, eax
0x180037ab4  js      loc_180037A28
0x180037aba  mov     rdx, r15; SourceString
0x180037abd  lea     rcx, [rsp+380h+ValueName]; DestinationString
0x180037ac2  call    cs:__imp_RtlInitUnicodeString
0x180037ac8  mov     rcx, [rsp+380h+Handle]; KeyHandle
0x180037acd  lea     rax, [rsp+380h+var_340]
0x180037ad2  mov     [rsp+380h+ResultLength], rax; ResultLength
0x180037ad7  lea     r9, [rbp+280h+KeyValueInformation]; KeyValueInformation
0x180037adb  mov     r15d, 1
0x180037ae1  mov     [rsp+380h+Length], 80h; Length
0x180037ae9  mov     r8d, r15d; KeyValueInformationClass
0x180037aec  lea     rdx, [rsp+380h+ValueName]; ValueName
0x180037af1  call    cs:__imp_NtQueryValueKey
0x180037af7  mov     edi, eax
0x180037af9  cmp     eax, 80000005h
0x180037afe  jz      short loc_180037B55
0x180037b00  test    edi, edi
0x180037b02  js      loc_180037A28
0x180037b08  mov     ecx, [rbx+4]
0x180037b0b  sub     ecx, r15d
0x180037b0e  jz      loc_180037BBE
0x180037b14  sub     ecx, r15d
0x180037b17  jz      loc_180037BBE
0x180037b1d  sub     ecx, r15d
0x180037b20  jz      short loc_180037B35
0x180037b22  sub     ecx, r15d
0x180037b25  jz      short loc_180037B35
0x180037b27  sub     ecx, 3
0x180037b2a  jz      loc_180037BBE
0x180037b30  cmp     ecx, 4
0x180037b33  jnz     short loc_180037BAD
0x180037b35  mov     eax, [rbx+0Ch]
0x180037b38  cmp     [rsi], eax
0x180037b3a  jb      short loc_180037BB7
0x180037b3c  mov     edx, [rbx+8]
0x180037b3f  mov     r8d, eax; Size
0x180037b42  add     rdx, rbx; Src
0x180037b45  mov     rcx, r14; void *
0x180037b48  call    memcpy_0
0x180037b4d  mov     eax, [rbx+0Ch]
0x180037b50  jmp     loc_180037C17
0x180037b55  mov     rcx, gs:60h
0x180037b5e  xor     edx, edx; Flags
0x180037b60  mov     r8d, [rsp+380h+var_340]; Size
0x180037b65  mov     rcx, [rcx+30h]; HeapHandle
0x180037b69  call    cs:__imp_RtlAllocateHeap
0x180037b6f  mov     rbx, rax
0x180037b72  test    rax, rax
0x180037b75  jz      loc_180037A28
0x180037b7b  mov     ecx, [rsp+380h+var_340]
0x180037b7f  lea     rax, [rsp+380h+var_340]
0x180037b84  mov     [rsp+380h+ResultLength], rax; ResultLength
0x180037b89  lea     rdx, [rsp+380h+ValueName]; ValueName
0x180037b8e  mov     [rsp+380h+Length], ecx; Length
0x180037b92  mov     r9, rbx; KeyValueInformation
0x180037b95  mov     rcx, [rsp+380h+Handle]; KeyHandle
0x180037b9a  mov     r8d, r15d; KeyValueInformationClass
0x180037b9d  mov     r12b, r15b
0x180037ba0  call    cs:__imp_NtQueryValueKey
0x180037ba6  mov     edi, eax
0x180037ba8  jmp     loc_180037B00
0x180037bad  mov     edi, 0C00000E5h
0x180037bb2  jmp     loc_180037A28
0x180037bb7  mov     edi, 80000005h
0x180037bbc  jmp     short loc_180037C17
0x180037bbe  mov     eax, [rbx+0Ch]
0x180037bc1  cmp     eax, 2
0x180037bc4  jb      short loc_180037C1E
0x180037bc6  mov     r9d, [rbx+8]
0x180037bca  and     eax, 0FFFFFFFEh
0x180037bcd  mov     edx, eax
0x180037bcf  add     rax, r9
0x180037bd2  mov     [rbx+0Ch], edx
0x180037bd5  cmp     [rax+rbx-2], r13w
0x180037bdb  jnz     short loc_180037BE3
0x180037bdd  add     edx, 0FFFFFFFEh
0x180037be0  mov     [rbx+0Ch], edx
0x180037be3  mov     eax, [rsi]
0x180037be5  lea     rcx, [rdx+2]
0x180037be9  mov     r8d, edx; Size
0x180037bec  cmp     rax, rcx
0x180037bef  jb      short loc_180037C0F
0x180037bf1  test    r14, r14
0x180037bf4  jz      short loc_180037C0F
0x180037bf6  lea     rdx, [r9+rbx]; Src
0x180037bfa  mov     rcx, r14; void *
0x180037bfd  call    memcpy_0
0x180037c02  mov     ecx, [rbx+0Ch]
0x180037c05  mov     [rcx+r14], r13w
0x180037c0a  mov     edx, [rbx+0Ch]
0x180037c0d  jmp     short loc_180037C14
0x180037c0f  mov     edi, 80000005h
0x180037c14  lea     eax, [rdx+2]
0x180037c17  mov     [rsi], eax
0x180037c19  jmp     loc_180037A28
0x180037c1e  mov     edi, 0C0000034h
0x180037c23  jmp     loc_180037A28
0x180037c28  mov     rcx, gs:60h
0x180037c31  mov     r8, rbx; P
0x180037c34  xor     edx, edx; Flags
0x180037c36  mov     rcx, [rcx+30h]; HeapHandle
0x180037c3a  call    cs:__imp_RtlFreeHeap
0x180037c40  jmp     loc_180037A46
```
