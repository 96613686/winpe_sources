# SendWerReportInternal(_WER_REPORT_INFORMATION *,ushort const *,ulong,ulong,ushort const * *,ulong,ushort const * *,ulong)

- ea: `0x180018f84`
- end: `0x18001908e`
- name: `?SendWerReportInternal@@YAJPEAU_WER_REPORT_INFORMATION@@PEBGKKPEAPEBGK2K@Z`
- size: `266`
- prototype: `__int64 __usercall@<rax>(PWER_REPORT_INFORMATION pReportInformation@<rcx>, PCWSTR pwzEventType@<rdx>, DWORD dwFlags@<r8d>, unsigned int@<r9d>, const unsigned __int16 **, unsigned int, const unsigned __int16 **, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180018cc4`

## callees

- `0x1800187d0`
- `0x180018f84`

## import_xrefs

- `wer!WerReportCloseHandle` at `0x180019078`
- `wer!WerReportCloseHandle` at `0x180019078`
- `wer!WerReportSetParameter` at `0x180018fe5`
- `wer!WerReportSetParameter` at `0x180018fe5`
- `wer!WerReportCreate` at `0x180018fb4`
- `wer!WerReportCreate` at `0x180018fb4`
- `wer!WerReportAddFile` at `0x18001903f`
- `wer!WerReportAddFile` at `0x18001903f`
- `wer!WerReportSubmit` at `0x18001905f`
- `wer!WerReportSubmit` at `0x18001905f`

## pseudocode

```c
__int64 __fastcall SendWerReportInternal(
        PWER_REPORT_INFORMATION pReportInformation,
        PCWSTR pwzEventType,
        DWORD dwFlags,
        char a4,
        const unsigned __int16 **a5,
        unsigned int a6,
        const unsigned __int16 **a7,
        unsigned int a8)
{
  HRESULT v11; // ebx
  __int64 v12; // rdi
  __int64 v13; // rbx
  HREPORT phReportHandle; // [rsp+20h] [rbp-48h] BYREF

  phReportHandle = 0;
  v11 = WerReportCreate(pwzEventType, WerReportNonCritical, pReportInformation, &phReportHandle);
  if ( v11 >= 0 )
  {
    v12 = 0;
    if ( a6 )
    {
      while ( 1 )
      {
        v11 = WerReportSetParameter(phReportHandle, v12, 0, a5[v12]);
        if ( v11 < 0 )
          break;
        v12 = (unsigned int)(v12 + 1);
        if ( (unsigned int)v12 >= a6 )
          goto LABEL_5;
      }
    }
    else
    {
LABEL_5:
      if ( (a4 & 1) != 0 )
        AddFileToWerReport(pReportInformation->wzApplicationPath, phReportHandle);
      if ( a7 && a8 )
      {
        v13 = 0;
        do
        {
          WerReportAddFile(phReportHandle, a7[v13], WerFileTypeOther, 1u);
          v13 = (unsigned int)(v13 + 1);
        }
        while ( (unsigned int)v13 < a8 );
      }
      v11 = WerReportSubmit(phReportHandle, WerConsentNotAsked, dwFlags, 0);
      if ( v11 >= 0 )
        v11 = 0;
    }
  }
  if ( phReportHandle )
    WerReportCloseHandle(phReportHandle);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180018f84  push    rbx
0x180018f86  push    rbp
0x180018f87  push    rdi
0x180018f88  push    r12
0x180018f8a  push    r14
0x180018f8c  push    r15
0x180018f8e  sub     rsp, 38h
0x180018f92  mov     rax, rdx
0x180018f95  mov     [rsp+68h+phReportHandle], 0
0x180018f9e  mov     r12d, r8d
0x180018fa1  mov     r15d, r9d
0x180018fa4  mov     r8, rcx; pReportInformation
0x180018fa7  lea     r9, [rsp+68h+phReportHandle]; phReportHandle
0x180018fac  mov     rbp, rcx
0x180018faf  xor     edx, edx; repType
0x180018fb1  mov     rcx, rax; pwzEventType
0x180018fb4  call    cs:__imp_WerReportCreate
0x180018fba  mov     ebx, eax
0x180018fbc  test    eax, eax
0x180018fbe  js      loc_18001906E
0x180018fc4  mov     r14, [rsp+68h+arg_20]
0x180018fcc  xor     edi, edi
0x180018fce  cmp     [rsp+68h+arg_28], edi
0x180018fd5  jbe     short loc_180018FFC
0x180018fd7  mov     r9, [r14+rdi*8]; pwzValue
0x180018fdb  xor     r8d, r8d; pwzName
0x180018fde  mov     rcx, [rsp+68h+phReportHandle]; hReportHandle
0x180018fe3  mov     edx, edi; dwparamID
0x180018fe5  call    cs:__imp_WerReportSetParameter
0x180018feb  mov     ebx, eax
0x180018fed  test    eax, eax
0x180018fef  js      short loc_18001906E
0x180018ff1  inc     edi
0x180018ff3  cmp     edi, [rsp+68h+arg_28]
0x180018ffa  jb      short loc_180018FD7
0x180018ffc  test    r15b, 1
0x180019000  jz      short loc_180019013
0x180019002  mov     rdx, [rsp+68h+phReportHandle]; void *
0x180019007  lea     rcx, [rbp+290h]; unsigned __int16 *
0x18001900e  call    ?AddFileToWerReport@@YAJPEBGPEAX@Z; AddFileToWerReport(ushort const *,void *)
0x180019013  mov     rdi, [rsp+68h+arg_30]
0x18001901b  test    rdi, rdi
0x18001901e  jz      short loc_180019050
0x180019020  cmp     [rsp+68h+arg_38], 0
0x180019028  jbe     short loc_180019050
0x18001902a  xor     ebx, ebx
0x18001902c  mov     rdx, [rdi+rbx*8]; pwzPath
0x180019030  mov     r9d, 1; dwFileFlags
0x180019036  mov     rcx, [rsp+68h+phReportHandle]; hReportHandle
0x18001903b  lea     r8d, [r9+4]; repFileType
0x18001903f  call    cs:__imp_WerReportAddFile
0x180019045  inc     ebx
0x180019047  cmp     ebx, [rsp+68h+arg_38]
0x18001904e  jb      short loc_18001902C
0x180019050  mov     rcx, [rsp+68h+phReportHandle]; hReportHandle
0x180019055  xor     r9d, r9d; pSubmitResult
0x180019058  mov     r8d, r12d; dwFlags
0x18001905b  lea     edx, [r9+1]; consent
0x18001905f  call    cs:__imp_WerReportSubmit
0x180019065  mov     ebx, eax
0x180019067  xor     eax, eax
0x180019069  test    ebx, ebx
0x18001906b  cmovns  ebx, eax
0x18001906e  mov     rcx, [rsp+68h+phReportHandle]; hReportHandle
0x180019073  test    rcx, rcx
0x180019076  jz      short loc_18001907E
0x180019078  call    cs:__imp_WerReportCloseHandle
0x18001907e  mov     eax, ebx
0x180019080  add     rsp, 38h
0x180019084  pop     r15
0x180019086  pop     r14
0x180019088  pop     r12
0x18001908a  pop     rdi
0x18001908b  pop     rbp
0x18001908c  pop     rbx
0x18001908d  retn
```
