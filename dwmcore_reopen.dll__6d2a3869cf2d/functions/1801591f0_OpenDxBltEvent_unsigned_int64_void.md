# OpenDxBltEvent(unsigned __int64,void * *)

- ea: `0x1801591f0`
- end: `0x180159492`
- name: `?OpenDxBltEvent@@YAJ_KPEAPEAX@Z`
- size: `674`
- prototype: `__int64 __fastcall(unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180159020`

## callees

- `0x180050270`
- `0x1801591f0`
- `0x180159498`
- `0x1802284b0`
- `0x18022945c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1801592ae`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1801592ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18015936c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18015936c`
- `ntdll!NtQueryDirectoryObject` at `0x1801592ec`
- `ntdll!NtQueryDirectoryObject` at `0x1801592ec`
- `ntdll!NtOpenDirectoryObject` at `0x180159419`
- `ntdll!NtOpenDirectoryObject` at `0x180159419`
- `ntdll!RtlInitUnicodeString` at `0x1801593dd`
- `ntdll!RtlInitUnicodeString` at `0x1801593dd`

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
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_18032ADA0, 3u, v6, 0x84u, 0);
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
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_18032ADA0, 3u, v6, 0x97u, 0);
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
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_18032ADA0, 3u, v5, RestartScan, 0);
LABEL_10:
  if ( DirectoryHandle )
    CloseHandle(DirectoryHandle);
  return v6;
}

```

## disassembly

