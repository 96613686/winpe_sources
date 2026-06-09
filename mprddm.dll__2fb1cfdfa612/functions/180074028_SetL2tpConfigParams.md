# SetL2tpConfigParams

- ea: `0x180074028`
- end: `0x180074194`
- name: `SetL2tpConfigParams`
- size: `364`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800059f0`

## callees

- `0x180074028`
- `0x18007419c`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800740e5`
- `ADVAPI32!RegSetValueExW` at `0x180074121`
- `ADVAPI32!RegSetValueExW` at `0x18007417b`
- `ADVAPI32!RegSetValueExW` at `0x1800740e5`
- `ADVAPI32!RegSetValueExW` at `0x180074121`
- `ADVAPI32!RegSetValueExW` at `0x18007417b`
- `ADVAPI32!RegDeleteKeyExW` at `0x18007415b`
- `ADVAPI32!RegDeleteKeyExW` at `0x18007415b`

## pseudocode

```c
__int64 __fastcall SetL2tpConfigParams(HKEY hKey, char a2, __int64 a3)
{
  __int64 v5; // r9
  const BYTE *lpData; // rbp
  unsigned int v8; // ebx
  unsigned int v9; // eax
  __int64 v10; // r8
  unsigned int v11; // eax
  __int64 v12; // rdx
  LPCWSTR lpValueName; // [rsp+30h] [rbp-68h]
  BYTE *v15[12]; // [rsp+38h] [rbp-60h]

  lpValueName = L"idleTimeout";
  v15[0] = (BYTE *)a3;
  v15[1] = (BYTE *)L"saLifeTime";
  LODWORD(v5) = 0;
  v15[2] = (BYTE *)(a3 + 8);
  v15[3] = (BYTE *)L"saDataSize";
  v15[4] = (BYTE *)(a3 + 12);
  if ( a2 != 1 && a2 != 2 )
  {
    if ( a2 == 3 || (unsigned int)(a2 - 4) < 2 )
    {
      lpData = (const BYTE *)(a3 + 4);
      if ( *(_DWORD *)(a3 + 4) <= 3u )
      {
        v8 = 0;
        while ( 1 )
        {
          v9 = RegSetValueExW(hKey, (LPCWSTR)v15[2 * v8 - 1], 0, 4u, v15[2 * v8], 4u);
          v5 = v9;
          if ( v9 )
            break;
          if ( ++v8 >= 3 )
          {
            if ( a2 < 5
              || (v11 = RegSetValueExW(hKey, L"mmSaLifeTime", 0, 4u, (const BYTE *)(a3 + 24), 4u), (v5 = v11) == 0) )
            {
              if ( a2 >= 3 )
              {
                v12 = *(_QWORD *)(a3 + 16);
                if ( v12 )
                {
                  LODWORD(v5) = SetL2tpCustomPolicy(hKey, v12, v10, v5);
                  if ( (_DWORD)v5 )
                    return (unsigned int)v5;
                }
                else
                {
                  RegDeleteKeyExW(hKey, L"L2TPCustomPolicy", 0, 0);
                }
                LODWORD(v5) = RegSetValueExW(hKey, L"EncryptionType", 0, 4u, lpData, 4u);
              }
            }
            return (unsigned int)v5;
          }
        }
      }
      else
      {
        LODWORD(v5) = 87;
      }
    }
    else
    {
      LODWORD(v5) = 50;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180074028  mov     r11, rsp
0x18007402b  push    rbx
0x18007402c  push    rbp
0x18007402d  push    rsi
0x18007402e  push    rdi
0x18007402f  push    r14
0x180074031  push    r15
0x180074033  sub     rsp, 68h
0x180074037  lea     rax, aIdletimeout; "idleTimeout"
0x18007403e  movsx   r14d, dl
0x180074042  mov     [r11-68h], rax
0x180074046  mov     rsi, rcx
0x180074049  lea     rax, aSalifetime; "saLifeTime"
0x180074050  mov     [r11-60h], r8
0x180074054  mov     [r11-58h], rax
0x180074058  xor     r9d, r9d
0x18007405b  lea     rax, [r8+8]
0x18007405f  mov     ecx, r14d
0x180074062  mov     [r11-50h], rax
0x180074066  lea     rax, aSadatasize; "saDataSize"
0x18007406d  mov     [r11-48h], rax
0x180074071  lea     rax, [r8+0Ch]
0x180074075  mov     [r11-40h], rax
0x180074079  mov     rdi, r8
0x18007407c  sub     ecx, 1
0x18007407f  jz      loc_180074184
0x180074085  sub     ecx, 1
0x180074088  jz      loc_180074184
0x18007408e  sub     ecx, 1
0x180074091  jz      short loc_1800740A8
0x180074093  sub     ecx, 1
0x180074096  jz      short loc_1800740A8
0x180074098  cmp     ecx, 1
0x18007409b  jz      short loc_1800740A8
0x18007409d  mov     r9d, 32h ; '2'
0x1800740a3  jmp     loc_180074184
0x1800740a8  lea     rbp, [r8+4]
0x1800740ac  cmp     dword ptr [rbp+0], 3
0x1800740b0  jbe     short loc_1800740BD
0x1800740b2  mov     r9d, 57h ; 'W'
0x1800740b8  jmp     loc_180074184
0x1800740bd  xor     ebx, ebx
0x1800740bf  lea     r15d, [rbx+4]
0x1800740c3  mov     edx, ebx
0x1800740c5  mov     r9d, r15d; dwType
0x1800740c8  add     rdx, rdx
0x1800740cb  mov     [rsp+98h+cbData], r15d; cbData
0x1800740d0  xor     r8d, r8d; Reserved
0x1800740d3  mov     rcx, rsi; hKey
0x1800740d6  mov     rax, [rsp+rdx*8+98h+var_60]
0x1800740db  mov     rdx, [rsp+rdx*8+98h+lpValueName]; lpValueName
0x1800740e0  mov     [rsp+98h+lpData], rax; lpData
0x1800740e5  call    cs:__imp_RegSetValueExW
0x1800740eb  mov     r9d, eax
0x1800740ee  test    eax, eax
0x1800740f0  jnz     loc_180074184
0x1800740f6  inc     ebx
0x1800740f8  cmp     ebx, 3
0x1800740fb  jb      short loc_1800740C3
0x1800740fd  cmp     r14b, 5
0x180074101  jl      short loc_18007412E
0x180074103  lea     rax, [rdi+18h]
0x180074107  mov     [rsp+98h+cbData], r15d; cbData
0x18007410c  mov     r9d, r15d; dwType
0x18007410f  mov     [rsp+98h+lpData], rax; lpData
0x180074114  xor     r8d, r8d; Reserved
0x180074117  lea     rdx, aMmsalifetime; "mmSaLifeTime"
0x18007411e  mov     rcx, rsi; hKey
0x180074121  call    cs:__imp_RegSetValueExW
0x180074127  mov     r9d, eax
0x18007412a  test    eax, eax
0x18007412c  jnz     short loc_180074184
0x18007412e  cmp     r14b, 3
0x180074132  jl      short loc_180074184
0x180074134  mov     rdx, [rdi+10h]
0x180074138  mov     rcx, rsi; hKey
0x18007413b  test    rdx, rdx
0x18007413e  jz      short loc_18007414E
0x180074140  call    SetL2tpCustomPolicy
0x180074145  mov     r9d, eax
0x180074148  test    eax, eax
0x18007414a  jnz     short loc_180074184
0x18007414c  jmp     short loc_180074161
0x18007414e  xor     r9d, r9d; Reserved
0x180074151  lea     rdx, aL2tpcustompoli; "L2TPCustomPolicy"
0x180074158  xor     r8d, r8d; samDesired
0x18007415b  call    cs:__imp_RegDeleteKeyExW
0x180074161  mov     [rsp+98h+cbData], r15d; cbData
0x180074166  lea     rdx, aEncryptiontype; "EncryptionType"
0x18007416d  mov     r9d, r15d; dwType
0x180074170  mov     [rsp+98h+lpData], rbp; lpData
0x180074175  xor     r8d, r8d; Reserved
0x180074178  mov     rcx, rsi; hKey
0x18007417b  call    cs:__imp_RegSetValueExW
0x180074181  mov     r9d, eax
0x180074184  mov     eax, r9d
0x180074187  add     rsp, 68h
0x18007418b  pop     r15
0x18007418d  pop     r14
0x18007418f  pop     rdi
0x180074190  pop     rsi
0x180074191  pop     rbp
0x180074192  pop     rbx
0x180074193  retn
```
