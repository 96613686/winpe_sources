# DisplayValue(_METADATA_RECORD *,STRU *)

- ea: `0x18000ec98`
- end: `0x18000eeb1`
- name: `?DisplayValue@@YAJPEAU_METADATA_RECORD@@PEAVSTRU@@@Z`
- size: `537`
- prototype: `int(struct _METADATA_RECORD *, struct STRU *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000238c`

## callees

- `0x18000ea44`
- `0x18000eb50`
- `0x18000ebc0`
- `0x18000ec98`

## import_xrefs

- `ADVAPI32!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18000ed5d`
- `ADVAPI32!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18000ed5d`
- `KERNEL32!GetLastError` at `0x18000ed67`
- `KERNEL32!GetLastError` at `0x18000ed78`
- `KERNEL32!GetLastError` at `0x18000ed67`
- `KERNEL32!GetLastError` at `0x18000ed78`
- `KERNEL32!LocalFree` at `0x18000edb8`
- `KERNEL32!LocalFree` at `0x18000edb8`
- `IisRTL!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000ed9c`
- `IisRTL!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000ed9c`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000ee28`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000ee97`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000ee28`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000ee97`
- `IisRTL!?Resize@STRU@@QEAAJK@Z` at `0x18000ecd8`
- `IisRTL!?Resize@STRU@@QEAAJK@Z` at `0x18000ecd8`

## pseudocode

```c
int __fastcall DisplayValue(struct _METADATA_RECORD *a1, struct STRU *a2)
{
  DWORD dwMDDataLen; // edx
  int result; // eax
  unsigned __int8 *pbMDData; // rcx
  unsigned int v7; // edi
  signed int LastError; // eax
  DWORD dwMDDataType; // edi
  unsigned __int8 *v10; // rdx
  ULONG StringSecurityDescriptorLen; // [rsp+58h] [rbp+10h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+60h] [rbp+18h] BYREF

  if ( !a2 || !a1 )
    return -2147024809;
  if ( !a1->pbMDData )
    return STRU::Copy(a2, &byte_1800127D8);
  dwMDDataLen = a1->dwMDDataLen;
  if ( !dwMDDataLen )
    return STRU::Copy(a2, &byte_1800127D8);
  result = STRU::Resize(a2, 2 * dwMDDataLen);
  if ( result < 0 )
    return result;
  if ( a1->dwMDIdentifier != 3003
    && a1->dwMDIdentifier != 4010
    && a1->dwMDIdentifier != 5015
    && a1->dwMDIdentifier != 5502
    && a1->dwMDIdentifier != 7502
    && a1->dwMDIdentifier != 6021 )
  {
    if ( a1->dwMDIdentifier == 6027 )
    {
      pbMDData = a1->pbMDData;
      StringSecurityDescriptor = 0;
      StringSecurityDescriptorLen = 0;
      if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
             pbMDData,
             1u,
             0xFu,
             &StringSecurityDescriptor,
             &StringSecurityDescriptorLen) )
      {
        v7 = 0;
        if ( (int)STRU::Copy(a2, StringSecurityDescriptor, StringSecurityDescriptorLen) < 0 )
          v7 = -2147024882;
      }
      else if ( GetLastError() )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v7 = -2147467259;
      }
      if ( StringSecurityDescriptor )
        LocalFree(StringSecurityDescriptor);
      if ( !v7 )
        return 0;
      dwMDDataType = 3;
      goto LABEL_24;
    }
    dwMDDataType = a1->dwMDDataType;
    if ( dwMDDataType == 1 )
    {
      if ( a1->dwMDDataLen != 4 )
      {
LABEL_40:
        result = DisplayBinary(a1->pbMDData, a1->dwMDDataLen, a2);
LABEL_41:
        if ( result < 0 )
          return result;
        return 0;
      }
      result = DisplayDwordRadix(*(_DWORD *)a1->pbMDData, a2, 10);
LABEL_38:
      if ( result < 0 )
      {
LABEL_39:
        if ( dwMDDataType == 3 )
          goto LABEL_41;
        goto LABEL_40;
      }
      return 0;
    }
    if ( a1->dwMDDataType != 2 )
    {
      if ( a1->dwMDDataType == 3 )
        goto LABEL_24;
      if ( a1->dwMDDataType != 4 )
      {
        if ( a1->dwMDDataType == 5 )
        {
          result = DisplayMultiSz((unsigned __int16 *)a1->pbMDData, a1->dwMDDataLen, a2);
          goto LABEL_38;
        }
LABEL_24:
        result = DisplayBinary(a1->pbMDData, a1->dwMDDataLen, a2);
        goto LABEL_38;
      }
    }
    if ( a1->dwMDDataLen < 2 )
      goto LABEL_35;
    v10 = a1->pbMDData;
    if ( *(_WORD *)&v10[2 * ((unsigned __int64)a1->dwMDDataLen >> 1) - 2] )
      goto LABEL_35;
    result = STRU::Copy(a2, (const unsigned __int16 *)v10);
    if ( result < 0 )
      goto LABEL_39;
    if ( *((_DWORD *)a2 + 12) != ((unsigned __int64)a1->dwMDDataLen >> 1) - 1 )
    {
LABEL_35:
      result = -2147024809;
      goto LABEL_39;
    }
    return 0;
  }
  return STRU::Copy(a2, L"NOT AUDITED");
}

```

