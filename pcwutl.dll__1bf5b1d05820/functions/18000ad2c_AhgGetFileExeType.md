# AhgGetFileExeType

- ea: `0x18000ad2c`
- end: `0x18000ae57`
- name: `AhgGetFileExeType`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180009cdc`

## callees

- `0x18000ad2c`
- `0x18000e240`
- `0x1800191a2`

## import_xrefs

- `ntdll!NtQuerySection` at `0x18000adec`
- `ntdll!NtQuerySection` at `0x18000adec`
- `ntdll!RtlNtStatusToDosError` at `0x18000ad98`
- `ntdll!RtlNtStatusToDosError` at `0x18000adf8`
- `ntdll!RtlNtStatusToDosError` at `0x18000ad98`
- `ntdll!RtlNtStatusToDosError` at `0x18000adf8`
- `ntdll!NtCreateSection` at `0x18000ad8c`
- `ntdll!NtCreateSection` at `0x18000ad8c`
- `ntdll!NtClose` at `0x18000ae42`
- `ntdll!NtClose` at `0x18000ae42`

## string_xrefs

- `0x18000adab`: `Failed to create section [%d]`

## pseudocode

```c
__int64 __fastcall AhgGetFileExeType(_WORD *a1, BOOL *a2, void *a3)
{
  int v6; // eax
  ULONG v7; // eax
  ULONG v8; // ebx
  const char *v9; // r9
  __int64 v10; // r8
  __int64 v11; // rcx
  int Section; // eax
  BOOL v13; // eax
  ULONG SectionPageProtection[2]; // [rsp+20h] [rbp-88h]
  _BYTE SectionInformation[48]; // [rsp+40h] [rbp-68h] BYREF
  __int16 v17; // [rsp+70h] [rbp-38h]
  char v18; // [rsp+73h] [rbp-35h]
  void *SectionHandle; // [rsp+B0h] [rbp+8h] BYREF

  SectionHandle = 0;
  memset_0(SectionInformation, 0, 0x40u);
  *a1 = 0;
  *a2 = 0;
  v6 = NtCreateSection(&SectionHandle, 1u, 0, 0, 2u, 0x11000000u, a3);
  if ( v6 < 0 )
  {
    v7 = RtlNtStatusToDosError(v6);
    v8 = v7;
    if ( v7 == 193 )
      goto LABEL_10;
    v9 = "Failed to create section [%d]";
    v10 = 150;
    v11 = 1;
    goto LABEL_4;
  }
  Section = NtQuerySection(SectionHandle, SectionImageInformation, SectionInformation, 0x40u, 0);
  if ( Section < 0 )
  {
    v7 = RtlNtStatusToDosError(Section);
    v9 = "Failed to get the section information [%d]";
    v10 = 163;
    v8 = v7;
    v11 = 2;
LABEL_4:
    SectionPageProtection[0] = v7;
    AslLogCallPrintf(v11, "AhgGetFileExeType", v10, v9, *(_QWORD *)SectionPageProtection);
    goto LABEL_10;
  }
  v13 = 0;
  if ( v17 == 332 )
    v13 = (v18 & 1) != 0;
  *a1 = v17;
  v8 = 0;
  *a2 = v13;
LABEL_10:
  if ( SectionHandle )
    NtClose(SectionHandle);
  return v8;
}

