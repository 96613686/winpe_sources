# PESetPhase1Initialization

- ea: `0x18007ffd8`
- end: `0x18008034d`
- name: `PESetPhase1Initialization`
- size: `885`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18005f428`

## callees

- `0x18000ec18`
- `0x1800204dc`
- `0x18007ffd8`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800801ee`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800801ee`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800800b9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800800b9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180080187`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180080291`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180080187`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180080291`
- `ntoskrnl!ExAllocatePool2` at `0x180080046`
- `ntoskrnl!ExAllocatePool2` at `0x180080157`
- `ntoskrnl!ExAllocatePool2` at `0x18008026c`
- `ntoskrnl!ExAllocatePool2` at `0x180080046`
- `ntoskrnl!ExAllocatePool2` at `0x180080157`
- `ntoskrnl!ExAllocatePool2` at `0x18008026c`
- `ntoskrnl!ExFreePoolWithTag` at `0x180080128`
- `ntoskrnl!ExFreePoolWithTag` at `0x180080305`
- `ntoskrnl!ExFreePoolWithTag` at `0x180080332`
- `ntoskrnl!ExFreePoolWithTag` at `0x180080128`
- `ntoskrnl!ExFreePoolWithTag` at `0x180080305`
- `ntoskrnl!ExFreePoolWithTag` at `0x180080332`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800802e3`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800802e3`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800801b3`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800802c0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800801b3`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800802c0`
- `ntoskrnl!ZwQuerySystemInformation` at `0x180080019`
- `ntoskrnl!ZwQuerySystemInformation` at `0x180080080`
- `ntoskrnl!ZwQuerySystemInformation` at `0x180080019`
- `ntoskrnl!ZwQuerySystemInformation` at `0x180080080`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1800800fa`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1800800fa`
- `ntoskrnl!RtlInitAnsiString` at `0x1800800e3`
- `ntoskrnl!RtlInitAnsiString` at `0x1800800e3`
- `ntoskrnl!wcschr` at `0x1800801a0`
- `ntoskrnl!wcschr` at `0x1800802ad`
- `ntoskrnl!wcschr` at `0x1800801a0`
- `ntoskrnl!wcschr` at `0x1800802ad`

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
      qword_180049F98 = (__int64)&g_PEBootDriverList;
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
          v10 = (struct _UNICODE_STRING **)qword_180049F98;
          if ( *(PVOID **)qword_180049F98 != &g_PEBootDriverList )
            __fastfail(3u);
          *(_QWORD *)&v6->Length = &g_PEBootDriverList;
          v6->Buffer = (PWSTR)v10;
          *v10 = v6;
          qword_180049F98 = (__int64)v6;
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
0x18007ffd8  push    rbp
0x18007ffda  push    rbx
0x18007ffdb  push    rdi
0x18007ffdc  push    r12
0x18007ffde  push    r14
0x18007ffe0  push    r15
0x18007ffe2  mov     rbp, rsp
0x18007ffe5  sub     rsp, 58h
0x18007ffe9  xorps   xmm0, xmm0
0x18007ffec  mov     [rbp+ReturnLength], 0
0x18007fff3  xorps   xmm1, xmm1
0x18007fff6  mov     r12, rcx
0x18007fff9  movups  xmmword ptr [rbp+SourceString.Length], xmm0
0x18007fffd  movups  xmmword ptr [rbp+UnicodeString.Length], xmm1
0x180080001  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180080005  call    PEAuthInitStore
0x18008000a  mov     r8d, [rbp+ReturnLength]; SystemInformationLength
0x18008000e  lea     r9, [rbp+ReturnLength]; ReturnLength
0x180080012  xor     edx, edx; SystemInformation
0x180080014  lea     ebx, [rdx+0Bh]
0x180080017  mov     ecx, ebx; SystemInformationClass
0x180080019  call    cs:__imp_ZwQuerySystemInformation
0x180080020  nop     dword ptr [rax+rax+00h]
0x180080025  mov     edx, 80000000h
0x18008002a  lea     ecx, [rax+rdx]
0x18008002d  test    edx, ecx
0x18008002f  jnz     short loc_180080038
0x180080031  cmp     eax, 0C0000004h
0x180080036  jnz     short loc_18008005A
0x180080038  mov     edx, [rbp+ReturnLength]
0x18008003b  mov     ecx, 102h
0x180080040  mov     r8d, 55414550h
0x180080046  call    cs:__imp_ExAllocatePool2
0x18008004d  nop     dword ptr [rax+rax+00h]
0x180080052  mov     r15, rax
0x180080055  test    rax, rax
0x180080058  jnz     short loc_180080073
0x18008005a  xor     edx, edx
0x18008005c  lea     ecx, [rdx+1]
0x18008005f  call    PEAuthStoreParameter
0x180080064  mov     cs:g_PEAuthStateVariables, 0
0x18008006e  jmp     loc_18008033E
0x180080073  mov     r8d, [rbp+ReturnLength]; SystemInformationLength
0x180080077  lea     r9, [rbp+ReturnLength]; ReturnLength
0x18008007b  mov     rdx, r15; SystemInformation
0x18008007e  mov     ecx, ebx; SystemInformationClass
0x180080080  call    cs:__imp_ZwQuerySystemInformation
0x180080087  nop     dword ptr [rax+rax+00h]
0x18008008c  test    eax, eax
0x18008008e  js      loc_180080319
0x180080094  lea     rbx, g_PEBootDriverList
0x18008009b  xor     r14d, r14d
0x18008009e  xor     edi, edi
0x1800800a0  mov     cs:qword_180049F98, rbx
0x1800800a7  lea     rdx, aSystemroot; "\\SystemRoot"
0x1800800ae  mov     cs:g_PEBootDriverList, rbx
0x1800800b5  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800800b9  call    cs:__imp_RtlInitUnicodeString
0x1800800c0  nop     dword ptr [rax+rax+00h]
0x1800800c5  cmp     r14d, [r15]
0x1800800c8  jz      loc_18008020D
0x1800800ce  mov     eax, r14d
0x1800800d1  lea     rcx, [rbp+SourceString]; DestinationString
0x1800800d5  imul    rdx, rax, 128h
0x1800800dc  add     rdx, 30h ; '0'
0x1800800e0  add     rdx, r15; SourceString
0x1800800e3  call    cs:__imp_RtlInitAnsiString
0x1800800ea  nop     dword ptr [rax+rax+00h]
0x1800800ef  mov     r8b, 1; AllocateDestinationString
0x1800800f2  lea     rdx, [rbp+SourceString]; SourceString
0x1800800f6  lea     rcx, [rbp+UnicodeString]; DestinationString
0x1800800fa  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180080101  nop     dword ptr [rax+rax+00h]
0x180080106  test    eax, eax
0x180080108  jns     short loc_18008013B
0x18008010a  xor     edx, edx
0x18008010c  lea     ecx, [rdx+1]
0x18008010f  call    PEAuthStoreParameter
0x180080114  mov     cs:g_PEAuthStateVariables, 0
0x18008011e  test    rdi, rdi
0x180080121  jz      short loc_180080136
0x180080123  xor     edx, edx; Tag
0x180080125  mov     rcx, rdi; P
0x180080128  call    cs:__imp_ExFreePoolWithTag
0x18008012f  nop     dword ptr [rax+rax+00h]
0x180080134  xor     edi, edi
0x180080136  inc     r14d
0x180080139  jmp     short loc_1800800C5
0x18008013b  movzx   eax, [rbp+UnicodeString.Length]
0x18008013f  mov     ecx, 102h
0x180080144  add     ax, 2Ah ; '*'
0x180080148  mov     r8d, 55414550h
0x18008014e  add     ax, [rbp+DestinationString.Length]
0x180080152  movzx   ebx, ax
0x180080155  mov     edx, ebx
0x180080157  call    cs:__imp_ExAllocatePool2
0x18008015e  nop     dword ptr [rax+rax+00h]
0x180080163  mov     rdi, rax
0x180080166  test    rax, rax
0x180080169  jz      loc_180080206
0x18008016f  add     rax, 28h ; '('
0x180080173  lea     rdx, [rbp+DestinationString]; SourceString
0x180080177  sub     bx, 28h ; '('
0x18008017b  mov     [rdi+18h], rax
0x18008017f  lea     rcx, [rdi+10h]; DestinationString
0x180080183  mov     [rdi+12h], bx
0x180080187  call    cs:__imp_RtlCopyUnicodeString
0x18008018e  nop     dword ptr [rax+rax+00h]
0x180080193  mov     rcx, [rbp+UnicodeString.Buffer]
0x180080197  mov     edx, 5Ch ; '\'; Ch
0x18008019c  add     rcx, 2; Str
0x1800801a0  call    cs:__imp_wcschr
0x1800801a7  nop     dword ptr [rax+rax+00h]
0x1800801ac  mov     rdx, rax; Source
0x1800801af  lea     rcx, [rdi+10h]; Destination
0x1800801b3  call    cs:__imp_RtlAppendUnicodeToString
0x1800801ba  nop     dword ptr [rax+rax+00h]
0x1800801bf  mov     dword ptr [rdi+20h], 0
0x1800801c6  lea     rbx, g_PEBootDriverList
0x1800801cd  mov     rax, cs:qword_180049F98
0x1800801d4  cmp     [rax], rbx
0x1800801d7  jnz     short loc_1800801FF
0x1800801d9  mov     [rdi], rbx
0x1800801dc  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x1800801e0  mov     [rdi+8], rax
0x1800801e4  mov     [rax], rdi
0x1800801e7  mov     cs:qword_180049F98, rdi
0x1800801ee  call    cs:__imp_RtlFreeUnicodeString
0x1800801f5  nop     dword ptr [rax+rax+00h]
0x1800801fa  jmp     loc_180080136
0x1800801ff  mov     ecx, 3
0x180080204  int     29h; Win8: RtlFailFast(ecx)
0x180080206  lea     rbx, g_PEBootDriverList
0x18008020d  test    r12, r12
0x180080210  jz      loc_18008032D
0x180080216  cmp     cs:g_PEBootDriverList, rbx
0x18008021d  jz      loc_18008032D
0x180080223  mov     rbx, [r12]
0x180080227  mov     r14d, 2
0x18008022d  cmp     rbx, r12
0x180080230  jz      loc_18008032D
0x180080236  test    dword ptr [rbx+3Ch], 801h
0x18008023d  jz      loc_180080311
0x180080243  mov     rcx, [rbx+30h]
0x180080247  test    rcx, rcx
0x18008024a  jz      loc_180080311
0x180080250  movzx   eax, [rbp+DestinationString.Length]
0x180080254  mov     r8d, 55414550h
0x18008025a  add     ax, [rcx+4Ah]
0x18008025e  mov     ecx, 102h
0x180080263  add     ax, r14w
0x180080267  movzx   edi, ax
0x18008026a  mov     edx, edi
0x18008026c  call    cs:__imp_ExAllocatePool2
0x180080273  nop     dword ptr [rax+rax+00h]
0x180080278  mov     [rbp+UnicodeString.Buffer], rax
0x18008027c  test    rax, rax
0x18008027f  jz      loc_180080319
0x180080285  lea     rdx, [rbp+DestinationString]; SourceString
0x180080289  mov     [rbp+UnicodeString.MaximumLength], di
0x18008028d  lea     rcx, [rbp+UnicodeString]; DestinationString
0x180080291  call    cs:__imp_RtlCopyUnicodeString
0x180080298  nop     dword ptr [rax+rax+00h]
0x18008029d  mov     rax, [rbx+30h]
0x1800802a1  mov     edx, 5Ch ; '\'; Ch
0x1800802a6  mov     rcx, [rax+50h]
0x1800802aa  add     rcx, r14; Str
0x1800802ad  call    cs:__imp_wcschr
0x1800802b4  nop     dword ptr [rax+rax+00h]
0x1800802b9  mov     rdx, rax; Source
0x1800802bc  lea     rcx, [rbp+UnicodeString]; Destination
0x1800802c0  call    cs:__imp_RtlAppendUnicodeToString
0x1800802c7  nop     dword ptr [rax+rax+00h]
0x1800802cc  mov     rdi, cs:g_PEBootDriverList
0x1800802d3  test    rdi, rdi
0x1800802d6  jz      short loc_1800802FF
0x1800802d8  lea     rcx, [rdi+10h]; String1
0x1800802dc  mov     r8b, 1; CaseInSensitive
0x1800802df  lea     rdx, [rbp+UnicodeString]; String2
0x1800802e3  call    cs:__imp_RtlCompareUnicodeString
0x1800802ea  nop     dword ptr [rax+rax+00h]
0x1800802ef  test    eax, eax
0x1800802f1  jz      short loc_1800802F8
0x1800802f3  mov     rdi, [rdi]
0x1800802f6  jmp     short loc_1800802D3
0x1800802f8  mov     dword ptr [rdi+20h], 0C0000428h
0x1800802ff  mov     rcx, [rbp+UnicodeString.Buffer]; P
0x180080303  xor     edx, edx; Tag
0x180080305  call    cs:__imp_ExFreePoolWithTag
0x18008030c  nop     dword ptr [rax+rax+00h]
0x180080311  mov     rbx, [rbx]
0x180080314  jmp     loc_18008022D
0x180080319  xor     edx, edx
0x18008031b  lea     ecx, [rdx+1]
0x18008031e  call    PEAuthStoreParameter
0x180080323  mov     cs:g_PEAuthStateVariables, 0
0x18008032d  xor     edx, edx; Tag
0x18008032f  mov     rcx, r15; P
0x180080332  call    cs:__imp_ExFreePoolWithTag
0x180080339  nop     dword ptr [rax+rax+00h]
0x18008033e  add     rsp, 58h
0x180080342  pop     r15
0x180080344  pop     r14
0x180080346  pop     r12
0x180080348  pop     rdi
0x180080349  pop     rbx
0x18008034a  pop     rbp
0x18008034b  retn
```
