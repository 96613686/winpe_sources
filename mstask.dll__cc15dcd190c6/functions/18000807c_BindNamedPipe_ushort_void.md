# BindNamedPipe(ushort *,void * *)

- ea: `0x18000807c`
- end: `0x18000816f`
- name: `?BindNamedPipe@@YAJPEAGPEAPEAX@Z`
- size: `243`
- prototype: `__int64 __fastcall(unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007e60`
- `0x180009acc`

## callees

- `0x180001840`
- `0x18000807c`
- `0x180008180`
- `0x18001aac0`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x180008130`
- `RPCRT4!RpcStringBindingComposeW` at `0x180008130`

## pseudocode

```c
RPC_STATUS __fastcall BindNamedPipe(unsigned __int16 *a1, void **a2)
{
  int v3; // edx
  __int64 v4; // rax
  RPC_STATUS result; // eax
  RPC_WSTR String[2]; // [rsp+30h] [rbp-238h] BYREF
  int v7; // [rsp+40h] [rbp-228h] BYREF
  unsigned __int16 v8[262]; // [rsp+44h] [rbp-224h] BYREF

  String[0] = 0;
  *a2 = 0;
  if ( !a1 || *a1 != 92 || (v3 = 1, a1[1] != 92) )
    v3 = 0;
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  if ( !v3 && (_DWORD)v4 )
  {
    if ( (unsigned int)(v4 + 2) >= 0x206 )
      return 1210;
    v7 = 6029404;
    v8[0] = 0;
    if ( (int)StringCchCopyW(v8, 0x101u, a1) < 0 )
      return 1210;
    a1 = (unsigned __int16 *)&v7;
  }
  result = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_np", a1, (RPC_WSTR)L"\\PIPE\\atsvc", 0, String);
  if ( !result )
    return BindingFromStringBinding(String, a2);
  return result;
}

```

## disassembly

```asm
0x18000807c  mov     [rsp+arg_10], rbx
0x180008081  push    rdi
0x180008082  sub     rsp, 260h
0x180008089  mov     rax, cs:__security_cookie
0x180008090  xor     rax, rsp
0x180008093  mov     [rsp+268h+var_18], rax
0x18000809b  xor     edi, edi
0x18000809d  mov     rbx, rdx
0x1800080a0  mov     [rsp+268h+String], rdi
0x1800080a5  mov     [rdx], rdi
0x1800080a8  lea     r8d, [rdi+5Ch]
0x1800080ac  test    rcx, rcx
0x1800080af  jz      short loc_1800080C1
0x1800080b1  cmp     [rcx], r8w
0x1800080b5  jnz     short loc_1800080C1
0x1800080b7  lea     edx, [rdi+1]
0x1800080ba  cmp     [rcx+2], r8w
0x1800080bf  jz      short loc_1800080C3
0x1800080c1  mov     edx, edi
0x1800080c3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800080c7  inc     rax
0x1800080ca  cmp     [rcx+rax*2], di
0x1800080ce  jnz     short loc_1800080C7
0x1800080d0  test    edx, edx
0x1800080d2  jnz     short loc_18000810E
0x1800080d4  test    eax, eax
0x1800080d6  jz      short loc_18000810E
0x1800080d8  add     eax, 2
0x1800080db  cmp     eax, 206h
0x1800080e0  jnb     loc_180008168
0x1800080e6  mov     r8, rcx; unsigned __int16 *
0x1800080e9  mov     [rsp+268h+var_228], 5C005Ch
0x1800080f1  lea     rcx, [rsp+268h+var_224]; unsigned __int16 *
0x1800080f6  mov     [rsp+268h+var_224], di
0x1800080fb  mov     edx, 101h; unsigned __int64
0x180008100  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008105  test    eax, eax
0x180008107  js      short loc_180008168
0x180008109  lea     rcx, [rsp+268h+var_228]
0x18000810e  lea     rax, [rsp+268h+String]
0x180008113  mov     r8, rcx; NetworkAddr
0x180008116  mov     [rsp+268h+StringBinding], rax; StringBinding
0x18000811b  lea     r9, Endpoint; "\\PIPE\\atsvc"
0x180008122  lea     rdx, ProtSeq; "ncacn_np"
0x180008129  mov     [rsp+268h+Options], rdi; Options
0x18000812e  xor     ecx, ecx; ObjUuid
0x180008130  call    cs:__imp_RpcStringBindingComposeW
0x180008136  test    eax, eax
0x180008138  jnz     short loc_180008147
0x18000813a  mov     rdx, rbx; void **
0x18000813d  lea     rcx, [rsp+268h+String]; String
0x180008142  call    ?BindingFromStringBinding@@YAJPEAPEAGPEAPEAX@Z; BindingFromStringBinding(ushort * *,void * *)
0x180008147  mov     rcx, [rsp+268h+var_18]
0x18000814f  xor     rcx, rsp; StackCookie
0x180008152  call    __security_check_cookie
0x180008157  mov     rbx, [rsp+268h+arg_10]
0x18000815f  add     rsp, 260h
0x180008166  pop     rdi
0x180008167  retn
0x180008168  mov     eax, 4BAh
0x18000816d  jmp     short loc_180008147
```
