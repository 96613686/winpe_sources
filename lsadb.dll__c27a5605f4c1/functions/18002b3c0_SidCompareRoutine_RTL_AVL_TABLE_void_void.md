# SidCompareRoutine(_RTL_AVL_TABLE *,void *,void *)

- ea: `0x18002b3c0`
- end: `0x18002b44e`
- name: `?SidCompareRoutine@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z`
- size: `142`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002b3c0`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x18002b3eb`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002b3f7`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002b3eb`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002b3f7`
- `ntdll!RtlLengthSid` at `0x18002b408`
- `ntdll!RtlLengthSid` at `0x18002b408`

## pseudocode

```c
__int64 __fastcall SidCompareRoutine(struct _RTL_AVL_TABLE *Table, unsigned __int8 **FirstStruct, PSID *SecondStruct)
{
  unsigned __int8 *v3; // rdi
  _BYTE *v4; // rsi
  unsigned __int8 v5; // al
  PUCHAR v7; // rbx
  PUCHAR v8; // rax
  ULONG v9; // r11d
  unsigned int v10; // edx
  int v11; // r8d
  unsigned __int8 v12; // r9

  v3 = *FirstStruct;
  v4 = *SecondStruct;
  v5 = **FirstStruct;
  if ( v5 < *(_BYTE *)*SecondStruct )
    return 0;
  if ( v5 > *(_BYTE *)*SecondStruct )
    return 1;
  v7 = RtlSubAuthorityCountSid(*SecondStruct);
  v8 = RtlSubAuthorityCountSid(v3);
  if ( *v8 < *v7 )
    return 0;
  if ( *v8 > *v7 )
    return 1;
  v9 = RtlLengthSid(v3);
  v10 = 2;
  v11 = 0;
  if ( v9 )
  {
    while ( 1 )
    {
      v12 = v3[v11];
      if ( v12 != v4[v11] )
        break;
      if ( ++v11 >= v9 )
        return v10;
    }
    return v12 >= v4[v11];
  }
  return v10;
}

```

## disassembly

```asm
0x18002b3c0  mov     [rsp+arg_0], rbx
0x18002b3c5  mov     [rsp+arg_8], rsi
0x18002b3ca  push    rdi
0x18002b3cb  sub     rsp, 20h
0x18002b3cf  mov     rdi, [rdx]
0x18002b3d2  mov     rsi, [r8]
0x18002b3d5  mov     al, [rdi]
0x18002b3d7  cmp     al, [rsi]
0x18002b3d9  jnb     short loc_18002B3DF
0x18002b3db  xor     eax, eax
0x18002b3dd  jmp     short loc_18002B43E
0x18002b3df  jbe     short loc_18002B3E8
0x18002b3e1  mov     eax, 1
0x18002b3e6  jmp     short loc_18002B43E
0x18002b3e8  mov     rcx, rsi; Sid
0x18002b3eb  call    cs:__imp_RtlSubAuthorityCountSid
0x18002b3f1  mov     rcx, rdi; Sid
0x18002b3f4  mov     rbx, rax
0x18002b3f7  call    cs:__imp_RtlSubAuthorityCountSid
0x18002b3fd  mov     cl, [rax]
0x18002b3ff  cmp     cl, [rbx]
0x18002b401  jb      short loc_18002B3DB
0x18002b403  ja      short loc_18002B3E1
0x18002b405  mov     rcx, rdi; Sid
0x18002b408  call    cs:__imp_RtlLengthSid
0x18002b40e  mov     r11d, eax
0x18002b411  mov     edx, 2
0x18002b416  xor     eax, eax
0x18002b418  mov     r8d, eax
0x18002b41b  test    r11d, r11d
0x18002b41e  jz      short loc_18002B43C
0x18002b420  mov     ecx, r8d
0x18002b423  mov     r9b, [rcx+rdi]
0x18002b427  cmp     r9b, [rcx+rsi]
0x18002b42b  jnz     short loc_18002B437
0x18002b42d  inc     r8d
0x18002b430  cmp     r8d, r11d
0x18002b433  jb      short loc_18002B420
0x18002b435  jmp     short loc_18002B43C
0x18002b437  mov     edx, eax
0x18002b439  setnb   dl
0x18002b43c  mov     eax, edx
0x18002b43e  mov     rbx, [rsp+28h+arg_0]
0x18002b443  mov     rsi, [rsp+28h+arg_8]
0x18002b448  add     rsp, 20h
0x18002b44c  pop     rdi
0x18002b44d  retn
```
