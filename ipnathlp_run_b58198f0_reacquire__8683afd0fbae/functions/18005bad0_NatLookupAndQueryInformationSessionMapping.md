# NatLookupAndQueryInformationSessionMapping

- ea: `0x18005bad0`
- end: `0x18005bcc3`
- name: `NatLookupAndQueryInformationSessionMapping`
- size: `499`
- prototype: `__int64 __usercall@<rax>(HANDLE FileHandle@<rcx>, int, __int16, PVOID, __int64, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180084088`
- `0x180089100`

## callees

- `0x180051f30`
- `0x18005bad0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005bb42`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005bb42`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005bc31`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005bc31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005bc43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005bc91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005bc43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005bc91`
- `ntdll!NtDeviceIoControlFile` at `0x18005bc16`
- `ntdll!NtDeviceIoControlFile` at `0x18005bc16`
- `ntdll!RtlNtStatusToDosError` at `0x18005bc55`
- `ntdll!RtlNtStatusToDosError` at `0x18005bc55`

## pseudocode

```c
ULONG __fastcall NatLookupAndQueryInformationSessionMapping(
        HANDLE FileHandle,
        char a2,
        int a3,
        __int16 a4,
        int a5,
        __int16 a6,
        PVOID OutputBuffer,
        ULONG *a8,
        int a9)
{
  HANDLE EventW; // rsi
  NTSTATUS v14; // eax
  int Status; // edi
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-39h] BYREF
  __int128 InputBuffer; // [rsp+68h] [rbp-29h] BYREF
  __int16 v19; // [rsp+78h] [rbp-19h]

  LOBYTE(v19) = 0;
  IoStatusBlock = 0;
  InputBuffer = 0;
  if ( !a8 || a9 >= 3 )
    return 87;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
    return 8;
  WORD4(InputBuffer) = a4;
  HIDWORD(InputBuffer) = a5;
  v19 = a6;
  LOBYTE(InputBuffer) = a2;
  DWORD1(InputBuffer) = a3;
  if ( a9 )
  {
    if ( a9 == 1 )
    {
      v14 = NtDeviceIoControlFile(
              FileHandle,
              EventW,
              0,
              0,
              &IoStatusBlock,
              0x12805Cu,
              &InputBuffer,
              0x14u,
              OutputBuffer,
              *a8);
      goto LABEL_11;
    }
    if ( a9 == 2 )
    {
      v14 = NtDeviceIoControlFile(
              FileHandle,
              EventW,
              0,
              0,
              &IoStatusBlock,
              0x128060u,
              &InputBuffer,
              0x14u,
              OutputBuffer,
              *a8);
      goto LABEL_11;
    }
    CloseHandle(EventW);
    return 87;
  }
  v14 = NtDeviceIoControlFile(
          FileHandle,
          EventW,
          0,
          0,
          &IoStatusBlock,
          0x128058u,
          &InputBuffer,
          0x14u,
          OutputBuffer,
          *a8);
LABEL_11:
  Status = v14;
  if ( v14 == 259 )
  {
    WaitForSingleObject(EventW, 0xFFFFFFFF);
    Status = IoStatusBlock.Status;
  }
  CloseHandle(EventW);
  if ( Status < 0 )
    return RtlNtStatusToDosError(Status);
  if ( a9 )
  {
    if ( a9 == 1 )
      *a8 = 48;
    else
      *a8 = 40;
  }
  else
  {
    *a8 = 36;
  }
  return 0;
}

