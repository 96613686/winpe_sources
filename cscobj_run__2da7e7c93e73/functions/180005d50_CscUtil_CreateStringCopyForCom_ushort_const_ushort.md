# CscUtil_CreateStringCopyForCom(ushort const *,ushort * *)

- ea: `0x180005d50`
- end: `0x180005e3a`
- name: `?CscUtil_CreateStringCopyForCom@@YAJPEBGPEAPEAG@Z`
- size: `234`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006e70`
- `0x1800076e0`
- `0x18000d720`

## callees

- `0x180005d50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005d81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005d81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005e2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005e2b`

## pseudocode

```c
__int64 __fastcall CscUtil_CreateStringCopyForCom(const unsigned __int16 *a1, LPVOID *a2)
{
  const unsigned __int16 *v3; // rbx
  __int64 v4; // rdi
  unsigned __int64 v5; // rdi
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rdx
  __int64 v9; // rcx
  unsigned __int16 *v10; // rcx
  int v11; // ebx

  v3 = a1;
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  v5 = v4 + 1;
  v6 = (unsigned __int16 *)CoTaskMemAlloc(2 * v5);
  *a2 = v6;
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  if ( v5 )
  {
    if ( v5 > 0x7FFFFFFF )
    {
      v11 = -2147024809;
      *v6 = 0;
      goto LABEL_18;
    }
    v9 = 2147483646;
    do
    {
      if ( !v9 )
        break;
      if ( !*v3 )
        break;
      *v7++ = *v3++;
      --v9;
      --v5;
    }
    while ( v5 );
    v10 = v7 - 1;
    v11 = -2147024774;
    if ( v5 )
    {
      v10 = v7;
      v11 = 0;
    }
    *v10 = 0;
  }
  else
  {
    v11 = -2147024809;
  }
  if ( v11 < 0 )
  {
LABEL_18:
    CoTaskMemFree(*a2);
    *a2 = 0;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180005d50  mov     [rsp+arg_0], rbx
0x180005d55  mov     [rsp+arg_8], rsi
0x180005d5a  push    rdi
0x180005d5b  sub     rsp, 20h
0x180005d5f  mov     rsi, rdx
0x180005d62  mov     rbx, rcx
0x180005d65  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180005d6c  nop     dword ptr [rax+00h]
0x180005d70  inc     rdi
0x180005d73  cmp     word ptr [rcx+rdi*2], 0
0x180005d78  jnz     short loc_180005D70
0x180005d7a  inc     rdi
0x180005d7d  lea     rcx, [rdi+rdi]; cb
0x180005d81  call    cs:__imp_CoTaskMemAlloc
0x180005d87  mov     [rsi], rax
0x180005d8a  mov     rdx, rax
0x180005d8d  test    rax, rax
0x180005d90  jnz     short loc_180005DA7
0x180005d92  mov     eax, 8007000Eh
0x180005d97  mov     rbx, [rsp+28h+arg_0]
0x180005d9c  mov     rsi, [rsp+28h+arg_8]
0x180005da1  add     rsp, 20h
0x180005da5  pop     rdi
0x180005da6  retn
0x180005da7  test    rdi, rdi
0x180005daa  jz      short loc_180005E19
0x180005dac  cmp     rdi, 7FFFFFFFh
0x180005db3  ja      short loc_180005E12
0x180005db5  mov     ecx, 7FFFFFFEh
0x180005dba  nop     word ptr [rax+rax+00h]
0x180005dc0  test    rcx, rcx
0x180005dc3  jz      short loc_180005DE1
0x180005dc5  movzx   eax, word ptr [rbx]
0x180005dc8  test    ax, ax
0x180005dcb  jz      short loc_180005DE1
0x180005dcd  mov     [rdx], ax
0x180005dd0  add     rbx, 2
0x180005dd4  add     rdx, 2
0x180005dd8  dec     rcx
0x180005ddb  sub     rdi, 1
0x180005ddf  jnz     short loc_180005DC0
0x180005de1  test    rdi, rdi
0x180005de4  lea     rcx, [rdx-2]
0x180005de8  mov     ebx, 8007007Ah
0x180005ded  cmovnz  rcx, rdx
0x180005df1  xor     eax, eax
0x180005df3  test    rdi, rdi
0x180005df6  cmovnz  ebx, eax
0x180005df9  mov     [rcx], ax
0x180005dfc  test    ebx, ebx
0x180005dfe  js      short loc_180005E28
0x180005e00  mov     rsi, [rsp+28h+arg_8]
0x180005e05  mov     eax, ebx
0x180005e07  mov     rbx, [rsp+28h+arg_0]
0x180005e0c  add     rsp, 20h
0x180005e10  pop     rdi
0x180005e11  retn
0x180005e12  mov     ebx, 80070057h
0x180005e17  jmp     short loc_180005E23
0x180005e19  mov     ebx, 80070057h
0x180005e1e  test    rdi, rdi
0x180005e21  jz      short loc_180005DFC
0x180005e23  xor     eax, eax
0x180005e25  mov     [rdx], ax
0x180005e28  mov     rcx, [rsi]; pv
0x180005e2b  call    cs:__imp_CoTaskMemFree
0x180005e31  mov     qword ptr [rsi], 0
0x180005e38  jmp     short loc_180005E00
```
