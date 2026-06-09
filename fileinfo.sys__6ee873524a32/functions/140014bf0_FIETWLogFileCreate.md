# FIETWLogFileCreate

- ea: `0x140014bf0`
- end: `0x140014db1`
- name: `FIETWLogFileCreate`
- size: `449`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140016bc0`
- `0x140016dc0`

## callees

- `0x140003920`
- `0x140003a00`
- `0x140014bf0`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x140014ca7`
- `ntoskrnl!PsGetThreadId` at `0x140014ca7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140014d96`
- `ntoskrnl!RtlInitUnicodeString` at `0x140014d96`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140014d15`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140014d15`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140014d5b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140014d5b`
- `FLTMGR!FltGetFileNameInformation` at `0x140014c66`
- `FLTMGR!FltGetFileNameInformation` at `0x140014c66`

## pseudocode

```c
void __fastcall FIETWLogFileCreate(struct _FLT_CALLBACK_DATA *a1, __int64 a2, FLT_FILE_NAME_OPTIONS a3, __int16 a4)
{
  void (__fastcall *v7)(const PETHREAD, _QWORD *, __int64, __int64, __int16, __int128 *); // rdi
  struct _KTHREAD *Thread; // rcx
  unsigned int ThreadId; // eax
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  int ActivityIdCallbackData; // eax
  __int128 *v12; // rdx
  __int16 v13; // [rsp+40h] [rbp-59h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+48h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-49h] BYREF
  __int128 v16; // [rsp+60h] [rbp-39h] BYREF
  __int128 v17; // [rsp+70h] [rbp-29h]
  __int64 v18; // [rsp+80h] [rbp-19h]
  __int128 v19; // [rsp+88h] [rbp-11h] BYREF
  _QWORD v20[3]; // [rsp+98h] [rbp-1h] BYREF
  int Length; // [rsp+B0h] [rbp+17h]
  int v22; // [rsp+B4h] [rbp+1Bh]
  __int16 *v23; // [rsp+B8h] [rbp+1Fh]
  __int64 v24; // [rsp+C0h] [rbp+27h]

  v18 = 0;
  v16 = 0;
  v13 = 0;
  v17 = 0;
  FileNameInformation = 0;
  DestinationString = 0;
  v19 = 0;
  v7 = *(void (__fastcall **)(const PETHREAD, _QWORD *, __int64, __int64, __int16, __int128 *))(qword_140009A00 + 16);
  if ( v7 )
  {
    if ( FltGetFileNameInformation(a1, a3, &FileNameInformation) < 0 )
      RtlInitUnicodeString(&DestinationString, FIUnknown);
    else
      DestinationString = FileNameInformation->Name;
    Thread = a1->Thread;
    v18 = 0;
    v16 = (unsigned __int64)a1;
    v17 = 0;
    if ( Thread )
      ThreadId = (unsigned int)PsGetThreadId(Thread);
    else
      ThreadId = -1;
    Iopb = a1->Iopb;
    LODWORD(v17) = ThreadId;
    *((_QWORD *)&v16 + 1) = *(_QWORD *)(a2 + 32);
    DWORD1(v17) = Iopb->Parameters.Create.Options;
    DWORD2(v17) = Iopb->Parameters.Create.FileAttributes;
    HIDWORD(v17) = Iopb->Parameters.Create.ShareAccess;
    v20[0] = &v16;
    v20[2] = DestinationString.Buffer;
    Length = DestinationString.Length;
    v23 = &v13;
    v20[1] = 32;
    v22 = 0;
    v13 = 0;
    v24 = 2;
    ActivityIdCallbackData = FltGetActivityIdCallbackData(a1, &v19);
    v12 = &v19;
    if ( ActivityIdCallbackData < 0 )
      v12 = 0;
    v7(a1->Thread, v20, 3, 0x4000000, a4, v12);
  }
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
}

