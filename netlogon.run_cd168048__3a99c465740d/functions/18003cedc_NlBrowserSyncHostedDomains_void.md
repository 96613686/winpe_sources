# NlBrowserSyncHostedDomains(void)

- ea: `0x18003cedc`
- end: `0x18003d200`
- name: `?NlBrowserSyncHostedDomains@@YAXXZ`
- size: `804`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180075514`

## callees

- `0x180007518`
- `0x18000c440`
- `0x18000e910`
- `0x18000ed00`
- `0x1800267ec`
- `0x180027350`
- `0x18003cedc`
- `0x18003da54`
- `0x1800901f8`

## import_xrefs

- `ntdll!RtlOemToUnicodeN` at `0x18003d09e`
- `ntdll!RtlOemToUnicodeN` at `0x18003d180`
- `ntdll!RtlOemToUnicodeN` at `0x18003d09e`
- `ntdll!RtlOemToUnicodeN` at `0x18003d180`
- `netutils!NetApiBufferFree` at `0x18003d1d5`
- `netutils!NetApiBufferFree` at `0x18003d1d5`
- `netutils!NetpwNameCompare` at `0x18003cfe0`
- `netutils!NetpwNameCompare` at `0x18003cfe0`
- `srvcli!NetServerTransportEnum` at `0x18003cf3f`
- `srvcli!NetServerTransportEnum` at `0x18003cf3f`
- `srvcli!NetServerComputerNameDel` at `0x18003d0f1`
- `srvcli!NetServerComputerNameDel` at `0x18003d0f1`

## string_xrefs

- `0x18003d0ce`: `NlBrowserSyncHostedDomains: hosted computer name mismatch (SMB server): %ws %ws.\n`
- `0x18003d108`: `NlBrowserSyncHostedDomains: can't NetServerComputerNameDel: %ws.\n`
- `0x18003d131`: `NlBrowserSyncHostedDomains: can't NetServerComputerNameAdd: %ws.\n`

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
  __int64 v16; // rdx
  unsigned __int64 v17; // rcx
  NTSTATUS v18; // eax
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
              v17 = BytesInUnicodeString & 0xFFFFFFFE;
              if ( v17 >= 0x20 )
                goto LABEL_35;
              *(WCHAR *)((char *)UnicodeString + v17) = 0;
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
            v18 = RtlOemToUnicodeN(
                    UnicodeString,
                    0x1Eu,
                    &BytesInUnicodeString,
                    *(PCCH *)&bufptr[v9 + 16],
                    *(_DWORD *)&bufptr[v9 + 24]);
            if ( v18 >= 0 )
            {
              v17 = BytesInUnicodeString & 0xFFFFFFFE;
              if ( v17 >= 0x20 )
LABEL_35:
                _report_rangecheckfailure(v17, v16);
              *(WCHAR *)((char *)UnicodeString + v17) = 0;
            }
            else
            {
              NlPrintRoutine(
                0x100u,
                L"%ws: NlBrowserSyncHostedDomains: can't RtlOemToUnicode: %lx.\n",
                *(_QWORD *)&bufptr[v9 + 40],
                (unsigned int)v18);
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
0x18003cedc  push    rbp
0x18003cede  push    rbx
0x18003cedf  push    rsi
0x18003cee0  push    rdi
0x18003cee1  push    r12
0x18003cee3  push    r14
0x18003cee5  push    r15
0x18003cee7  mov     rbp, rsp
0x18003ceea  sub     rsp, 80h
0x18003cef1  mov     rax, cs:__security_cookie
0x18003cef8  xor     rax, rsp
0x18003cefb  mov     [rbp+var_8], rax
0x18003ceff  lea     rax, [rbp+var_30]
0x18003cf03  mov     [rsp+80h+resume_handle], 0; resume_handle
0x18003cf0c  mov     [rsp+80h+totalentries], rax; totalentries
0x18003cf11  lea     r8, [rbp+bufptr]; bufptr
0x18003cf15  lea     rax, [rbp+var_40]
0x18003cf19  mov     [rbp+var_40], 0
0x18003cf20  or      r9d, 0FFFFFFFFh; prefmaxlen
0x18003cf24  mov     [rsp+80h+entriesread], rax; entriesread
0x18003cf29  mov     edx, 1; level
0x18003cf2e  mov     [rbp+var_30], 0
0x18003cf35  xor     ecx, ecx; servername
0x18003cf37  mov     [rbp+bufptr], 0
0x18003cf3f  call    cs:__imp_NetServerTransportEnum
0x18003cf46  nop     dword ptr [rax+rax+00h]
0x18003cf4b  test    eax, eax
0x18003cf4d  jz      short loc_18003CF6F
0x18003cf4f  cmp     eax, 0EAh
0x18003cf54  jz      short loc_18003CF6F
0x18003cf56  mov     r8d, eax
0x18003cf59  lea     rdx, aNlbrowsersynce; "NlBrowserSyncEnulatedDomains: Cannot Ne"...
0x18003cf60  mov     ecx, 100h; unsigned int
0x18003cf65  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003cf6a  jmp     loc_18003D1E1
0x18003cf6f  mov     ebx, [rbp+var_40]
0x18003cf72  test    ebx, ebx
0x18003cf74  jz      loc_18003D1E1
0x18003cf7a  xor     r15d, r15d
0x18003cf7d  test    ebx, ebx
0x18003cf7f  jz      loc_18003D00F
0x18003cf85  lea     edi, [r15+1]
0x18003cf89  mov     eax, r15d
0x18003cf8c  mov     r15d, edi
0x18003cf8f  cmp     edi, ebx
0x18003cf91  jnb     short loc_18003D006
0x18003cf93  lea     r12, [rax+rax*2]
0x18003cf97  add     r12, r12
0x18003cf9a  mov     rsi, [rbp+bufptr]
0x18003cf9e  cmp     qword ptr [rsi+r12*8+28h], 0
0x18003cfa4  jz      short loc_18003D000
0x18003cfa6  mov     eax, [rsi+r12*8+18h]
0x18003cfab  lea     r14, [rdi+rdi*2]
0x18003cfaf  add     r14, r14
0x18003cfb2  cmp     eax, [rsi+r14*8+18h]
0x18003cfb7  jnz     short loc_18003D000
0x18003cfb9  mov     rdx, [rsi+r14*8+10h]; Buf2
0x18003cfbe  mov     r8d, eax; Size
0x18003cfc1  mov     rcx, [rsi+r12*8+10h]; Buf1
0x18003cfc6  call    memcmp_0
0x18003cfcb  test    eax, eax
0x18003cfcd  jnz     short loc_18003D000
0x18003cfcf  mov     rdx, [rsi+r14*8+28h]
0x18003cfd4  lea     r8d, [rax+6]
0x18003cfd8  mov     rcx, [rsi+r12*8+28h]
0x18003cfdd  xor     r9d, r9d
0x18003cfe0  call    cs:__imp_NetpwNameCompare
0x18003cfe7  nop     dword ptr [rax+rax+00h]
0x18003cfec  test    eax, eax
0x18003cfee  jnz     short loc_18003CFFD
0x18003cff0  mov     rax, [rbp+bufptr]
0x18003cff4  mov     qword ptr [rax+r14*8+28h], 0
0x18003cffd  mov     ebx, [rbp+var_40]
0x18003d000  inc     edi
0x18003d002  cmp     edi, ebx
0x18003d004  jb      short loc_18003CF9A
0x18003d006  cmp     r15d, ebx
0x18003d009  jb      loc_18003CF85
0x18003d00f  xor     r14d, r14d
0x18003d012  mov     esi, 100h
0x18003d017  lea     r12d, [r14+1Eh]
0x18003d01b  cmp     r14d, ebx
0x18003d01e  jnb     loc_18003D1D1
0x18003d024  mov     rax, [rbp+bufptr]
0x18003d028  lea     rdi, [r14+r14*2]
0x18003d02c  shl     rdi, 4
0x18003d030  mov     [rbp+BytesInUnicodeString], 0
0x18003d037  mov     rcx, [rdi+rax+28h]; SourceString
0x18003d03c  test    rcx, rcx
0x18003d03f  jz      loc_18003D1C3
0x18003d045  xor     edx, edx; unsigned __int8
0x18003d047  call    ?NlFindNetbiosDomain@@YAPEAU_DOMAIN_INFO@@PEBGE@Z; NlFindNetbiosDomain(ushort const *,uchar)
0x18003d04c  mov     rbx, rax
0x18003d04f  test    rax, rax
0x18003d052  jz      loc_18003D14C
0x18003d058  mov     rcx, [rbp+bufptr]
0x18003d05c  mov     eax, [rax+148h]
0x18003d062  mov     r15d, [rdi+rcx+18h]
0x18003d067  add     rdi, rcx
0x18003d06a  cmp     r15d, eax
0x18003d06d  jnz     short loc_18003D08A
0x18003d06f  mov     rcx, [rdi+10h]; Buf1
0x18003d073  lea     rdx, [rbx+138h]; Buf2
0x18003d07a  mov     r8d, eax; Size
0x18003d07d  call    memcmp_0
0x18003d082  test    eax, eax
0x18003d084  jz      loc_18003D142
0x18003d08a  mov     r9, [rdi+10h]; OemString
0x18003d08e  lea     r8, [rbp+BytesInUnicodeString]; BytesInUnicodeString
0x18003d092  mov     edx, r12d; MaxBytesInUnicodeString
0x18003d095  mov     dword ptr [rsp+80h+entriesread], r15d; BytesInOemString
0x18003d09a  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18003d09e  call    cs:__imp_RtlOemToUnicodeN
0x18003d0a5  nop     dword ptr [rax+rax+00h]
0x18003d0aa  test    eax, eax
0x18003d0ac  js      loc_18003D142
0x18003d0b2  mov     ecx, [rbp+BytesInUnicodeString]
0x18003d0b5  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18003d0b9  cmp     rcx, 20h ; ' '
0x18003d0bd  jnb     loc_18003D1CB
0x18003d0c3  xor     eax, eax
0x18003d0c5  lea     r9, [rbp+UnicodeString]
0x18003d0c9  mov     [rbp+rcx+UnicodeString], ax
0x18003d0ce  lea     r8, aNlbrowsersynch_0; "NlBrowserSyncHostedDomains: hosted comp"...
0x18003d0d5  mov     rax, [rbx+108h]
0x18003d0dc  mov     rdx, rbx; struct _DOMAIN_INFO *
0x18003d0df  mov     ecx, esi; unsigned int
0x18003d0e1  mov     [rsp+80h+entriesread], rax
0x18003d0e6  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18003d0eb  lea     rdx, [rbp+UnicodeString]; EmulatedServerName
0x18003d0ef  xor     ecx, ecx; ServerName
0x18003d0f1  call    cs:__imp_NetServerComputerNameDel
0x18003d0f8  nop     dword ptr [rax+rax+00h]
0x18003d0fd  test    eax, eax
0x18003d0ff  jz      short loc_18003D116
0x18003d101  lea     r9, [rbp+UnicodeString]
0x18003d105  mov     rdx, rbx; struct _DOMAIN_INFO *
0x18003d108  lea     r8, aNlbrowsersynch; "NlBrowserSyncHostedDomains: can't NetSe"...
0x18003d10f  mov     ecx, esi; unsigned int
0x18003d111  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18003d116  mov     rdx, [rbx+108h]; unsigned __int16 *
0x18003d11d  lea     rcx, [rbx+48h]; unsigned __int16 *
0x18003d121  call    ?NlServerComputerNameAdd@@YAKPEAG0@Z; NlServerComputerNameAdd(ushort *,ushort *)
0x18003d126  test    eax, eax
0x18003d128  jz      short loc_18003D142
0x18003d12a  mov     r9, [rbx+108h]
0x18003d131  lea     r8, aNlbrowsersynch_1; "NlBrowserSyncHostedDomains: can't NetSe"...
0x18003d138  mov     rdx, rbx; struct _DOMAIN_INFO *
0x18003d13b  mov     ecx, esi; unsigned int
0x18003d13d  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18003d142  mov     rcx, rbx; struct _DOMAIN_INFO *
0x18003d145  call    ?NlDereferenceDomain@@YAXPEAU_DOMAIN_INFO@@@Z; NlDereferenceDomain(_DOMAIN_INFO *)
0x18003d14a  jmp     short loc_18003D1C0
0x18003d14c  mov     r8, [rbp+bufptr]
0x18003d150  lea     rdx, aWsNlbrowsersyn_0; "%ws: NlBrowserSyncHostedDomains: SMB se"...
0x18003d157  mov     ecx, esi; unsigned int
0x18003d159  mov     r8, [rdi+r8+28h]
0x18003d15e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003d163  mov     r9, [rbp+bufptr]
0x18003d167  lea     r8, [rbp+BytesInUnicodeString]; BytesInUnicodeString
0x18003d16b  mov     edx, r12d; MaxBytesInUnicodeString
0x18003d16e  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18003d172  mov     eax, [rdi+r9+18h]
0x18003d177  mov     r9, [rdi+r9+10h]; OemString
0x18003d17c  mov     dword ptr [rsp+80h+entriesread], eax; BytesInOemString
0x18003d180  call    cs:__imp_RtlOemToUnicodeN
0x18003d187  nop     dword ptr [rax+rax+00h]
0x18003d18c  test    eax, eax
0x18003d18e  jns     short loc_18003D1AC
0x18003d190  mov     r8, [rbp+bufptr]
0x18003d194  lea     rdx, aWsNlbrowsersyn; "%ws: NlBrowserSyncHostedDomains: can't "...
0x18003d19b  mov     r9d, eax
0x18003d19e  mov     ecx, esi; unsigned int
0x18003d1a0  mov     r8, [rdi+r8+28h]
0x18003d1a5  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003d1aa  jmp     short loc_18003D1C0
0x18003d1ac  mov     ecx, [rbp+BytesInUnicodeString]
0x18003d1af  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18003d1b3  cmp     rcx, 20h ; ' '
0x18003d1b7  jnb     short loc_18003D1CB
0x18003d1b9  xor     eax, eax
0x18003d1bb  mov     [rbp+rcx+UnicodeString], ax
0x18003d1c0  mov     ebx, [rbp+var_40]
0x18003d1c3  inc     r14d
0x18003d1c6  jmp     loc_18003D01B
0x18003d1cb  call    __report_rangecheckfailure
0x18003d1d1  mov     rcx, [rbp+bufptr]; Buffer
0x18003d1d5  call    cs:__imp_NetApiBufferFree
0x18003d1dc  nop     dword ptr [rax+rax+00h]
0x18003d1e1  mov     rcx, [rbp+var_8]
0x18003d1e5  xor     rcx, rsp; StackCookie
0x18003d1e8  call    __security_check_cookie
0x18003d1ed  add     rsp, 80h
0x18003d1f4  pop     r15
0x18003d1f6  pop     r14
0x18003d1f8  pop     r12
0x18003d1fa  pop     rdi
0x18003d1fb  pop     rsi
0x18003d1fc  pop     rbx
0x18003d1fd  pop     rbp
0x18003d1fe  retn
```
