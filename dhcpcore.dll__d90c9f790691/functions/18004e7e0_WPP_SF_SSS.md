# WPP_SF_SSS

- ea: `0x18004e7e0`
- end: `0x18004e891`
- name: `WPP_SF_SSS`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x18001afbc`

## callees

- `0x18001a154`
- `0x18004e7e0`

## string_xrefs

- `0x18004e845`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces\?\DhcpClassIdBin`

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
0x18004e7e0  push    rbx
0x18004e7e2  sub     rsp, 50h
0x18004e7e6  mov     rdx, [rsp+58h+arg_20]
0x18004e7ee  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004e7f2  xor     ebx, ebx
0x18004e7f4  mov     r8d, 0Ah
0x18004e7fa  test    rdx, rdx
0x18004e7fd  jz      short loc_18004E815
0x18004e7ff  mov     rcx, rax
0x18004e802  inc     rcx
0x18004e805  cmp     [rdx+rcx*2], bx
0x18004e809  jnz     short loc_18004E802
0x18004e80b  lea     rcx, ds:2[rcx*2]
0x18004e813  jmp     short loc_18004E818
0x18004e815  mov     rcx, r8
0x18004e818  test    rdx, rdx
0x18004e81b  lea     r10, aNull_0; "NULL"
0x18004e822  cmovz   rdx, r10
0x18004e826  test    r9, r9
0x18004e829  jz      short loc_18004E840
0x18004e82b  inc     rax
0x18004e82e  cmp     [r9+rax*2], bx
0x18004e833  jnz     short loc_18004E82B
0x18004e835  lea     r8, ds:2[rax*2]
0x18004e83d  test    r9, r9
0x18004e840  mov     [rsp+58h+var_10], rbx
0x18004e845  lea     rax, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Tc"...
0x18004e84c  mov     [rsp+58h+var_18], 9Eh
0x18004e855  cmovz   r9, r10
0x18004e859  mov     [rsp+58h+var_20], rax
0x18004e85e  mov     r10d, 1Ch
0x18004e864  mov     [rsp+58h+var_28], rcx
0x18004e869  mov     r11d, 404h
0x18004e86f  mov     [rsp+58h+var_30], rdx
0x18004e874  mov     ecx, r11d
0x18004e877  mov     [rsp+58h+var_38], r8
0x18004e87c  mov     edx, r10d
0x18004e87f  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18004e886  call    FastWppTraceMessage
0x18004e88b  add     rsp, 50h
0x18004e88f  pop     rbx
0x18004e890  retn
```
