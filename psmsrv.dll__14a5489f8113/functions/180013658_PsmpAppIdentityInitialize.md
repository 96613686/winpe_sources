# PsmpAppIdentityInitialize

- ea: `0x180013658`
- end: `0x18001374b`
- name: `PsmpAppIdentityInitialize`
- size: `243`
- prototype: `NTSTATUS __fastcall(PSID SourceSid, int, char, _WORD *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180019670`

## callees

- `0x180013658`
- `0x18001c10c`

## import_xrefs

- `ntdll!RtlCopySid` at `0x180013725`
- `ntdll!RtlCopySid` at `0x180013725`

## pseudocode

```c
NTSTATUS __fastcall PsmpAppIdentityInitialize(PSID SourceSid, int a2, char a3, _WORD *a4, __int64 a5)
{
  _WORD *v5; // rdi
  __int64 v9; // rbx
  __int64 v10; // r10
  _WORD *v11; // rax
  __int64 v12; // rsi
  __int64 v13; // rcx
  _WORD *v14; // rax
  _WORD *v15; // rcx
  NTSTATUS result; // eax

  v5 = a4;
  v9 = 232;
  if ( !a4 )
    goto LABEL_13;
  v10 = 232;
  v11 = a4;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v10;
  }
  while ( v10 );
  v12 = (232 - v10) & -(__int64)(v10 != 0);
  if ( !v10 )
LABEL_13:
    LODWORD(v12) = 0;
  memset_0((void *)(a5 + 8), 0, 0x218u);
  *(_DWORD *)a5 = a2;
  *(_DWORD *)(a5 + 4) = 2 * v12 + 2;
  v13 = 2147483646;
  v14 = (_WORD *)(a5 + 8);
  do
  {
    if ( !v13 )
      break;
    if ( !*v5 )
      break;
    *v14++ = *v5++;
    --v13;
    --v9;
  }
  while ( v9 );
  v15 = v14 - 1;
  if ( v9 )
    v15 = v14;
  *v15 = 0;
  result = RtlCopySid(0x44u, (PSID)(a5 + 472), SourceSid);
  *(_BYTE *)(a5 + 540) = a3;
  return result;
}

```

## disassembly

```asm
0x180013658  push    rbx
0x18001365a  push    rbp
0x18001365b  push    rsi
0x18001365c  push    rdi
0x18001365d  push    r12
0x18001365f  push    r13
0x180013661  push    r14
0x180013663  push    r15
0x180013665  sub     rsp, 28h
0x180013669  mov     r14, [rsp+68h+arg_20]
0x180013671  xor     r13d, r13d
0x180013674  mov     rdi, r9
0x180013677  mov     r15d, r8d
0x18001367a  mov     ebp, edx
0x18001367c  mov     r12, rcx
0x18001367f  mov     ebx, 0E8h
0x180013684  test    r9, r9
0x180013687  jz      loc_180013743
0x18001368d  mov     r10d, ebx
0x180013690  mov     rax, r9
0x180013693  cmp     [rax], r13w
0x180013697  jz      short loc_1800136A3
0x180013699  add     rax, 2
0x18001369d  sub     r10, 1
0x1800136a1  jnz     short loc_180013693
0x1800136a3  mov     rcx, rbx
0x1800136a6  mov     rax, r10
0x1800136a9  sub     rcx, r10
0x1800136ac  neg     rax
0x1800136af  sbb     rsi, rsi
0x1800136b2  and     rsi, rcx
0x1800136b5  test    r10, r10
0x1800136b8  jz      loc_180013743
0x1800136be  lea     rcx, [r14+8]; void *
0x1800136c2  xor     edx, edx; Val
0x1800136c4  mov     r8d, 218h; Size
0x1800136ca  call    memset_0
0x1800136cf  lea     eax, ds:2[rsi*2]
0x1800136d6  mov     [r14], ebp
0x1800136d9  mov     [r14+4], eax
0x1800136dd  mov     ecx, 7FFFFFFEh
0x1800136e2  lea     rax, [r14+8]
0x1800136e6  test    rcx, rcx
0x1800136e9  jz      short loc_180013707
0x1800136eb  movzx   edx, word ptr [rdi]
0x1800136ee  test    dx, dx
0x1800136f1  jz      short loc_180013707
0x1800136f3  mov     [rax], dx
0x1800136f6  add     rdi, 2
0x1800136fa  add     rax, 2
0x1800136fe  dec     rcx
0x180013701  sub     rbx, 1
0x180013705  jnz     short loc_1800136E6
0x180013707  test    rbx, rbx
0x18001370a  lea     rcx, [rax-2]
0x18001370e  lea     rdx, [r14+1D8h]; DestinationSid
0x180013715  mov     r8, r12; SourceSid
0x180013718  cmovnz  rcx, rax
0x18001371c  mov     [rcx], r13w
0x180013720  mov     ecx, 44h ; 'D'; DestinationSidLength
0x180013725  call    cs:__imp_RtlCopySid
0x18001372b  mov     [r14+21Ch], r15b
0x180013732  add     rsp, 28h
0x180013736  pop     r15
0x180013738  pop     r14
0x18001373a  pop     r13
0x18001373c  pop     r12
0x18001373e  pop     rdi
0x18001373f  pop     rsi
0x180013740  pop     rbp
0x180013741  pop     rbx
0x180013742  retn
0x180013743  mov     rsi, r13
0x180013746  jmp     loc_1800136BE
```
