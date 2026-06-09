# NatLookupAndQueryInformationSessionMapping

- ea: `0x1800575b0`
- end: `0x18005777e`
- name: `NatLookupAndQueryInformationSessionMapping`
- size: `462`
- prototype: `ULONG __fastcall(HANDLE FileHandle, char, int, __int16, int, __int16, PVOID OutputBuffer, ULONG *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18007dc48`
- `0x1800829c0`

## callees

- `0x18004e0c0`
- `0x1800575b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180057622`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180057622`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180057705`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180057705`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057711`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057753`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057711`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057753`
- `ntdll!NtDeviceIoControlFile` at `0x1800576f0`
- `ntdll!NtDeviceIoControlFile` at `0x1800576f0`
- `ntdll!RtlNtStatusToDosError` at `0x18005771d`
- `ntdll!RtlNtStatusToDosError` at `0x18005771d`

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
0x1800575b0  push    rbp
0x1800575b2  push    rbx
0x1800575b3  push    rsi
0x1800575b4  push    rdi
0x1800575b5  push    r12
0x1800575b7  push    r13
0x1800575b9  push    r14
0x1800575bb  push    r15
0x1800575bd  lea     rbp, [rsp-7]
0x1800575c2  sub     rsp, 98h
0x1800575c9  mov     rax, cs:__security_cookie
0x1800575d0  xor     rax, rsp
0x1800575d3  mov     [rbp+3Fh+var_50], rax
0x1800575d7  mov     r14, [rbp+3Fh+arg_38]
0x1800575de  xor     eax, eax
0x1800575e0  mov     r15, [rbp+3Fh+arg_30]
0x1800575e4  xorps   xmm0, xmm0
0x1800575e7  mov     [rbp+3Fh+var_80], r9w
0x1800575ec  mov     r13d, r8d
0x1800575ef  mov     byte ptr [rbp+3Fh+var_58], al
0x1800575f2  mov     r12b, dl
0x1800575f5  mov     rdi, rcx
0x1800575f8  movups  xmmword ptr [rbp+3Fh+var_78], xmm0
0x1800575fc  movups  [rbp+3Fh+var_68], xmm0
0x180057600  test    r14, r14
0x180057603  jz      loc_180057759
0x180057609  mov     ebx, [rbp+3Fh+arg_40]
0x18005760f  cmp     ebx, 3
0x180057612  jge     loc_180057759
0x180057618  xor     r9d, r9d; lpName
0x18005761b  xor     r8d, r8d; bInitialState
0x18005761e  xor     edx, edx; bManualReset
0x180057620  xor     ecx, ecx; lpEventAttributes
0x180057622  call    cs:__imp_CreateEventW
0x180057628  mov     rsi, rax
0x18005762b  test    rax, rax
0x18005762e  jnz     short loc_180057638
0x180057630  lea     eax, [rsi+8]
0x180057633  jmp     loc_18005775E
0x180057638  movzx   eax, [rbp+3Fh+var_80]
0x18005763c  mov     word ptr [rbp+3Fh+var_68+8], ax
0x180057640  mov     eax, [rbp+3Fh+arg_20]
0x180057643  mov     dword ptr [rbp+3Fh+var_68+0Ch], eax
0x180057646  movzx   eax, [rbp+3Fh+arg_28]
0x18005764a  mov     [rbp+3Fh+var_58], ax
0x18005764e  mov     byte ptr [rbp+3Fh+var_68], r12b
0x180057652  mov     dword ptr [rbp+3Fh+var_68+4], r13d
0x180057656  test    ebx, ebx
0x180057658  jnz     short loc_180057681
0x18005765a  mov     eax, [r14]
0x18005765d  mov     [rsp+0D0h+OutputBufferLength], eax
0x180057661  lea     rax, [rbp+3Fh+var_68]
0x180057665  mov     [rsp+0D0h+OutputBuffer], r15
0x18005766a  mov     [rsp+0D0h+InputBufferLength], 14h
0x180057672  mov     [rsp+0D0h+InputBuffer], rax
0x180057677  mov     [rsp+0D0h+IoControlCode], 128058h
0x18005767f  jmp     short loc_1800576DB
0x180057681  cmp     ebx, 1
0x180057684  jnz     short loc_1800576AD
0x180057686  mov     eax, [r14]
0x180057689  mov     [rsp+0D0h+OutputBufferLength], eax
0x18005768d  lea     rax, [rbp+3Fh+var_68]
0x180057691  mov     [rsp+0D0h+OutputBuffer], r15
0x180057696  mov     [rsp+0D0h+InputBufferLength], 14h
0x18005769e  mov     [rsp+0D0h+InputBuffer], rax
0x1800576a3  mov     [rsp+0D0h+IoControlCode], 12805Ch
0x1800576ab  jmp     short loc_1800576DB
0x1800576ad  cmp     ebx, 2
0x1800576b0  jnz     loc_180057750
0x1800576b6  mov     eax, [r14]
0x1800576b9  mov     [rsp+0D0h+OutputBufferLength], eax; OutputBufferLength
0x1800576bd  lea     rax, [rbp+3Fh+var_68]
0x1800576c1  mov     [rsp+0D0h+OutputBuffer], r15; OutputBuffer
0x1800576c6  mov     [rsp+0D0h+InputBufferLength], 14h; InputBufferLength
0x1800576ce  mov     [rsp+0D0h+InputBuffer], rax; InputBuffer
0x1800576d3  mov     [rsp+0D0h+IoControlCode], 128060h; IoControlCode
0x1800576db  lea     rax, [rbp+3Fh+var_78]
0x1800576df  xor     r9d, r9d; ApcContext
0x1800576e2  xor     r8d, r8d; ApcRoutine
0x1800576e5  mov     [rsp+0D0h+IoStatusBlock], rax; IoStatusBlock
0x1800576ea  mov     rdx, rsi; Event
0x1800576ed  mov     rcx, rdi; FileHandle
0x1800576f0  call    cs:__imp_NtDeviceIoControlFile
0x1800576f6  mov     edi, eax
0x1800576f8  cmp     eax, 103h
0x1800576fd  jnz     short loc_18005770E
0x1800576ff  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180057702  mov     rcx, rsi; hHandle
0x180057705  call    cs:__imp_WaitForSingleObject
0x18005770b  mov     edi, dword ptr [rbp+3Fh+var_78]
0x18005770e  mov     rcx, rsi; hObject
0x180057711  call    cs:__imp_CloseHandle
0x180057717  test    edi, edi
0x180057719  jns     short loc_180057725
0x18005771b  mov     ecx, edi; Status
0x18005771d  call    cs:__imp_RtlNtStatusToDosError
0x180057723  jmp     short loc_18005775E
0x180057725  test    ebx, ebx
0x180057727  jz      short loc_180057745
0x180057729  sub     ebx, 1
0x18005772c  jz      short loc_18005773C
0x18005772e  cmp     ebx, 1
0x180057731  jnz     short loc_180057759
0x180057733  mov     dword ptr [r14], 28h ; '('
0x18005773a  jmp     short loc_18005774C
0x18005773c  mov     dword ptr [r14], 30h ; '0'
0x180057743  jmp     short loc_18005774C
0x180057745  mov     dword ptr [r14], 24h ; '$'
0x18005774c  xor     eax, eax
0x18005774e  jmp     short loc_18005775E
0x180057750  mov     rcx, rsi; hObject
0x180057753  call    cs:__imp_CloseHandle
0x180057759  mov     eax, 57h ; 'W'
0x18005775e  mov     rcx, [rbp+3Fh+var_50]
0x180057762  xor     rcx, rsp; StackCookie
0x180057765  call    __security_check_cookie
0x18005776a  add     rsp, 98h
0x180057771  pop     r15
0x180057773  pop     r14
0x180057775  pop     r13
0x180057777  pop     r12
0x180057779  pop     rdi
0x18005777a  pop     rsi
0x18005777b  pop     rbx
0x18005777c  pop     rbp
0x18005777d  retn
```
