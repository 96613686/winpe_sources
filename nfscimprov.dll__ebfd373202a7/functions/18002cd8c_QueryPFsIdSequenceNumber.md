# QueryPFsIdSequenceNumber

- ea: `0x18002cd8c`
- end: `0x18002cef6`
- name: `QueryPFsIdSequenceNumber`
- size: `362`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18002d2b4`

## callees

- `0x18002cd8c`
- `0x18002d19c`
- `0x18002d1f8`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18002cdfb`
- `ADVAPI32!RegQueryValueExW` at `0x18002ce97`
- `ADVAPI32!RegQueryValueExW` at `0x18002cdfb`
- `ADVAPI32!RegQueryValueExW` at `0x18002ce97`
- `CLUSAPI!ClusterRegQueryValue` at `0x18002cdde`
- `CLUSAPI!ClusterRegQueryValue` at `0x18002ce7a`
- `CLUSAPI!ClusterRegQueryValue` at `0x18002cdde`
- `CLUSAPI!ClusterRegQueryValue` at `0x18002ce7a`

## string_xrefs

- `0x18002ce5e`: `PFsIdDuplicateCheck`
- `0x18002cdb4`: `PFsIdSequenceNumber`

## pseudocode

```c
__int64 __fastcall QueryPFsIdSequenceNumber(HKEY hKey, char a2, _DWORD *a3, bool *a4)
{
  LONG v8; // eax
  unsigned int v9; // ecx
  LONG v10; // eax
  DWORD cbData; // [rsp+30h] [rbp-10h] BYREF
  DWORD dwValueType[3]; // [rsp+34h] [rbp-Ch] BYREF
  int Data; // [rsp+68h] [rbp+28h] BYREF

  Data = 0;
  dwValueType[0] = 0;
  cbData = 4;
  if ( a2 )
    v8 = ClusterRegQueryValue(hKey, L"PFsIdSequenceNumber", dwValueType, (LPBYTE)&Data, &cbData);
  else
    v8 = RegQueryValueExW(hKey, L"PFsIdSequenceNumber", 0, dwValueType, (LPBYTE)&Data, &cbData);
  v9 = v8;
  if ( v8 )
  {
    if ( v8 != 2 )
      return v9;
    Data = 0;
    v9 = SetPFsIdSequenceNumber(hKey, a2, 0);
    if ( v9 )
      return v9;
  }
  else if ( dwValueType[0] != 4 || cbData > 4 )
  {
    return 13;
  }
  *a3 = Data;
  if ( a4 )
  {
    cbData = 4;
    if ( a2 )
      v10 = ClusterRegQueryValue(hKey, L"PFsIdDuplicateCheck", dwValueType, (LPBYTE)&Data, &cbData);
    else
      v10 = RegQueryValueExW(hKey, L"PFsIdDuplicateCheck", 0, dwValueType, (LPBYTE)&Data, &cbData);
    v9 = v10;
    if ( !v10 )
    {
      if ( dwValueType[0] != 4 || cbData > 4 )
        return 13;
LABEL_21:
      *a4 = Data != 0;
      return v9;
    }
    if ( v10 == 2 )
    {
      Data = 0;
      v9 = SetPFsIdSequenceNumberDuplicateCheck(hKey, a2, 0);
      if ( !v9 )
        goto LABEL_21;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18002cd8c  mov     [rsp-18h+arg_0], rbx
0x18002cd91  mov     [rsp-18h+arg_10], rsi
0x18002cd96  push    rbp
0x18002cd97  push    rdi
0x18002cd98  push    r14
0x18002cd9a  mov     rbp, rsp
0x18002cd9d  sub     rsp, 40h
0x18002cda1  mov     dil, dl
0x18002cda4  mov     [rbp+Data], 0
0x18002cdab  test    dl, dl
0x18002cdad  mov     [rbp+dwValueType], 0
0x18002cdb4  lea     rdx, aPfsidsequencen; "PFsIdSequenceNumber"
0x18002cdbb  mov     [rbp+cbData], 4
0x18002cdc2  mov     rsi, r9
0x18002cdc5  lea     rax, [rbp+cbData]
0x18002cdc9  mov     r14, r8
0x18002cdcc  mov     rbx, rcx
0x18002cdcf  jz      short loc_18002CDE6
0x18002cdd1  lea     r9, [rbp+Data]; lpData
0x18002cdd5  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18002cdda  lea     r8, [rbp+dwValueType]; lpdwValueType
0x18002cdde  call    cs:__imp_ClusterRegQueryValue
0x18002cde4  jmp     short loc_18002CE01
0x18002cde6  mov     [rsp+40h+var_18], rax; lpcbData
0x18002cdeb  lea     r9, [rbp+dwValueType]; lpType
0x18002cdef  lea     rax, [rbp+Data]
0x18002cdf3  xor     r8d, r8d; lpReserved
0x18002cdf6  mov     [rsp+40h+lpcbData], rax; lpData
0x18002cdfb  call    cs:__imp_RegQueryValueExW
0x18002ce01  mov     ecx, eax
0x18002ce03  test    eax, eax
0x18002ce05  jnz     short loc_18002CE1C
0x18002ce07  cmp     [rbp+dwValueType], 4
0x18002ce0b  jnz     loc_18002CEA9
0x18002ce11  cmp     [rbp+cbData], 4
0x18002ce15  jbe     short loc_18002CE44
0x18002ce17  jmp     loc_18002CEA9
0x18002ce1c  cmp     ecx, 2
0x18002ce1f  jnz     loc_18002CEE1
0x18002ce25  xor     r8d, r8d
0x18002ce28  mov     [rbp+Data], 0
0x18002ce2f  mov     dl, dil
0x18002ce32  mov     rcx, rbx
0x18002ce35  call    SetPFsIdSequenceNumber
0x18002ce3a  mov     ecx, eax
0x18002ce3c  test    eax, eax
0x18002ce3e  jnz     loc_18002CEE1
0x18002ce44  mov     eax, [rbp+Data]
0x18002ce47  mov     [r14], eax
0x18002ce4a  test    rsi, rsi
0x18002ce4d  jz      loc_18002CEE1
0x18002ce53  mov     [rbp+cbData], 4
0x18002ce5a  lea     rax, [rbp+cbData]
0x18002ce5e  lea     rdx, aPfsidduplicate; "PFsIdDuplicateCheck"
0x18002ce65  mov     rcx, rbx; hKey
0x18002ce68  test    dil, dil
0x18002ce6b  jz      short loc_18002CE82
0x18002ce6d  lea     r9, [rbp+Data]; lpData
0x18002ce71  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18002ce76  lea     r8, [rbp+dwValueType]; lpdwValueType
0x18002ce7a  call    cs:__imp_ClusterRegQueryValue
0x18002ce80  jmp     short loc_18002CE9D
0x18002ce82  mov     [rsp+40h+var_18], rax; lpcbData
0x18002ce87  lea     r9, [rbp+dwValueType]; lpType
0x18002ce8b  lea     rax, [rbp+Data]
0x18002ce8f  xor     r8d, r8d; lpReserved
0x18002ce92  mov     [rsp+40h+lpcbData], rax; lpData
0x18002ce97  call    cs:__imp_RegQueryValueExW
0x18002ce9d  mov     ecx, eax
0x18002ce9f  test    eax, eax
0x18002cea1  jnz     short loc_18002CEB8
0x18002cea3  cmp     [rbp+dwValueType], 4
0x18002cea7  jz      short loc_18002CEB0
0x18002cea9  mov     ecx, 0Dh
0x18002ceae  jmp     short loc_18002CEE1
0x18002ceb0  cmp     [rbp+cbData], 4
0x18002ceb4  jbe     short loc_18002CED8
0x18002ceb6  jmp     short loc_18002CEA9
0x18002ceb8  cmp     ecx, 2
0x18002cebb  jnz     short loc_18002CEE1
0x18002cebd  xor     r8d, r8d
0x18002cec0  mov     [rbp+Data], 0
0x18002cec7  mov     dl, dil
0x18002ceca  mov     rcx, rbx
0x18002cecd  call    SetPFsIdSequenceNumberDuplicateCheck
0x18002ced2  mov     ecx, eax
0x18002ced4  test    eax, eax
0x18002ced6  jnz     short loc_18002CEE1
0x18002ced8  cmp     [rbp+Data], 0
0x18002cedc  setnz   al
0x18002cedf  mov     [rsi], al
0x18002cee1  mov     rbx, [rsp+40h+arg_0]
0x18002cee6  mov     eax, ecx
0x18002cee8  mov     rsi, [rsp+40h+arg_10]
0x18002ceed  add     rsp, 40h
0x18002cef1  pop     r14
0x18002cef3  pop     rdi
0x18002cef4  pop     rbp
0x18002cef5  retn
```
