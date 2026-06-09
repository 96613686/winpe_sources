# TOKEN_KEY::GetIsEqual(IHttpCacheKey *)

- ea: `0x180011640`
- end: `0x1800116b4`
- name: `?GetIsEqual@TOKEN_KEY@@UEBA_NPEAVIHttpCacheKey@@@Z`
- size: `116`
- prototype: `bool __fastcall(TOKEN_KEY *__hidden this, struct IHttpCacheKey *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180011640`
- `0x180013010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001166b`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001166b`

## pseudocode

```c
bool __fastcall TOKEN_KEY::GetIsEqual(TOKEN_KEY *this, struct IHttpCacheKey *a2)
{
  __int64 v4; // rdi
  const unsigned __int16 *Str; // rax
  __int64 v6; // rdi
  int v7; // edx
  int v8; // ecx

  v4 = (*(__int64 (__fastcall **)(struct IHttpCacheKey *))(*(_QWORD *)a2 + 40LL))(a2);
  Str = STRU::QueryStr((TOKEN_KEY *)((char *)this + 8));
  v6 = v4 - (_QWORD)Str;
  do
  {
    v7 = *(const unsigned __int16 *)((char *)Str + v6);
    v8 = *Str - v7;
    if ( v8 )
      break;
    ++Str;
  }
  while ( v7 );
  return !v8
      && *((_DWORD *)this + 30) == (*(unsigned int (__fastcall **)(struct IHttpCacheKey *))(*(_QWORD *)a2 + 56LL))(a2);
}

```

## disassembly

```asm
0x180011640  mov     [rsp+arg_0], rbx
0x180011645  mov     [rsp+arg_8], rsi
0x18001164a  push    rdi
0x18001164b  sub     rsp, 20h
0x18001164f  mov     rax, [rdx]
0x180011652  mov     rsi, rcx
0x180011655  mov     rcx, rdx
0x180011658  mov     rbx, rdx
0x18001165b  mov     rax, [rax+28h]
0x18001165f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011664  lea     rcx, [rsi+8]
0x180011668  mov     rdi, rax
0x18001166b  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180011671  sub     rdi, rax
0x180011674  movzx   ecx, word ptr [rax]
0x180011677  movzx   edx, word ptr [rax+rdi]
0x18001167b  sub     ecx, edx
0x18001167d  jnz     short loc_180011687
0x18001167f  add     rax, 2
0x180011683  test    edx, edx
0x180011685  jnz     short loc_180011674
0x180011687  test    ecx, ecx
0x180011689  jnz     short loc_1800116A2
0x18001168b  mov     rax, [rbx]
0x18001168e  mov     rcx, rbx
0x180011691  mov     rax, [rax+38h]
0x180011695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001169a  cmp     [rsi+78h], eax
0x18001169d  setz    al
0x1800116a0  jmp     short loc_1800116A4
0x1800116a2  xor     al, al
0x1800116a4  mov     rbx, [rsp+28h+arg_0]
0x1800116a9  mov     rsi, [rsp+28h+arg_8]
0x1800116ae  add     rsp, 20h
0x1800116b2  pop     rdi
0x1800116b3  retn
```
