# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)

- ea: `0x180011e48`
- end: `0x180011f1e`
- name: `?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z`
- size: `214`
- prototype: `__int64 __fastcall(_QWORD *, _WORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000a91c`

## callees

- `0x180011d18`
- `0x180011e48`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011efe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011efe`

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
0x180011e48  push    rbx
0x180011e4a  push    rbp
0x180011e4b  push    rsi
0x180011e4c  push    rdi
0x180011e4d  push    r14
0x180011e4f  push    r15
0x180011e51  sub     rsp, 28h
0x180011e55  xor     r15d, r15d
0x180011e58  mov     rsi, r8
0x180011e5b  mov     r14, rdx
0x180011e5e  mov     rdi, rcx
0x180011e61  test    rdx, rdx
0x180011e64  jz      loc_180011EF3
0x180011e6a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180011e6e  inc     rbx
0x180011e71  cmp     [rdx+rbx*2], r15w
0x180011e76  jnz     short loc_180011E6E
0x180011e78  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180011e7c  jnz     short loc_180011E83
0x180011e7e  mov     rsi, rbx
0x180011e81  jmp     short loc_180011E8A
0x180011e83  cmp     r8, rbx
0x180011e86  cmovb   rbx, r8
0x180011e8a  mov     rdx, rsi
0x180011e8d  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x180011e92  mov     ebp, eax
0x180011e94  test    eax, eax
0x180011e96  js      short loc_180011F0F
0x180011e98  add     rsi, 1
0x180011e9c  jz      short loc_180011EED
0x180011e9e  mov     rdx, [rdi]
0x180011ea1  cmp     rsi, 7FFFFFFFh
0x180011ea8  ja      short loc_180011EB3
0x180011eaa  cmp     rbx, 7FFFFFFEh
0x180011eb1  jbe     short loc_180011EB9
0x180011eb3  mov     [rdx], r15w
0x180011eb7  jmp     short loc_180011EED
0x180011eb9  mov     rax, rbx
0x180011ebc  test    rax, rax
0x180011ebf  jz      short loc_180011EDE
0x180011ec1  movzx   ecx, word ptr [r14]
0x180011ec5  test    cx, cx
0x180011ec8  jz      short loc_180011EDE
0x180011eca  mov     [rdx], cx
0x180011ecd  add     r14, 2
0x180011ed1  add     rdx, 2
0x180011ed5  dec     rax
0x180011ed8  sub     rsi, 1
0x180011edc  jnz     short loc_180011EBC
0x180011ede  test    rsi, rsi
0x180011ee1  lea     rcx, [rdx-2]
0x180011ee5  cmovnz  rcx, rdx
0x180011ee9  mov     [rcx], r15w
0x180011eed  mov     [rdi+8], rbx
0x180011ef1  jmp     short loc_180011F0F
0x180011ef3  mov     rcx, [rcx]; pv
0x180011ef6  mov     ebp, r15d
0x180011ef9  test    rcx, rcx
0x180011efc  jz      short loc_180011F07
0x180011efe  call    cs:__imp_CoTaskMemFree
0x180011f04  mov     [rdi], r15
0x180011f07  mov     [rdi+8], r15
0x180011f0b  mov     [rdi+10h], r15
0x180011f0f  mov     eax, ebp
0x180011f11  add     rsp, 28h
0x180011f15  pop     r15
0x180011f17  pop     r14
0x180011f19  pop     rdi
0x180011f1a  pop     rsi
0x180011f1b  pop     rbp
0x180011f1c  pop     rbx
0x180011f1d  retn
```
