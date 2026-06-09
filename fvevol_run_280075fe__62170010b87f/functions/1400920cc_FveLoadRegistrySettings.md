# FveLoadRegistrySettings

- ea: `0x1400920cc`
- end: `0x140092308`
- name: `FveLoadRegistrySettings`
- size: `572`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14005f7e0`
- `0x14005fa50`
- `0x140091794`
- `0x1400c8ba8`
- `0x1400c9120`
- `0x1400ebf70`
- `0x1400ebfe0`
- `0x1400ec0a0`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x140021d00`
- `0x1400920cc`
- `0x1400de1d4`
- `0x1400e3a5c`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400921fa`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400922bb`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400921fa`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400922bb`
- `ntoskrnl!RtlStringFromGUID` at `0x140092180`
- `ntoskrnl!RtlStringFromGUID` at `0x140092180`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400921b4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400921b4`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14009215e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14009219e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14009229d`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14009215e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14009219e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14009229d`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140092249`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140092249`

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
0x1400920cc  push    rbp
0x1400920ce  push    rbx
0x1400920cf  push    rsi
0x1400920d0  push    rdi
0x1400920d1  push    r12
0x1400920d3  push    r13
0x1400920d5  push    r14
0x1400920d7  push    r15
0x1400920d9  lea     rbp, [rsp-17h]
0x1400920de  sub     rsp, 0C8h
0x1400920e5  xor     r12d, r12d
0x1400920e8  lea     rax, aFvevol_0; "FVEVOL"
0x1400920ef  test    r8, r8
0x1400920f2  mov     rsi, r8
0x1400920f5  xorps   xmm0, xmm0
0x1400920f8  xorps   xmm1, xmm1
0x1400920fb  cmovz   rsi, rax
0x1400920ff  mov     rdi, r9
0x140092102  mov     r14d, edx
0x140092105  mov     r15, rcx
0x140092108  movups  xmmword ptr [rbp+4Fh+GuidString.Length], xmm0
0x14009210c  movups  xmmword ptr [rsp+100h+Destination.Length], xmm1
0x140092111  mov     rcx, cs:WPP_GLOBAL_Control
0x140092118  lea     r13, WPP_GLOBAL_Control
0x14009211f  cmp     rcx, r13
0x140092122  jnz     loc_14009225C
0x140092128  xor     edx, edx; Val
0x14009212a  lea     rcx, [rbp+4Fh+var_B0]; void *
0x14009212e  xorps   xmm0, xmm0
0x140092131  xorps   xmm1, xmm1
0x140092134  movups  xmmword ptr [rbp+4Fh+GuidString.Length], xmm0
0x140092138  lea     r8d, [rdx+70h]; Size
0x14009213c  movups  xmmword ptr [rsp+100h+Destination.Length], xmm1
0x140092141  call    memset
0x140092146  lea     rcx, [rsp+100h+Destination]
0x14009214b  call    FveAllocateUnicodePath
0x140092150  mov     ebx, eax
0x140092152  test    eax, eax
0x140092154  js      short loc_1400921B0
0x140092156  mov     rdx, rsi; Source
0x140092159  lea     rcx, [rsp+100h+Destination]; Destination
0x14009215e  call    cs:__imp_RtlAppendUnicodeToString
0x140092165  nop     dword ptr [rax+rax+00h]
0x14009216a  mov     ebx, eax
0x14009216c  test    eax, eax
0x14009216e  js      short loc_1400921B0
0x140092170  test    rdi, rdi
0x140092173  jz      loc_14009220C
0x140092179  lea     rdx, [rbp+4Fh+GuidString]; GuidString
0x14009217d  mov     rcx, rdi; Guid
0x140092180  call    cs:__imp_RtlStringFromGUID
0x140092187  nop     dword ptr [rax+rax+00h]
0x14009218c  mov     ebx, eax
0x14009218e  test    eax, eax
0x140092190  js      short loc_1400921B0
0x140092192  lea     rdx, Source; "\\"
0x140092199  lea     rcx, [rsp+100h+Destination]; Destination
0x14009219e  call    cs:__imp_RtlAppendUnicodeToString
0x1400921a5  nop     dword ptr [rax+rax+00h]
0x1400921aa  mov     ebx, eax
0x1400921ac  test    eax, eax
0x1400921ae  jns     short loc_1400921F1
0x1400921b0  lea     rcx, [rbp+4Fh+GuidString]; UnicodeString
0x1400921b4  call    cs:__imp_RtlFreeUnicodeString
0x1400921bb  nop     dword ptr [rax+rax+00h]
0x1400921c0  lea     rcx, [rsp+100h+Destination]
0x1400921c5  call    FveFreeUnicodePath
0x1400921ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400921d1  cmp     rcx, r13
0x1400921d4  jnz     loc_1400922D6
0x1400921da  mov     eax, ebx
0x1400921dc  add     rsp, 0C8h
0x1400921e3  pop     r15
0x1400921e5  pop     r14
0x1400921e7  pop     r13
0x1400921e9  pop     r12
0x1400921eb  pop     rdi
0x1400921ec  pop     rsi
0x1400921ed  pop     rbx
0x1400921ee  pop     rbp
0x1400921ef  retn
0x1400921f1  lea     rdx, [rbp+4Fh+GuidString]; Source
0x1400921f5  lea     rcx, [rsp+100h+Destination]; Destination
0x1400921fa  call    cs:__imp_RtlAppendUnicodeStringToString
0x140092201  nop     dword ptr [rax+rax+00h]
0x140092206  mov     ebx, eax
0x140092208  test    eax, eax
0x14009220a  js      short loc_1400921B0
0x14009220c  mov     rdi, [rbp+4Fh+Source]
0x140092210  test    rdi, rdi
0x140092213  jnz     short loc_14009228B
0x140092215  movzx   edx, [rbp+4Fh+Destination.MaximumLength]
0x140092219  lea     r9, [rbp+4Fh+var_B0]
0x14009221d  mov     rax, [rbp+4Fh+Destination.Buffer]
0x140092221  lea     r8, [rbp+4Fh+var_B0]
0x140092225  shr     rdx, 1
0x140092228  mov     ecx, r14d
0x14009222b  mov     [rsp+100h+var_E0], r12
0x140092230  mov     [rax+rdx*2-2], r12w
0x140092236  lea     rax, FveLoadRegistryQueryRoutine
0x14009223d  mov     rdx, [rbp+4Fh+Destination.Buffer]
0x140092241  mov     [rbp+4Fh+var_B0], rax
0x140092245  mov     [rbp+4Fh+var_98], r15
0x140092249  call    cs:__imp_RtlQueryRegistryValuesEx
0x140092250  nop     dword ptr [rax+rax+00h]
0x140092255  mov     ebx, eax
0x140092257  jmp     loc_1400921B0
0x14009225c  mov     eax, [rcx+2Ch]
0x14009225f  test    al, 8
0x140092261  jz      loc_140092128
0x140092267  cmp     byte ptr [rcx+29h], 5
0x14009226b  jb      loc_140092128
0x140092271  mov     rcx, [rcx+18h]
0x140092275  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14009227c  mov     edx, 34h ; '4'
0x140092281  call    WPP_SF_
0x140092286  jmp     loc_140092128
0x14009228b  cmp     [rdi], r12w
0x14009228f  jbe     short loc_140092215
0x140092291  lea     rdx, Source; "\\"
0x140092298  lea     rcx, [rsp+100h+Destination]; Destination
0x14009229d  call    cs:__imp_RtlAppendUnicodeToString
0x1400922a4  nop     dword ptr [rax+rax+00h]
0x1400922a9  mov     ebx, eax
0x1400922ab  test    eax, eax
0x1400922ad  js      loc_1400921B0
0x1400922b3  mov     rdx, rdi; Source
0x1400922b6  lea     rcx, [rsp+100h+Destination]; Destination
0x1400922bb  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400922c2  nop     dword ptr [rax+rax+00h]
0x1400922c7  mov     ebx, eax
0x1400922c9  test    eax, eax
0x1400922cb  js      loc_1400921B0
0x1400922d1  jmp     loc_140092215
0x1400922d6  mov     eax, [rcx+2Ch]
0x1400922d9  test    al, 8
0x1400922db  jz      loc_1400921DA
0x1400922e1  cmp     byte ptr [rcx+29h], 5
0x1400922e5  jb      loc_1400921DA
0x1400922eb  mov     rcx, [rcx+18h]
0x1400922ef  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400922f6  mov     edx, 35h ; '5'
0x1400922fb  mov     r9d, ebx
0x1400922fe  call    WPP_SF_d
0x140092303  jmp     loc_1400921DA
```
