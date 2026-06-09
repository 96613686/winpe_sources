# CscSec_LookupAccountSid(ushort const *,void *,ushort * *,ushort * *,_SID_NAME_USE *)

- ea: `0x1800341c8`
- end: `0x1800342fe`
- name: `?CscSec_LookupAccountSid@@YAJPEBGPEAXPEAPEAG2PEAW4_SID_NAME_USE@@@Z`
- size: `310`
- prototype: `int(const unsigned __int16 *, void *, unsigned __int16 **, unsigned __int16 **, enum _SID_NAME_USE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18002d014`

## callees

- `0x18000d640`
- `0x18002edf8`
- `0x18002f10c`
- `0x1800341c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003423a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003423a`
- `ADVAPI32!LookupAccountSidW` at `0x180034226`
- `ADVAPI32!LookupAccountSidW` at `0x1800342b8`
- `ADVAPI32!LookupAccountSidW` at `0x180034226`
- `ADVAPI32!LookupAccountSidW` at `0x1800342b8`

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
  enum _SID_NAME_USE *peUse; // [rsp+30h] [rbp-20h]
  enum _SID_NAME_USE *peUsea; // [rsp+30h] [rbp-20h]
  LPWSTR ReferencedDomainName[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD cchReferencedDomainName; // [rsp+90h] [rbp+40h] BYREF
  int v20; // [rsp+94h] [rbp+44h]
  DWORD cchName; // [rsp+A0h] [rbp+50h] BYREF
  LPWSTR Name; // [rsp+A8h] [rbp+58h] BYREF

  v20 = HIDWORD(a1);
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
            Error = ResultFromLastError();
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
0x1800341c8  mov     r11, rsp
0x1800341cb  mov     [r11+8], rcx
0x1800341cf  push    rbp
0x1800341d0  push    rbx
0x1800341d1  push    rsi
0x1800341d2  push    rdi
0x1800341d3  push    r12
0x1800341d5  push    r14
0x1800341d7  push    r15
0x1800341d9  mov     rbp, rsp
0x1800341dc  sub     rsp, 50h
0x1800341e0  mov     rdi, [rbp+arg_20]
0x1800341e4  lea     rax, [rbp+arg_0]
0x1800341e8  mov     [r11-58h], rdi
0x1800341ec  mov     r14, r9
0x1800341ef  mov     r15, r8
0x1800341f2  mov     qword ptr [r8], 0
0x1800341f9  mov     qword ptr [r9], 0
0x180034200  xor     r8d, r8d; Name
0x180034203  mov     [r11-60h], rax
0x180034207  lea     r9, [rbp+cchName]; cchName
0x18003420b  xor     ecx, ecx; lpSystemName
0x18003420d  mov     qword ptr [r11-68h], 0
0x180034215  mov     r12, rdx
0x180034218  mov     [rbp+cchName], 0
0x18003421f  mov     [rbp+arg_0], 0
0x180034226  call    cs:__imp_LookupAccountSidW
0x18003422c  test    eax, eax
0x18003422e  jz      short loc_18003423A
0x180034230  mov     ebx, 80004005h
0x180034235  jmp     loc_1800342ED
0x18003423a  call    cs:__imp_GetLastError
0x180034240  mov     ebx, eax
0x180034242  cmp     eax, 7Ah ; 'z'
0x180034245  jz      short loc_18003425D
0x180034247  test    eax, eax
0x180034249  jle     loc_1800342ED
0x18003424f  movzx   ebx, ax
0x180034252  or      ebx, 80070000h
0x180034258  jmp     loc_1800342ED
0x18003425d  mov     ecx, [rbp+cchName]
0x180034260  lea     rdx, [rbp+Name]
0x180034264  mov     [rbp+Name], 0
0x18003426c  call    ??$CscUtil_HeapAllocArray@G@@YAJ_KPEAPEAG@Z; CscUtil_HeapAllocArray<ushort>(unsigned __int64,ushort * *)
0x180034271  mov     ebx, eax
0x180034273  test    eax, eax
0x180034275  js      short loc_1800342ED
0x180034277  mov     ecx, [rbp+arg_0]
0x18003427a  lea     rdx, [rbp+var_10]
0x18003427e  mov     [rbp+var_10], 0
0x180034286  call    ??$CscUtil_HeapAllocArray@G@@YAJ_KPEAPEAG@Z; CscUtil_HeapAllocArray<ushort>(unsigned __int64,ushort * *)
0x18003428b  mov     ebx, eax
0x18003428d  test    eax, eax
0x18003428f  js      short loc_1800342E1
0x180034291  mov     rsi, [rbp+var_10]
0x180034295  lea     rax, [rbp+arg_0]
0x180034299  mov     [rsp+50h+peUse], rdi; peUse
0x18003429e  lea     r9, [rbp+cchName]; cchName
0x1800342a2  mov     rdi, [rbp+Name]
0x1800342a6  mov     rdx, r12; Sid
0x1800342a9  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800342ae  mov     r8, rdi; Name
0x1800342b1  xor     ecx, ecx; lpSystemName
0x1800342b3  mov     [rsp+50h+ReferencedDomainName], rsi; ReferencedDomainName
0x1800342b8  call    cs:__imp_LookupAccountSidW
0x1800342be  test    eax, eax
0x1800342c0  jnz     short loc_1800342CB
0x1800342c2  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800342c7  mov     ebx, eax
0x1800342c9  jmp     short loc_1800342D7
0x1800342cb  mov     [r15], rdi
0x1800342ce  xor     edi, edi
0x1800342d0  mov     [r14], rsi
0x1800342d3  xor     esi, esi
0x1800342d5  xor     ebx, ebx
0x1800342d7  mov     rcx, rsi; lpMem
0x1800342da  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x1800342df  jmp     short loc_1800342E5
0x1800342e1  mov     rdi, [rbp+Name]
0x1800342e5  mov     rcx, rdi; lpMem
0x1800342e8  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x1800342ed  mov     eax, ebx
0x1800342ef  add     rsp, 50h
0x1800342f3  pop     r15
0x1800342f5  pop     r14
0x1800342f7  pop     r12
0x1800342f9  pop     rdi
0x1800342fa  pop     rsi
0x1800342fb  pop     rbx
0x1800342fc  pop     rbp
0x1800342fd  retn
```
