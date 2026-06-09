# CVPNDiagHelper::GetAttributeInfo(ulong *,tagHelperAttributeInfo * *)

- ea: `0x1800084a0`
- end: `0x1800085ce`
- name: `?GetAttributeInfo@CVPNDiagHelper@@UEAAJPEAKPEAPEAUtagHelperAttributeInfo@@@Z`
- size: `302`
- prototype: `__int64 __fastcall(CVPNDiagHelper *__hidden this, unsigned int *, struct tagHelperAttributeInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008084`
- `0x1800084a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008510`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008510`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008592`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800085a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008592`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800085a7`

## pseudocode

```c
__int64 __fastcall CVPNDiagHelper::GetAttributeInfo(
        CVPNDiagHelper *this,
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
  v6 = &CVPNDiagHelper::m_attrInfos;
  v7 = &CVPNDiagHelper::m_attrInfos;
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
0x1800084a0  push    rbx
0x1800084a2  push    rbp
0x1800084a3  push    rsi
0x1800084a4  push    rdi
0x1800084a5  push    r12
0x1800084a7  push    r13
0x1800084a9  push    r14
0x1800084ab  push    r15
0x1800084ad  sub     rsp, 28h
0x1800084b1  xor     esi, esi
0x1800084b3  mov     r14, r8
0x1800084b6  mov     r12, rdx
0x1800084b9  test    rdx, rdx
0x1800084bc  jz      loc_1800085B5
0x1800084c2  test    r8, r8
0x1800084c5  jz      loc_1800085B5
0x1800084cb  cmp     cs:?m_attrInfos@CVPNDiagHelper@@0QBUtagHelperAttributeInfo@@B.pwszName, rsi; tagHelperAttributeInfo const near * const CVPNDiagHelper::m_attrInfos ...
0x1800084d2  lea     r15, ?m_attrInfos@CVPNDiagHelper@@0QBUtagHelperAttributeInfo@@B; tagHelperAttributeInfo const near * const CVPNDiagHelper::m_attrInfos
0x1800084d9  mov     rax, r15
0x1800084dc  mov     edi, esi
0x1800084de  jz      short loc_1800084EB
0x1800084e0  inc     edi
0x1800084e2  lea     rax, [rax+10h]
0x1800084e6  cmp     [rax], rsi
0x1800084e9  jnz     short loc_1800084E0
0x1800084eb  mov     [rdx], esi
0x1800084ed  mov     [r8], rsi
0x1800084f0  test    edi, edi
0x1800084f2  jnz     short loc_1800084FB
0x1800084f4  mov     ebx, esi
0x1800084f6  jmp     loc_1800085BA
0x1800084fb  cmp     edi, 104h
0x180008501  ja      loc_1800085B5
0x180008507  mov     ebx, edi
0x180008509  shl     rbx, 4
0x18000850d  mov     rcx, rbx; cb
0x180008510  call    cs:__imp_CoTaskMemAlloc
0x180008517  nop     dword ptr [rax+rax+00h]
0x18000851c  mov     rbp, rax
0x18000851f  test    rax, rax
0x180008522  jnz     short loc_18000852E
0x180008524  mov     ebx, 8007000Eh
0x180008529  jmp     loc_1800085BA
0x18000852e  mov     r13, rbp
0x180008531  test    rbx, rbx
0x180008534  jz      short loc_180008542
0x180008536  mov     [rax], sil
0x180008539  inc     rax
0x18000853c  sub     rbx, 1
0x180008540  jnz     short loc_180008536
0x180008542  test    edi, edi
0x180008544  jz      short loc_180008572
0x180008546  mov     r8, [r15]; unsigned __int16 *
0x180008549  mov     edx, 0FFFFh; unsigned __int64
0x18000854e  mov     rcx, r13; unsigned __int16 **
0x180008551  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x180008556  mov     ebx, eax
0x180008558  test    eax, eax
0x18000855a  js      short loc_18000857D
0x18000855c  mov     eax, [r15+8]
0x180008560  inc     esi
0x180008562  mov     [r13+8], eax
0x180008566  add     r15, 10h
0x18000856a  add     r13, 10h
0x18000856e  cmp     esi, edi
0x180008570  jb      short loc_180008546
0x180008572  mov     [r12], edi
0x180008576  xor     ebx, ebx
0x180008578  mov     [r14], rbp
0x18000857b  jmp     short loc_1800085BA
0x18000857d  test    esi, esi
0x18000857f  jz      short loc_1800085A4
0x180008581  xor     edi, edi
0x180008583  mov     eax, edi
0x180008585  add     rax, rax
0x180008588  mov     rcx, [rbp+rax*8+0]; pv
0x18000858d  test    rcx, rcx
0x180008590  jz      short loc_18000859E
0x180008592  call    cs:__imp_CoTaskMemFree
0x180008599  nop     dword ptr [rax+rax+00h]
0x18000859e  inc     edi
0x1800085a0  cmp     edi, esi
0x1800085a2  jb      short loc_180008583
0x1800085a4  mov     rcx, rbp; pv
0x1800085a7  call    cs:__imp_CoTaskMemFree
0x1800085ae  nop     dword ptr [rax+rax+00h]
0x1800085b3  jmp     short loc_1800085BA
0x1800085b5  mov     ebx, 80070057h
0x1800085ba  mov     eax, ebx
0x1800085bc  add     rsp, 28h
0x1800085c0  pop     r15
0x1800085c2  pop     r14
0x1800085c4  pop     r13
0x1800085c6  pop     r12
0x1800085c8  pop     rdi
0x1800085c9  pop     rsi
0x1800085ca  pop     rbp
0x1800085cb  pop     rbx
0x1800085cc  retn
```
