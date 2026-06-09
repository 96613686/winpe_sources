# _GetUserDnsDomainName(ushort const *,void * const,ushort * *)

- ea: `0x1800060a8`
- end: `0x18000619e`
- name: `?_GetUserDnsDomainName@@YAJPEBGQEAXPEAPEAG@Z`
- size: `246`
- prototype: `__int64 __fastcall(LPCWCH lpString1, PSID pSid, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180006de0`

## callees

- `0x180005b60`
- `0x1800060a8`
- `0x180006690`
- `0x18000fa10`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180006103`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180006103`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180006116`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000613f`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000614f`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180006116`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000613f`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000614f`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800060e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800060e3`

## pseudocode

```c
__int64 __fastcall _GetUserDnsDomainName(LPCWCH lpString1, PSID pSid, unsigned __int16 **a3)
{
  __int64 result; // rax
  unsigned int v7; // ebx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-58h]
  DWORD nSize; // [rsp+30h] [rbp-48h] BYREF
  WCHAR Buffer[16]; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *a3 = 0;
  nSize = 16;
  if ( GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize)
    && CompareStringOrdinal(lpString1, -1, Buffer, -1, 1) == 2
    || IsWellKnownSid(pSid, WinLocalSystemSid)
    || IsWellKnownSid(pSid, WinLocalServiceSid)
    || IsWellKnownSid(pSid, WinNetworkServiceSid) )
  {
    return 0;
  }
  result = GetUserNameAndDomain(NameDnsDomain, 0, a3);
  v7 = result;
  if ( (_DWORD)result != -2147023684 && (_DWORD)result != -2147023564 && (_DWORD)result != -2147023541 )
  {
    if ( (int)result < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20C,
        (unsigned int)"minio\\profapi\\env.cpp",
        (const char *)(unsigned int)result,
        bIgnoreCase);
      return v7;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800060a8  push    rbx
0x1800060aa  push    rsi
0x1800060ab  push    rdi
0x1800060ac  sub     rsp, 60h
0x1800060b0  mov     rax, cs:__security_cookie
0x1800060b7  xor     rax, rsp
0x1800060ba  mov     [rsp+78h+var_20], rax
0x1800060bf  mov     rdi, r8
0x1800060c2  mov     qword ptr [r8], 0
0x1800060c9  mov     rbx, rdx
0x1800060cc  mov     [rsp+78h+nSize], 10h
0x1800060d4  mov     rsi, rcx
0x1800060d7  lea     r8, [rsp+78h+nSize]; nSize
0x1800060dc  lea     rdx, [rsp+78h+Buffer]; lpBuffer
0x1800060e1  xor     ecx, ecx; NameType
0x1800060e3  call    cs:__imp_GetComputerNameExW
0x1800060e9  test    eax, eax
0x1800060eb  jz      short loc_18000610E
0x1800060ed  or      edx, 0FFFFFFFFh; cchCount1
0x1800060f0  mov     [rsp+78h+bIgnoreCase], 1; int
0x1800060f8  mov     r9d, edx; cchCount2
0x1800060fb  lea     r8, [rsp+78h+Buffer]; lpString2
0x180006100  mov     rcx, rsi; lpString1
0x180006103  call    cs:__imp_CompareStringOrdinal
0x180006109  cmp     eax, 2
0x18000610c  jz      short loc_180006120
0x18000610e  mov     edx, 16h; WellKnownSidType
0x180006113  mov     rcx, rbx; pSid
0x180006116  call    cs:__imp_IsWellKnownSid
0x18000611c  test    eax, eax
0x18000611e  jz      short loc_180006137
0x180006120  xor     eax, eax
0x180006122  mov     rcx, [rsp+78h+var_20]
0x180006127  xor     rcx, rsp; StackCookie
0x18000612a  call    __security_check_cookie
0x18000612f  add     rsp, 60h
0x180006133  pop     rdi
0x180006134  pop     rsi
0x180006135  pop     rbx
0x180006136  retn
0x180006137  mov     edx, 17h; WellKnownSidType
0x18000613c  mov     rcx, rbx; pSid
0x18000613f  call    cs:__imp_IsWellKnownSid
0x180006145  test    eax, eax
0x180006147  jnz     short loc_180006120
0x180006149  lea     edx, [rax+18h]; WellKnownSidType
0x18000614c  mov     rcx, rbx; pSid
0x18000614f  call    cs:__imp_IsWellKnownSid
0x180006155  test    eax, eax
0x180006157  jnz     short loc_180006120
0x180006159  mov     r8, rdi; unsigned __int16 **
0x18000615c  lea     ecx, [rax+0Ch]; NameFormat
0x18000615f  xor     edx, edx; unsigned __int16 **
0x180006161  call    ?GetUserNameAndDomain@@YAJW4EXTENDED_NAME_FORMAT@@PEAPEAG1@Z; GetUserNameAndDomain(EXTENDED_NAME_FORMAT,ushort * *,ushort * *)
0x180006166  mov     ebx, eax
0x180006168  cmp     eax, 800704BCh
0x18000616d  jz      short loc_180006122
0x18000616f  cmp     eax, 80070534h
0x180006174  jz      short loc_180006122
0x180006176  cmp     eax, 8007054Bh
0x18000617b  jz      short loc_180006122
0x18000617d  test    eax, eax
0x18000617f  jns     short loc_180006120
0x180006181  mov     rcx, [rsp+78h]; this
0x180006186  lea     r8, aMinioProfapiEn; "minio\\profapi\\env.cpp"
0x18000618d  mov     r9d, eax; char *
0x180006190  mov     edx, 20Ch; void *
0x180006195  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000619a  mov     eax, ebx
0x18000619c  jmp     short loc_180006122
```
