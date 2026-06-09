# ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(unsigned __int64)

- ea: `0x18000cad0`
- end: `0x18000cb98`
- name: `?GrowBuffer@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@AEAA_N_K@Z`
- size: `200`
- prototype: `char __fastcall(__int64, size_t)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800095a4`

## callees

- `0x180005bcc`
- `0x18000cad0`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000cb69`
- `msvcrt!memmove_s` at `0x18000cb69`
- `msvcrt!calloc` at `0x18000cb0b`
- `msvcrt!calloc` at `0x18000cb46`
- `msvcrt!calloc` at `0x18000cb0b`
- `msvcrt!calloc` at `0x18000cb46`
- `msvcrt!free` at `0x18000cb79`
- `msvcrt!free` at `0x18000cb79`

## pseudocode

```c
char __fastcall ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(
        __int64 a1,
        size_t a2)
{
  size_t v4; // rdx
  size_t v5; // rcx
  void *v6; // rax
  void *v7; // rax
  void *v8; // rsi
  errno_t v10; // eax

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 <= v4 )
    return 1;
  v5 = *(int *)(a1 + 24);
  if ( !*(_QWORD *)a1 )
  {
    if ( v5 > a2 )
      a2 = v5;
    v6 = calloc(a2, 8u);
    *(_QWORD *)a1 = v6;
    if ( v6 )
      goto LABEL_15;
    return 0;
  }
  if ( !v5 )
  {
    v5 = v4 >> 1;
    if ( a2 - v4 > v4 >> 1 )
      v5 = a2 - v4;
  }
  if ( a2 < v4 + v5 )
    a2 = v4 + v5;
  v7 = calloc(a2, 8u);
  v8 = v7;
  if ( !v7 )
    return 0;
  v10 = memmove_s(v7, 8LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 8LL * *(_QWORD *)(a1 + 8));
  ATL::AtlCrtErrorCheck(v10);
  free(*(void **)a1);
  *(_QWORD *)a1 = v8;
LABEL_15:
  *(_QWORD *)(a1 + 16) = a2;
  return 1;
}

```

## disassembly

```asm
0x18000cad0  mov     [rsp+arg_0], rbx
0x18000cad5  mov     [rsp+arg_8], rsi
0x18000cada  push    rdi
0x18000cadb  sub     rsp, 20h
0x18000cadf  mov     rbx, rdx
0x18000cae2  mov     rdi, rcx
0x18000cae5  mov     rdx, [rcx+10h]
0x18000cae9  cmp     rbx, rdx
0x18000caec  jbe     loc_18000CB86
0x18000caf2  cmp     qword ptr [rdi], 0
0x18000caf6  movsxd  rcx, dword ptr [rcx+18h]
0x18000cafa  jnz     short loc_18000CB1B
0x18000cafc  cmp     rcx, rbx
0x18000caff  mov     edx, 8; Size
0x18000cb04  cmova   rbx, rcx
0x18000cb08  mov     rcx, rbx; Count
0x18000cb0b  call    cs:__imp_calloc
0x18000cb11  mov     [rdi], rax
0x18000cb14  test    rax, rax
0x18000cb17  jz      short loc_18000CB54
0x18000cb19  jmp     short loc_18000CB82
0x18000cb1b  test    rcx, rcx
0x18000cb1e  jnz     short loc_18000CB33
0x18000cb20  mov     rcx, rdx
0x18000cb23  mov     rax, rbx
0x18000cb26  shr     rcx, 1
0x18000cb29  sub     rax, rdx
0x18000cb2c  cmp     rax, rcx
0x18000cb2f  cmova   rcx, rax
0x18000cb33  lea     rax, [rdx+rcx]
0x18000cb37  mov     edx, 8; Size
0x18000cb3c  cmp     rbx, rax
0x18000cb3f  cmovb   rbx, rax
0x18000cb43  mov     rcx, rbx; Count
0x18000cb46  call    cs:__imp_calloc
0x18000cb4c  mov     rsi, rax
0x18000cb4f  test    rax, rax
0x18000cb52  jnz     short loc_18000CB58
0x18000cb54  xor     al, al
0x18000cb56  jmp     short loc_18000CB88
0x18000cb58  mov     rdx, [rdi+8]
0x18000cb5c  mov     rcx, rsi; Destination
0x18000cb5f  mov     r8, [rdi]; Source
0x18000cb62  shl     rdx, 3; DestinationSize
0x18000cb66  mov     r9, rdx; SourceSize
0x18000cb69  call    cs:__imp_memmove_s
0x18000cb6f  mov     ecx, eax; int
0x18000cb71  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000cb76  mov     rcx, [rdi]; Block
0x18000cb79  call    cs:__imp_free
0x18000cb7f  mov     [rdi], rsi
0x18000cb82  mov     [rdi+10h], rbx
0x18000cb86  mov     al, 1
0x18000cb88  mov     rbx, [rsp+28h+arg_0]
0x18000cb8d  mov     rsi, [rsp+28h+arg_8]
0x18000cb92  add     rsp, 20h
0x18000cb96  pop     rdi
0x18000cb97  retn
```
