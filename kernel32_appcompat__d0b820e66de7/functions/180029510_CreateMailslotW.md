# CreateMailslotW

- ea: `0x180029510`
- end: `0x1800296b4`
- name: `CreateMailslotW`
- size: `420`
- prototype: `HANDLE __stdcall(LPCWSTR lpName, DWORD nMaxMessageSize, DWORD lReadTimeout, LPSECURITY_ATTRIBUTES lpSecurityAttributes)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180027a40`

## callees

- `0x18000ccf0`
- `0x180029510`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x180029680`
- `ntdll!RtlSetLastWin32Error` at `0x180029680`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180029577`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180029577`
- `ntdll!NtCreateMailslotFile` at `0x180029603`
- `ntdll!NtCreateMailslotFile` at `0x180029603`
- `ntdll!RtlInitUnicodeString` at `0x18002955d`
- `ntdll!RtlInitUnicodeString` at `0x18002955d`
- `ntdll!RtlFreeHeap` at `0x180029639`
- `ntdll!RtlFreeHeap` at `0x180029639`

## pseudocode

```c
HANDLE __stdcall CreateMailslotW(
        LPCWSTR lpName,
        DWORD nMaxMessageSize,
        DWORD lReadTimeout,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes)
{
  __int64 v4; // rsi
  PWSTR Buffer; // r14
  ULONG v9; // ecx
  NTSTATUS v10; // eax
  int v11; // ebx
  bool v13; // zf
  union _LARGE_INTEGER TimeOut; // [rsp+40h] [rbp-49h] BYREF
  void *MailSlotFileHandle; // [rsp+48h] [rbp-41h] BYREF
  PCWSTR NtFileNamePart; // [rsp+50h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-31h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-11h] BYREF

  v4 = lReadTimeout;
  NtFileNamePart = 0;
  TimeOut.QuadPart = 0;
  MailSlotFileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString, lpName);
  if ( RtlDosPathNameToNtPathName_U(lpName, &DestinationString, &NtFileNamePart, 0) )
  {
    Buffer = DestinationString.Buffer;
    v9 = 64;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( lpSecurityAttributes )
    {
      v13 = !lpSecurityAttributes->bInheritHandle;
      ObjectAttributes.SecurityDescriptor = lpSecurityAttributes->lpSecurityDescriptor;
      if ( !v13 )
        v9 = 66;
      ObjectAttributes.Attributes = v9;
    }
    if ( (_DWORD)v4 == -1 )
      TimeOut.QuadPart = -1;
    else
      TimeOut.QuadPart = -10000 * v4;
    v10 = NtCreateMailslotFile(
            &MailSlotFileHandle,
            0x80140000,
            &ObjectAttributes,
            &IoStatusBlock,
            2u,
            0,
            nMaxMessageSize,
            &TimeOut);
    v11 = v10;
    if ( v10 == -1073741637 || v10 == -1073741808 )
      v11 = -1073741773;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    if ( v11 >= 0 )
      return MailSlotFileHandle;
    BaseSetLastNTError((unsigned int)v11);
  }
  else
  {
    RtlSetLastWin32Error(3u);
  }
  return (HANDLE)-1LL;
}

