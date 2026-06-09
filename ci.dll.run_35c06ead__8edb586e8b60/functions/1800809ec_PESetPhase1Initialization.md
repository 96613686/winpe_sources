# PESetPhase1Initialization

- ea: `0x1800809ec`
- end: `0x180080d61`
- name: `PESetPhase1Initialization`
- size: `885`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18005f3c8`

## callees

- `0x18000ec28`
- `0x1800205ac`
- `0x1800809ec`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x180080c02`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180080c02`
- `ntoskrnl!RtlInitUnicodeString` at `0x180080acd`
- `ntoskrnl!RtlInitUnicodeString` at `0x180080acd`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180080b9b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180080ca5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180080b9b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180080ca5`
- `ntoskrnl!ExAllocatePool2` at `0x180080a5a`
- `ntoskrnl!ExAllocatePool2` at `0x180080b6b`
- `ntoskrnl!ExAllocatePool2` at `0x180080c80`
- `ntoskrnl!ExAllocatePool2` at `0x180080a5a`
- `ntoskrnl!ExAllocatePool2` at `0x180080b6b`
- `ntoskrnl!ExAllocatePool2` at `0x180080c80`
- `ntoskrnl!ExFreePoolWithTag` at `0x180080b3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x180080d19`
- `ntoskrnl!ExFreePoolWithTag` at `0x180080d46`
- `ntoskrnl!ExFreePoolWithTag` at `0x180080b3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x180080d19`
- `ntoskrnl!ExFreePoolWithTag` at `0x180080d46`
- `ntoskrnl!RtlCompareUnicodeString` at `0x180080cf7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x180080cf7`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180080bc7`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180080cd4`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180080bc7`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180080cd4`
- `ntoskrnl!ZwQuerySystemInformation` at `0x180080a2d`
- `ntoskrnl!ZwQuerySystemInformation` at `0x180080a94`
- `ntoskrnl!ZwQuerySystemInformation` at `0x180080a2d`
- `ntoskrnl!ZwQuerySystemInformation` at `0x180080a94`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x180080b0e`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x180080b0e`
- `ntoskrnl!RtlInitAnsiString` at `0x180080af7`
- `ntoskrnl!RtlInitAnsiString` at `0x180080af7`
- `ntoskrnl!wcschr` at `0x180080bb4`
- `ntoskrnl!wcschr` at `0x180080cc1`
- `ntoskrnl!wcschr` at `0x180080bb4`
- `ntoskrnl!wcschr` at `0x180080cc1`

## pseudocode

