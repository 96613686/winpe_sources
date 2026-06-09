# CHashValueStringList::InitKeyCopy(wchar_t const *)

- ea: `0x18000f3a0`
- end: `0x18000f425`
- name: `?InitKeyCopy@CHashValueStringList@@QEAAJPEB_W@Z`
- size: `133`
- prototype: `int(CHashValueStringList *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001fb44`

## callees

- `0x18000f3a0`
- `0x18000f42c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f3f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f3f6`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18000f3c7`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18000f3c7`

## pseudocode

```c
__int64 __fastcall CHashValueStringList::InitKeyCopy(CHashValueStringList *this, const wchar_t *a2)
{
  HRESULT v3; // esi
  wchar_t *v4; // rbx
  __int64 v5; // rdx
  void *v6; // rcx
  unsigned int v7; // ebp
  wchar_t *v9; // [rsp+50h] [rbp+18h] BYREF

  v9 = 0;
  v3 = SHStrDupW(a2, &v9);
  if ( v3 >= 0 )
  {
    v4 = v9;
    v5 = -1;
    do
      ++v5;
    while ( v9[v5] );
    v6 = (void *)*((_QWORD *)this + 5);
    v7 = v5 + 1;
    *((_QWORD *)this + 5) = v9;
    if ( v6 )
      CoTaskMemFree(v6);
    *((_QWORD *)this + 3) = v4;
    *((_DWORD *)this + 8) = v7;
    *((_DWORD *)this + 4) = PStringHash(v4, v7);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000f3a0  mov     r11, rsp
0x18000f3a3  mov     [r11+8], rbx
0x18000f3a7  mov     [r11+10h], rbp
0x18000f3ab  push    rsi
0x18000f3ac  push    rdi
0x18000f3ad  push    r14
0x18000f3af  sub     rsp, 20h
0x18000f3b3  mov     rax, rdx
0x18000f3b6  mov     rdi, rcx
0x18000f3b9  xor     r14d, r14d
0x18000f3bc  lea     rdx, [r11+18h]; ppwsz
0x18000f3c0  mov     rcx, rax; psz
0x18000f3c3  mov     [r11+18h], r14
0x18000f3c7  call    cs:__imp_SHStrDupW
0x18000f3cd  mov     esi, eax
0x18000f3cf  test    eax, eax
0x18000f3d1  js      short loc_18000F410
0x18000f3d3  mov     rbx, [rsp+38h+arg_10]
0x18000f3d8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000f3dc  inc     rdx
0x18000f3df  cmp     [rbx+rdx*2], r14w
0x18000f3e4  jnz     short loc_18000F3DC
0x18000f3e6  mov     rcx, [rdi+28h]; pv
0x18000f3ea  lea     ebp, [rdx+1]
0x18000f3ed  mov     [rdi+28h], rbx
0x18000f3f1  test    rcx, rcx
0x18000f3f4  jz      short loc_18000F3FC
0x18000f3f6  call    cs:__imp_CoTaskMemFree
0x18000f3fc  mov     edx, ebp; unsigned int
0x18000f3fe  mov     [rdi+18h], rbx
0x18000f402  mov     rcx, rbx; wchar_t *
0x18000f405  mov     [rdi+20h], ebp
0x18000f408  call    ?PStringHash@@YAKPEB_WK@Z; PStringHash(wchar_t const *,ulong)
0x18000f40d  mov     [rdi+10h], eax
0x18000f410  mov     rbx, [rsp+38h+arg_0]
0x18000f415  mov     eax, esi
0x18000f417  mov     rbp, [rsp+38h+arg_8]
0x18000f41c  add     rsp, 20h
0x18000f420  pop     r14
0x18000f422  pop     rdi
0x18000f423  pop     rsi
0x18000f424  retn
```
