# OPTIONS_VERB_HANDLER::DoWork(IHttpContext *)

- ea: `0x180003f24`
- end: `0x180004012`
- name: `?DoWork@OPTIONS_VERB_HANDLER@@SA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001290`

## callees

- `0x180003a5c`
- `0x180003f24`
- `0x180004018`
- `0x180005010`

## pseudocode

```c
__int64 __fastcall OPTIONS_VERB_HANDLER::DoWork(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rax
  struct IHttpTraceContext *v4; // rax
  const struct _GUID *v5; // rdx
  int v6; // ebx
  __int64 v7; // rax

  v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
  v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 272LL))(a1);
  if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v3) )
  {
    v4 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 272LL))(a1);
    IISGeneralEvents::GENERAL_OPTIONS_HANDLER::RaiseEvent(v4, v5);
  }
  v6 = (*(__int64 (__fastcall **)(__int64, const char *, const char *, __int64, _DWORD))(*(_QWORD *)v2 + 40LL))(
         v2,
         "Public",
         "OPTIONS, TRACE, GET, HEAD, POST",
         31,
         0);
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  if ( v6 < 0 )
  {
    *(_WORD *)(v7 + 536) = 0;
    (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v2 + 24LL))(
      v2,
      500,
      "Internal Server Error",
      0,
      v6,
      0,
      0);
  }
  else
  {
    *(_QWORD *)(v7 + 224) = "OPTIONS, TRACE, GET, HEAD, POST";
    *(_WORD *)(v7 + 216) = 31;
  }
  return 2;
}

```

## disassembly

```asm
0x180003f24  push    rbx
0x180003f26  push    rbp
0x180003f27  push    rdi
0x180003f28  push    r14
0x180003f2a  sub     rsp, 48h
0x180003f2e  mov     rax, [rcx]
0x180003f31  mov     rbx, rcx
0x180003f34  mov     rax, [rax+20h]
0x180003f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f3d  mov     rdx, [rbx]
0x180003f40  mov     rdi, rax
0x180003f43  mov     rcx, rbx
0x180003f46  mov     rax, [rdx+110h]
0x180003f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f52  mov     rcx, rax
0x180003f55  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x180003f5a  test    eax, eax
0x180003f5c  jz      short loc_180003F78
0x180003f5e  mov     rcx, [rbx]
0x180003f61  mov     rax, [rcx+110h]
0x180003f68  mov     rcx, rbx
0x180003f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f70  mov     rcx, rax; struct IHttpTraceContext *
0x180003f73  call    ?RaiseEvent@GENERAL_OPTIONS_HANDLER@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z; IISGeneralEvents::GENERAL_OPTIONS_HANDLER::RaiseEvent(IHttpTraceContext *,_GUID const *)
0x180003f78  mov     rax, [rdi]
0x180003f7b  lea     rbp, aOptionsTraceGe; "OPTIONS, TRACE, GET, HEAD, POST"
0x180003f82  mov     r14d, 1Fh
0x180003f88  mov     [rsp+68h+var_48], 0
0x180003f90  mov     r9d, r14d
0x180003f93  lea     rdx, aPublic; "Public"
0x180003f9a  mov     r8, rbp
0x180003f9d  mov     rcx, rdi
0x180003fa0  mov     rax, [rax+28h]
0x180003fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fa9  mov     ebx, eax
0x180003fab  mov     rcx, rdi
0x180003fae  mov     rax, [rdi]
0x180003fb1  mov     rax, [rax+8]
0x180003fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fba  test    ebx, ebx
0x180003fbc  js      short loc_180003FCF
0x180003fbe  mov     [rax+0E0h], rbp
0x180003fc5  mov     [rax+0D8h], r14w
0x180003fcd  jmp     short loc_180004003
0x180003fcf  xor     ecx, ecx
0x180003fd1  lea     r8, aInternalServer; "Internal Server Error"
0x180003fd8  mov     [rax+218h], cx
0x180003fdf  xor     r9d, r9d
0x180003fe2  mov     rax, [rdi]
0x180003fe5  mov     edx, 1F4h
0x180003fea  mov     [rsp+68h+var_38], ecx
0x180003fee  mov     [rsp+68h+var_40], rcx
0x180003ff3  mov     rcx, rdi
0x180003ff6  mov     [rsp+68h+var_48], ebx
0x180003ffa  mov     rax, [rax+18h]
0x180003ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004003  mov     eax, 2
0x180004008  add     rsp, 48h
0x18000400c  pop     r14
0x18000400e  pop     rdi
0x18000400f  pop     rbp
0x180004010  pop     rbx
0x180004011  retn
```
