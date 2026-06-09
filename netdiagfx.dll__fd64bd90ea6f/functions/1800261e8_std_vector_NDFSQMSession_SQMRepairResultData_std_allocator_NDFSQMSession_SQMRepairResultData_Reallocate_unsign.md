# std::vector<NDFSQMSession::SQMRepairResultData,std::allocator<NDFSQMSession::SQMRepairResultData>>::_Reallocate(unsigned __int64)

- ea: `0x1800261e8`
- end: `0x180026286`
- name: `?_Reallocate@?$vector@USQMRepairResultData@NDFSQMSession@@V?$allocator@USQMRepairResultData@NDFSQMSession@@@std@@@std@@IEAAX_K@Z`
- size: `158`
- prototype: `char *__fastcall(__int64 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x18002628c`

## callees

- `0x1800017f4`
- `0x1800018d8`
- `0x180023b14`
- `0x180026008`
- `0x1800261e8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180026260`
- `msvcrt!??3@YAXPEAX@Z` at `0x180026260`

## pseudocode

```c
char *__fastcall std::vector<NDFSQMSession::SQMRepairResultData>::_Reallocate(__int64 *a1, unsigned __int64 a2)
{
  char *v3; // rsi
  unsigned __int64 v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rdi
  char *result; // rax

  v3 = 0;
  if ( a2 )
  {
    if ( a2 > 0x1FFFFFFFFFFFFFFLL || (v4 = a2 << 7, (v3 = (char *)operator new(a2 << 7)) == 0) )
      std::_Xbad_alloc();
  }
  else
  {
    v4 = 0;
  }
  std::_Uninit_move<NDFSQMSession::SQMRepairResultData *,NDFSQMSession::SQMRepairResultData *,std::allocator<NDFSQMSession::SQMRepairResultData>,NDFSQMSession::SQMRepairResultData>(
    *a1,
    a1[1],
    (__int64)v3);
  v6 = a1[1] - *a1;
  if ( *a1 )
  {
    std::vector<NDFSQMSession::SQMRepairResultData>::_Destroy(v5, *a1, (NDFSQMSession::SQMRepairResultData *)a1[1]);
    operator delete((void *)*a1);
  }
  result = &v3[v4];
  a1[2] = (__int64)&v3[v4];
  a1[1] = (__int64)&v3[v6 & 0xFFFFFFFFFFFFFF80uLL];
  *a1 = (__int64)v3;
  return result;
}

```

## disassembly

```asm
0x1800261e8  push    rbx
0x1800261ea  push    rsi
0x1800261eb  push    rdi
0x1800261ec  push    r14
0x1800261ee  sub     rsp, 38h
0x1800261f2  mov     rbx, rdx
0x1800261f5  mov     r14, rcx
0x1800261f8  xor     esi, esi
0x1800261fa  mov     [rsp+58h+arg_8], rsi
0x1800261ff  test    rdx, rdx
0x180026202  jz      short loc_180026232
0x180026204  mov     rax, 1FFFFFFFFFFFFFFh
0x18002620e  cmp     rdx, rax
0x180026211  ja      short loc_18002622C
0x180026213  shl     rbx, 7
0x180026217  mov     rcx, rbx; Size
0x18002621a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002621f  mov     rsi, rax
0x180026222  mov     [rsp+58h+arg_8], rax
0x180026227  test    rax, rax
0x18002622a  jnz     short loc_180026236
0x18002622c  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180026232  shl     rbx, 7
0x180026236  mov     r8, rsi
0x180026239  mov     rdx, [r14+8]
0x18002623d  mov     rcx, [r14]
0x180026240  call    ??$_Uninit_move@PEAUSQMRepairResultData@NDFSQMSession@@PEAU12@V?$allocator@USQMRepairResultData@NDFSQMSession@@@std@@U12@@std@@YAPEAUSQMRepairResultData@NDFSQMSession@@PEAU12@00AEAU?$_Wrap_alloc@V?$allocator@USQMRepairResultData@NDFSQMSession@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<NDFSQMSession::SQMRepairResultData *,NDFSQMSession::SQMRepairResultData *,std::allocator<NDFSQMSession::SQMRepairResultData>,NDFSQMSession::SQMRepairResultData>(NDFSQMSession::SQMRepairResultData *,NDFSQMSession::SQMRepairResultData *,NDFSQMSession::SQMRepairResultData *,std::_Wrap_alloc<std::allocator<NDFSQMSession::SQMRepairResultData>> &,NDFSQMSession::SQMRepairResultData *,std::_Nonscalar_ptr_iterator_tag)
0x180026245  nop
0x180026246  mov     rdx, [r14]
0x180026249  mov     r8, [r14+8]
0x18002624d  mov     rdi, r8
0x180026250  sub     rdi, rdx
0x180026253  test    rdx, rdx
0x180026256  jz      short loc_180026266
0x180026258  call    ?_Destroy@?$vector@USQMRepairResultData@NDFSQMSession@@V?$allocator@USQMRepairResultData@NDFSQMSession@@@std@@@std@@IEAAXPEAUSQMRepairResultData@NDFSQMSession@@0@Z; std::vector<NDFSQMSession::SQMRepairResultData>::_Destroy(NDFSQMSession::SQMRepairResultData *,NDFSQMSession::SQMRepairResultData *)
0x18002625d  mov     rcx, [r14]
0x180026260  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180026266  lea     rax, [rbx+rsi]
0x18002626a  mov     [r14+10h], rax
0x18002626e  and     rdi, 0FFFFFFFFFFFFFF80h
0x180026272  add     rdi, rsi
0x180026275  mov     [r14+8], rdi
0x180026279  mov     [r14], rsi
0x18002627c  add     rsp, 38h
0x180026280  pop     r14
0x180026282  pop     rdi
0x180026283  pop     rsi
0x180026284  pop     rbx
0x180026285  retn
```
