# GetMachineId

- ea: `0x1800555d8`
- end: `0x18005581a`
- name: `GetMachineId`
- size: `578`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180055820`

## callees

- `0x18000d7c0`
- `0x18004b5f0`
- `0x1800555d8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800556db`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005570d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800556db`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005570d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800556c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800556f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800557ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800557d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800556c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800556f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800557ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800557d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800557c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800557e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800557c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800557e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800556a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005576d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800556a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005576d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180055634`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180055634`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180055693`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180055749`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180055693`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180055749`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180055784`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180055784`

## string_xrefs

- `0x180055652`: `GetComputerName failed %d`

## pseudocode

```c
__int64 __fastcall GetMachineId(LPWSTR *a1)
{
  __int64 LastError; // rdi
  DWORD v3; // eax
  DWORD v4; // ebx
  HANDLE ProcessHeap; // rax
  void *v6; // rsi
  SIZE_T v7; // rbx
  HANDLE v8; // rax
  WCHAR *ReferencedDomainName; // rbx
  HANDLE v10; // rax
  HANDLE v11; // rax
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-40h] BYREF
  DWORD cbSid; // [rsp+44h] [rbp-3Ch] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-38h] BYREF
  DWORD nSize; // [rsp+4Ch] [rbp-34h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-30h] BYREF
  WCHAR Buffer[16]; // [rsp+58h] [rbp-28h] BYREF

  *a1 = 0;
  cbSid = 0;
  cchReferencedDomainName = 0;
  peUse = SidTypeInvalid;
  StringSid = 0;
  nSize = 16;
  if ( !GetComputerNameW(Buffer, &nSize) )
  {
    LastError = GetLastError();
    EventWrite0(0x100000, L"GetComputerName failed %d", LastError);
    return (unsigned int)LastError;
  }
  if ( !LookupAccountNameW(0, Buffer, 0, &cbSid, 0, &cchReferencedDomainName, &peUse) )
  {
    v3 = GetLastError();
    LODWORD(LastError) = v3;
    if ( v3 != 122 )
    {
      EventWrite0(0x100000, L"LookupAccountName failed %d", v3);
      return (unsigned int)LastError;
    }
  }
  v4 = cbSid;
  ProcessHeap = GetProcessHeap();
  LODWORD(LastError) = 8;
  v6 = HeapAlloc(ProcessHeap, 8u, v4);
  if ( !v6 )
    return (unsigned int)LastError;
  v7 = 2LL * cchReferencedDomainName;
  v8 = GetProcessHeap();
  ReferencedDomainName = (WCHAR *)HeapAlloc(v8, 8u, v7);
  if ( ReferencedDomainName )
  {
    if ( !LookupAccountNameW(0, Buffer, v6, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
    {
      EventWrite0(0x100000, L"LookupAccountName failed %d", 0);
LABEL_11:
      LODWORD(LastError) = GetLastError();
      goto LABEL_14;
    }
    if ( !ConvertSidToStringSidW(v6, &StringSid) )
      goto LABEL_11;
    *a1 = StringSid;
    EventWrite0(0x100000, L"Machine id is %s");
    LODWORD(LastError) = 0;
  }
LABEL_14:
  v10 = GetProcessHeap();
  HeapFree(v10, 0, v6);
  if ( ReferencedDomainName )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, ReferencedDomainName);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800555d8  mov     [rsp-18h+arg_8], rbx
0x1800555dd  mov     [rsp-18h+arg_10], rsi
0x1800555e2  push    rbp
0x1800555e3  push    rdi
0x1800555e4  push    r14
0x1800555e6  mov     rbp, rsp
0x1800555e9  sub     rsp, 80h
0x1800555f0  mov     rax, cs:__security_cookie
0x1800555f7  xor     rax, rsp
0x1800555fa  mov     [rbp+var_8], rax
0x1800555fe  mov     r14, rcx
0x180055601  mov     qword ptr [rcx], 0
0x180055608  lea     rcx, [rbp+Buffer]; lpBuffer
0x18005560c  mov     [rbp+cbSid], 0
0x180055613  lea     rdx, [rbp+nSize]; nSize
0x180055617  mov     [rbp+var_40], 0
0x18005561e  mov     [rbp+var_38], 7
0x180055625  mov     [rbp+StringSid], 0
0x18005562d  mov     [rbp+nSize], 10h
0x180055634  call    cs:__imp_GetComputerNameW
0x18005563b  nop     dword ptr [rax+rax+00h]
0x180055640  test    eax, eax
0x180055642  jnz     short loc_18005566B
0x180055644  call    cs:__imp_GetLastError
0x18005564b  nop     dword ptr [rax+rax+00h]
0x180055650  mov     edi, eax
0x180055652  lea     rdx, aGetcomputernam; "GetComputerName failed %d"
0x180055659  mov     r8d, eax
0x18005565c  mov     ecx, 100000h
0x180055661  call    EventWrite0
0x180055666  jmp     loc_1800557F3
0x18005566b  lea     rax, [rbp+var_38]
0x18005566f  xor     r8d, r8d; Sid
0x180055672  mov     [rsp+80h+peUse], rax; peUse
0x180055677  lea     r9, [rbp+cbSid]; cbSid
0x18005567b  lea     rax, [rbp+var_40]
0x18005567f  xor     ecx, ecx; lpSystemName
0x180055681  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180055686  lea     rdx, [rbp+Buffer]; lpAccountName
0x18005568a  mov     [rsp+80h+ReferencedDomainName], 0; ReferencedDomainName
0x180055693  call    cs:__imp_LookupAccountNameW
0x18005569a  nop     dword ptr [rax+rax+00h]
0x18005569f  test    eax, eax
0x1800556a1  jnz     short loc_1800556BF
0x1800556a3  call    cs:__imp_GetLastError
0x1800556aa  nop     dword ptr [rax+rax+00h]
0x1800556af  mov     edi, eax
0x1800556b1  cmp     eax, 7Ah ; 'z'
0x1800556b4  jz      short loc_1800556BF
0x1800556b6  lea     rdx, aLookupaccountn_0; "LookupAccountName failed %d"
0x1800556bd  jmp     short loc_180055659
0x1800556bf  mov     ebx, [rbp+cbSid]
0x1800556c2  call    cs:__imp_GetProcessHeap
0x1800556c9  nop     dword ptr [rax+rax+00h]
0x1800556ce  mov     edi, 8
0x1800556d3  mov     r8d, ebx; dwBytes
0x1800556d6  mov     rcx, rax; hHeap
0x1800556d9  mov     edx, edi; dwFlags
0x1800556db  call    cs:__imp_HeapAlloc
0x1800556e2  nop     dword ptr [rax+rax+00h]
0x1800556e7  mov     rsi, rax
0x1800556ea  test    rax, rax
0x1800556ed  jz      loc_1800557F3
0x1800556f3  mov     ebx, [rbp+var_40]
0x1800556f6  add     rbx, rbx
0x1800556f9  call    cs:__imp_GetProcessHeap
0x180055700  nop     dword ptr [rax+rax+00h]
0x180055705  mov     r8, rbx; dwBytes
0x180055708  mov     edx, edi; dwFlags
0x18005570a  mov     rcx, rax; hHeap
0x18005570d  call    cs:__imp_HeapAlloc
0x180055714  nop     dword ptr [rax+rax+00h]
0x180055719  mov     rbx, rax
0x18005571c  test    rax, rax
0x18005571f  jz      loc_1800557AE
0x180055725  lea     rax, [rbp+var_38]
0x180055729  mov     r8, rsi; Sid
0x18005572c  mov     [rsp+80h+peUse], rax; peUse
0x180055731  lea     r9, [rbp+cbSid]; cbSid
0x180055735  lea     rax, [rbp+var_40]
0x180055739  xor     ecx, ecx; lpSystemName
0x18005573b  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180055740  lea     rdx, [rbp+Buffer]; lpAccountName
0x180055744  mov     [rsp+80h+ReferencedDomainName], rbx; ReferencedDomainName
0x180055749  call    cs:__imp_LookupAccountNameW
0x180055750  nop     dword ptr [rax+rax+00h]
0x180055755  test    eax, eax
0x180055757  jnz     short loc_18005577D
0x180055759  xor     r8d, r8d
0x18005575c  lea     rdx, aLookupaccountn_0; "LookupAccountName failed %d"
0x180055763  mov     ecx, 100000h
0x180055768  call    EventWrite0
0x18005576d  call    cs:__imp_GetLastError
0x180055774  nop     dword ptr [rax+rax+00h]
0x180055779  mov     edi, eax
0x18005577b  jmp     short loc_1800557AE
0x18005577d  lea     rdx, [rbp+StringSid]; StringSid
0x180055781  mov     rcx, rsi; Sid
0x180055784  call    cs:__imp_ConvertSidToStringSidW
0x18005578b  nop     dword ptr [rax+rax+00h]
0x180055790  test    eax, eax
0x180055792  jz      short loc_18005576D
0x180055794  mov     r8, [rbp+StringSid]
0x180055798  lea     rdx, aMachineIdIsS; "Machine id is %s"
0x18005579f  mov     ecx, 100000h
0x1800557a4  mov     [r14], r8
0x1800557a7  call    EventWrite0
0x1800557ac  xor     edi, edi
0x1800557ae  call    cs:__imp_GetProcessHeap
0x1800557b5  nop     dword ptr [rax+rax+00h]
0x1800557ba  mov     r8, rsi; lpMem
0x1800557bd  xor     edx, edx; dwFlags
0x1800557bf  mov     rcx, rax; hHeap
0x1800557c2  call    cs:__imp_HeapFree
0x1800557c9  nop     dword ptr [rax+rax+00h]
0x1800557ce  test    rbx, rbx
0x1800557d1  jz      short loc_1800557F3
0x1800557d3  call    cs:__imp_GetProcessHeap
0x1800557da  nop     dword ptr [rax+rax+00h]
0x1800557df  mov     r8, rbx; lpMem
0x1800557e2  xor     edx, edx; dwFlags
0x1800557e4  mov     rcx, rax; hHeap
0x1800557e7  call    cs:__imp_HeapFree
0x1800557ee  nop     dword ptr [rax+rax+00h]
0x1800557f3  mov     eax, edi
0x1800557f5  mov     rcx, [rbp+var_8]
0x1800557f9  xor     rcx, rsp; StackCookie
0x1800557fc  call    __security_check_cookie
0x180055801  lea     r11, [rsp+80h+var_s0]
0x180055809  mov     rbx, [r11+28h]
0x18005580d  mov     rsi, [r11+30h]
0x180055811  mov     rsp, r11
0x180055814  pop     r14
0x180055816  pop     rdi
0x180055817  pop     rbp
0x180055818  retn
```
