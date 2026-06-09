# CompareValues

- ea: `0x140008b4c`
- end: `0x140008df4`
- name: `CompareValues`
- size: `680`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpValueName, int, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140008320`
- `0x140008788`

## callees

- `0x140002b70`
- `0x140008b4c`
- `0x140009574`
- `0x14000c62c`
- `0x14000c9c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140008bf5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140008c2a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140008cbf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140008cee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140008bf5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140008c2a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140008cbf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140008cee`

## pseudocode

```c
__int64 __fastcall CompareValues(
        HKEY hKey,
        __int64 a2,
        HKEY a3,
        __int64 a4,
        LPCWSTR lpValueName,
        unsigned int a6,
        _DWORD *a7)
{
  const WCHAR *v9; // rbx
  _DWORD *v10; // rdi
  unsigned int v11; // r14d
  unsigned int v13; // esi
  BYTE *lpData; // r15
  unsigned int v15; // ebx
  LPBYTE v16; // r13
  __int64 v17; // r10
  DWORD cbData; // [rsp+30h] [rbp-20h] BYREF
  DWORD v19; // [rsp+34h] [rbp-1Ch] BYREF
  DWORD Type; // [rsp+38h] [rbp-18h] BYREF
  BYTE *Memory; // [rsp+40h] [rbp-10h] BYREF
  LPBYTE v22; // [rsp+48h] [rbp-8h] BYREF
  DWORD lpcbData; // [rsp+90h] [rbp+40h] BYREF
  __int64 v24; // [rsp+98h] [rbp+48h]
  __int64 v25; // [rsp+A8h] [rbp+58h]

  v25 = a4;
  v24 = a2;
  Type = 0;
  v19 = 0;
  cbData = 0;
  lpcbData = 0;
  if ( !hKey || !a2 || !a3 || !a4 || (v9 = lpValueName) == 0 || (v10 = a7) == 0 )
  {
    v15 = 87;
    goto LABEL_36;
  }
  v11 = a6;
  if ( a6 <= 1 && *a7 == 1 )
    return 0;
  v13 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
  if ( v13 )
    goto LABEL_11;
  v13 = RegQueryValueExW(a3, v9, 0, &v19, 0, &lpcbData);
  if ( v13 )
    goto LABEL_11;
  if ( v11 <= 1 && (Type != v19 || cbData != lpcbData) )
  {
    *v10 = 1;
    return 0;
  }
  cbData = (cbData + 1) & 0xFFFFFFFE;
  Memory = (BYTE *)AllocateMemory(cbData + 2);
  lpData = Memory;
  if ( !Memory )
    goto LABEL_18;
  lpcbData = (lpcbData + 1) & 0xFFFFFFFE;
  v22 = (LPBYTE)AllocateMemory(lpcbData + 2);
  if ( v22 )
  {
    v13 = RegQueryValueExW(hKey, v9, 0, &Type, lpData, &cbData);
    if ( !v13 )
    {
      v16 = v22;
      v13 = RegQueryValueExW(a3, v9, 0, &v19, v22, &lpcbData);
      if ( !v13 )
      {
        if ( Type == v19 && cbData == lpcbData )
        {
          v17 = 0;
          if ( !cbData )
          {
LABEL_28:
            if ( ((v11 - 2) & 0xFFFFFFFD) == 0 )
              PrintValue(v24, (__int64)v9, Type, (__int64)lpData, cbData, 3);
LABEL_33:
            FreeMemory(&Memory);
            FreeMemory(&v22);
            SaveErrorMessage(0);
            return 0;
          }
          while ( lpData[v17] == v16[v17] )
          {
            v17 = (unsigned int)(v17 + 1);
            if ( (unsigned int)v17 >= cbData )
              goto LABEL_28;
          }
        }
        if ( v11 - 3 <= 1 )
        {
          PrintValue(v24, (__int64)v9, Type, (__int64)lpData, cbData, 1);
          PrintValue(v25, (__int64)v9, v19, (__int64)v16, lpcbData, 2);
        }
        *v10 = 1;
        goto LABEL_33;
      }
    }
    FreeMemory(&Memory);
    FreeMemory(&v22);
LABEL_11:
    SaveErrorMessage(v13);
    return v13;
  }
  FreeMemory(&Memory);
LABEL_18:
  v15 = 14;
LABEL_36:
  SaveErrorMessage(v15);
  return v15;
}

