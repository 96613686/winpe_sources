# IP_MODULE::CacheIpRecord(IP_RECORD *,IHttpContext *,REQUEST_CONTEXT * *)

- ea: `0x1800044c8`
- end: `0x1800045b4`
- name: `?CacheIpRecord@IP_MODULE@@CAJPEAVIP_RECORD@@PEAVIHttpContext@@PEAPEAVREQUEST_CONTEXT@@@Z`
- size: `236`
- prototype: `__int64 __fastcall(struct IP_RECORD *, struct IHttpContext *, struct REQUEST_CONTEXT **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800047a4`

## callees

- `0x180001008`
- `0x180001048`
- `0x1800044c8`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall IP_MODULE::CacheIpRecord(struct IP_RECORD *a1, struct IHttpContext *a2, struct REQUEST_CONTEXT **a3)
{
  volatile signed __int32 *v6; // rax
  volatile signed __int32 *v7; // rbx
  __int64 v8; // rax
  __int64 result; // rax
  __int64 (__fastcall ***v10)(_QWORD, void *); // rax

  *a3 = 0;
  v6 = (volatile signed __int32 *)operator new(0x20u);
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  *((_DWORD *)v6 + 2) = 1;
  *(_QWORD *)v6 = &REQUEST_CONTEXT::`vftable';
  *((_QWORD *)v6 + 2) = a1;
  *((_WORD *)v6 + 12) = 0;
  v8 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 56LL))(a2);
  result = (*(__int64 (__fastcall **)(__int64, volatile signed __int32 *, void *))(*(_QWORD *)v8 + 8LL))(
             v8,
             v7,
             g_pModuleID);
  if ( (_DWORD)result == -2147024811 )
  {
    if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      *(_QWORD *)v7 = &REQUEST_CONTEXT::`vftable';
      operator delete((void *)v7);
    }
    v10 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 56LL))(a2);
    v7 = (volatile signed __int32 *)(**v10)(v10, g_pModuleID);
    result = 0;
  }
  else if ( (int)result < 0 )
  {
    return result;
  }
  *a3 = (struct REQUEST_CONTEXT *)v7;
  return result;
}

```

## disassembly

```asm
0x1800044c8  mov     [rsp+arg_0], rbx
0x1800044cd  mov     [rsp+arg_8], rbp
0x1800044d2  push    rsi
0x1800044d3  push    rdi
0x1800044d4  push    r14
0x1800044d6  sub     rsp, 20h
0x1800044da  mov     rbp, rcx
0x1800044dd  mov     qword ptr [r8], 0
0x1800044e4  mov     ecx, 20h ; ' '; Size
0x1800044e9  mov     rdi, r8
0x1800044ec  mov     rsi, rdx
0x1800044ef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800044f4  mov     rbx, rax
0x1800044f7  test    rax, rax
0x1800044fa  jz      loc_18000459C
0x180004500  mov     dword ptr [rax+8], 1
0x180004507  lea     r14, ??_7REQUEST_CONTEXT@@6B@; const REQUEST_CONTEXT::`vftable'
0x18000450e  mov     [rax], r14
0x180004511  mov     rcx, rsi
0x180004514  mov     [rax+10h], rbp
0x180004518  xor     eax, eax
0x18000451a  mov     [rbx+18h], ax
0x18000451e  mov     rax, [rsi]
0x180004521  mov     rax, [rax+38h]
0x180004525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000452a  mov     r8, cs:?g_pModuleID@@3PEAXEA; void * g_pModuleID
0x180004531  mov     r9, rax
0x180004534  mov     rdx, rbx
0x180004537  mov     rcx, [rax]
0x18000453a  mov     rax, [rcx+8]
0x18000453e  mov     rcx, r9
0x180004541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004546  cmp     eax, 80070055h
0x18000454b  jnz     short loc_180004593
0x18000454d  or      eax, 0FFFFFFFFh
0x180004550  lock xadd [rbx+8], eax
0x180004555  cmp     eax, 1
0x180004558  jnz     short loc_180004565
0x18000455a  mov     rcx, rbx; Block
0x18000455d  mov     [rbx], r14
0x180004560  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004565  mov     rax, [rsi]
0x180004568  mov     rcx, rsi
0x18000456b  mov     rax, [rax+38h]
0x18000456f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004574  mov     rdx, cs:?g_pModuleID@@3PEAXEA; void * g_pModuleID
0x18000457b  mov     r8, rax
0x18000457e  mov     rcx, [rax]
0x180004581  mov     rax, [rcx]
0x180004584  mov     rcx, r8
0x180004587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000458c  mov     rbx, rax
0x18000458f  xor     eax, eax
0x180004591  jmp     short loc_180004597
0x180004593  test    eax, eax
0x180004595  js      short loc_1800045A1
0x180004597  mov     [rdi], rbx
0x18000459a  jmp     short loc_1800045A1
0x18000459c  mov     eax, 8007000Eh
0x1800045a1  mov     rbx, [rsp+38h+arg_0]
0x1800045a6  mov     rbp, [rsp+38h+arg_8]
0x1800045ab  add     rsp, 20h
0x1800045af  pop     r14
0x1800045b1  pop     rdi
0x1800045b2  pop     rsi
0x1800045b3  retn
```
