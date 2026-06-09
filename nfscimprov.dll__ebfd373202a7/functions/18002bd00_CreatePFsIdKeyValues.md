# CreatePFsIdKeyValues

- ea: `0x18002bd00`
- end: `0x18002be61`
- name: `CreatePFsIdKeyValues`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002bb5c`

## callees

- `0x18002bd00`
- `0x18002c5d4`
- `0x18002d1f8`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18002bd7a`
- `ADVAPI32!RegSetValueExW` at `0x18002be42`
- `ADVAPI32!RegSetValueExW` at `0x18002bd7a`
- `ADVAPI32!RegSetValueExW` at `0x18002be42`
- `CLUSAPI!ClusterRegSetValue` at `0x18002bd5b`
- `CLUSAPI!ClusterRegSetValue` at `0x18002be24`
- `CLUSAPI!ClusterRegSetValue` at `0x18002bd5b`
- `CLUSAPI!ClusterRegSetValue` at `0x18002be24`

## pseudocode

```c
DWORD __fastcall CreatePFsIdKeyValues(HKEY a1, HKEY a2, char a3, _DWORD *a4, BOOL Data, BYTE *lpData, char *a7)
{
  char *v7; // r13
  char v11; // bp
  DWORD result; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  char v15; // di
  BYTE *v16; // rbx

  v7 = a7;
  v11 = *a7;
  Data = Data;
  if ( a3 )
    result = ClusterRegSetValue(a2, L"TerminalNode", 4u, (const BYTE *)&Data, 4u);
  else
    result = RegSetValueExW(a2, L"TerminalNode", 0, 4u, (const BYTE *)&Data, 4u);
  if ( a4 )
  {
    v15 = 0;
    if ( !result )
    {
      v16 = lpData;
      while ( 1 )
      {
        if ( ++*(_DWORD *)v16 == -1 )
          goto LABEL_16;
        if ( *(_DWORD *)v16 )
        {
          if ( v11 )
            goto LABEL_12;
LABEL_16:
          if ( result )
            return result;
          if ( !v15 )
          {
LABEL_18:
            *a4 = *(_DWORD *)v16;
            if ( a3 )
              result = ClusterRegSetValue(a2, L"Id", 4u, v16, 4u);
            else
              result = RegSetValueExW(a2, L"Id", 0, 4u, v16, 4u);
            goto LABEL_22;
          }
        }
        else
        {
          *(_DWORD *)v16 = 1;
          if ( v15 )
            return 50;
          v11 = 1;
          LOBYTE(v14) = 1;
          LOBYTE(v13) = a3;
          v15 = 1;
          result = SetPFsIdSequenceNumberDuplicateCheck(a1, v13, v14);
LABEL_12:
          if ( result )
            return result;
          result = LookupPfsIdDuplicate(a1);
          if ( result != 183 )
          {
            if ( !result )
              goto LABEL_18;
            goto LABEL_16;
          }
          result = 0;
          v15 = 1;
        }
      }
    }
  }
  else
  {
LABEL_22:
    if ( !result )
      *v7 = v11;
  }
  return result;
}

```

## disassembly

