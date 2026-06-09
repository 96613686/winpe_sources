# CRAHelperClass::GetAttributeInfo(ulong *,tagHelperAttributeInfo * *)

- ea: `0x18000d520`
- end: `0x18000d63b`
- name: `?GetAttributeInfo@CRAHelperClass@@UEAAJPEAKPEAPEAUtagHelperAttributeInfo@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(CRAHelperClass *__hidden this, unsigned int *, struct tagHelperAttributeInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000d520`
- `0x18000f248`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d60c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d61b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d60c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d61b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d590`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d590`

## pseudocode

```c
__int64 __fastcall CRAHelperClass::GetAttributeInfo(
        CRAHelperClass *this,
        unsigned int *a2,
        struct tagHelperAttributeInfo **a3)
{
  unsigned int v3; // esi
  const struct tagHelperAttributeInfo near *const *v6; // r15
  const struct tagHelperAttributeInfo near *const *v7; // rax
  unsigned int v8; // edi
  int v9; // ebx
  SIZE_T v10; // rbx
  struct tagHelperAttributeInfo *v11; // rax
  struct tagHelperAttributeInfo *v12; // rbp
  struct tagHelperAttributeInfo *i; // r13
  unsigned int j; // edi
  LPWSTR pwszName; // rcx

  v3 = 0;
  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  v6 = &CRAHelperClass::m_attrInfos;
  v7 = &CRAHelperClass::m_attrInfos;
  v8 = 0;
  if ( CRAHelperClass::m_attrInfos )
  {
    do
    {
      ++v8;
      v7 += 2;
    }
    while ( *v7 );
  }
  *a2 = 0;
  *a3 = 0;
  if ( !v8 )
    return 0;
  if ( v8 > 0x104 )
    return (unsigned int)-2147024809;
  v10 = 16LL * v8;
  v11 = (struct tagHelperAttributeInfo *)CoTaskMemAlloc(v10);
  v12 = v11;
  if ( v11 )
  {
    for ( i = v11; v10; --v10 )
    {
      LOBYTE(v11->pwszName) = 0;
      v11 = (struct tagHelperAttributeInfo *)((char *)v11 + 1);
    }
    while ( 1 )
    {
      v9 = StringCchCopyWithAlloc(&i->pwszName, 0xFFFFu, *(const unsigned __int16 **)v6);
      if ( v9 < 0 )
        break;
      ++v3;
      i->type = *((_DWORD *)v6 + 2);
      v6 += 2;
      ++i;
      if ( v3 >= v8 )
      {
        *a2 = v8;
        v9 = 0;
        *a3 = v12;
        return (unsigned int)v9;
      }
    }
    if ( v3 )
    {
      for ( j = 0; j < v3; ++j )
      {
        pwszName = v12[j].pwszName;
        if ( pwszName )
          CoTaskMemFree(pwszName);
      }
    }
    CoTaskMemFree(v12);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000d520  push    rbx
0x18000d522  push    rbp
0x18000d523  push    rsi
0x18000d524  push    rdi
0x18000d525  push    r12
0x18000d527  push    r13
0x18000d529  push    r14
0x18000d52b  push    r15
0x18000d52d  sub     rsp, 28h
0x18000d531  xor     esi, esi
0x18000d533  mov     r14, r8
0x18000d536  mov     r12, rdx
0x18000d539  test    rdx, rdx
0x18000d53c  jz      loc_18000D623
0x18000d542  test    r8, r8
0x18000d545  jz      loc_18000D623
0x18000d54b  cmp     cs:?m_attrInfos@CRAHelperClass@@0QBUtagHelperAttributeInfo@@B, rsi; tagHelperAttributeInfo const near * const CRAHelperClass::m_attrInfos
0x18000d552  lea     r15, ?m_attrInfos@CRAHelperClass@@0QBUtagHelperAttributeInfo@@B; tagHelperAttributeInfo const near * const CRAHelperClass::m_attrInfos
0x18000d559  mov     rax, r15
0x18000d55c  mov     edi, esi
0x18000d55e  jz      short loc_18000D56B
0x18000d560  inc     edi
0x18000d562  lea     rax, [rax+10h]
0x18000d566  cmp     [rax], rsi
0x18000d569  jnz     short loc_18000D560
0x18000d56b  mov     [rdx], esi
0x18000d56d  mov     [r8], rsi
0x18000d570  test    edi, edi
0x18000d572  jnz     short loc_18000D57B
0x18000d574  mov     ebx, esi
0x18000d576  jmp     loc_18000D628
0x18000d57b  cmp     edi, 104h
0x18000d581  ja      loc_18000D623
0x18000d587  mov     ebx, edi
0x18000d589  shl     rbx, 4
0x18000d58d  mov     rcx, rbx; cb
0x18000d590  call    cs:__imp_CoTaskMemAlloc
0x18000d596  mov     rbp, rax
0x18000d599  test    rax, rax
0x18000d59c  jnz     short loc_18000D5A8
0x18000d59e  mov     ebx, 8007000Eh
0x18000d5a3  jmp     loc_18000D628
0x18000d5a8  mov     r13, rbp
0x18000d5ab  test    rbx, rbx
0x18000d5ae  jz      short loc_18000D5BC
0x18000d5b0  mov     [rax], sil
0x18000d5b3  inc     rax
0x18000d5b6  sub     rbx, 1
0x18000d5ba  jnz     short loc_18000D5B0
0x18000d5bc  test    edi, edi
0x18000d5be  jz      short loc_18000D5EC
0x18000d5c0  mov     r8, [r15]; unsigned __int16 *
0x18000d5c3  mov     edx, 0FFFFh; unsigned __int64
0x18000d5c8  mov     rcx, r13; unsigned __int16 **
0x18000d5cb  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x18000d5d0  mov     ebx, eax
0x18000d5d2  test    eax, eax
0x18000d5d4  js      short loc_18000D5F7
0x18000d5d6  mov     eax, [r15+8]
0x18000d5da  inc     esi
0x18000d5dc  mov     [r13+8], eax
0x18000d5e0  add     r15, 10h
0x18000d5e4  add     r13, 10h
0x18000d5e8  cmp     esi, edi
0x18000d5ea  jb      short loc_18000D5C0
0x18000d5ec  mov     [r12], edi
0x18000d5f0  xor     ebx, ebx
0x18000d5f2  mov     [r14], rbp
0x18000d5f5  jmp     short loc_18000D628
0x18000d5f7  test    esi, esi
0x18000d5f9  jz      short loc_18000D618
0x18000d5fb  xor     edi, edi
0x18000d5fd  mov     eax, edi
0x18000d5ff  add     rax, rax
0x18000d602  mov     rcx, [rbp+rax*8+0]; pv
0x18000d607  test    rcx, rcx
0x18000d60a  jz      short loc_18000D612
0x18000d60c  call    cs:__imp_CoTaskMemFree
0x18000d612  inc     edi
0x18000d614  cmp     edi, esi
0x18000d616  jb      short loc_18000D5FD
0x18000d618  mov     rcx, rbp; pv
0x18000d61b  call    cs:__imp_CoTaskMemFree
0x18000d621  jmp     short loc_18000D628
0x18000d623  mov     ebx, 80070057h
0x18000d628  mov     eax, ebx
0x18000d62a  add     rsp, 28h
0x18000d62e  pop     r15
0x18000d630  pop     r14
0x18000d632  pop     r13
0x18000d634  pop     r12
0x18000d636  pop     rdi
0x18000d637  pop     rsi
0x18000d638  pop     rbp
0x18000d639  pop     rbx
0x18000d63a  retn
```
