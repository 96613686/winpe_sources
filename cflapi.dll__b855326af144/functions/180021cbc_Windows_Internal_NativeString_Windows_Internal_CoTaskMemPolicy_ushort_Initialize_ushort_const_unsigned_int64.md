# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)

- ea: `0x180021cbc`
- end: `0x180021d92`
- name: `?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z`
- size: `214`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001d29c`
- `0x18001d938`
- `0x18001f96c`

## callees

- `0x180021718`
- `0x180021cbc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021d72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021d72`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        _QWORD *a1,
        _WORD *a2,
        unsigned __int64 a3)
{
  unsigned __int64 v3; // rsi
  _WORD *v4; // r14
  unsigned __int64 v6; // rbx
  int v7; // ebp
  unsigned __int64 v8; // rsi
  _WORD *v9; // rdx
  unsigned __int64 v10; // rax
  _WORD *v11; // rcx
  _WORD *v12; // rcx

  v3 = a3;
  v4 = a2;
  if ( a2 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    if ( a3 == -1 )
    {
      v3 = v6;
    }
    else if ( a3 < v6 )
    {
      v6 = a3;
    }
    v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
           (__int64)a1,
           v3);
    if ( v7 >= 0 )
    {
      v8 = v3 + 1;
      if ( v8 )
      {
        v9 = (_WORD *)*a1;
        if ( v8 <= 0x7FFFFFFF && v6 <= 0x7FFFFFFE )
        {
          v10 = v6;
          do
          {
            if ( !v10 )
              break;
            if ( !*v4 )
              break;
            *v9++ = *v4++;
            --v10;
            --v8;
          }
          while ( v8 );
          v11 = v9 - 1;
          if ( v8 )
            v11 = v9;
          *v11 = 0;
        }
        else
        {
          *v9 = 0;
        }
      }
      a1[1] = v6;
    }
  }
  else
  {
    v12 = (_WORD *)*a1;
    v7 = 0;
    if ( v12 )
    {
      CoTaskMemFree(v12);
      *a1 = 0;
    }
    a1[1] = 0;
    a1[2] = 0;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180021cbc  push    rbx
0x180021cbe  push    rbp
0x180021cbf  push    rsi
0x180021cc0  push    rdi
0x180021cc1  push    r14
0x180021cc3  push    r15
0x180021cc5  sub     rsp, 28h
0x180021cc9  xor     r15d, r15d
0x180021ccc  mov     rsi, r8
0x180021ccf  mov     r14, rdx
0x180021cd2  mov     rdi, rcx
0x180021cd5  test    rdx, rdx
0x180021cd8  jz      loc_180021D67
0x180021cde  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180021ce2  inc     rbx
0x180021ce5  cmp     [rdx+rbx*2], r15w
0x180021cea  jnz     short loc_180021CE2
0x180021cec  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180021cf0  jnz     short loc_180021CF7
0x180021cf2  mov     rsi, rbx
0x180021cf5  jmp     short loc_180021CFE
0x180021cf7  cmp     r8, rbx
0x180021cfa  cmovb   rbx, r8
0x180021cfe  mov     rdx, rsi
0x180021d01  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x180021d06  mov     ebp, eax
0x180021d08  test    eax, eax
0x180021d0a  js      short loc_180021D83
0x180021d0c  add     rsi, 1
0x180021d10  jz      short loc_180021D61
0x180021d12  mov     rdx, [rdi]
0x180021d15  cmp     rsi, 7FFFFFFFh
0x180021d1c  ja      short loc_180021D27
0x180021d1e  cmp     rbx, 7FFFFFFEh
0x180021d25  jbe     short loc_180021D2D
0x180021d27  mov     [rdx], r15w
0x180021d2b  jmp     short loc_180021D61
0x180021d2d  mov     rax, rbx
0x180021d30  test    rax, rax
0x180021d33  jz      short loc_180021D52
0x180021d35  movzx   ecx, word ptr [r14]
0x180021d39  test    cx, cx
0x180021d3c  jz      short loc_180021D52
0x180021d3e  mov     [rdx], cx
0x180021d41  add     r14, 2
0x180021d45  add     rdx, 2
0x180021d49  dec     rax
0x180021d4c  sub     rsi, 1
0x180021d50  jnz     short loc_180021D30
0x180021d52  test    rsi, rsi
0x180021d55  lea     rcx, [rdx-2]
0x180021d59  cmovnz  rcx, rdx
0x180021d5d  mov     [rcx], r15w
0x180021d61  mov     [rdi+8], rbx
0x180021d65  jmp     short loc_180021D83
0x180021d67  mov     rcx, [rcx]; pv
0x180021d6a  mov     ebp, r15d
0x180021d6d  test    rcx, rcx
0x180021d70  jz      short loc_180021D7B
0x180021d72  call    cs:__imp_CoTaskMemFree
0x180021d78  mov     [rdi], r15
0x180021d7b  mov     [rdi+8], r15
0x180021d7f  mov     [rdi+10h], r15
0x180021d83  mov     eax, ebp
0x180021d85  add     rsp, 28h
0x180021d89  pop     r15
0x180021d8b  pop     r14
0x180021d8d  pop     rdi
0x180021d8e  pop     rsi
0x180021d8f  pop     rbp
0x180021d90  pop     rbx
0x180021d91  retn
```