```asm
0x18002bd00  mov     r11, rsp
0x18002bd03  mov     [r11+8], rcx
0x18002bd07  push    rbx
0x18002bd08  push    rbp
0x18002bd09  push    rsi
0x18002bd0a  push    rdi
0x18002bd0b  push    r12
0x18002bd0d  push    r13
0x18002bd0f  push    r14
0x18002bd11  push    r15
0x18002bd13  sub     rsp, 38h
0x18002bd17  mov     r13, [rsp+78h+arg_30]
0x18002bd1f  xor     eax, eax
0x18002bd21  cmp     byte ptr [rsp+78h+Data], al
0x18002bd28  mov     r15, rdx
0x18002bd2b  mov     r12, r9
0x18002bd2e  lea     rdx, aTerminalnode; "TerminalNode"
0x18002bd35  setnz   al
0x18002bd38  mov     r14b, r8b
0x18002bd3b  mov     bpl, [r13+0]
0x18002bd3f  mov     esi, 4
0x18002bd44  mov     [r11+28h], eax
0x18002bd48  mov     rcx, r15; hKey
0x18002bd4b  test    r8b, r8b
0x18002bd4e  jz      short loc_18002BD63
0x18002bd50  lea     r9, [r11+28h]; lpData
0x18002bd54  mov     [rsp+78h+cbData], esi; cbData
0x18002bd58  mov     r8d, esi; dwType
0x18002bd5b  call    cs:__imp_ClusterRegSetValue
0x18002bd61  jmp     short loc_18002BD80
0x18002bd63  lea     rax, [rsp+78h+Data]
0x18002bd6b  mov     [rsp+78h+var_50], esi; cbData
0x18002bd6f  mov     r9d, esi; dwType
0x18002bd72  mov     qword ptr [rsp+78h+cbData], rax; lpData
0x18002bd77  xor     r8d, r8d; Reserved
0x18002bd7a  call    cs:__imp_RegSetValueExW
0x18002bd80  test    r12, r12
0x18002bd83  jz      loc_18002BE48
0x18002bd89  xor     dil, dil
0x18002bd8c  test    eax, eax
0x18002bd8e  jnz     loc_18002BE50
0x18002bd94  mov     rbx, [rsp+78h+lpData]
0x18002bd9c  inc     dword ptr [rbx]
0x18002bd9e  cmp     dword ptr [rbx], 0FFFFFFFFh
0x18002bda1  jz      short loc_18002BDFC
0x18002bda3  cmp     dword ptr [rbx], 0
0x18002bda6  jnz     short loc_18002BDCE
0x18002bda8  mov     dword ptr [rbx], 1
0x18002bdae  test    dil, dil
0x18002bdb1  jnz     short loc_18002BE2C
0x18002bdb3  mov     rcx, [rsp+78h+hKey]
0x18002bdbb  mov     bpl, 1
0x18002bdbe  mov     r8b, bpl
0x18002bdc1  mov     dl, r14b
0x18002bdc4  mov     dil, bpl
0x18002bdc7  call    SetPFsIdSequenceNumberDuplicateCheck
0x18002bdcc  jmp     short loc_18002BDD3
0x18002bdce  test    bpl, bpl
0x18002bdd1  jz      short loc_18002BDFC
0x18002bdd3  test    eax, eax
0x18002bdd5  jnz     short loc_18002BE50
0x18002bdd7  mov     r8d, [rbx]
0x18002bdda  mov     dl, r14b
0x18002bddd  mov     rcx, [rsp+78h+hKey]; hKey
0x18002bde5  call    LookupPfsIdDuplicate
0x18002bdea  cmp     eax, 0B7h
0x18002bdef  jnz     short loc_18002BDF8
0x18002bdf1  xor     eax, eax
0x18002bdf3  mov     dil, 1
0x18002bdf6  jmp     short loc_18002BD9C
0x18002bdf8  test    eax, eax
0x18002bdfa  jz      short loc_18002BE05
0x18002bdfc  test    eax, eax
0x18002bdfe  jnz     short loc_18002BE50
0x18002be00  test    dil, dil
0x18002be03  jnz     short loc_18002BD9C
0x18002be05  mov     eax, [rbx]
0x18002be07  lea     rdx, aId; "Id"
0x18002be0e  mov     [r12], eax
0x18002be12  mov     rcx, r15; hKey
0x18002be15  test    r14b, r14b
0x18002be18  jz      short loc_18002BE33
0x18002be1a  mov     r9, rbx; lpData
0x18002be1d  mov     [rsp+78h+cbData], esi; cbData
0x18002be21  mov     r8d, esi; dwType
0x18002be24  call    cs:__imp_ClusterRegSetValue
0x18002be2a  jmp     short loc_18002BE48
0x18002be2c  mov     eax, 32h ; '2'
0x18002be31  jmp     short loc_18002BE50
0x18002be33  mov     [rsp+78h+var_50], esi; cbData
0x18002be37  mov     r9d, esi; dwType
0x18002be3a  xor     r8d, r8d; Reserved
0x18002be3d  mov     qword ptr [rsp+78h+cbData], rbx; lpData
0x18002be42  call    cs:__imp_RegSetValueExW
0x18002be48  test    eax, eax
0x18002be4a  jnz     short loc_18002BE50
0x18002be4c  mov     [r13+0], bpl
0x18002be50  add     rsp, 38h
0x18002be54  pop     r15
0x18002be56  pop     r14
0x18002be58  pop     r13
0x18002be5a  pop     r12
0x18002be5c  pop     rdi
0x18002be5d  pop     rsi
0x18002be5e  pop     rbp
0x18002be5f  pop     rbx
0x18002be60  retn
```
