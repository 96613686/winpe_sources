# NlBrowserSyncHostedDomains(void)

- ea: `0x18003aaa0`
- end: `0x18003ad9b`
- name: `?NlBrowserSyncHostedDomains@@YAXXZ`
- size: `763`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800700b0`

## callees

- `0x180007278`
- `0x18000bd98`
- `0x18000e270`
- `0x18000e660`
- `0x180025708`
- `0x180026180`
- `0x18003aaa0`
- `0x18003b574`
- `0x180089aa8`

## import_xrefs

- `ntdll!RtlOemToUnicodeN` at `0x18003ac52`
- `ntdll!RtlOemToUnicodeN` at `0x18003ad28`
- `ntdll!RtlOemToUnicodeN` at `0x18003ac52`
- `ntdll!RtlOemToUnicodeN` at `0x18003ad28`
- `netutils!NetApiBufferFree` at `0x18003ad77`
- `netutils!NetApiBufferFree` at `0x18003ad77`
- `netutils!NetpwNameCompare` at `0x18003ab9e`
- `netutils!NetpwNameCompare` at `0x18003ab9e`
- `srvcli!NetServerTransportEnum` at `0x18003ab03`
- `srvcli!NetServerTransportEnum` at `0x18003ab03`
- `srvcli!NetServerComputerNameDel` at `0x18003ac9f`
- `srvcli!NetServerComputerNameDel` at `0x18003ac9f`

## string_xrefs

- `0x18003ac7c`: `NlBrowserSyncHostedDomains: hosted computer name mismatch (SMB server): %ws %ws.\n`
- `0x18003acb0`: `NlBrowserSyncHostedDomains: can't NetServerComputerNameDel: %ws.\n`
- `0x18003acd9`: `NlBrowserSyncHostedDomains: can't NetServerComputerNameAdd: %ws.\n`

## pseudocode

