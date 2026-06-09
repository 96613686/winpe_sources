# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint,ushort)

- ea: `0x1800066dc`
- end: `0x18000678b`
- name: `?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@IG@Z`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800046d0`

## callees

- `0x1800057cc`
- `0x1800066dc`
- `0x180008bf4`
- `0x180009b24`
- `0x180009ca0`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
        __int64 a1,
        HINSTANCE a2,
        unsigned int a3)
{
  int v4; // esi
  unsigned __int16 *v5; // rdi
  unsigned __int64 v6; // rbx
  __int64 v7; // rbp
  unsigned __int16 *v9; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int16 v10; // [rsp+98h] [rbp+20h] BYREF

  v9 = 0;
  v10 = 0;
  v4 = -2147467259;
  if ( Windows::Internal::ResourceString::FindAndSize(a2, a3, a3, (const unsigned __int16 **)&v9, &v10) )
  {
    v5 = v9;
    if ( v9 )
    {
      v6 = -1;
      do
        ++v6;
      while ( v9[v6] );
      v7 = v10;
      if ( v10 < v6 )
        v6 = v10;
      v4 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(a1, v10);
      if ( v4 >= 0 )
      {
        StringCchCopyNW(*(unsigned __int16 **)a1, v7 + 1, v5, v6);
        *(_QWORD *)(a1 + 8) = v6;
      }
    }
    else
    {
      v4 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(a1);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800066dc  mov     r11, rsp
0x1800066df  mov     [r11+20h], r9w
0x1800066e4  push    rbx
0x1800066e5  push    rbp
0x1800066e6  push    rsi
0x1800066e7  push    rdi
0x1800066e8  push    r14
0x1800066ea  push    r15
0x1800066ec  sub     rsp, 48h
0x1800066f0  mov     r10, rdx
0x1800066f3  lea     rax, [r11+20h]
0x1800066f7  mov     r14, rcx
0x1800066fa  mov     [r11-58h], rax
0x1800066fe  xor     r15d, r15d
0x180006701  lea     r9, [r11-48h]; unsigned __int16 **
0x180006705  mov     rcx, r10; hModule
0x180006708  mov     [r11-48h], r15
0x18000670c  mov     edx, r8d; unsigned int
0x18000670f  mov     [r11+20h], r15w
0x180006714  mov     esi, 80004005h
0x180006719  call    ?FindAndSize@ResourceString@Internal@Windows@@SA_NPEAUHINSTANCE__@@IGPEAPEBGPEAG@Z; Windows::Internal::ResourceString::FindAndSize(HINSTANCE__ *,uint,ushort,ushort const * *,ushort *)
0x18000671e  test    al, al
0x180006720  jz      short loc_18000677C
0x180006722  mov     rdi, [rsp+78h+var_48]
0x180006727  test    rdi, rdi
0x18000672a  jz      short loc_180006771
0x18000672c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006730  inc     rbx
0x180006733  cmp     [rdi+rbx*2], r15w
0x180006738  jnz     short loc_180006730
0x18000673a  movzx   ebp, [rsp+78h+arg_18]
0x180006742  mov     rcx, r14
0x180006745  cmp     rbp, rbx
0x180006748  mov     edx, ebp
0x18000674a  cmovb   rbx, rbp
0x18000674e  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x180006753  mov     esi, eax
0x180006755  test    eax, eax
0x180006757  js      short loc_18000677C
0x180006759  mov     rcx, [r14]; unsigned __int16 *
0x18000675c  lea     rdx, [rbp+1]; unsigned __int64
0x180006760  mov     r9, rbx; unsigned __int64
0x180006763  mov     r8, rdi; unsigned __int16 *
0x180006766  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000676b  mov     [r14+8], rbx
0x18000676f  jmp     short loc_18000677C
0x180006771  mov     rcx, r14
0x180006774  mov     esi, r15d
0x180006777  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000677c  mov     eax, esi
0x18000677e  add     rsp, 48h
0x180006782  pop     r15
0x180006784  pop     r14
0x180006786  pop     rdi
0x180006787  pop     rsi
0x180006788  pop     rbp
0x180006789  pop     rbx
0x18000678a  retn
```
