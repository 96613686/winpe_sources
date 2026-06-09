# RasStatAcquireAddress

- ea: `0x18005b774`
- end: `0x18005b990`
- name: `RasStatAcquireAddress`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800578ec`

## callees

- `0x1800588f4`
- `0x180058dc4`
- `0x18005b774`
- `0x18005b9f4`
- `0x18005c74c`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `WS2_32!__imp_htonl` at `0x18005b8cf`
- `WS2_32!__imp_htonl` at `0x18005b8db`
- `WS2_32!__imp_htonl` at `0x18005b8cf`
- `WS2_32!__imp_htonl` at `0x18005b8db`

## string_xrefs

- `0x18005b7e4`: `RasStatAcquireAddress`

## pseudocode

```c
__int64 __fastcall RasStatAcquireAddress(__int128 *a1, __int64 a2, u_long *a3, u_long *a4)
{
  __int128 v4; // xmm6
  int RoutingDomainAddressPool; // eax
  _QWORD *v9; // rbx
  __int64 v10; // rdi
  unsigned int v11; // ebx
  bool v12; // zf
  unsigned int v13; // eax
  unsigned int v14; // edi
  _QWORD *v16; // [rsp+28h] [rbp-E0h] BYREF
  __int128 v17; // [rsp+38h] [rbp-D0h] BYREF
  int v18; // [rsp+48h] [rbp-C0h] BYREF
  char v19[2044]; // [rsp+4Ch] [rbp-BCh] BYREF

  v4 = *a1;
  v16 = 0;
  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800C9740 + 1),
      L"RasStatAcquireAddress");
  v17 = v4;
  RoutingDomainAddressPool = RasGetRoutingDomainAddressPool(&v17, 1, &v16);
  if ( RoutingDomainAddressPool || (v9 = v16) == 0 )
  {
    v11 = 717;
    if ( RoutingDomainAddressPool )
      return v11;
  }
  else
  {
    v10 = v16[5];
    if ( v10 || (rasStatAllocateAddresses(v16), (v10 = v9[5]) != 0) )
    {
      v12 = (_QWORD)xmmword_1800C9740 == 0;
      v9[5] = *(_QWORD *)v10;
      *(_QWORD *)v10 = v9[4];
      v9[4] = v10;
      if ( !v12 )
      {
        LOWORD(v18) = 0;
        FormatRRASErrorString(&v18, L"Acquired 0x%x", *(unsigned int *)(v10 + 16));
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v18);
      }
      *a3 = htonl(*(_DWORD *)(v10 + 16));
      *a4 = htonl(0xFFFFFFFF);
      *(_QWORD *)(v10 + 8) = a2;
      ++v9[1];
      RasStatCheckPoolState(v9);
      v11 = 0;
    }
    else
    {
      v11 = 717;
      if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          *((_QWORD *)&xmmword_1800C9740 + 1),
          L"Out of addresses");
    }
  }
  v17 = v4;
  v13 = RasReleaseRoutingDomainAddressPool(&v17);
  v14 = v13;
  if ( v13 && (_QWORD)xmmword_1800C9740 )
  {
    LOWORD(v18) = 0;
    FormatRRASErrorString(&v18, L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d", v13);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800C9740,
      &v18);
  }
  if ( !v11 && v14 )
    return v14;
  return v11;
}

