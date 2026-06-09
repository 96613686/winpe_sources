# RegistryPath::ReadStringValue(ushort const *,ushort * *)

- ea: `0x18000cf10`
- end: `0x18000d23a`
- name: `?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z`
- size: `810`
- prototype: `unsigned int(RegistryPath *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000a2a0`
- `0x18000c680`

## callees

- `0x18000c190`
- `0x18000ced0`
- `0x18000cf10`
- `0x180027448`
- `0x18002bc58`
- `0x18002c23c`
- `0x180044a9c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cfc2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d0cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cfc2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d0cf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cfd3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d0e0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cfd3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d0e0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000cf94`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d00f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d09d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000cf94`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d00f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d09d`

## string_xrefs

- `0x18000d041`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x18000d03a`: `RegistryPath::ReadStringValue`
- `0x18000d11e`: `RegReadStringValue`
- `0x18000d15f`: `RegReadStringValue`
- `0x18000d1a2`: `RegReadStringValue`
- `0x18000d1dc`: `RegReadStringValue`
- `0x18000d1fd`: `RegReadStringValue`
- `0x18000d166`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x18000d1a9`: `%s: The registry key value "%s@%s" does not exist. Using default value NULL. Error code: 0x%08x.`
- `0x18000d1e3`: `%s: The registry key value "%s@%s" is not of one of the specified types (flags = 0x%08x). Using default value NULL.`

## pseudocode

```c
__int64 __fastcall RegistryPath::ReadStringValue(RegistryPath *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  HKEY v3; // rsi
  const unsigned __int16 *v6; // rdi
  HKEY v7; // r12
  LSTATUS ValueW; // eax
  const unsigned __int16 *v9; // rdx
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *pvData; // rax
  LSTATUS v14; // eax
  __int64 v16; // rax
  const WCHAR *v17; // r12
  LSTATUS v18; // eax
  unsigned int v19; // ebx
  HANDLE v20; // rax
  unsigned __int16 *v21; // rax
  int v22; // eax
  const wchar_t *v23; // r9
  int v24; // eax
  const wchar_t *v25; // r9
  int v26; // eax
  const wchar_t *v27; // r9
  LPDWORD pdwType; // [rsp+20h] [rbp-48h]
  SIZE_T dwBytes; // [rsp+70h] [rbp+8h] BYREF
  DWORD v30; // [rsp+88h] [rbp+20h] BYREF

  v3 = (HKEY)*((_QWORD *)this + 4);
  if ( v3 )
  {
    v6 = *(const unsigned __int16 **)this;
    if ( *(_QWORD *)this )
    {
      if ( *v6 )
      {
        v7 = (HKEY)*((_QWORD *)this + 5);
        v30 = 0;
        LODWORD(dwBytes) = 0;
        if ( v7 )
        {
          if ( a3 )
          {
            *a3 = 0;
            ValueW = RegGetValueW(v7, 0, a2, 2u, &v30, 0, (LPDWORD)&dwBytes);
            v10 = ValueW;
            if ( ValueW != 2 )
            {
              if ( ValueW != 1630 )
              {
                if ( ValueW && ValueW != 234 )
                  goto LABEL_24;
                if ( !(_DWORD)dwBytes )
                  goto LABEL_13;
                v11 = dwBytes;
                ProcessHeap = GetProcessHeap();
                pvData = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v11);
                *a3 = pvData;
                if ( pvData )
                {
                  v14 = RegGetValueW(v7, 0, a2, 2u, &v30, pvData, (LPDWORD)&dwBytes);
LABEL_12:
                  v10 = v14;
                  goto LABEL_13;
                }
                goto LABEL_23;
              }
              goto LABEL_30;
            }
            goto LABEL_27;
          }
        }
        else if ( a3 )
        {
          v16 = *((_QWORD *)this + 3);
          *a3 = 0;
          v17 = &v6[v16];
          v18 = RegGetValueW(v3, v17, a2, 2u, &v30, 0, (LPDWORD)&dwBytes);
          v10 = v18;
          if ( v18 != 2 )
          {
            if ( v18 != 1630 )
            {
              if ( v18 && v18 != 234 )
                goto LABEL_24;
              if ( !(_DWORD)dwBytes )
              {
LABEL_13:
                if ( !v10 )
                  return v10;
LABEL_24:
                Logger::WriteRegistryFailureEvent(v10, v9, v6, a2);
                v22 = IsEmptyString(a2);
                LODWORD(pdwType) = v10;
                v23 = L"(default)";
                if ( !v22 )
                  v23 = a2;
                Logger::TraceWarning(
                  L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
                  L"RegReadStringValue",
                  v6,
                  v23,
                  pdwType);
                SafeFree(*a3);
                *a3 = 0;
                return v10;
              }
              v19 = dwBytes;
              v20 = GetProcessHeap();
              v21 = (unsigned __int16 *)HeapAlloc(v20, 8u, v19);
              *a3 = v21;
              if ( v21 )
              {
                v14 = RegGetValueW(v3, v17, a2, 2u, &v30, v21, (LPDWORD)&dwBytes);
                goto LABEL_12;
              }
LABEL_23:
              v10 = 14;
              Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegReadStringValue");
              goto LABEL_24;
            }
LABEL_30:
            v26 = IsEmptyString(a2);
            LODWORD(pdwType) = 2;
            v27 = L"(default)";
            if ( !v26 )
              v27 = a2;
            Logger::TraceWarning(
              L"%s: The registry key value \"%s@%s\" is not of one of the specified types (flags = 0x%08x). Using default value NULL.",
              L"RegReadStringValue",
              v6,
              v27,
              pdwType);
            return 0;
          }
LABEL_27:
          v24 = IsEmptyString(a2);
          LODWORD(pdwType) = 2;
          v25 = L"(default)";
          if ( !v24 )
            v25 = a2;
          Logger::TraceWarning(
            L"%s: The registry key value \"%s@%s\" does not exist. Using default value NULL. Error code: 0x%08x.",
            L"RegReadStringValue",
            v6,
            v25,
            pdwType);
          return 0;
        }
        Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegReadStringValue", L"pData");
        return 87;
      }
    }
  }
  Logger::TraceError(
    L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
    L"RegistryPath::ReadStringValue");
  return 87;
}

```