```

## disassembly

```asm
0x140014bf0  mov     [rsp-8+arg_8], rbx
0x140014bf5  push    rbp
0x140014bf6  push    rsi
0x140014bf7  push    rdi
0x140014bf8  push    r14
0x140014bfa  push    r15
0x140014bfc  lea     rbp, [rsp-37h]
0x140014c01  sub     rsp, 0D0h
0x140014c08  mov     rax, cs:__security_cookie
0x140014c0f  xor     rax, rsp
0x140014c12  mov     [rbp+57h+var_28], rax
0x140014c16  xor     eax, eax
0x140014c18  xorps   xmm0, xmm0
0x140014c1b  xor     r15d, r15d
0x140014c1e  mov     [rbp+57h+var_70], rax
0x140014c22  mov     rax, cs:qword_140009A00
0x140014c29  xorps   xmm1, xmm1
0x140014c2c  movups  [rbp+57h+var_90], xmm0
0x140014c30  mov     [rbp+57h+var_B0], r15w
0x140014c35  movzx   r14d, r9w
0x140014c39  movups  [rbp+57h+var_80], xmm0
0x140014c3d  mov     [rbp+57h+FileNameInformation], r15
0x140014c41  mov     r10d, r8d
0x140014c44  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140014c48  mov     rsi, rdx
0x140014c4b  mov     rbx, rcx
0x140014c4e  movups  [rbp+57h+var_68], xmm1
0x140014c52  mov     rdi, [rax+10h]
0x140014c56  test    rdi, rdi
0x140014c59  jz      loc_140014D52
0x140014c5f  lea     r8, [rbp+57h+FileNameInformation]; FileNameInformation
0x140014c63  mov     edx, r10d; NameOptions
0x140014c66  call    cs:__imp_FltGetFileNameInformation
0x140014c6d  nop     dword ptr [rax+rax+00h]
0x140014c72  test    eax, eax
0x140014c74  js      loc_140014D8B
0x140014c7a  mov     rax, [rbp+57h+FileNameInformation]
0x140014c7e  movups  xmm0, xmmword ptr [rax+8]
0x140014c82  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140014c86  mov     rcx, [rbx+8]; Thread
0x140014c8a  xorps   xmm0, xmm0
0x140014c8d  mov     qword ptr [rbp+57h+var_90+8], r15
0x140014c91  mov     [rbp+57h+var_70], r15
0x140014c95  mov     qword ptr [rbp+57h+var_90], rbx
0x140014c99  movdqu  [rbp+57h+var_80], xmm0
0x140014c9e  test    rcx, rcx
0x140014ca1  jz      loc_140014DA7
0x140014ca7  call    cs:__imp_PsGetThreadId
0x140014cae  nop     dword ptr [rax+rax+00h]
0x140014cb3  mov     rcx, [rbx+10h]
0x140014cb7  lea     rdx, [rbp+57h+var_68]
0x140014cbb  mov     dword ptr [rbp+57h+var_80], eax
0x140014cbe  mov     rax, [rsi+20h]
0x140014cc2  mov     qword ptr [rbp+57h+var_90+8], rax
0x140014cc6  mov     eax, [rcx+20h]
0x140014cc9  mov     dword ptr [rbp+57h+var_80+4], eax
0x140014ccc  movzx   eax, word ptr [rcx+28h]
0x140014cd0  mov     dword ptr [rbp+57h+var_80+8], eax
0x140014cd3  movzx   eax, word ptr [rcx+2Ah]
0x140014cd7  mov     rcx, rbx
0x140014cda  mov     dword ptr [rbp+57h+var_80+0Ch], eax
0x140014cdd  lea     rax, [rbp+57h+var_90]
0x140014ce1  mov     [rbp+57h+var_58], rax
0x140014ce5  mov     rax, [rbp+57h+DestinationString.Buffer]
0x140014ce9  mov     [rbp+57h+var_48], rax
0x140014ced  movzx   eax, [rbp+57h+DestinationString.Length]
0x140014cf1  mov     [rbp+57h+var_40], eax
0x140014cf4  lea     rax, [rbp+57h+var_B0]
0x140014cf8  mov     [rbp+57h+var_38], rax
0x140014cfc  mov     [rbp+57h+var_50], 20h ; ' '
0x140014d04  mov     [rbp+57h+var_3C], r15d
0x140014d08  mov     [rbp+57h+var_B0], r15w
0x140014d0d  mov     [rbp+57h+var_30], 2
0x140014d15  call    cs:__imp_FltGetActivityIdCallbackData
0x140014d1c  nop     dword ptr [rax+rax+00h]
0x140014d21  mov     rcx, [rbx+8]
0x140014d25  lea     rdx, [rbp+57h+var_68]
0x140014d29  test    eax, eax
0x140014d2b  mov     r9d, 4000000h
0x140014d31  mov     r8d, 3
0x140014d37  mov     rax, rdi
0x140014d3a  cmovs   rdx, r15
0x140014d3e  mov     [rsp+0F0h+var_C8], rdx
0x140014d43  lea     rdx, [rbp+57h+var_58]
0x140014d47  mov     [rsp+0F0h+var_D0], r14w
0x140014d4d  call    _guard_dispatch_icall
0x140014d52  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140014d56  test    rcx, rcx
0x140014d59  jz      short loc_140014D67
0x140014d5b  call    cs:__imp_FltReleaseFileNameInformation
0x140014d62  nop     dword ptr [rax+rax+00h]
0x140014d67  mov     rcx, [rbp+57h+var_28]
0x140014d6b  xor     rcx, rsp; StackCookie
0x140014d6e  call    __security_check_cookie
0x140014d73  mov     rbx, [rsp+0F0h+arg_8]
0x140014d7b  add     rsp, 0D0h
0x140014d82  pop     r15
0x140014d84  pop     r14
0x140014d86  pop     rdi
0x140014d87  pop     rsi
0x140014d88  pop     rbp
0x140014d89  retn
0x140014d8b  lea     rdx, FIUnknown; "\\FI_UNKNOWN"
0x140014d92  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140014d96  call    cs:__imp_RtlInitUnicodeString
0x140014d9d  nop     dword ptr [rax+rax+00h]
0x140014da2  jmp     loc_140014C86
0x140014da7  mov     eax, 0FFFFFFFFh
0x140014dac  jmp     loc_140014CB3
```
