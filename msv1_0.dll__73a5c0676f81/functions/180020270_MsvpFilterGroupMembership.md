# MsvpFilterGroupMembership

- ea: `0x180020270`
- end: `0x180020495`
- name: `MsvpFilterGroupMembership`
- size: `549`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180022220`

## callees

- `0x180020270`
- `0x18006bd68`
- `0x18006d010`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x18002043a`
- `ntdll!RtlSubAuthoritySid` at `0x18002043a`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800202ed`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800202f9`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800202ed`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800202f9`
- `ntdll!RtlSubAuthorityCountSid` at `0x180020427`
- `ntdll!RtlSubAuthorityCountSid` at `0x180020427`
- `ntdll!RtlLengthSid` at `0x18002032f`
- `ntdll!RtlLengthSid` at `0x18002032f`
- `ntdll!RtlLengthRequiredSid` at `0x1800202e1`
- `ntdll!RtlLengthRequiredSid` at `0x1800202e1`

## pseudocode

```c
__int64 __fastcall MsvpFilterGroupMembership(__int64 a1, unsigned __int8 *a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  __int64 v5; // r14
  __int64 v6; // r15
  unsigned int v8; // ebp
  unsigned int v9; // r13d
  unsigned int v10; // r14d
  ULONG v12; // ecx
  __int64 v13; // r12
  unsigned __int8 *v14; // rbx
  ULONG v15; // edi
  PSID_IDENTIFIER_AUTHORITY v16; // rbx
  PSID_IDENTIFIER_AUTHORITY v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  unsigned int v20; // edi
  unsigned int v21; // r13d
  unsigned int v22; // ebp
  __int64 v23; // rdx
  int v24; // ecx
  __int64 v25; // rbx
  PUCHAR v26; // rax
  __int64 v27; // rcx
  int v29; // [rsp+80h] [rbp+8h]

  v5 = a4;
  *(_DWORD *)a3 = 0;
  v6 = a3;
  *(_QWORD *)(a3 + 8) = 0;
  *(_DWORD *)a4 = 0;
  v8 = 0;
  *(_QWORD *)(a4 + 8) = 0;
  v9 = 0;
  v29 = 0;
  if ( *(_DWORD *)a1 )
  {
    v10 = 0;
    do
    {
      v12 = a2[1];
      v13 = 16LL * v10;
      v14 = *(unsigned __int8 **)(v13 + *(_QWORD *)(a1 + 8));
      if ( v14[1] == v12 + 1
        && (v15 = RtlLengthRequiredSid(v12) - 2,
            v16 = RtlIdentifierAuthoritySid(v14),
            v17 = RtlIdentifierAuthoritySid(a2),
            !memcmp_0(v17, v16, v15)) )
      {
        *(_DWORD *)(*(_QWORD *)(a1 + 8) + v13 + 8) |= 0x20000000u;
        ++v8;
      }
      else
      {
        ++v9;
        v29 += RtlLengthSid(*(PSID *)(*(_QWORD *)(a1 + 8) + 16LL * v10)) + 16;
      }
      ++v10;
    }
    while ( v10 < *(_DWORD *)a1 );
    v5 = a4;
    v6 = a3;
    if ( v8 )
    {
      v18 = ((__int64 (__fastcall *)(__int64))qword_180088390)(8LL * v8);
      *(_QWORD *)(a3 + 8) = v18;
      if ( !v18 )
      {
LABEL_13:
        v20 = -1073741670;
        if ( *(_QWORD *)(a3 + 8) )
        {
          ((void (*)(void))qword_180088398)();
          *(_QWORD *)(a3 + 8) = 0;
        }
        if ( *(_QWORD *)(a4 + 8) )
        {
          ((void (*)(void))qword_180088398)();
          *(_QWORD *)(a4 + 8) = 0;
        }
        return v20;
      }
      *(_DWORD *)a3 = v8;
    }
    if ( v9 )
    {
      v19 = ((__int64 (__fastcall *)(__int64))qword_180088390)(16LL * v9);
      *(_QWORD *)(a4 + 8) = v19;
      if ( !v19 )
        goto LABEL_13;
      *(_DWORD *)a4 = v9;
    }
  }
  v20 = 0;
  v21 = 0;
  v22 = 0;
  if ( *(_DWORD *)a1 )
  {
    do
    {
      v23 = *(_QWORD *)(a1 + 8);
      v24 = *(_DWORD *)(v23 + 16LL * v22 + 8);
      if ( (v24 & 0x20000000) != 0 )
      {
        v25 = v20;
        *(_DWORD *)(*(_QWORD *)(v6 + 8) + 8LL * v20 + 4) = v24 & 0xDFFFFFFF;
        v26 = RtlSubAuthorityCountSid(*(PSID *)(*(_QWORD *)(a1 + 8) + 16LL * v22));
        ++v20;
        *(_DWORD *)(*(_QWORD *)(v6 + 8) + 8 * v25) = *RtlSubAuthoritySid(
                                                        *(PSID *)(*(_QWORD *)(a1 + 8) + 16LL * v22),
                                                        (unsigned int)*v26 - 1);
      }
      else
      {
        v27 = 2LL * v21++;
        *(_OWORD *)(*(_QWORD *)(v5 + 8) + 8 * v27) = *(_OWORD *)(v23 + 16LL * v22);
      }
      ++v22;
    }
    while ( v22 < *(_DWORD *)a1 );
    v20 = 0;
  }
  *a5 = v29;
  return v20;
}

```

