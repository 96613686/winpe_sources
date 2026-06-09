# SCardContainerNameToNgcKeyName

- ea: `0x1800e3524`
- end: `0x1800e367d`
- name: `SCardContainerNameToNgcKeyName`
- size: `345`
- prototype: `__int64 __fastcall(LPCWSTR pszKeyName)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800e3374`

## callees

- `0x1800e3524`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e3643`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e3643`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e35db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e3635`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e35db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e3635`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e35ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e35ec`
- `ncrypt!NCryptOpenKey` at `0x1800e3599`
- `ncrypt!NCryptOpenKey` at `0x1800e3599`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800e3570`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800e3570`
- `ncrypt!NCryptGetProperty` at `0x1800e35cc`
- `ncrypt!NCryptGetProperty` at `0x1800e3624`
- `ncrypt!NCryptGetProperty` at `0x1800e35cc`
- `ncrypt!NCryptGetProperty` at `0x1800e3624`
- `ncrypt!NCryptFreeObject` at `0x1800e3652`
- `ncrypt!NCryptFreeObject` at `0x1800e3661`
- `ncrypt!NCryptFreeObject` at `0x1800e3652`
- `ncrypt!NCryptFreeObject` at `0x1800e3661`

## pseudocode

```c
__int64 __fastcall SCardContainerNameToNgcKeyName(LPCWSTR pszKeyName, BYTE **a2)
{
  SECURITY_STATUS Property; // ebx
  DWORD v5; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *v7; // rdi
  HANDLE v8; // rax
  DWORD pcbResult; // [rsp+50h] [rbp+20h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+60h] [rbp+30h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+68h] [rbp+38h] BYREF

  phProvider = 0;
  phKey = 0;
  pcbResult = 0;
  if ( !pszKeyName || !a2 )
    return 2148073511LL;
  Property = NCryptOpenStorageProvider(&phProvider, L"Microsoft Smart Card Key Storage Provider", 0);
  if ( Property >= 0 )
  {
    Property = NCryptOpenKey(phProvider, &phKey, pszKeyName, 1u, 0x40u);
    if ( Property >= 0 )
    {
      Property = NCryptGetProperty(phKey, L"SmartCardNgcKeyName", 0, pcbResult, &pcbResult, 0x40u);
      if ( Property >= 0 )
      {
        v5 = pcbResult;
        ProcessHeap = GetProcessHeap();
        v7 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v5);
        if ( v7 )
        {
          Property = NCryptGetProperty(phKey, L"SmartCardNgcKeyName", v7, pcbResult, &pcbResult, 0x40u);
          if ( Property < 0 )
          {
            v8 = GetProcessHeap();
            HeapFree(v8, 0, v7);
          }
          else
          {
            *a2 = v7;
          }
        }
        else
        {
          Property = -2146893810;
        }
      }
    }
  }
  if ( phProvider )
    NCryptFreeObject(phProvider);
  if ( phKey )
    NCryptFreeObject(phKey);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1800e3524  mov     [rsp-18h+arg_8], rbx
