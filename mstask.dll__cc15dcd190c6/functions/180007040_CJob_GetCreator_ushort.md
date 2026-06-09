# CJob::GetCreator(ushort * *)

- ea: `0x180007040`
- end: `0x180007130`
- name: `?GetCreator@CJob@@UEAAJPEAPEAG@Z`
- size: `240`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007040`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007085`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007085`

## pseudocode

```c
__int64 __fastcall CJob::GetCreator(CJob *this, unsigned __int16 **a2)
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

  v2 = (unsigned __int16 *)*((_QWORD *)this + 17);
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
0x180007040  mov     [rsp+arg_0], rbx
0x180007045  mov     [rsp+arg_8], rsi
0x18000704a  push    rdi
0x18000704b  sub     rsp, 20h
0x18000704f  mov     rax, [rcx+88h]
0x180007056  lea     rbx, ?wszEmpty@@3PAGA; ushort near * wszEmpty
0x18000705d  test    rax, rax
0x180007060  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180007067  mov     rsi, rdx
0x18000706a  mov     rcx, rdi
0x18000706d  cmovnz  rbx, rax
0x180007071  cmp     word ptr [rbx+rcx*2+2], 0
0x180007077  lea     rcx, [rcx+1]
0x18000707b  jnz     short loc_180007071
0x18000707d  lea     rcx, ds:2[rcx*2]; cb
0x180007085  call    cs:__imp_CoTaskMemAlloc
0x18000708b  mov     [rsi], rax
0x18000708e  mov     r8, rax
0x180007091  test    rax, rax
0x180007094  jz      short loc_180007110
0x180007096  nop     word ptr [rax+rax+00000000h]
0x1800070a0  cmp     word ptr [rbx+rdi*2+2], 0
0x1800070a6  lea     rdi, [rdi+1]
0x1800070aa  jnz     short loc_1800070A0
0x1800070ac  lea     rdx, [rdi+1]
0x1800070b0  test    rdx, rdx
0x1800070b3  jz      short loc_18000711E
0x1800070b5  cmp     rdx, 7FFFFFFFh
0x1800070bc  ja      short loc_180007117
0x1800070be  mov     eax, 7FFFFFFEh
0x1800070c3  test    rax, rax
0x1800070c6  jz      short loc_1800070E5
0x1800070c8  movzx   ecx, word ptr [rbx]
0x1800070cb  test    cx, cx
0x1800070ce  jz      short loc_1800070E5
0x1800070d0  mov     [r8], cx
0x1800070d4  add     rbx, 2
0x1800070d8  add     r8, 2
0x1800070dc  dec     rax
0x1800070df  sub     rdx, 1
0x1800070e3  jnz     short loc_1800070C3
0x1800070e5  test    rdx, rdx
0x1800070e8  lea     rax, [r8-2]
0x1800070ec  cmovnz  rax, r8
0x1800070f0  xor     ecx, ecx
0x1800070f2  test    rdx, rdx
0x1800070f5  mov     [rax], cx
0x1800070f8  mov     eax, 8007007Ah
0x1800070fd  cmovnz  eax, ecx
0x180007100  mov     rbx, [rsp+28h+arg_0]
0x180007105  mov     rsi, [rsp+28h+arg_8]
0x18000710a  add     rsp, 20h
0x18000710e  pop     rdi
0x18000710f  retn
0x180007110  mov     eax, 8007000Eh
0x180007115  jmp     short loc_180007100
0x180007117  mov     eax, 80070057h
0x18000711c  jmp     short loc_180007128
0x18000711e  mov     eax, 80070057h
0x180007123  test    rdx, rdx
0x180007126  jz      short loc_180007100
0x180007128  xor     ecx, ecx
0x18000712a  mov     [r8], cx
0x18000712e  jmp     short loc_180007100
```
