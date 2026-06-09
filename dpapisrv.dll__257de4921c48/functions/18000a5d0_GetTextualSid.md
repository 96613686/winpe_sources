# GetTextualSid

- ea: `0x18000a5d0`
- end: `0x18000a687`
- name: `GetTextualSid`
- size: `183`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004e60`
- `0x18001866c`
- `0x180019f40`
- `0x18002ad50`
- `0x18002c834`
- `0x18002def8`
- `0x1800382f4`
- `0x1800385fc`

## callees

- `0x18000a5d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a656`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a656`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a5f1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a5f1`

## pseudocode

```c
__int64 __fastcall GetTextualSid(void *a1, _WORD *a2, unsigned int a3)
{
  unsigned int v5; // esi
  BOOL v6; // eax
  LPWSTR v7; // r9
  __int64 v8; // rax
  __int64 v9; // r8
  LPWSTR v10; // rdx
  _WORD *v11; // rcx
  LPWSTR StringSid; // [rsp+48h] [rbp+20h] BYREF

  v5 = 0;
  StringSid = 0;
  v6 = ConvertSidToStringSidW(a1, &StringSid);
  v7 = StringSid;
  if ( v6 )
  {
    v8 = 2147483646;
    v9 = a3;
    if ( a3 - 1 > 0x7FFFFFFE )
    {
      if ( a3 )
        *a2 = 0;
    }
    else
    {
      v10 = StringSid;
      do
      {
        if ( !v8 )
          break;
        if ( !*v10 )
          break;
        *a2++ = *v10++;
        --v8;
        --v9;
      }
      while ( v9 );
      v11 = a2 - 1;
      if ( v9 )
        v11 = a2;
      *v11 = 0;
      if ( v9 )
        v5 = 1;
    }
  }
  if ( v7 )
    LocalFree(v7);
  return v5;
}

```

## disassembly

```asm
0x18000a5d0  mov     [rsp+arg_0], rbx
0x18000a5d5  mov     [rsp+arg_8], rsi
0x18000a5da  push    rdi
0x18000a5db  sub     rsp, 20h
0x18000a5df  mov     rbx, rdx
0x18000a5e2  mov     edi, r8d
0x18000a5e5  xor     esi, esi
0x18000a5e7  lea     rdx, [rsp+28h+StringSid]; StringSid
0x18000a5ec  mov     [rsp+28h+StringSid], rsi
0x18000a5f1  call    cs:__imp_ConvertSidToStringSidW
0x18000a5f8  nop     dword ptr [rax+rax+00h]
0x18000a5fd  mov     r9, [rsp+28h+StringSid]
0x18000a602  test    eax, eax
0x18000a604  jz      short loc_18000A64E
0x18000a606  lea     ecx, [rdi-1]
0x18000a609  mov     eax, 7FFFFFFEh
0x18000a60e  mov     r8d, edi
0x18000a611  cmp     ecx, eax
0x18000a613  ja      short loc_18000A67C
0x18000a615  mov     rdx, r9
0x18000a618  test    rax, rax
0x18000a61b  jz      short loc_18000A639
0x18000a61d  movzx   ecx, word ptr [rdx]
0x18000a620  test    cx, cx
0x18000a623  jz      short loc_18000A639
0x18000a625  mov     [rbx], cx
0x18000a628  add     rdx, 2
0x18000a62c  add     rbx, 2
0x18000a630  dec     rax
0x18000a633  sub     r8, 1
0x18000a637  jnz     short loc_18000A618
0x18000a639  test    r8, r8
0x18000a63c  lea     rcx, [rbx-2]
0x18000a640  cmovnz  rcx, rbx
0x18000a644  xor     eax, eax
0x18000a646  mov     [rcx], ax
0x18000a649  test    r8, r8
0x18000a64c  jnz     short loc_18000A675
0x18000a64e  test    r9, r9
0x18000a651  jz      short loc_18000A662
0x18000a653  mov     rcx, r9; hMem
0x18000a656  call    cs:__imp_LocalFree
0x18000a65d  nop     dword ptr [rax+rax+00h]
0x18000a662  mov     rbx, [rsp+28h+arg_0]
0x18000a667  mov     eax, esi
0x18000a669  mov     rsi, [rsp+28h+arg_8]
0x18000a66e  add     rsp, 20h
0x18000a672  pop     rdi
0x18000a673  retn
0x18000a675  mov     esi, 1
0x18000a67a  jmp     short loc_18000A64E
0x18000a67c  test    edi, edi
0x18000a67e  jz      short loc_18000A64E
0x18000a680  xor     edx, edx
0x18000a682  mov     [rbx], dx
0x18000a685  jmp     short loc_18000A64E
```
