# BasepGetExeArchType

- ea: `0x180023470`
- end: `0x18002366f`
- name: `BasepGetExeArchType`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180023380`

## callees

- `0x180023470`
- `0x18008275d`

## import_xrefs

- `ntdll!NtCreateSection` at `0x1800234fe`
- `ntdll!NtCreateSection` at `0x1800234fe`
- `ntdll!NtClose` at `0x180023554`
- `ntdll!NtClose` at `0x180023554`
- `ntdll!LdrQueryImageFileKeyOption` at `0x180023608`
- `ntdll!LdrQueryImageFileKeyOption` at `0x180023608`
- `ntdll!LdrOpenImageFileOptionsKey` at `0x1800235d2`
- `ntdll!LdrOpenImageFileOptionsKey` at `0x1800235d2`
- `ntdll!NtQuerySection` at `0x180023523`
- `ntdll!NtQuerySection` at `0x180023523`
- `ntdll!RtlInitUnicodeString` at `0x1800234ce`
- `ntdll!RtlInitUnicodeString` at `0x1800234ce`
- `ntdll!NtQuerySystemInformation` at `0x1800235b0`
- `ntdll!NtQuerySystemInformation` at `0x1800235b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180023582`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180023582`

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
0x180023470  mov     [rsp-8+arg_8], rbx
0x180023475  push    rbp
0x180023476  push    rsi
0x180023477  push    rdi
0x180023478  push    r13
0x18002347a  push    r14
0x18002347c  lea     rbp, [rsp-37h]
0x180023481  sub     rsp, 0D0h
0x180023488  mov     rdi, rdx
0x18002348b  mov     rbx, r8
0x18002348e  xor     edx, edx; Val
0x180023490  mov     r14, rcx
0x180023493  lea     rcx, [rbp+57h+SectionInformation]; void *
0x180023497  lea     r8d, [rdx+40h]; Size
0x18002349b  call    memset_0
0x1800234a0  xorps   xmm0, xmm0
0x1800234a3  mov     [rbp+57h+SectionHandle], 0
0x1800234ab  xor     esi, esi
0x1800234ad  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800234b1  mov     rdx, rbx; SourceString
0x1800234b4  mov     [rbp+57h+SystemInformation], esi
0x1800234b7  movups  xmmword ptr [rbp+57h+SystemInfo], xmm0
0x1800234bb  mov     [rbp+57h+NewKeyHandle], rsi
0x1800234bf  movups  xmmword ptr [rbp+57h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800234c3  mov     [rbp+57h+Buffer], esi
0x1800234c6  movups  xmmword ptr [rbp+57h+SystemInfo.dwNumberOfProcessors], xmm0
0x1800234ca  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800234ce  call    cs:__imp_RtlInitUnicodeString
0x1800234d5  nop     dword ptr [rax+rax+00h]
0x1800234da  mov     [rsp+0F0h+FileHandle], rdi; FileHandle
0x1800234df  lea     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x1800234e3  lea     edi, [rsi+1]
0x1800234e6  mov     [rsp+0F0h+AllocationAttributes], 11000000h; AllocationAttributes
0x1800234ee  mov     edx, edi; DesiredAccess
0x1800234f0  mov     [rsp+0F0h+SectionPageProtection], 2; SectionPageProtection
0x1800234f8  xor     r9d, r9d; MaximumSize
0x1800234fb  xor     r8d, r8d; ObjectAttributes
0x1800234fe  call    cs:__imp_NtCreateSection
0x180023505  nop     dword ptr [rax+rax+00h]
0x18002350a  mov     ebx, eax
0x18002350c  test    eax, eax
0x18002350e  js      short loc_18002354B
0x180023510  mov     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x180023514  lea     r9d, [rsi+40h]; Length
0x180023518  lea     r8, [rbp+57h+SectionInformation]; SectionInformation
0x18002351c  mov     qword ptr [rsp+0F0h+SectionPageProtection], rsi; ResultLength
0x180023521  mov     edx, edi; SectionInformationClass
0x180023523  call    cs:__imp_NtQuerySection
0x18002352a  nop     dword ptr [rax+rax+00h]
0x18002352f  mov     ebx, eax
0x180023531  test    eax, eax
0x180023533  js      short loc_18002354B
0x180023535  movzx   esi, [rbp+57h+var_30]
0x180023539  mov     eax, 14Ch
0x18002353e  cmp     si, ax
0x180023541  jnz     short loc_180023549
0x180023543  test    [rbp+57h+var_2D], dil
0x180023547  jnz     short loc_18002357E
0x180023549  xor     ebx, ebx
0x18002354b  mov     rcx, [rbp+57h+SectionHandle]; Handle
0x18002354f  test    rcx, rcx
0x180023552  jz      short loc_180023560
0x180023554  call    cs:__imp_NtClose
0x18002355b  nop     dword ptr [rax+rax+00h]
0x180023560  mov     eax, ebx
0x180023562  mov     [r14], si
0x180023566  mov     rbx, [rsp+0F0h+arg_8]
0x18002356e  add     rsp, 0D0h
0x180023575  pop     r14
0x180023577  pop     r13
0x180023579  pop     rdi
0x18002357a  pop     rsi
0x18002357b  pop     rbp
0x18002357c  retn
0x18002357e  lea     rcx, [rbp+57h+SystemInfo]; lpSystemInfo
0x180023582  call    cs:__imp_GetSystemInfo
0x180023589  nop     dword ptr [rax+rax+00h]
0x18002358e  mov     eax, 9
0x180023593  lea     r13d, [rax-3]
0x180023597  cmp     word ptr [rbp+57h+SystemInfo], ax
0x18002359b  jnz     loc_18002362E
0x1800235a1  xor     r9d, r9d; ReturnLength
0x1800235a4  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x1800235a8  lea     r8d, [r9+4]; SystemInformationLength
0x1800235ac  lea     ecx, [r9+3Bh]; SystemInformationClass
0x1800235b0  call    cs:__imp_NtQuerySystemInformation
0x1800235b7  nop     dword ptr [rax+rax+00h]
0x1800235bc  mov     ebx, eax
0x1800235be  test    eax, eax
0x1800235c0  js      short loc_18002354B
0x1800235c2  test    byte ptr [rbp+57h+SystemInformation], dil
0x1800235c6  jz      short loc_180023549
0x1800235c8  lea     r8, [rbp+57h+NewKeyHandle]; NewKeyHandle
0x1800235cc  xor     edx, edx; Wow64
0x1800235ce  lea     rcx, [rbp+57h+DestinationString]; SubKey
0x1800235d2  call    cs:__imp_LdrOpenImageFileOptionsKey
0x1800235d9  nop     dword ptr [rax+rax+00h]
0x1800235de  test    eax, eax
0x1800235e0  js      short loc_18002363E
0x1800235e2  mov     rcx, [rbp+57h+NewKeyHandle]; KeyHandle
0x1800235e6  lea     r9, [rbp+57h+Buffer]; Buffer
0x1800235ea  mov     qword ptr [rsp+0F0h+AllocationAttributes], 0; ReturnedLength
0x1800235f3  lea     rdx, aWow64; "Wow64"
0x1800235fa  mov     r8d, 4; Type
0x180023600  mov     [rsp+0F0h+SectionPageProtection], 4; BufferSize
0x180023608  call    cs:__imp_LdrQueryImageFileKeyOption
0x18002360f  nop     dword ptr [rax+rax+00h]
0x180023614  cmp     eax, 0C0000034h
0x180023619  jz      short loc_180023649
0x18002361b  test    eax, eax
0x18002361d  js      loc_180023549
0x180023623  cmp     [rbp+57h+Buffer], 0
0x180023627  jnz     short loc_180023649
0x180023629  jmp     loc_180023549
0x18002362e  cmp     word ptr [rbp+57h+SystemInfo], r13w
0x180023633  jnz     loc_180023549
0x180023639  jmp     loc_1800235A1
0x18002363e  cmp     eax, 0C0000034h
0x180023643  jnz     loc_180023549
0x180023649  movzx   eax, word ptr [rbp+57h+SystemInfo]
0x18002364d  cmp     eax, r13d
0x180023650  jz      short loc_180023665
0x180023652  cmp     eax, 9
0x180023655  jnz     loc_180023549
0x18002365b  mov     esi, 8664h
0x180023660  jmp     loc_180023549
0x180023665  mov     esi, 200h
0x18002366a  jmp     loc_180023549
```
