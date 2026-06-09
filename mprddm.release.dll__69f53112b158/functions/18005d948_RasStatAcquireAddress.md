# RasStatAcquireAddress

- ea: `0x18005d948`
- end: `0x18005db6c`
- name: `RasStatAcquireAddress`
- size: `548`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800597d4`

## callees

- `0x18005a844`
- `0x18005ad18`
- `0x18005d948`
- `0x18005dbd4`
- `0x18005e97c`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `WS2_32!__imp_htonl` at `0x18005daa4`
- `WS2_32!__imp_htonl` at `0x18005dab6`
- `WS2_32!__imp_htonl` at `0x18005daa4`
- `WS2_32!__imp_htonl` at `0x18005dab6`

## string_xrefs

- `0x18005d9c0`: `RasStatAcquireAddress`

## pseudocode

```c
__int64 __fastcall RasStatAcquireAddress(__int128 *a1, __int64 a2, u_long *a3, u_long *a4)
{
  __int128 v4; // xmm6
  unsigned int v8; // ebx
  _QWORD *v9; // rdi
  __int64 v10; // rsi
  bool v11; // zf
  unsigned int v12; // eax
  unsigned int v13; // edi
  _QWORD *v15; // [rsp+28h] [rbp-E0h] BYREF
  _QWORD v16[3]; // [rsp+30h] [rbp-D8h] BYREF
  int v17; // [rsp+48h] [rbp-C0h] BYREF
  char v18[2044]; // [rsp+4Ch] [rbp-BCh] BYREF

  v4 = *a1;
  v15 = 0;
  v17 = 0;
  v8 = 717;
  memset_0(v18, 0, sizeof(v18));
  if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800D0740 + 1),
      L"RasStatAcquireAddress");
  *(_OWORD *)&v16[1] = v4;
  if ( !(unsigned int)RasGetRoutingDomainAddressPool(&v16[1], 1, &v15) )
  {
    v9 = v15;
    if ( v15 )
    {
      v10 = v15[5];
      if ( v10 || (rasStatAllocateAddresses(v15), (v10 = v9[5]) != 0) )
      {
        v11 = (_QWORD)xmmword_1800D0740 == 0;
        v9[5] = *(_QWORD *)v10;
        *(_QWORD *)v10 = v9[4];
        v9[4] = v10;
        if ( !v11 )
        {
          LOWORD(v17) = 0;
          FormatRRASErrorString(&v17, L"Acquired 0x%x", *(unsigned int *)(v10 + 16));
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800D0740,
            &v17);
        }
        *a3 = htonl(*(_DWORD *)(v10 + 16));
        *a4 = htonl(0xFFFFFFFF);
        *(_QWORD *)(v10 + 8) = a2;
        ++v9[1];
        RasStatCheckPoolState(v9);
        v8 = 0;
      }
      else if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
      {
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          *((_QWORD *)&xmmword_1800D0740 + 1),
          L"Out of addresses");
      }
    }
    *(_OWORD *)&v16[1] = v4;
    v12 = RasReleaseRoutingDomainAddressPool(&v16[1]);
    v13 = v12;
    if ( v12 && (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v17) = 0;
      FormatRRASErrorString(&v17, L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d", v12);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v17);
    }
    if ( !v8 && v13 )
      return v13;
  }
  return v8;
}