```

## disassembly

```asm
0x18005bad0  push    rbp
0x18005bad2  push    rbx
0x18005bad3  push    rsi
0x18005bad4  push    rdi
0x18005bad5  push    r12
0x18005bad7  push    r13
0x18005bad9  push    r14
0x18005badb  push    r15
0x18005badd  lea     rbp, [rsp-7]
0x18005bae2  sub     rsp, 98h
0x18005bae9  mov     rax, cs:__security_cookie
0x18005baf0  xor     rax, rsp
0x18005baf3  mov     [rbp+3Fh+var_50], rax
0x18005baf7  mov     r14, [rbp+3Fh+arg_38]
0x18005bafe  xor     eax, eax
0x18005bb00  mov     r15, [rbp+3Fh+arg_30]
0x18005bb04  xorps   xmm0, xmm0
0x18005bb07  mov     [rbp+3Fh+var_80], r9w
0x18005bb0c  mov     r13d, r8d
0x18005bb0f  mov     byte ptr [rbp+3Fh+var_58], al
0x18005bb12  mov     r12b, dl
0x18005bb15  mov     rdi, rcx
0x18005bb18  movups  xmmword ptr [rbp+3Fh+var_78], xmm0
0x18005bb1c  movups  [rbp+3Fh+var_68], xmm0
0x18005bb20  test    r14, r14
0x18005bb23  jz      loc_18005BC9D
0x18005bb29  mov     ebx, [rbp+3Fh+arg_40]
0x18005bb2f  cmp     ebx, 3
0x18005bb32  jge     loc_18005BC9D
0x18005bb38  xor     r9d, r9d; lpName
0x18005bb3b  xor     r8d, r8d; bInitialState
0x18005bb3e  xor     edx, edx; bManualReset
0x18005bb40  xor     ecx, ecx; lpEventAttributes
0x18005bb42  call    cs:__imp_CreateEventW
0x18005bb49  nop     dword ptr [rax+rax+00h]
0x18005bb4e  mov     rsi, rax
0x18005bb51  test    rax, rax
0x18005bb54  jnz     short loc_18005BB5E
0x18005bb56  lea     eax, [rsi+8]
0x18005bb59  jmp     loc_18005BCA2
0x18005bb5e  movzx   eax, [rbp+3Fh+var_80]
0x18005bb62  mov     word ptr [rbp+3Fh+var_68+8], ax
0x18005bb66  mov     eax, [rbp+3Fh+arg_20]
0x18005bb69  mov     dword ptr [rbp+3Fh+var_68+0Ch], eax
0x18005bb6c  movzx   eax, [rbp+3Fh+arg_28]
0x18005bb70  mov     [rbp+3Fh+var_58], ax
0x18005bb74  mov     byte ptr [rbp+3Fh+var_68], r12b
0x18005bb78  mov     dword ptr [rbp+3Fh+var_68+4], r13d
0x18005bb7c  test    ebx, ebx
0x18005bb7e  jnz     short loc_18005BBA7
0x18005bb80  mov     eax, [r14]
0x18005bb83  mov     [rsp+0D0h+OutputBufferLength], eax
0x18005bb87  lea     rax, [rbp+3Fh+var_68]
0x18005bb8b  mov     [rsp+0D0h+OutputBuffer], r15
0x18005bb90  mov     [rsp+0D0h+InputBufferLength], 14h
0x18005bb98  mov     [rsp+0D0h+InputBuffer], rax
0x18005bb9d  mov     [rsp+0D0h+IoControlCode], 128058h
0x18005bba5  jmp     short loc_18005BC01
0x18005bba7  cmp     ebx, 1
0x18005bbaa  jnz     short loc_18005BBD3
0x18005bbac  mov     eax, [r14]
0x18005bbaf  mov     [rsp+0D0h+OutputBufferLength], eax
0x18005bbb3  lea     rax, [rbp+3Fh+var_68]
0x18005bbb7  mov     [rsp+0D0h+OutputBuffer], r15
0x18005bbbc  mov     [rsp+0D0h+InputBufferLength], 14h
0x18005bbc4  mov     [rsp+0D0h+InputBuffer], rax
0x18005bbc9  mov     [rsp+0D0h+IoControlCode], 12805Ch
0x18005bbd1  jmp     short loc_18005BC01
0x18005bbd3  cmp     ebx, 2
0x18005bbd6  jnz     loc_18005BC8E
0x18005bbdc  mov     eax, [r14]
0x18005bbdf  mov     [rsp+0D0h+OutputBufferLength], eax; OutputBufferLength
0x18005bbe3  lea     rax, [rbp+3Fh+var_68]
0x18005bbe7  mov     [rsp+0D0h+OutputBuffer], r15; OutputBuffer
0x18005bbec  mov     [rsp+0D0h+InputBufferLength], 14h; InputBufferLength
0x18005bbf4  mov     [rsp+0D0h+InputBuffer], rax; InputBuffer
0x18005bbf9  mov     [rsp+0D0h+IoControlCode], 128060h; IoControlCode
0x18005bc01  lea     rax, [rbp+3Fh+var_78]
0x18005bc05  xor     r9d, r9d; ApcContext
0x18005bc08  xor     r8d, r8d; ApcRoutine
0x18005bc0b  mov     [rsp+0D0h+IoStatusBlock], rax; IoStatusBlock
0x18005bc10  mov     rdx, rsi; Event
0x18005bc13  mov     rcx, rdi; FileHandle
0x18005bc16  call    cs:__imp_NtDeviceIoControlFile
0x18005bc1d  nop     dword ptr [rax+rax+00h]
0x18005bc22  mov     edi, eax
0x18005bc24  cmp     eax, 103h
0x18005bc29  jnz     short loc_18005BC40
0x18005bc2b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18005bc2e  mov     rcx, rsi; hHandle
0x18005bc31  call    cs:__imp_WaitForSingleObject
0x18005bc38  nop     dword ptr [rax+rax+00h]
0x18005bc3d  mov     edi, dword ptr [rbp+3Fh+var_78]
0x18005bc40  mov     rcx, rsi; hObject
0x18005bc43  call    cs:__imp_CloseHandle
0x18005bc4a  nop     dword ptr [rax+rax+00h]
0x18005bc4f  test    edi, edi
0x18005bc51  jns     short loc_18005BC63
0x18005bc53  mov     ecx, edi; Status
0x18005bc55  call    cs:__imp_RtlNtStatusToDosError
0x18005bc5c  nop     dword ptr [rax+rax+00h]
0x18005bc61  jmp     short loc_18005BCA2
0x18005bc63  test    ebx, ebx
0x18005bc65  jz      short loc_18005BC83
0x18005bc67  sub     ebx, 1
0x18005bc6a  jz      short loc_18005BC7A
0x18005bc6c  cmp     ebx, 1
0x18005bc6f  jnz     short loc_18005BC9D
0x18005bc71  mov     dword ptr [r14], 28h ; '('
0x18005bc78  jmp     short loc_18005BC8A
0x18005bc7a  mov     dword ptr [r14], 30h ; '0'
0x18005bc81  jmp     short loc_18005BC8A
0x18005bc83  mov     dword ptr [r14], 24h ; '$'
0x18005bc8a  xor     eax, eax
0x18005bc8c  jmp     short loc_18005BCA2
0x18005bc8e  mov     rcx, rsi; hObject
0x18005bc91  call    cs:__imp_CloseHandle
0x18005bc98  nop     dword ptr [rax+rax+00h]
0x18005bc9d  mov     eax, 57h ; 'W'
0x18005bca2  mov     rcx, [rbp+3Fh+var_50]
0x18005bca6  xor     rcx, rsp; StackCookie
0x18005bca9  call    __security_check_cookie
0x18005bcae  add     rsp, 98h
0x18005bcb5  pop     r15
0x18005bcb7  pop     r14
0x18005bcb9  pop     r13
0x18005bcbb  pop     r12
0x18005bcbd  pop     rdi
0x18005bcbe  pop     rsi
0x18005bcbf  pop     rbx
0x18005bcc0  pop     rbp
0x18005bcc1  retn
```
