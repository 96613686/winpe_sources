# CJob::GetWorkingDirectory(ushort * *)

- ea: `0x180007450`
- end: `0x180007556`
- name: `?GetWorkingDirectory@CJob@@UEAAJPEAPEAG@Z`
- size: `262`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007450`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007495`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007495`

## pseudocode

```c
__int64 __fastcall CJob::GetWorkingDirectory(CJob *this, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rax
  unsigned __int16 *v3; // rbx
  __int64 v4; // rdi
  __int64 v6; // rcx
  bool v7; // zf
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rcx
  __int64 result; // rax
  unsigned __int64 v11; // rdx
  __int64 v12; // rax
  unsigned __int16 *v13; // rax

  v2 = (unsigned __int16 *)*((_QWORD *)this + 16);
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
  v11 = v4 + 1;
  if ( v4 == -1 )
    return 2147942487LL;
  if ( v11 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
    *v9 = 0;
  }
  else
  {
    v12 = 2147483646;
    do
    {
      if ( !v12 )
        break;
      if ( !*v3 )
        break;
      *v9++ = *v3++;
      --v12;
      --v11;
    }
    while ( v11 );
    v13 = v9 - 1;
    if ( v11 )
      v13 = v9;
    *v13 = 0;
    result = 2147942522LL;
    if ( v11 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180007450  mov     [rsp+arg_0], rbx
0x180007455  mov     [rsp+arg_8], rsi
0x18000745a  push    rdi
0x18000745b  sub     rsp, 20h
0x18000745f  mov     rax, [rcx+80h]
0x180007466  lea     rbx, ?wszEmpty@@3PAGA; ushort near * wszEmpty
0x18000746d  test    rax, rax
0x180007470  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180007477  mov     rsi, rdx
0x18000747a  mov     rcx, rdi
0x18000747d  cmovnz  rbx, rax
0x180007481  cmp     word ptr [rbx+rcx*2+2], 0
0x180007487  lea     rcx, [rcx+1]
0x18000748b  jnz     short loc_180007481
0x18000748d  lea     rcx, ds:2[rcx*2]; cb
0x180007495  call    cs:__imp_CoTaskMemAlloc
0x18000749b  mov     [rsi], rax
0x18000749e  mov     rcx, rax
0x1800074a1  test    rax, rax
0x1800074a4  jnz     short loc_1800074C0
0x1800074a6  mov     eax, 8007000Eh
0x1800074ab  mov     rbx, [rsp+28h+arg_0]
0x1800074b0  mov     rsi, [rsp+28h+arg_8]
0x1800074b5  add     rsp, 20h
0x1800074b9  pop     rdi
0x1800074ba  retn
0x1800074c0  cmp     word ptr [rbx+rdi*2+2], 0
0x1800074c6  lea     rdi, [rdi+1]
0x1800074ca  jnz     short loc_1800074C0
0x1800074cc  lea     rdx, [rdi+1]
0x1800074d0  test    rdx, rdx
0x1800074d3  jz      short loc_18000753C
0x1800074d5  cmp     rdx, 7FFFFFFFh
0x1800074dc  ja      short loc_180007535
0x1800074de  mov     eax, 7FFFFFFEh
0x1800074e3  test    rax, rax
0x1800074e6  jz      short loc_180007507
0x1800074e8  movzx   r8d, word ptr [rbx]
0x1800074ec  test    r8w, r8w
0x1800074f0  jz      short loc_180007507
0x1800074f2  mov     [rcx], r8w
0x1800074f6  add     rbx, 2
0x1800074fa  add     rcx, 2
0x1800074fe  dec     rax
0x180007501  sub     rdx, 1
0x180007505  jnz     short loc_1800074E3
0x180007507  mov     rbx, [rsp+28h+arg_0]
0x18000750c  lea     rax, [rcx-2]
0x180007510  mov     rsi, [rsp+28h+arg_8]
0x180007515  test    rdx, rdx
0x180007518  cmovnz  rax, rcx
0x18000751c  xor     r8d, r8d
0x18000751f  test    rdx, rdx
0x180007522  mov     [rax], r8w
0x180007526  mov     eax, 8007007Ah
0x18000752b  cmovnz  eax, r8d
0x18000752f  add     rsp, 20h
0x180007533  pop     rdi
0x180007534  retn
0x180007535  mov     eax, 80070057h
0x18000753a  jmp     short loc_18000754A
0x18000753c  mov     eax, 80070057h
0x180007541  test    rdx, rdx
0x180007544  jz      loc_1800074AB
0x18000754a  xor     r8d, r8d
0x18000754d  mov     [rcx], r8w
0x180007551  jmp     loc_1800074AB
```