```

## disassembly

```asm
0x140008b4c  mov     [rsp-38h+arg_10], rbx
0x140008b51  mov     [rsp-38h+arg_18], r9
0x140008b56  mov     [rsp-38h+arg_8], rdx
0x140008b5b  push    rbp
0x140008b5c  push    rsi
0x140008b5d  push    rdi
0x140008b5e  push    r12
0x140008b60  push    r13
0x140008b62  push    r14
0x140008b64  push    r15
0x140008b66  mov     rbp, rsp
0x140008b69  sub     rsp, 50h
0x140008b6d  xor     r15d, r15d
0x140008b70  mov     r12, r8
0x140008b73  mov     [rbp+Type], r15d
0x140008b77  mov     rax, rdx
0x140008b7a  mov     [rbp+var_1C], r15d
0x140008b7e  mov     r13, rcx
0x140008b81  mov     [rbp+cbData], r15d
0x140008b85  mov     [rbp+arg_0], r15d
0x140008b89  test    rcx, rcx
0x140008b8c  jz      loc_140008DCE
0x140008b92  test    rax, rax
0x140008b95  jz      loc_140008DCE
0x140008b9b  test    r8, r8
0x140008b9e  jz      loc_140008DCE
0x140008ba4  test    r9, r9
0x140008ba7  jz      loc_140008DCE
0x140008bad  mov     rbx, [rbp+lpValueName]
0x140008bb1  test    rbx, rbx
0x140008bb4  jz      loc_140008DCE
0x140008bba  mov     rdi, [rbp+arg_30]
0x140008bbe  test    rdi, rdi
0x140008bc1  jz      loc_140008DCE
0x140008bc7  mov     r14d, [rbp+arg_28]
0x140008bcb  cmp     r14d, 1
0x140008bcf  ja      short loc_140008BDD
0x140008bd1  cmp     dword ptr [rdi], 1
0x140008bd4  jnz     short loc_140008BDD
0x140008bd6  xor     eax, eax
0x140008bd8  jmp     loc_140008DDC
0x140008bdd  lea     rax, [rbp+cbData]
0x140008be1  xor     r8d, r8d; lpReserved
0x140008be4  mov     [rsp+50h+lpcbData], rax; lpcbData
0x140008be9  lea     r9, [rbp+Type]; lpType
0x140008bed  mov     rdx, rbx; lpValueName
0x140008bf0  mov     [rsp+50h+lpData], r15; lpData
0x140008bf5  call    cs:__imp_RegQueryValueExW
0x140008bfb  mov     esi, eax
0x140008bfd  test    eax, eax
0x140008bff  jz      short loc_140008C0F
0x140008c01  mov     ecx, esi
0x140008c03  call    SaveErrorMessage
0x140008c08  mov     eax, esi
0x140008c0a  jmp     loc_140008DDC
0x140008c0f  lea     rax, [rbp+arg_0]
0x140008c13  xor     r8d, r8d; lpReserved
0x140008c16  mov     [rsp+50h+lpcbData], rax; lpcbData
0x140008c1b  lea     r9, [rbp+var_1C]; lpType
0x140008c1f  mov     rdx, rbx; lpValueName
0x140008c22  mov     [rsp+50h+lpData], r15; lpData
0x140008c27  mov     rcx, r12; hKey
0x140008c2a  call    cs:__imp_RegQueryValueExW
0x140008c30  mov     esi, eax
0x140008c32  test    eax, eax
0x140008c34  jnz     short loc_140008C01
0x140008c36  mov     ecx, [rbp+cbData]
0x140008c39  cmp     r14d, 1
0x140008c3d  ja      short loc_140008C54
0x140008c3f  mov     eax, [rbp+var_1C]
0x140008c42  cmp     [rbp+Type], eax
0x140008c45  jnz     short loc_140008C4C
0x140008c47  cmp     ecx, [rbp+arg_0]
0x140008c4a  jz      short loc_140008C54
0x140008c4c  mov     dword ptr [rdi], 1
0x140008c52  jmp     short loc_140008BD6
0x140008c54  inc     ecx
0x140008c56  mov     esi, 0FFFFFFFEh
0x140008c5b  and     ecx, esi
0x140008c5d  mov     [rbp+cbData], ecx
0x140008c60  add     ecx, 2; dwBytes
0x140008c63  call    AllocateMemory
0x140008c68  mov     [rbp+var_10], rax
0x140008c6c  mov     r15, rax
0x140008c6f  test    rax, rax
0x140008c72  jnz     short loc_140008C7E
0x140008c74  mov     ebx, 0Eh
0x140008c79  jmp     loc_140008DD3
0x140008c7e  mov     ecx, [rbp+arg_0]
0x140008c81  inc     ecx
0x140008c83  and     ecx, esi
0x140008c85  mov     [rbp+arg_0], ecx
0x140008c88  add     ecx, 2; dwBytes
0x140008c8b  call    AllocateMemory
0x140008c90  mov     [rbp+var_8], rax
0x140008c94  test    rax, rax
0x140008c97  jnz     short loc_140008CA4
0x140008c99  lea     rcx, [rbp+var_10]
0x140008c9d  call    FreeMemory
0x140008ca2  jmp     short loc_140008C74
0x140008ca4  lea     rax, [rbp+cbData]
0x140008ca8  xor     r8d, r8d; lpReserved
0x140008cab  mov     [rsp+50h+lpcbData], rax; lpcbData
0x140008cb0  lea     r9, [rbp+Type]; lpType
0x140008cb4  mov     rdx, rbx; lpValueName
0x140008cb7  mov     [rsp+50h+lpData], r15; lpData
0x140008cbc  mov     rcx, r13; hKey
0x140008cbf  call    cs:__imp_RegQueryValueExW
0x140008cc5  mov     esi, eax
0x140008cc7  test    eax, eax
0x140008cc9  jnz     loc_140008DB7
0x140008ccf  mov     r13, [rbp+var_8]
0x140008cd3  lea     rax, [rbp+arg_0]
0x140008cd7  mov     [rsp+50h+lpcbData], rax; lpcbData
0x140008cdc  lea     r9, [rbp+var_1C]; lpType
0x140008ce0  xor     r8d, r8d; lpReserved
0x140008ce3  mov     [rsp+50h+lpData], r13; lpData
0x140008ce8  mov     rdx, rbx; lpValueName
0x140008ceb  mov     rcx, r12; hKey
0x140008cee  call    cs:__imp_RegQueryValueExW
0x140008cf4  mov     esi, eax
0x140008cf6  test    eax, eax
0x140008cf8  jnz     loc_140008DB7
0x140008cfe  mov     r8d, [rbp+Type]
0x140008d02  mov     edx, [rbp+cbData]
0x140008d05  cmp     r8d, [rbp+var_1C]
0x140008d09  jnz     short loc_140008D51
0x140008d0b  cmp     edx, [rbp+arg_0]
0x140008d0e  jnz     short loc_140008D51
0x140008d10  xor     r10d, r10d
0x140008d13  test    edx, edx
0x140008d15  jz      short loc_140008D29
0x140008d17  mov     al, [r10+r13]
0x140008d1b  cmp     [r10+r15], al
0x140008d1f  jnz     short loc_140008D51
0x140008d21  inc     r10d
0x140008d24  cmp     r10d, edx
0x140008d27  jb      short loc_140008D17
0x140008d29  lea     eax, [r14-2]
0x140008d2d  test    eax, 0FFFFFFFDh
0x140008d32  jnz     short loc_140008D99
0x140008d34  mov     rcx, [rbp+arg_8]
0x140008d38  mov     r9, r15
0x140008d3b  mov     dword ptr [rsp+50h+lpcbData], 3
0x140008d43  mov     dword ptr [rsp+50h+lpData], edx
0x140008d47  mov     rdx, rbx
0x140008d4a  call    PrintValue
0x140008d4f  jmp     short loc_140008D99
0x140008d51  lea     eax, [r14-3]
0x140008d55  mov     esi, 1
0x140008d5a  cmp     eax, esi
0x140008d5c  ja      short loc_140008D97
0x140008d5e  mov     rcx, [rbp+arg_8]
0x140008d62  mov     r9, r15
0x140008d65  mov     dword ptr [rsp+50h+lpcbData], esi
0x140008d69  mov     dword ptr [rsp+50h+lpData], edx
0x140008d6d  mov     rdx, rbx
0x140008d70  call    PrintValue
0x140008d75  mov     eax, [rbp+arg_0]
0x140008d78  mov     r9, r13
0x140008d7b  mov     r8d, [rbp+var_1C]
0x140008d7f  mov     rdx, rbx
0x140008d82  mov     rcx, [rbp+arg_18]
0x140008d86  mov     dword ptr [rsp+50h+lpcbData], 2
0x140008d8e  mov     dword ptr [rsp+50h+lpData], eax
0x140008d92  call    PrintValue
0x140008d97  mov     [rdi], esi
0x140008d99  lea     rcx, [rbp+var_10]
0x140008d9d  call    FreeMemory
0x140008da2  lea     rcx, [rbp+var_8]
0x140008da6  call    FreeMemory
0x140008dab  xor     ecx, ecx
0x140008dad  call    SaveErrorMessage
0x140008db2  jmp     loc_140008BD6
0x140008db7  lea     rcx, [rbp+var_10]
0x140008dbb  call    FreeMemory
0x140008dc0  lea     rcx, [rbp+var_8]
0x140008dc4  call    FreeMemory
0x140008dc9  jmp     loc_140008C01
0x140008dce  mov     ebx, 57h ; 'W'
0x140008dd3  mov     ecx, ebx
0x140008dd5  call    SaveErrorMessage
0x140008dda  mov     eax, ebx
0x140008ddc  mov     rbx, [rsp+50h+arg_10]
0x140008de4  add     rsp, 50h
0x140008de8  pop     r15
0x140008dea  pop     r14
0x140008dec  pop     r13
0x140008dee  pop     r12
0x140008df0  pop     rdi
0x140008df1  pop     rsi
0x140008df2  pop     rbp
0x140008df3  retn
```
