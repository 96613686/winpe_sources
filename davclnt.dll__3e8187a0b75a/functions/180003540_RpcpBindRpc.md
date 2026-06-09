# RpcpBindRpc

- ea: `0x180003540`
- end: `0x1800036c8`
- name: `RpcpBindRpc`
- size: `392`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, RPC_BINDING_HANDLE *)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180001600`
- `0x1800028f0`
- `0x1800033f0`
- `0x180003b90`

## callees

- `0x180003540`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180003563`
- `KERNEL32!LocalAlloc` at `0x180003563`
- `KERNEL32!LocalFree` at `0x1800035e2`
- `KERNEL32!LocalFree` at `0x180003665`
- `KERNEL32!LocalFree` at `0x1800035e2`
- `KERNEL32!LocalFree` at `0x180003665`
- `RPCRT4!RpcStringFreeW` at `0x180003684`
- `RPCRT4!RpcStringFreeW` at `0x180003684`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180003677`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180003677`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000365a`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000365a`

## string_xrefs

- `0x1800035f5`: `DAV RPC SERVICE`

## pseudocode

```c
__int64 __fastcall RpcpBindRpc(__int64 a1, __int64 a2, __int64 a3, RPC_BINDING_HANDLE *a4)
{
  unsigned __int16 *v5; // rdi
  __int64 v6; // r9
  const wchar_t *v7; // rdx
  __int64 v8; // rax
  __int64 v9; // r8
  unsigned __int16 *v10; // r10
  unsigned __int16 *v11; // rdx
  unsigned __int16 *v12; // rcx
  __int64 v13; // rax
  const wchar_t *v15; // rdx
  unsigned __int16 *v16; // r8
  unsigned __int16 *v17; // rdx
  RPC_STATUS v18; // ebx
  RPC_STATUS v19; // ebx
  RPC_WSTR String[3]; // [rsp+30h] [rbp-18h] BYREF

  String[0] = 0;
  *a4 = 0;
  v5 = (unsigned __int16 *)LocalAlloc(0, 0x2Eu);
  if ( !v5 )
    return 3221225495LL;
  v6 = 2147483646;
  v7 = L"\\PIPE\\";
  v8 = 2147483646;
  v9 = 23;
  v10 = v5;
  do
  {
    if ( !v8 )
      break;
    if ( !*v7 )
      break;
    *v10++ = *v7++;
    --v8;
    --v9;
  }
  while ( v9 );
  v11 = v10 - 1;
  v12 = v5;
  if ( v9 )
    v11 = v10;
  *v11 = 0;
  if ( !v9 )
  {
LABEL_13:
    LocalFree(v12);
    return 3221225485LL;
  }
  v13 = 23;
  while ( *v12 )
  {
    ++v12;
    if ( !--v13 )
      goto LABEL_12;
  }
  v15 = L"DAV RPC SERVICE";
  v16 = &v5[23 - v13];
  do
  {
    if ( !v6 )
      break;
    if ( !*v15 )
      break;
    *v16++ = *v15++;
    --v6;
    --v13;
  }
  while ( v13 );
  v17 = v16 - 1;
  if ( v13 )
    v17 = v16;
  *v17 = 0;
  if ( !v13 )
  {
LABEL_12:
    v12 = v5;
    goto LABEL_13;
  }
  v18 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_np", 0, v5, 0, String);
  LocalFree(v5);
  if ( v18 )
    return 3221225495LL;
  v19 = RpcBindingFromStringBindingW(String[0], a4);
  RpcStringFreeW(String);
  if ( v19 )
  {
    *a4 = 0;
    if ( (unsigned int)(v19 - 1706) <= 1 )
      return 3221225762LL;
    return 3221225495LL;
  }
  return 0;
}

```

## disassembly