```c
void NlBrowserSyncHostedDomains(void)
{
  DWORD v0; // eax
  DWORD v1; // ebx
  DWORD v2; // r15d
  __int64 v3; // rdi
  __int64 v4; // rax
  __int64 v5; // r12
  LPBYTE v6; // rsi
  unsigned int v7; // eax
  __int64 i; // r14
  __int64 v9; // rdi
  const WCHAR *v10; // rcx
  struct _DOMAIN_INFO *NetbiosDomain; // rax
  struct _DOMAIN_INFO *v12; // rbx
  unsigned int v13; // eax
  ULONG v14; // r15d
  BYTE *v15; // rdi
  unsigned __int64 v16; // rcx
  NTSTATUS v17; // eax
  unsigned __int64 v18; // rcx
  DWORD entriesread; // [rsp+40h] [rbp-40h] BYREF
  ULONG BytesInUnicodeString; // [rsp+44h] [rbp-3Ch] BYREF
  LPBYTE bufptr; // [rsp+48h] [rbp-38h] BYREF
  DWORD totalentries; // [rsp+50h] [rbp-30h] BYREF
  WCHAR UnicodeString[16]; // [rsp+58h] [rbp-28h] BYREF

  entriesread = 0;
  totalentries = 0;
  bufptr = 0;
  v0 = NetServerTransportEnum(0, 1u, &bufptr, 0xFFFFFFFF, &entriesread, &totalentries, 0);
  if ( !v0 || v0 == 234 )
  {
    v1 = entriesread;
    if ( entriesread )
    {
      v2 = 0;
      do
      {
        v3 = v2 + 1;
        v4 = v2;
        v2 = v3;
        if ( (unsigned int)v3 < v1 )
        {
          v5 = 6 * v4;
          do
          {
            v6 = bufptr;
            if ( *(_QWORD *)&bufptr[8 * v5 + 40] )
            {
              v7 = *(_DWORD *)&bufptr[8 * v5 + 24];
              if ( v7 == *(_DWORD *)&bufptr[48 * v3 + 24]
                && !memcmp_0(*(const void **)&bufptr[8 * v5 + 16], *(const void **)&bufptr[48 * v3 + 16], v7) )
              {
                if ( !(unsigned int)NetpwNameCompare(*(_QWORD *)&v6[8 * v5 + 40], *(_QWORD *)&v6[48 * v3 + 40], 6) )
                  *(_QWORD *)&bufptr[48 * v3 + 40] = 0;
                v1 = entriesread;
              }
            }
            v3 = (unsigned int)(v3 + 1);
          }
          while ( (unsigned int)v3 < v1 );
        }
      }
      while ( v2 < v1 );
      for ( i = 0; (unsigned int)i < v1; i = (unsigned int)(i + 1) )
      {
        v9 = 48 * i;
        BytesInUnicodeString = 0;
        v10 = *(const WCHAR **)&bufptr[48 * i + 40];
        if ( v10 )
        {
          NetbiosDomain = NlFindNetbiosDomain(v10, 0);
          v12 = NetbiosDomain;
          if ( NetbiosDomain )
          {
            v13 = *((_DWORD *)NetbiosDomain + 82);
            v14 = *(_DWORD *)&bufptr[v9 + 24];
            v15 = &bufptr[v9];
            if ( (v14 != v13 || memcmp_0(*((const void **)v15 + 2), (char *)v12 + 312, v13))
              && RtlOemToUnicodeN(UnicodeString, 0x1Eu, &BytesInUnicodeString, *((PCCH *)v15 + 2), v14) >= 0 )
            {
              v16 = BytesInUnicodeString & 0xFFFFFFFE;
              if ( v16 >= 0x20 )
                goto LABEL_35;
              *(WCHAR *)((char *)UnicodeString + v16) = 0;
              NlPrintDomRoutine(
                0x100u,
                v12,
                L"NlBrowserSyncHostedDomains: hosted computer name mismatch (SMB server): %ws %ws.\n",
                UnicodeString,
                *((_QWORD *)v12 + 33));
              if ( NetServerComputerNameDel(0, UnicodeString) )
                NlPrintDomRoutine(
                  0x100u,
                  v12,
                  L"NlBrowserSyncHostedDomains: can't NetServerComputerNameDel: %ws.\n",
                  UnicodeString);
              if ( NlServerComputerNameAdd((unsigned __int16 *)v12 + 36, *((unsigned __int16 **)v12 + 33)) )
                NlPrintDomRoutine(
                  0x100u,
                  v12,
                  L"NlBrowserSyncHostedDomains: can't NetServerComputerNameAdd: %ws.\n",
                  *((_QWORD *)v12 + 33));
            }
            NlDereferenceDomain(v12);
          }
          else
          {
            NlPrintRoutine(
              0x100u,
              L"%ws: NlBrowserSyncHostedDomains: SMB server had a hosted domain we didn't (deleting)\n",
              *(_QWORD *)&bufptr[v9 + 40]);
            v17 = RtlOemToUnicodeN(
                    UnicodeString,
                    0x1Eu,
                    &BytesInUnicodeString,
                    *(PCCH *)&bufptr[v9 + 16],
                    *(_DWORD *)&bufptr[v9 + 24]);
            if ( v17 >= 0 )
            {
              v18 = BytesInUnicodeString & 0xFFFFFFFE;
              if ( v18 >= 0x20 )
LABEL_35:
                _report_rangecheckfailure();
              *(WCHAR *)((char *)UnicodeString + v18) = 0;
            }
            else
            {
              NlPrintRoutine(
                0x100u,
                L"%ws: NlBrowserSyncHostedDomains: can't RtlOemToUnicode: %lx.\n",
                *(_QWORD *)&bufptr[v9 + 40],
                (unsigned int)v17);
            }
          }
          v1 = entriesread;
        }
      }
      NetApiBufferFree(bufptr);
    }
  }
  else
  {
    NlPrintRoutine(0x100u, L"NlBrowserSyncEnulatedDomains: Cannot NetServerTransportEnum %ld\n", v0);
  }
}

```

## disassembly