```

## disassembly

```asm
0x18005d948  mov     rax, rsp
0x18005d94b  mov     [rax+10h], rbx
0x18005d94f  push    rbp
0x18005d950  push    rsi
0x18005d951  push    rdi
0x18005d952  push    r12
0x18005d954  push    r13
0x18005d956  push    r14
0x18005d958  push    r15
0x18005d95a  lea     rbp, [rax-798h]
0x18005d961  sub     rsp, 860h
0x18005d968  movaps  xmmword ptr [rax-48h], xmm6
0x18005d96c  mov     rax, cs:__security_cookie
0x18005d973  xor     rax, rsp
0x18005d976  mov     [rbp+790h+var_50], rax
0x18005d97d  movaps  xmm6, xmmword ptr [rcx]
0x18005d980  mov     r15, r8
0x18005d983  mov     r14, rdx
0x18005d986  lea     rcx, [rsp+890h+var_84C]; void *
0x18005d98b  xor     r13d, r13d
0x18005d98e  xor     edx, edx; Val
0x18005d990  mov     r8d, 7FCh; Size
0x18005d996  mov     [rsp+890h+var_870], r13
0x18005d99b  mov     [rsp+890h+var_850], r13d
0x18005d9a0  mov     r12, r9
0x18005d9a3  mov     ebx, 2CDh
0x18005d9a8  call    memset_0
0x18005d9ad  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18005d9b4  test    rdx, rdx
0x18005d9b7  jz      short loc_18005D9D3
0x18005d9b9  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005d9c0  lea     r8, aRasstatacquire; "RasStatAcquireAddress"
0x18005d9c7  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005d9ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d9d3  lea     r8, [rsp+890h+var_870]
0x18005d9d8  movdqa  xmmword ptr [rsp+890h+var_868+8], xmm6
0x18005d9de  mov     edx, 1
0x18005d9e3  lea     rcx, [rsp+890h+var_868+8]
0x18005d9e8  call    RasGetRoutingDomainAddressPool
0x18005d9ed  test    eax, eax
0x18005d9ef  jnz     loc_18005DB3A
0x18005d9f5  mov     rdi, [rsp+890h+var_870]
0x18005d9fa  test    rdi, rdi
0x18005d9fd  jz      loc_18005DAD9
0x18005da03  mov     rsi, [rdi+28h]
0x18005da07  test    rsi, rsi
0x18005da0a  jnz     short loc_18005DA4C
0x18005da0c  mov     rcx, rdi
0x18005da0f  call    rasStatAllocateAddresses
0x18005da14  mov     rsi, [rdi+28h]
0x18005da18  test    rsi, rsi
0x18005da1b  jnz     short loc_18005DA4C
0x18005da1d  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18005da24  test    rdx, rdx
0x18005da27  jz      loc_18005DAD9
0x18005da2d  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005da34  lea     r8, aOutOfAddresses; "Out of addresses"
0x18005da3b  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005da42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005da47  jmp     loc_18005DAD9
0x18005da4c  cmp     qword ptr cs:xmmword_1800D0740, r13
0x18005da53  mov     rax, [rsi]
0x18005da56  mov     [rdi+28h], rax
0x18005da5a  mov     rax, [rdi+20h]
0x18005da5e  mov     [rsi], rax
0x18005da61  mov     [rdi+20h], rsi
0x18005da65  jz      short loc_18005DAA1
0x18005da67  mov     word ptr [rsp+890h+var_850], r13w
0x18005da6d  lea     rdx, aAcquired0xX; "Acquired 0x%x"
0x18005da74  mov     r8d, [rsi+10h]
0x18005da78  lea     rcx, [rsp+890h+var_850]
0x18005da7d  call    FormatRRASErrorString
0x18005da82  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005da89  lea     r8, [rsp+890h+var_850]
0x18005da8e  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005da95  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005da9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005daa1  mov     ecx, [rsi+10h]; hostlong
0x18005daa4  call    cs:__imp_htonl
0x18005daab  nop     dword ptr [rax+rax+00h]
0x18005dab0  or      ecx, 0FFFFFFFFh; hostlong
0x18005dab3  mov     [r15], eax
0x18005dab6  call    cs:__imp_htonl
0x18005dabd  nop     dword ptr [rax+rax+00h]
0x18005dac2  mov     [r12], eax
0x18005dac6  mov     rcx, rdi
0x18005dac9  mov     [rsi+8], r14
0x18005dacd  inc     qword ptr [rdi+8]
0x18005dad1  call    RasStatCheckPoolState
0x18005dad6  mov     ebx, r13d
0x18005dad9  lea     rcx, [rsp+890h+var_868+8]
0x18005dade  movdqa  xmmword ptr [rsp+890h+var_868+8], xmm6
0x18005dae4  call    RasReleaseRoutingDomainAddressPool
0x18005dae9  mov     edi, eax
0x18005daeb  test    eax, eax
0x18005daed  jz      short loc_18005DB31
0x18005daef  cmp     qword ptr cs:xmmword_1800D0740, r13
0x18005daf6  jz      short loc_18005DB31
0x18005daf8  mov     r8d, eax
0x18005dafb  mov     word ptr [rsp+890h+var_850], r13w
0x18005db01  lea     rdx, aRasreleaserout; "RasReleaseRoutingDomainAddressPool fail"...
0x18005db08  lea     rcx, [rsp+890h+var_850]
0x18005db0d  call    FormatRRASErrorString
0x18005db12  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005db19  lea     r8, [rsp+890h+var_850]
0x18005db1e  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005db25  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005db2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005db31  test    ebx, ebx
0x18005db33  jnz     short loc_18005DB3A
0x18005db35  test    edi, edi
0x18005db37  cmovnz  ebx, edi
0x18005db3a  mov     eax, ebx
0x18005db3c  mov     rcx, [rbp+790h+var_50]
0x18005db43  xor     rcx, rsp; StackCookie
0x18005db46  call    __security_check_cookie
0x18005db4b  lea     r11, [rsp+890h+var_30]
0x18005db53  mov     rbx, [r11+48h]
0x18005db57  movaps  xmm6, xmmword ptr [r11-10h]
0x18005db5c  mov     rsp, r11
0x18005db5f  pop     r15
0x18005db61  pop     r14
0x18005db63  pop     r13
0x18005db65  pop     r12
0x18005db67  pop     rdi
0x18005db68  pop     rsi
0x18005db69  pop     rbp
0x18005db6a  retn
```
