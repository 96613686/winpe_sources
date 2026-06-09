# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)

- ea: `0x180021718`
- end: `0x180021817`
- name: `?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z`
- size: `255`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800215f8`
- `0x180021cbc`

## callees

- `0x180021718`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021793`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021793`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800217e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800217e3`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rdi
  unsigned __int64 v4; // r8
  __int64 v5; // rcx
  _WORD *v6; // rax
  unsigned int v7; // ecx
  unsigned __int64 v8; // rcx
  LPVOID v9; // rax

  v2 = a2 + 1;
  if ( a2 + 1 < a2 )
    return (unsigned int)-2147024362;
  v4 = *(_QWORD *)(a1 + 16);
  v5 = -1;
  if ( v4 == -1 )
  {
    if ( *(_QWORD *)(a1 + 8) == -1 )
    {
      if ( *(_QWORD *)a1 )
      {
        do
          ++v5;
        while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v5) );
      }
      else
      {
        v5 = 0;
      }
      *(_QWORD *)(a1 + 8) = v5;
    }
    else
    {
      v5 = *(_QWORD *)(a1 + 8);
    }
    v4 = (v5 + 1) & -(__int64)(*(_QWORD *)a1 != 0);
    *(_QWORD *)(a1 + 16) = v4;
  }
  if ( !v4 )
  {
    if ( is_mul_ok(v2, 2u) )
    {
      v6 = CoTaskMemAlloc(2 * v2);
      if ( v6 )
      {
        *(_QWORD *)(a1 + 16) = v2;
        *(_QWORD *)a1 = v6;
        *v6 = 0;
        return 0;
      }
      return (unsigned int)-2147024882;
    }
    return (unsigned int)-2147024362;
  }
  v7 = 0;
  if ( v2 > v4 )
  {
    if ( is_mul_ok(v4, 2u) )
    {
      v8 = v4 + 2048;
      if ( v4 <= 0x800 )
        v8 = 2 * v4;
      if ( v2 <= v8 )
        v2 = v8;
      v9 = CoTaskMemRealloc(*(LPVOID *)a1, 2 * v2);
      if ( v9 )
      {
        *(_QWORD *)(a1 + 16) = v2;
        *(_QWORD *)a1 = v9;
        return 0;
      }
      return (unsigned int)-2147024882;
    }
    return (unsigned int)-2147024362;
  }
  return v7;
}

```

## disassembly

```asm
0x180021718  mov     [rsp+arg_0], rbx
0x18002171d  mov     [rsp+arg_10], rsi
0x180021722  push    rdi
0x180021723  sub     rsp, 20h
0x180021727  lea     rdi, [rdx+1]
0x18002172b  mov     rbx, rcx
0x18002172e  cmp     rdi, rdx
0x180021731  jb      loc_180021800
0x180021737  mov     r8, [rcx+10h]
0x18002173b  xor     esi, esi
0x18002173d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180021741  cmp     r8, rcx
0x180021744  jnz     short loc_18002177F
0x180021746  cmp     [rbx+8], rcx
0x18002174a  jnz     short loc_180021768
0x18002174c  mov     rax, [rbx]
0x18002174f  test    rax, rax
0x180021752  jz      short loc_18002175F
0x180021754  inc     rcx
0x180021757  cmp     [rax+rcx*2], si
0x18002175b  jnz     short loc_180021754
0x18002175d  jmp     short loc_180021762
0x18002175f  mov     rcx, rsi
0x180021762  mov     [rbx+8], rcx
0x180021766  jmp     short loc_18002176C
0x180021768  mov     rcx, [rbx+8]
0x18002176c  mov     rax, [rbx]
0x18002176f  inc     rcx
0x180021772  neg     rax
0x180021775  sbb     r8, r8
0x180021778  and     r8, rcx
0x18002177b  mov     [rbx+10h], r8
0x18002177f  test    r8, r8
0x180021782  jnz     short loc_1800217AA
0x180021784  lea     eax, [r8+2]
0x180021788  mul     rdi
0x18002178b  test    rdx, rdx
0x18002178e  jnz     short loc_180021800
0x180021790  mov     rcx, rax; cb
0x180021793  call    cs:__imp_CoTaskMemAlloc
0x180021799  test    rax, rax
0x18002179c  jz      short loc_1800217F9
0x18002179e  mov     [rbx+10h], rdi
0x1800217a2  mov     [rbx], rax
0x1800217a5  mov     [rax], si
0x1800217a8  jmp     short loc_1800217F5
0x1800217aa  mov     ecx, esi
0x1800217ac  cmp     rdi, r8
0x1800217af  jbe     short loc_180021805
0x1800217b1  mov     eax, 2
0x1800217b6  mul     r8
0x1800217b9  mov     r9, rax
0x1800217bc  test    rdx, rdx
0x1800217bf  jnz     short loc_180021800
0x1800217c1  sub     rax, r8
0x1800217c4  lea     rcx, [r8+800h]
0x1800217cb  cmp     rax, 800h
0x1800217d1  cmovbe  rcx, r9
0x1800217d5  cmp     rdi, rcx
0x1800217d8  cmovbe  rdi, rcx
0x1800217dc  mov     rcx, [rbx]; pv
0x1800217df  lea     rdx, [rdi+rdi]; cb
0x1800217e3  call    cs:__imp_CoTaskMemRealloc
0x1800217e9  test    rax, rax
0x1800217ec  jz      short loc_1800217F9
0x1800217ee  mov     [rbx+10h], rdi
0x1800217f2  mov     [rbx], rax
0x1800217f5  mov     ecx, esi
0x1800217f7  jmp     short loc_180021805
0x1800217f9  mov     ecx, 8007000Eh
0x1800217fe  jmp     short loc_180021805
0x180021800  mov     ecx, 80070216h
0x180021805  mov     rbx, [rsp+28h+arg_0]
0x18002180a  mov     eax, ecx
0x18002180c  mov     rsi, [rsp+28h+arg_10]
0x180021811  add     rsp, 20h
0x180021815  pop     rdi
0x180021816  retn
```