```asm
0x1801591f0  mov     [rsp-8+arg_10], rbx
0x1801591f5  mov     [rsp-8+arg_18], rsi
0x1801591fa  push    rbp
0x1801591fb  push    rdi
0x1801591fc  push    r12
0x1801591fe  push    r14
0x180159200  push    r15
0x180159202  lea     rbp, [rsp-3E0h]
0x18015920a  sub     rsp, 4E0h
0x180159211  mov     rax, cs:__security_cookie
0x180159218  xor     rax, rsp
0x18015921b  mov     [rbp+400h+var_30], rax
0x180159222  xorps   xmm1, xmm1
0x180159225  mov     r14, rdx
0x180159228  mov     rsi, rcx
0x18015922b  xorps   xmm0, xmm0
0x18015922e  xor     r15d, r15d
0x180159231  lea     rcx, [rbp+400h+Buffer]; void *
0x180159235  xor     edx, edx; Val
0x180159237  mov     [rsp+500h+DirectoryHandle], r15
0x18015923c  mov     r8d, 228h; Size
0x180159242  movups  xmmword ptr [rsp+500h+DestinationString.Length], xmm0
0x180159247  movups  xmmword ptr [rsp+500h+ObjectAttributes.Length], xmm1
0x18015924c  movups  xmmword ptr [rsp+500h+ObjectAttributes.ObjectName], xmm1
0x180159251  movups  xmmword ptr [rbp+400h+ObjectAttributes.SecurityDescriptor], xmm1
0x180159255  call    memset_0
0x18015925a  lea     r12, aDwmdxbltevent; "DwmDxBltEvent_"
0x180159261  mov     [rsp+500h+var_4B8], r15d
0x180159266  mov     r9, r12
0x180159269  mov     qword ptr [rsp+500h+RestartScan], rsi
0x18015926e  lea     r8, aSI64x; "%s%I64x"
0x180159275  mov     edx, 104h; unsigned __int64
0x18015927a  lea     rcx, [rbp+400h+Name]; unsigned __int16 *
0x180159281  mov     dil, 1
0x180159284  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180159289  mov     ebx, eax
0x18015928b  test    eax, eax
0x18015928d  js      loc_180159480
0x180159293  nop     dword ptr [rax+00h]
0x180159297  nop     word ptr [rax+rax+00000000h]
0x1801592a0  lea     r8, [rbp+400h+Name]; lpName
0x1801592a7  xor     edx, edx; bInheritHandle
0x1801592a9  mov     ecx, 2; dwDesiredAccess
0x1801592ae  call    cs:__imp_OpenEventW
0x1801592b4  test    rax, rax
0x1801592b7  jnz     loc_18015944D
0x1801592bd  mov     rcx, [rsp+500h+DirectoryHandle]; DirectoryHandle
0x1801592c2  test    rcx, rcx
0x1801592c5  jz      loc_18015939F
0x1801592cb  lea     rax, [rsp+500h+var_4B8]
0x1801592d0  mov     [rsp+500h+ReturnLength], r15; ReturnLength
0x1801592d5  mov     [rsp+500h+Context], rax; Context
0x1801592da  lea     rdx, [rbp+400h+Buffer]; Buffer
0x1801592de  mov     r9b, 1; ReturnSingleEntry
0x1801592e1  mov     [rsp+500h+RestartScan], dil; RestartScan
0x1801592e6  mov     r8d, 228h; BufferLength
0x1801592ec  call    cs:__imp_NtQueryDirectoryObject
0x1801592f2  mov     ebx, eax
0x1801592f4  cmp     eax, 8000001Ah
0x1801592f9  jz      loc_18015942F
0x1801592ff  test    eax, eax
0x180159301  js      loc_180159434
0x180159307  mov     [rsp+500h+Context], rsi
0x18015930c  lea     r9, [rbp+400h+Buffer]
0x180159310  lea     r8, aAppcontainerna; "AppContainerNamedObjects\\%wZ\\%s%I64x"
0x180159317  mov     qword ptr [rsp+500h+RestartScan], r12
0x18015931c  mov     edx, 104h; unsigned __int64
0x180159321  lea     rcx, [rbp+400h+Name]; unsigned __int16 *
0x180159328  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18015932d  mov     ebx, eax
0x18015932f  test    eax, eax
0x180159331  js      short loc_18015933B
0x180159333  xor     dil, dil
0x180159336  jmp     loc_1801592A0
0x18015933b  mov     [rsp+500h+Context], r15; void *
0x180159340  mov     dword ptr [rsp+500h+RestartScan], 0A3h; unsigned int
0x180159348  mov     r9d, eax; int
0x18015934b  mov     r8d, 3; unsigned int
0x180159351  lea     rdx, dword_18032ADA0; int *
0x180159358  mov     ecx, 14h; unsigned int
0x18015935d  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180159362  mov     rcx, [rsp+500h+DirectoryHandle]; hObject
0x180159367  test    rcx, rcx
0x18015936a  jz      short loc_180159372
0x18015936c  call    cs:__imp_CloseHandle
0x180159372  mov     eax, ebx
0x180159374  mov     rcx, [rbp+400h+var_30]
0x18015937b  xor     rcx, rsp; StackCookie
0x18015937e  call    __security_check_cookie
0x180159383  lea     r11, [rsp+500h+var_20]
0x18015938b  mov     rbx, [r11+40h]
0x18015938f  mov     rsi, [r11+48h]
0x180159393  mov     rsp, r11
0x180159396  pop     r15
0x180159398  pop     r14
0x18015939a  pop     r12
0x18015939c  pop     rdi
0x18015939d  pop     rbp
0x18015939e  retn
0x18015939f  mov     r9, gs:60h
0x1801593a8  lea     r8, aSessionsUAppco; "\\Sessions\\%u\\AppContainerNamedObject"...
0x1801593af  mov     edx, 104h; unsigned __int64
0x1801593b4  lea     rcx, [rbp+400h+Name]; unsigned __int16 *
0x1801593bb  mov     r9d, [r9+2C0h]
0x1801593c2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801593c7  mov     ebx, eax
0x1801593c9  test    eax, eax
0x1801593cb  js      loc_18015946E
0x1801593d1  lea     rdx, [rbp+400h+Name]; SourceString
0x1801593d8  lea     rcx, [rsp+500h+DestinationString]; DestinationString
0x1801593dd  call    cs:__imp_RtlInitUnicodeString
0x1801593e3  lea     rax, [rsp+500h+DestinationString]
0x1801593e8  mov     [rsp+500h+ObjectAttributes.Length], 30h ; '0'
0x1801593f0  xorps   xmm0, xmm0
0x1801593f3  mov     [rsp+500h+ObjectAttributes.ObjectName], rax
0x1801593f8  lea     r8, [rsp+500h+ObjectAttributes]; ObjectAttributes
0x1801593fd  mov     [rsp+500h+ObjectAttributes.RootDirectory], r15
0x180159402  mov     edx, 1; DesiredAccess
0x180159407  mov     [rsp+500h+ObjectAttributes.Attributes], 40h ; '@'
0x18015940f  lea     rcx, [rsp+500h+DirectoryHandle]; FileHandle
0x180159414  movdqu  xmmword ptr [rbp+400h+ObjectAttributes.SecurityDescriptor], xmm0
0x180159419  call    cs:__imp_NtOpenDirectoryObject
0x18015941f  mov     ebx, eax
0x180159421  test    eax, eax
0x180159423  js      short loc_180159455
0x180159425  mov     rcx, [rsp+500h+DirectoryHandle]
0x18015942a  jmp     loc_1801592CB
0x18015942f  mov     ebx, 0C0000034h
0x180159434  bts     ebx, 1Ch
0x180159438  mov     [rsp+500h+Context], r15
0x18015943d  mov     r9d, ebx
0x180159440  mov     dword ptr [rsp+500h+RestartScan], 97h
0x180159448  jmp     loc_18015934B
0x18015944d  mov     [r14], rax
0x180159450  jmp     loc_180159362
0x180159455  bts     ebx, 1Ch
0x180159459  mov     [rsp+500h+Context], r15
0x18015945e  mov     r9d, ebx
0x180159461  mov     dword ptr [rsp+500h+RestartScan], 84h
0x180159469  jmp     loc_18015934B
0x18015946e  mov     [rsp+500h+Context], r15
0x180159473  mov     dword ptr [rsp+500h+RestartScan], 7Bh ; '{'
0x18015947b  jmp     loc_180159348
0x180159480  mov     [rsp+500h+Context], r15
0x180159485  mov     dword ptr [rsp+500h+RestartScan], 5Dh ; ']'
0x18015948d  jmp     loc_180159348
```
