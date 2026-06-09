# BasepGetExeArchType

- ea: `0x180025600`
- end: `0x1800257ca`
- name: `BasepGetExeArchType`
- size: `458`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025510`

## callees

- `0x180025600`
- `0x18007a7dd`

## import_xrefs

- `ntdll!NtCreateSection` at `0x180025688`
- `ntdll!NtCreateSection` at `0x180025688`
- `ntdll!NtClose` at `0x1800256d2`
- `ntdll!NtClose` at `0x1800256d2`
- `ntdll!LdrQueryImageFileKeyOption` at `0x180025769`
- `ntdll!LdrQueryImageFileKeyOption` at `0x180025769`
- `ntdll!LdrOpenImageFileOptionsKey` at `0x180025739`
- `ntdll!LdrOpenImageFileOptionsKey` at `0x180025739`
- `ntdll!NtQuerySection` at `0x1800256a7`
- `ntdll!NtQuerySection` at `0x1800256a7`
- `ntdll!RtlInitUnicodeString` at `0x18002565e`
- `ntdll!RtlInitUnicodeString` at `0x18002565e`
- `ntdll!NtQuerySystemInformation` at `0x18002571d`
- `ntdll!NtQuerySystemInformation` at `0x18002571d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800256f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800256f9`

## pseudocode

```c
__int64 __fastcall BasepGetExeArchType(__int16 *a1, void *a2, const WCHAR *a3)
{
  __int16 v6; // si
  NTSTATUS Section; // ebx
  __int64 result; // rax
  NTSTATUS v9; // eax
  NTSTATUS v10; // eax
  void *SectionHandle; // [rsp+40h] [rbp-59h] BYREF
  void *NewKeyHandle; // [rsp+48h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-49h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+60h] [rbp-39h] BYREF
  _BYTE SectionInformation[48]; // [rsp+90h] [rbp-9h] BYREF
  __int16 v16; // [rsp+C0h] [rbp+27h]
  char v17; // [rsp+C3h] [rbp+2Ah]
  int SystemInformation; // [rsp+100h] [rbp+67h] BYREF
  int Buffer; // [rsp+118h] [rbp+7Fh] BYREF

  memset_0(SectionInformation, 0, 0x40u);
  SectionHandle = 0;
  v6 = 0;
  SystemInformation = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  NewKeyHandle = 0;
  Buffer = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a3);
  Section = NtCreateSection(&SectionHandle, 1u, 0, 0, 2u, 0x11000000u, a2);
  if ( Section >= 0 )
  {
    Section = NtQuerySection(SectionHandle, SectionImageInformation, SectionInformation, 0x40u, 0);
    if ( Section >= 0 )
    {
      v6 = v16;
      if ( v16 != 332 )
        goto LABEL_5;
      if ( (v17 & 1) == 0 )
        goto LABEL_5;
      GetSystemInfo(&SystemInfo);
      if ( SystemInfo.wProcessorArchitecture != 9 && SystemInfo.wProcessorArchitecture != 6 )
        goto LABEL_5;
      Section = NtQuerySystemInformation(SystemComPlusPackage, &SystemInformation, 4u, 0);
      if ( Section >= 0 )
      {
        if ( (SystemInformation & 1) != 0 )
        {
          v9 = LdrOpenImageFileOptionsKey(&DestinationString, 0, &NewKeyHandle);
          if ( v9 >= 0 )
          {
            v10 = LdrQueryImageFileKeyOption(NewKeyHandle, L"Wow64", 4u, &Buffer, 4u, 0);
            if ( v10 != -1073741772 && (v10 < 0 || !Buffer) )
              goto LABEL_5;
LABEL_20:
            if ( SystemInfo.wProcessorArchitecture == 6 )
            {
              v6 = 512;
            }
            else if ( SystemInfo.wProcessorArchitecture == 9 )
            {
              v6 = -31132;
            }
            goto LABEL_5;
          }
          if ( v9 == -1073741772 )
            goto LABEL_20;
        }
LABEL_5:
        Section = 0;
      }
    }
  }
  if ( SectionHandle )
    NtClose(SectionHandle);
  result = (unsigned int)Section;
  *a1 = v6;
  return result;
}

