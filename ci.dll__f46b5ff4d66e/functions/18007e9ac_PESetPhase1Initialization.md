# PESetPhase1Initialization

- ea: `0x18007e9ac`
- end: `0x18007ed21`
- name: `PESetPhase1Initialization`
- size: `885`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18005ecdc`

## callees

- `0x18000ec18`
- `0x18002056c`
- `0x18007e9ac`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18007ebc2`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007ebc2`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007ea8d`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007ea8d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18007eb5b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18007ec65`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18007eb5b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18007ec65`
- `ntoskrnl!ExAllocatePool2` at `0x18007ea1a`
- `ntoskrnl!ExAllocatePool2` at `0x18007eb2b`
- `ntoskrnl!ExAllocatePool2` at `0x18007ec40`
- `ntoskrnl!ExAllocatePool2` at `0x18007ea1a`
- `ntoskrnl!ExAllocatePool2` at `0x18007eb2b`
- `ntoskrnl!ExAllocatePool2` at `0x18007ec40`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007eafc`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007ecd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007ed06`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007eafc`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007ecd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007ed06`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18007ecb7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18007ecb7`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18007eb87`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18007ec94`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18007eb87`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18007ec94`
- `ntoskrnl!ZwQuerySystemInformation` at `0x18007e9ed`
- `ntoskrnl!ZwQuerySystemInformation` at `0x18007ea54`
- `ntoskrnl!ZwQuerySystemInformation` at `0x18007e9ed`
- `ntoskrnl!ZwQuerySystemInformation` at `0x18007ea54`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x18007eace`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x18007eace`
- `ntoskrnl!RtlInitAnsiString` at `0x18007eab7`
- `ntoskrnl!RtlInitAnsiString` at `0x18007eab7`
- `ntoskrnl!wcschr` at `0x18007eb74`
- `ntoskrnl!wcschr` at `0x18007ec81`
- `ntoskrnl!wcschr` at `0x18007eb74`
- `ntoskrnl!wcschr` at `0x18007ec81`

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
      qword_180048FB8 = (__int64)&g_PEBootDriverList;
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
          v10 = (struct _UNICODE_STRING **)qword_180048FB8;
          if ( *(PVOID **)qword_180048FB8 != &g_PEBootDriverList )
            __fastfail(3u);
          *(_QWORD *)&v6->Length = &g_PEBootDriverList;
          v6->Buffer = (PWSTR)v10;
          *v10 = v6;
          qword_180048FB8 = (__int64)v6;
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
0x18007e9ac  push    rbp
0x18007e9ae  push    rbx
0x18007e9af  push    rdi
0x18007e9b0  push    r12
0x18007e9b2  push    r14
0x18007e9b4  push    r15
0x18007e9b6  mov     rbp, rsp
0x18007e9b9  sub     rsp, 58h
0x18007e9bd  xorps   xmm0, xmm0
0x18007e9c0  mov     [rbp+ReturnLength], 0
0x18007e9c7  xorps   xmm1, xmm1
0x18007e9ca  mov     r12, rcx
0x18007e9cd  movups  xmmword ptr [rbp+SourceString.Length], xmm0
0x18007e9d1  movups  xmmword ptr [rbp+UnicodeString.Length], xmm1
0x18007e9d5  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18007e9d9  call    PEAuthInitStore
0x18007e9de  mov     r8d, [rbp+ReturnLength]; SystemInformationLength
0x18007e9e2  lea     r9, [rbp+ReturnLength]; ReturnLength
0x18007e9e6  xor     edx, edx; SystemInformation
0x18007e9e8  lea     ebx, [rdx+0Bh]
0x18007e9eb  mov     ecx, ebx; SystemInformationClass
0x18007e9ed  call    cs:__imp_ZwQuerySystemInformation
0x18007e9f4  nop     dword ptr [rax+rax+00h]
0x18007e9f9  mov     edx, 80000000h
0x18007e9fe  lea     ecx, [rax+rdx]
0x18007ea01  test    edx, ecx
0x18007ea03  jnz     short loc_18007EA0C
0x18007ea05  cmp     eax, 0C0000004h
0x18007ea0a  jnz     short loc_18007EA2E
0x18007ea0c  mov     edx, [rbp+ReturnLength]
0x18007ea0f  mov     ecx, 102h
0x18007ea14  mov     r8d, 55414550h
0x18007ea1a  call    cs:__imp_ExAllocatePool2
0x18007ea21  nop     dword ptr [rax+rax+00h]
0x18007ea26  mov     r15, rax
0x18007ea29  test    rax, rax
0x18007ea2c  jnz     short loc_18007EA47
0x18007ea2e  xor     edx, edx
0x18007ea30  lea     ecx, [rdx+1]
0x18007ea33  call    PEAuthStoreParameter
0x18007ea38  mov     cs:g_PEAuthStateVariables, 0
0x18007ea42  jmp     loc_18007ED12
0x18007ea47  mov     r8d, [rbp+ReturnLength]; SystemInformationLength
0x18007ea4b  lea     r9, [rbp+ReturnLength]; ReturnLength
0x18007ea4f  mov     rdx, r15; SystemInformation
0x18007ea52  mov     ecx, ebx; SystemInformationClass
0x18007ea54  call    cs:__imp_ZwQuerySystemInformation
0x18007ea5b  nop     dword ptr [rax+rax+00h]
0x18007ea60  test    eax, eax
0x18007ea62  js      loc_18007ECED
0x18007ea68  lea     rbx, g_PEBootDriverList
0x18007ea6f  xor     r14d, r14d
0x18007ea72  xor     edi, edi
0x18007ea74  mov     cs:qword_180048FB8, rbx
0x18007ea7b  lea     rdx, aSystemroot; "\\SystemRoot"
0x18007ea82  mov     cs:g_PEBootDriverList, rbx
0x18007ea89  lea     rcx, [rbp+DestinationString]; DestinationString
0x18007ea8d  call    cs:__imp_RtlInitUnicodeString
0x18007ea94  nop     dword ptr [rax+rax+00h]
0x18007ea99  cmp     r14d, [r15]
0x18007ea9c  jz      loc_18007EBE1
0x18007eaa2  mov     eax, r14d
0x18007eaa5  lea     rcx, [rbp+SourceString]; DestinationString
0x18007eaa9  imul    rdx, rax, 128h
0x18007eab0  add     rdx, 30h ; '0'
0x18007eab4  add     rdx, r15; SourceString
0x18007eab7  call    cs:__imp_RtlInitAnsiString
0x18007eabe  nop     dword ptr [rax+rax+00h]
0x18007eac3  mov     r8b, 1; AllocateDestinationString
0x18007eac6  lea     rdx, [rbp+SourceString]; SourceString
0x18007eaca  lea     rcx, [rbp+UnicodeString]; DestinationString
0x18007eace  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18007ead5  nop     dword ptr [rax+rax+00h]
0x18007eada  test    eax, eax
0x18007eadc  jns     short loc_18007EB0F
0x18007eade  xor     edx, edx
0x18007eae0  lea     ecx, [rdx+1]
0x18007eae3  call    PEAuthStoreParameter
0x18007eae8  mov     cs:g_PEAuthStateVariables, 0
0x18007eaf2  test    rdi, rdi
0x18007eaf5  jz      short loc_18007EB0A
0x18007eaf7  xor     edx, edx; Tag
0x18007eaf9  mov     rcx, rdi; P
0x18007eafc  call    cs:__imp_ExFreePoolWithTag
0x18007eb03  nop     dword ptr [rax+rax+00h]
0x18007eb08  xor     edi, edi
0x18007eb0a  inc     r14d
0x18007eb0d  jmp     short loc_18007EA99
0x18007eb0f  movzx   eax, [rbp+UnicodeString.Length]
0x18007eb13  mov     ecx, 102h
0x18007eb18  add     ax, 2Ah ; '*'
0x18007eb1c  mov     r8d, 55414550h
0x18007eb22  add     ax, [rbp+DestinationString.Length]
0x18007eb26  movzx   ebx, ax
0x18007eb29  mov     edx, ebx
0x18007eb2b  call    cs:__imp_ExAllocatePool2
0x18007eb32  nop     dword ptr [rax+rax+00h]
0x18007eb37  mov     rdi, rax
0x18007eb3a  test    rax, rax
0x18007eb3d  jz      loc_18007EBDA
0x18007eb43  add     rax, 28h ; '('
0x18007eb47  lea     rdx, [rbp+DestinationString]; SourceString
0x18007eb4b  sub     bx, 28h ; '('
0x18007eb4f  mov     [rdi+18h], rax
0x18007eb53  lea     rcx, [rdi+10h]; DestinationString
0x18007eb57  mov     [rdi+12h], bx
0x18007eb5b  call    cs:__imp_RtlCopyUnicodeString
0x18007eb62  nop     dword ptr [rax+rax+00h]
0x18007eb67  mov     rcx, [rbp+UnicodeString.Buffer]
0x18007eb6b  mov     edx, 5Ch ; '\'; Ch
0x18007eb70  add     rcx, 2; Str
0x18007eb74  call    cs:__imp_wcschr
0x18007eb7b  nop     dword ptr [rax+rax+00h]
0x18007eb80  mov     rdx, rax; Source
0x18007eb83  lea     rcx, [rdi+10h]; Destination
0x18007eb87  call    cs:__imp_RtlAppendUnicodeToString
0x18007eb8e  nop     dword ptr [rax+rax+00h]
0x18007eb93  mov     dword ptr [rdi+20h], 0
0x18007eb9a  lea     rbx, g_PEBootDriverList
0x18007eba1  mov     rax, cs:qword_180048FB8
0x18007eba8  cmp     [rax], rbx
0x18007ebab  jnz     short loc_18007EBD3
0x18007ebad  mov     [rdi], rbx
0x18007ebb0  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18007ebb4  mov     [rdi+8], rax
0x18007ebb8  mov     [rax], rdi
0x18007ebbb  mov     cs:qword_180048FB8, rdi
0x18007ebc2  call    cs:__imp_RtlFreeUnicodeString
0x18007ebc9  nop     dword ptr [rax+rax+00h]
0x18007ebce  jmp     loc_18007EB0A
0x18007ebd3  mov     ecx, 3
0x18007ebd8  int     29h; Win8: RtlFailFast(ecx)
0x18007ebda  lea     rbx, g_PEBootDriverList
0x18007ebe1  test    r12, r12
0x18007ebe4  jz      loc_18007ED01
0x18007ebea  cmp     cs:g_PEBootDriverList, rbx
0x18007ebf1  jz      loc_18007ED01
0x18007ebf7  mov     rbx, [r12]
0x18007ebfb  mov     r14d, 2
0x18007ec01  cmp     rbx, r12
0x18007ec04  jz      loc_18007ED01
0x18007ec0a  test    dword ptr [rbx+3Ch], 801h
0x18007ec11  jz      loc_18007ECE5
0x18007ec17  mov     rcx, [rbx+30h]
0x18007ec1b  test    rcx, rcx
0x18007ec1e  jz      loc_18007ECE5
0x18007ec24  movzx   eax, [rbp+DestinationString.Length]
0x18007ec28  mov     r8d, 55414550h
0x18007ec2e  add     ax, [rcx+4Ah]
0x18007ec32  mov     ecx, 102h
0x18007ec37  add     ax, r14w
0x18007ec3b  movzx   edi, ax
0x18007ec3e  mov     edx, edi
0x18007ec40  call    cs:__imp_ExAllocatePool2
0x18007ec47  nop     dword ptr [rax+rax+00h]
0x18007ec4c  mov     [rbp+UnicodeString.Buffer], rax
0x18007ec50  test    rax, rax
0x18007ec53  jz      loc_18007ECED
0x18007ec59  lea     rdx, [rbp+DestinationString]; SourceString
0x18007ec5d  mov     [rbp+UnicodeString.MaximumLength], di
0x18007ec61  lea     rcx, [rbp+UnicodeString]; DestinationString
0x18007ec65  call    cs:__imp_RtlCopyUnicodeString
0x18007ec6c  nop     dword ptr [rax+rax+00h]
0x18007ec71  mov     rax, [rbx+30h]
0x18007ec75  mov     edx, 5Ch ; '\'; Ch
0x18007ec7a  mov     rcx, [rax+50h]
0x18007ec7e  add     rcx, r14; Str
0x18007ec81  call    cs:__imp_wcschr
0x18007ec88  nop     dword ptr [rax+rax+00h]
0x18007ec8d  mov     rdx, rax; Source
0x18007ec90  lea     rcx, [rbp+UnicodeString]; Destination
0x18007ec94  call    cs:__imp_RtlAppendUnicodeToString
0x18007ec9b  nop     dword ptr [rax+rax+00h]
0x18007eca0  mov     rdi, cs:g_PEBootDriverList
0x18007eca7  test    rdi, rdi
0x18007ecaa  jz      short loc_18007ECD3
0x18007ecac  lea     rcx, [rdi+10h]; String1
0x18007ecb0  mov     r8b, 1; CaseInSensitive
0x18007ecb3  lea     rdx, [rbp+UnicodeString]; String2
0x18007ecb7  call    cs:__imp_RtlCompareUnicodeString
0x18007ecbe  nop     dword ptr [rax+rax+00h]
0x18007ecc3  test    eax, eax
0x18007ecc5  jz      short loc_18007ECCC
0x18007ecc7  mov     rdi, [rdi]
0x18007ecca  jmp     short loc_18007ECA7
0x18007eccc  mov     dword ptr [rdi+20h], 0C0000428h
0x18007ecd3  mov     rcx, [rbp+UnicodeString.Buffer]; P
0x18007ecd7  xor     edx, edx; Tag
0x18007ecd9  call    cs:__imp_ExFreePoolWithTag
0x18007ece0  nop     dword ptr [rax+rax+00h]
0x18007ece5  mov     rbx, [rbx]
0x18007ece8  jmp     loc_18007EC01
0x18007eced  xor     edx, edx
0x18007ecef  lea     ecx, [rdx+1]
0x18007ecf2  call    PEAuthStoreParameter
0x18007ecf7  mov     cs:g_PEAuthStateVariables, 0
0x18007ed01  xor     edx, edx; Tag
0x18007ed03  mov     rcx, r15; P
0x18007ed06  call    cs:__imp_ExFreePoolWithTag
0x18007ed0d  nop     dword ptr [rax+rax+00h]
0x18007ed12  add     rsp, 58h
0x18007ed16  pop     r15
0x18007ed18  pop     r14
0x18007ed1a  pop     r12
0x18007ed1c  pop     rdi
0x18007ed1d  pop     rbx
0x18007ed1e  pop     rbp
0x18007ed1f  retn
```