```asm
0x180003540  mov     [rsp+arg_8], rbp
0x180003545  mov     [rsp+arg_10], rsi
0x18000354a  push    rdi
0x18000354b  sub     rsp, 40h
0x18000354f  xor     ebp, ebp
0x180003551  mov     edx, 2Eh ; '.'; uBytes
0x180003556  xor     ecx, ecx; uFlags
0x180003558  mov     [rsp+48h+String], rbp
0x18000355d  mov     [r9], rbp
0x180003560  mov     rsi, r9
0x180003563  call    cs:__imp_LocalAlloc
0x180003569  mov     rdi, rax
0x18000356c  test    rax, rax
0x18000356f  jz      loc_1800036BA
0x180003575  mov     r9d, 7FFFFFFEh
0x18000357b  lea     rdx, aPipe; "\\PIPE\\"
0x180003582  mov     r11d, 17h
0x180003588  mov     eax, r9d
0x18000358b  mov     r8d, r11d
0x18000358e  mov     r10, rdi
0x180003591  test    rax, rax
0x180003594  jz      short loc_1800035B3
0x180003596  movzx   ecx, word ptr [rdx]
0x180003599  test    cx, cx
0x18000359c  jz      short loc_1800035B3
0x18000359e  mov     [r10], cx
0x1800035a2  add     rdx, 2
0x1800035a6  add     r10, 2
0x1800035aa  dec     rax
0x1800035ad  sub     r8, 1
0x1800035b1  jnz     short loc_180003591
0x1800035b3  test    r8, r8
0x1800035b6  lea     rdx, [r10-2]
0x1800035ba  mov     rcx, rdi
0x1800035bd  cmovnz  rdx, r10
0x1800035c1  mov     [rdx], bp
0x1800035c4  jz      short loc_1800035E2
0x1800035c6  mov     rax, r11
0x1800035c9  nop     dword ptr [rax+00000000h]
0x1800035d0  cmp     [rcx], bp
0x1800035d3  jz      short loc_1800035F2
0x1800035d5  add     rcx, 2
0x1800035d9  sub     rax, 1
0x1800035dd  jnz     short loc_1800035D0
0x1800035df  mov     rcx, rdi; hMem
0x1800035e2  call    cs:__imp_LocalFree
0x1800035e8  mov     eax, 0C000000Dh
0x1800035ed  jmp     loc_180003695
0x1800035f2  sub     r11, rax
0x1800035f5  lea     rdx, aDavRpcService; "DAV RPC SERVICE"
0x1800035fc  lea     r8, [rdi+r11*2]
0x180003600  test    rax, rax
0x180003603  jz      short loc_180003627
0x180003605  test    r9, r9
0x180003608  jz      short loc_180003627
0x18000360a  movzx   ecx, word ptr [rdx]
0x18000360d  test    cx, cx
0x180003610  jz      short loc_180003627
0x180003612  mov     [r8], cx
0x180003616  add     rdx, 2
0x18000361a  add     r8, 2
0x18000361e  dec     r9
0x180003621  sub     rax, 1
0x180003625  jnz     short loc_180003605
0x180003627  test    rax, rax
0x18000362a  lea     rdx, [r8-2]
0x18000362e  cmovnz  rdx, r8
0x180003632  mov     [rdx], bp
0x180003635  jz      short loc_1800035DF
0x180003637  lea     rax, [rsp+48h+String]
0x18000363c  mov     [rsp+48h+arg_0], rbx
0x180003641  mov     [rsp+48h+StringBinding], rax; StringBinding
0x180003646  lea     rdx, ProtSeq; "ncacn_np"
0x18000364d  mov     r9, rdi; Endpoint
0x180003650  mov     [rsp+48h+Options], rbp; Options
0x180003655  xor     r8d, r8d; NetworkAddr
0x180003658  xor     ecx, ecx; ObjUuid
0x18000365a  call    cs:__imp_RpcStringBindingComposeW
0x180003660  mov     rcx, rdi; hMem
0x180003663  mov     ebx, eax
0x180003665  call    cs:__imp_LocalFree
0x18000366b  test    ebx, ebx
0x18000366d  jnz     short loc_1800036C1
0x18000366f  mov     rcx, [rsp+48h+String]; StringBinding
0x180003674  mov     rdx, rsi; Binding
0x180003677  call    cs:__imp_RpcBindingFromStringBindingW
0x18000367d  lea     rcx, [rsp+48h+String]; String
0x180003682  mov     ebx, eax
0x180003684  call    cs:__imp_RpcStringFreeW
0x18000368a  test    ebx, ebx
0x18000368c  jnz     short loc_1800036A5
0x18000368e  mov     eax, ebp
0x180003690  mov     rbx, [rsp+48h+arg_0]
0x180003695  mov     rbp, [rsp+48h+arg_8]
0x18000369a  mov     rsi, [rsp+48h+arg_10]
0x18000369f  add     rsp, 40h
0x1800036a3  pop     rdi
0x1800036a4  retn
0x1800036a5  lea     eax, [rbx-6AAh]
0x1800036ab  mov     [rsi], rbp
0x1800036ae  cmp     eax, 1
0x1800036b1  ja      short loc_1800036C1
0x1800036b3  mov     eax, 0C0000122h
0x1800036b8  jmp     short loc_180003690
0x1800036ba  mov     eax, 0C0000017h
0x1800036bf  jmp     short loc_180003695
0x1800036c1  mov     eax, 0C0000017h
0x1800036c6  jmp     short loc_180003690
```
