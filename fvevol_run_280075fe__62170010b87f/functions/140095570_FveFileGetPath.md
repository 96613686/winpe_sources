# FveFileGetPath

- ea: `0x140095570`
- end: `0x140095754`
- name: `FveFileGetPath`
- size: `484`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING SourceString@<rcx>, GUID *Guid@<rdx>, PUNICODE_STRING DestinationString)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400909ec`
- `0x1400953a8`

## callees

- `0x140007830`
- `0x140008dc0`
- `0x140008e44`
- `0x1400218c0`
- `0x140095570`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400955cf`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400955cf`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14009566d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14009566d`
- `ntoskrnl!RtlStringFromGUID` at `0x140095653`
- `ntoskrnl!RtlStringFromGUID` at `0x140095653`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140095680`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140095680`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400955e5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140095605`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140095621`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140095639`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14009570f`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400955e5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140095605`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140095621`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140095639`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14009570f`

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
0x140095570  push    rbx
0x140095572  push    rbp
0x140095573  push    rsi
0x140095574  push    rdi
0x140095575  push    r14
0x140095577  push    r15
0x140095579  sub     rsp, 88h
0x140095580  mov     rax, cs:__security_cookie
0x140095587  xor     rax, rsp
0x14009558a  mov     [rsp+0B8h+var_48], rax
0x14009558f  mov     rdi, [rsp+0B8h+DestinationString]
0x140095597  xorps   xmm0, xmm0
0x14009559a  movups  xmmword ptr [rsp+0B8h+GuidString.Length], xmm0
0x14009559f  mov     rbp, r9
0x1400955a2  mov     esi, r8d
0x1400955a5  mov     r14, rdx
0x1400955a8  mov     rbx, rcx
0x1400955ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400955b2  lea     r15, WPP_GLOBAL_Control
0x1400955b9  cmp     rcx, r15
0x1400955bc  jz      short loc_1400955C9
0x1400955be  mov     eax, [rcx+2Ch]
0x1400955c1  test    al, 20h
0x1400955c3  jnz     loc_1400956C0
0x1400955c9  mov     rdx, rbx; SourceString
0x1400955cc  mov     rcx, rdi; DestinationString
0x1400955cf  call    cs:__imp_RtlCopyUnicodeString
0x1400955d6  nop     dword ptr [rax+rax+00h]
0x1400955db  lea     rdx, Source; "\\"
0x1400955e2  mov     rcx, rdi; Destination
0x1400955e5  call    cs:__imp_RtlAppendUnicodeToString
0x1400955ec  nop     dword ptr [rax+rax+00h]
0x1400955f1  mov     ebx, eax
0x1400955f3  test    eax, eax
0x1400955f5  js      loc_140095690
0x1400955fb  lea     rdx, aSystemVolumeIn; "System Volume Information"
0x140095602  mov     rcx, rdi; Destination
0x140095605  call    cs:__imp_RtlAppendUnicodeToString
0x14009560c  nop     dword ptr [rax+rax+00h]
0x140095611  mov     ebx, eax
0x140095613  test    eax, eax
0x140095615  js      short loc_140095690
0x140095617  lea     rdx, Source; "\\"
0x14009561e  mov     rcx, rdi; Destination
0x140095621  call    cs:__imp_RtlAppendUnicodeToString
0x140095628  nop     dword ptr [rax+rax+00h]
0x14009562d  mov     ebx, eax
0x14009562f  test    eax, eax
0x140095631  js      short loc_140095690
0x140095633  mov     rdx, rbp; Source
0x140095636  mov     rcx, rdi; Destination
0x140095639  call    cs:__imp_RtlAppendUnicodeToString
0x140095640  nop     dword ptr [rax+rax+00h]
0x140095645  mov     ebx, eax
0x140095647  test    eax, eax
0x140095649  js      short loc_140095690
0x14009564b  lea     rdx, [rsp+0B8h+GuidString]; GuidString
0x140095650  mov     rcx, r14; Guid
0x140095653  call    cs:__imp_RtlStringFromGUID
0x14009565a  nop     dword ptr [rax+rax+00h]
0x14009565f  mov     ebx, eax
0x140095661  test    eax, eax
0x140095663  js      short loc_140095690
0x140095665  lea     rdx, [rsp+0B8h+GuidString]; Source
0x14009566a  mov     rcx, rdi; Destination
0x14009566d  call    cs:__imp_RtlAppendUnicodeStringToString
0x140095674  nop     dword ptr [rax+rax+00h]
0x140095679  lea     rcx, [rsp+0B8h+GuidString]; UnicodeString
0x14009567e  mov     ebx, eax
0x140095680  call    cs:__imp_RtlFreeUnicodeString
0x140095687  nop     dword ptr [rax+rax+00h]
0x14009568c  test    ebx, ebx
0x14009568e  jns     short loc_1400956E4
0x140095690  mov     rcx, cs:WPP_GLOBAL_Control
0x140095697  cmp     rcx, r15
0x14009569a  jnz     loc_140095722
0x1400956a0  mov     eax, ebx
0x1400956a2  mov     rcx, [rsp+0B8h+var_48]
0x1400956a7  xor     rcx, rsp; StackCookie
0x1400956aa  call    __security_check_cookie
0x1400956af  add     rsp, 88h
0x1400956b6  pop     r15
0x1400956b8  pop     r14
0x1400956ba  pop     rdi
0x1400956bb  pop     rsi
0x1400956bc  pop     rbp
0x1400956bd  pop     rbx
0x1400956be  retn
0x1400956c0  cmp     byte ptr [rcx+29h], 5
0x1400956c4  jb      loc_1400955C9
0x1400956ca  mov     rcx, [rcx+18h]
0x1400956ce  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x1400956d5  mov     edx, 1Eh
0x1400956da  call    WPP_SF_
0x1400956df  jmp     loc_1400955C9
0x1400956e4  test    esi, esi
0x1400956e6  jle     short loc_140095690
0x1400956e8  mov     r9d, esi
0x1400956eb  lea     r8, aD; ".%d"
0x1400956f2  mov     edx, 40h ; '@'; cbDest
0x1400956f7  lea     rcx, [rsp+0B8h+pszDest]; pszDest
0x1400956fc  call    RtlStringCbPrintfW
0x140095701  mov     ebx, eax
0x140095703  test    eax, eax
0x140095705  js      short loc_140095690
0x140095707  lea     rdx, [rsp+0B8h+pszDest]; Source
0x14009570c  mov     rcx, rdi; Destination
0x14009570f  call    cs:__imp_RtlAppendUnicodeToString
0x140095716  nop     dword ptr [rax+rax+00h]
0x14009571b  mov     ebx, eax
0x14009571d  jmp     loc_140095690
0x140095722  mov     eax, [rcx+2Ch]
0x140095725  test    al, 20h
0x140095727  jz      loc_1400956A0
0x14009572d  cmp     byte ptr [rcx+29h], 5
0x140095731  jb      loc_1400956A0
0x140095737  mov     rcx, [rcx+18h]
0x14009573b  lea     r8, WPP_da32f44cce2a3b38e812d6f02aeccf92_Traceguids
0x140095742  mov     edx, 1Fh
0x140095747  mov     r9d, ebx
0x14009574a  call    WPP_SF_d
0x14009574f  jmp     loc_1400956A0
```
