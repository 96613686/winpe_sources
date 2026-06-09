# FveLoadRegistrySettings

- ea: `0x14009417c`
- end: `0x1400943b8`
- name: `FveLoadRegistrySettings`
- size: `572`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140061860`
- `0x140061ad0`
- `0x140093844`
- `0x1400cc684`
- `0x1400ccbf0`
- `0x1400f0f60`
- `0x1400f0fd0`
- `0x1400f1090`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x140023040`
- `0x14009417c`
- `0x1400e08f4`
- `0x1400e6538`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400942aa`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14009436b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400942aa`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14009436b`
- `ntoskrnl!RtlStringFromGUID` at `0x140094230`
- `ntoskrnl!RtlStringFromGUID` at `0x140094230`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140094264`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140094264`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14009420e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14009424e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14009434d`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14009420e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14009424e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14009434d`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400942f9`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400942f9`

## pseudocode

```c
__int64 __fastcall FveLoadRegistrySettings(
        __int64 a1,
        unsigned int a2,
        const WCHAR *a3,
        const GUID *a4,
        PCUNICODE_STRING Source)
{
  const WCHAR *v5; // rsi
  NTSTATUS appended; // ebx
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-81h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+40h] [rbp-71h] BYREF
  _QWORD v13[22]; // [rsp+50h] [rbp-61h] BYREF

  v5 = a3;
  if ( !a3 )
    v5 = L"FVEVOL";
  GuidString = 0;
  Destination = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
  }
  GuidString = 0;
  Destination = 0;
  memset(v13, 0, 0x70u);
  appended = FveAllocateUnicodePath(&Destination);
  if ( appended >= 0 )
  {
    appended = RtlAppendUnicodeToString(&Destination, v5);
    if ( appended >= 0 )
    {
      if ( !a4
        || (appended = RtlStringFromGUID(a4, &GuidString), appended >= 0)
        && (appended = RtlAppendUnicodeToString(&Destination, L"\\"), appended >= 0)
        && (appended = RtlAppendUnicodeStringToString(&Destination, &GuidString), appended >= 0) )
      {
        if ( !Source
          || !Source->Length
          || (appended = RtlAppendUnicodeToString(&Destination, L"\\"), appended >= 0)
          && (appended = RtlAppendUnicodeStringToString(&Destination, Source), appended >= 0) )
        {
          Destination.Buffer[((unsigned __int64)Destination.MaximumLength >> 1) - 1] = 0;
          v13[0] = FveLoadRegistryQueryRoutine;
          v13[3] = a1;
          appended = RtlQueryRegistryValuesEx(a2, Destination.Buffer, v13, v13, 0);
        }
      }
    }
  }
  RtlFreeUnicodeString(&GuidString);
  FveFreeUnicodePath(&Destination);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      53,
      WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids,
      (unsigned int)appended);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14009417c  push    rbp
