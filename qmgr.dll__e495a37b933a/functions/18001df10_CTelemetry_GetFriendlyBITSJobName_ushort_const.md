# CTelemetry::GetFriendlyBITSJobName(ushort const *)

- ea: `0x18001df10`
- end: `0x18001e1be`
- name: `?GetFriendlyBITSJobName@CTelemetry@@SAPEBGPEBG@Z`
- size: `686`
- prototype: `const unsigned __int16 *__fastcall(LPCWCH lpString1)`
- caller_count: `9`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001bac0`
- `0x18001eeb8`
- `0x18001ef30`
- `0x18008339c`
- `0x1800898ac`
- `0x18008995c`
- `0x180089acc`
- `0x1800d1468`
- `0x1800d176c`

## callees

- `0x18001df10`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001df33`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001df67`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001df95`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001dfc9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001dff7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e025`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e053`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e081`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e0af`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e0dd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e10b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e139`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e16d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e198`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001df33`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001df67`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001df95`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001dfc9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001dff7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e025`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e053`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e081`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e0af`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e0dd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e10b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e139`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e16d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e198`

## string_xrefs

- `0x18001df3e`: `WindowsUpdate`

## pseudocode

```c
const unsigned __int16 *__fastcall CTelemetry::GetFriendlyBITSJobName(LPCWCH lpString1)
{
  const unsigned __int16 *result; // rax
  bool v3; // zf

  if ( CompareStringOrdinal(lpString1, -1, L"WU Client Download", -1, 0) == 2 )
    return L"WindowsUpdate";
  if ( CompareStringOrdinal(lpString1, -1, L"MicrosoftMapsMosGeoStore", -1, 0) == 2 )
    return L"MapsMos";
  if ( CompareStringOrdinal(lpString1, -1, L"MicrosoftMapsBingGeoStore", -1, 0) == 2 )
    return L"MapsBing";
  if ( CompareStringOrdinal(lpString1, -1, L"HTTP(S) AppX Download", -1, 0) == 2 )
    return L"AppX";
  if ( CompareStringOrdinal(lpString1, -1, L"MDMSW Job", -1, 0) == 2 )
    return L"MDM";
  if ( CompareStringOrdinal(lpString1, -1, L"Font Download", -1, 0) == 2 )
    return L"FontDownload";
  if ( CompareStringOrdinal(lpString1, -1, L"Font Metadata Download", -1, 0) == 2 )
    return L"FontMetadataDownload";
  if ( CompareStringOrdinal(lpString1, -1, L"Font File Download", -1, 0) == 2 )
    return L"FontFileDownload";
  if ( CompareStringOrdinal(lpString1, -1, L"CCMDTS Job", -1, 0) == 2 )
    return L"CCM";
  if ( CompareStringOrdinal(lpString1, -1, L"Push Notification Platform Job: 1", -1, 0) == 2 )
    return L"PushNotification1";
  if ( CompareStringOrdinal(lpString1, -1, L"Push Notification Platform Job: 2", -1, 0) == 2 )
    return L"PushNotification2";
  if ( CompareStringOrdinal(lpString1, -1, L"Push Notification Platform Job: 3", -1, 0) == 2 )
    return L"PushNotification3";
  if ( CompareStringOrdinal(lpString1, -1, L"Push Notification Platform Job: 4", -1, 0) == 2 )
    return L"PushNotification4";
  v3 = CompareStringOrdinal(lpString1, -1, L"SpeechModelDownloadJob", -1, 0) == 2;
  result = L"SpeechModel";
  if ( !v3 )
    return L"Other";
  return result;
}

