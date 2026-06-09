# ATL::CExpansionVector::Add(wchar_t const *,wchar_t const *)

- ea: `0x18000ba00`
- end: `0x18000bb1b`
- name: `?Add@CExpansionVector@ATL@@QEAAJPEB_W0@Z`
- size: `283`
- prototype: `int(ATL::CExpansionVector *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x180012854`

## callees

- `0x18000173c`
- `0x18000178c`
- `0x18000ba00`
- `0x180012e60`
- `0x180027372`

## import_xrefs

- `msvcrt!realloc` at `0x18000baa6`
- `msvcrt!realloc` at `0x18000baa6`
- `ole32!CoTaskMemAlloc` at `0x18000ba4f`
- `ole32!CoTaskMemAlloc` at `0x18000ba5a`
- `ole32!CoTaskMemAlloc` at `0x18000ba4f`
- `ole32!CoTaskMemAlloc` at `0x18000ba5a`
- `ole32!CoTaskMemFree` at `0x18000bab4`
- `ole32!CoTaskMemFree` at `0x18000babe`
- `ole32!CoTaskMemFree` at `0x18000baf1`
- `ole32!CoTaskMemFree` at `0x18000bafb`
- `ole32!CoTaskMemFree` at `0x18000bab4`
- `ole32!CoTaskMemFree` at `0x18000babe`
- `ole32!CoTaskMemFree` at `0x18000baf1`
- `ole32!CoTaskMemFree` at `0x18000bafb`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::Add(ATL::CExpansionVector *this, const wchar_t *a2, const wchar_t *a3)
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

  v6 = (void **)operator new(0x10u);
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
    operator delete(v6);
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
  operator delete(v6);
  *((int *)this + 3) /= 2;
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000ba00  push    rbx
0x18000ba02  push    rbp
0x18000ba03  push    rsi
0x18000ba04  push    rdi
0x18000ba05  push    r14
0x18000ba07  push    r15
0x18000ba09  sub     rsp, 28h
0x18000ba0d  mov     rdi, rcx
0x18000ba10  mov     rbp, r8
0x18000ba13  mov     ecx, 10h; Size
0x18000ba18  mov     r14, rdx
0x18000ba1b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ba20  mov     rsi, rax
0x18000ba23  test    rax, rax
0x18000ba26  jz      loc_18000BB09
0x18000ba2c  mov     rcx, rbp; wchar_t *
0x18000ba2f  call    ?ocslen@@YAHPEB_W@Z; ocslen(wchar_t const *)
0x18000ba34  mov     rcx, r14; wchar_t *
0x18000ba37  lea     ebx, ds:2[rax*2]
0x18000ba3e  call    ?ocslen@@YAHPEB_W@Z; ocslen(wchar_t const *)
0x18000ba43  lea     eax, ds:2[rax*2]
0x18000ba4a  mov     ecx, eax; cb
0x18000ba4c  mov     r15d, eax
0x18000ba4f  call    cs:__imp_CoTaskMemAlloc
0x18000ba55  mov     ecx, ebx; cb
0x18000ba57  mov     [rsi], rax
0x18000ba5a  call    cs:__imp_CoTaskMemAlloc
0x18000ba60  mov     rcx, [rsi]; void *
0x18000ba63  mov     [rsi+8], rax
0x18000ba67  test    rcx, rcx
0x18000ba6a  jz      loc_18000BAF1
0x18000ba70  test    rax, rax
0x18000ba73  jz      short loc_18000BAF1
0x18000ba75  mov     r8d, r15d; Size
0x18000ba78  mov     rdx, r14; Src
0x18000ba7b  call    memcpy_0
0x18000ba80  mov     rcx, [rsi+8]; void *
0x18000ba84  mov     r8d, ebx; Size
0x18000ba87  mov     rdx, rbp; Src
0x18000ba8a  call    memcpy_0
0x18000ba8f  mov     eax, [rdi+0Ch]
0x18000ba92  cmp     [rdi+8], eax
0x18000ba95  jnz     short loc_18000BADF
0x18000ba97  mov     rcx, [rdi]; Block
0x18000ba9a  add     eax, eax
0x18000ba9c  movsxd  rdx, eax
0x18000ba9f  shl     rdx, 3; Size
0x18000baa3  mov     [rdi+0Ch], eax
0x18000baa6  call    cs:__imp_realloc
0x18000baac  test    rax, rax
0x18000baaf  jnz     short loc_18000BADC
0x18000bab1  mov     rcx, [rsi]; pv
0x18000bab4  call    cs:__imp_CoTaskMemFree
0x18000baba  mov     rcx, [rsi+8]; pv
0x18000babe  call    cs:__imp_CoTaskMemFree
0x18000bac4  mov     rcx, rsi; Block
0x18000bac7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bacc  mov     eax, [rdi+0Ch]
0x18000bacf  mov     ecx, 2
0x18000bad4  cdq
0x18000bad5  idiv    ecx
0x18000bad7  mov     [rdi+0Ch], eax
0x18000bada  jmp     short loc_18000BB09
0x18000badc  mov     [rdi], rax
0x18000badf  movsxd  rdx, dword ptr [rdi+8]
0x18000bae3  xor     eax, eax
0x18000bae5  mov     rcx, [rdi]
0x18000bae8  mov     [rcx+rdx*8], rsi
0x18000baec  inc     dword ptr [rdi+8]
0x18000baef  jmp     short loc_18000BB0E
0x18000baf1  call    cs:__imp_CoTaskMemFree
0x18000baf7  mov     rcx, [rsi+8]; pv
0x18000bafb  call    cs:__imp_CoTaskMemFree
0x18000bb01  mov     rcx, rsi; Block
0x18000bb04  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bb09  mov     eax, 8007000Eh
0x18000bb0e  add     rsp, 28h
0x18000bb12  pop     r15
0x18000bb14  pop     r14
0x18000bb16  pop     rdi
0x18000bb17  pop     rsi
0x18000bb18  pop     rbp
0x18000bb19  pop     rbx
0x18000bb1a  retn
```
