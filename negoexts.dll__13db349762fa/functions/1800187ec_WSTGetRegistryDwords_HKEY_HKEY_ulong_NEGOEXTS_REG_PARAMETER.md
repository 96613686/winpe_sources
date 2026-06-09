# WSTGetRegistryDwords(HKEY__ *,HKEY__ *,ulong,_NEGOEXTS_REG_PARAMETER *)

- ea: `0x1800187ec`
- end: `0x180018912`
- name: `?WSTGetRegistryDwords@@YAKPEAUHKEY__@@0KPEAU_NEGOEXTS_REG_PARAMETER@@@Z`
- size: `294`
- prototype: `unsigned int __fastcall(HKEY hKey, HKEY, unsigned int, struct _NEGOEXTS_REG_PARAMETER *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000d0a8`

## callees

- `0x1800187ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018877`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800188b3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018877`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800188b3`

## pseudocode

```c
__int64 __fastcall WSTGetRegistryDwords(HKEY hKey, HKEY a2, DWORD a3, struct _NEGOEXTS_REG_PARAMETER *a4)
{
  __int64 v7; // rbx
  __int64 v8; // r15
  bool v9; // zf
  HKEY v10; // rsi
  LSTATUS v11; // eax
  const WCHAR *v12; // rdx
  int v13; // eax
  BYTE Data[4]; // [rsp+30h] [rbp-10h] BYREF
  DWORD Type[3]; // [rsp+34h] [rbp-Ch] BYREF
  DWORD cbData; // [rsp+80h] [rbp+40h] BYREF

  cbData = a3;
  v7 = 160;
  v8 = 5;
  do
  {
    --v8;
    cbData = 4;
    v7 -= 32;
    Type[0] = 0;
    v9 = *(_DWORD *)((char *)a4 + v7 + 24) == 0;
    *(_DWORD *)Data = 0;
    if ( v9 || !a2 )
    {
      if ( !hKey )
        goto LABEL_16;
      v10 = hKey;
    }
    else
    {
      v10 = a2;
    }
    v11 = RegQueryValueExW(v10, *(LPCWSTR *)((char *)a4 + v7), 0, Type, Data, &cbData);
    if ( v11 == 2 )
    {
      if ( v10 != a2 )
        goto LABEL_16;
      v12 = *(const WCHAR **)((char *)a4 + v7);
      cbData = 4;
      v11 = RegQueryValueExW(hKey, v12, 0, Type, Data, &cbData);
    }
    if ( v11 || Type[0] != 4 || cbData != 4 )
    {
LABEL_16:
      v13 = *(_DWORD *)((char *)a4 + v7 + 16);
      goto LABEL_17;
    }
    if ( *(_DWORD *)((char *)a4 + v7 + 20) )
    {
      **(_DWORD **)((char *)a4 + v7 + 8) = *(_DWORD *)Data == 0;
      continue;
    }
    v13 = *(_DWORD *)Data;
LABEL_17:
    **(_DWORD **)((char *)a4 + v7 + 8) = v13;
  }
  while ( v8 );
  return 0;
}

```

## disassembly

```asm
0x1800187ec  mov     [rsp-28h+arg_0], rbx
0x1800187f1  mov     [rsp-28h+arg_8], rsi
0x1800187f6  mov     [rsp-28h+cbData], r8d
0x1800187fb  push    rbp
0x1800187fc  push    rdi
0x1800187fd  push    r12
0x1800187ff  push    r14
0x180018801  push    r15
0x180018803  mov     rbp, rsp
0x180018806  sub     rsp, 40h
0x18001880a  mov     rdi, r9
0x18001880d  mov     r14, rdx
0x180018810  mov     r12, rcx
0x180018813  mov     ebx, 0A0h
0x180018818  mov     r15d, 5
0x18001881e  dec     r15
0x180018821  mov     [rbp+cbData], 4
0x180018828  lea     rbx, [rbx-20h]
0x18001882c  mov     [rbp+Type], 0
0x180018833  cmp     dword ptr [rbx+rdi+18h], 0
0x180018838  mov     dword ptr [rbp+Data], 0
0x18001883f  jz      short loc_18001884B
0x180018841  test    r14, r14
0x180018844  jz      short loc_18001884B
0x180018846  mov     rsi, r14
0x180018849  jmp     short loc_180018857
0x18001884b  test    r12, r12
0x18001884e  jz      loc_1800188E5
0x180018854  mov     rsi, r12
0x180018857  mov     rdx, [rbx+rdi]; lpValueName
0x18001885b  lea     rax, [rbp+cbData]
0x18001885f  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180018864  lea     r9, [rbp+Type]; lpType
0x180018868  lea     rax, [rbp+Data]
0x18001886c  xor     r8d, r8d; lpReserved
0x18001886f  mov     rcx, rsi; hKey
0x180018872  mov     [rsp+40h+lpData], rax; lpData
0x180018877  call    cs:__imp_RegQueryValueExW
0x18001887d  cmp     eax, 2
0x180018880  jnz     short loc_1800188B9
0x180018882  cmp     rsi, r14
0x180018885  jnz     short loc_1800188E5
0x180018887  test    rsi, rsi
0x18001888a  jz      short loc_1800188E5
0x18001888c  mov     rdx, [rbx+rdi]; lpValueName
0x180018890  lea     rax, [rbp+cbData]
0x180018894  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180018899  lea     r9, [rbp+Type]; lpType
0x18001889d  lea     rax, [rbp+Data]
0x1800188a1  mov     [rbp+cbData], 4
0x1800188a8  xor     r8d, r8d; lpReserved
0x1800188ab  mov     [rsp+40h+lpData], rax; lpData
0x1800188b0  mov     rcx, r12; hKey
0x1800188b3  call    cs:__imp_RegQueryValueExW
0x1800188b9  test    eax, eax
0x1800188bb  jnz     short loc_1800188E5
0x1800188bd  cmp     [rbp+Type], 4
0x1800188c1  jnz     short loc_1800188E5
0x1800188c3  cmp     [rbp+cbData], 4
0x1800188c7  jnz     short loc_1800188E5
0x1800188c9  cmp     [rbx+rdi+14h], eax
0x1800188cd  jz      short loc_1800188E0
0x1800188cf  mov     rax, [rbx+rdi+8]
0x1800188d4  xor     ecx, ecx
0x1800188d6  cmp     dword ptr [rbp+Data], ecx
0x1800188d9  setz    cl
0x1800188dc  mov     [rax], ecx
0x1800188de  jmp     short loc_1800188F0
0x1800188e0  mov     eax, dword ptr [rbp+Data]
0x1800188e3  jmp     short loc_1800188E9
0x1800188e5  mov     eax, [rbx+rdi+10h]
0x1800188e9  mov     rcx, [rbx+rdi+8]
0x1800188ee  mov     [rcx], eax
0x1800188f0  test    r15, r15
0x1800188f3  jnz     loc_18001881E
0x1800188f9  mov     rbx, [rsp+40h+arg_0]
0x1800188fe  xor     eax, eax
0x180018900  mov     rsi, [rsp+40h+arg_8]
0x180018905  add     rsp, 40h
0x180018909  pop     r15
0x18001890b  pop     r14
0x18001890d  pop     r12
0x18001890f  pop     rdi
0x180018910  pop     rbp
0x180018911  retn
```
