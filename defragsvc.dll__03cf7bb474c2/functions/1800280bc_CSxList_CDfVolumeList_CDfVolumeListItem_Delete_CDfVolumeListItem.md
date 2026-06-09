# CSxList<CDfVolumeList,CDfVolumeListItem>::Delete(CDfVolumeListItem *)

- ea: `0x1800280bc`
- end: `0x18002814a`
- name: `?Delete@?$CSxList@VCDfVolumeList@@VCDfVolumeListItem@@@@QEAAJPEAVCDfVolumeListItem@@@Z`
- size: `142`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001727c`
- `0x18004275c`

## callees

- `0x180017e94`
- `0x1800280bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028129`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028129`

## pseudocode

```c
__int64 __fastcall CSxList<CDfVolumeList,CDfVolumeListItem>::Delete(__int64 a1, __int64 a2)
{
  void *i; // rbx
  unsigned int v3; // edi
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
    v3 = 0;
    v5[1] = v6;
    *((_QWORD *)i + 1) = i;
    *(_QWORD *)i = i;
    CDfVolumeListItem::Release(*((CDfVolumeListItem **)i + 2));
    *((_QWORD *)i + 2) = 0;
    CoTaskMemFree(i);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x1800280bc  mov     [rsp+arg_0], rbx
0x1800280c1  push    rdi
0x1800280c2  sub     rsp, 20h
0x1800280c6  test    rdx, rdx
0x1800280c9  jz      short loc_180028131
0x1800280cb  mov     rbx, [rcx+8]
0x1800280cf  lea     rax, [rcx+18h]
0x1800280d3  cmp     rbx, rax
0x1800280d6  jnz     short loc_180028138
0x1800280d8  mov     edi, 1
0x1800280dd  mov     rbx, [rsp+28h+arg_0]
0x1800280e2  mov     eax, edi
0x1800280e4  add     rsp, 20h
0x1800280e8  pop     rdi
0x1800280e9  retn
0x1800280ea  test    rbx, rbx
0x1800280ed  jz      short loc_1800280D8
0x1800280ef  mov     edi, 1
0x1800280f4  lock add [rcx], edi
0x1800280f7  mov     rcx, [rbx]
0x1800280fa  cmp     [rcx+8], rbx
0x1800280fe  jnz     short loc_180028143
0x180028100  mov     rax, [rbx+8]
0x180028104  cmp     [rax], rbx
0x180028107  jnz     short loc_180028143
0x180028109  mov     [rax], rcx
0x18002810c  xor     edi, edi
0x18002810e  mov     [rcx+8], rax
0x180028112  mov     [rbx+8], rbx
0x180028116  mov     [rbx], rbx
0x180028119  mov     rcx, [rbx+10h]; this
0x18002811d  call    ?Release@CDfVolumeListItem@@QEAAKXZ; CDfVolumeListItem::Release(void)
0x180028122  mov     rcx, rbx; pv
0x180028125  mov     [rbx+10h], rdi
0x180028129  call    cs:__imp_CoTaskMemFree
0x18002812f  jmp     short loc_1800280DD
0x180028131  mov     edi, 80070057h
0x180028136  jmp     short loc_1800280DD
0x180028138  cmp     [rbx+10h], rdx
0x18002813c  jz      short loc_1800280EA
0x18002813e  mov     rbx, [rbx]
0x180028141  jmp     short loc_1800280D3
0x180028143  mov     ecx, 3
0x180028148  int     29h; Win8: RtlFailFast(ecx)
```
