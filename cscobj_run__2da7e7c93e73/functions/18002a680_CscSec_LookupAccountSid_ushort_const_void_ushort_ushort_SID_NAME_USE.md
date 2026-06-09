# CscSec_LookupAccountSid(ushort const *,void *,ushort * *,ushort * *,_SID_NAME_USE *)

- ea: `0x18002a680`
- end: `0x18002a7b6`
- name: `?CscSec_LookupAccountSid@@YAJPEBGPEAXPEAPEAG2PEAW4_SID_NAME_USE@@@Z`
- size: `310`
- prototype: `int(const unsigned __int16 *, void *, unsigned __int16 **, unsigned __int16 **, enum _SID_NAME_USE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015974`

## callees

- `0x1800084e0`
- `0x180009864`
- `0x1800146d4`
- `0x18002a680`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a6f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a6f2`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18002a6de`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18002a770`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18002a6de`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18002a770`

## pseudocode

```c
__int64 __fastcall CscSec_LookupAccountSid(
        const unsigned __int16 *a1,
        void *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4,
        PSID_NAME_USE a5)
{
  enum _SID_NAME_USE *v5; // rdi
  int Error; // ebx
  signed int LastError; // eax
  void *v11; // rdx
  unsigned __int16 *v12; // rsi
  unsigned __int16 *v13; // rdi
  void *v14; // rdx
  UstVarLib *v15; // rcx
  enum _SID_NAME_USE *peUse; // [rsp+30h] [rbp-20h]
  enum _SID_NAME_USE *peUsea; // [rsp+30h] [rbp-20h]
  LPWSTR ReferencedDomainName[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD cchReferencedDomainName; // [rsp+90h] [rbp+40h] BYREF
  int v21; // [rsp+94h] [rbp+44h]
  DWORD cchName; // [rsp+A0h] [rbp+50h] BYREF
  LPWSTR Name; // [rsp+A8h] [rbp+58h] BYREF

  v21 = HIDWORD(a1);
  v5 = a5;
  peUse = a5;
  *a3 = 0;
  *a4 = 0;
  cchName = 0;
  cchReferencedDomainName = 0;
  if ( LookupAccountSidW(0, a2, 0, &cchName, 0, &cchReferencedDomainName, peUse) )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    LastError = GetLastError();
    Error = LastError;
    if ( LastError == 122 )
    {
      Name = 0;
      Error = CscUtil_HeapAllocArray<unsigned short>(cchName, &Name);
      if ( Error >= 0 )
      {
        ReferencedDomainName[0] = 0;
        Error = CscUtil_HeapAllocArray<unsigned short>(cchReferencedDomainName, ReferencedDomainName);
        if ( Error < 0 )
        {
          v13 = Name;
        }
        else
        {
          v12 = ReferencedDomainName[0];
          peUsea = v5;
          v13 = Name;
          if ( LookupAccountSidW(0, a2, Name, &cchName, ReferencedDomainName[0], &cchReferencedDomainName, peUsea) )
          {
            *a3 = v13;
            v13 = 0;
            *a4 = v12;
            v12 = 0;
            Error = 0;
          }
          else
          {
            Error = UstVarLib::ResultFromLastError(v15);
          }
          CscUtil_HeapFree(v12, v14);
        }
        CscUtil_HeapFree(v13, v11);
      }
    }
    else if ( LastError > 0 )
    {
      return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002a680  mov     r11, rsp
0x18002a683  mov     [r11+8], rcx
0x18002a687  push    rbp
0x18002a688  push    rbx
0x18002a689  push    rsi
0x18002a68a  push    rdi
0x18002a68b  push    r12
0x18002a68d  push    r14
0x18002a68f  push    r15
0x18002a691  mov     rbp, rsp
0x18002a694  sub     rsp, 50h
0x18002a698  mov     rdi, [rbp+arg_20]
0x18002a69c  lea     rax, [rbp+arg_0]
0x18002a6a0  mov     [r11-58h], rdi
0x18002a6a4  mov     r14, r9
0x18002a6a7  mov     r15, r8
0x18002a6aa  mov     qword ptr [r8], 0
0x18002a6b1  mov     qword ptr [r9], 0
0x18002a6b8  xor     r8d, r8d; Name
0x18002a6bb  mov     [r11-60h], rax
0x18002a6bf  lea     r9, [rbp+cchName]; cchName
0x18002a6c3  xor     ecx, ecx; lpSystemName
0x18002a6c5  mov     qword ptr [r11-68h], 0
0x18002a6cd  mov     r12, rdx
0x18002a6d0  mov     [rbp+cchName], 0
0x18002a6d7  mov     [rbp+arg_0], 0
0x18002a6de  call    cs:__imp_LookupAccountSidW
0x18002a6e4  test    eax, eax
0x18002a6e6  jz      short loc_18002A6F2
0x18002a6e8  mov     ebx, 80004005h
0x18002a6ed  jmp     loc_18002A7A5
0x18002a6f2  call    cs:__imp_GetLastError
0x18002a6f8  mov     ebx, eax
0x18002a6fa  cmp     eax, 7Ah ; 'z'
0x18002a6fd  jz      short loc_18002A715
0x18002a6ff  test    eax, eax
0x18002a701  jle     loc_18002A7A5
0x18002a707  movzx   ebx, ax
0x18002a70a  or      ebx, 80070000h
0x18002a710  jmp     loc_18002A7A5
0x18002a715  mov     ecx, [rbp+cchName]
0x18002a718  lea     rdx, [rbp+Name]
0x18002a71c  mov     [rbp+Name], 0
0x18002a724  call    ??$CscUtil_HeapAllocArray@G@@YAJ_KPEAPEAG@Z; CscUtil_HeapAllocArray<ushort>(unsigned __int64,ushort * *)
0x18002a729  mov     ebx, eax
0x18002a72b  test    eax, eax
0x18002a72d  js      short loc_18002A7A5
0x18002a72f  mov     ecx, [rbp+arg_0]
0x18002a732  lea     rdx, [rbp+var_10]
0x18002a736  mov     [rbp+var_10], 0
0x18002a73e  call    ??$CscUtil_HeapAllocArray@G@@YAJ_KPEAPEAG@Z; CscUtil_HeapAllocArray<ushort>(unsigned __int64,ushort * *)
0x18002a743  mov     ebx, eax
0x18002a745  test    eax, eax
0x18002a747  js      short loc_18002A799
0x18002a749  mov     rsi, [rbp+var_10]
0x18002a74d  lea     rax, [rbp+arg_0]
0x18002a751  mov     [rsp+50h+peUse], rdi; peUse
0x18002a756  lea     r9, [rbp+cchName]; cchName
0x18002a75a  mov     rdi, [rbp+Name]
0x18002a75e  mov     rdx, r12; Sid
0x18002a761  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18002a766  mov     r8, rdi; Name
0x18002a769  xor     ecx, ecx; lpSystemName
0x18002a76b  mov     [rsp+50h+ReferencedDomainName], rsi; ReferencedDomainName
0x18002a770  call    cs:__imp_LookupAccountSidW
0x18002a776  test    eax, eax
0x18002a778  jnz     short loc_18002A783
0x18002a77a  call    ?ResultFromLastError@UstVarLib@@YAJXZ; UstVarLib::ResultFromLastError(void)
0x18002a77f  mov     ebx, eax
0x18002a781  jmp     short loc_18002A78F
0x18002a783  mov     [r15], rdi
0x18002a786  xor     edi, edi
0x18002a788  mov     [r14], rsi
0x18002a78b  xor     esi, esi
0x18002a78d  xor     ebx, ebx
0x18002a78f  mov     rcx, rsi; lpMem
0x18002a792  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18002a797  jmp     short loc_18002A79D
0x18002a799  mov     rdi, [rbp+Name]
0x18002a79d  mov     rcx, rdi; lpMem
0x18002a7a0  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18002a7a5  mov     eax, ebx
0x18002a7a7  add     rsp, 50h
0x18002a7ab  pop     r15
0x18002a7ad  pop     r14
0x18002a7af  pop     r12
0x18002a7b1  pop     rdi
0x18002a7b2  pop     rsi
0x18002a7b3  pop     rbx
0x18002a7b4  pop     rbp
0x18002a7b5  retn
```
