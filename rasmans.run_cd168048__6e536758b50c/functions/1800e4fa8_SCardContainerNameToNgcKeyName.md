# SCardContainerNameToNgcKeyName

- ea: `0x1800e4fa8`
- end: `0x1800e5126`
- name: `SCardContainerNameToNgcKeyName`
- size: `382`
- prototype: `__int64 __fastcall(LPCWSTR pszKeyName)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800e4dd8`

## callees

- `0x1800e4cd8`
- `0x1800e4fa8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e5088`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e5088`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e5071`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e5071`
- `ncrypt!NCryptOpenKey` at `0x1800e5023`
- `ncrypt!NCryptOpenKey` at `0x1800e5023`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800e4ff4`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800e4ff4`
- `ncrypt!NCryptGetProperty` at `0x1800e505c`
- `ncrypt!NCryptGetProperty` at `0x1800e50c6`
- `ncrypt!NCryptGetProperty` at `0x1800e505c`
- `ncrypt!NCryptGetProperty` at `0x1800e50c6`
- `ncrypt!NCryptFreeObject` at `0x1800e50ee`
- `ncrypt!NCryptFreeObject` at `0x1800e5103`
- `ncrypt!NCryptFreeObject` at `0x1800e50ee`
- `ncrypt!NCryptFreeObject` at `0x1800e5103`

## pseudocode

```c
__int64 __fastcall SCardContainerNameToNgcKeyName(LPCWSTR pszKeyName, BYTE **a2)
{
  SECURITY_STATUS Property; // ebx
  DWORD v5; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *v7; // rdi
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
            FreeH(v7);
          else
            *a2 = v7;
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
0x1800e4fa8  mov     [rsp-18h+arg_8], rbx
0x1800e4fad  push    rbp
0x1800e4fae  push    rsi
0x1800e4faf  push    rdi
0x1800e4fb0  mov     rbp, rsp
0x1800e4fb3  sub     rsp, 30h
0x1800e4fb7  mov     [rbp+phProvider], 0
0x1800e4fbf  mov     rsi, rdx
0x1800e4fc2  mov     [rbp+phKey], 0
0x1800e4fca  mov     rdi, rcx
0x1800e4fcd  mov     [rbp+pcbResult], 0
0x1800e4fd4  test    rcx, rcx
0x1800e4fd7  jz      loc_1800E5113
0x1800e4fdd  test    rdx, rdx
0x1800e4fe0  jz      loc_1800E5113
0x1800e4fe6  xor     r8d, r8d; dwFlags
0x1800e4fe9  lea     rdx, aMicrosoftSmart; "Microsoft Smart Card Key Storage Provid"...
0x1800e4ff0  lea     rcx, [rbp+phProvider]; phProvider
0x1800e4ff4  call    cs:__imp_NCryptOpenStorageProvider
0x1800e4ffb  nop     dword ptr [rax+rax+00h]
0x1800e5000  mov     ebx, eax
0x1800e5002  test    eax, eax
0x1800e5004  js      loc_1800E50E5
0x1800e500a  mov     rcx, [rbp+phProvider]; hProvider
0x1800e500e  lea     rdx, [rbp+phKey]; phKey
0x1800e5012  mov     r9d, 1; dwLegacyKeySpec
0x1800e5018  mov     [rsp+30h+dwFlags], 40h ; '@'; dwFlags
0x1800e5020  mov     r8, rdi; pszKeyName
0x1800e5023  call    cs:__imp_NCryptOpenKey
0x1800e502a  nop     dword ptr [rax+rax+00h]
0x1800e502f  mov     ebx, eax
0x1800e5031  test    eax, eax
0x1800e5033  js      loc_1800E50E5
0x1800e5039  mov     r9d, [rbp+pcbResult]; cbOutput
0x1800e503d  lea     rax, [rbp+pcbResult]
0x1800e5041  mov     rcx, [rbp+phKey]; hObject
0x1800e5045  lea     rdx, aSmartcardngcke; "SmartCardNgcKeyName"
0x1800e504c  mov     [rsp+30h+var_8], 40h ; '@'; dwFlags
0x1800e5054  xor     r8d, r8d; pbOutput
0x1800e5057  mov     qword ptr [rsp+30h+dwFlags], rax; pcbResult
0x1800e505c  call    cs:__imp_NCryptGetProperty
0x1800e5063  nop     dword ptr [rax+rax+00h]
0x1800e5068  mov     ebx, eax
0x1800e506a  test    eax, eax
0x1800e506c  js      short loc_1800E50E5
0x1800e506e  mov     ebx, [rbp+pcbResult]
0x1800e5071  call    cs:__imp_GetProcessHeap
0x1800e5078  nop     dword ptr [rax+rax+00h]
0x1800e507d  mov     r8d, ebx; dwBytes
0x1800e5080  mov     edx, 8; dwFlags
0x1800e5085  mov     rcx, rax; hHeap
0x1800e5088  call    cs:__imp_HeapAlloc
0x1800e508f  nop     dword ptr [rax+rax+00h]
0x1800e5094  mov     rdi, rax
0x1800e5097  test    rax, rax
0x1800e509a  jnz     short loc_1800E50A3
0x1800e509c  mov     ebx, 8009000Eh
0x1800e50a1  jmp     short loc_1800E50E5
0x1800e50a3  mov     r9d, [rbp+pcbResult]; cbOutput
0x1800e50a7  lea     rax, [rbp+pcbResult]
0x1800e50ab  mov     rcx, [rbp+phKey]; hObject
0x1800e50af  lea     rdx, aSmartcardngcke; "SmartCardNgcKeyName"
0x1800e50b6  mov     [rsp+30h+var_8], 40h ; '@'; dwFlags
0x1800e50be  mov     r8, rdi; pbOutput
0x1800e50c1  mov     qword ptr [rsp+30h+dwFlags], rax; pcbResult
0x1800e50c6  call    cs:__imp_NCryptGetProperty
0x1800e50cd  nop     dword ptr [rax+rax+00h]
0x1800e50d2  mov     ebx, eax
0x1800e50d4  test    eax, eax
0x1800e50d6  js      short loc_1800E50DD
0x1800e50d8  mov     [rsi], rdi
0x1800e50db  jmp     short loc_1800E50E5
0x1800e50dd  mov     rcx, rdi
0x1800e50e0  call    FreeH
0x1800e50e5  mov     rcx, [rbp+phProvider]; hObject
0x1800e50e9  test    rcx, rcx
0x1800e50ec  jz      short loc_1800E50FA
0x1800e50ee  call    cs:__imp_NCryptFreeObject
0x1800e50f5  nop     dword ptr [rax+rax+00h]
0x1800e50fa  mov     rcx, [rbp+phKey]; hObject
0x1800e50fe  test    rcx, rcx
0x1800e5101  jz      short loc_1800E510F
0x1800e5103  call    cs:__imp_NCryptFreeObject
0x1800e510a  nop     dword ptr [rax+rax+00h]
0x1800e510f  mov     eax, ebx
0x1800e5111  jmp     short loc_1800E5118
0x1800e5113  mov     eax, 80090027h
0x1800e5118  mov     rbx, [rsp+30h+arg_8]
0x1800e511d  add     rsp, 30h
0x1800e5121  pop     rdi
0x1800e5122  pop     rsi
0x1800e5123  pop     rbp
0x1800e5124  retn
```
