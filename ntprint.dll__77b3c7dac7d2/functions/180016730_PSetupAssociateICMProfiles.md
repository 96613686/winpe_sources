# PSetupAssociateICMProfiles

- ea: `0x180016730`
- end: `0x180016859`
- name: `PSetupAssociateICMProfiles`
- size: `297`
- prototype: `__int64 __fastcall(unsigned __int16 *, PCWSTR pDeviceName)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180016990`

## callees

- `0x180002300`
- `0x180007944`
- `0x18000c368`
- `0x180016730`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001676f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001676f`
- `mscms!WcsAssociateColorProfileWithDevice` at `0x180016824`
- `mscms!WcsAssociateColorProfileWithDevice` at `0x180016824`
- `mscms!GetColorDirectoryW` at `0x1800167b0`
- `mscms!GetColorDirectoryW` at `0x1800167b0`

## pseudocode

```c
__int64 __fastcall PSetupAssociateICMProfiles(unsigned __int16 *a1, PCWSTR pDeviceName)
{
  __int64 v5; // rax
  DWORD v6; // edx
  __int64 v7; // rax
  __int64 v8; // rax
  DWORD pdwSize[4]; // [rsp+20h] [rbp-248h] BYREF
  WCHAR pBuffer[264]; // [rsp+30h] [rbp-238h] BYREF

  pdwSize[0] = 520;
  if ( PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled() )
  {
    SetLastError(0x4ECu);
    return 0;
  }
  if ( !a1 || !pDeviceName || !GetColorDirectoryW(0, pBuffer, pdwSize) )
    return 0;
  v5 = -1;
  do
    ++v5;
  while ( pBuffer[v5] );
  v6 = v5 + 1;
  pdwSize[0] = v6;
  pBuffer[v6 - 1] = 92;
  while ( *a1 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a1[v7] );
    if ( (unsigned __int64)v6 + v7 + 1 <= 0x104 )
    {
      StringCchCopyW(&pBuffer[v6], 260LL - v6, a1);
      if ( !WcsAssociateColorProfileWithDevice(WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE, pBuffer, pDeviceName) )
        return 0;
      v6 = pdwSize[0];
    }
    v8 = -1;
    do
      ++v8;
    while ( a1[v8] );
    a1 += v8 + 1;
  }
  return 1;
}

```

## disassembly

```asm
0x180016730  mov     [rsp+arg_10], rbx
0x180016735  push    rbp
0x180016736  push    rsi
0x180016737  push    rdi
0x180016738  sub     rsp, 250h
0x18001673f  mov     rax, cs:__security_cookie
0x180016746  xor     rax, rsp
0x180016749  mov     [rsp+268h+var_28], rax
0x180016751  mov     rdi, rdx
0x180016754  mov     [rsp+268h+pdwSize], 208h
0x18001675c  mov     rbx, rcx
0x18001675f  call    ?IsWindowsProtectedPrintEnabled@WindowsProtectedPrintHelpers@PrintCore@@SA_NXZ; PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled(void)
0x180016764  xor     esi, esi
0x180016766  test    al, al
0x180016768  jz      short loc_18001679A
0x18001676a  mov     ecx, 4ECh; dwErrCode
0x18001676f  call    cs:__imp_SetLastError
0x180016775  xor     eax, eax
0x180016777  mov     rcx, [rsp+268h+var_28]
0x18001677f  xor     rcx, rsp; StackCookie
0x180016782  call    __security_check_cookie
0x180016787  mov     rbx, [rsp+268h+arg_10]
0x18001678f  add     rsp, 250h
0x180016796  pop     rdi
0x180016797  pop     rsi
0x180016798  pop     rbp
0x180016799  retn
0x18001679a  test    rbx, rbx
0x18001679d  jz      short loc_180016775
0x18001679f  test    rdi, rdi
0x1800167a2  jz      short loc_180016775
0x1800167a4  lea     r8, [rsp+268h+pdwSize]; pdwSize
0x1800167a9  xor     ecx, ecx; pMachineName
0x1800167ab  lea     rdx, [rsp+268h+pBuffer]; pBuffer
0x1800167b0  call    cs:__imp_GetColorDirectoryW
0x1800167b6  test    eax, eax
0x1800167b8  jz      short loc_180016775
0x1800167ba  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800167be  lea     rcx, [rsp+268h+pBuffer]
0x1800167c3  mov     rax, rbp
0x1800167c6  inc     rax
0x1800167c9  cmp     [rcx+rax*2], si
0x1800167cd  jnz     short loc_1800167C6
0x1800167cf  lea     edx, [rax+1]
0x1800167d2  mov     eax, 5Ch ; '\'
0x1800167d7  lea     ecx, [rdx-1]
0x1800167da  mov     [rsp+268h+pdwSize], edx
0x1800167de  mov     [rsp+rcx*2+268h+pBuffer], ax
0x1800167e3  jmp     short loc_18001684A
0x1800167e5  mov     ecx, edx
0x1800167e7  mov     rax, rbp
0x1800167ea  inc     rax
0x1800167ed  cmp     [rbx+rax*2], si
0x1800167f1  jnz     short loc_1800167EA
0x1800167f3  inc     rax
0x1800167f6  add     rax, rcx
0x1800167f9  cmp     rax, 104h
0x1800167ff  ja      short loc_180016836
0x180016801  lea     rax, [rsp+268h+pBuffer]
0x180016806  mov     edx, 104h
0x18001680b  sub     rdx, rcx; unsigned __int64
0x18001680e  mov     r8, rbx; unsigned __int16 *
0x180016811  lea     rcx, [rax+rcx*2]; unsigned __int16 *
0x180016815  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001681a  mov     r8, rdi; pDeviceName
0x18001681d  lea     rdx, [rsp+268h+pBuffer]; pProfileName
0x180016822  xor     ecx, ecx; scope
0x180016824  call    cs:__imp_WcsAssociateColorProfileWithDevice
0x18001682a  test    eax, eax
0x18001682c  jz      loc_180016775
0x180016832  mov     edx, [rsp+268h+pdwSize]
0x180016836  mov     rax, rbp
0x180016839  inc     rax
0x18001683c  cmp     [rbx+rax*2], si
0x180016840  jnz     short loc_180016839
0x180016842  lea     rbx, [rbx+rax*2]
0x180016846  add     rbx, 2
0x18001684a  cmp     [rbx], si
0x18001684d  jnz     short loc_1800167E5
0x18001684f  mov     eax, 1
0x180016854  jmp     loc_180016777
```