```

## disassembly

```asm
0x18005b774  mov     rax, rsp
0x18005b777  push    rbp
0x18005b778  push    rbx
0x18005b779  push    rsi
0x18005b77a  push    rdi
0x18005b77b  push    r12
0x18005b77d  push    r14
0x18005b77f  push    r15
0x18005b781  lea     rbp, [rax-798h]
0x18005b788  sub     rsp, 860h
0x18005b78f  movaps  xmmword ptr [rax-48h], xmm6
0x18005b793  mov     rax, cs:__security_cookie
0x18005b79a  xor     rax, rsp
0x18005b79d  mov     [rbp+790h+var_50], rax
0x18005b7a4  movaps  xmm6, xmmword ptr [rcx]
0x18005b7a7  mov     r15, r8
0x18005b7aa  mov     r14, rdx
0x18005b7ad  mov     [rsp+890h+var_870], 0
0x18005b7b6  xor     eax, eax
0x18005b7b8  lea     rcx, [rsp+890h+var_84C]; void *
0x18005b7bd  xor     edx, edx; Val
0x18005b7bf  mov     [rsp+890h+var_850], eax
0x18005b7c3  mov     r8d, 7FCh; Size
0x18005b7c9  mov     r12, r9
0x18005b7cc  call    memset_0
0x18005b7d1  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18005b7d8  test    rdx, rdx
0x18005b7db  jz      short loc_18005B7F7
0x18005b7dd  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005b7e4  lea     r8, aRasstatacquire; "RasStatAcquireAddress"
0x18005b7eb  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005b7f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b7f7  lea     r8, [rsp+890h+var_870]
0x18005b7fc  movdqa  [rsp+890h+var_868+8], xmm6
0x18005b802  mov     edx, 1
0x18005b807  lea     rcx, [rsp+890h+var_868+8]
0x18005b80c  call    RasGetRoutingDomainAddressPool
0x18005b811  test    eax, eax
0x18005b813  jnz     loc_18005B8F9
0x18005b819  mov     rbx, [rsp+890h+var_870]
0x18005b81e  test    rbx, rbx
0x18005b821  jz      loc_18005B8F9
0x18005b827  mov     rdi, [rbx+28h]
0x18005b82b  test    rdi, rdi
0x18005b82e  jnz     short loc_18005B875
0x18005b830  mov     rcx, rbx
0x18005b833  call    rasStatAllocateAddresses
0x18005b838  mov     rdi, [rbx+28h]
0x18005b83c  test    rdi, rdi
0x18005b83f  jnz     short loc_18005B875
0x18005b841  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18005b848  mov     ebx, 2CDh
0x18005b84d  test    rdx, rdx
0x18005b850  jz      loc_18005B902
0x18005b856  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005b85d  lea     r8, aOutOfAddresses; "Out of addresses"
0x18005b864  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005b86b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b870  jmp     loc_18005B902
0x18005b875  cmp     qword ptr cs:xmmword_1800C9740, 0
0x18005b87d  mov     rax, [rdi]
0x18005b880  mov     [rbx+28h], rax
0x18005b884  mov     rax, [rbx+20h]
0x18005b888  mov     [rdi], rax
0x18005b88b  mov     [rbx+20h], rdi
0x18005b88f  jz      short loc_18005B8CC
0x18005b891  xor     eax, eax
0x18005b893  lea     rdx, aAcquired0xX; "Acquired 0x%x"
0x18005b89a  mov     word ptr [rsp+890h+var_850], ax
0x18005b89f  lea     rcx, [rsp+890h+var_850]
0x18005b8a4  mov     r8d, [rdi+10h]
0x18005b8a8  call    FormatRRASErrorString
0x18005b8ad  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18005b8b4  lea     r8, [rsp+890h+var_850]
0x18005b8b9  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005b8c0  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005b8c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b8cc  mov     ecx, [rdi+10h]; hostlong
0x18005b8cf  call    cs:__imp_htonl
0x18005b8d5  or      ecx, 0FFFFFFFFh; hostlong
0x18005b8d8  mov     [r15], eax
0x18005b8db  call    cs:__imp_htonl
0x18005b8e1  mov     [r12], eax
0x18005b8e5  mov     rcx, rbx
0x18005b8e8  mov     [rdi+8], r14
0x18005b8ec  inc     qword ptr [rbx+8]
0x18005b8f0  call    RasStatCheckPoolState
0x18005b8f5  xor     ebx, ebx
0x18005b8f7  jmp     short loc_18005B902
0x18005b8f9  mov     ebx, 2CDh
0x18005b8fe  test    eax, eax
0x18005b900  jnz     short loc_18005B965
0x18005b902  lea     rcx, [rsp+890h+var_868+8]
0x18005b907  movdqa  [rsp+890h+var_868+8], xmm6
0x18005b90d  call    RasReleaseRoutingDomainAddressPool
0x18005b912  mov     edi, eax
0x18005b914  test    eax, eax
0x18005b916  jz      short loc_18005B95C
0x18005b918  cmp     qword ptr cs:xmmword_1800C9740, 0
0x18005b920  jz      short loc_18005B95C
0x18005b922  xor     ecx, ecx
0x18005b924  lea     rdx, aRasreleaserout; "RasReleaseRoutingDomainAddressPool fail"...
0x18005b92b  mov     word ptr [rsp+890h+var_850], cx
0x18005b930  mov     r8d, eax
0x18005b933  lea     rcx, [rsp+890h+var_850]
0x18005b938  call    FormatRRASErrorString
0x18005b93d  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18005b944  lea     r8, [rsp+890h+var_850]
0x18005b949  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005b950  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005b957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b95c  test    ebx, ebx
0x18005b95e  jnz     short loc_18005B965
0x18005b960  test    edi, edi
0x18005b962  cmovnz  ebx, edi
0x18005b965  mov     eax, ebx
0x18005b967  mov     rcx, [rbp+790h+var_50]
0x18005b96e  xor     rcx, rsp; StackCookie
0x18005b971  call    __security_check_cookie
0x18005b976  movaps  xmm6, [rsp+890h+var_48+8]
0x18005b97e  add     rsp, 860h
0x18005b985  pop     r15
0x18005b987  pop     r14
0x18005b989  pop     r12
0x18005b98b  pop     rdi
0x18005b98c  pop     rsi
0x18005b98d  pop     rbx
0x18005b98e  pop     rbp
0x18005b98f  retn
```