## disassembly

```asm
0x180020270  mov     rax, rsp
0x180020273  mov     [rax+20h], r9
0x180020277  mov     [rax+18h], r8
0x18002027b  mov     [rax+10h], rdx
0x18002027f  push    rbx
0x180020280  push    rbp
0x180020281  push    rsi
0x180020282  push    rdi
0x180020283  push    r12
0x180020285  push    r13
0x180020287  push    r14
0x180020289  push    r15
0x18002028b  sub     rsp, 38h
0x18002028f  xor     ebx, ebx
0x180020291  mov     r14, r9
0x180020294  mov     [r8], ebx
0x180020297  mov     r15, r8
0x18002029a  mov     [r8+8], rbx
0x18002029e  mov     rsi, rcx
0x1800202a1  mov     [r9], ebx
0x1800202a4  mov     ebp, ebx
0x1800202a6  mov     [r9+8], rbx
0x1800202aa  mov     r13d, ebx
0x1800202ad  mov     [rsp+78h+arg_0], ebx
0x1800202b4  cmp     [rcx], ebx
0x1800202b6  jbe     loc_1800203EA
0x1800202bc  mov     r14d, ebx
0x1800202bf  mov     r15, rdx
0x1800202c2  mov     rax, [rsi+8]
0x1800202c6  movzx   ecx, byte ptr [r15+1]; SubAuthorityCount
0x1800202cb  mov     r12d, r14d
0x1800202ce  shl     r12, 4
0x1800202d2  mov     rbx, [r12+rax]
0x1800202d6  lea     eax, [rcx+1]
0x1800202d9  movzx   edx, byte ptr [rbx+1]
0x1800202dd  cmp     edx, eax
0x1800202df  jnz     short loc_180020322
0x1800202e1  call    cs:__imp_RtlLengthRequiredSid
0x1800202e7  mov     rcx, rbx; Sid
0x1800202ea  lea     edi, [rax-2]
0x1800202ed  call    cs:__imp_RtlIdentifierAuthoritySid
0x1800202f3  mov     rcx, r15; Sid
0x1800202f6  mov     rbx, rax
0x1800202f9  call    cs:__imp_RtlIdentifierAuthoritySid
0x1800202ff  mov     r8d, edi; Size
0x180020302  mov     rdx, rbx; Buf2
0x180020305  mov     rcx, rax; Buf1
0x180020308  call    memcmp_0
0x18002030d  xor     ebx, ebx
0x18002030f  test    eax, eax
0x180020311  jnz     short loc_180020324
0x180020313  mov     rax, [rsi+8]
0x180020317  bts     dword ptr [rax+r12+8], 1Dh
0x18002031e  inc     ebp
0x180020320  jmp     short loc_180020348
0x180020322  xor     ebx, ebx
0x180020324  mov     rcx, [rsi+8]
0x180020328  inc     r13d
0x18002032b  mov     rcx, [rcx+r12]; Sid
0x18002032f  call    cs:__imp_RtlLengthSid
0x180020335  mov     ecx, [rsp+78h+arg_0]
0x18002033c  add     ecx, 10h
0x18002033f  add     ecx, eax
0x180020341  mov     [rsp+78h+arg_0], ecx
0x180020348  inc     r14d
0x18002034b  cmp     r14d, [rsi]
0x18002034e  jb      loc_1800202C2
0x180020354  mov     r14, [rsp+78h+arg_18]
0x18002035c  mov     r15, [rsp+78h+arg_10]
0x180020364  test    ebp, ebp
0x180020366  jz      short loc_180020386
0x180020368  mov     rax, cs:qword_180088390
0x18002036f  mov     ecx, ebp
0x180020371  shl     rcx, 3
0x180020375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002037a  mov     [r15+8], rax
0x18002037e  test    rax, rax
0x180020381  jz      short loc_1800203A7
0x180020383  mov     [r15], ebp
0x180020386  test    r13d, r13d
0x180020389  jz      short loc_1800203EA
0x18002038b  mov     rax, cs:qword_180088390
0x180020392  mov     ecx, r13d
0x180020395  shl     rcx, 4
0x180020399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002039e  mov     [r14+8], rax
0x1800203a2  test    rax, rax
0x1800203a5  jnz     short loc_1800203E7
0x1800203a7  mov     rcx, [r15+8]
0x1800203ab  mov     edi, 0C000009Ah
0x1800203b0  test    rcx, rcx
0x1800203b3  jz      short loc_1800203C5
0x1800203b5  mov     rax, cs:qword_180088398
0x1800203bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203c1  mov     [r15+8], rbx
0x1800203c5  mov     rcx, [r14+8]
0x1800203c9  test    rcx, rcx
0x1800203cc  jz      loc_180020482
0x1800203d2  mov     rax, cs:qword_180088398
0x1800203d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203de  mov     [r14+8], rbx
0x1800203e2  jmp     loc_180020482
0x1800203e7  mov     [r14], r13d
0x1800203ea  mov     edi, ebx
0x1800203ec  mov     dword ptr [rsp+78h+arg_10], ebx
0x1800203f3  mov     r13d, ebx
0x1800203f6  mov     ebp, ebx
0x1800203f8  cmp     [rsi], ebx
0x1800203fa  jbe     short loc_180020471
0x1800203fc  mov     rdx, [rsi+8]
0x180020400  mov     r12d, ebp
0x180020403  add     r12, r12
0x180020406  mov     ecx, [rdx+r12*8+8]
0x18002040b  bt      ecx, 1Dh
0x18002040f  jnb     short loc_18002044D
0x180020411  mov     rax, [r15+8]
0x180020415  btr     ecx, 1Dh
0x180020419  mov     ebx, edi
0x18002041b  mov     [rax+rbx*8+4], ecx
0x18002041f  mov     rcx, [rsi+8]
0x180020423  mov     rcx, [rcx+r12*8]; Sid
0x180020427  call    cs:__imp_RtlSubAuthorityCountSid
0x18002042d  mov     rcx, [rsi+8]
0x180020431  movzx   edx, byte ptr [rax]
0x180020434  mov     rcx, [rcx+r12*8]; Sid
0x180020438  dec     edx; SubAuthority
0x18002043a  call    cs:__imp_RtlSubAuthoritySid
0x180020440  mov     rcx, [r15+8]
0x180020444  inc     edi
0x180020446  mov     eax, [rax]
0x180020448  mov     [rcx+rbx*8], eax
0x18002044b  jmp     short loc_180020464
0x18002044d  mov     rax, [r14+8]
0x180020451  movups  xmm0, xmmword ptr [rdx+r12*8]
0x180020456  mov     ecx, r13d
0x180020459  add     rcx, rcx
0x18002045c  inc     r13d
0x18002045f  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x180020464  inc     ebp
0x180020466  cmp     ebp, [rsi]
0x180020468  jb      short loc_1800203FC
0x18002046a  mov     edi, dword ptr [rsp+78h+arg_10]
0x180020471  mov     rcx, [rsp+78h+arg_20]
0x180020479  mov     eax, [rsp+78h+arg_0]
0x180020480  mov     [rcx], eax
0x180020482  mov     eax, edi
0x180020484  add     rsp, 38h
0x180020488  pop     r15
0x18002048a  pop     r14
0x18002048c  pop     r13
0x18002048e  pop     r12
0x180020490  pop     rdi
0x180020491  pop     rsi
0x180020492  pop     rbp
0x180020493  pop     rbx
0x180020494  retn
```