```c
void __fastcall PESetPhase1Initialization(__int64 **a1)
{
  NTSTATUS v2; // eax
  void *v3; // rax
  _DWORD *v4; // r15
  int v5; // r14d
  struct _UNICODE_STRING *v6; // rdi
  unsigned __int16 v7; // bx
  struct _UNICODE_STRING *Pool2; // rax
  wchar_t *v9; // rax
  struct _UNICODE_STRING **v10; // rax
  __int64 *i; // rbx
  __int64 v12; // rcx
  __int64 v13; // rdi
  wchar_t *v14; // rax
  PVOID j; // rdi
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-28h] BYREF
  struct _STRING SourceString; // [rsp+40h] [rbp-18h] BYREF
  ULONG ReturnLength; // [rsp+98h] [rbp+40h] BYREF

  ReturnLength = 0;
  SourceString = 0;
  UnicodeString = 0;
  DestinationString = 0;
  PEAuthInitStore();
  v2 = ZwQuerySystemInformation(SystemModuleInformation, 0, ReturnLength, &ReturnLength);
  if ( ((int)(v2 + 0x80000000) < 0 || v2 == -1073741820)
    && (v3 = (void *)ExAllocatePool2(258, ReturnLength, 1430340944), (v4 = v3) != 0) )
  {
    if ( ZwQuerySystemInformation(SystemModuleInformation, v3, ReturnLength, &ReturnLength) < 0 )
    {
LABEL_30:
      PEAuthStoreParameter(1, 0);
      g_PEAuthStateVariables = 0;
    }
    else
    {
      v5 = 0;
      v6 = 0;
      qword_180049FB8 = (__int64)&g_PEBootDriverList;
      g_PEBootDriverList = &g_PEBootDriverList;
      RtlInitUnicodeString(&DestinationString, L"\\SystemRoot");
      while ( v5 != *v4 )
      {
        RtlInitAnsiString(&SourceString, (PCSZ)&v4[74 * v5 + 12]);
        if ( RtlAnsiStringToUnicodeString(&UnicodeString, &SourceString, 1u) >= 0 )
        {
          v7 = DestinationString.Length + UnicodeString.Length + 42;
          Pool2 = (struct _UNICODE_STRING *)ExAllocatePool2(258, v7, 1430340944);
          v6 = Pool2;
          if ( !Pool2 )
            break;
          Pool2[1].Buffer = (PWSTR)&Pool2[2].Buffer;
          Pool2[1].MaximumLength = v7 - 40;
          RtlCopyUnicodeString(Pool2 + 1, &DestinationString);
          v9 = wcschr((const wchar_t *)UnicodeString.Buffer + 1, 0x5Cu);
          RtlAppendUnicodeToString(v6 + 1, v9);
          *(_DWORD *)&v6[2].Length = 0;
          v10 = (struct _UNICODE_STRING **)qword_180049FB8;
          if ( *(PVOID **)qword_180049FB8 != &g_PEBootDriverList )
            __fastfail(3u);
          *(_QWORD *)&v6->Length = &g_PEBootDriverList;
          v6->Buffer = (PWSTR)v10;
          *v10 = v6;
          qword_180049FB8 = (__int64)v6;
          RtlFreeUnicodeString(&UnicodeString);
        }
        else
        {
          PEAuthStoreParameter(1, 0);
          g_PEAuthStateVariables = 0;
          if ( v6 )
          {
            ExFreePoolWithTag(v6, 0);
            v6 = 0;
          }
        }
        ++v5;
      }
      if ( a1 && g_PEBootDriverList != &g_PEBootDriverList )
      {
        for ( i = *a1; i != (__int64 *)a1; i = (__int64 *)*i )
        {
          if ( (*((_DWORD *)i + 15) & 0x801) != 0 )
          {
            v12 = i[6];
            if ( v12 )
            {
              v13 = (unsigned __int16)(*(_WORD *)(v12 + 74) + DestinationString.Length + 2);
              UnicodeString.Buffer = (PWSTR)ExAllocatePool2(258, v13, 1430340944);
              if ( !UnicodeString.Buffer )
                goto LABEL_30;
              UnicodeString.MaximumLength = v13;
              RtlCopyUnicodeString(&UnicodeString, &DestinationString);
              v14 = wcschr((const wchar_t *)(*(_QWORD *)(i[6] + 80) + 2LL), 0x5Cu);
              RtlAppendUnicodeToString(&UnicodeString, v14);
              for ( j = g_PEBootDriverList; j; j = *(PVOID *)j )
              {
                if ( !RtlCompareUnicodeString((PCUNICODE_STRING)j + 1, &UnicodeString, 1u) )
                {
                  *((_DWORD *)j + 8) = -1073740760;
                  break;
                }
              }
              ExFreePoolWithTag(UnicodeString.Buffer, 0);
            }
          }
        }
      }
    }
    ExFreePoolWithTag(v4, 0);
  }
  else
  {
    PEAuthStoreParameter(1, 0);
    g_PEAuthStateVariables = 0;
  }
}

```

## disassembly

