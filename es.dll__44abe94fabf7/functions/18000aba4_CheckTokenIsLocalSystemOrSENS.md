# CheckTokenIsLocalSystemOrSENS

- ea: `0x18000aba4`
- end: `0x18000ac39`
- name: `CheckTokenIsLocalSystemOrSENS`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a1f0`

## callees

- `0x18000aba4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000abcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000abcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac0e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000abc3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000ac04`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000abc3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000ac04`

## pseudocode

```c
signed int __fastcall CheckTokenIsLocalSystemOrSENS(__int64 a1)
{
  signed int result; // eax
  bool v2; // sf
  bool v3; // sf
  WINBOOL IsMember; // [rsp+30h] [rbp+8h] BYREF
  int v5; // [rsp+34h] [rbp+Ch]
  WINBOOL v6; // [rsp+38h] [rbp+10h] BYREF

  v5 = HIDWORD(a1);
  IsMember = 0;
  if ( CheckTokenMembership(0, pSid, &IsMember) )
  {
    result = 0;
    goto LABEL_7;
  }
  result = GetLastError();
  v2 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v2 = result < 0;
  }
  if ( !v2 )
  {
LABEL_7:
    if ( IsMember )
      return result;
    v6 = 0;
    if ( CheckTokenMembership(0, qword_180064668, &v6) )
    {
      result = 0;
    }
    else
    {
      result = GetLastError();
      v3 = result < 0;
      if ( result > 0 )
      {
        result = (unsigned __int16)result | 0x80070000;
        v3 = result < 0;
      }
      if ( v3 )
        return result;
    }
    if ( !v6 )
      return -2147024891;
  }
  return result;
}

```

## disassembly

```asm
0x18000aba4  mov     qword ptr [rsp+IsMember], rcx
0x18000aba9  sub     rsp, 28h
0x18000abad  mov     rdx, cs:pSid; SidToCheck
0x18000abb4  lea     r8, [rsp+28h+IsMember]; IsMember
0x18000abb9  xor     ecx, ecx; TokenHandle
0x18000abbb  mov     [rsp+28h+IsMember], 0
0x18000abc3  call    cs:__imp_CheckTokenMembership
0x18000abc9  test    eax, eax
0x18000abcb  jnz     short loc_18000ABE5
0x18000abcd  call    cs:__imp_GetLastError
0x18000abd3  test    eax, eax
0x18000abd5  jle     short loc_18000ABE1
0x18000abd7  movzx   eax, ax
0x18000abda  or      eax, 80070000h
0x18000abdf  test    eax, eax
0x18000abe1  jns     short loc_18000ABE7
0x18000abe3  jmp     short loc_18000AC34
0x18000abe5  xor     eax, eax
0x18000abe7  cmp     [rsp+28h+IsMember], 0
0x18000abec  jnz     short loc_18000AC34
0x18000abee  mov     rdx, cs:qword_180064668; SidToCheck
0x18000abf5  lea     r8, [rsp+28h+arg_8]; IsMember
0x18000abfa  xor     ecx, ecx; TokenHandle
0x18000abfc  mov     [rsp+28h+arg_8], 0
0x18000ac04  call    cs:__imp_CheckTokenMembership
0x18000ac0a  test    eax, eax
0x18000ac0c  jnz     short loc_18000AC26
0x18000ac0e  call    cs:__imp_GetLastError
0x18000ac14  test    eax, eax
0x18000ac16  jle     short loc_18000AC22
0x18000ac18  movzx   eax, ax
0x18000ac1b  or      eax, 80070000h
0x18000ac20  test    eax, eax
0x18000ac22  js      short loc_18000AC34
0x18000ac24  jmp     short loc_18000AC28
0x18000ac26  xor     eax, eax
0x18000ac28  cmp     [rsp+28h+arg_8], 0
0x18000ac2d  jnz     short loc_18000AC34
0x18000ac2f  mov     eax, 80070005h
0x18000ac34  add     rsp, 28h
0x18000ac38  retn
```
