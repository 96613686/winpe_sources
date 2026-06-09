# W3_MAIN_CONTEXT::SetClientCertificate(_HTTP_SSL_CLIENT_CERT_INFO *)

- ea: `0x180019fec`
- end: `0x18001a073`
- name: `?SetClientCertificate@W3_MAIN_CONTEXT@@QEAAJPEAU_HTTP_SSL_CLIENT_CERT_INFO@@@Z`
- size: `135`
- prototype: `__int64 __fastcall(W3_MAIN_CONTEXT *__hidden this, struct _HTTP_SSL_CLIENT_CERT_INFO *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006f10`
- `0x18001a5a8`

## callees

- `0x180019fec`

## import_xrefs

- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18001a03f`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18001a03f`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18001a008`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18001a008`

## pseudocode

```c
__int64 __fastcall W3_MAIN_CONTEXT::SetClientCertificate(W3_MAIN_CONTEXT *this, struct _HTTP_SSL_CLIENT_CERT_INFO *a2)
{
  char *v4; // rbx

  v4 = (char *)ALLOC_CACHE_HANDLER::Alloc(CERTIFICATE_CONTEXT::sm_pachCertContexts);
  if ( v4 )
  {
    *((_QWORD *)v4 + 1) = a2;
    *(_QWORD *)v4 = &CERTIFICATE_CONTEXT::`vftable';
    *((_DWORD *)v4 + 4) = 0;
    BUFFER::BUFFER((BUFFER *)(v4 + 24), (unsigned __int8 *)v4 + 72, 0xD0u);
  }
  else
  {
    v4 = 0;
  }
  *((_QWORD *)this + 1185) = v4;
  return v4 == 0 ? 0x80070008 : 0;
}

```

## disassembly

```asm
0x180019fec  mov     [rsp+arg_0], rbx
0x180019ff1  mov     [rsp+arg_8], rsi
0x180019ff6  push    rdi
0x180019ff7  sub     rsp, 20h
0x180019ffb  mov     rdi, rcx
0x180019ffe  mov     rsi, rdx
0x18001a001  mov     rcx, cs:?sm_pachCertContexts@CERTIFICATE_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CERTIFICATE_CONTEXT::sm_pachCertContexts
0x18001a008  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18001a00f  nop     dword ptr [rax+rax+00h]
0x18001a014  mov     rbx, rax
0x18001a017  test    rax, rax
0x18001a01a  jz      short loc_18001A04D
0x18001a01c  lea     rax, ??_7CERTIFICATE_CONTEXT@@6B@; const CERTIFICATE_CONTEXT::`vftable'
0x18001a023  mov     [rbx+8], rsi
0x18001a027  lea     rdx, [rbx+48h]
0x18001a02b  mov     [rbx], rax
0x18001a02e  lea     rcx, [rbx+18h]
0x18001a032  mov     dword ptr [rbx+10h], 0
0x18001a039  mov     r8d, 0D0h
0x18001a03f  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18001a046  nop     dword ptr [rax+rax+00h]
0x18001a04b  jmp     short loc_18001A04F
0x18001a04d  xor     ebx, ebx
0x18001a04f  mov     rsi, [rsp+28h+arg_8]
0x18001a054  mov     [rdi+2508h], rbx
0x18001a05b  neg     rbx
0x18001a05e  mov     rbx, [rsp+28h+arg_0]
0x18001a063  sbb     eax, eax
0x18001a065  not     eax
0x18001a067  and     eax, 80070008h
0x18001a06c  add     rsp, 20h
0x18001a070  pop     rdi
0x18001a071  retn
```
