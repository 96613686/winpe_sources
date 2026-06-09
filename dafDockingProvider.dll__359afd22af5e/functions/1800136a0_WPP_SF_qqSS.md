# WPP_SF_qqSS

- ea: `0x1800136a0`
- end: `0x180013780`
- name: `WPP_SF_qqSS`
- size: `224`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, char, __int64, __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180011550`
- `0x180011d84`
- `0x1800123fc`
- `0x180012698`
- `0x180012860`

## callees

- `0x1800136a0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001376c`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001376c`

## pseudocode

```c
ULONG WPP_SF_qqSS(TRACEHANDLE LoggerHandle, USHORT a2, __int64 a3, __int64 a4, ...)
{
  const wchar_t *v4; // r9
  __int64 v5; // r8
  __int64 v7; // r10
  __int64 v8; // rax
  __int64 v9; // rcx
  const wchar_t *v10; // rax
  bool v11; // zf
  __int64 v13; // [rsp+98h] [rbp+20h] BYREF
  __int64 v14; // [rsp+A0h] [rbp+28h] BYREF
  va_list va; // [rsp+A0h] [rbp+28h]
  const wchar_t *v16; // [rsp+A8h] [rbp+30h]
  const wchar_t *v17; // [rsp+B0h] [rbp+38h]
  va_list va1; // [rsp+B8h] [rbp+40h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v14 = va_arg(va1, _QWORD);
  v16 = va_arg(va1, const wchar_t *);
  v17 = va_arg(va1, const wchar_t *);
  v13 = a4;
  v4 = v17;
  v5 = -1;
  v7 = 10;
  if ( v17 )
  {
    v8 = -1;
    do
      ++v8;
    while ( v17[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  v10 = v16;
  if ( !v17 )
    v4 = L"NULL";
  v11 = v16 == 0;
  if ( v16 )
  {
    do
      ++v5;
    while ( v16[v5] );
    v7 = 2 * v5 + 2;
    v11 = v16 == 0;
  }
  if ( v11 )
    v10 = L"NULL";
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
           a2,
           &v13,
           8,
           va,
           8,
           v10,
           v7,
           v4,
           v9,
           0);
}

```

## disassembly

```asm
0x1800136a0  mov     [rsp+arg_0], rbx
0x1800136a5  mov     [rsp+arg_18], r9
0x1800136aa  push    rdi
0x1800136ab  sub     rsp, 70h
0x1800136af  mov     r9, [rsp+78h+arg_30]
0x1800136b7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800136bb  xor     ebx, ebx
0x1800136bd  mov     r11, rcx
0x1800136c0  mov     r10d, 0Ah
0x1800136c6  test    r9, r9
0x1800136c9  jz      short loc_1800136E2
0x1800136cb  mov     rax, r8
0x1800136ce  inc     rax
0x1800136d1  cmp     [r9+rax*2], bx
0x1800136d6  jnz     short loc_1800136CE
0x1800136d8  lea     rcx, ds:2[rax*2]
0x1800136e0  jmp     short loc_1800136E5
0x1800136e2  mov     rcx, r10
0x1800136e5  mov     rax, [rsp+78h+arg_28]
0x1800136ed  lea     rdi, aNull_0; "NULL"
0x1800136f4  test    r9, r9
0x1800136f7  cmovz   r9, rdi
0x1800136fb  test    rax, rax
0x1800136fe  jz      short loc_180013715
0x180013700  inc     r8
0x180013703  cmp     [rax+r8*2], bx
0x180013708  jnz     short loc_180013700
0x18001370a  lea     r10, ds:2[r8*2]
0x180013712  test    rax, rax
0x180013715  mov     [rsp+78h+var_18], rbx
0x18001371a  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids; MessageGuid
0x180013721  mov     [rsp+78h+var_20], rcx
0x180013726  cmovz   rax, rdi
0x18001372a  mov     [rsp+78h+var_28], r9
0x18001372f  mov     ecx, 8
0x180013734  mov     [rsp+78h+var_30], r10
0x180013739  mov     [rsp+78h+var_38], rax
0x18001373e  lea     rax, [rsp+78h+arg_20]
0x180013746  mov     [rsp+78h+var_40], rcx
0x18001374b  mov     [rsp+78h+var_48], rax
0x180013750  lea     rax, [rsp+78h+arg_18]
0x180013758  mov     [rsp+78h+var_50], rcx
0x18001375d  movzx   r9d, dx; MessageNumber
0x180013761  lea     edx, [rcx+23h]; MessageFlags
0x180013764  mov     rcx, r11; LoggerHandle
0x180013767  mov     [rsp+78h+var_58], rax
0x18001376c  call    cs:__imp_TraceMessage
0x180013772  mov     rbx, [rsp+78h+arg_0]
0x18001377a  add     rsp, 70h
0x18001377e  pop     rdi
0x18001377f  retn
```
