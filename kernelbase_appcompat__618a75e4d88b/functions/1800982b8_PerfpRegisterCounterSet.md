# PerfpRegisterCounterSet

- ea: `0x1800982b8`
- end: `0x18009852f`
- name: `PerfpRegisterCounterSet`
- size: `631`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180098ee8`

## callees

- `0x1800982b8`
- `0x180098538`
- `0x1800985d0`
- `0x180162770`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800983b5`
- `ntdll!RtlInitUnicodeString` at `0x1800983b5`
- `ntdll!NtOpenFile` at `0x18009840a`
- `ntdll!NtOpenFile` at `0x18009840a`
- `ntdll!RtlNtStatusToDosError` at `0x1800984ca`
- `ntdll!RtlNtStatusToDosError` at `0x1800984ca`
- `ntdll!TpAllocIoCompletion` at `0x180098440`
- `ntdll!TpAllocIoCompletion` at `0x180098440`
- `ntdll!NtClose` at `0x18009847d`
- `ntdll!NtClose` at `0x1800984bc`
- `ntdll!NtClose` at `0x18009847d`
- `ntdll!NtClose` at `0x1800984bc`
- `ntdll!TpCancelAsyncIoOperation` at `0x1800984db`
- `ntdll!TpCancelAsyncIoOperation` at `0x1800984db`
- `ntdll!TpReleaseIoCompletion` at `0x1800984ea`
- `ntdll!TpReleaseIoCompletion` at `0x1800984ea`
- `ntdll!TpStartAsyncIoOperation` at `0x180098455`
- `ntdll!TpStartAsyncIoOperation` at `0x180098455`

## pseudocode

```c
ULONG __fastcall PerfpRegisterCounterSet(__int64 a1)
{
  __int64 v2; // r15
  int v3; // edx
  int v4; // r8d
  int v5; // r9d
  int v6; // r10d
  int v7; // r11d
  int v8; // ebx
  int v9; // edi
  int v10; // esi
  __int64 v11; // r9
  NTSTATUS v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  _QWORD *v15; // rbx
  int v16; // edi
  NTSTATUS v18; // ecx
  int v19; // [rsp+48h] [rbp-B8h]
  int v20; // [rsp+60h] [rbp-A0h]
  int v21; // [rsp+68h] [rbp-98h]
  HANDLE FileHandle; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v23[2]; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t pszDest[40]; // [rsp+E0h] [rbp-20h] BYREF

  FileHandle = 0;
  v23[0] = 1966108;
  v2 = a1 + 192;
  v3 = *(unsigned __int8 *)(a1 + 205);
  v4 = *(unsigned __int8 *)(a1 + 204);
  v5 = *(unsigned __int8 *)(a1 + 203);
  v6 = *(unsigned __int8 *)(a1 + 202);
  v7 = *(unsigned __int8 *)(a1 + 201);
  v8 = *(unsigned __int8 *)(a1 + 200);
  v9 = *(unsigned __int16 *)(a1 + 198);
  v10 = *(unsigned __int16 *)(a1 + 196);
  v23[1] = L"\\Device\\PcwDrv";
  v21 = *(unsigned __int8 *)(a1 + 207);
  v20 = *(unsigned __int8 *)(a1 + 206);
  v19 = v5;
  v11 = *(unsigned int *)(a1 + 192);
  DestinationString = 0;
  IoStatusBlock = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  StringCbPrintfW(
    pszDest,
    0x50u,
    L"{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
    v11,
    v10,
    v9,
    v8,
    v7,
    v6,
    v19,
    v4,
    v3,
    v20,
    v21);
  RtlInitUnicodeString(&DestinationString, pszDest);
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v23;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  v12 = NtOpenFile(&FileHandle, 1u, &ObjectAttributes, &IoStatusBlock, 7u, 0);
  if ( v12 < 0 )
  {
    if ( v12 == -1073741772 )
    {
      *(_QWORD *)(a1 + 160) = 0;
      *(_QWORD *)(a1 + 168) = 0;
      if ( (Microsoft_Windows_Diagnosis_PCWEnableBits & 0x20) != 0 )
        McTemplateU0jj_EtwEventWriteTransfer(v14, v13, a1 + 208, v2);
      return 0;
    }
    v18 = v12;
  }
  else
  {
    v15 = (_QWORD *)(a1 + 160);
    v16 = TpAllocIoCompletion(a1 + 160, FileHandle, PerfpNotificationCallback, a1, 0);
    if ( v16 < 0 )
    {
      NtClose(FileHandle);
    }
    else
    {
      TpStartAsyncIoOperation(*v15);
      v16 = PcwRegisterCounterSet((PVOID)(a1 + 168));
      NtClose(FileHandle);
      if ( v16 >= 0 )
        return 0;
      TpCancelAsyncIoOperation(*v15);
      TpReleaseIoCompletion(*v15);
    }
    v18 = v16;
  }
  return RtlNtStatusToDosError(v18);
}

```