```

## disassembly

```asm
0x18000ad2c  mov     rax, rsp
0x18000ad2f  push    rbx
0x18000ad30  push    rsi
0x18000ad31  push    rdi
0x18000ad32  push    r14
0x18000ad34  sub     rsp, 88h
0x18000ad3b  mov     rdi, rdx
0x18000ad3e  mov     qword ptr [rax+8], 0
0x18000ad46  xor     edx, edx; Val
0x18000ad48  mov     rbx, r8
0x18000ad4b  mov     rsi, rcx
0x18000ad4e  lea     rcx, [rax-68h]; void *
0x18000ad52  lea     r8d, [rdx+40h]; Size
0x18000ad56  call    memset_0
0x18000ad5b  xor     eax, eax
0x18000ad5d  mov     [rsp+0A8h+FileHandle], rbx; FileHandle
0x18000ad62  mov     [rsi], ax
0x18000ad65  lea     rcx, [rsp+0A8h+SectionHandle]; SectionHandle
0x18000ad6d  mov     [rsp+0A8h+AllocationAttributes], 11000000h; AllocationAttributes
0x18000ad75  xor     r9d, r9d; MaximumSize
0x18000ad78  xor     r8d, r8d; ObjectAttributes
0x18000ad7b  mov     [rdi], eax
0x18000ad7d  lea     r14d, [rax+1]
0x18000ad81  mov     [rsp+0A8h+SectionPageProtection], 2; SectionPageProtection
0x18000ad89  mov     edx, r14d; DesiredAccess
0x18000ad8c  call    cs:__imp_NtCreateSection
0x18000ad92  test    eax, eax
0x18000ad94  jns     short loc_18000ADCD
0x18000ad96  mov     ecx, eax; Status
0x18000ad98  call    cs:__imp_RtlNtStatusToDosError
0x18000ad9e  mov     ebx, eax
0x18000ada0  cmp     eax, 0C1h
0x18000ada5  jz      loc_18000AE35
0x18000adab  lea     r9, aFailedToCreate_0; "Failed to create section [%d]"
0x18000adb2  mov     r8d, 96h
0x18000adb8  mov     ecx, r14d
0x18000adbb  lea     rdx, aAhggetfileexet; "AhgGetFileExeType"
0x18000adc2  mov     [rsp+0A8h+SectionPageProtection], eax
0x18000adc6  call    AslLogCallPrintf
0x18000adcb  jmp     short loc_18000AE35
0x18000adcd  mov     rcx, [rsp+0A8h+SectionHandle]; SectionHandle
0x18000add5  lea     r8, [rsp+0A8h+SectionInformation]; SectionInformation
0x18000adda  mov     r9d, 40h ; '@'; Length
0x18000ade0  mov     qword ptr [rsp+0A8h+SectionPageProtection], 0; ResultLength
0x18000ade9  mov     edx, r14d; SectionInformationClass
0x18000adec  call    cs:__imp_NtQuerySection
0x18000adf2  test    eax, eax
0x18000adf4  jns     short loc_18000AE14
0x18000adf6  mov     ecx, eax; Status
0x18000adf8  call    cs:__imp_RtlNtStatusToDosError
0x18000adfe  lea     r9, aFailedToGetThe_1; "Failed to get the section information ["...
0x18000ae05  mov     r8d, 0A3h
0x18000ae0b  mov     ebx, eax
0x18000ae0d  mov     ecx, 2
0x18000ae12  jmp     short loc_18000ADBB
0x18000ae14  movzx   ecx, [rsp+0A8h+var_38]
0x18000ae19  xor     eax, eax
0x18000ae1b  mov     edx, 14Ch
0x18000ae20  cmp     cx, dx
0x18000ae23  jnz     short loc_18000AE2E
0x18000ae25  test    [rsp+0A8h+var_35], r14b
0x18000ae2a  cmovnz  eax, r14d
0x18000ae2e  mov     [rsi], cx
0x18000ae31  xor     ebx, ebx
0x18000ae33  mov     [rdi], eax
0x18000ae35  mov     rcx, [rsp+0A8h+SectionHandle]; Handle
0x18000ae3d  test    rcx, rcx
0x18000ae40  jz      short loc_18000AE48
0x18000ae42  call    cs:__imp_NtClose
0x18000ae48  mov     eax, ebx
0x18000ae4a  add     rsp, 88h
0x18000ae51  pop     r14
0x18000ae53  pop     rdi
0x18000ae54  pop     rsi
0x18000ae55  pop     rbx
0x18000ae56  retn
```
