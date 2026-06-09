# CscUtil_CreateStringCopyForCom(ushort const *,ushort * *)

- ea: `0x180003c80`
- end: `0x180003d56`
- name: `?CscUtil_CreateStringCopyForCom@@YAJPEBGPEAPEAG@Z`
- size: `214`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `14`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800036a0`
- `0x180017e60`
- `0x18001d1a0`
- `0x18001dc80`
- `0x18001e5f4`
- `0x18001ecf0`
- `0x180020270`
- `0x18003c5fc`
- `0x18003ccc0`
- `0x18003ccd0`
- `0x18003ccf0`
- `0x180046860`
- `0x1800479b4`
- `0x180047c20`

## callees

- `0x180003c80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003cb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003cb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d47`

## pseudocode

```c
__int64 __fastcall CscUtil_CreateStringCopyForCom(const unsigned __int16 *a1, LPVOID *a2)
{
  const unsigned __int16 *v3; // rbx
  __int64 v4; // rdi
  unsigned __int64 v5; // rdi
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rdx
  __int64 v8; // rcx
  unsigned __int16 *v9; // rcx
  int v10; // ebx

  v3 = a1;
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  v5 = v4 + 1;
  v6 = (unsigned __int16 *)CoTaskMemAlloc(2 * v5);
  *a2 = v6;
  v7 = v6;
  if ( v6 )
  {
    if ( v5 )
    {
      if ( v5 > 0x7FFFFFFF )
      {
        v10 = -2147024809;
        *v6 = 0;
        goto LABEL_18;
      }
      v8 = 2147483646;
      do
      {
        if ( !v8 )
          break;
        if ( !*v3 )
          break;
        *v7++ = *v3++;
        --v8;
        --v5;
      }
      while ( v5 );
      v9 = v7 - 1;
      v10 = -2147024774;
      if ( v5 )
      {
        v9 = v7;
        v10 = 0;
      }
      *v9 = 0;
    }
    else
    {
      v10 = -2147024809;
    }
    if ( v10 >= 0 )
      return (unsigned int)v10;
LABEL_18:
    CoTaskMemFree(*a2);
    *a2 = 0;
    return (unsigned int)v10;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180003c80  mov     [rsp+arg_0], rbx
0x180003c85  mov     [rsp+arg_8], rsi
0x180003c8a  push    rdi
0x180003c8b  sub     rsp, 20h
0x180003c8f  mov     rsi, rdx
0x180003c92  mov     rbx, rcx
0x180003c95  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180003c9c  nop     dword ptr [rax+00h]
0x180003ca0  inc     rdi
0x180003ca3  cmp     word ptr [rcx+rdi*2], 0
0x180003ca8  jnz     short loc_180003CA0
0x180003caa  inc     rdi
0x180003cad  lea     rcx, [rdi+rdi]; cb
0x180003cb1  call    cs:__imp_CoTaskMemAlloc
0x180003cb7  mov     [rsi], rax
0x180003cba  mov     rdx, rax
0x180003cbd  test    rax, rax
0x180003cc0  jz      short loc_180003D27
0x180003cc2  test    rdi, rdi
0x180003cc5  jz      short loc_180003D35
0x180003cc7  cmp     rdi, 7FFFFFFFh
0x180003cce  ja      short loc_180003D2E
0x180003cd0  mov     ecx, 7FFFFFFEh
0x180003cd5  test    rcx, rcx
0x180003cd8  jz      short loc_180003CF6
0x180003cda  movzx   eax, word ptr [rbx]
0x180003cdd  test    ax, ax
0x180003ce0  jz      short loc_180003CF6
0x180003ce2  mov     [rdx], ax
0x180003ce5  add     rbx, 2
0x180003ce9  add     rdx, 2
0x180003ced  dec     rcx
0x180003cf0  sub     rdi, 1
0x180003cf4  jnz     short loc_180003CD5
0x180003cf6  test    rdi, rdi
0x180003cf9  lea     rcx, [rdx-2]
0x180003cfd  mov     ebx, 8007007Ah
0x180003d02  cmovnz  rcx, rdx
0x180003d06  xor     eax, eax
0x180003d08  test    rdi, rdi
0x180003d0b  cmovnz  ebx, eax
0x180003d0e  mov     [rcx], ax
0x180003d11  test    ebx, ebx
0x180003d13  js      short loc_180003D44
0x180003d15  mov     eax, ebx
0x180003d17  mov     rbx, [rsp+28h+arg_0]
0x180003d1c  mov     rsi, [rsp+28h+arg_8]
0x180003d21  add     rsp, 20h
0x180003d25  pop     rdi
0x180003d26  retn
0x180003d27  mov     eax, 8007000Eh
0x180003d2c  jmp     short loc_180003D17
0x180003d2e  mov     ebx, 80070057h
0x180003d33  jmp     short loc_180003D3F
0x180003d35  mov     ebx, 80070057h
0x180003d3a  test    rdi, rdi
0x180003d3d  jz      short loc_180003D11
0x180003d3f  xor     eax, eax
0x180003d41  mov     [rdx], ax
0x180003d44  mov     rcx, [rsi]; pv
0x180003d47  call    cs:__imp_CoTaskMemFree
0x180003d4d  mov     qword ptr [rsi], 0
0x180003d54  jmp     short loc_180003D15
```
