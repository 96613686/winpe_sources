# CPPTPDiagHelper::GetAttributeInfo(ulong *,tagHelperAttributeInfo * *)

- ea: `0x180009c90`
- end: `0x180009dbe`
- name: `?GetAttributeInfo@CPPTPDiagHelper@@UEAAJPEAKPEAPEAUtagHelperAttributeInfo@@@Z`
- size: `302`
- prototype: `__int64 __fastcall(CPPTPDiagHelper *__hidden this, unsigned int *, struct tagHelperAttributeInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008084`
- `0x180009c90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009d00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009d00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d97`

## pseudocode

```c
__int64 __fastcall CPPTPDiagHelper::GetAttributeInfo(
        CPPTPDiagHelper *this,
        unsigned int *a2,
        struct tagHelperAttributeInfo **a3)
{
  unsigned int v3; // esi
  const struct tagHelperAttributeInfo *v6; // r15
  const struct tagHelperAttributeInfo *v7; // rax
  unsigned int i; // edi
  int v9; // ebx
  SIZE_T v10; // rbx
  struct tagHelperAttributeInfo *v11; // rax
  struct tagHelperAttributeInfo *v12; // rbp
  struct tagHelperAttributeInfo *j; // r13
  unsigned int k; // edi
  LPWSTR pwszName; // rcx

  v3 = 0;
  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  v6 = &CPPTPDiagHelper::m_attrInfos;
  v7 = &CPPTPDiagHelper::m_attrInfos;
  for ( i = 0; v7->pwszName; ++v7 )
    ++i;
  *a2 = 0;
  *a3 = 0;
  if ( !i )
    return 0;
  if ( i > 0x104 )
    return (unsigned int)-2147024809;
  v10 = 16LL * i;
  v11 = (struct tagHelperAttributeInfo *)CoTaskMemAlloc(v10);
  v12 = v11;
  if ( v11 )
  {
    for ( j = v11; v10; --v10 )
    {
      LOBYTE(v11->pwszName) = 0;
      v11 = (struct tagHelperAttributeInfo *)((char *)v11 + 1);
    }
    while ( 1 )
    {
      v9 = StringCchCopyWithAlloc(&j->pwszName, 0xFFFFu, v6->pwszName);
      if ( v9 < 0 )
        break;
      ++v3;
      j->type = v6->type;
      ++v6;
      ++j;
      if ( v3 >= i )
      {
        *a2 = i;
        v9 = 0;
        *a3 = v12;
        return (unsigned int)v9;
      }
    }
    if ( v3 )
    {
      for ( k = 0; k < v3; ++k )
      {
        pwszName = v12[k].pwszName;
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
0x180009c90  push    rbx
0x180009c92  push    rbp
0x180009c93  push    rsi
0x180009c94  push    rdi
0x180009c95  push    r12
0x180009c97  push    r13
0x180009c99  push    r14
0x180009c9b  push    r15
0x180009c9d  sub     rsp, 28h
0x180009ca1  xor     esi, esi
0x180009ca3  mov     r14, r8
0x180009ca6  mov     r12, rdx
0x180009ca9  test    rdx, rdx
0x180009cac  jz      loc_180009DA5
0x180009cb2  test    r8, r8
0x180009cb5  jz      loc_180009DA5
0x180009cbb  cmp     cs:?m_attrInfos@CPPTPDiagHelper@@0QBUtagHelperAttributeInfo@@B.pwszName, rsi; tagHelperAttributeInfo const near * const CPPTPDiagHelper::m_attrInfos ...
0x180009cc2  lea     r15, ?m_attrInfos@CPPTPDiagHelper@@0QBUtagHelperAttributeInfo@@B; tagHelperAttributeInfo const near * const CPPTPDiagHelper::m_attrInfos
0x180009cc9  mov     rax, r15
0x180009ccc  mov     edi, esi
0x180009cce  jz      short loc_180009CDB
0x180009cd0  inc     edi
0x180009cd2  lea     rax, [rax+10h]
0x180009cd6  cmp     [rax], rsi
0x180009cd9  jnz     short loc_180009CD0
0x180009cdb  mov     [rdx], esi
0x180009cdd  mov     [r8], rsi
0x180009ce0  test    edi, edi
0x180009ce2  jnz     short loc_180009CEB
0x180009ce4  mov     ebx, esi
0x180009ce6  jmp     loc_180009DAA
0x180009ceb  cmp     edi, 104h
0x180009cf1  ja      loc_180009DA5
0x180009cf7  mov     ebx, edi
0x180009cf9  shl     rbx, 4
0x180009cfd  mov     rcx, rbx; cb
0x180009d00  call    cs:__imp_CoTaskMemAlloc
0x180009d07  nop     dword ptr [rax+rax+00h]
0x180009d0c  mov     rbp, rax
0x180009d0f  test    rax, rax
0x180009d12  jnz     short loc_180009D1E
0x180009d14  mov     ebx, 8007000Eh
0x180009d19  jmp     loc_180009DAA
0x180009d1e  mov     r13, rbp
0x180009d21  test    rbx, rbx
0x180009d24  jz      short loc_180009D32
0x180009d26  mov     [rax], sil
0x180009d29  inc     rax
0x180009d2c  sub     rbx, 1
0x180009d30  jnz     short loc_180009D26
0x180009d32  test    edi, edi
0x180009d34  jz      short loc_180009D62
0x180009d36  mov     r8, [r15]; unsigned __int16 *
0x180009d39  mov     edx, 0FFFFh; unsigned __int64
0x180009d3e  mov     rcx, r13; unsigned __int16 **
0x180009d41  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x180009d46  mov     ebx, eax
0x180009d48  test    eax, eax
0x180009d4a  js      short loc_180009D6D
0x180009d4c  mov     eax, [r15+8]
0x180009d50  inc     esi
0x180009d52  mov     [r13+8], eax
0x180009d56  add     r15, 10h
0x180009d5a  add     r13, 10h
0x180009d5e  cmp     esi, edi
0x180009d60  jb      short loc_180009D36
0x180009d62  mov     [r12], edi
0x180009d66  xor     ebx, ebx
0x180009d68  mov     [r14], rbp
0x180009d6b  jmp     short loc_180009DAA
0x180009d6d  test    esi, esi
0x180009d6f  jz      short loc_180009D94
0x180009d71  xor     edi, edi
0x180009d73  mov     eax, edi
0x180009d75  add     rax, rax
0x180009d78  mov     rcx, [rbp+rax*8+0]; pv
0x180009d7d  test    rcx, rcx
0x180009d80  jz      short loc_180009D8E
0x180009d82  call    cs:__imp_CoTaskMemFree
0x180009d89  nop     dword ptr [rax+rax+00h]
0x180009d8e  inc     edi
0x180009d90  cmp     edi, esi
0x180009d92  jb      short loc_180009D73
0x180009d94  mov     rcx, rbp; pv
0x180009d97  call    cs:__imp_CoTaskMemFree
0x180009d9e  nop     dword ptr [rax+rax+00h]
0x180009da3  jmp     short loc_180009DAA
0x180009da5  mov     ebx, 80070057h
0x180009daa  mov     eax, ebx
0x180009dac  add     rsp, 28h
0x180009db0  pop     r15
0x180009db2  pop     r14
0x180009db4  pop     r13
0x180009db6  pop     r12
0x180009db8  pop     rdi
0x180009db9  pop     rsi
0x180009dba  pop     rbp
0x180009dbb  pop     rbx
0x180009dbc  retn
```