0x14009417e  push    rbx
0x14009417f  push    rsi
0x140094180  push    rdi
0x140094181  push    r12
0x140094183  push    r13
0x140094185  push    r14
0x140094187  push    r15
0x140094189  lea     rbp, [rsp-17h]
0x14009418e  sub     rsp, 0C8h
0x140094195  xor     r12d, r12d
0x140094198  lea     rax, aFvevol_0; "FVEVOL"
0x14009419f  test    r8, r8
0x1400941a2  mov     rsi, r8
0x1400941a5  xorps   xmm0, xmm0
0x1400941a8  xorps   xmm1, xmm1
0x1400941ab  cmovz   rsi, rax
0x1400941af  mov     rdi, r9
0x1400941b2  mov     r14d, edx
0x1400941b5  mov     r15, rcx
0x1400941b8  movups  xmmword ptr [rbp+4Fh+GuidString.Length], xmm0
0x1400941bc  movups  xmmword ptr [rsp+100h+Destination.Length], xmm1
0x1400941c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400941c8  lea     r13, WPP_GLOBAL_Control
0x1400941cf  cmp     rcx, r13
0x1400941d2  jnz     loc_14009430C
0x1400941d8  xor     edx, edx; Val
0x1400941da  lea     rcx, [rbp+4Fh+var_B0]; void *
0x1400941de  xorps   xmm0, xmm0
0x1400941e1  xorps   xmm1, xmm1
0x1400941e4  movups  xmmword ptr [rbp+4Fh+GuidString.Length], xmm0
0x1400941e8  lea     r8d, [rdx+70h]; Size
0x1400941ec  movups  xmmword ptr [rsp+100h+Destination.Length], xmm1
0x1400941f1  call    memset
0x1400941f6  lea     rcx, [rsp+100h+Destination]
0x1400941fb  call    FveAllocateUnicodePath
0x140094200  mov     ebx, eax
0x140094202  test    eax, eax
0x140094204  js      short loc_140094260
0x140094206  mov     rdx, rsi; Source
0x140094209  lea     rcx, [rsp+100h+Destination]; Destination
0x14009420e  call    cs:__imp_RtlAppendUnicodeToString
0x140094215  nop     dword ptr [rax+rax+00h]
0x14009421a  mov     ebx, eax
0x14009421c  test    eax, eax
0x14009421e  js      short loc_140094260
0x140094220  test    rdi, rdi
0x140094223  jz      loc_1400942BC
0x140094229  lea     rdx, [rbp+4Fh+GuidString]; GuidString
0x14009422d  mov     rcx, rdi; Guid
0x140094230  call    cs:__imp_RtlStringFromGUID
0x140094237  nop     dword ptr [rax+rax+00h]
0x14009423c  mov     ebx, eax
0x14009423e  test    eax, eax
0x140094240  js      short loc_140094260
0x140094242  lea     rdx, Source; "\\"
0x140094249  lea     rcx, [rsp+100h+Destination]; Destination
0x14009424e  call    cs:__imp_RtlAppendUnicodeToString
0x140094255  nop     dword ptr [rax+rax+00h]
0x14009425a  mov     ebx, eax
0x14009425c  test    eax, eax
0x14009425e  jns     short loc_1400942A1
0x140094260  lea     rcx, [rbp+4Fh+GuidString]; UnicodeString
0x140094264  call    cs:__imp_RtlFreeUnicodeString
0x14009426b  nop     dword ptr [rax+rax+00h]
0x140094270  lea     rcx, [rsp+100h+Destination]
0x140094275  call    FveFreeUnicodePath
0x14009427a  mov     rcx, cs:WPP_GLOBAL_Control
0x140094281  cmp     rcx, r13
0x140094284  jnz     loc_140094386
0x14009428a  mov     eax, ebx
0x14009428c  add     rsp, 0C8h
0x140094293  pop     r15
0x140094295  pop     r14
0x140094297  pop     r13
0x140094299  pop     r12
0x14009429b  pop     rdi
0x14009429c  pop     rsi
0x14009429d  pop     rbx
0x14009429e  pop     rbp
0x14009429f  retn
0x1400942a1  lea     rdx, [rbp+4Fh+GuidString]; Source
0x1400942a5  lea     rcx, [rsp+100h+Destination]; Destination
0x1400942aa  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400942b1  nop     dword ptr [rax+rax+00h]
0x1400942b6  mov     ebx, eax
0x1400942b8  test    eax, eax
0x1400942ba  js      short loc_140094260
0x1400942bc  mov     rdi, [rbp+4Fh+Source]
0x1400942c0  test    rdi, rdi
0x1400942c3  jnz     short loc_14009433B
0x1400942c5  movzx   edx, [rbp+4Fh+Destination.MaximumLength]
0x1400942c9  lea     r9, [rbp+4Fh+var_B0]
0x1400942cd  mov     rax, [rbp+4Fh+Destination.Buffer]
0x1400942d1  lea     r8, [rbp+4Fh+var_B0]
0x1400942d5  shr     rdx, 1
0x1400942d8  mov     ecx, r14d
0x1400942db  mov     [rsp+100h+var_E0], r12
0x1400942e0  mov     [rax+rdx*2-2], r12w
0x1400942e6  lea     rax, FveLoadRegistryQueryRoutine
0x1400942ed  mov     rdx, [rbp+4Fh+Destination.Buffer]
0x1400942f1  mov     [rbp+4Fh+var_B0], rax
0x1400942f5  mov     [rbp+4Fh+var_98], r15
0x1400942f9  call    cs:__imp_RtlQueryRegistryValuesEx
0x140094300  nop     dword ptr [rax+rax+00h]
0x140094305  mov     ebx, eax
0x140094307  jmp     loc_140094260
0x14009430c  mov     eax, [rcx+2Ch]
0x14009430f  test    al, 8
0x140094311  jz      loc_1400941D8
0x140094317  cmp     byte ptr [rcx+29h], 5
0x14009431b  jb      loc_1400941D8
0x140094321  mov     rcx, [rcx+18h]
0x140094325  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14009432c  mov     edx, 34h ; '4'
0x140094331  call    WPP_SF_
0x140094336  jmp     loc_1400941D8
0x14009433b  cmp     [rdi], r12w
0x14009433f  jbe     short loc_1400942C5
0x140094341  lea     rdx, Source; "\\"
0x140094348  lea     rcx, [rsp+100h+Destination]; Destination
0x14009434d  call    cs:__imp_RtlAppendUnicodeToString
0x140094354  nop     dword ptr [rax+rax+00h]
0x140094359  mov     ebx, eax
0x14009435b  test    eax, eax
0x14009435d  js      loc_140094260
0x140094363  mov     rdx, rdi; Source
0x140094366  lea     rcx, [rsp+100h+Destination]; Destination
0x14009436b  call    cs:__imp_RtlAppendUnicodeStringToString
0x140094372  nop     dword ptr [rax+rax+00h]
0x140094377  mov     ebx, eax
0x140094379  test    eax, eax
0x14009437b  js      loc_140094260
0x140094381  jmp     loc_1400942C5
0x140094386  mov     eax, [rcx+2Ch]
0x140094389  test    al, 8
0x14009438b  jz      loc_14009428A
0x140094391  cmp     byte ptr [rcx+29h], 5
0x140094395  jb      loc_14009428A
0x14009439b  mov     rcx, [rcx+18h]
0x14009439f  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400943a6  mov     edx, 35h ; '5'
0x1400943ab  mov     r9d, ebx
0x1400943ae  call    WPP_SF_d
0x1400943b3  jmp     loc_14009428A
```
