# CPropertyDescription::_FormatPrefix(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)

- ea: `0x18001a0c0`
- end: `0x18001a1f7`
- name: `?_FormatPrefix@CPropertyDescription@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000cee0`

## callees

- `0x18001a074`
- `0x18001a0c0`
- `0x18001c070`
- `0x18001c0f0`
- `0x18006ed20`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001a140`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001a140`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a154`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a1bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a154`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a1bb`

## pseudocode

```c
__int64 __fastcall CPropertyDescription::_FormatPrefix(__int64 *a1, __int64 a2)
{
  __int64 v2; // rax
  int v4; // esi
  __int64 v6; // rax
  unsigned __int16 *v8; // rbx
  LPVOID v9; // r8
  unsigned __int16 *v10; // r9
  LPVOID pv; // [rsp+20h] [rbp-A8h] BYREF
  int v12; // [rsp+28h] [rbp-A0h] BYREF
  WCHAR Buffer[64]; // [rsp+30h] [rbp-98h] BYREF

  v2 = *a1;
  v4 = 0;
  v12 = 0;
  (*(void (__fastcall **)(__int64 *, int *))(v2 + 72))(a1, &v12);
  if ( (v12 & 0x200) == 0 )
  {
    v6 = *a1;
    pv = 0;
    v4 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v6 + 48))(a1, &pv);
    if ( v4 >= 0 )
    {
      if ( LoadStringW(g_hModMUIResources, 0x7Au, Buffer, 64) )
      {
        if ( !*(_QWORD *)a2 )
        {
          v4 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                 a2,
                 0);
          if ( v4 < 0 )
            goto LABEL_5;
          StringCchCopyNW(*(unsigned __int16 **)a2, 1u, &Src, 0);
          *(_QWORD *)(a2 + 8) = 0;
        }
        v8 = *(unsigned __int16 **)a2;
        v9 = pv;
        v10 = *(unsigned __int16 **)a2;
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 16) = 0;
        *(_QWORD *)(a2 + 8) = 0;
        v4 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ConcatFormat(
               a2,
               Buffer,
               v9,
               v10);
        CoTaskMemFree(v8);
      }
      else
      {
        v4 = -2147467259;
      }
LABEL_5:
      CoTaskMemFree(pv);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001a0c0  mov     [rsp+arg_10], rbx
0x18001a0c5  mov     [rsp+arg_18], rsi
0x18001a0ca  push    rdi
0x18001a0cb  sub     rsp, 0C0h
0x18001a0d2  mov     rax, cs:__security_cookie
0x18001a0d9  xor     rax, rsp
0x18001a0dc  mov     [rsp+0C8h+var_18], rax
0x18001a0e4  mov     rax, [rcx]
0x18001a0e7  mov     rdi, rdx
0x18001a0ea  xor     esi, esi
0x18001a0ec  lea     rdx, [rsp+0C8h+var_A0]
0x18001a0f1  mov     rbx, rcx
0x18001a0f4  mov     [rsp+0C8h+var_A0], esi
0x18001a0f8  mov     rax, [rax+48h]
0x18001a0fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a101  test    [rsp+0C8h+var_A0], 200h
0x18001a109  jnz     short loc_18001A15A
0x18001a10b  mov     rax, [rbx]
0x18001a10e  lea     rdx, [rsp+0C8h+pv]
0x18001a113  mov     rcx, rbx
0x18001a116  mov     [rsp+0C8h+pv], rsi
0x18001a11b  mov     rax, [rax+30h]
0x18001a11f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a124  mov     esi, eax
0x18001a126  test    eax, eax
0x18001a128  js      short loc_18001A15A
0x18001a12a  mov     rcx, cs:?g_hModMUIResources@@3PEAUHINSTANCE__@@EA; hInstance
0x18001a131  lea     r8, [rsp+0C8h+Buffer]; lpBuffer
0x18001a136  mov     r9d, 40h ; '@'; cchBufferMax
0x18001a13c  lea     edx, [r9+3Ah]; uID
0x18001a140  call    cs:__imp_LoadStringW
0x18001a146  test    eax, eax
0x18001a148  jnz     short loc_18001A181
0x18001a14a  mov     esi, 80004005h
0x18001a14f  mov     rcx, [rsp+0C8h+pv]; pv
0x18001a154  call    cs:__imp_CoTaskMemFree
0x18001a15a  mov     eax, esi
0x18001a15c  mov     rcx, [rsp+0C8h+var_18]
0x18001a164  xor     rcx, rsp; StackCookie
0x18001a167  call    __security_check_cookie
0x18001a16c  lea     r11, [rsp+0C8h+var_8]
0x18001a174  mov     rbx, [r11+20h]
0x18001a178  mov     rsi, [r11+28h]
0x18001a17c  mov     rsp, r11
0x18001a17f  pop     rdi
0x18001a180  retn
0x18001a181  cmp     qword ptr [rdi], 0
0x18001a185  jz      short loc_18001A1C3
0x18001a187  mov     rbx, [rdi]
0x18001a18a  lea     rdx, [rsp+0C8h+Buffer]
0x18001a18f  mov     r8, [rsp+0C8h+pv]
0x18001a194  mov     r9, rbx
0x18001a197  mov     rcx, rdi
0x18001a19a  mov     qword ptr [rdi], 0
0x18001a1a1  mov     qword ptr [rdi+10h], 0
0x18001a1a9  mov     qword ptr [rdi+8], 0
0x18001a1b1  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x18001a1b6  mov     rcx, rbx; pv
0x18001a1b9  mov     esi, eax
0x18001a1bb  call    cs:__imp_CoTaskMemFree
0x18001a1c1  jmp     short loc_18001A14F
0x18001a1c3  xor     edx, edx
0x18001a1c5  mov     rcx, rdi
0x18001a1c8  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x18001a1cd  mov     esi, eax
0x18001a1cf  test    eax, eax
0x18001a1d1  js      loc_18001A14F
0x18001a1d7  mov     rcx, [rdi]; unsigned __int16 *
0x18001a1da  lea     r8, Src; unsigned __int16 *
0x18001a1e1  xor     r9d, r9d; unsigned __int64
0x18001a1e4  lea     edx, [r9+1]; unsigned __int64
0x18001a1e8  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001a1ed  mov     qword ptr [rdi+8], 0
0x18001a1f5  jmp     short loc_18001A187
```