0x1800e3529  push    rbp
0x1800e352a  push    rsi
0x1800e352b  push    rdi
0x1800e352c  mov     rbp, rsp
0x1800e352f  sub     rsp, 30h
0x1800e3533  mov     [rbp+phProvider], 0
0x1800e353b  mov     rsi, rdx
0x1800e353e  mov     [rbp+phKey], 0
0x1800e3546  mov     rdi, rcx
0x1800e3549  mov     [rbp+pcbResult], 0
0x1800e3550  test    rcx, rcx
0x1800e3553  jz      loc_1800E366B
0x1800e3559  test    rdx, rdx
0x1800e355c  jz      loc_1800E366B
0x1800e3562  xor     r8d, r8d; dwFlags
0x1800e3565  lea     rdx, aMicrosoftSmart; "Microsoft Smart Card Key Storage Provid"...
0x1800e356c  lea     rcx, [rbp+phProvider]; phProvider
0x1800e3570  call    cs:__imp_NCryptOpenStorageProvider
0x1800e3576  mov     ebx, eax
0x1800e3578  test    eax, eax
0x1800e357a  js      loc_1800E3649
0x1800e3580  mov     rcx, [rbp+phProvider]; hProvider
0x1800e3584  lea     rdx, [rbp+phKey]; phKey
0x1800e3588  mov     r9d, 1; dwLegacyKeySpec
0x1800e358e  mov     [rsp+30h+dwFlags], 40h ; '@'; dwFlags
0x1800e3596  mov     r8, rdi; pszKeyName
0x1800e3599  call    cs:__imp_NCryptOpenKey
0x1800e359f  mov     ebx, eax
0x1800e35a1  test    eax, eax
0x1800e35a3  js      loc_1800E3649
0x1800e35a9  mov     r9d, [rbp+pcbResult]; cbOutput
0x1800e35ad  lea     rax, [rbp+pcbResult]
0x1800e35b1  mov     rcx, [rbp+phKey]; hObject
0x1800e35b5  lea     rdx, aSmartcardngcke; "SmartCardNgcKeyName"
0x1800e35bc  mov     [rsp+30h+var_8], 40h ; '@'; dwFlags
0x1800e35c4  xor     r8d, r8d; pbOutput
0x1800e35c7  mov     qword ptr [rsp+30h+dwFlags], rax; pcbResult
0x1800e35cc  call    cs:__imp_NCryptGetProperty
0x1800e35d2  mov     ebx, eax
0x1800e35d4  test    eax, eax
0x1800e35d6  js      short loc_1800E3649
0x1800e35d8  mov     ebx, [rbp+pcbResult]
0x1800e35db  call    cs:__imp_GetProcessHeap
0x1800e35e1  mov     r8d, ebx; dwBytes
0x1800e35e4  mov     edx, 8; dwFlags
0x1800e35e9  mov     rcx, rax; hHeap
0x1800e35ec  call    cs:__imp_HeapAlloc
0x1800e35f2  mov     rdi, rax
0x1800e35f5  test    rax, rax
0x1800e35f8  jnz     short loc_1800E3601
0x1800e35fa  mov     ebx, 8009000Eh
0x1800e35ff  jmp     short loc_1800E3649
0x1800e3601  mov     r9d, [rbp+pcbResult]; cbOutput
0x1800e3605  lea     rax, [rbp+pcbResult]
0x1800e3609  mov     rcx, [rbp+phKey]; hObject
0x1800e360d  lea     rdx, aSmartcardngcke; "SmartCardNgcKeyName"
0x1800e3614  mov     [rsp+30h+var_8], 40h ; '@'; dwFlags
0x1800e361c  mov     r8, rdi; pbOutput
0x1800e361f  mov     qword ptr [rsp+30h+dwFlags], rax; pcbResult
0x1800e3624  call    cs:__imp_NCryptGetProperty
0x1800e362a  mov     ebx, eax
0x1800e362c  test    eax, eax
0x1800e362e  js      short loc_1800E3635
0x1800e3630  mov     [rsi], rdi
0x1800e3633  jmp     short loc_1800E3649
0x1800e3635  call    cs:__imp_GetProcessHeap
0x1800e363b  mov     r8, rdi; lpMem
0x1800e363e  xor     edx, edx; dwFlags
0x1800e3640  mov     rcx, rax; hHeap
0x1800e3643  call    cs:__imp_HeapFree
0x1800e3649  mov     rcx, [rbp+phProvider]; hObject
0x1800e364d  test    rcx, rcx
0x1800e3650  jz      short loc_1800E3658
0x1800e3652  call    cs:__imp_NCryptFreeObject
0x1800e3658  mov     rcx, [rbp+phKey]; hObject
0x1800e365c  test    rcx, rcx
0x1800e365f  jz      short loc_1800E3667
0x1800e3661  call    cs:__imp_NCryptFreeObject
0x1800e3667  mov     eax, ebx
0x1800e3669  jmp     short loc_1800E3670
0x1800e366b  mov     eax, 80090027h
0x1800e3670  mov     rbx, [rsp+30h+arg_8]
0x1800e3675  add     rsp, 30h
0x1800e3679  pop     rdi
0x1800e367a  pop     rsi
0x1800e367b  pop     rbp
0x1800e367c  retn
```
