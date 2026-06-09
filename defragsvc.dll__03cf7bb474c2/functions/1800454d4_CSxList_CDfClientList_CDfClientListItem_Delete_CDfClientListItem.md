# CSxList<CDfClientList,CDfClientListItem>::Delete(CDfClientListItem *)

- ea: `0x1800454d4`
- end: `0x180045562`
- name: `?Delete@?$CSxList@VCDfClientList@@VCDfClientListItem@@@@QEAAJPEAVCDfClientListItem@@@Z`
- size: `142`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001c8b0`
- `0x180045e50`

## callees

- `0x18001d82c`
- `0x1800454d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045553`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045553`

## pseudocode

```c
__int64 __fastcall CSxList<CDfClientList,CDfClientListItem>::Delete(__int64 a1, __int64 a2)
{
  unsigned int v2; // edi
  void *i; // rbx
  _QWORD *v5; // rcx
  void **v6; // rax

  if ( a2 )
  {
    for ( i = *(void **)(a1 + 8); ; i = *(void **)i )
    {
      if ( i == (void *)(a1 + 24) )
        return 1;
      if ( *((_QWORD *)i + 2) == a2 )
        break;
    }
    if ( !i )
      return 1;
    _InterlockedAdd((volatile signed __int32 *)a1, 1u);
    v5 = *(_QWORD **)i;
    if ( *(void **)(*(_QWORD *)i + 8LL) != i || (v6 = (void **)*((_QWORD *)i + 1), *v6 != i) )
      __fastfail(3u);
    *v6 = v5;
    v2 = 0;
    v5[1] = v6;
    *((_QWORD *)i + 1) = i;
    *(_QWORD *)i = i;
    CDfClientListItem::Release(*((CDfClientListItem **)i + 2));
    *((_QWORD *)i + 2) = 0;
    CoTaskMemFree(i);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v2;
}

```

## disassembly

```asm
0x1800454d4  mov     [rsp+arg_0], rbx
0x1800454d9  push    rdi
0x1800454da  sub     rsp, 20h
0x1800454de  test    rdx, rdx
0x1800454e1  jnz     short loc_1800454EA
0x1800454e3  mov     edi, 80070057h
0x1800454e8  jmp     short loc_180045507
0x1800454ea  mov     rbx, [rcx+8]
0x1800454ee  lea     rax, [rcx+18h]
0x1800454f2  jmp     short loc_1800454FD
0x1800454f4  cmp     [rbx+10h], rdx
0x1800454f8  jz      short loc_180045514
0x1800454fa  mov     rbx, [rbx]
0x1800454fd  cmp     rbx, rax
0x180045500  jnz     short loc_1800454F4
0x180045502  mov     edi, 1
0x180045507  mov     rbx, [rsp+28h+arg_0]
0x18004550c  mov     eax, edi
0x18004550e  add     rsp, 20h
0x180045512  pop     rdi
0x180045513  retn
0x180045514  test    rbx, rbx
0x180045517  jz      short loc_180045502
0x180045519  mov     edi, 1
0x18004551e  lock add [rcx], edi
0x180045521  mov     rcx, [rbx]
0x180045524  cmp     [rcx+8], rbx
0x180045528  jnz     short loc_18004555B
0x18004552a  mov     rax, [rbx+8]
0x18004552e  cmp     [rax], rbx
0x180045531  jnz     short loc_18004555B
0x180045533  mov     [rax], rcx
0x180045536  xor     edi, edi
0x180045538  mov     [rcx+8], rax
0x18004553c  mov     [rbx+8], rbx
0x180045540  mov     [rbx], rbx
0x180045543  mov     rcx, [rbx+10h]; this
0x180045547  call    ?Release@CDfClientListItem@@QEAAKXZ; CDfClientListItem::Release(void)
0x18004554c  mov     rcx, rbx; pv
0x18004554f  mov     [rbx+10h], rdi
0x180045553  call    cs:__imp_CoTaskMemFree
0x180045559  jmp     short loc_180045507
0x18004555b  mov     ecx, 3
0x180045560  int     29h; Win8: RtlFailFast(ecx)
```
