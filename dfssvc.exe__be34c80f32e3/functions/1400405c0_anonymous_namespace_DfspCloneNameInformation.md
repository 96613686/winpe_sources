# _anonymous_namespace_::DfspCloneNameInformation

- ea: `0x1400405c0`
- end: `0x140040795`
- name: `_anonymous_namespace_::DfspCloneNameInformation`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14003f82c`

## callees

- `0x1400011d0`
- `0x14001e548`
- `0x1400405c0`
- `0x14005ce22`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x140040659`
- `ntdll!RtlInitUnicodeStringEx` at `0x140040659`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1400406b4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1400406b4`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::DfspCloneNameInformation(__int64 a1, __int64 a2)
{
  unsigned int v2; // ebx
  __int64 v5; // rax
  __int64 v6; // rbp
  unsigned __int64 v7; // rbp
  unsigned __int16 *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  unsigned __int64 v11; // rbp
  unsigned __int16 *v12; // rax
  void *v13; // rcx
  DWORD SecurityDescriptorLength; // ebp
  void *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  unsigned __int64 v18; // rbp
  unsigned __int16 *v19; // rax

  v2 = 0;
  *(_OWORD *)(a1 + 120) = *(_OWORD *)(a2 + 120);
  *(_OWORD *)(a1 + 136) = *(_OWORD *)(a2 + 136);
  v5 = *(_QWORD *)(a2 + 104);
  if ( v5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(v5 + 2 * v6) );
    v7 = v6 + 1;
    v8 = (unsigned __int16 *)operator new(saturated_mul(v7, 2u));
    *(_QWORD *)(a1 + 104) = v8;
    if ( !v8 )
      return 8;
    StringCchCopyW(v8, v7, *(const unsigned __int16 **)(a2 + 104));
  }
  RtlInitUnicodeStringEx((PUNICODE_STRING)(a1 + 80), *(PCWSTR *)(a1 + 104));
  v9 = *(_QWORD *)(a2 + 112);
  if ( v9 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(v9 + 2 * v10) );
    v11 = v10 + 1;
    v12 = (unsigned __int16 *)operator new(saturated_mul(v10 + 1, 2u));
    *(_QWORD *)(a1 + 112) = v12;
    if ( !v12 )
      return 8;
    StringCchCopyW(v12, v11, *(const unsigned __int16 **)(a2 + 112));
  }
  v13 = *(void **)(a2 + 192);
  if ( v13 )
  {
    SecurityDescriptorLength = GetSecurityDescriptorLength(v13);
    v15 = operator new(SecurityDescriptorLength);
    *(_QWORD *)(a1 + 192) = v15;
    if ( !v15 )
      return 8;
    memcpy_0(v15, *(const void **)(a2 + 192), SecurityDescriptorLength);
  }
  v16 = *(_QWORD *)(a2 + 176);
  if ( !v16 )
  {
LABEL_20:
    *(_DWORD *)(a1 + 60) = *(_DWORD *)(a2 + 60);
    *(_DWORD *)(a1 + 64) = *(_DWORD *)(a2 + 64);
    *(_QWORD *)(a1 + 72) = *(_QWORD *)(a2 + 72);
    *(_DWORD *)(a1 + 184) = *(_DWORD *)(a2 + 184);
    *(_DWORD *)(a1 + 172) = *(_DWORD *)(a2 + 172);
    *(_DWORD *)(a1 + 168) = *(_DWORD *)(a2 + 168);
    return v2;
  }
  v17 = -1;
  do
    ++v17;
  while ( *(_WORD *)(v16 + 2 * v17) );
  v18 = v17 + 1;
  v19 = (unsigned __int16 *)operator new(saturated_mul(v17 + 1, 2u));
  *(_QWORD *)(a1 + 176) = v19;
  if ( v19 )
  {
    StringCchCopyW(v19, v18, *(const unsigned __int16 **)(a2 + 176));
    goto LABEL_20;
  }
  return 8;
}

```

## disassembly

