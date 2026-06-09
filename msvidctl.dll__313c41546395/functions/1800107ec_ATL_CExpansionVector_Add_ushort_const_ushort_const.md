# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x1800107ec`
- end: `0x18001090c`
- name: `?Add@CExpansionVector@ATL@@QEAAJPEBG0@Z`
- size: `288`
- prototype: `int(ATL::CExpansionVector *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x1800109b4`

## callees

- `0x180004740`
- `0x180004b54`
- `0x18001007c`
- `0x1800107ec`
- `0x1800eee18`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18001088f`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18001088f`
- `ole32!CoTaskMemAlloc` at `0x180010838`
- `ole32!CoTaskMemAlloc` at `0x180010843`
- `ole32!CoTaskMemAlloc` at `0x180010838`
- `ole32!CoTaskMemAlloc` at `0x180010843`
- `ole32!CoTaskMemFree` at `0x18001089d`
- `ole32!CoTaskMemFree` at `0x1800108a7`
- `ole32!CoTaskMemFree` at `0x1800108dd`
- `ole32!CoTaskMemFree` at `0x1800108e7`
- `ole32!CoTaskMemFree` at `0x18001089d`
- `ole32!CoTaskMemFree` at `0x1800108a7`
- `ole32!CoTaskMemFree` at `0x1800108dd`
- `ole32!CoTaskMemFree` at `0x1800108e7`

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
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rax
  __int64 result; // rax

  v6 = (void **)operator new(0x10u);
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
    operator delete(v6, 0x10u);
    return 2147942414LL;
  }
  memcpy_0(v10, a2, (unsigned int)v8);
  memcpy_0(v6[1], a3, v7);
  v11 = *((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 2) != v11 )
  {
LABEL_7:
    result = 0;
    *(_QWORD *)(*(_QWORD *)this + 8LL * (int)(*((_DWORD *)this + 2))++) = v6;
    return result;
  }
  v12 = *(_QWORD *)this;
  v13 = 2 * v11;
  *((_DWORD *)this + 3) = v13;
  v14 = _o_realloc(v12, 8LL * v13);
  if ( v14 )
  {
    *(_QWORD *)this = v14;
    goto LABEL_7;
  }
  CoTaskMemFree(*v6);
  CoTaskMemFree(v6[1]);
  operator delete(v6, 0x10u);
  *((int *)this + 3) /= 2;
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800107ec  push    rbx
0x1800107ee  push    rbp
0x1800107ef  push    rsi
0x1800107f0  push    rdi
0x1800107f1  push    r12
0x1800107f3  push    r14
0x1800107f5  push    r15
0x1800107f7  sub     rsp, 20h
0x1800107fb  mov     rdi, rcx
0x1800107fe  mov     r12d, 10h
0x180010804  mov     ecx, r12d; Size
0x180010807  mov     rbp, r8
0x18001080a  mov     r14, rdx
0x18001080d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010812  mov     rcx, rbp; unsigned __int16 *
0x180010815  mov     rsi, rax
0x180010818  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x18001081d  mov     rcx, r14; unsigned __int16 *
0x180010820  lea     ebx, ds:2[rax*2]
0x180010827  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x18001082c  lea     eax, ds:2[rax*2]
0x180010833  mov     ecx, eax; cb
0x180010835  mov     r15d, eax
0x180010838  call    cs:__imp_CoTaskMemAlloc
0x18001083e  mov     ecx, ebx; cb
0x180010840  mov     [rsi], rax
0x180010843  call    cs:__imp_CoTaskMemAlloc
0x180010849  mov     rcx, [rsi]; void *
0x18001084c  mov     [rsi+8], rax
0x180010850  test    rcx, rcx
0x180010853  jz      loc_1800108DD
0x180010859  test    rax, rax
0x18001085c  jz      short loc_1800108DD
0x18001085e  mov     r8d, r15d; Size
0x180010861  mov     rdx, r14; Src
0x180010864  call    memcpy_0
0x180010869  mov     rcx, [rsi+8]; void *
0x18001086d  mov     r8d, ebx; Size
0x180010870  mov     rdx, rbp; Src
0x180010873  call    memcpy_0
0x180010878  mov     eax, [rdi+0Ch]
0x18001087b  cmp     [rdi+8], eax
0x18001087e  jnz     short loc_1800108CB
0x180010880  mov     rcx, [rdi]
0x180010883  add     eax, eax
0x180010885  movsxd  rdx, eax
0x180010888  shl     rdx, 3
0x18001088c  mov     [rdi+0Ch], eax
0x18001088f  call    cs:__imp__o_realloc
0x180010895  test    rax, rax
0x180010898  jnz     short loc_1800108C8
0x18001089a  mov     rcx, [rsi]; pv
0x18001089d  call    cs:__imp_CoTaskMemFree
0x1800108a3  mov     rcx, [rsi+8]; pv
0x1800108a7  call    cs:__imp_CoTaskMemFree
0x1800108ad  mov     edx, r12d; unsigned __int64
0x1800108b0  mov     rcx, rsi; void *
0x1800108b3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800108b8  mov     eax, [rdi+0Ch]
0x1800108bb  lea     ecx, [r12-0Eh]
0x1800108c0  cdq
0x1800108c1  idiv    ecx
0x1800108c3  mov     [rdi+0Ch], eax
0x1800108c6  jmp     short loc_1800108F8
0x1800108c8  mov     [rdi], rax
0x1800108cb  movsxd  rdx, dword ptr [rdi+8]
0x1800108cf  xor     eax, eax
0x1800108d1  mov     rcx, [rdi]
0x1800108d4  mov     [rcx+rdx*8], rsi
0x1800108d8  inc     dword ptr [rdi+8]
0x1800108db  jmp     short loc_1800108FD
0x1800108dd  call    cs:__imp_CoTaskMemFree
0x1800108e3  mov     rcx, [rsi+8]; pv
0x1800108e7  call    cs:__imp_CoTaskMemFree
0x1800108ed  mov     rdx, r12; unsigned __int64
0x1800108f0  mov     rcx, rsi; void *
0x1800108f3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800108f8  mov     eax, 8007000Eh
0x1800108fd  add     rsp, 20h
0x180010901  pop     r15
0x180010903  pop     r14
0x180010905  pop     r12
0x180010907  pop     rdi
0x180010908  pop     rsi
0x180010909  pop     rbp
0x18001090a  pop     rbx
0x18001090b  retn
```
