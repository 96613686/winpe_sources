# WPP_SF_SSS

- ea: `0x1800126dc`
- end: `0x18001278d`
- name: `WPP_SF_SSS`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x18000f964`

## callees

- `0x180003e70`
- `0x1800126dc`

## string_xrefs

- `0x180012741`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces\?\DhcpClassIdBin`

## pseudocode

```c
ULONG __fastcall WPP_SF_SSS(__int64 a1, __int64 a2, __int64 a3, const wchar_t *a4, const wchar_t *a5)
{
  const wchar_t *v5; // rdx
  __int64 v6; // rax
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rcx
  bool v10; // zf

  v5 = a5;
  v6 = -1;
  v7 = 10;
  if ( a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a5[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  if ( !a5 )
    v5 = L"NULL";
  v10 = a4 == 0;
  if ( a4 )
  {
    do
      ++v6;
    while ( a4[v6] );
    v7 = 2 * v6 + 2;
    v10 = a4 == 0;
  }
  if ( v10 )
    a4 = L"NULL";
  return FastWppTraceMessage(
           1028,
           0x1Cu,
           (ULONGLONG)WPP_94d5010c5674399d06148e3a91870046_Traceguids,
           a4,
           v7,
           v5,
           v9,
           L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces\\?\\DhcpClassIdBin",
           158,
           0);
}

```

## disassembly

```asm
0x1800126dc  push    rbx
0x1800126de  sub     rsp, 50h
0x1800126e2  mov     rdx, [rsp+58h+arg_20]
0x1800126ea  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800126ee  xor     ebx, ebx
0x1800126f0  mov     r8d, 0Ah
0x1800126f6  test    rdx, rdx
0x1800126f9  jz      short loc_180012711
0x1800126fb  mov     rcx, rax
0x1800126fe  inc     rcx
0x180012701  cmp     [rdx+rcx*2], bx
0x180012705  jnz     short loc_1800126FE
0x180012707  lea     rcx, ds:2[rcx*2]
0x18001270f  jmp     short loc_180012714
0x180012711  mov     rcx, r8
0x180012714  test    rdx, rdx
0x180012717  lea     r10, aNull; "NULL"
0x18001271e  cmovz   rdx, r10
0x180012722  test    r9, r9
0x180012725  jz      short loc_18001273C
0x180012727  inc     rax
0x18001272a  cmp     [r9+rax*2], bx
0x18001272f  jnz     short loc_180012727
0x180012731  lea     r8, ds:2[rax*2]
0x180012739  test    r9, r9
0x18001273c  mov     [rsp+58h+var_10], rbx
0x180012741  lea     rax, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Tc"...
0x180012748  mov     [rsp+58h+var_18], 9Eh
0x180012751  cmovz   r9, r10
0x180012755  mov     [rsp+58h+var_20], rax
0x18001275a  mov     r10d, 1Ch
0x180012760  mov     [rsp+58h+var_28], rcx
0x180012765  mov     r11d, 404h
0x18001276b  mov     [rsp+58h+var_30], rdx
0x180012770  mov     ecx, r11d
0x180012773  mov     [rsp+58h+var_38], r8
0x180012778  mov     edx, r10d
0x18001277b  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x180012782  call    FastWppTraceMessage
0x180012787  add     rsp, 50h
0x18001278b  pop     rbx
0x18001278c  retn
```
