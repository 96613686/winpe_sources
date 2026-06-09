# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x180011414`
- end: `0x180011536`
- name: `?Add@CExpansionVector@ATL@@QEAAJPEBG0@Z`
- size: `290`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800116b4`

## callees

- `0x180011414`
- `0x180015574`
- `0x18005582e`

## import_xrefs

- `msvcrt!realloc` at `0x1800114bb`
- `msvcrt!realloc` at `0x1800114bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800114c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800114d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800114dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011509`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011513`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001151d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800114c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800114d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800114dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011509`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011513`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001151d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001142f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011464`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001146f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001142f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011464`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001146f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CExpansionVector::Add(
        ATL::CExpansionVector *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  void **v6; // rsi
  unsigned int v7; // ebx
  unsigned int v8; // r15d
  LPVOID v9; // rax
  void *v10; // rcx
  int v11; // eax
  int v12; // eax
  void *v13; // rax
  __int64 result; // rax

  v6 = (void **)CoTaskMemAlloc(0x10u);
  if ( !v6 )
    return 2147942414LL;
  v7 = 2 * ocslen(a3) + 2;
  v8 = 2 * ocslen(a2) + 2;
  *v6 = CoTaskMemAlloc(v8);
  v9 = CoTaskMemAlloc(v7);
  v6[1] = v9;
  v10 = *v6;
  if ( !*v6 || !v9 )
  {
    CoTaskMemFree(v10);
    CoTaskMemFree(v6[1]);
    CoTaskMemFree(v6);
    return 2147942414LL;
  }
  memcpy_0(v10, a2, v8);
  memcpy_0(v6[1], a3, v7);
  v11 = *((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 2) != v11 )
  {
LABEL_8:
    result = 0;
    *(_QWORD *)(*(_QWORD *)this + 8LL * (int)(*((_DWORD *)this + 2))++) = v6;
    return result;
  }
  v12 = 2 * v11;
  *((_DWORD *)this + 3) = v12;
  v13 = realloc(*(void **)this, 8LL * v12);
  if ( v13 )
  {
    *(_QWORD *)this = v13;
    goto LABEL_8;
  }
  CoTaskMemFree(*v6);
  CoTaskMemFree(v6[1]);
  CoTaskMemFree(v6);
  *((int *)this + 3) /= 2;
  return 2147942414LL;
}

```

## disassembly

```asm
0x180011414  push    rbx
0x180011416  push    rbp
0x180011417  push    rsi
0x180011418  push    rdi
0x180011419  push    r14
0x18001141b  push    r15
0x18001141d  sub     rsp, 28h
0x180011421  mov     rbp, r8
0x180011424  mov     r14, rdx
0x180011427  mov     rdi, rcx
0x18001142a  mov     ecx, 10h; cb
0x18001142f  call    cs:__imp_CoTaskMemAlloc
0x180011435  mov     rsi, rax
0x180011438  test    rax, rax
0x18001143b  jz      loc_180011524
0x180011441  mov     rcx, rbp; unsigned __int16 *
0x180011444  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x180011449  lea     ebx, ds:2[rax*2]
0x180011450  mov     rcx, r14; unsigned __int16 *
0x180011453  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x180011458  lea     eax, ds:2[rax*2]
0x18001145f  mov     r15d, eax
0x180011462  mov     ecx, eax; cb
0x180011464  call    cs:__imp_CoTaskMemAlloc
0x18001146a  mov     [rsi], rax
0x18001146d  mov     ecx, ebx; cb
0x18001146f  call    cs:__imp_CoTaskMemAlloc
0x180011475  mov     [rsi+8], rax
0x180011479  mov     rcx, [rsi]; void *
0x18001147c  test    rcx, rcx
0x18001147f  jz      loc_180011509
0x180011485  test    rax, rax
0x180011488  jz      short loc_180011509
0x18001148a  mov     r8d, r15d; Size
0x18001148d  mov     rdx, r14; Src
0x180011490  call    memcpy_0
0x180011495  mov     r8d, ebx; Size
0x180011498  mov     rdx, rbp; Src
0x18001149b  mov     rcx, [rsi+8]; void *
0x18001149f  call    memcpy_0
0x1800114a4  mov     eax, [rdi+0Ch]
0x1800114a7  cmp     [rdi+8], eax
0x1800114aa  jnz     short loc_1800114F7
0x1800114ac  add     eax, eax
0x1800114ae  mov     [rdi+0Ch], eax
0x1800114b1  movsxd  rdx, eax
0x1800114b4  shl     rdx, 3; Size
0x1800114b8  mov     rcx, [rdi]; Block
0x1800114bb  call    cs:__imp_realloc
0x1800114c1  test    rax, rax
0x1800114c4  jnz     short loc_1800114F4
0x1800114c6  mov     rcx, [rsi]; pv
0x1800114c9  call    cs:__imp_CoTaskMemFree
0x1800114cf  mov     rcx, [rsi+8]; pv
0x1800114d3  call    cs:__imp_CoTaskMemFree
0x1800114d9  nop
0x1800114da  mov     rcx, rsi; pv
0x1800114dd  call    cs:__imp_CoTaskMemFree
0x1800114e3  nop
0x1800114e4  mov     eax, [rdi+0Ch]
0x1800114e7  cdq
0x1800114e8  mov     ecx, 2
0x1800114ed  idiv    ecx
0x1800114ef  mov     [rdi+0Ch], eax
0x1800114f2  jmp     short loc_180011524
0x1800114f4  mov     [rdi], rax
0x1800114f7  xor     eax, eax
0x1800114f9  movsxd  rdx, dword ptr [rdi+8]
0x1800114fd  mov     rcx, [rdi]
0x180011500  mov     [rcx+rdx*8], rsi
0x180011504  inc     dword ptr [rdi+8]
0x180011507  jmp     short loc_180011529
0x180011509  call    cs:__imp_CoTaskMemFree
0x18001150f  mov     rcx, [rsi+8]; pv
0x180011513  call    cs:__imp_CoTaskMemFree
0x180011519  nop
0x18001151a  mov     rcx, rsi; pv
0x18001151d  call    cs:__imp_CoTaskMemFree
0x180011523  nop
0x180011524  mov     eax, 8007000Eh
0x180011529  add     rsp, 28h
0x18001152d  pop     r15
0x18001152f  pop     r14
0x180011531  pop     rdi
0x180011532  pop     rsi
0x180011533  pop     rbp
0x180011534  pop     rbx
0x180011535  retn
```
