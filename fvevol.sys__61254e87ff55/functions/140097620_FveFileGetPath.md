# FveFileGetPath

- ea: `0x140097620`
- end: `0x140097804`
- name: `FveFileGetPath`
- size: `484`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING SourceString@<rcx>, GUID *Guid@<rdx>, PUNICODE_STRING DestinationString)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140092a9c`
- `0x140097458`

## callees

- `0x1400078f0`
- `0x140008e80`
- `0x140008f04`
- `0x140022bf0`
- `0x140097620`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14009767f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14009767f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14009771d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14009771d`
- `ntoskrnl!RtlStringFromGUID` at `0x140097703`
- `ntoskrnl!RtlStringFromGUID` at `0x140097703`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140097730`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140097730`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140097695`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400976b5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400976d1`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400976e9`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400977bf`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140097695`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400976b5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400976d1`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400976e9`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400977bf`

## pseudocode

```c
__int64 __fastcall FveFileGetPath(
        PCUNICODE_STRING SourceString,
        GUID *Guid,
        int a3,
        const WCHAR *a4,
        PUNICODE_STRING DestinationString)
{
  NTSTATUS appended; // ebx
  struct _UNICODE_STRING GuidString; // [rsp+20h] [rbp-98h] BYREF
  wchar_t pszDest[32]; // [rsp+30h] [rbp-88h] BYREF

  GuidString = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids);
  }
  RtlCopyUnicodeString(DestinationString, SourceString);
  appended = RtlAppendUnicodeToString(DestinationString, L"\\");
  if ( appended >= 0 )
  {
    appended = RtlAppendUnicodeToString(DestinationString, L"System Volume Information");
    if ( appended >= 0 )
    {
      appended = RtlAppendUnicodeToString(DestinationString, L"\\");
      if ( appended >= 0 )
      {
        appended = RtlAppendUnicodeToString(DestinationString, a4);
        if ( appended >= 0 )
        {
          appended = RtlStringFromGUID(Guid, &GuidString);
          if ( appended >= 0 )
          {
            appended = RtlAppendUnicodeStringToString(DestinationString, &GuidString);
            RtlFreeUnicodeString(&GuidString);
            if ( appended >= 0 && a3 > 0 )
            {
              appended = RtlStringCbPrintfW(
                           pszDest,
                           0x40u,
                           L".%d",
                           (unsigned int)a3,
                           *(_QWORD *)&GuidString.Length,
                           GuidString.Buffer);
              if ( appended >= 0 )
                appended = RtlAppendUnicodeToString(DestinationString, pszDest);
            }
          }
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      31,
      WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids,
      (unsigned int)appended);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140097620  push    rbx
0x140097622  push    rbp
0x140097623  push    rsi
0x140097624  push    rdi
0x140097625  push    r14
0x140097627  push    r15
0x140097629  sub     rsp, 88h
0x140097630  mov     rax, cs:__security_cookie
0x140097637  xor     rax, rsp
0x14009763a  mov     [rsp+0B8h+var_48], rax
0x14009763f  mov     rdi, [rsp+0B8h+DestinationString]
0x140097647  xorps   xmm0, xmm0
0x14009764a  movups  xmmword ptr [rsp+0B8h+GuidString.Length], xmm0
0x14009764f  mov     rbp, r9
0x140097652  mov     esi, r8d
0x140097655  mov     r14, rdx
0x140097658  mov     rbx, rcx
0x14009765b  mov     rcx, cs:WPP_GLOBAL_Control
0x140097662  lea     r15, WPP_GLOBAL_Control
0x140097669  cmp     rcx, r15
0x14009766c  jz      short loc_140097679
0x14009766e  mov     eax, [rcx+2Ch]
0x140097671  test    al, 20h
0x140097673  jnz     loc_140097770
0x140097679  mov     rdx, rbx; SourceString
0x14009767c  mov     rcx, rdi; DestinationString
0x14009767f  call    cs:__imp_RtlCopyUnicodeString
0x140097686  nop     dword ptr [rax+rax+00h]
0x14009768b  lea     rdx, Source; "\\"
0x140097692  mov     rcx, rdi; Destination
0x140097695  call    cs:__imp_RtlAppendUnicodeToString
0x14009769c  nop     dword ptr [rax+rax+00h]
0x1400976a1  mov     ebx, eax
0x1400976a3  test    eax, eax
0x1400976a5  js      loc_140097740
0x1400976ab  lea     rdx, aSystemVolumeIn; "System Volume Information"
0x1400976b2  mov     rcx, rdi; Destination
0x1400976b5  call    cs:__imp_RtlAppendUnicodeToString
0x1400976bc  nop     dword ptr [rax+rax+00h]
0x1400976c1  mov     ebx, eax
0x1400976c3  test    eax, eax
0x1400976c5  js      short loc_140097740
0x1400976c7  lea     rdx, Source; "\\"
0x1400976ce  mov     rcx, rdi; Destination
0x1400976d1  call    cs:__imp_RtlAppendUnicodeToString
0x1400976d8  nop     dword ptr [rax+rax+00h]
0x1400976dd  mov     ebx, eax
0x1400976df  test    eax, eax
0x1400976e1  js      short loc_140097740
0x1400976e3  mov     rdx, rbp; Source
0x1400976e6  mov     rcx, rdi; Destination
0x1400976e9  call    cs:__imp_RtlAppendUnicodeToString
0x1400976f0  nop     dword ptr [rax+rax+00h]
0x1400976f5  mov     ebx, eax
0x1400976f7  test    eax, eax
0x1400976f9  js      short loc_140097740
0x1400976fb  lea     rdx, [rsp+0B8h+GuidString]; GuidString
0x140097700  mov     rcx, r14; Guid
0x140097703  call    cs:__imp_RtlStringFromGUID
0x14009770a  nop     dword ptr [rax+rax+00h]
0x14009770f  mov     ebx, eax
0x140097711  test    eax, eax
0x140097713  js      short loc_140097740
0x140097715  lea     rdx, [rsp+0B8h+GuidString]; Source
0x14009771a  mov     rcx, rdi; Destination
0x14009771d  call    cs:__imp_RtlAppendUnicodeStringToString
0x140097724  nop     dword ptr [rax+rax+00h]
0x140097729  lea     rcx, [rsp+0B8h+GuidString]; UnicodeString
0x14009772e  mov     ebx, eax
0x140097730  call    cs:__imp_RtlFreeUnicodeString
0x140097737  nop     dword ptr [rax+rax+00h]
0x14009773c  test    ebx, ebx
0x14009773e  jns     short loc_140097794
0x140097740  mov     rcx, cs:WPP_GLOBAL_Control
0x140097747  cmp     rcx, r15
0x14009774a  jnz     loc_1400977D2
0x140097750  mov     eax, ebx
0x140097752  mov     rcx, [rsp+0B8h+var_48]
0x140097757  xor     rcx, rsp; StackCookie
0x14009775a  call    __security_check_cookie
0x14009775f  add     rsp, 88h
0x140097766  pop     r15
0x140097768  pop     r14
0x14009776a  pop     rdi
0x14009776b  pop     rsi
0x14009776c  pop     rbp
0x14009776d  pop     rbx
0x14009776e  retn
0x140097770  cmp     byte ptr [rcx+29h], 5
0x140097774  jb      loc_140097679
0x14009777a  mov     rcx, [rcx+18h]
0x14009777e  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x140097785  mov     edx, 1Eh
0x14009778a  call    WPP_SF_
0x14009778f  jmp     loc_140097679
0x140097794  test    esi, esi
0x140097796  jle     short loc_140097740
0x140097798  mov     r9d, esi
0x14009779b  lea     r8, aD; ".%d"
0x1400977a2  mov     edx, 40h ; '@'; cbDest
0x1400977a7  lea     rcx, [rsp+0B8h+pszDest]; pszDest
0x1400977ac  call    RtlStringCbPrintfW
0x1400977b1  mov     ebx, eax
0x1400977b3  test    eax, eax
0x1400977b5  js      short loc_140097740
0x1400977b7  lea     rdx, [rsp+0B8h+pszDest]; Source
0x1400977bc  mov     rcx, rdi; Destination
0x1400977bf  call    cs:__imp_RtlAppendUnicodeToString
0x1400977c6  nop     dword ptr [rax+rax+00h]
0x1400977cb  mov     ebx, eax
0x1400977cd  jmp     loc_140097740
0x1400977d2  mov     eax, [rcx+2Ch]
0x1400977d5  test    al, 20h
0x1400977d7  jz      loc_140097750
0x1400977dd  cmp     byte ptr [rcx+29h], 5
0x1400977e1  jb      loc_140097750
0x1400977e7  mov     rcx, [rcx+18h]
0x1400977eb  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x1400977f2  mov     edx, 1Fh
0x1400977f7  mov     r9d, ebx
0x1400977fa  call    WPP_SF_d
0x1400977ff  jmp     loc_140097750
```
