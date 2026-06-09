# WfpCreateRegDomain

- ea: `0x18000ffdc`
- end: `0x1800101a1`
- name: `WfpCreateRegDomain`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x1800106f0`

## callees

- `0x18000438c`
- `0x180005fc8`
- `0x18000ffdc`
- `0x180012bd0`
- `0x18004a0d1`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180010044`
- `ntdll!RtlInitUnicodeString` at `0x180010044`
- `ntdll!NtCreateFile` at `0x18001015d`
- `ntdll!NtCreateFile` at `0x18001015d`

## string_xrefs

- `0x1800100bd`: `WfpRioRDOpen`

## pseudocode

```c
__int64 __fastcall WfpCreateRegDomain(_OWORD *a1, _WORD *a2, NTSTATUS *a3)
{
  __int64 v6; // rdi
  __int64 v7; // rax
  ULONG EaLength; // r15d
  unsigned __int8 *EaBuffer; // rbx
  __int64 v11; // rax
  __int64 v12; // rcx
  PVOID v13; // [rsp+60h] [rbp-49h] BYREF
  void *FileHandle; // [rsp+68h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp+7h] BYREF

  FileHandle = 0;
  v13 = 0;
  *a3 = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  *(&ObjectAttributes.Length + 1) = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\WfpL2\\WfpRioRegDomain");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  v6 = -1;
  ObjectAttributes.RootDirectory = 0;
  v7 = -1;
  ObjectAttributes.Attributes = 64;
  do
    ++v7;
  while ( a2[v7] );
  EaLength = 2 * v7 + 48;
  WfpMemAlloc(EaLength, 8u);
  EaBuffer = (unsigned __int8 *)v13;
  if ( v13 )
  {
    *(_DWORD *)v13 = 0;
    *((_WORD *)EaBuffer + 2) = 3072;
    strcpy((char *)EaBuffer + 8, "WfpRioRDOpen");
    v11 = -1;
    do
      ++v11;
    while ( a2[v11] );
    *((_WORD *)EaBuffer + 3) = 2 * (v11 + 11);
    v12 = EaBuffer[5];
    *(_OWORD *)&EaBuffer[v12 + 9] = *a1;
    do
      ++v6;
    while ( a2[v6] );
    *(_DWORD *)&EaBuffer[v12 + 25] = 2 * v6;
    memcpy_0(&EaBuffer[v12 + 29], a2, (unsigned int)(2 * v6));
    *a3 = NtCreateFile(&FileHandle, 0xC0000000, &ObjectAttributes, &IoStatusBlock, 0, 0, 0, 3u, 0, EaBuffer, EaLength);
    WfpMemFree(&v13);
    return (__int64)FileHandle;
  }
  else
  {
    *a3 = -1073741670;
    return -1;
  }
}

```

## disassembly

