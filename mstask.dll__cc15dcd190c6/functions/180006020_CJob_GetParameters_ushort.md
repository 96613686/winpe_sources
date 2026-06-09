# CJob::GetParameters(ushort * *)

- ea: `0x180006020`
- end: `0x180006110`
- name: `?GetParameters@CJob@@UEAAJPEAPEAG@Z`
- size: `240`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006020`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006064`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006064`

## pseudocode

```c
__int64 __fastcall CJob::GetParameters(CJob *this, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rax
  unsigned __int16 *v3; // rbx
  __int64 v4; // rdi
  __int64 v6; // rcx
  bool v7; // zf
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // r8
  unsigned __int64 v10; // rdx
  __int64 v11; // rax
  unsigned __int16 *v12; // rax
  __int64 result; // rax

  v2 = (unsigned __int16 *)*((_QWORD *)this + 15);
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
0x180006020  mov     [rsp+arg_0], rbx
0x180006025  mov     [rsp+arg_8], rsi
0x18000602a  push    rdi
0x18000602b  sub     rsp, 20h
0x18000602f  mov     rax, [rcx+78h]
0x180006033  lea     rbx, ?wszEmpty@@3PAGA; ushort near * wszEmpty
0x18000603a  test    rax, rax
0x18000603d  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180006044  mov     rsi, rdx
0x180006047  mov     rcx, rdi
0x18000604a  cmovnz  rbx, rax
0x18000604e  xchg    ax, ax
0x180006050  cmp     word ptr [rbx+rcx*2+2], 0
0x180006056  lea     rcx, [rcx+1]
0x18000605a  jnz     short loc_180006050
0x18000605c  lea     rcx, ds:2[rcx*2]; cb
0x180006064  call    cs:__imp_CoTaskMemAlloc
0x18000606a  mov     [rsi], rax
0x18000606d  mov     r8, rax
0x180006070  test    rax, rax
0x180006073  jz      short loc_1800060F0
0x180006075  nop     word ptr [rax+rax+00000000h]
0x180006080  cmp     word ptr [rbx+rdi*2+2], 0
0x180006086  lea     rdi, [rdi+1]
0x18000608a  jnz     short loc_180006080
0x18000608c  lea     rdx, [rdi+1]
0x180006090  test    rdx, rdx
0x180006093  jz      short loc_1800060FE
0x180006095  cmp     rdx, 7FFFFFFFh
0x18000609c  ja      short loc_1800060F7
0x18000609e  mov     eax, 7FFFFFFEh
0x1800060a3  test    rax, rax
0x1800060a6  jz      short loc_1800060C5
0x1800060a8  movzx   ecx, word ptr [rbx]
0x1800060ab  test    cx, cx
0x1800060ae  jz      short loc_1800060C5
0x1800060b0  mov     [r8], cx
0x1800060b4  add     rbx, 2
0x1800060b8  add     r8, 2
0x1800060bc  dec     rax
0x1800060bf  sub     rdx, 1
0x1800060c3  jnz     short loc_1800060A3
0x1800060c5  test    rdx, rdx
0x1800060c8  lea     rax, [r8-2]
0x1800060cc  cmovnz  rax, r8
0x1800060d0  xor     ecx, ecx
0x1800060d2  test    rdx, rdx
0x1800060d5  mov     [rax], cx
0x1800060d8  mov     eax, 8007007Ah
0x1800060dd  cmovnz  eax, ecx
0x1800060e0  mov     rbx, [rsp+28h+arg_0]
0x1800060e5  mov     rsi, [rsp+28h+arg_8]
0x1800060ea  add     rsp, 20h
0x1800060ee  pop     rdi
0x1800060ef  retn
0x1800060f0  mov     eax, 8007000Eh
0x1800060f5  jmp     short loc_1800060E0
0x1800060f7  mov     eax, 80070057h
0x1800060fc  jmp     short loc_180006108
0x1800060fe  mov     eax, 80070057h
0x180006103  test    rdx, rdx
0x180006106  jz      short loc_1800060E0
0x180006108  xor     ecx, ecx
0x18000610a  mov     [r8], cx
0x18000610e  jmp     short loc_1800060E0
```
