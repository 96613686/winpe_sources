# CompareValues

- ea: `0x1400090a8`
- end: `0x14000936c`
- name: `CompareValues`
- size: `708`
- prototype: `__int64 __fastcall(HKEY hKey, __int64, HKEY, __int64, LPCWSTR lpValueName, unsigned int, _DWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140008838`
- `0x140008cbc`

## callees

- `0x140002ce4`
- `0x1400090a8`
- `0x140009b2c`
- `0x14000ce50`
- `0x14000d2d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140009151`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000918c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000922a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000925f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140009151`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000918c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000922a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000925f`

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
              PrintValue(v24, (_DWORD)v9, Type, (_DWORD)lpData, cbData, 3);
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
          PrintValue(v24, (_DWORD)v9, Type, (_DWORD)lpData, cbData, 1);
          PrintValue(v25, (_DWORD)v9, v19, (_DWORD)v16, lpcbData, 2);
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
0x1400090a8  mov     [rsp-38h+arg_10], rbx
0x1400090ad  mov     [rsp-38h+arg_18], r9
0x1400090b2  mov     [rsp-38h+arg_8], rdx
0x1400090b7  push    rbp
0x1400090b8  push    rsi
0x1400090b9  push    rdi
0x1400090ba  push    r12
0x1400090bc  push    r13
0x1400090be  push    r14
0x1400090c0  push    r15
0x1400090c2  mov     rbp, rsp
0x1400090c5  sub     rsp, 50h
0x1400090c9  xor     r15d, r15d
0x1400090cc  mov     r12, r8
0x1400090cf  mov     [rbp+Type], r15d
0x1400090d3  mov     rax, rdx
0x1400090d6  mov     [rbp+var_1C], r15d
0x1400090da  mov     r13, rcx
0x1400090dd  mov     [rbp+cbData], r15d
0x1400090e1  mov     [rbp+arg_0], r15d
0x1400090e5  test    rcx, rcx
0x1400090e8  jz      loc_140009345
0x1400090ee  test    rax, rax
0x1400090f1  jz      loc_140009345
0x1400090f7  test    r8, r8
0x1400090fa  jz      loc_140009345
0x140009100  test    r9, r9
0x140009103  jz      loc_140009345
0x140009109  mov     rbx, [rbp+lpValueName]
0x14000910d  test    rbx, rbx
0x140009110  jz      loc_140009345
0x140009116  mov     rdi, [rbp+arg_30]
0x14000911a  test    rdi, rdi
0x14000911d  jz      loc_140009345
0x140009123  mov     r14d, [rbp+arg_28]
0x140009127  cmp     r14d, 1
0x14000912b  ja      short loc_140009139
0x14000912d  cmp     dword ptr [rdi], 1
0x140009130  jnz     short loc_140009139
0x140009132  xor     eax, eax
0x140009134  jmp     loc_140009353
0x140009139  lea     rax, [rbp+cbData]
0x14000913d  xor     r8d, r8d; lpReserved
0x140009140  mov     [rsp+50h+lpcbData], rax; lpcbData
0x140009145  lea     r9, [rbp+Type]; lpType
0x140009149  mov     rdx, rbx; lpValueName
0x14000914c  mov     [rsp+50h+lpData], r15; lpData
0x140009151  call    cs:__imp_RegQueryValueExW
0x140009158  nop     dword ptr [rax+rax+00h]
0x14000915d  mov     esi, eax
0x14000915f  test    eax, eax
0x140009161  jz      short loc_140009171
0x140009163  mov     ecx, esi
0x140009165  call    SaveErrorMessage
0x14000916a  mov     eax, esi
0x14000916c  jmp     loc_140009353
0x140009171  lea     rax, [rbp+arg_0]
0x140009175  xor     r8d, r8d; lpReserved
0x140009178  mov     [rsp+50h+lpcbData], rax; lpcbData
0x14000917d  lea     r9, [rbp+var_1C]; lpType
0x140009181  mov     rdx, rbx; lpValueName
0x140009184  mov     [rsp+50h+lpData], r15; lpData
0x140009189  mov     rcx, r12; hKey
0x14000918c  call    cs:__imp_RegQueryValueExW
0x140009193  nop     dword ptr [rax+rax+00h]
0x140009198  mov     esi, eax
0x14000919a  test    eax, eax
0x14000919c  jnz     short loc_140009163
0x14000919e  mov     ecx, [rbp+cbData]
0x1400091a1  cmp     r14d, 1
0x1400091a5  ja      short loc_1400091BF
0x1400091a7  mov     eax, [rbp+var_1C]
0x1400091aa  cmp     [rbp+Type], eax
0x1400091ad  jnz     short loc_1400091B4
0x1400091af  cmp     ecx, [rbp+arg_0]
0x1400091b2  jz      short loc_1400091BF
0x1400091b4  mov     dword ptr [rdi], 1
0x1400091ba  jmp     loc_140009132
0x1400091bf  inc     ecx
0x1400091c1  mov     esi, 0FFFFFFFEh
0x1400091c6  and     ecx, esi
0x1400091c8  mov     [rbp+cbData], ecx
0x1400091cb  add     ecx, 2; dwBytes
0x1400091ce  call    AllocateMemory
0x1400091d3  mov     [rbp+var_10], rax
0x1400091d7  mov     r15, rax
0x1400091da  test    rax, rax
0x1400091dd  jnz     short loc_1400091E9
0x1400091df  mov     ebx, 0Eh
0x1400091e4  jmp     loc_14000934A
0x1400091e9  mov     ecx, [rbp+arg_0]
0x1400091ec  inc     ecx
0x1400091ee  and     ecx, esi
0x1400091f0  mov     [rbp+arg_0], ecx
0x1400091f3  add     ecx, 2; dwBytes
0x1400091f6  call    AllocateMemory
0x1400091fb  mov     [rbp+var_8], rax
0x1400091ff  test    rax, rax
0x140009202  jnz     short loc_14000920F
0x140009204  lea     rcx, [rbp+var_10]
0x140009208  call    FreeMemory
0x14000920d  jmp     short loc_1400091DF
0x14000920f  lea     rax, [rbp+cbData]
0x140009213  xor     r8d, r8d; lpReserved
0x140009216  mov     [rsp+50h+lpcbData], rax; lpcbData
0x14000921b  lea     r9, [rbp+Type]; lpType
0x14000921f  mov     rdx, rbx; lpValueName
0x140009222  mov     [rsp+50h+lpData], r15; lpData
0x140009227  mov     rcx, r13; hKey
0x14000922a  call    cs:__imp_RegQueryValueExW
0x140009231  nop     dword ptr [rax+rax+00h]
0x140009236  mov     esi, eax
0x140009238  test    eax, eax
0x14000923a  jnz     loc_14000932E
0x140009240  mov     r13, [rbp+var_8]
0x140009244  lea     rax, [rbp+arg_0]
0x140009248  mov     [rsp+50h+lpcbData], rax; lpcbData
0x14000924d  lea     r9, [rbp+var_1C]; lpType
0x140009251  xor     r8d, r8d; lpReserved
0x140009254  mov     [rsp+50h+lpData], r13; lpData
0x140009259  mov     rdx, rbx; lpValueName
0x14000925c  mov     rcx, r12; hKey
0x14000925f  call    cs:__imp_RegQueryValueExW
0x140009266  nop     dword ptr [rax+rax+00h]
0x14000926b  mov     esi, eax
0x14000926d  test    eax, eax
0x14000926f  jnz     loc_14000932E
0x140009275  mov     r8d, [rbp+Type]
0x140009279  mov     edx, [rbp+cbData]
0x14000927c  cmp     r8d, [rbp+var_1C]
0x140009280  jnz     short loc_1400092C8
0x140009282  cmp     edx, [rbp+arg_0]
0x140009285  jnz     short loc_1400092C8
0x140009287  xor     r10d, r10d
0x14000928a  test    edx, edx
0x14000928c  jz      short loc_1400092A0
0x14000928e  mov     al, [r10+r13]
0x140009292  cmp     [r10+r15], al
0x140009296  jnz     short loc_1400092C8
0x140009298  inc     r10d
0x14000929b  cmp     r10d, edx
0x14000929e  jb      short loc_14000928E
0x1400092a0  lea     eax, [r14-2]
0x1400092a4  test    eax, 0FFFFFFFDh
0x1400092a9  jnz     short loc_140009310
0x1400092ab  mov     rcx, [rbp+arg_8]
0x1400092af  mov     r9, r15
0x1400092b2  mov     dword ptr [rsp+50h+lpcbData], 3
0x1400092ba  mov     dword ptr [rsp+50h+lpData], edx
0x1400092be  mov     rdx, rbx
0x1400092c1  call    PrintValue
0x1400092c6  jmp     short loc_140009310
0x1400092c8  lea     eax, [r14-3]
0x1400092cc  mov     esi, 1
0x1400092d1  cmp     eax, esi
0x1400092d3  ja      short loc_14000930E
0x1400092d5  mov     rcx, [rbp+arg_8]
0x1400092d9  mov     r9, r15
0x1400092dc  mov     dword ptr [rsp+50h+lpcbData], esi
0x1400092e0  mov     dword ptr [rsp+50h+lpData], edx
0x1400092e4  mov     rdx, rbx
0x1400092e7  call    PrintValue
0x1400092ec  mov     eax, [rbp+arg_0]
0x1400092ef  mov     r9, r13
0x1400092f2  mov     r8d, [rbp+var_1C]
0x1400092f6  mov     rdx, rbx
0x1400092f9  mov     rcx, [rbp+arg_18]
0x1400092fd  mov     dword ptr [rsp+50h+lpcbData], 2
0x140009305  mov     dword ptr [rsp+50h+lpData], eax
0x140009309  call    PrintValue
0x14000930e  mov     [rdi], esi
0x140009310  lea     rcx, [rbp+var_10]
0x140009314  call    FreeMemory
0x140009319  lea     rcx, [rbp+var_8]
0x14000931d  call    FreeMemory
0x140009322  xor     ecx, ecx
0x140009324  call    SaveErrorMessage
0x140009329  jmp     loc_140009132
0x14000932e  lea     rcx, [rbp+var_10]
0x140009332  call    FreeMemory
0x140009337  lea     rcx, [rbp+var_8]
0x14000933b  call    FreeMemory
0x140009340  jmp     loc_140009163
0x140009345  mov     ebx, 57h ; 'W'
0x14000934a  mov     ecx, ebx
0x14000934c  call    SaveErrorMessage
0x140009351  mov     eax, ebx
0x140009353  mov     rbx, [rsp+50h+arg_10]
0x14000935b  add     rsp, 50h
0x14000935f  pop     r15
0x140009361  pop     r14
0x140009363  pop     r13
0x140009365  pop     r12
0x140009367  pop     rdi
0x140009368  pop     rsi
0x140009369  pop     rbp
0x14000936a  retn
```