```asm
0x18000ffdc  mov     [rsp-8+arg_0], rbx
0x18000ffe1  push    rbp
0x18000ffe2  push    rsi
0x18000ffe3  push    rdi
0x18000ffe4  push    r12
0x18000ffe6  push    r13
0x18000ffe8  push    r14
0x18000ffea  push    r15
0x18000ffec  lea     rbp, [rsp-27h]
0x18000fff1  sub     rsp, 0D0h
0x18000fff8  mov     rax, cs:__security_cookie
0x18000ffff  xor     rax, rsp
0x180010002  mov     [rbp+57h+var_40], rax
0x180010006  xorps   xmm0, xmm0
0x180010009  xor     r13d, r13d
0x18001000c  mov     rsi, rdx
0x18001000f  mov     [rbp+57h+FileHandle], r13
0x180010013  mov     r12, rcx
0x180010016  mov     [rbp+57h+var_A0], r13
0x18001001a  xorps   xmm1, xmm1
0x18001001d  mov     [r8], r13d
0x180010020  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180010024  xor     eax, eax
0x180010026  lea     rdx, aDeviceWfpl2Wfp; "\\Device\\WfpL2\\WfpRioRegDomain"
0x18001002d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180010031  mov     r14, r8
0x180010034  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180010038  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18001003c  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180010040  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x180010044  call    cs:__imp_RtlInitUnicodeString
0x18001004b  nop     dword ptr [rax+rax+00h]
0x180010050  lea     rax, [rbp+57h+DestinationString]
0x180010054  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001005b  xorps   xmm0, xmm0
0x18001005e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180010062  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180010066  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x18001006a  mov     rax, rdi
0x18001006d  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180010074  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180010079  inc     rax
0x18001007c  cmp     [rsi+rax*2], r13w
0x180010081  jnz     short loc_180010079
0x180010083  lea     r15d, ds:30h[rax*2]
0x18001008b  mov     edx, 8; dwFlags
0x180010090  mov     ecx, r15d; dwBytes
0x180010093  lea     r8, [rbp+57h+var_A0]
0x180010097  call    WfpMemAlloc
0x18001009c  mov     rbx, [rbp+57h+var_A0]
0x1800100a0  test    rbx, rbx
0x1800100a3  jnz     short loc_1800100B4
0x1800100a5  mov     dword ptr [r14], 0C000009Ah
0x1800100ac  mov     rax, rdi
0x1800100af  jmp     loc_180010179
0x1800100b4  mov     [rbx], r13d
0x1800100b7  mov     word ptr [rbx+4], 0C00h
0x1800100bd  movsd   xmm0, qword ptr cs:aWfpriordopen; "WfpRioRDOpen"
0x1800100c5  movsd   qword ptr [rbx+8], xmm0
0x1800100ca  mov     eax, dword ptr cs:aWfpriordopen+8; "Open"
0x1800100d0  mov     [rbx+10h], eax
0x1800100d3  mov     al, byte ptr cs:aWfpriordopen+0Ch; ""
0x1800100d9  mov     [rbx+14h], al
0x1800100dc  mov     rax, rdi
0x1800100df  inc     rax
0x1800100e2  cmp     [rsi+rax*2], r13w
0x1800100e7  jnz     short loc_1800100DF
0x1800100e9  add     ax, 0Bh
0x1800100ed  add     ax, ax
0x1800100f0  mov     [rbx+6], ax
0x1800100f4  movzx   ecx, byte ptr [rbx+5]
0x1800100f8  movups  xmm0, xmmword ptr [r12]
0x1800100fd  movdqu  xmmword ptr [rcx+rbx+9], xmm0
0x180010103  inc     rdi
0x180010106  cmp     [rsi+rdi*2], r13w
0x18001010b  jnz     short loc_180010103
0x18001010d  lea     eax, [rdi+rdi]
0x180010110  mov     rdx, rsi; Src
0x180010113  mov     [rcx+rbx+19h], eax
0x180010117  add     rcx, 1Dh
0x18001011b  add     rcx, rbx; void *
0x18001011e  mov     r8d, eax; Size
0x180010121  call    memcpy_0
0x180010126  mov     [rsp+100h+EaLength], r15d; EaLength
0x18001012b  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18001012f  mov     [rsp+100h+EaBuffer], rbx; EaBuffer
0x180010134  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180010138  mov     [rsp+100h+CreateOptions], r13d; CreateOptions
0x18001013d  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180010141  mov     [rsp+100h+CreateDisposition], 3; CreateDisposition
0x180010149  mov     edx, 0C0000000h; DesiredAccess
0x18001014e  mov     [rsp+100h+ShareAccess], r13d; ShareAccess
0x180010153  mov     [rsp+100h+FileAttributes], r13d; FileAttributes
0x180010158  mov     [rsp+100h+AllocationSize], r13; AllocationSize
0x18001015d  call    cs:__imp_NtCreateFile
0x180010164  nop     dword ptr [rax+rax+00h]
0x180010169  lea     rcx, [rbp+57h+var_A0]
0x18001016d  mov     [r14], eax
0x180010170  call    WfpMemFree
0x180010175  mov     rax, [rbp+57h+FileHandle]
0x180010179  mov     rcx, [rbp+57h+var_40]
0x18001017d  xor     rcx, rsp; StackCookie
0x180010180  call    __security_check_cookie
0x180010185  mov     rbx, [rsp+100h+arg_0]
0x18001018d  add     rsp, 0D0h
0x180010194  pop     r15
0x180010196  pop     r14
0x180010198  pop     r13
0x18001019a  pop     r12
0x18001019c  pop     rdi
0x18001019d  pop     rsi
0x18001019e  pop     rbp
0x18001019f  retn
```
