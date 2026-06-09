# CWFPClientsHelperClass::GetAttributeInfo(ulong *,tagHelperAttributeInfo * *)

- ea: `0x180009c80`
- end: `0x180009d9b`
- name: `?GetAttributeInfo@CWFPClientsHelperClass@@UEAAJPEAKPEAPEAUtagHelperAttributeInfo@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(CWFPClientsHelperClass *__hidden this, unsigned int *, struct tagHelperAttributeInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008ac0`
- `0x180009c80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009cf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009cf0`

## pseudocode

```c
__int64 __fastcall CWFPClientsHelperClass::GetAttributeInfo(
        CWFPClientsHelperClass *this,
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
  v6 = &CWFPClientsHelperClass::m_attrInfos;
  v7 = &CWFPClientsHelperClass::m_attrInfos;
  v8 = 0;
  if ( CWFPClientsHelperClass::m_attrInfos )
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
0x180009c80  push    rbx
0x180009c82  push    rbp
0x180009c83  push    rsi
0x180009c84  push    rdi
0x180009c85  push    r12
0x180009c87  push    r13
0x180009c89  push    r14
0x180009c8b  push    r15
0x180009c8d  sub     rsp, 28h
0x180009c91  xor     esi, esi
0x180009c93  mov     r14, r8
0x180009c96  mov     r12, rdx
0x180009c99  test    rdx, rdx
0x180009c9c  jz      loc_180009D83
0x180009ca2  test    r8, r8
0x180009ca5  jz      loc_180009D83
0x180009cab  cmp     cs:?m_attrInfos@CWFPClientsHelperClass@@0QBUtagHelperAttributeInfo@@B, rsi; tagHelperAttributeInfo const near * const CWFPClientsHelperClass::m_attrInfos
0x180009cb2  lea     r15, ?m_attrInfos@CWFPClientsHelperClass@@0QBUtagHelperAttributeInfo@@B; tagHelperAttributeInfo const near * const CWFPClientsHelperClass::m_attrInfos
0x180009cb9  mov     rax, r15
0x180009cbc  mov     edi, esi
0x180009cbe  jz      short loc_180009CCB
0x180009cc0  inc     edi
0x180009cc2  lea     rax, [rax+10h]
0x180009cc6  cmp     [rax], rsi
0x180009cc9  jnz     short loc_180009CC0
0x180009ccb  mov     [rdx], esi
0x180009ccd  mov     [r8], rsi
0x180009cd0  test    edi, edi
0x180009cd2  jnz     short loc_180009CDB
0x180009cd4  mov     ebx, esi
0x180009cd6  jmp     loc_180009D88
0x180009cdb  cmp     edi, 104h
0x180009ce1  ja      loc_180009D83
0x180009ce7  mov     ebx, edi
0x180009ce9  shl     rbx, 4
0x180009ced  mov     rcx, rbx; cb
0x180009cf0  call    cs:__imp_CoTaskMemAlloc
0x180009cf6  mov     rbp, rax
0x180009cf9  test    rax, rax
0x180009cfc  jnz     short loc_180009D08
0x180009cfe  mov     ebx, 8007000Eh
0x180009d03  jmp     loc_180009D88
0x180009d08  mov     r13, rbp
0x180009d0b  test    rbx, rbx
0x180009d0e  jz      short loc_180009D1C
0x180009d10  mov     [rax], sil
0x180009d13  inc     rax
0x180009d16  sub     rbx, 1
0x180009d1a  jnz     short loc_180009D10
0x180009d1c  test    edi, edi
0x180009d1e  jz      short loc_180009D4C
0x180009d20  mov     r8, [r15]; unsigned __int16 *
0x180009d23  mov     edx, 0FFFFh; unsigned __int64
0x180009d28  mov     rcx, r13; unsigned __int16 **
0x180009d2b  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x180009d30  mov     ebx, eax
0x180009d32  test    eax, eax
0x180009d34  js      short loc_180009D57
0x180009d36  mov     eax, [r15+8]
0x180009d3a  inc     esi
0x180009d3c  mov     [r13+8], eax
0x180009d40  add     r15, 10h
0x180009d44  add     r13, 10h
0x180009d48  cmp     esi, edi
0x180009d4a  jb      short loc_180009D20
0x180009d4c  mov     [r12], edi
0x180009d50  xor     ebx, ebx
0x180009d52  mov     [r14], rbp
0x180009d55  jmp     short loc_180009D88
0x180009d57  test    esi, esi
0x180009d59  jz      short loc_180009D78
0x180009d5b  xor     edi, edi
0x180009d5d  mov     eax, edi
0x180009d5f  add     rax, rax
0x180009d62  mov     rcx, [rbp+rax*8+0]; pv
0x180009d67  test    rcx, rcx
0x180009d6a  jz      short loc_180009D72
0x180009d6c  call    cs:__imp_CoTaskMemFree
0x180009d72  inc     edi
0x180009d74  cmp     edi, esi
0x180009d76  jb      short loc_180009D5D
0x180009d78  mov     rcx, rbp; pv
0x180009d7b  call    cs:__imp_CoTaskMemFree
0x180009d81  jmp     short loc_180009D88
0x180009d83  mov     ebx, 80070057h
0x180009d88  mov     eax, ebx
0x180009d8a  add     rsp, 28h
0x180009d8e  pop     r15
0x180009d90  pop     r14
0x180009d92  pop     r13
0x180009d94  pop     r12
0x180009d96  pop     rdi
0x180009d97  pop     rsi
0x180009d98  pop     rbp
0x180009d99  pop     rbx
0x180009d9a  retn
```