```asm
0x18003aaa0  push    rbp
0x18003aaa2  push    rbx
0x18003aaa3  push    rsi
0x18003aaa4  push    rdi
0x18003aaa5  push    r12
0x18003aaa7  push    r14
0x18003aaa9  push    r15
0x18003aaab  mov     rbp, rsp
0x18003aaae  sub     rsp, 80h
0x18003aab5  mov     rax, cs:__security_cookie
0x18003aabc  xor     rax, rsp
0x18003aabf  mov     [rbp+var_8], rax
0x18003aac3  lea     rax, [rbp+var_30]
0x18003aac7  mov     [rsp+80h+resume_handle], 0; resume_handle
0x18003aad0  mov     [rsp+80h+totalentries], rax; totalentries
0x18003aad5  lea     r8, [rbp+bufptr]; bufptr
0x18003aad9  lea     rax, [rbp+var_40]
0x18003aadd  mov     [rbp+var_40], 0
0x18003aae4  or      r9d, 0FFFFFFFFh; prefmaxlen
0x18003aae8  mov     [rsp+80h+entriesread], rax; entriesread
0x18003aaed  mov     edx, 1; level
0x18003aaf2  mov     [rbp+var_30], 0
0x18003aaf9  xor     ecx, ecx; servername
0x18003aafb  mov     [rbp+bufptr], 0
0x18003ab03  call    cs:__imp_NetServerTransportEnum
0x18003ab09  test    eax, eax
0x18003ab0b  jz      short loc_18003AB2D
0x18003ab0d  cmp     eax, 0EAh
0x18003ab12  jz      short loc_18003AB2D
0x18003ab14  mov     r8d, eax
0x18003ab17  lea     rdx, aNlbrowsersynce; "NlBrowserSyncEnulatedDomains: Cannot Ne"...
0x18003ab1e  mov     ecx, 100h; unsigned int
0x18003ab23  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003ab28  jmp     loc_18003AD7D
0x18003ab2d  mov     ebx, [rbp+var_40]
0x18003ab30  test    ebx, ebx
0x18003ab32  jz      loc_18003AD7D
0x18003ab38  xor     r15d, r15d
0x18003ab3b  test    ebx, ebx
0x18003ab3d  jz      loc_18003ABC3
0x18003ab43  lea     edi, [r15+1]
0x18003ab47  mov     eax, r15d
0x18003ab4a  mov     r15d, edi
0x18003ab4d  cmp     edi, ebx
0x18003ab4f  jnb     short loc_18003ABBE
0x18003ab51  lea     r12, [rax+rax*2]
0x18003ab55  add     r12, r12
0x18003ab58  mov     rsi, [rbp+bufptr]
0x18003ab5c  cmp     qword ptr [rsi+r12*8+28h], 0
0x18003ab62  jz      short loc_18003ABB8
0x18003ab64  mov     eax, [rsi+r12*8+18h]
0x18003ab69  lea     r14, [rdi+rdi*2]
0x18003ab6d  add     r14, r14
0x18003ab70  cmp     eax, [rsi+r14*8+18h]
0x18003ab75  jnz     short loc_18003ABB8
0x18003ab77  mov     rdx, [rsi+r14*8+10h]; Buf2
0x18003ab7c  mov     r8d, eax; Size
0x18003ab7f  mov     rcx, [rsi+r12*8+10h]; Buf1
0x18003ab84  call    memcmp_0
0x18003ab89  test    eax, eax
0x18003ab8b  jnz     short loc_18003ABB8
0x18003ab8d  mov     rdx, [rsi+r14*8+28h]
0x18003ab92  lea     r8d, [rax+6]
0x18003ab96  mov     rcx, [rsi+r12*8+28h]
0x18003ab9b  xor     r9d, r9d
0x18003ab9e  call    cs:__imp_NetpwNameCompare
0x18003aba4  test    eax, eax
0x18003aba6  jnz     short loc_18003ABB5
0x18003aba8  mov     rax, [rbp+bufptr]
0x18003abac  mov     qword ptr [rax+r14*8+28h], 0
0x18003abb5  mov     ebx, [rbp+var_40]
0x18003abb8  inc     edi
0x18003abba  cmp     edi, ebx
0x18003abbc  jb      short loc_18003AB58
0x18003abbe  cmp     r15d, ebx
0x18003abc1  jb      short loc_18003AB43
0x18003abc3  xor     r14d, r14d
0x18003abc6  mov     esi, 100h
0x18003abcb  lea     r12d, [r14+1Eh]
0x18003abcf  cmp     r14d, ebx
0x18003abd2  jnb     loc_18003AD73
0x18003abd8  mov     rax, [rbp+bufptr]
0x18003abdc  lea     rdi, [r14+r14*2]
0x18003abe0  shl     rdi, 4
0x18003abe4  mov     [rbp+BytesInUnicodeString], 0
0x18003abeb  mov     rcx, [rdi+rax+28h]; SourceString
0x18003abf0  test    rcx, rcx
0x18003abf3  jz      loc_18003AD65
0x18003abf9  xor     edx, edx; unsigned __int8
0x18003abfb  call    ?NlFindNetbiosDomain@@YAPEAU_DOMAIN_INFO@@PEBGE@Z; NlFindNetbiosDomain(ushort const *,uchar)
0x18003ac00  mov     rbx, rax
0x18003ac03  test    rax, rax
0x18003ac06  jz      loc_18003ACF4
0x18003ac0c  mov     rcx, [rbp+bufptr]
0x18003ac10  mov     eax, [rax+148h]
0x18003ac16  mov     r15d, [rdi+rcx+18h]
0x18003ac1b  add     rdi, rcx
0x18003ac1e  cmp     r15d, eax
0x18003ac21  jnz     short loc_18003AC3E
0x18003ac23  mov     rcx, [rdi+10h]; Buf1
0x18003ac27  lea     rdx, [rbx+138h]; Buf2
0x18003ac2e  mov     r8d, eax; Size
0x18003ac31  call    memcmp_0
0x18003ac36  test    eax, eax
0x18003ac38  jz      loc_18003ACEA
0x18003ac3e  mov     r9, [rdi+10h]; OemString
0x18003ac42  lea     r8, [rbp+BytesInUnicodeString]; BytesInUnicodeString
0x18003ac46  mov     edx, r12d; MaxBytesInUnicodeString
0x18003ac49  mov     dword ptr [rsp+80h+entriesread], r15d; BytesInOemString
0x18003ac4e  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18003ac52  call    cs:__imp_RtlOemToUnicodeN
0x18003ac58  test    eax, eax
0x18003ac5a  js      loc_18003ACEA
0x18003ac60  mov     ecx, [rbp+BytesInUnicodeString]
0x18003ac63  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18003ac67  cmp     rcx, 20h ; ' '
0x18003ac6b  jnb     loc_18003AD6D
0x18003ac71  xor     eax, eax
0x18003ac73  lea     r9, [rbp+UnicodeString]
0x18003ac77  mov     [rbp+rcx+UnicodeString], ax
0x18003ac7c  lea     r8, aNlbrowsersynch_0; "NlBrowserSyncHostedDomains: hosted comp"...
0x18003ac83  mov     rax, [rbx+108h]
0x18003ac8a  mov     rdx, rbx; struct _DOMAIN_INFO *
0x18003ac8d  mov     ecx, esi; unsigned int
0x18003ac8f  mov     [rsp+80h+entriesread], rax
0x18003ac94  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18003ac99  lea     rdx, [rbp+UnicodeString]; EmulatedServerName
0x18003ac9d  xor     ecx, ecx; ServerName
0x18003ac9f  call    cs:__imp_NetServerComputerNameDel
0x18003aca5  test    eax, eax
0x18003aca7  jz      short loc_18003ACBE
0x18003aca9  lea     r9, [rbp+UnicodeString]
0x18003acad  mov     rdx, rbx; struct _DOMAIN_INFO *
0x18003acb0  lea     r8, aNlbrowsersynch; "NlBrowserSyncHostedDomains: can't NetSe"...
0x18003acb7  mov     ecx, esi; unsigned int
0x18003acb9  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18003acbe  mov     rdx, [rbx+108h]; unsigned __int16 *
0x18003acc5  lea     rcx, [rbx+48h]; unsigned __int16 *
0x18003acc9  call    ?NlServerComputerNameAdd@@YAKPEAG0@Z; NlServerComputerNameAdd(ushort *,ushort *)
0x18003acce  test    eax, eax
0x18003acd0  jz      short loc_18003ACEA
0x18003acd2  mov     r9, [rbx+108h]
0x18003acd9  lea     r8, aNlbrowsersynch_1; "NlBrowserSyncHostedDomains: can't NetSe"...
0x18003ace0  mov     rdx, rbx; struct _DOMAIN_INFO *
0x18003ace3  mov     ecx, esi; unsigned int
0x18003ace5  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18003acea  mov     rcx, rbx; struct _DOMAIN_INFO *
0x18003aced  call    ?NlDereferenceDomain@@YAXPEAU_DOMAIN_INFO@@@Z; NlDereferenceDomain(_DOMAIN_INFO *)
0x18003acf2  jmp     short loc_18003AD62
0x18003acf4  mov     r8, [rbp+bufptr]
0x18003acf8  lea     rdx, aWsNlbrowsersyn_0; "%ws: NlBrowserSyncHostedDomains: SMB se"...
0x18003acff  mov     ecx, esi; unsigned int
0x18003ad01  mov     r8, [rdi+r8+28h]
0x18003ad06  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003ad0b  mov     r9, [rbp+bufptr]
0x18003ad0f  lea     r8, [rbp+BytesInUnicodeString]; BytesInUnicodeString
0x18003ad13  mov     edx, r12d; MaxBytesInUnicodeString
0x18003ad16  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18003ad1a  mov     eax, [rdi+r9+18h]
0x18003ad1f  mov     r9, [rdi+r9+10h]; OemString
0x18003ad24  mov     dword ptr [rsp+80h+entriesread], eax; BytesInOemString
0x18003ad28  call    cs:__imp_RtlOemToUnicodeN
0x18003ad2e  test    eax, eax
0x18003ad30  jns     short loc_18003AD4E
0x18003ad32  mov     r8, [rbp+bufptr]
0x18003ad36  lea     rdx, aWsNlbrowsersyn; "%ws: NlBrowserSyncHostedDomains: can't "...
0x18003ad3d  mov     r9d, eax
0x18003ad40  mov     ecx, esi; unsigned int
0x18003ad42  mov     r8, [rdi+r8+28h]
0x18003ad47  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003ad4c  jmp     short loc_18003AD62
0x18003ad4e  mov     ecx, [rbp+BytesInUnicodeString]
0x18003ad51  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18003ad55  cmp     rcx, 20h ; ' '
0x18003ad59  jnb     short loc_18003AD6D
0x18003ad5b  xor     eax, eax
0x18003ad5d  mov     [rbp+rcx+UnicodeString], ax
0x18003ad62  mov     ebx, [rbp+var_40]
0x18003ad65  inc     r14d
0x18003ad68  jmp     loc_18003ABCF
0x18003ad6d  call    __report_rangecheckfailure
0x18003ad73  mov     rcx, [rbp+bufptr]; Buffer
0x18003ad77  call    cs:__imp_NetApiBufferFree
0x18003ad7d  mov     rcx, [rbp+var_8]
0x18003ad81  xor     rcx, rsp; StackCookie
0x18003ad84  call    __security_check_cookie
0x18003ad89  add     rsp, 80h
0x18003ad90  pop     r15
0x18003ad92  pop     r14
0x18003ad94  pop     r12
0x18003ad96  pop     rdi
0x18003ad97  pop     rsi
0x18003ad98  pop     rbx
0x18003ad99  pop     rbp
0x18003ad9a  retn
```
