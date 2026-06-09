# W3_MAIN_CONTEXT::SetClientCertificate(_HTTP_SSL_CLIENT_CERT_INFO *)

- ea: `0x180018ad0`
- end: `0x180018b4a`
- name: `?SetClientCertificate@W3_MAIN_CONTEXT@@QEAAJPEAU_HTTP_SSL_CLIENT_CERT_INFO@@@Z`
- size: `122`
- prototype: `__int64 __fastcall(W3_MAIN_CONTEXT *__hidden this, struct _HTTP_SSL_CLIENT_CERT_INFO *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006a70`
- `0x180018ff4`

## callees

- `0x180018ad0`

## import_xrefs

- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180018b1d`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180018b1d`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180018aec`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180018aec`

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
0x180018ad0  mov     [rsp+arg_0], rbx
0x180018ad5  mov     [rsp+arg_8], rsi
0x180018ada  push    rdi
0x180018adb  sub     rsp, 20h
0x180018adf  mov     rdi, rcx
0x180018ae2  mov     rsi, rdx
0x180018ae5  mov     rcx, cs:?sm_pachCertContexts@CERTIFICATE_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CERTIFICATE_CONTEXT::sm_pachCertContexts
0x180018aec  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180018af2  mov     rbx, rax
0x180018af5  test    rax, rax
0x180018af8  jz      short loc_180018B25
0x180018afa  lea     rax, ??_7CERTIFICATE_CONTEXT@@6B@; const CERTIFICATE_CONTEXT::`vftable'
0x180018b01  mov     [rbx+8], rsi
0x180018b05  lea     rdx, [rbx+48h]
0x180018b09  mov     [rbx], rax
0x180018b0c  lea     rcx, [rbx+18h]
0x180018b10  mov     dword ptr [rbx+10h], 0
0x180018b17  mov     r8d, 0D0h
0x180018b1d  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180018b23  jmp     short loc_180018B27
0x180018b25  xor     ebx, ebx
0x180018b27  mov     rsi, [rsp+28h+arg_8]
0x180018b2c  mov     [rdi+2508h], rbx
0x180018b33  neg     rbx
0x180018b36  mov     rbx, [rsp+28h+arg_0]
0x180018b3b  sbb     eax, eax
0x180018b3d  not     eax
0x180018b3f  and     eax, 80070008h
0x180018b44  add     rsp, 20h
0x180018b48  pop     rdi
0x180018b49  retn
```
