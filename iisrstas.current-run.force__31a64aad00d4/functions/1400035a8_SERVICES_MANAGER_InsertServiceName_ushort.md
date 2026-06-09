# SERVICES_MANAGER::InsertServiceName(ushort *)

- ea: `0x1400035a8`
- end: `0x14000366c`
- name: `?InsertServiceName@SERVICES_MANAGER@@AEAAJPEAG@Z`
- size: `196`
- prototype: `int(SERVICES_MANAGER *__hidden this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140003018`
- `0x140003dc4`

## callees

- `0x140001014`
- `0x1400035a8`
- `0x14000494c`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x14000363b`
- `msvcrt!wcscpy_s` at `0x14000363b`
- `msvcrt!_wcsicmp` at `0x1400035dc`
- `msvcrt!_wcsicmp` at `0x1400035dc`

## pseudocode

```c
__int64 __fastcall SERVICES_MANAGER::InsertServiceName(SERVICES_MANAGER *this, unsigned __int16 *a2)
{
  LIST_ARRAY *v2; // rbx
  unsigned int v3; // eax
  unsigned int v6; // edi
  __int64 v7; // rax
  rsize_t v8; // rbp
  wchar_t *v9; // rax
  wchar_t *v10; // rdi
  __int64 result; // rax

  v2 = (SERVICES_MANAGER *)((char *)this + 8);
  v3 = *((_DWORD *)this + 2);
  if ( v3 )
  {
    v6 = 0;
    while ( v6 <= v3 - 1 )
    {
      if ( !_wcsicmp(a2, *(const wchar_t **)(*((_QWORD *)this + 6) + 8LL * v6)) )
        return 0;
      v3 = *(_DWORD *)v2;
      if ( ++v6 >= *(_DWORD *)v2 )
        goto LABEL_6;
    }
    return 2147943813LL;
  }
  else
  {
LABEL_6:
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    v8 = v7 + 1;
    v9 = (wchar_t *)operator new(saturated_mul(v7 + 1, 2u));
    v10 = v9;
    if ( v9 )
    {
      wcscpy_s(v9, v8, a2);
      result = LIST_ARRAY::CheckRange(v2, *(_DWORD *)v2, 1);
      if ( (int)result >= 0 )
        *(_QWORD *)(*((_QWORD *)v2 + 5) + 8LL * (unsigned int)(*(_DWORD *)v2)++) = v10;
    }
    else
    {
      return 2147942408LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400035a8  push    rbx
0x1400035aa  push    rbp
0x1400035ab  push    rsi
0x1400035ac  push    rdi
0x1400035ad  push    r14
0x1400035af  sub     rsp, 20h
0x1400035b3  lea     rbx, [rcx+8]
0x1400035b7  xor     r14d, r14d
0x1400035ba  mov     eax, [rbx]
0x1400035bc  mov     rsi, rdx
0x1400035bf  mov     rbp, rcx
0x1400035c2  test    eax, eax
0x1400035c4  jz      short loc_1400035EE
0x1400035c6  mov     edi, r14d
0x1400035c9  dec     eax
0x1400035cb  cmp     edi, eax
0x1400035cd  ja      short loc_14000362B
0x1400035cf  mov     rdx, [rbp+30h]
0x1400035d3  mov     rcx, rsi; String1
0x1400035d6  mov     eax, edi
0x1400035d8  mov     rdx, [rdx+rax*8]; String2
0x1400035dc  call    cs:__imp__wcsicmp
0x1400035e2  test    eax, eax
0x1400035e4  jz      short loc_140003626
0x1400035e6  mov     eax, [rbx]
0x1400035e8  inc     edi
0x1400035ea  cmp     edi, eax
0x1400035ec  jb      short loc_1400035C9
0x1400035ee  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400035f2  mov     rax, rcx
0x1400035f5  inc     rax
0x1400035f8  cmp     [rsi+rax*2], r14w
0x1400035fd  jnz     short loc_1400035F5
0x1400035ff  lea     rbp, [rax+1]
0x140003603  mov     eax, 2
0x140003608  mul     rbp
0x14000360b  cmovb   rax, rcx
0x14000360f  mov     rcx, rax; Size
0x140003612  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140003617  mov     rdi, rax
0x14000361a  test    rax, rax
0x14000361d  jnz     short loc_140003632
0x14000361f  mov     eax, 80070008h
0x140003624  jmp     short loc_140003661
0x140003626  mov     eax, r14d
0x140003629  jmp     short loc_140003661
0x14000362b  mov     eax, 80070585h
0x140003630  jmp     short loc_140003661
0x140003632  mov     r8, rsi; Source
0x140003635  mov     rdx, rbp; SizeInWords
0x140003638  mov     rcx, rdi; Destination
0x14000363b  call    cs:__imp_wcscpy_s
0x140003641  mov     edx, [rbx]; unsigned int
0x140003643  mov     r8d, 1; int
0x140003649  mov     rcx, rbx; this
0x14000364c  call    ?CheckRange@LIST_ARRAY@@AEAAJKH@Z; LIST_ARRAY::CheckRange(ulong,int)
0x140003651  test    eax, eax
0x140003653  js      short loc_140003661
0x140003655  mov     edx, [rbx]
0x140003657  mov     rcx, [rbx+28h]
0x14000365b  mov     [rcx+rdx*8], rdi
0x14000365f  inc     dword ptr [rbx]
0x140003661  add     rsp, 20h
0x140003665  pop     r14
0x140003667  pop     rdi
0x140003668  pop     rsi
0x140003669  pop     rbp
0x14000366a  pop     rbx
0x14000366b  retn
```