```

## disassembly

```asm
0x180029510  push    rbp
0x180029512  push    rbx
0x180029513  push    rsi
0x180029514  push    rdi
0x180029515  push    r14
0x180029517  push    r15
0x180029519  lea     rbp, [rsp-2Fh]
0x18002951e  sub     rsp, 0B8h
0x180029525  xorps   xmm0, xmm0
0x180029528  mov     esi, r8d
0x18002952b  xor     eax, eax
0x18002952d  mov     r15d, edx
0x180029530  mov     rdx, rcx; SourceString
0x180029533  mov     [rbp+57h+NtFileNamePart], rax
0x180029537  mov     rbx, rcx
0x18002953a  mov     qword ptr [rbp+57h+var_A0], rax
0x18002953e  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180029542  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180029546  mov     [rbp+57h+MailSlotFileHandle], rax
0x18002954a  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18002954e  mov     rdi, r9
0x180029551  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180029555  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180029559  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18002955d  call    cs:__imp_RtlInitUnicodeString
0x180029564  nop     dword ptr [rax+rax+00h]
0x180029569  xor     r9d, r9d; DirectoryInfo
0x18002956c  lea     r8, [rbp+57h+NtFileNamePart]; NtFileNamePart
0x180029570  lea     rdx, [rbp+57h+DestinationString]; NtPathName
0x180029574  mov     rcx, rbx; DosPathName
0x180029577  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18002957e  nop     dword ptr [rax+rax+00h]
0x180029583  test    al, al
0x180029585  jz      loc_18002967B
0x18002958b  mov     r14, [rbp+57h+DestinationString.Buffer]
0x18002958f  mov     ecx, 40h ; '@'
0x180029594  mov     [rbp+57h+ObjectAttributes.Attributes], ecx
0x180029597  lea     rax, [rbp+57h+DestinationString]
0x18002959b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18002959f  xorps   xmm0, xmm0
0x1800295a2  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800295a9  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800295b1  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800295b6  test    rdi, rdi
0x1800295b9  jnz     loc_18002968E
0x1800295bf  or      eax, 0FFFFFFFFh
0x1800295c2  cmp     esi, eax
0x1800295c4  jnz     loc_18002966B
0x1800295ca  mov     dword ptr [rbp+57h+var_A0+4], 0FFFFFFFFh
0x1800295d1  mov     dword ptr [rbp+57h+var_A0], eax
0x1800295d4  lea     rax, [rbp+57h+var_A0]
0x1800295d8  mov     edx, 80140000h; DesiredAccess
0x1800295dd  mov     [rsp+0E0h+TimeOut], rax; TimeOut
0x1800295e2  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800295e6  mov     [rsp+0E0h+MaxMessageSize], r15d; MaxMessageSize
0x1800295eb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800295ef  mov     [rsp+0E0h+ShareAccess], 0; ShareAccess
0x1800295f7  lea     rcx, [rbp+57h+MailSlotFileHandle]; MailSlotFileHandle
0x1800295fb  mov     [rsp+0E0h+FileAttributes], 2; FileAttributes
0x180029603  call    cs:__imp_NtCreateMailslotFile
0x18002960a  nop     dword ptr [rax+rax+00h]
0x18002960f  mov     ebx, eax
0x180029611  cmp     eax, 0C00000BBh
0x180029616  jz      loc_1800296AA
0x18002961c  cmp     eax, 0C0000010h
0x180029621  jz      loc_1800296AA
0x180029627  mov     rcx, gs:60h
0x180029630  mov     r8, r14; P
0x180029633  xor     edx, edx; Flags
0x180029635  mov     rcx, [rcx+30h]; HeapHandle
0x180029639  call    cs:__imp_RtlFreeHeap
0x180029640  nop     dword ptr [rax+rax+00h]
0x180029645  test    ebx, ebx
0x180029647  js      short loc_18002964F
0x180029649  mov     rax, [rbp+57h+MailSlotFileHandle]
0x18002964d  jmp     short loc_18002965A
0x18002964f  mov     ecx, ebx
0x180029651  call    BaseSetLastNTError
0x180029656  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002965a  add     rsp, 0B8h
0x180029661  pop     r15
0x180029663  pop     r14
0x180029665  pop     rdi
0x180029666  pop     rsi
0x180029667  pop     rbx
0x180029668  pop     rbp
0x180029669  retn
0x18002966b  imul    rcx, rsi, 0FFFFFFFFFFFFD8F0h
0x180029672  mov     qword ptr [rbp+57h+var_A0], rcx
0x180029676  jmp     loc_1800295D4
0x18002967b  mov     ecx, 3; LastError
0x180029680  call    cs:__imp_RtlSetLastWin32Error
0x180029687  nop     dword ptr [rax+rax+00h]
0x18002968c  jmp     short loc_180029656
0x18002968e  mov     rax, [rdi+8]
0x180029692  cmp     dword ptr [rdi+10h], 0
0x180029696  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x18002969a  mov     eax, 42h ; 'B'
0x18002969f  cmovnz  ecx, eax
0x1800296a2  mov     [rbp+57h+ObjectAttributes.Attributes], ecx
0x1800296a5  jmp     loc_1800295BF
0x1800296aa  mov     ebx, 0C0000033h
0x1800296af  jmp     loc_180029627
```
