# OpenDxBltEvent(unsigned __int64,void * *)

- ea: `0x180008b60`
- end: `0x180008e02`
- name: `?OpenDxBltEvent@@YAJ_KPEAPEAX@Z`
- size: `674`
- prototype: `__int64 __fastcall(unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008990`

## callees

- `0x180008b60`
- `0x180008e08`
- `0x180042de0`
- `0x180228490`
- `0x18022943c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180008c1e`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180008c1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008cdc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008cdc`
- `ntdll!NtQueryDirectoryObject` at `0x180008c5c`
- `ntdll!NtQueryDirectoryObject` at `0x180008c5c`
- `ntdll!NtOpenDirectoryObject` at `0x180008d89`
- `ntdll!NtOpenDirectoryObject` at `0x180008d89`
- `ntdll!RtlInitUnicodeString` at `0x180008d4d`
- `ntdll!RtlInitUnicodeString` at `0x180008d4d`

## pseudocode

```c
__int64 __fastcall OpenDxBltEvent(__int64 a1, void **a2)
{
  BOOLEAN v4; // di
  int v5; // eax
  unsigned int v6; // ebx
  HANDLE v7; // rax
  HANDLE v8; // rcx
  NTSTATUS v9; // eax
  int v10; // ebx
  NTSTATUS v12; // ebx
  unsigned int RestartScan; // [rsp+20h] [rbp-E0h]
  HANDLE DirectoryHandle; // [rsp+40h] [rbp-C0h] BYREF
  ULONG Context; // [rsp+48h] [rbp-B8h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE Buffer[560]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Name[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  DirectoryHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset_0(Buffer, 0, 0x228u);
  Context = 0;
  v4 = 1;
  v5 = StringCchPrintfW(Name, 0x104u, L"%s%I64x", L"DwmDxBltEvent_", a1);
  v6 = v5;
  if ( v5 < 0 )
  {
    RestartScan = 93;
    goto LABEL_9;
  }
  while ( 1 )
  {
    v7 = OpenEventW(2u, 0, Name);
    if ( v7 )
    {
      *a2 = v7;
      goto LABEL_10;
    }
    v8 = DirectoryHandle;
    if ( DirectoryHandle )
      goto LABEL_4;
    v5 = StringCchPrintfW(Name, 0x104u, L"\\Sessions\\%u\\AppContainerNamedObjects", NtCurrentPeb()->SessionId);
    v6 = v5;
    if ( v5 < 0 )
      break;
    RtlInitUnicodeString(&DestinationString, Name);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v12 = NtOpenDirectoryObject(&DirectoryHandle, 1u, &ObjectAttributes);
    if ( v12 < 0 )
    {
      v6 = v12 | 0x10000000;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1802D2C50, 3u, v6, 0x84u, 0);
      goto LABEL_10;
    }
    v8 = DirectoryHandle;
LABEL_4:
    v9 = NtQueryDirectoryObject(v8, Buffer, 0x228u, 1u, v4, &Context, 0);
    v10 = v9;
    if ( v9 == -2147483622 )
    {
      v10 = -1073741772;
LABEL_17:
      v6 = v10 | 0x10000000;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1802D2C50, 3u, v6, 0x97u, 0);
      goto LABEL_10;
    }
    if ( v9 < 0 )
      goto LABEL_17;
    v5 = StringCchPrintfW(Name, 0x104u, L"AppContainerNamedObjects\\%wZ\\%s%I64x", Buffer, L"DwmDxBltEvent_", a1);
    v6 = v5;
    if ( v5 < 0 )
    {
      RestartScan = 163;
      goto LABEL_9;
    }
    v4 = 0;
  }
  RestartScan = 123;
LABEL_9:
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1802D2C50, 3u, v5, RestartScan, 0);
LABEL_10:
  if ( DirectoryHandle )
    CloseHandle(DirectoryHandle);
  return v6;
}

