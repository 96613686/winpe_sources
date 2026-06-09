# WPP_SF_slSl

- ea: `0x18000dad4`
- end: `0x18000db91`
- name: `WPP_SF_slSl`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009fe0`

## callees

- `0x18000dad4`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000db7c`
- `ntdll!EtwTraceMessage` at `0x18000db7c`

## string_xrefs

- `0x18000db67`: `CreateLogFile`

## pseudocode

```c
__int64 WPP_SF_slSl(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, const wchar_t *a6, ...)
{
  const wchar_t *v6; // rdx
  __int64 v7; // rax
  __int64 v8; // rax
  int v10[6]; // [rsp+70h] [rbp-18h] BYREF
  va_list va; // [rsp+C0h] [rbp+38h] BYREF

  va_start(va, a6);
  v6 = a6;
  v10[0] = 611;
  if ( a6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a6[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  if ( !a6 )
    v6 = L"NULL";
  return EtwTraceMessage(
           a1,
           43,
           WPP_e57e63d898f739975f6041d6b7096587_Traceguids,
           10,
           "CreateLogFile",
           14,
           v10,
           4,
           v6,
           v8,
           va,
           4,
           0);
}

```

## disassembly

```asm
0x18000dad4  sub     rsp, 88h
0x18000dadb  mov     rdx, [rsp+88h+arg_28]
0x18000dae3  xor     r9d, r9d
0x18000dae6  mov     [rsp+88h+var_18], 263h
0x18000daee  mov     r10d, 0Ah
0x18000daf4  test    rdx, rdx
0x18000daf7  jz      short loc_18000DB11
0x18000daf9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000dafd  inc     rax
0x18000db00  cmp     [rdx+rax*2], r9w
0x18000db05  jnz     short loc_18000DAFD
0x18000db07  lea     rax, ds:2[rax*2]
0x18000db0f  jmp     short loc_18000DB14
0x18000db11  mov     rax, r10
0x18000db14  mov     [rsp+88h+var_28], r9
0x18000db19  lea     r8, aNull_0; "NULL"
0x18000db20  mov     r9d, 4
0x18000db26  test    rdx, rdx
0x18000db29  mov     [rsp+88h+var_30], r9
0x18000db2e  cmovz   rdx, r8
0x18000db32  lea     r8, [rsp+88h+arg_30]
0x18000db3a  mov     [rsp+88h+var_38], r8
0x18000db3f  lea     r8, WPP_e57e63d898f739975f6041d6b7096587_Traceguids
0x18000db46  mov     [rsp+88h+var_40], rax
0x18000db4b  lea     rax, [rsp+88h+var_18]
0x18000db50  mov     [rsp+88h+var_48], rdx
0x18000db55  mov     edx, 2Bh ; '+'
0x18000db5a  mov     [rsp+88h+var_50], r9
0x18000db5f  mov     r9d, r10d
0x18000db62  mov     [rsp+88h+var_58], rax
0x18000db67  lea     rax, aCreatelogfile_0; "CreateLogFile"
0x18000db6e  mov     [rsp+88h+var_60], 0Eh
0x18000db77  mov     [rsp+88h+var_68], rax
0x18000db7c  call    cs:__imp_EtwTraceMessage
0x18000db83  nop     dword ptr [rax+rax+00h]
0x18000db88  add     rsp, 88h
0x18000db8f  retn
```
