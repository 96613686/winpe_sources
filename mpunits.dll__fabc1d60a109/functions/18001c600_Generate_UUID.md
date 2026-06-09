# Generate_UUID

- ea: `0x18001c600`
- end: `0x18001c6af`
- name: `Generate_UUID`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001bc60`

## callees

- `0x18001c600`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `msvcrt!free` at `0x18001c694`
- `msvcrt!free` at `0x18001c694`
- `msvcrt!calloc` at `0x18001c659`
- `msvcrt!calloc` at `0x18001c659`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001c682`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001c682`
- `RPCRT4!UuidCreateSequential` at `0x18001c66c`
- `RPCRT4!UuidCreateSequential` at `0x18001c66c`

## pseudocode

```c
OLECHAR *__fastcall Generate_UUID(__int128 *a1)
{
  __int64 v1; // xmm1_8
  OLECHAR *v2; // rbx
  __int128 v4; // [rsp+20h] [rbp-48h] BYREF
  __int64 v5; // [rsp+30h] [rbp-38h]
  UUID Uuid; // [rsp+40h] [rbp-28h] BYREF

  Uuid = 0;
  if ( NITS_PRESENCE_STUB == 1
    || (v1 = *((_QWORD *)a1 + 2),
        v4 = *a1,
        v5 = v1,
        !((unsigned int (__fastcall *)(__int128 *, _QWORD))NITS_STUB[0])(&v4, 0)) )
  {
    v2 = (OLECHAR *)calloc(1u, 0x50u);
    if ( v2 )
    {
      if ( !UuidCreateSequential(&Uuid) && StringFromGUID2(&Uuid, v2, 40) )
        return v2;
      free(v2);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001c600  push    rbx
0x18001c602  sub     rsp, 60h
0x18001c606  mov     rax, cs:__security_cookie
0x18001c60d  xor     rax, rsp
0x18001c610  mov     [rsp+68h+var_18], rax
0x18001c615  cmp     cs:NITS_PRESENCE_STUB, 1
0x18001c61d  xorps   xmm0, xmm0
0x18001c620  movups  xmmword ptr [rsp+68h+Uuid.Data1], xmm0
0x18001c625  jz      short loc_18001C651
0x18001c627  movaps  xmm0, xmmword ptr [rcx]
0x18001c62a  xor     edx, edx
0x18001c62c  movsd   xmm1, qword ptr [rcx+10h]
0x18001c631  lea     rcx, [rsp+68h+var_48]
0x18001c636  mov     rax, cs:NITS_STUB
0x18001c63d  movaps  [rsp+68h+var_48], xmm0
0x18001c642  movsd   [rsp+68h+var_38], xmm1
0x18001c648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c64d  test    eax, eax
0x18001c64f  jnz     short loc_18001C69A
0x18001c651  mov     edx, 50h ; 'P'; Size
0x18001c656  lea     ecx, [rdx-4Fh]; Count
0x18001c659  call    cs:__imp_calloc
0x18001c65f  mov     rbx, rax
0x18001c662  test    rax, rax
0x18001c665  jz      short loc_18001C69A
0x18001c667  lea     rcx, [rsp+68h+Uuid]; Uuid
0x18001c66c  call    cs:__imp_UuidCreateSequential
0x18001c672  test    eax, eax
0x18001c674  jnz     short loc_18001C691
0x18001c676  lea     r8d, [rax+28h]; cchMax
0x18001c67a  mov     rdx, rbx; lpsz
0x18001c67d  lea     rcx, [rsp+68h+Uuid]; rguid
0x18001c682  call    cs:__imp_StringFromGUID2
0x18001c688  test    eax, eax
0x18001c68a  jz      short loc_18001C691
0x18001c68c  mov     rax, rbx
0x18001c68f  jmp     short loc_18001C69C
0x18001c691  mov     rcx, rbx; Block
0x18001c694  call    cs:__imp_free
0x18001c69a  xor     eax, eax
0x18001c69c  mov     rcx, [rsp+68h+var_18]
0x18001c6a1  xor     rcx, rsp; StackCookie
0x18001c6a4  call    __security_check_cookie
0x18001c6a9  add     rsp, 60h
0x18001c6ad  pop     rbx
0x18001c6ae  retn
```
