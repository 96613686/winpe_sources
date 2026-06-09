# HTTP_COMPRESSION::UpdateVaryHeader(IHttpContext *)

- ea: `0x180002000`
- end: `0x180002085`
- name: `?UpdateVaryHeader@HTTP_COMPRESSION@@CAJPEAVIHttpContext@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(struct IHttpContext *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800010b0`

## callees

- `0x180002000`
- `0x180005f90`
- `0x180009010`

## import_xrefs

- `msvcrt!strchr` at `0x180006a76`
- `msvcrt!strchr` at `0x180006a76`

## pseudocode

```c
__int64 __fastcall HTTP_COMPRESSION::UpdateVaryHeader(struct IHttpContext *a1)
{
  __int64 v1; // rbx
  __int64 v2; // rax
  char v4[16]; // [rsp+30h] [rbp-28h] BYREF

  v1 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
  v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 8LL))(v1);
  strcpy(v4, "Accept-Encoding");
  if ( *(_WORD *)(v2 + 504) == 1 && strchr(*(const char **)(v2 + 512), 42) )
    return 0;
  else
    return (*(__int64 (__fastcall **)(__int64, __int64, char *, __int64, _DWORD))(*(_QWORD *)v1 + 32LL))(
             v1,
             28,
             v4,
             15,
             0);
}

```

## disassembly

```asm
0x180002000  push    rbx
0x180002002  sub     rsp, 50h
0x180002006  mov     rax, cs:__security_cookie
0x18000200d  xor     rax, rsp
0x180002010  mov     [rsp+58h+var_18], rax
0x180002015  mov     rax, [rcx]
0x180002018  mov     rax, [rax+20h]
0x18000201c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002021  mov     rbx, rax
0x180002024  mov     rcx, rbx
0x180002027  mov     rax, [rax]
0x18000202a  mov     rax, [rax+8]
0x18000202e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002033  movups  xmm0, xmmword ptr cs:aAcceptEncoding; "Accept-Encoding"
0x18000203a  movups  [rsp+58h+var_28], xmm0
0x18000203f  cmp     word ptr [rax+1F8h], 1
0x180002047  jz      loc_180006A6A
0x18000204d  mov     rax, [rbx]
0x180002050  lea     r8, [rsp+58h+var_28]
0x180002055  xor     ecx, ecx
0x180002057  mov     r9d, 0Fh
0x18000205d  mov     [rsp+58h+var_38], ecx
0x180002061  mov     edx, 1Ch
0x180002066  mov     rcx, rbx
0x180002069  mov     rax, [rax+20h]
0x18000206d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002072  mov     rcx, [rsp+58h+var_18]
0x180002077  xor     rcx, rsp; StackCookie
0x18000207a  call    __security_check_cookie
0x18000207f  add     rsp, 50h
0x180002083  pop     rbx
0x180002084  retn
0x180006a6a  mov     rcx, [rax+200h]; Str
0x180006a71  mov     edx, 2Ah ; '*'; Val
0x180006a76  call    cs:__imp_strchr
0x180006a7c  test    rax, rax
0x180006a7f  jz      loc_18000204D
0x180006a85  xor     ecx, ecx
0x180006a87  mov     eax, ecx
0x180006a89  jmp     loc_180002072
```