```

## disassembly

```asm
0x180025600  mov     [rsp-8+arg_8], rbx
0x180025605  push    rbp
0x180025606  push    rsi
0x180025607  push    rdi
0x180025608  push    r13
0x18002560a  push    r14
0x18002560c  lea     rbp, [rsp-37h]
0x180025611  sub     rsp, 0D0h
0x180025618  mov     rdi, rdx
0x18002561b  mov     rbx, r8
0x18002561e  xor     edx, edx; Val
0x180025620  mov     r14, rcx
0x180025623  lea     rcx, [rbp+57h+SectionInformation]; void *
0x180025627  lea     r8d, [rdx+40h]; Size
0x18002562b  call    memset_0
0x180025630  xorps   xmm0, xmm0
0x180025633  mov     [rbp+57h+SectionHandle], 0
0x18002563b  xor     esi, esi
0x18002563d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180025641  mov     rdx, rbx; SourceString
0x180025644  mov     [rbp+57h+SystemInformation], esi
0x180025647  movups  xmmword ptr [rbp+57h+SystemInfo], xmm0
0x18002564b  mov     [rbp+57h+NewKeyHandle], rsi
0x18002564f  movups  xmmword ptr [rbp+57h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180025653  mov     [rbp+57h+Buffer], esi
0x180025656  movups  xmmword ptr [rbp+57h+SystemInfo.dwNumberOfProcessors], xmm0
0x18002565a  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18002565e  call    cs:__imp_RtlInitUnicodeString
0x180025664  mov     [rsp+0F0h+FileHandle], rdi; FileHandle
0x180025669  lea     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x18002566d  lea     edi, [rsi+1]
0x180025670  mov     [rsp+0F0h+AllocationAttributes], 11000000h; AllocationAttributes
0x180025678  mov     edx, edi; DesiredAccess
0x18002567a  mov     [rsp+0F0h+SectionPageProtection], 2; SectionPageProtection
0x180025682  xor     r9d, r9d; MaximumSize
0x180025685  xor     r8d, r8d; ObjectAttributes
0x180025688  call    cs:__imp_NtCreateSection
0x18002568e  mov     ebx, eax
0x180025690  test    eax, eax
0x180025692  js      short loc_1800256C9
0x180025694  mov     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x180025698  lea     r9d, [rsi+40h]; Length
0x18002569c  lea     r8, [rbp+57h+SectionInformation]; SectionInformation
0x1800256a0  mov     qword ptr [rsp+0F0h+SectionPageProtection], rsi; ResultLength
0x1800256a5  mov     edx, edi; SectionInformationClass
0x1800256a7  call    cs:__imp_NtQuerySection
0x1800256ad  mov     ebx, eax
0x1800256af  test    eax, eax
0x1800256b1  js      short loc_1800256C9
0x1800256b3  movzx   esi, [rbp+57h+var_30]
0x1800256b7  mov     eax, 14Ch
0x1800256bc  cmp     si, ax
0x1800256bf  jnz     short loc_1800256C7
0x1800256c1  test    [rbp+57h+var_2D], dil
0x1800256c5  jnz     short loc_1800256F5
0x1800256c7  xor     ebx, ebx
0x1800256c9  mov     rcx, [rbp+57h+SectionHandle]; Handle
0x1800256cd  test    rcx, rcx
0x1800256d0  jz      short loc_1800256D8
0x1800256d2  call    cs:__imp_NtClose
0x1800256d8  mov     eax, ebx
0x1800256da  mov     [r14], si
0x1800256de  mov     rbx, [rsp+0F0h+arg_8]
0x1800256e6  add     rsp, 0D0h
0x1800256ed  pop     r14
0x1800256ef  pop     r13
0x1800256f1  pop     rdi
0x1800256f2  pop     rsi
0x1800256f3  pop     rbp
0x1800256f4  retn
0x1800256f5  lea     rcx, [rbp+57h+SystemInfo]; lpSystemInfo
0x1800256f9  call    cs:__imp_GetSystemInfo
0x1800256ff  mov     eax, 9
0x180025704  lea     r13d, [rax-3]
0x180025708  cmp     word ptr [rbp+57h+SystemInfo], ax
0x18002570c  jnz     short loc_180025789
0x18002570e  xor     r9d, r9d; ReturnLength
0x180025711  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x180025715  lea     r8d, [r9+4]; SystemInformationLength
0x180025719  lea     ecx, [r9+3Bh]; SystemInformationClass
0x18002571d  call    cs:__imp_NtQuerySystemInformation
0x180025723  mov     ebx, eax
0x180025725  test    eax, eax
0x180025727  js      short loc_1800256C9
0x180025729  test    byte ptr [rbp+57h+SystemInformation], dil
0x18002572d  jz      short loc_1800256C7
0x18002572f  lea     r8, [rbp+57h+NewKeyHandle]; NewKeyHandle
0x180025733  xor     edx, edx; Wow64
0x180025735  lea     rcx, [rbp+57h+DestinationString]; SubKey
0x180025739  call    cs:__imp_LdrOpenImageFileOptionsKey
0x18002573f  test    eax, eax
0x180025741  js      short loc_180025799
0x180025743  mov     rcx, [rbp+57h+NewKeyHandle]; KeyHandle
0x180025747  lea     r9, [rbp+57h+Buffer]; Buffer
0x18002574b  mov     qword ptr [rsp+0F0h+AllocationAttributes], 0; ReturnedLength
0x180025754  lea     rdx, aWow64; "Wow64"
0x18002575b  mov     r8d, 4; Type
0x180025761  mov     [rsp+0F0h+SectionPageProtection], 4; BufferSize
0x180025769  call    cs:__imp_LdrQueryImageFileKeyOption
0x18002576f  cmp     eax, 0C0000034h
0x180025774  jz      short loc_1800257A4
0x180025776  test    eax, eax
0x180025778  js      loc_1800256C7
0x18002577e  cmp     [rbp+57h+Buffer], 0
0x180025782  jnz     short loc_1800257A4
0x180025784  jmp     loc_1800256C7
0x180025789  cmp     word ptr [rbp+57h+SystemInfo], r13w
0x18002578e  jnz     loc_1800256C7
0x180025794  jmp     loc_18002570E
0x180025799  cmp     eax, 0C0000034h
0x18002579e  jnz     loc_1800256C7
0x1800257a4  movzx   eax, word ptr [rbp+57h+SystemInfo]
0x1800257a8  cmp     eax, r13d
0x1800257ab  jz      short loc_1800257C0
0x1800257ad  cmp     eax, 9
0x1800257b0  jnz     loc_1800256C7
0x1800257b6  mov     esi, 8664h
0x1800257bb  jmp     loc_1800256C7
0x1800257c0  mov     esi, 200h
0x1800257c5  jmp     loc_1800256C7
```
