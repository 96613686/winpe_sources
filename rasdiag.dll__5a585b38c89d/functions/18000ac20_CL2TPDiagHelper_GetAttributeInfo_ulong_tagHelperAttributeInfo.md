# CL2TPDiagHelper::GetAttributeInfo(ulong *,tagHelperAttributeInfo * *)

- ea: `0x18000ac20`
- end: `0x18000ad4e`
- name: `?GetAttributeInfo@CL2TPDiagHelper@@UEAAJPEAKPEAPEAUtagHelperAttributeInfo@@@Z`
- size: `302`
- prototype: `__int64 __fastcall(CL2TPDiagHelper *__hidden this, unsigned int *, struct tagHelperAttributeInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008084`
- `0x18000ac20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ac90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ac90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ad12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ad27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ad12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ad27`

## pseudocode

```c
__int64 __fastcall CL2TPDiagHelper::GetAttributeInfo(
        CL2TPDiagHelper *this,
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
  v6 = &CL2TPDiagHelper::m_attrInfos;
  v7 = &CL2TPDiagHelper::m_attrInfos;
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
0x18000ac20  push    rbx
0x18000ac22  push    rbp
0x18000ac23  push    rsi
0x18000ac24  push    rdi
0x18000ac25  push    r12
0x18000ac27  push    r13
0x18000ac29  push    r14
0x18000ac2b  push    r15
0x18000ac2d  sub     rsp, 28h
0x18000ac31  xor     esi, esi
0x18000ac33  mov     r14, r8
0x18000ac36  mov     r12, rdx
0x18000ac39  test    rdx, rdx
0x18000ac3c  jz      loc_18000AD35
0x18000ac42  test    r8, r8
0x18000ac45  jz      loc_18000AD35
0x18000ac4b  cmp     cs:?m_attrInfos@CL2TPDiagHelper@@0QBUtagHelperAttributeInfo@@B.pwszName, rsi; tagHelperAttributeInfo const near * const CL2TPDiagHelper::m_attrInfos ...
0x18000ac52  lea     r15, ?m_attrInfos@CL2TPDiagHelper@@0QBUtagHelperAttributeInfo@@B; tagHelperAttributeInfo const near * const CL2TPDiagHelper::m_attrInfos
0x18000ac59  mov     rax, r15
0x18000ac5c  mov     edi, esi
0x18000ac5e  jz      short loc_18000AC6B
0x18000ac60  inc     edi
0x18000ac62  lea     rax, [rax+10h]
0x18000ac66  cmp     [rax], rsi
0x18000ac69  jnz     short loc_18000AC60
0x18000ac6b  mov     [rdx], esi
0x18000ac6d  mov     [r8], rsi
0x18000ac70  test    edi, edi
0x18000ac72  jnz     short loc_18000AC7B
0x18000ac74  mov     ebx, esi
0x18000ac76  jmp     loc_18000AD3A
0x18000ac7b  cmp     edi, 104h
0x18000ac81  ja      loc_18000AD35
0x18000ac87  mov     ebx, edi
0x18000ac89  shl     rbx, 4
0x18000ac8d  mov     rcx, rbx; cb
0x18000ac90  call    cs:__imp_CoTaskMemAlloc
0x18000ac97  nop     dword ptr [rax+rax+00h]
0x18000ac9c  mov     rbp, rax
0x18000ac9f  test    rax, rax
0x18000aca2  jnz     short loc_18000ACAE
0x18000aca4  mov     ebx, 8007000Eh
0x18000aca9  jmp     loc_18000AD3A
0x18000acae  mov     r13, rbp
0x18000acb1  test    rbx, rbx
0x18000acb4  jz      short loc_18000ACC2
0x18000acb6  mov     [rax], sil
0x18000acb9  inc     rax
0x18000acbc  sub     rbx, 1
0x18000acc0  jnz     short loc_18000ACB6
0x18000acc2  test    edi, edi
0x18000acc4  jz      short loc_18000ACF2
0x18000acc6  mov     r8, [r15]; unsigned __int16 *
0x18000acc9  mov     edx, 0FFFFh; unsigned __int64
0x18000acce  mov     rcx, r13; unsigned __int16 **
0x18000acd1  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x18000acd6  mov     ebx, eax
0x18000acd8  test    eax, eax
0x18000acda  js      short loc_18000ACFD
0x18000acdc  mov     eax, [r15+8]
0x18000ace0  inc     esi
0x18000ace2  mov     [r13+8], eax
0x18000ace6  add     r15, 10h
0x18000acea  add     r13, 10h
0x18000acee  cmp     esi, edi
0x18000acf0  jb      short loc_18000ACC6
0x18000acf2  mov     [r12], edi
0x18000acf6  xor     ebx, ebx
0x18000acf8  mov     [r14], rbp
0x18000acfb  jmp     short loc_18000AD3A
0x18000acfd  test    esi, esi
0x18000acff  jz      short loc_18000AD24
0x18000ad01  xor     edi, edi
0x18000ad03  mov     eax, edi
0x18000ad05  add     rax, rax
0x18000ad08  mov     rcx, [rbp+rax*8+0]; pv
0x18000ad0d  test    rcx, rcx
0x18000ad10  jz      short loc_18000AD1E
0x18000ad12  call    cs:__imp_CoTaskMemFree
0x18000ad19  nop     dword ptr [rax+rax+00h]
0x18000ad1e  inc     edi
0x18000ad20  cmp     edi, esi
0x18000ad22  jb      short loc_18000AD03
0x18000ad24  mov     rcx, rbp; pv
0x18000ad27  call    cs:__imp_CoTaskMemFree
0x18000ad2e  nop     dword ptr [rax+rax+00h]
0x18000ad33  jmp     short loc_18000AD3A
0x18000ad35  mov     ebx, 80070057h
0x18000ad3a  mov     eax, ebx
0x18000ad3c  add     rsp, 28h
0x18000ad40  pop     r15
0x18000ad42  pop     r14
0x18000ad44  pop     r13
0x18000ad46  pop     r12
0x18000ad48  pop     rdi
0x18000ad49  pop     rsi
0x18000ad4a  pop     rbp
0x18000ad4b  pop     rbx
0x18000ad4c  retn
```
