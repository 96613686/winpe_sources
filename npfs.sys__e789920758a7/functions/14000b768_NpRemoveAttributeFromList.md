# NpRemoveAttributeFromList

- ea: `0x14000b768`
- end: `0x14000b844`
- name: `NpRemoveAttributeFromList`
- size: `220`
- prototype: `__int64 __fastcall(_QWORD **, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000b84c`

## callees

- `0x14000b768`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b82d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b82d`

## string_xrefs

- `0x14000b7d6`: `ServerProcessId`
- `0x14000b7b2`: `ClientComputerName`
- `0x14000b7c4`: `ClientProcessId`
- `0x14000b7a9`: `RestrictedAccess`

## pseudocode

```c
__int64 __fastcall NpRemoveAttributeFromList(_QWORD **a1, __int64 a2)
{
  _QWORD *v4; // rcx
  const char *v5; // r9
  __int64 v6; // r8
  int v7; // eax
  int v8; // edx
  _QWORD **v9; // rax
  _QWORD *v11; // rdx

  v4 = *a1;
  if ( v4 == a1 )
    return 3221226021LL;
  while ( 1 )
  {
    v5 = (const char *)v4[2];
    if ( (_DWORD)v5 == 1 )
    {
      v5 = "ServerProcessId";
    }
    else
    {
      switch ( (unsigned int)v4[2] )
      {
        case 2u:
          v5 = "ServerSessionId";
          break;
        case 3u:
          v5 = "ClientProcessId";
          break;
        case 4u:
          v5 = "ClientSessionId";
          break;
        case 6u:
          v5 = "ClientComputerName";
          break;
        case 7u:
          v5 = "RestrictedAccess";
          break;
      }
    }
    v6 = a2 - (_QWORD)v5;
    do
    {
      v7 = (unsigned __int8)v5[v6];
      v8 = *(unsigned __int8 *)v5 - v7;
      if ( v8 )
        break;
      ++v5;
    }
    while ( v7 );
    v9 = (_QWORD **)*v4;
    if ( !v8 )
      break;
    v4 = (_QWORD *)*v4;
    if ( v9 == a1 )
      return 3221226021LL;
  }
  if ( v9[1] != v4 || (v11 = (_QWORD *)v4[1], (_QWORD *)*v11 != v4) )
    __fastfail(3u);
  *v11 = v9;
  v9[1] = v11;
  ExFreePoolWithTag(v4, 0);
  return 0;
}

```

## disassembly

```asm
0x14000b768  sub     rsp, 28h
0x14000b76c  mov     r10, rcx
0x14000b76f  mov     r11, rdx
0x14000b772  mov     rcx, [rcx]; P
0x14000b775  cmp     rcx, r10
0x14000b778  jz      loc_14000B80A
0x14000b77e  mov     r9, [rcx+10h]
0x14000b782  mov     r8d, r9d
0x14000b785  sub     r8d, 1
0x14000b789  jz      short loc_14000B7D6
0x14000b78b  sub     r8d, 1
0x14000b78f  jz      short loc_14000B7CD
0x14000b791  sub     r8d, 1
0x14000b795  jz      short loc_14000B7C4
0x14000b797  sub     r8d, 1
0x14000b79b  jz      short loc_14000B7BB
0x14000b79d  sub     r8d, 2
0x14000b7a1  jz      short loc_14000B7B2
0x14000b7a3  cmp     r8d, 1
0x14000b7a7  jnz     short loc_14000B7DD
0x14000b7a9  lea     r9, aRestrictedacce; "RestrictedAccess"
0x14000b7b0  jmp     short loc_14000B7DD
0x14000b7b2  lea     r9, Str2; "ClientComputerName"
0x14000b7b9  jmp     short loc_14000B7DD
0x14000b7bb  lea     r9, aClientsessioni; "ClientSessionId"
0x14000b7c2  jmp     short loc_14000B7DD
0x14000b7c4  lea     r9, aClientprocessi; "ClientProcessId"
0x14000b7cb  jmp     short loc_14000B7DD
0x14000b7cd  lea     r9, aServersessioni; "ServerSessionId"
0x14000b7d4  jmp     short loc_14000B7DD
0x14000b7d6  lea     r9, aServerprocessi; "ServerProcessId"
0x14000b7dd  mov     r8, r11
0x14000b7e0  sub     r8, r9
0x14000b7e3  movzx   edx, byte ptr [r9]
0x14000b7e7  movzx   eax, byte ptr [r9+r8]
0x14000b7ec  sub     edx, eax
0x14000b7ee  jnz     short loc_14000B7F7
0x14000b7f0  inc     r9
0x14000b7f3  test    eax, eax
0x14000b7f5  jnz     short loc_14000B7E3
0x14000b7f7  mov     rax, [rcx]
0x14000b7fa  test    edx, edx
0x14000b7fc  jz      short loc_14000B815
0x14000b7fe  mov     rcx, rax
0x14000b801  cmp     rax, r10
0x14000b804  jnz     loc_14000B77E
0x14000b80a  mov     eax, 0C0000225h
0x14000b80f  add     rsp, 28h
0x14000b813  retn
0x14000b815  cmp     [rax+8], rcx
0x14000b819  jnz     short loc_14000B83D
0x14000b81b  mov     rdx, [rcx+8]
0x14000b81f  cmp     [rdx], rcx
0x14000b822  jnz     short loc_14000B83D
0x14000b824  mov     [rdx], rax
0x14000b827  mov     [rax+8], rdx
0x14000b82b  xor     edx, edx; Tag
0x14000b82d  call    cs:__imp_ExFreePoolWithTag
0x14000b834  nop     dword ptr [rax+rax+00h]
0x14000b839  xor     eax, eax
0x14000b83b  jmp     short loc_14000B80F
0x14000b83d  mov     ecx, 3
0x14000b842  int     29h; Win8: RtlFailFast(ecx)
```