```

## disassembly

```asm
0x18001df10  mov     [rsp+arg_0], rbx
0x18001df15  push    rdi
0x18001df16  sub     rsp, 30h
0x18001df1a  mov     r9d, 0FFFFFFFFh; cchCount2
0x18001df20  lea     r8, String2; "WU Client Download"
0x18001df27  xor     edi, edi
0x18001df29  mov     edx, r9d; cchCount1
0x18001df2c  mov     rbx, rcx
0x18001df2f  mov     [rsp+38h+bIgnoreCase], edi; bIgnoreCase
0x18001df33  call    cs:__imp_CompareStringOrdinal
0x18001df39  cmp     eax, 2
0x18001df3c  jnz     short loc_18001DF50
0x18001df3e  lea     rax, aWindowsupdate; "WindowsUpdate"
0x18001df45  mov     rbx, [rsp+38h+arg_0]
0x18001df4a  add     rsp, 30h
0x18001df4e  pop     rdi
0x18001df4f  retn
0x18001df50  mov     r9d, 0FFFFFFFFh; cchCount2
0x18001df56  mov     [rsp+38h+bIgnoreCase], edi; bIgnoreCase
0x18001df5a  mov     edx, r9d; cchCount1
0x18001df5d  lea     r8, aMicrosoftmapsm; "MicrosoftMapsMosGeoStore"
0x18001df64  mov     rcx, rbx; lpString1
0x18001df67  call    cs:__imp_CompareStringOrdinal
0x18001df6d  cmp     eax, 2
0x18001df70  jnz     short loc_18001DF7E
0x18001df72  lea     rax, aMapsmos; "MapsMos"
0x18001df79  jmp     loc_18001E1B3
0x18001df7e  mov     r9d, 0FFFFFFFFh; cchCount2
0x18001df84  mov     [rsp+38h+bIgnoreCase], edi; bIgnoreCase
0x18001df88  mov     edx, r9d; cchCount1
0x18001df8b  lea     r8, aMicrosoftmapsb; "MicrosoftMapsBingGeoStore"
0x18001df92  mov     rcx, rbx; lpString1
0x18001df95  call    cs:__imp_CompareStringOrdinal
0x18001df9b  cmp     eax, 2
0x18001df9e  jnz     short loc_18001DFB2
0x18001dfa0  lea     rax, aMapsbing; "MapsBing"
0x18001dfa7  mov     rbx, [rsp+38h+arg_0]
0x18001dfac  add     rsp, 30h
0x18001dfb0  pop     rdi
0x18001dfb1  retn
0x18001dfb2  mov     r9d, 0FFFFFFFFh; cchCount2
0x18001dfb8  mov     [rsp+38h+bIgnoreCase], edi; bIgnoreCase
0x18001dfbc  mov     edx, r9d; cchCount1
0x18001dfbf  lea     r8, aHttpSAppxDownl; "HTTP(S) AppX Download"
0x18001dfc6  mov     rcx, rbx; lpString1
0x18001dfc9  call    cs:__imp_CompareStringOrdinal
0x18001dfcf  cmp     eax, 2
0x18001dfd2  jnz     short loc_18001DFE0
0x18001dfd4  lea     rax, aAppx_0; "AppX"
0x18001dfdb  jmp     loc_18001E1B3
0x18001dfe0  mov     r9d, 0FFFFFFFFh; cchCount2
0x18001dfe6  mov     [rsp+38h+bIgnoreCase], edi; bIgnoreCase
0x18001dfea  mov     edx, r9d; cchCount1
0x18001dfed  lea     r8, aMdmswJob; "MDMSW Job"
0x18001dff4  mov     rcx, rbx; lpString1
0x18001dff7  call    cs:__imp_CompareStringOrdinal
0x18001dffd  cmp     eax, 2
0x18001e000  jnz     short loc_18001E00E
0x18001e002  lea     rax, aMdm; "MDM"
0x18001e009  jmp     loc_18001E1B3
0x18001e00e  mov     r9d, 0FFFFFFFFh; cchCount2
0x18001e014  mov     [rsp+38h+bIgnoreCase], edi; bIgnoreCase
0x18001e018  mov     edx, r9d; cchCount1
0x18001e01b  lea     r8, aFontDownload; "Font Download"
0x18001e022  mov     rcx, rbx; lpString1
0x18001e025  call    cs:__imp_CompareStringOrdinal
0x18001e02b  cmp     eax, 2
0x18001e02e  jnz     short loc_18001E03C
0x18001e030  lea     rax, aFontdownload; "FontDownload"
0x18001e037  jmp     loc_18001E1B3
0x18001e03c  mov     r9d, 0FFFFFFFFh; cchCount2
0x18001e042  mov     [rsp+38h+bIgnoreCase], edi; bIgnoreCase
0x18001e046  mov     edx, r9d; cchCount1
0x18001e049  lea     r8, aFontMetadataDo; "Font Metadata Download"
0x18001e050  mov     rcx, rbx; lpString1
0x18001e053  call    cs:__imp_CompareStringOrdinal
0x18001e059  cmp     eax, 2
0x18001e05c  jnz     short loc_18001E06A
0x18001e05e  lea     rax, aFontmetadatado; "FontMetadataDownload"
0x18001e065  jmp     loc_18001E1B3
0x18001e06a  mov     r9d, 0FFFFFFFFh; cchCount2
0x18001e070  mov     [rsp+38h+bIgnoreCase], edi; bIgnoreCase
0x18001e074  mov     edx, r9d; cchCount1
0x18001e077  lea     r8, aFontFileDownlo; "Font File Download"
0x18001e07e  mov     rcx, rbx; lpString1
0x18001e081  call    cs:__imp_CompareStringOrdinal
0x18001e087  cmp     eax, 2
0x18001e08a  jnz     short loc_18001E098
0x18001e08c  lea     rax, aFontfiledownlo; "FontFileDownload"
0x18001e093  jmp     loc_18001E1B3
0x18001e098  mov     r9d, 0FFFFFFFFh; cchCount2
0x18001e09e  mov     [rsp+38h+bIgnoreCase], edi; bIgnoreCase
0x18001e0a2  mov     edx, r9d; cchCount1
0x18001e0a5  lea     r8, aCcmdtsJob; "CCMDTS Job"
0x18001e0ac  mov     rcx, rbx; lpString1
0x18001e0af  call    cs:__imp_CompareStringOrdinal
0x18001e0b5  cmp     eax, 2
0x18001e0b8  jnz     short loc_18001E0C6
0x18001e0ba  lea     rax, aCcm; "CCM"
0x18001e0c1  jmp     loc_18001E1B3
0x18001e0c6  mov     r9d, 0FFFFFFFFh; cchCount2
0x18001e0cc  mov     [rsp+38h+bIgnoreCase], edi; bIgnoreCase
0x18001e0d0  mov     edx, r9d; cchCount1
0x18001e0d3  lea     r8, aPushNotificati; "Push Notification Platform Job: 1"
0x18001e0da  mov     rcx, rbx; lpString1
0x18001e0dd  call    cs:__imp_CompareStringOrdinal
0x18001e0e3  cmp     eax, 2
0x18001e0e6  jnz     short loc_18001E0F4
0x18001e0e8  lea     rax, aPushnotificati_2; "PushNotification1"
0x18001e0ef  jmp     loc_18001E1B3
0x18001e0f4  mov     r9d, 0FFFFFFFFh; cchCount2
0x18001e0fa  mov     [rsp+38h+bIgnoreCase], edi; bIgnoreCase
0x18001e0fe  mov     edx, r9d; cchCount1
0x18001e101  lea     r8, aPushNotificati_0; "Push Notification Platform Job: 2"
0x18001e108  mov     rcx, rbx; lpString1
0x18001e10b  call    cs:__imp_CompareStringOrdinal
0x18001e111  cmp     eax, 2
0x18001e114  jnz     short loc_18001E122
0x18001e116  lea     rax, aPushnotificati_0; "PushNotification2"
0x18001e11d  jmp     loc_18001E1B3
0x18001e122  mov     r9d, 0FFFFFFFFh; cchCount2
0x18001e128  mov     [rsp+38h+bIgnoreCase], edi; bIgnoreCase
0x18001e12c  mov     edx, r9d; cchCount1
0x18001e12f  lea     r8, aPushNotificati_1; "Push Notification Platform Job: 3"
0x18001e136  mov     rcx, rbx; lpString1
0x18001e139  call    cs:__imp_CompareStringOrdinal
0x18001e13f  cmp     eax, 2
0x18001e142  jnz     short loc_18001E156
0x18001e144  lea     rax, aPushnotificati; "PushNotification3"
0x18001e14b  mov     rbx, [rsp+38h+arg_0]
0x18001e150  add     rsp, 30h
0x18001e154  pop     rdi
0x18001e155  retn
0x18001e156  mov     r9d, 0FFFFFFFFh; cchCount2
0x18001e15c  mov     [rsp+38h+bIgnoreCase], edi; bIgnoreCase
0x18001e160  mov     edx, r9d; cchCount1
0x18001e163  lea     r8, aPushNotificati_2; "Push Notification Platform Job: 4"
0x18001e16a  mov     rcx, rbx; lpString1
0x18001e16d  call    cs:__imp_CompareStringOrdinal
0x18001e173  cmp     eax, 2
0x18001e176  jnz     short loc_18001E181
0x18001e178  lea     rax, aPushnotificati_1; "PushNotification4"
0x18001e17f  jmp     short loc_18001E1B3
0x18001e181  mov     r9d, 0FFFFFFFFh; cchCount2
0x18001e187  mov     [rsp+38h+bIgnoreCase], edi; bIgnoreCase
0x18001e18b  mov     edx, r9d; cchCount1
0x18001e18e  lea     r8, aSpeechmodeldow; "SpeechModelDownloadJob"
0x18001e195  mov     rcx, rbx; lpString1
0x18001e198  call    cs:__imp_CompareStringOrdinal
0x18001e19e  cmp     eax, 2
0x18001e1a1  lea     rdx, aOther; "Other"
0x18001e1a8  lea     rax, aSpeechmodel; "SpeechModel"
0x18001e1af  cmovnz  rax, rdx
0x18001e1b3  mov     rbx, [rsp+38h+arg_0]
0x18001e1b8  add     rsp, 30h
0x18001e1bc  pop     rdi
0x18001e1bd  retn
```
