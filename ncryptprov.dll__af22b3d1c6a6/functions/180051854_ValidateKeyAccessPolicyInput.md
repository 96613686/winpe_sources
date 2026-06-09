# ValidateKeyAccessPolicyInput

- ea: `0x180051854`
- end: `0x1800519c8`
- name: `ValidateKeyAccessPolicyInput`
- size: `372`
- prototype: `__int64 __fastcall(_DWORD *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180050eb8`

## callees

- `0x18000af80`
- `0x180051854`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800518ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051921`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800518ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051921`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051993`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800519a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180051993`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800519a9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800518da`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180051911`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800518da`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180051911`

## string_xrefs

- `0x18005197b`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`

## pseudocode

```c
__int64 __fastcall ValidateKeyAccessPolicyInput(_DWORD *a1, unsigned int a2, __int64 a3)
{
  __int64 v5; // rbx
  unsigned int v6; // ecx
  unsigned int v7; // r8d
  __int64 v8; // r9
  DWORD LastError; // eax
  const char *v10; // rdx
  unsigned int v11; // ebx
  LPWSTR StringSid; // [rsp+30h] [rbp+8h] BYREF
  LPWSTR v14; // [rsp+48h] [rbp+20h] BYREF

  StringSid = 0;
  v14 = 0;
  if ( !a1 || a2 < 0x10 )
  {
    v8 = 2772;
    goto LABEL_16;
  }
  if ( *a1 != 1
    || (a1[1] & 0xFFFFFFFE) != 0
    || (v5 = (unsigned int)a1[2], v6 = v5 + 16, (unsigned int)v5 >= 0xFFFFFFF0)
    || (v7 = v6 + a1[3], v7 < v6) )
  {
    v8 = 2783;
    goto LABEL_16;
  }
  if ( a2 < v7 )
  {
    v8 = 2790;
LABEL_16:
    LastError = -2146893785;
    v10 = "Status";
    goto LABEL_17;
  }
  if ( ConvertSidToStringSidW(a1 + 4, &StringSid) )
  {
    if ( ConvertSidToStringSidW((char *)a1 + v5 + 16, &v14) )
    {
      v11 = 0;
      *(_DWORD *)a3 = *a1;
      *(_DWORD *)(a3 + 4) = a1[1];
      *(_QWORD *)(a3 + 8) = StringSid;
      *(_QWORD *)(a3 + 16) = v14;
      return v11;
    }
    LastError = GetLastError();
    v10 = "dwError";
    v8 = 2810;
  }
  else
  {
    LastError = GetLastError();
    v10 = "dwError";
    v8 = 2802;
  }
LABEL_17:
  v11 = -2146893785;
  DebugTraceError(LastError, v10, "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c", v8);
  if ( StringSid )
    LocalFree(StringSid);
  if ( v14 )
    LocalFree(v14);
  return v11;
}

```

## disassembly

```asm
0x180051854  mov     rax, rsp
0x180051857  mov     [rax+10h], rbx
0x18005185b  mov     [rax+18h], rsi
0x18005185f  push    rdi
0x180051860  sub     rsp, 20h
0x180051864  mov     qword ptr [rax+8], 0
0x18005186c  mov     rsi, r8
0x18005186f  mov     qword ptr [rax+20h], 0
0x180051877  mov     rdi, rcx
0x18005187a  test    rcx, rcx
0x18005187d  jz      loc_180051964
0x180051883  cmp     edx, 10h
0x180051886  jb      loc_180051964
0x18005188c  cmp     dword ptr [rcx], 1
0x18005188f  jnz     loc_18005195C
0x180051895  test    dword ptr [rcx+4], 0FFFFFFFEh
0x18005189c  jnz     loc_18005195C
0x1800518a2  mov     ebx, [rcx+8]
0x1800518a5  lea     ecx, [rbx+10h]
0x1800518a8  cmp     ecx, 10h
0x1800518ab  jb      loc_18005195C
0x1800518b1  mov     r8d, [rdi+0Ch]
0x1800518b5  add     r8d, ecx
0x1800518b8  cmp     r8d, ecx
0x1800518bb  jb      loc_18005195C
0x1800518c1  cmp     edx, r8d
0x1800518c4  jnb     short loc_1800518D1
0x1800518c6  mov     r9d, 0AE6h
0x1800518cc  jmp     loc_18005196A
0x1800518d1  lea     rcx, [rdi+10h]; Sid
0x1800518d5  lea     rdx, [rsp+28h+StringSid]; StringSid
0x1800518da  call    cs:__imp_ConvertSidToStringSidW
0x1800518e1  nop     dword ptr [rax+rax+00h]
0x1800518e6  test    eax, eax
0x1800518e8  jnz     short loc_180051905
0x1800518ea  call    cs:__imp_GetLastError
0x1800518f1  nop     dword ptr [rax+rax+00h]
0x1800518f6  lea     rdx, aDwerror; "dwError"
0x1800518fd  mov     r9d, 0AF2h
0x180051903  jmp     short loc_180051976
0x180051905  lea     rcx, [rbx+10h]
0x180051909  add     rcx, rdi; Sid
0x18005190c  lea     rdx, [rsp+28h+arg_18]; StringSid
0x180051911  call    cs:__imp_ConvertSidToStringSidW
0x180051918  nop     dword ptr [rax+rax+00h]
0x18005191d  test    eax, eax
0x18005191f  jnz     short loc_18005193C
0x180051921  call    cs:__imp_GetLastError
0x180051928  nop     dword ptr [rax+rax+00h]
0x18005192d  lea     rdx, aDwerror; "dwError"
0x180051934  mov     r9d, 0AFAh
0x18005193a  jmp     short loc_180051976
0x18005193c  mov     eax, [rdi]
0x18005193e  xor     ebx, ebx
0x180051940  mov     [rsi], eax
0x180051942  mov     eax, [rdi+4]
0x180051945  mov     [rsi+4], eax
0x180051948  mov     rax, [rsp+28h+StringSid]
0x18005194d  mov     [rsi+8], rax
0x180051951  mov     rax, [rsp+28h+arg_18]
0x180051956  mov     [rsi+10h], rax
0x18005195a  jmp     short loc_1800519B5
0x18005195c  mov     r9d, 0ADFh
0x180051962  jmp     short loc_18005196A
0x180051964  mov     r9d, 0AD4h
0x18005196a  mov     eax, 80090027h
0x18005196f  lea     rdx, aStatus; "Status"
0x180051976  mov     ebx, 80090027h
0x18005197b  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180051982  mov     ecx, eax
0x180051984  call    DebugTraceError
0x180051989  mov     rcx, [rsp+28h+StringSid]; hMem
0x18005198e  test    rcx, rcx
0x180051991  jz      short loc_18005199F
0x180051993  call    cs:__imp_LocalFree
0x18005199a  nop     dword ptr [rax+rax+00h]
0x18005199f  mov     rcx, [rsp+28h+arg_18]; hMem
0x1800519a4  test    rcx, rcx
0x1800519a7  jz      short loc_1800519B5
0x1800519a9  call    cs:__imp_LocalFree
0x1800519b0  nop     dword ptr [rax+rax+00h]
0x1800519b5  mov     rsi, [rsp+28h+arg_10]
0x1800519ba  mov     eax, ebx
0x1800519bc  mov     rbx, [rsp+28h+arg_8]
0x1800519c1  add     rsp, 20h
0x1800519c5  pop     rdi
0x1800519c6  retn
```