```

## disassembly

```asm
0x180008b60  mov     [rsp-8+arg_10], rbx
0x180008b65  mov     [rsp-8+arg_18], rsi
0x180008b6a  push    rbp
0x180008b6b  push    rdi
0x180008b6c  push    r12
0x180008b6e  push    r14
0x180008b70  push    r15
0x180008b72  lea     rbp, [rsp-3E0h]
0x180008b7a  sub     rsp, 4E0h
0x180008b81  mov     rax, cs:__security_cookie
0x180008b88  xor     rax, rsp
0x180008b8b  mov     [rbp+400h+var_30], rax
0x180008b92  xorps   xmm1, xmm1
0x180008b95  mov     r14, rdx
0x180008b98  mov     rsi, rcx
0x180008b9b  xorps   xmm0, xmm0
0x180008b9e  xor     r15d, r15d
0x180008ba1  lea     rcx, [rbp+400h+Buffer]; void *
0x180008ba5  xor     edx, edx; Val
0x180008ba7  mov     [rsp+500h+DirectoryHandle], r15
0x180008bac  mov     r8d, 228h; Size
0x180008bb2  movups  xmmword ptr [rsp+500h+DestinationString.Length], xmm0
0x180008bb7  movups  xmmword ptr [rsp+500h+ObjectAttributes.Length], xmm1
0x180008bbc  movups  xmmword ptr [rsp+500h+ObjectAttributes.ObjectName], xmm1
0x180008bc1  movups  xmmword ptr [rbp+400h+ObjectAttributes.SecurityDescriptor], xmm1
0x180008bc5  call    memset_0
0x180008bca  lea     r12, aDwmdxbltevent; "DwmDxBltEvent_"
0x180008bd1  mov     [rsp+500h+var_4B8], r15d
0x180008bd6  mov     r9, r12
0x180008bd9  mov     qword ptr [rsp+500h+RestartScan], rsi
0x180008bde  lea     r8, aSI64x; "%s%I64x"
0x180008be5  mov     edx, 104h; unsigned __int64
0x180008bea  lea     rcx, [rbp+400h+Name]; unsigned __int16 *
0x180008bf1  mov     dil, 1
0x180008bf4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008bf9  mov     ebx, eax
0x180008bfb  test    eax, eax
0x180008bfd  js      loc_180008DF0
0x180008c03  nop     dword ptr [rax+00h]
0x180008c07  nop     word ptr [rax+rax+00000000h]
0x180008c10  lea     r8, [rbp+400h+Name]; lpName
0x180008c17  xor     edx, edx; bInheritHandle
0x180008c19  mov     ecx, 2; dwDesiredAccess
0x180008c1e  call    cs:__imp_OpenEventW
0x180008c24  test    rax, rax
0x180008c27  jnz     loc_180008DBD
0x180008c2d  mov     rcx, [rsp+500h+DirectoryHandle]; DirectoryHandle
0x180008c32  test    rcx, rcx
0x180008c35  jz      loc_180008D0F
0x180008c3b  lea     rax, [rsp+500h+var_4B8]
0x180008c40  mov     [rsp+500h+ReturnLength], r15; ReturnLength
0x180008c45  mov     [rsp+500h+Context], rax; Context
0x180008c4a  lea     rdx, [rbp+400h+Buffer]; Buffer
0x180008c4e  mov     r9b, 1; ReturnSingleEntry
0x180008c51  mov     [rsp+500h+RestartScan], dil; RestartScan
0x180008c56  mov     r8d, 228h; BufferLength
0x180008c5c  call    cs:__imp_NtQueryDirectoryObject
0x180008c62  mov     ebx, eax
0x180008c64  cmp     eax, 8000001Ah
0x180008c69  jz      loc_180008D9F
0x180008c6f  test    eax, eax
0x180008c71  js      loc_180008DA4
0x180008c77  mov     [rsp+500h+Context], rsi
0x180008c7c  lea     r9, [rbp+400h+Buffer]
0x180008c80  lea     r8, aAppcontainerna; "AppContainerNamedObjects\\%wZ\\%s%I64x"
0x180008c87  mov     qword ptr [rsp+500h+RestartScan], r12
0x180008c8c  mov     edx, 104h; unsigned __int64
0x180008c91  lea     rcx, [rbp+400h+Name]; unsigned __int16 *
0x180008c98  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008c9d  mov     ebx, eax
0x180008c9f  test    eax, eax
0x180008ca1  js      short loc_180008CAB
0x180008ca3  xor     dil, dil
0x180008ca6  jmp     loc_180008C10
0x180008cab  mov     [rsp+500h+Context], r15; void *
0x180008cb0  mov     dword ptr [rsp+500h+RestartScan], 0A3h; unsigned int
0x180008cb8  mov     r9d, eax; int
0x180008cbb  mov     r8d, 3; unsigned int
0x180008cc1  lea     rdx, qword_1802D2C50; int *
0x180008cc8  mov     ecx, 14h; unsigned int
0x180008ccd  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180008cd2  mov     rcx, [rsp+500h+DirectoryHandle]; hObject
0x180008cd7  test    rcx, rcx
0x180008cda  jz      short loc_180008CE2
0x180008cdc  call    cs:__imp_CloseHandle
0x180008ce2  mov     eax, ebx
0x180008ce4  mov     rcx, [rbp+400h+var_30]
0x180008ceb  xor     rcx, rsp; StackCookie
0x180008cee  call    __security_check_cookie
0x180008cf3  lea     r11, [rsp+500h+var_20]
0x180008cfb  mov     rbx, [r11+40h]
0x180008cff  mov     rsi, [r11+48h]
0x180008d03  mov     rsp, r11
0x180008d06  pop     r15
0x180008d08  pop     r14
0x180008d0a  pop     r12
0x180008d0c  pop     rdi
0x180008d0d  pop     rbp
0x180008d0e  retn
0x180008d0f  mov     r9, gs:60h
0x180008d18  lea     r8, aSessionsUAppco; "\\Sessions\\%u\\AppContainerNamedObject"...
0x180008d1f  mov     edx, 104h; unsigned __int64
0x180008d24  lea     rcx, [rbp+400h+Name]; unsigned __int16 *
0x180008d2b  mov     r9d, [r9+2C0h]
0x180008d32  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008d37  mov     ebx, eax
0x180008d39  test    eax, eax
0x180008d3b  js      loc_180008DDE
0x180008d41  lea     rdx, [rbp+400h+Name]; SourceString
0x180008d48  lea     rcx, [rsp+500h+DestinationString]; DestinationString
0x180008d4d  call    cs:__imp_RtlInitUnicodeString
0x180008d53  lea     rax, [rsp+500h+DestinationString]
0x180008d58  mov     [rsp+500h+ObjectAttributes.Length], 30h ; '0'
0x180008d60  xorps   xmm0, xmm0
0x180008d63  mov     [rsp+500h+ObjectAttributes.ObjectName], rax
0x180008d68  lea     r8, [rsp+500h+ObjectAttributes]; ObjectAttributes
0x180008d6d  mov     [rsp+500h+ObjectAttributes.RootDirectory], r15
0x180008d72  mov     edx, 1; DesiredAccess
0x180008d77  mov     [rsp+500h+ObjectAttributes.Attributes], 40h ; '@'
0x180008d7f  lea     rcx, [rsp+500h+DirectoryHandle]; FileHandle
0x180008d84  movdqu  xmmword ptr [rbp+400h+ObjectAttributes.SecurityDescriptor], xmm0
0x180008d89  call    cs:__imp_NtOpenDirectoryObject
0x180008d8f  mov     ebx, eax
0x180008d91  test    eax, eax
0x180008d93  js      short loc_180008DC5
0x180008d95  mov     rcx, [rsp+500h+DirectoryHandle]
0x180008d9a  jmp     loc_180008C3B
0x180008d9f  mov     ebx, 0C0000034h
0x180008da4  bts     ebx, 1Ch
0x180008da8  mov     [rsp+500h+Context], r15
0x180008dad  mov     r9d, ebx
0x180008db0  mov     dword ptr [rsp+500h+RestartScan], 97h
0x180008db8  jmp     loc_180008CBB
0x180008dbd  mov     [r14], rax
0x180008dc0  jmp     loc_180008CD2
0x180008dc5  bts     ebx, 1Ch
0x180008dc9  mov     [rsp+500h+Context], r15
0x180008dce  mov     r9d, ebx
0x180008dd1  mov     dword ptr [rsp+500h+RestartScan], 84h
0x180008dd9  jmp     loc_180008CBB
0x180008dde  mov     [rsp+500h+Context], r15
0x180008de3  mov     dword ptr [rsp+500h+RestartScan], 7Bh ; '{'
0x180008deb  jmp     loc_180008CB8
0x180008df0  mov     [rsp+500h+Context], r15
0x180008df5  mov     dword ptr [rsp+500h+RestartScan], 5Dh ; ']'
0x180008dfd  jmp     loc_180008CB8
```
