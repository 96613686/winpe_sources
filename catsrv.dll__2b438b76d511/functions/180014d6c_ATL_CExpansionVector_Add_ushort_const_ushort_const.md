# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x180014d6c`
- end: `0x180014e8a`
- name: `?Add@CExpansionVector@ATL@@QEAAJPEBG0@Z`
- size: `286`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800150b4`

## callees

- `0x180014d6c`
- `0x18001797c`
- `0x18005550e`

## import_xrefs

- `msvcrt!realloc` at `0x180014e13`
- `msvcrt!realloc` at `0x180014e13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014e21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014e2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014e34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014e5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014e69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014e72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014e21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014e2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014e34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014e5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014e69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014e72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014d87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014dbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014dc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014d87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014dbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014dc7`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::Add(
        ATL::CExpansionVector *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  void **v6; // rsi
  unsigned int v7; // ebx
  SIZE_T v8; // r15
  LPVOID v9; // rax
  void *v10; // rcx
  int v11; // eax
  void *v12; // rcx
  int v13; // eax
  void *v14; // rax
  __int64 result; // rax

  v6 = (void **)CoTaskMemAlloc(0x10u);
  if ( !v6 )
    return 2147942414LL;
  v7 = 2 * ocslen(a3) + 2;
  v8 = 2 * (unsigned int)ocslen(a2) + 2;
  *v6 = CoTaskMemAlloc(v8);
  v9 = CoTaskMemAlloc(v7);
  v10 = *v6;
  v6[1] = v9;
  if ( !v10 || !v9 )
  {
    CoTaskMemFree(v10);
    CoTaskMemFree(v6[1]);
    CoTaskMemFree(v6);
    return 2147942414LL;
  }
  memcpy_0(v10, a2, (unsigned int)v8);
  memcpy_0(v6[1], a3, v7);
  v11 = *((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 2) != v11 )
  {
LABEL_8:
    result = 0;
    *(_QWORD *)(*(_QWORD *)this + 8LL * (int)(*((_DWORD *)this + 2))++) = v6;
    return result;
  }
  v12 = *(void **)this;
  v13 = 2 * v11;
  *((_DWORD *)this + 3) = v13;
  v14 = realloc(v12, 8LL * v13);
  if ( v14 )
  {
    *(_QWORD *)this = v14;
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
0x180014d6c  push    rbx
0x180014d6e  push    rbp
0x180014d6f  push    rsi
0x180014d70  push    rdi
0x180014d71  push    r14
0x180014d73  push    r15
0x180014d75  sub     rsp, 28h
0x180014d79  mov     rdi, rcx
0x180014d7c  mov     rbp, r8
0x180014d7f  mov     ecx, 10h; cb
0x180014d84  mov     r14, rdx
0x180014d87  call    cs:__imp_CoTaskMemAlloc
0x180014d8d  mov     rsi, rax
0x180014d90  test    rax, rax
0x180014d93  jz      loc_180014E78
0x180014d99  mov     rcx, rbp; unsigned __int16 *
0x180014d9c  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x180014da1  mov     rcx, r14; unsigned __int16 *
0x180014da4  lea     ebx, ds:2[rax*2]
0x180014dab  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x180014db0  lea     eax, ds:2[rax*2]
0x180014db7  mov     ecx, eax; cb
0x180014db9  mov     r15d, eax
0x180014dbc  call    cs:__imp_CoTaskMemAlloc
0x180014dc2  mov     ecx, ebx; cb
0x180014dc4  mov     [rsi], rax
0x180014dc7  call    cs:__imp_CoTaskMemAlloc
0x180014dcd  mov     rcx, [rsi]; void *
0x180014dd0  mov     [rsi+8], rax
0x180014dd4  test    rcx, rcx
0x180014dd7  jz      loc_180014E5F
0x180014ddd  test    rax, rax
0x180014de0  jz      short loc_180014E5F
0x180014de2  mov     r8d, r15d; Size
0x180014de5  mov     rdx, r14; Src
0x180014de8  call    memcpy_0
0x180014ded  mov     rcx, [rsi+8]; void *
0x180014df1  mov     r8d, ebx; Size
0x180014df4  mov     rdx, rbp; Src
0x180014df7  call    memcpy_0
0x180014dfc  mov     eax, [rdi+0Ch]
0x180014dff  cmp     [rdi+8], eax
0x180014e02  jnz     short loc_180014E4D
0x180014e04  mov     rcx, [rdi]; Block
0x180014e07  add     eax, eax
0x180014e09  movsxd  rdx, eax
0x180014e0c  shl     rdx, 3; Size
0x180014e10  mov     [rdi+0Ch], eax
0x180014e13  call    cs:__imp_realloc
0x180014e19  test    rax, rax
0x180014e1c  jnz     short loc_180014E4A
0x180014e1e  mov     rcx, [rsi]; pv
0x180014e21  call    cs:__imp_CoTaskMemFree
0x180014e27  mov     rcx, [rsi+8]; pv
0x180014e2b  call    cs:__imp_CoTaskMemFree
0x180014e31  mov     rcx, rsi; pv
0x180014e34  call    cs:__imp_CoTaskMemFree
0x180014e3a  mov     eax, [rdi+0Ch]
0x180014e3d  mov     ecx, 2
0x180014e42  cdq
0x180014e43  idiv    ecx
0x180014e45  mov     [rdi+0Ch], eax
0x180014e48  jmp     short loc_180014E78
0x180014e4a  mov     [rdi], rax
0x180014e4d  movsxd  rdx, dword ptr [rdi+8]
0x180014e51  xor     eax, eax
0x180014e53  mov     rcx, [rdi]
0x180014e56  mov     [rcx+rdx*8], rsi
0x180014e5a  inc     dword ptr [rdi+8]
0x180014e5d  jmp     short loc_180014E7D
0x180014e5f  call    cs:__imp_CoTaskMemFree
0x180014e65  mov     rcx, [rsi+8]; pv
0x180014e69  call    cs:__imp_CoTaskMemFree
0x180014e6f  mov     rcx, rsi; pv
0x180014e72  call    cs:__imp_CoTaskMemFree
0x180014e78  mov     eax, 8007000Eh
0x180014e7d  add     rsp, 28h
0x180014e81  pop     r15
0x180014e83  pop     r14
0x180014e85  pop     rdi
0x180014e86  pop     rsi
0x180014e87  pop     rbp
0x180014e88  pop     rbx
0x180014e89  retn
```
