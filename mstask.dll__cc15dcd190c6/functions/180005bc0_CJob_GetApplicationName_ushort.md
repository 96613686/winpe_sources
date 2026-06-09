# CJob::GetApplicationName(ushort * *)

- ea: `0x180005bc0`
- end: `0x180005cbc`
- name: `?GetApplicationName@CJob@@UEAAJPEAPEAG@Z`
- size: `252`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005bc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005c04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005c04`

## pseudocode

```c
__int64 __fastcall CJob::GetApplicationName(CJob *this, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rax
  unsigned __int16 *v3; // rbx
  __int64 v4; // rdi
  __int64 v6; // rcx
  bool v7; // zf
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rcx
  unsigned __int64 v10; // r8
  __int64 v11; // rax
  unsigned __int16 *v12; // rax
  __int64 result; // rax

  v2 = (unsigned __int16 *)*((_QWORD *)this + 14);
  v3 = (unsigned __int16 *)&wszEmpty;
  v4 = -1;
  v6 = -1;
  if ( v2 )
    v3 = v2;
  do
    v7 = v3[++v6] == 0;
  while ( !v7 );
  v8 = (unsigned __int16 *)CoTaskMemAlloc(2 * v6 + 2);
  *a2 = v8;
  v9 = v8;
  if ( !v8 )
    return 2147942414LL;
  do
    v7 = v3[++v4] == 0;
  while ( !v7 );
  v10 = v4 + 1;
  if ( v4 == -1 )
    return 2147942487LL;
  if ( v10 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
    *v9 = 0;
  }
  else
  {
    v11 = 2147483646;
    do
    {
      if ( !v11 )
        break;
      if ( !*v3 )
        break;
      *v9++ = *v3++;
      --v11;
      --v10;
    }
    while ( v10 );
    v12 = v9 - 1;
    if ( v10 )
      v12 = v9;
    *v12 = 0;
    result = 2147942522LL;
    if ( v10 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005bc0  mov     [rsp+arg_0], rbx
0x180005bc5  mov     [rsp+arg_8], rsi
0x180005bca  push    rdi
0x180005bcb  sub     rsp, 20h
0x180005bcf  mov     rax, [rcx+70h]
0x180005bd3  lea     rbx, ?wszEmpty@@3PAGA; ushort near * wszEmpty
0x180005bda  test    rax, rax
0x180005bdd  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180005be4  mov     rsi, rdx
0x180005be7  mov     rcx, rdi
0x180005bea  cmovnz  rbx, rax
0x180005bee  xchg    ax, ax
0x180005bf0  cmp     word ptr [rbx+rcx*2+2], 0
0x180005bf6  lea     rcx, [rcx+1]
0x180005bfa  jnz     short loc_180005BF0
0x180005bfc  lea     rcx, ds:2[rcx*2]; cb
0x180005c04  call    cs:__imp_CoTaskMemAlloc
0x180005c0a  mov     [rsi], rax
0x180005c0d  mov     rcx, rax
0x180005c10  test    rax, rax
0x180005c13  jz      short loc_180005C8F
0x180005c15  nop     word ptr [rax+rax+00000000h]
0x180005c20  cmp     word ptr [rbx+rdi*2+2], 0
0x180005c26  lea     rdi, [rdi+1]
0x180005c2a  jnz     short loc_180005C20
0x180005c2c  lea     r8, [rdi+1]
0x180005c30  test    r8, r8
0x180005c33  jz      short loc_180005CAB
0x180005c35  cmp     r8, 7FFFFFFFh
0x180005c3c  ja      short loc_180005CA4
0x180005c3e  mov     eax, 7FFFFFFEh
0x180005c43  test    rax, rax
0x180005c46  jz      short loc_180005C64
0x180005c48  movzx   edx, word ptr [rbx]
0x180005c4b  test    dx, dx
0x180005c4e  jz      short loc_180005C64
0x180005c50  mov     [rcx], dx
0x180005c53  add     rbx, 2
0x180005c57  add     rcx, 2
0x180005c5b  dec     rax
0x180005c5e  sub     r8, 1
0x180005c62  jnz     short loc_180005C43
0x180005c64  test    r8, r8
0x180005c67  lea     rax, [rcx-2]
0x180005c6b  cmovnz  rax, rcx
0x180005c6f  xor     edx, edx
0x180005c71  test    r8, r8
0x180005c74  mov     [rax], dx
0x180005c77  mov     eax, 8007007Ah
0x180005c7c  cmovnz  eax, edx
0x180005c7f  mov     rbx, [rsp+28h+arg_0]
0x180005c84  mov     rsi, [rsp+28h+arg_8]
0x180005c89  add     rsp, 20h
0x180005c8d  pop     rdi
0x180005c8e  retn
0x180005c8f  mov     rbx, [rsp+28h+arg_0]
0x180005c94  mov     eax, 8007000Eh
0x180005c99  mov     rsi, [rsp+28h+arg_8]
0x180005c9e  add     rsp, 20h
0x180005ca2  pop     rdi
0x180005ca3  retn
0x180005ca4  mov     eax, 80070057h
0x180005ca9  jmp     short loc_180005CB5
0x180005cab  mov     eax, 80070057h
0x180005cb0  test    r8, r8
0x180005cb3  jz      short loc_180005C7F
0x180005cb5  xor     edx, edx
0x180005cb7  mov     [rcx], dx
0x180005cba  jmp     short loc_180005C7F
```
