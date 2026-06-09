# GetMachineId

- ea: `0x1800555b8`
- end: `0x1800557fa`
- name: `GetMachineId`
- size: `578`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180055800`

## callees

- `0x18000d7b0`
- `0x18004b630`
- `0x1800555b8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800556bb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800556ed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800556bb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800556ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800556a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800556d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005578e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800557b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800556a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800556d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005578e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800557b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800557a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800557c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800557a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800557c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055683`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005574d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055683`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005574d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180055614`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180055614`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180055673`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180055729`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180055673`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180055729`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180055764`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180055764`

## string_xrefs

- `0x180055632`: `GetComputerName failed %d`

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
0x1800555b8  mov     [rsp-18h+arg_8], rbx
0x1800555bd  mov     [rsp-18h+arg_10], rsi
0x1800555c2  push    rbp
0x1800555c3  push    rdi
0x1800555c4  push    r14
0x1800555c6  mov     rbp, rsp
0x1800555c9  sub     rsp, 80h
0x1800555d0  mov     rax, cs:__security_cookie
0x1800555d7  xor     rax, rsp
0x1800555da  mov     [rbp+var_8], rax
0x1800555de  mov     r14, rcx
0x1800555e1  mov     qword ptr [rcx], 0
0x1800555e8  lea     rcx, [rbp+Buffer]; lpBuffer
0x1800555ec  mov     [rbp+cbSid], 0
0x1800555f3  lea     rdx, [rbp+nSize]; nSize
0x1800555f7  mov     [rbp+var_40], 0
0x1800555fe  mov     [rbp+var_38], 7
0x180055605  mov     [rbp+StringSid], 0
0x18005560d  mov     [rbp+nSize], 10h
0x180055614  call    cs:__imp_GetComputerNameW
0x18005561b  nop     dword ptr [rax+rax+00h]
0x180055620  test    eax, eax
0x180055622  jnz     short loc_18005564B
0x180055624  call    cs:__imp_GetLastError
0x18005562b  nop     dword ptr [rax+rax+00h]
0x180055630  mov     edi, eax
0x180055632  lea     rdx, aGetcomputernam; "GetComputerName failed %d"
0x180055639  mov     r8d, eax
0x18005563c  mov     ecx, 100000h
0x180055641  call    EventWrite0
0x180055646  jmp     loc_1800557D3
0x18005564b  lea     rax, [rbp+var_38]
0x18005564f  xor     r8d, r8d; Sid
0x180055652  mov     [rsp+80h+peUse], rax; peUse
0x180055657  lea     r9, [rbp+cbSid]; cbSid
0x18005565b  lea     rax, [rbp+var_40]
0x18005565f  xor     ecx, ecx; lpSystemName
0x180055661  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180055666  lea     rdx, [rbp+Buffer]; lpAccountName
0x18005566a  mov     [rsp+80h+ReferencedDomainName], 0; ReferencedDomainName
0x180055673  call    cs:__imp_LookupAccountNameW
0x18005567a  nop     dword ptr [rax+rax+00h]
0x18005567f  test    eax, eax
0x180055681  jnz     short loc_18005569F
0x180055683  call    cs:__imp_GetLastError
0x18005568a  nop     dword ptr [rax+rax+00h]
0x18005568f  mov     edi, eax
0x180055691  cmp     eax, 7Ah ; 'z'
0x180055694  jz      short loc_18005569F
0x180055696  lea     rdx, aLookupaccountn_0; "LookupAccountName failed %d"
0x18005569d  jmp     short loc_180055639
0x18005569f  mov     ebx, [rbp+cbSid]
0x1800556a2  call    cs:__imp_GetProcessHeap
0x1800556a9  nop     dword ptr [rax+rax+00h]
0x1800556ae  mov     edi, 8
0x1800556b3  mov     r8d, ebx; dwBytes
0x1800556b6  mov     rcx, rax; hHeap
0x1800556b9  mov     edx, edi; dwFlags
0x1800556bb  call    cs:__imp_HeapAlloc
0x1800556c2  nop     dword ptr [rax+rax+00h]
0x1800556c7  mov     rsi, rax
0x1800556ca  test    rax, rax
0x1800556cd  jz      loc_1800557D3
0x1800556d3  mov     ebx, [rbp+var_40]
0x1800556d6  add     rbx, rbx
0x1800556d9  call    cs:__imp_GetProcessHeap
0x1800556e0  nop     dword ptr [rax+rax+00h]
0x1800556e5  mov     r8, rbx; dwBytes
0x1800556e8  mov     edx, edi; dwFlags
0x1800556ea  mov     rcx, rax; hHeap
0x1800556ed  call    cs:__imp_HeapAlloc
0x1800556f4  nop     dword ptr [rax+rax+00h]
0x1800556f9  mov     rbx, rax
0x1800556fc  test    rax, rax
0x1800556ff  jz      loc_18005578E
0x180055705  lea     rax, [rbp+var_38]
0x180055709  mov     r8, rsi; Sid
0x18005570c  mov     [rsp+80h+peUse], rax; peUse
0x180055711  lea     r9, [rbp+cbSid]; cbSid
0x180055715  lea     rax, [rbp+var_40]
0x180055719  xor     ecx, ecx; lpSystemName
0x18005571b  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180055720  lea     rdx, [rbp+Buffer]; lpAccountName
0x180055724  mov     [rsp+80h+ReferencedDomainName], rbx; ReferencedDomainName
0x180055729  call    cs:__imp_LookupAccountNameW
0x180055730  nop     dword ptr [rax+rax+00h]
0x180055735  test    eax, eax
0x180055737  jnz     short loc_18005575D
0x180055739  xor     r8d, r8d
0x18005573c  lea     rdx, aLookupaccountn_0; "LookupAccountName failed %d"
0x180055743  mov     ecx, 100000h
0x180055748  call    EventWrite0
0x18005574d  call    cs:__imp_GetLastError
0x180055754  nop     dword ptr [rax+rax+00h]
0x180055759  mov     edi, eax
0x18005575b  jmp     short loc_18005578E
0x18005575d  lea     rdx, [rbp+StringSid]; StringSid
0x180055761  mov     rcx, rsi; Sid
0x180055764  call    cs:__imp_ConvertSidToStringSidW
0x18005576b  nop     dword ptr [rax+rax+00h]
0x180055770  test    eax, eax
0x180055772  jz      short loc_18005574D
0x180055774  mov     r8, [rbp+StringSid]
0x180055778  lea     rdx, aMachineIdIsS; "Machine id is %s"
0x18005577f  mov     ecx, 100000h
0x180055784  mov     [r14], r8
0x180055787  call    EventWrite0
0x18005578c  xor     edi, edi
0x18005578e  call    cs:__imp_GetProcessHeap
0x180055795  nop     dword ptr [rax+rax+00h]
0x18005579a  mov     r8, rsi; lpMem
0x18005579d  xor     edx, edx; dwFlags
0x18005579f  mov     rcx, rax; hHeap
0x1800557a2  call    cs:__imp_HeapFree
0x1800557a9  nop     dword ptr [rax+rax+00h]
0x1800557ae  test    rbx, rbx
0x1800557b1  jz      short loc_1800557D3
0x1800557b3  call    cs:__imp_GetProcessHeap
0x1800557ba  nop     dword ptr [rax+rax+00h]
0x1800557bf  mov     r8, rbx; lpMem
0x1800557c2  xor     edx, edx; dwFlags
0x1800557c4  mov     rcx, rax; hHeap
0x1800557c7  call    cs:__imp_HeapFree
0x1800557ce  nop     dword ptr [rax+rax+00h]
0x1800557d3  mov     eax, edi
0x1800557d5  mov     rcx, [rbp+var_8]
0x1800557d9  xor     rcx, rsp; StackCookie
0x1800557dc  call    __security_check_cookie
0x1800557e1  lea     r11, [rsp+80h+var_s0]
0x1800557e9  mov     rbx, [r11+28h]
0x1800557ed  mov     rsi, [r11+30h]
0x1800557f1  mov     rsp, r11
0x1800557f4  pop     r14
0x1800557f6  pop     rdi
0x1800557f7  pop     rbp
0x1800557f8  retn
```