```asm
0x1400405c0  mov     rax, rsp
0x1400405c3  mov     [rax+8], rbx
0x1400405c7  mov     [rax+10h], rbp
0x1400405cb  mov     [rax+18h], rsi
0x1400405cf  mov     [rax+20h], rdi
0x1400405d3  push    r12
0x1400405d5  push    r14
0x1400405d7  push    r15
0x1400405d9  sub     rsp, 20h
0x1400405dd  movups  xmm0, xmmword ptr [rdx+78h]
0x1400405e1  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400405e5  xor     ebx, ebx
0x1400405e7  mov     rdi, rdx
0x1400405ea  mov     rsi, rcx
0x1400405ed  movdqu  xmmword ptr [rcx+78h], xmm0
0x1400405f2  movups  xmm1, xmmword ptr [rdx+88h]
0x1400405f9  lea     r12d, [r15+3]
0x1400405fd  movdqu  xmmword ptr [rcx+88h], xmm1
0x140040605  mov     rax, [rdx+68h]
0x140040609  test    rax, rax
0x14004060c  jz      short loc_140040651
0x14004060e  mov     rbp, r15
0x140040611  inc     rbp
0x140040614  cmp     [rax+rbp*2], bx
0x140040618  jnz     short loc_140040611
0x14004061a  inc     rbp
0x14004061d  mov     rax, r12
0x140040620  mul     rbp
0x140040623  cmovo   rax, r15
0x140040627  mov     rcx, rax; Size
0x14004062a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004062f  mov     [rsi+68h], rax
0x140040633  test    rax, rax
0x140040636  jnz     short loc_140040642
0x140040638  mov     ebx, 8
0x14004063d  jmp     loc_140040773
0x140040642  mov     r8, [rdi+68h]; unsigned __int16 *
0x140040646  mov     rdx, rbp; unsigned __int64
0x140040649  mov     rcx, rax; unsigned __int16 *
0x14004064c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140040651  mov     rdx, [rsi+68h]; SourceString
0x140040655  lea     rcx, [rsi+50h]; DestinationString
0x140040659  call    cs:__imp_RtlInitUnicodeStringEx
0x140040660  nop     dword ptr [rax+rax+00h]
0x140040665  mov     rcx, [rdi+70h]
0x140040669  test    rcx, rcx
0x14004066c  jz      short loc_1400406A8
0x14004066e  mov     rax, r15
0x140040671  inc     rax
0x140040674  cmp     [rcx+rax*2], bx
0x140040678  jnz     short loc_140040671
0x14004067a  lea     rbp, [rax+1]
0x14004067e  mov     rax, r12
0x140040681  mul     rbp
0x140040684  cmovo   rax, r15
0x140040688  mov     rcx, rax; Size
0x14004068b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140040690  mov     [rsi+70h], rax
0x140040694  test    rax, rax
0x140040697  jz      short loc_140040638
0x140040699  mov     r8, [rdi+70h]; unsigned __int16 *
0x14004069d  mov     rdx, rbp; unsigned __int64
0x1400406a0  mov     rcx, rax; unsigned __int16 *
0x1400406a3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400406a8  mov     rcx, [rdi+0C0h]; pSecurityDescriptor
0x1400406af  test    rcx, rcx
0x1400406b2  jz      short loc_1400406EB
0x1400406b4  call    cs:__imp_GetSecurityDescriptorLength
0x1400406bb  nop     dword ptr [rax+rax+00h]
0x1400406c0  mov     ecx, eax; Size
0x1400406c2  mov     ebp, eax
0x1400406c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400406c9  mov     [rsi+0C0h], rax
0x1400406d0  test    rax, rax
0x1400406d3  jz      loc_140040638
0x1400406d9  mov     rdx, [rdi+0C0h]; Src
0x1400406e0  mov     r8d, ebp; Size
0x1400406e3  mov     rcx, rax; void *
0x1400406e6  call    memcpy_0
0x1400406eb  mov     rdx, [rdi+0B0h]
0x1400406f2  test    rdx, rdx
0x1400406f5  jz      short loc_14004073B
0x1400406f7  mov     rcx, r15
0x1400406fa  inc     rcx
0x1400406fd  cmp     [rdx+rcx*2], bx
0x140040701  jnz     short loc_1400406FA
0x140040703  lea     rbp, [rcx+1]
0x140040707  mov     rax, r12
0x14004070a  mul     rbp
0x14004070d  cmovo   rax, r15
0x140040711  mov     rcx, rax; Size
0x140040714  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140040719  mov     [rsi+0B0h], rax
0x140040720  test    rax, rax
0x140040723  jz      loc_140040638
0x140040729  mov     r8, [rdi+0B0h]; unsigned __int16 *
0x140040730  mov     rdx, rbp; unsigned __int64
0x140040733  mov     rcx, rax; unsigned __int16 *
0x140040736  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14004073b  mov     ecx, [rdi+3Ch]
0x14004073e  mov     [rsi+3Ch], ecx
0x140040741  mov     ecx, [rdi+40h]
0x140040744  mov     [rsi+40h], ecx
0x140040747  mov     rcx, [rdi+48h]
0x14004074b  mov     [rsi+48h], rcx
0x14004074f  mov     ecx, [rdi+0B8h]
0x140040755  mov     [rsi+0B8h], ecx
0x14004075b  mov     ecx, [rdi+0ACh]
0x140040761  mov     [rsi+0ACh], ecx
0x140040767  mov     ecx, [rdi+0A8h]
0x14004076d  mov     [rsi+0A8h], ecx
0x140040773  mov     rbp, [rsp+38h+arg_8]
0x140040778  mov     eax, ebx
0x14004077a  mov     rbx, [rsp+38h+arg_0]
0x14004077f  mov     rsi, [rsp+38h+arg_10]
0x140040784  mov     rdi, [rsp+38h+arg_18]
0x140040789  add     rsp, 20h
0x14004078d  pop     r15
0x14004078f  pop     r14
0x140040791  pop     r12
0x140040793  retn
```