## disassembly

```asm
0x1800982b8  push    rbp
0x1800982ba  push    rbx
0x1800982bb  push    rsi
0x1800982bc  push    rdi
0x1800982bd  push    r14
0x1800982bf  push    r15
0x1800982c1  lea     rbp, [rsp-48h]
0x1800982c6  sub     rsp, 148h
0x1800982cd  mov     rax, cs:__security_cookie
0x1800982d4  xor     rax, rsp
0x1800982d7  mov     [rbp+70h+var_40], rax
0x1800982db  mov     r14, rcx
0x1800982de  mov     [rsp+170h+FileHandle], 0
0x1800982e7  xorps   xmm0, xmm0
0x1800982ea  mov     [rsp+170h+var_F8], 1E001Ch
0x1800982f3  lea     r15, [rcx+0C0h]
0x1800982fa  lea     rax, aDevicePcwdrv; "\\Device\\PcwDrv"
0x180098301  movzx   edx, byte ptr [r14+0CDh]
0x180098309  movzx   r8d, byte ptr [r14+0CCh]
0x180098311  movzx   r9d, byte ptr [r14+0CBh]
0x180098319  movzx   r10d, byte ptr [r14+0CAh]
0x180098321  movzx   r11d, byte ptr [r14+0C9h]
0x180098329  movzx   ebx, byte ptr [r14+0C8h]
0x180098331  movzx   edi, word ptr [r14+0C6h]
0x180098339  movzx   esi, word ptr [r14+0C4h]
0x180098341  mov     [rbp+70h+var_F0], rax
0x180098345  xor     eax, eax
0x180098347  movzx   eax, byte ptr [rcx+0CFh]
0x18009834e  movzx   ecx, byte ptr [rcx+0CEh]
0x180098355  mov     [rsp+170h+var_108], eax
0x180098359  mov     [rsp+170h+var_110], ecx
0x18009835d  lea     rcx, [rbp+70h+pszDest]; pszDest
0x180098361  mov     [rsp+170h+var_118], edx
0x180098365  mov     edx, 50h ; 'P'; cbDest
0x18009836a  mov     [rsp+170h+var_120], r8d
0x18009836f  lea     r8, a08lx04x04x02x0; "{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%"...
0x180098376  mov     [rsp+170h+var_128], r9d
0x18009837b  mov     r9d, [r15]
0x18009837e  mov     [rsp+170h+var_130], r10d
0x180098383  mov     [rsp+170h+var_138], r11d
0x180098388  mov     [rsp+170h+var_140], ebx
0x18009838c  movups  xmmword ptr [rbp+70h+ObjectAttributes.ObjectName], xmm0
0x180098390  mov     [rsp+170h+OpenOptions], edi
0x180098394  mov     [rsp+170h+ShareAccess], esi
0x180098398  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x18009839c  movups  xmmword ptr [rbp+70h+IoStatusBlock], xmm0
0x1800983a0  movups  xmmword ptr [rbp+70h+ObjectAttributes.Length], xmm0
0x1800983a4  movups  xmmword ptr [rbp+70h+ObjectAttributes+1Ch], xmm0
0x1800983a8  call    StringCbPrintfW
0x1800983ad  lea     rdx, [rbp+70h+pszDest]; SourceString
0x1800983b1  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x1800983b5  call    cs:__imp_RtlInitUnicodeString
0x1800983bc  nop     dword ptr [rax+rax+00h]
0x1800983c1  lea     rax, [rsp+170h+var_F8]
0x1800983c6  mov     [rsp+170h+OpenOptions], 0; OpenOptions
0x1800983ce  xorps   xmm0, xmm0
0x1800983d1  mov     [rbp+70h+ObjectAttributes.ObjectName], rax
0x1800983d5  lea     r9, [rbp+70h+IoStatusBlock]; IoStatusBlock
0x1800983d9  mov     [rbp+70h+ObjectAttributes.Length], 30h ; '0'
0x1800983e0  lea     r8, [rbp+70h+ObjectAttributes]; ObjectAttributes
0x1800983e4  mov     [rbp+70h+ObjectAttributes.RootDirectory], 0
0x1800983ec  mov     edx, 1; DesiredAccess
0x1800983f1  mov     [rbp+70h+ObjectAttributes.Attributes], 40h ; '@'
0x1800983f8  lea     rcx, [rsp+170h+FileHandle]; FileHandle
0x1800983fd  mov     [rsp+170h+ShareAccess], 7; ShareAccess
0x180098405  movdqu  xmmword ptr [rbp+70h+ObjectAttributes.SecurityDescriptor], xmm0
0x18009840a  call    cs:__imp_NtOpenFile
0x180098411  nop     dword ptr [rax+rax+00h]
0x180098416  test    eax, eax
0x180098418  js      loc_1800984AC
0x18009841e  mov     rdx, [rsp+170h+FileHandle]
0x180098423  lea     rbx, [r14+0A0h]
0x18009842a  mov     rcx, rbx
0x18009842d  mov     qword ptr [rsp+170h+ShareAccess], 0
0x180098436  mov     r9, r14
0x180098439  lea     r8, PerfpNotificationCallback
0x180098440  call    cs:__imp_TpAllocIoCompletion
0x180098447  nop     dword ptr [rax+rax+00h]
0x18009844c  mov     edi, eax
0x18009844e  test    eax, eax
0x180098450  js      short loc_1800984B7
0x180098452  mov     rcx, [rbx]
0x180098455  call    cs:__imp_TpStartAsyncIoOperation
0x18009845c  nop     dword ptr [rax+rax+00h]
0x180098461  mov     r8, [rsp+170h+FileHandle]
0x180098466  lea     rcx, [r14+0A8h]; OutputBuffer
0x18009846d  lea     rdx, [rbp+70h+DestinationString]
0x180098471  call    PcwRegisterCounterSet
0x180098476  mov     rcx, [rsp+170h+FileHandle]; Handle
0x18009847b  mov     edi, eax
0x18009847d  call    cs:__imp_NtClose
0x180098484  nop     dword ptr [rax+rax+00h]
0x180098489  test    edi, edi
0x18009848b  js      short loc_1800984D8
0x18009848d  xor     eax, eax
0x18009848f  mov     rcx, [rbp+70h+var_40]
0x180098493  xor     rcx, rsp; StackCookie
0x180098496  call    __security_check_cookie
0x18009849b  add     rsp, 148h
0x1800984a2  pop     r15
0x1800984a4  pop     r14
0x1800984a6  pop     rdi
0x1800984a7  pop     rsi
0x1800984a8  pop     rbx
0x1800984a9  pop     rbp
0x1800984aa  retn
0x1800984ac  cmp     eax, 0C0000034h
0x1800984b1  jz      short loc_1800984F8
0x1800984b3  mov     ecx, eax
0x1800984b5  jmp     short loc_1800984CA
0x1800984b7  mov     rcx, [rsp+170h+FileHandle]; Handle
0x1800984bc  call    cs:__imp_NtClose
0x1800984c3  nop     dword ptr [rax+rax+00h]
0x1800984c8  mov     ecx, edi; Status
0x1800984ca  call    cs:__imp_RtlNtStatusToDosError
0x1800984d1  nop     dword ptr [rax+rax+00h]
0x1800984d6  jmp     short loc_18009848F
0x1800984d8  mov     rcx, [rbx]
0x1800984db  call    cs:__imp_TpCancelAsyncIoOperation
0x1800984e2  nop     dword ptr [rax+rax+00h]
0x1800984e7  mov     rcx, [rbx]
0x1800984ea  call    cs:__imp_TpReleaseIoCompletion
0x1800984f1  nop     dword ptr [rax+rax+00h]
0x1800984f6  jmp     short loc_1800984C8
0x1800984f8  mov     qword ptr [r14+0A0h], 0
0x180098503  mov     qword ptr [r14+0A8h], 0
0x18009850e  test    cs:Microsoft_Windows_Diagnosis_PCWEnableBits, 20h
0x180098515  jz      loc_18009848D
0x18009851b  lea     r8, [r14+0D0h]
0x180098522  mov     r9, r15
0x180098525  call    McTemplateU0jj_EtwEventWriteTransfer
0x18009852a  jmp     loc_18009848D
```