## disassembly

```asm
0x18000ec98  mov     [rsp+arg_0], rbx
0x18000ec9d  push    rbp
0x18000ec9e  push    rsi
0x18000ec9f  push    rdi
0x18000eca0  sub     rsp, 30h
0x18000eca4  xor     ebp, ebp
0x18000eca6  mov     rsi, rdx
0x18000eca9  mov     rbx, rcx
0x18000ecac  test    rdx, rdx
0x18000ecaf  jz      loc_18000EE9F
0x18000ecb5  test    rcx, rcx
0x18000ecb8  jz      loc_18000EE9F
0x18000ecbe  cmp     [rcx+18h], rbp
0x18000ecc2  jz      loc_18000EE8D
0x18000ecc8  mov     edx, [rcx+10h]
0x18000eccb  test    edx, edx
0x18000eccd  jz      loc_18000EE8D
0x18000ecd3  add     edx, edx
0x18000ecd5  mov     rcx, rsi
0x18000ecd8  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x18000ecde  test    eax, eax
0x18000ece0  js      loc_18000EEA4
0x18000ece6  cmp     dword ptr [rbx], 0BBBh
0x18000ecec  jz      loc_18000EE84
0x18000ecf2  cmp     dword ptr [rbx], 0FAAh
0x18000ecf8  jz      loc_18000EE84
0x18000ecfe  cmp     dword ptr [rbx], 1397h
0x18000ed04  jz      loc_18000EE84
0x18000ed0a  cmp     dword ptr [rbx], 157Eh
0x18000ed10  jz      loc_18000EE84
0x18000ed16  cmp     dword ptr [rbx], 1D4Eh
0x18000ed1c  jz      loc_18000EE84
0x18000ed22  cmp     dword ptr [rbx], 1785h
0x18000ed28  jz      loc_18000EE84
0x18000ed2e  cmp     dword ptr [rbx], 178Bh
0x18000ed34  jnz     loc_18000EDDF
0x18000ed3a  mov     rcx, [rbx+18h]; SecurityDescriptor
0x18000ed3e  lea     rax, [rsp+48h+arg_8]
0x18000ed43  lea     r9, [rsp+48h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18000ed48  mov     [rsp+48h+StringSecurityDescriptorLen], rax; StringSecurityDescriptorLen
0x18000ed4d  lea     edx, [rbp+1]; RequestedStringSDRevision
0x18000ed50  mov     [rsp+48h+StringSecurityDescriptor], rbp
0x18000ed55  lea     r8d, [rbp+0Fh]; SecurityInformation
0x18000ed59  mov     [rsp+48h+arg_8], ebp
0x18000ed5d  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18000ed63  test    eax, eax
0x18000ed65  jnz     short loc_18000ED8F
0x18000ed67  call    cs:__imp_GetLastError
0x18000ed6d  test    eax, eax
0x18000ed6f  jnz     short loc_18000ED78
0x18000ed71  mov     edi, 80004005h
0x18000ed76  jmp     short loc_18000EDAE
0x18000ed78  call    cs:__imp_GetLastError
0x18000ed7e  mov     edi, eax
0x18000ed80  test    eax, eax
0x18000ed82  jle     short loc_18000EDAE
0x18000ed84  movzx   edi, ax
0x18000ed87  or      edi, 80070000h
0x18000ed8d  jmp     short loc_18000EDAE
0x18000ed8f  mov     r8d, [rsp+48h+arg_8]
0x18000ed94  mov     rcx, rsi
0x18000ed97  mov     rdx, [rsp+48h+StringSecurityDescriptor]
0x18000ed9c  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18000eda2  mov     edi, ebp
0x18000eda4  mov     ecx, 8007000Eh
0x18000eda9  test    eax, eax
0x18000edab  cmovs   edi, ecx
0x18000edae  mov     rcx, [rsp+48h+StringSecurityDescriptor]; hMem
0x18000edb3  test    rcx, rcx
0x18000edb6  jz      short loc_18000EDBE
0x18000edb8  call    cs:__imp_LocalFree
0x18000edbe  test    edi, edi
0x18000edc0  jz      loc_18000EE80
0x18000edc6  mov     edi, 3
0x18000edcb  mov     edx, [rbx+10h]; unsigned int
0x18000edce  mov     r8, rsi; struct STRU *
0x18000edd1  mov     rcx, [rbx+18h]; unsigned __int8 *
0x18000edd5  call    ?DisplayBinary@@YAJPEAEKPEAVSTRU@@@Z; DisplayBinary(uchar *,ulong,STRU *)
0x18000edda  jmp     loc_18000EE64
0x18000eddf  mov     edi, [rbx+0Ch]
0x18000ede2  mov     eax, edi
0x18000ede4  sub     eax, 1
0x18000ede7  jz      short loc_18000EE4A
0x18000ede9  sub     eax, 1
0x18000edec  jz      short loc_18000EE0E
0x18000edee  sub     eax, 1
0x18000edf1  jz      short loc_18000EDCB
0x18000edf3  sub     eax, 1
0x18000edf6  jz      short loc_18000EE0E
0x18000edf8  cmp     eax, 1
0x18000edfb  jnz     short loc_18000EDCB
0x18000edfd  mov     edx, [rbx+10h]; unsigned int
0x18000ee00  mov     r8, rsi; struct STRU *
0x18000ee03  mov     rcx, [rbx+18h]; unsigned __int16 *
0x18000ee07  call    ?DisplayMultiSz@@YAJPEAGKPEAVSTRU@@@Z; DisplayMultiSz(ushort *,ulong,STRU *)
0x18000ee0c  jmp     short loc_18000EE64
0x18000ee0e  cmp     dword ptr [rbx+10h], 2
0x18000ee12  jb      short loc_18000EE43
0x18000ee14  mov     eax, [rbx+10h]
0x18000ee17  mov     rdx, [rbx+18h]
0x18000ee1b  shr     rax, 1
0x18000ee1e  cmp     [rdx+rax*2-2], bp
0x18000ee23  jnz     short loc_18000EE43
0x18000ee25  mov     rcx, rsi
0x18000ee28  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000ee2e  test    eax, eax
0x18000ee30  js      short loc_18000EE68
0x18000ee32  mov     ecx, [rbx+10h]
0x18000ee35  mov     eax, [rsi+30h]
0x18000ee38  shr     rcx, 1
0x18000ee3b  dec     rcx
0x18000ee3e  cmp     rax, rcx
0x18000ee41  jz      short loc_18000EE80
0x18000ee43  mov     eax, 80070057h
0x18000ee48  jmp     short loc_18000EE68
0x18000ee4a  cmp     dword ptr [rbx+10h], 4
0x18000ee4e  jnz     short loc_18000EE6D
0x18000ee50  mov     rcx, [rbx+18h]
0x18000ee54  mov     r8d, 0Ah; int
0x18000ee5a  mov     rdx, rsi; struct STRU *
0x18000ee5d  mov     ecx, [rcx]; unsigned int
0x18000ee5f  call    ?DisplayDwordRadix@@YAJKPEAVSTRU@@H@Z; DisplayDwordRadix(ulong,STRU *,int)
0x18000ee64  test    eax, eax
0x18000ee66  jns     short loc_18000EE80
0x18000ee68  cmp     edi, 3
0x18000ee6b  jz      short loc_18000EE7C
0x18000ee6d  mov     edx, [rbx+10h]; unsigned int
0x18000ee70  mov     r8, rsi; struct STRU *
0x18000ee73  mov     rcx, [rbx+18h]; unsigned __int8 *
0x18000ee77  call    ?DisplayBinary@@YAJPEAEKPEAVSTRU@@@Z; DisplayBinary(uchar *,ulong,STRU *)
0x18000ee7c  test    eax, eax
0x18000ee7e  js      short loc_18000EEA4
0x18000ee80  mov     eax, ebp
0x18000ee82  jmp     short loc_18000EEA4
0x18000ee84  lea     rdx, aNotAudited; "NOT AUDITED"
0x18000ee8b  jmp     short loc_18000EE94
0x18000ee8d  lea     rdx, byte_1800127D8
0x18000ee94  mov     rcx, rsi
0x18000ee97  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000ee9d  jmp     short loc_18000EEA4
0x18000ee9f  mov     eax, 80070057h
0x18000eea4  mov     rbx, [rsp+48h+arg_0]
0x18000eea9  add     rsp, 30h
0x18000eead  pop     rdi
0x18000eeae  pop     rsi
0x18000eeaf  pop     rbp
0x18000eeb0  retn
```