## disassembly

```asm
0x18000cf10  mov     r11, rsp
0x18000cf13  push    rbx
0x18000cf14  push    rsi
0x18000cf15  push    rdi
0x18000cf16  push    r14
0x18000cf18  push    r15
0x18000cf1a  sub     rsp, 40h
0x18000cf1e  mov     rsi, [rcx+20h]
0x18000cf22  mov     r14, r8
0x18000cf25  mov     r15, rdx
0x18000cf28  test    rsi, rsi
0x18000cf2b  jz      loc_18000D03A
0x18000cf31  mov     rdi, [rcx]
0x18000cf34  test    rdi, rdi
0x18000cf37  jz      loc_18000D03A
0x18000cf3d  cmp     word ptr [rdi], 0
0x18000cf41  jz      loc_18000D03A
0x18000cf47  mov     [r11+18h], r12
0x18000cf4b  mov     r12, [rcx+28h]
0x18000cf4f  mov     [r11+10h], rbp
0x18000cf53  xor     ebp, ebp
0x18000cf55  mov     [r11+20h], ebp
0x18000cf59  mov     dword ptr [rsp+68h+dwBytes], ebp
0x18000cf5d  test    r12, r12
0x18000cf60  jz      loc_18000D05E
0x18000cf66  test    r8, r8
0x18000cf69  jz      loc_18000D1F6
0x18000cf6f  lea     rax, [r11+8]
0x18000cf73  mov     [r8], rbp
0x18000cf76  mov     [r11-38h], rax
0x18000cf7a  mov     r8, rdx; lpValue
0x18000cf7d  lea     rax, [r11+20h]
0x18000cf81  mov     [r11-40h], rbp
0x18000cf85  mov     r9d, 2; dwFlags
0x18000cf8b  mov     [r11-48h], rax
0x18000cf8f  xor     edx, edx; lpSubKey
0x18000cf91  mov     rcx, r12; hkey
0x18000cf94  call    cs:__imp_RegGetValueW
0x18000cf9a  mov     ebx, eax
0x18000cf9c  cmp     eax, 2
0x18000cf9f  jz      loc_18000D182
0x18000cfa5  cmp     eax, 65Eh
0x18000cfaa  jz      loc_18000D1BC
0x18000cfb0  test    eax, eax
0x18000cfb2  jnz     loc_18000D21A
0x18000cfb8  mov     eax, dword ptr [rsp+68h+dwBytes]
0x18000cfbc  test    eax, eax
0x18000cfbe  jz      short loc_18000D017
0x18000cfc0  mov     ebx, eax
0x18000cfc2  call    cs:__imp_GetProcessHeap
0x18000cfc8  mov     r8d, ebx; dwBytes
0x18000cfcb  mov     edx, 8; dwFlags
0x18000cfd0  mov     rcx, rax; hHeap
0x18000cfd3  call    cs:__imp_HeapAlloc
0x18000cfd9  mov     [r14], rax
0x18000cfdc  test    rax, rax
0x18000cfdf  jz      loc_18000D11E
0x18000cfe5  lea     rcx, [rsp+68h+dwBytes]
0x18000cfea  mov     r9d, 2; dwFlags
0x18000cff0  mov     [rsp+68h+pcbData], rcx; pcbData
0x18000cff5  mov     r8, r15; lpValue
0x18000cff8  mov     [rsp+68h+pvData], rax; pvData
0x18000cffd  xor     edx, edx; lpSubKey
0x18000cfff  lea     rax, [rsp+68h+arg_18]
0x18000d007  mov     rcx, r12; hkey
0x18000d00a  mov     [rsp+68h+pdwType], rax; pdwType
0x18000d00f  call    cs:__imp_RegGetValueW
0x18000d015  mov     ebx, eax
0x18000d017  test    ebx, ebx
0x18000d019  jnz     loc_18000D136
0x18000d01f  mov     rbp, [rsp+68h+arg_8]
0x18000d024  mov     eax, ebx
0x18000d026  mov     r12, [rsp+68h+arg_10]
0x18000d02e  add     rsp, 40h
0x18000d032  pop     r15
0x18000d034  pop     r14
0x18000d036  pop     rdi
0x18000d037  pop     rsi
0x18000d038  pop     rbx
0x18000d039  retn
0x18000d03a  lea     rdx, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18000d041  lea     rcx, aSThisPathObjec; "%s: This path object has not been prope"...
0x18000d048  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000d04d  mov     eax, 57h ; 'W'
0x18000d052  add     rsp, 40h
0x18000d056  pop     r15
0x18000d058  pop     r14
0x18000d05a  pop     rdi
0x18000d05b  pop     rsi
0x18000d05c  pop     rbx
0x18000d05d  retn
0x18000d05e  test    r14, r14
0x18000d061  jz      loc_18000D1F6
0x18000d067  mov     rax, [rcx+18h]
0x18000d06b  mov     r9d, 2; dwFlags
0x18000d071  mov     [r8], rbp
0x18000d074  mov     rcx, rsi; hkey
0x18000d077  mov     r8, r15; lpValue
0x18000d07a  lea     r12, [rdi+rax*2]
0x18000d07e  lea     rax, [rsp+68h+dwBytes]
0x18000d083  mov     rdx, r12; lpSubKey
0x18000d086  mov     [rsp+68h+pcbData], rax; pcbData
0x18000d08b  lea     rax, [rsp+68h+arg_18]
0x18000d093  mov     [rsp+68h+pvData], rbp; pvData
0x18000d098  mov     [rsp+68h+pdwType], rax; pdwType
0x18000d09d  call    cs:__imp_RegGetValueW
0x18000d0a3  mov     ebx, eax
0x18000d0a5  cmp     eax, 2
0x18000d0a8  jz      loc_18000D182
0x18000d0ae  cmp     eax, 65Eh
0x18000d0b3  jz      loc_18000D1BC
0x18000d0b9  test    eax, eax
0x18000d0bb  jnz     loc_18000D22A
0x18000d0c1  mov     eax, dword ptr [rsp+68h+dwBytes]
0x18000d0c5  test    eax, eax
0x18000d0c7  jz      loc_18000D017
0x18000d0cd  mov     ebx, eax
0x18000d0cf  call    cs:__imp_GetProcessHeap
0x18000d0d5  mov     r8d, ebx; dwBytes
0x18000d0d8  mov     edx, 8; dwFlags
0x18000d0dd  mov     rcx, rax; hHeap
0x18000d0e0  call    cs:__imp_HeapAlloc
0x18000d0e6  mov     [r14], rax
0x18000d0e9  test    rax, rax
0x18000d0ec  jz      short loc_18000D11E
0x18000d0ee  lea     rcx, [rsp+68h+dwBytes]
0x18000d0f3  mov     r9d, 2
0x18000d0f9  mov     [rsp+68h+pcbData], rcx
0x18000d0fe  mov     r8, r15
0x18000d101  mov     [rsp+68h+pvData], rax
0x18000d106  mov     rdx, r12
0x18000d109  lea     rax, [rsp+68h+arg_18]
0x18000d111  mov     rcx, rsi
0x18000d114  mov     [rsp+68h+pdwType], rax
0x18000d119  jmp     loc_18000D00F
0x18000d11e  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18000d125  mov     ebx, 0Eh
0x18000d12a  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18000d131  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18000d136  mov     r9, r15; unsigned __int16 *
0x18000d139  mov     r8, rdi; unsigned __int16 *
0x18000d13c  mov     ecx, ebx; unsigned int
0x18000d13e  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)
0x18000d143  mov     rcx, r15; unsigned __int16 *
0x18000d146  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18000d14b  test    eax, eax
0x18000d14d  mov     dword ptr [rsp+68h+pdwType], ebx
0x18000d151  lea     r9, aDefault; "(default)"
0x18000d158  mov     r8, rdi
0x18000d15b  cmovz   r9, r15
0x18000d15f  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18000d166  lea     rcx, aSCannotReadReg; "%s: Cannot read registry key value \"%s"...
0x18000d16d  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18000d172  mov     rcx, [r14]; lpMem
0x18000d175  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000d17a  mov     [r14], rbp
0x18000d17d  jmp     loc_18000D01F
0x18000d182  mov     rcx, r15; unsigned __int16 *
0x18000d185  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18000d18a  test    eax, eax
0x18000d18c  mov     dword ptr [rsp+68h+pdwType], 2
0x18000d194  lea     r9, aDefault; "(default)"
0x18000d19b  mov     r8, rdi
0x18000d19e  cmovz   r9, r15
0x18000d1a2  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18000d1a9  lea     rcx, aSTheRegistryKe; "%s: The registry key value \"%s@%s\" do"...
0x18000d1b0  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18000d1b5  mov     ebx, ebp
0x18000d1b7  jmp     loc_18000D01F
0x18000d1bc  mov     rcx, r15; unsigned __int16 *
0x18000d1bf  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18000d1c4  test    eax, eax
0x18000d1c6  mov     dword ptr [rsp+68h+pdwType], 2
0x18000d1ce  lea     r9, aDefault; "(default)"
0x18000d1d5  mov     r8, rdi
0x18000d1d8  cmovz   r9, r15
0x18000d1dc  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18000d1e3  lea     rcx, aSTheRegistryKe_4; "%s: The registry key value \"%s@%s\" is"...
0x18000d1ea  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18000d1ef  mov     ebx, ebp
0x18000d1f1  jmp     loc_18000D01F
0x18000d1f6  lea     r8, aPdata; "pData"
0x18000d1fd  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18000d204  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18000d20b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000d210  mov     ebx, 57h ; 'W'
0x18000d215  jmp     loc_18000D01F
0x18000d21a  cmp     eax, 0EAh
0x18000d21f  jnz     loc_18000D136
0x18000d225  jmp     loc_18000CFB8
0x18000d22a  cmp     eax, 0EAh
0x18000d22f  jnz     loc_18000D136
0x18000d235  jmp     loc_18000D0C1
```
