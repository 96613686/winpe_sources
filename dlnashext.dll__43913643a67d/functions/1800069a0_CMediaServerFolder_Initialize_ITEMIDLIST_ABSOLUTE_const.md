# CMediaServerFolder::Initialize(_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x1800069a0`
- end: `0x1800069f8`
- name: `?Initialize@CMediaServerFolder@@UEAAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `88`
- prototype: `int(CMediaServerFolder *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800069a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800069bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800069bc`
- `api-ms-win-shell-namespace-l1-1-0!ILClone` at `0x1800069ca`
- `api-ms-win-shell-namespace-l1-1-0!ILClone` at `0x1800069ca`

## pseudocode

```c
__int64 __fastcall CMediaServerFolder::Initialize(CMediaServerFolder *this, const ITEMIDLIST *a2)
{
  void *v4; // rcx
  LPITEMIDLIST v5; // rax
  unsigned int v6; // edx

  v4 = (void *)*((_QWORD *)this + 13);
  *((_QWORD *)this + 13) = 0;
  CoTaskMemFree(v4);
  if ( !a2 )
    return 2147942487LL;
  v5 = ILClone(a2);
  *((_QWORD *)this + 13) = v5;
  v6 = -2147024882;
  if ( v5 )
    return 0;
  return v6;
}

```

## disassembly

```asm
0x1800069a0  mov     [rsp+arg_0], rbx
0x1800069a5  push    rdi
0x1800069a6  sub     rsp, 20h
0x1800069aa  mov     rbx, rcx
0x1800069ad  mov     rdi, rdx
0x1800069b0  mov     rcx, [rcx+68h]; pv
0x1800069b4  mov     qword ptr [rbx+68h], 0
0x1800069bc  call    cs:__imp_CoTaskMemFree
0x1800069c2  test    rdi, rdi
0x1800069c5  jz      short loc_1800069F1
0x1800069c7  mov     rcx, rdi; pidl
0x1800069ca  call    cs:__imp_ILClone
0x1800069d0  mov     rcx, rax
0x1800069d3  mov     [rbx+68h], rax
0x1800069d7  xor     eax, eax
0x1800069d9  mov     edx, 8007000Eh
0x1800069de  test    rcx, rcx
0x1800069e1  cmovnz  edx, eax
0x1800069e4  mov     eax, edx
0x1800069e6  mov     rbx, [rsp+28h+arg_0]
0x1800069eb  add     rsp, 20h
0x1800069ef  pop     rdi
0x1800069f0  retn
0x1800069f1  mov     eax, 80070057h
0x1800069f6  jmp     short loc_1800069E6
```
