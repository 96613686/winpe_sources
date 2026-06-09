# CJob::GetCurFile(ushort * *)

- ea: `0x18000d650`
- end: `0x18000d71f`
- name: `?GetCurFile@CJob@@UEAAJPEAPEAG@Z`
- size: `207`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001840`
- `0x18000d650`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d6cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d6cf`

## pseudocode

```c
__int64 __fastcall CJob::GetCurFile(CJob *this, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rbx
  unsigned int v4; // edi
  __int64 v5; // rax
  unsigned __int64 v6; // r14
  unsigned __int16 *v7; // rax
  __int64 result; // rax
  unsigned __int16 *v9; // r10
  unsigned __int16 v10[8]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v11; // [rsp+30h] [rbp-38h]

  v2 = (unsigned __int16 *)*((_QWORD *)this + 18);
  *(_OWORD *)v10 = 0;
  v11 = 0;
  if ( v2 && *v2 )
  {
    v4 = 0;
  }
  else
  {
    StringCchCopyW(v10, 0x10u, L"*.job");
    v2 = v10;
    v4 = 1;
  }
  v5 = -1;
  do
    ++v5;
  while ( v2[v5] );
  v6 = (int)v5 + 1LL;
  v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v6);
  if ( v7 )
  {
    *v7 = 0;
    StringCchCopyW(v7, v6, v2);
    result = v4;
    *a2 = v9;
  }
  else
  {
    *a2 = 0;
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000d650  mov     [rsp+arg_10], rbx
0x18000d655  mov     [rsp+arg_18], rbp
0x18000d65a  push    rsi
0x18000d65b  push    rdi
0x18000d65c  push    r14
0x18000d65e  sub     rsp, 50h
0x18000d662  mov     rax, cs:__security_cookie
0x18000d669  xor     rax, rsp
0x18000d66c  mov     [rsp+68h+var_28], rax
0x18000d671  mov     rbx, [rcx+90h]
0x18000d678  xorps   xmm0, xmm0
0x18000d67b  xor     ebp, ebp
0x18000d67d  mov     rsi, rdx
0x18000d680  movups  xmmword ptr [rsp+68h+var_48], xmm0
0x18000d685  movups  [rsp+68h+var_38], xmm0
0x18000d68a  test    rbx, rbx
0x18000d68d  jz      short loc_18000D698
0x18000d68f  cmp     [rbx], bp
0x18000d692  jz      short loc_18000D698
0x18000d694  mov     edi, ebp
0x18000d696  jmp     short loc_18000D6B8
0x18000d698  lea     r8, aJob_1; "*.job"
0x18000d69f  mov     edx, 10h; unsigned __int64
0x18000d6a4  lea     rcx, [rsp+68h+var_48]; unsigned __int16 *
0x18000d6a9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d6ae  lea     rbx, [rsp+68h+var_48]
0x18000d6b3  mov     edi, 1
0x18000d6b8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d6bc  inc     rax
0x18000d6bf  cmp     [rbx+rax*2], bp
0x18000d6c3  jnz     short loc_18000D6BC
0x18000d6c5  movsxd  r14, eax
0x18000d6c8  inc     r14
0x18000d6cb  lea     rcx, [r14+r14]; cb
0x18000d6cf  call    cs:__imp_CoTaskMemAlloc
0x18000d6d5  mov     r10, rax
0x18000d6d8  test    rax, rax
0x18000d6db  jnz     short loc_18000D6E7
0x18000d6dd  mov     [rsi], rbp
0x18000d6e0  mov     eax, 8007000Eh
0x18000d6e5  jmp     short loc_18000D6FD
0x18000d6e7  mov     r8, rbx; unsigned __int16 *
0x18000d6ea  mov     [rax], bp
0x18000d6ed  mov     rdx, r14; unsigned __int64
0x18000d6f0  mov     rcx, r10; unsigned __int16 *
0x18000d6f3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d6f8  mov     eax, edi
0x18000d6fa  mov     [rsi], r10
0x18000d6fd  mov     rcx, [rsp+68h+var_28]
0x18000d702  xor     rcx, rsp; StackCookie
0x18000d705  call    __security_check_cookie
0x18000d70a  lea     r11, [rsp+68h+var_18]
0x18000d70f  mov     rbx, [r11+30h]
0x18000d713  mov     rbp, [r11+38h]
0x18000d717  mov     rsp, r11
0x18000d71a  pop     r14
0x18000d71c  pop     rdi
0x18000d71d  pop     rsi
0x18000d71e  retn
```
