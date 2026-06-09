# CreateMailslotW

- ea: `0x18000bd80`
- end: `0x18000befa`
- name: `CreateMailslotW`
- size: `378`
- prototype: `HANDLE __stdcall(LPCWSTR lpName, DWORD nMaxMessageSize, DWORD lReadTimeout, LPSECURITY_ATTRIBUTES lpSecurityAttributes)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000bf00`

## callees

- `0x18000bd80`
- `0x18000f920`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18000becf`
- `ntdll!RtlSetLastWin32Error` at `0x18000becf`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18000bde1`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18000bde1`
- `ntdll!NtCreateMailslotFile` at `0x18000be67`
- `ntdll!NtCreateMailslotFile` at `0x18000be67`
- `ntdll!RtlInitUnicodeString` at `0x18000bdcd`
- `ntdll!RtlInitUnicodeString` at `0x18000bdcd`
- `ntdll!RtlFreeHeap` at `0x18000be8f`
- `ntdll!RtlFreeHeap` at `0x18000be8f`

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
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-21h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-11h] BYREF

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
0x18000bd80  push    rbp
0x18000bd82  push    rbx
0x18000bd83  push    rsi
0x18000bd84  push    rdi
0x18000bd85  push    r14
0x18000bd87  push    r15
0x18000bd89  lea     rbp, [rsp-2Fh]
0x18000bd8e  sub     rsp, 0B8h
0x18000bd95  xorps   xmm0, xmm0
0x18000bd98  mov     esi, r8d
0x18000bd9b  xor     eax, eax
0x18000bd9d  mov     r15d, edx
0x18000bda0  mov     rdx, rcx; SourceString
0x18000bda3  mov     [rbp+57h+NtFileNamePart], rax
0x18000bda7  mov     rbx, rcx
0x18000bdaa  mov     qword ptr [rbp+57h+var_A0], rax
0x18000bdae  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000bdb2  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000bdb6  mov     [rbp+57h+MailSlotFileHandle], rax
0x18000bdba  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18000bdbe  mov     rdi, r9
0x18000bdc1  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000bdc5  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18000bdc9  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18000bdcd  call    cs:__imp_RtlInitUnicodeString
0x18000bdd3  xor     r9d, r9d; DirectoryInfo
0x18000bdd6  lea     r8, [rbp+57h+NtFileNamePart]; NtFileNamePart
0x18000bdda  lea     rdx, [rbp+57h+DestinationString]; NtPathName
0x18000bdde  mov     rcx, rbx; DosPathName
0x18000bde1  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18000bde7  test    al, al
0x18000bde9  jz      loc_18000BECA
0x18000bdef  mov     r14, [rbp+57h+DestinationString.Buffer]
0x18000bdf3  mov     ecx, 40h ; '@'
0x18000bdf8  mov     [rbp+57h+ObjectAttributes.Attributes], ecx
0x18000bdfb  lea     rax, [rbp+57h+DestinationString]
0x18000bdff  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000be03  xorps   xmm0, xmm0
0x18000be06  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000be0d  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18000be15  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000be1a  test    rdi, rdi
0x18000be1d  jnz     loc_18000BED7
0x18000be23  or      eax, 0FFFFFFFFh
0x18000be26  cmp     esi, eax
0x18000be28  jnz     loc_18000BEBA
0x18000be2e  mov     dword ptr [rbp+57h+var_A0+4], 0FFFFFFFFh
0x18000be35  mov     dword ptr [rbp+57h+var_A0], eax
0x18000be38  lea     rax, [rbp+57h+var_A0]
0x18000be3c  mov     edx, 80140000h; DesiredAccess
0x18000be41  mov     [rsp+0E0h+TimeOut], rax; TimeOut
0x18000be46  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000be4a  mov     [rsp+0E0h+MaxMessageSize], r15d; MaxMessageSize
0x18000be4f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000be53  mov     [rsp+0E0h+ShareAccess], 0; ShareAccess
0x18000be5b  lea     rcx, [rbp+57h+MailSlotFileHandle]; MailSlotFileHandle
0x18000be5f  mov     [rsp+0E0h+FileAttributes], 2; FileAttributes
0x18000be67  call    cs:__imp_NtCreateMailslotFile
0x18000be6d  mov     ebx, eax
0x18000be6f  cmp     eax, 0C00000BBh
0x18000be74  jz      short loc_18000BEF3
0x18000be76  cmp     eax, 0C0000010h
0x18000be7b  jz      short loc_18000BEF3
0x18000be7d  mov     rcx, gs:60h
0x18000be86  mov     r8, r14; P
0x18000be89  xor     edx, edx; Flags
0x18000be8b  mov     rcx, [rcx+30h]; HeapHandle
0x18000be8f  call    cs:__imp_RtlFreeHeap
0x18000be95  test    ebx, ebx
0x18000be97  js      short loc_18000BE9F
0x18000be99  mov     rax, [rbp+57h+MailSlotFileHandle]
0x18000be9d  jmp     short loc_18000BEAA
0x18000be9f  mov     ecx, ebx
0x18000bea1  call    BaseSetLastNTError
0x18000bea6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000beaa  add     rsp, 0B8h
0x18000beb1  pop     r15
0x18000beb3  pop     r14
0x18000beb5  pop     rdi
0x18000beb6  pop     rsi
0x18000beb7  pop     rbx
0x18000beb8  pop     rbp
0x18000beb9  retn
0x18000beba  imul    rcx, rsi, 0FFFFFFFFFFFFD8F0h
0x18000bec1  mov     qword ptr [rbp+57h+var_A0], rcx
0x18000bec5  jmp     loc_18000BE38
0x18000beca  mov     ecx, 3; LastError
0x18000becf  call    cs:__imp_RtlSetLastWin32Error
0x18000bed5  jmp     short loc_18000BEA6
0x18000bed7  mov     rax, [rdi+8]
0x18000bedb  cmp     dword ptr [rdi+10h], 0
0x18000bedf  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x18000bee3  mov     eax, 42h ; 'B'
0x18000bee8  cmovnz  ecx, eax
0x18000beeb  mov     [rbp+57h+ObjectAttributes.Attributes], ecx
0x18000beee  jmp     loc_18000BE23
0x18000bef3  mov     ebx, 0C0000033h
0x18000bef8  jmp     short loc_18000BE7D
```