```asm
0x1800809ec  push    rbp
0x1800809ee  push    rbx
0x1800809ef  push    rdi
0x1800809f0  push    r12
0x1800809f2  push    r14
0x1800809f4  push    r15
0x1800809f6  mov     rbp, rsp
0x1800809f9  sub     rsp, 58h
0x1800809fd  xorps   xmm0, xmm0
0x180080a00  mov     [rbp+ReturnLength], 0
0x180080a07  xorps   xmm1, xmm1
0x180080a0a  mov     r12, rcx
0x180080a0d  movups  xmmword ptr [rbp+SourceString.Length], xmm0
0x180080a11  movups  xmmword ptr [rbp+UnicodeString.Length], xmm1
0x180080a15  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180080a19  call    PEAuthInitStore
0x180080a1e  mov     r8d, [rbp+ReturnLength]; SystemInformationLength
0x180080a22  lea     r9, [rbp+ReturnLength]; ReturnLength
0x180080a26  xor     edx, edx; SystemInformation
0x180080a28  lea     ebx, [rdx+0Bh]
0x180080a2b  mov     ecx, ebx; SystemInformationClass
0x180080a2d  call    cs:__imp_ZwQuerySystemInformation
0x180080a34  nop     dword ptr [rax+rax+00h]
0x180080a39  mov     edx, 80000000h
0x180080a3e  lea     ecx, [rax+rdx]
0x180080a41  test    edx, ecx
0x180080a43  jnz     short loc_180080A4C
0x180080a45  cmp     eax, 0C0000004h
0x180080a4a  jnz     short loc_180080A6E
0x180080a4c  mov     edx, [rbp+ReturnLength]
0x180080a4f  mov     ecx, 102h
0x180080a54  mov     r8d, 55414550h
0x180080a5a  call    cs:__imp_ExAllocatePool2
0x180080a61  nop     dword ptr [rax+rax+00h]
0x180080a66  mov     r15, rax
0x180080a69  test    rax, rax
0x180080a6c  jnz     short loc_180080A87
0x180080a6e  xor     edx, edx
0x180080a70  lea     ecx, [rdx+1]
0x180080a73  call    PEAuthStoreParameter
0x180080a78  mov     cs:g_PEAuthStateVariables, 0
0x180080a82  jmp     loc_180080D52
0x180080a87  mov     r8d, [rbp+ReturnLength]; SystemInformationLength
0x180080a8b  lea     r9, [rbp+ReturnLength]; ReturnLength
0x180080a8f  mov     rdx, r15; SystemInformation
0x180080a92  mov     ecx, ebx; SystemInformationClass
0x180080a94  call    cs:__imp_ZwQuerySystemInformation
0x180080a9b  nop     dword ptr [rax+rax+00h]
0x180080aa0  test    eax, eax
0x180080aa2  js      loc_180080D2D
0x180080aa8  lea     rbx, g_PEBootDriverList
0x180080aaf  xor     r14d, r14d
0x180080ab2  xor     edi, edi
0x180080ab4  mov     cs:qword_180049FB8, rbx
0x180080abb  lea     rdx, aSystemroot; "\\SystemRoot"
0x180080ac2  mov     cs:g_PEBootDriverList, rbx
0x180080ac9  lea     rcx, [rbp+DestinationString]; DestinationString
0x180080acd  call    cs:__imp_RtlInitUnicodeString
0x180080ad4  nop     dword ptr [rax+rax+00h]
0x180080ad9  cmp     r14d, [r15]
0x180080adc  jz      loc_180080C21
0x180080ae2  mov     eax, r14d
0x180080ae5  lea     rcx, [rbp+SourceString]; DestinationString
0x180080ae9  imul    rdx, rax, 128h
0x180080af0  add     rdx, 30h ; '0'
0x180080af4  add     rdx, r15; SourceString
0x180080af7  call    cs:__imp_RtlInitAnsiString
0x180080afe  nop     dword ptr [rax+rax+00h]
0x180080b03  mov     r8b, 1; AllocateDestinationString
0x180080b06  lea     rdx, [rbp+SourceString]; SourceString
0x180080b0a  lea     rcx, [rbp+UnicodeString]; DestinationString
0x180080b0e  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180080b15  nop     dword ptr [rax+rax+00h]
0x180080b1a  test    eax, eax
0x180080b1c  jns     short loc_180080B4F
0x180080b1e  xor     edx, edx
0x180080b20  lea     ecx, [rdx+1]
0x180080b23  call    PEAuthStoreParameter
0x180080b28  mov     cs:g_PEAuthStateVariables, 0
0x180080b32  test    rdi, rdi
0x180080b35  jz      short loc_180080B4A
0x180080b37  xor     edx, edx; Tag
0x180080b39  mov     rcx, rdi; P
0x180080b3c  call    cs:__imp_ExFreePoolWithTag
0x180080b43  nop     dword ptr [rax+rax+00h]
0x180080b48  xor     edi, edi
0x180080b4a  inc     r14d
0x180080b4d  jmp     short loc_180080AD9
0x180080b4f  movzx   eax, [rbp+UnicodeString.Length]
0x180080b53  mov     ecx, 102h
0x180080b58  add     ax, 2Ah ; '*'
0x180080b5c  mov     r8d, 55414550h
0x180080b62  add     ax, [rbp+DestinationString.Length]
0x180080b66  movzx   ebx, ax
0x180080b69  mov     edx, ebx
0x180080b6b  call    cs:__imp_ExAllocatePool2
0x180080b72  nop     dword ptr [rax+rax+00h]
0x180080b77  mov     rdi, rax
0x180080b7a  test    rax, rax
0x180080b7d  jz      loc_180080C1A
0x180080b83  add     rax, 28h ; '('
0x180080b87  lea     rdx, [rbp+DestinationString]; SourceString
0x180080b8b  sub     bx, 28h ; '('
0x180080b8f  mov     [rdi+18h], rax
0x180080b93  lea     rcx, [rdi+10h]; DestinationString
0x180080b97  mov     [rdi+12h], bx
0x180080b9b  call    cs:__imp_RtlCopyUnicodeString
0x180080ba2  nop     dword ptr [rax+rax+00h]
0x180080ba7  mov     rcx, [rbp+UnicodeString.Buffer]
0x180080bab  mov     edx, 5Ch ; '\'; Ch
0x180080bb0  add     rcx, 2; Str
0x180080bb4  call    cs:__imp_wcschr
0x180080bbb  nop     dword ptr [rax+rax+00h]
0x180080bc0  mov     rdx, rax; Source
0x180080bc3  lea     rcx, [rdi+10h]; Destination
0x180080bc7  call    cs:__imp_RtlAppendUnicodeToString
0x180080bce  nop     dword ptr [rax+rax+00h]
0x180080bd3  mov     dword ptr [rdi+20h], 0
0x180080bda  lea     rbx, g_PEBootDriverList
0x180080be1  mov     rax, cs:qword_180049FB8
0x180080be8  cmp     [rax], rbx
0x180080beb  jnz     short loc_180080C13
0x180080bed  mov     [rdi], rbx
0x180080bf0  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180080bf4  mov     [rdi+8], rax
0x180080bf8  mov     [rax], rdi
0x180080bfb  mov     cs:qword_180049FB8, rdi
0x180080c02  call    cs:__imp_RtlFreeUnicodeString
0x180080c09  nop     dword ptr [rax+rax+00h]
0x180080c0e  jmp     loc_180080B4A
0x180080c13  mov     ecx, 3
0x180080c18  int     29h; Win8: RtlFailFast(ecx)
0x180080c1a  lea     rbx, g_PEBootDriverList
0x180080c21  test    r12, r12
0x180080c24  jz      loc_180080D41
0x180080c2a  cmp     cs:g_PEBootDriverList, rbx
0x180080c31  jz      loc_180080D41
0x180080c37  mov     rbx, [r12]
0x180080c3b  mov     r14d, 2
0x180080c41  cmp     rbx, r12
0x180080c44  jz      loc_180080D41
0x180080c4a  test    dword ptr [rbx+3Ch], 801h
0x180080c51  jz      loc_180080D25
0x180080c57  mov     rcx, [rbx+30h]
0x180080c5b  test    rcx, rcx
0x180080c5e  jz      loc_180080D25
0x180080c64  movzx   eax, [rbp+DestinationString.Length]
0x180080c68  mov     r8d, 55414550h
0x180080c6e  add     ax, [rcx+4Ah]
0x180080c72  mov     ecx, 102h
0x180080c77  add     ax, r14w
0x180080c7b  movzx   edi, ax
0x180080c7e  mov     edx, edi
0x180080c80  call    cs:__imp_ExAllocatePool2
0x180080c87  nop     dword ptr [rax+rax+00h]
0x180080c8c  mov     [rbp+UnicodeString.Buffer], rax
0x180080c90  test    rax, rax
0x180080c93  jz      loc_180080D2D
0x180080c99  lea     rdx, [rbp+DestinationString]; SourceString
0x180080c9d  mov     [rbp+UnicodeString.MaximumLength], di
0x180080ca1  lea     rcx, [rbp+UnicodeString]; DestinationString
0x180080ca5  call    cs:__imp_RtlCopyUnicodeString
0x180080cac  nop     dword ptr [rax+rax+00h]
0x180080cb1  mov     rax, [rbx+30h]
0x180080cb5  mov     edx, 5Ch ; '\'; Ch
0x180080cba  mov     rcx, [rax+50h]
0x180080cbe  add     rcx, r14; Str
0x180080cc1  call    cs:__imp_wcschr
0x180080cc8  nop     dword ptr [rax+rax+00h]
0x180080ccd  mov     rdx, rax; Source
0x180080cd0  lea     rcx, [rbp+UnicodeString]; Destination
0x180080cd4  call    cs:__imp_RtlAppendUnicodeToString
0x180080cdb  nop     dword ptr [rax+rax+00h]
0x180080ce0  mov     rdi, cs:g_PEBootDriverList
0x180080ce7  test    rdi, rdi
0x180080cea  jz      short loc_180080D13
0x180080cec  lea     rcx, [rdi+10h]; String1
0x180080cf0  mov     r8b, 1; CaseInSensitive
0x180080cf3  lea     rdx, [rbp+UnicodeString]; String2
0x180080cf7  call    cs:__imp_RtlCompareUnicodeString
0x180080cfe  nop     dword ptr [rax+rax+00h]
0x180080d03  test    eax, eax
0x180080d05  jz      short loc_180080D0C
0x180080d07  mov     rdi, [rdi]
0x180080d0a  jmp     short loc_180080CE7
0x180080d0c  mov     dword ptr [rdi+20h], 0C0000428h
0x180080d13  mov     rcx, [rbp+UnicodeString.Buffer]; P
0x180080d17  xor     edx, edx; Tag
0x180080d19  call    cs:__imp_ExFreePoolWithTag
0x180080d20  nop     dword ptr [rax+rax+00h]
0x180080d25  mov     rbx, [rbx]
0x180080d28  jmp     loc_180080C41
0x180080d2d  xor     edx, edx
0x180080d2f  lea     ecx, [rdx+1]
0x180080d32  call    PEAuthStoreParameter
0x180080d37  mov     cs:g_PEAuthStateVariables, 0
0x180080d41  xor     edx, edx; Tag
0x180080d43  mov     rcx, r15; P
0x180080d46  call    cs:__imp_ExFreePoolWithTag
0x180080d4d  nop     dword ptr [rax+rax+00h]
0x180080d52  add     rsp, 58h
0x180080d56  pop     r15
0x180080d58  pop     r14
0x180080d5a  pop     r12
0x180080d5c  pop     rdi
0x180080d5d  pop     rbx
0x180080d5e  pop     rbp
0x180080d5f  retn
```
