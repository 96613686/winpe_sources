# StateSeparation::SetValue(ushort const *,ushort const *,ulong,uchar const *,ulong)

- ea: `0x14003287c`
- end: `0x140032a3b`
- name: `?SetValue@StateSeparation@@QEAAKPEBG0KPEBEK@Z`
- size: `447`
- prototype: `unsigned int(StateSeparation *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140032218`
- `0x14003377c`

## callees

- `0x140002f60`
- `0x140013df8`
- `0x140013e64`
- `0x140014700`
- `0x1400167fc`
- `0x14002690c`
- `0x14003287c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400329ec`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400329ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StateSeparation::SetValue(
        StateSeparation *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        const unsigned __int8 *lpData,
        DWORD cbData)
{
  unsigned __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  LPCWSTR *v12; // r9
  unsigned __int64 v13; // r8
  _QWORD *v14; // rax
  __int128 v15; // xmm7
  __int128 v16; // xmm6
  const WCHAR *v17; // rdx
  unsigned int v18; // ebx
  LPCWSTR lpSubKey[2]; // [rsp+48h] [rbp-B0h] BYREF
  __int128 v21; // [rsp+58h] [rbp-A0h]
  _OWORD v22[2]; // [rsp+68h] [rbp-90h] BYREF
  char *Src[4]; // [rsp+88h] [rbp-70h] BYREF

  *(_OWORD *)lpSubKey = 0;
  v21 = 0;
  v9 = *((_QWORD *)this + 2);
  if ( *((_QWORD *)this + 3) > 7u )
    this = *(StateSeparation **)this;
  try
  {
    std::wstring::_Construct<2,unsigned short const *>((__int64)lpSubKey, this, v9);
    if ( a2 && *a2 )
    {
      if ( (_QWORD)v21 == 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      v12 = lpSubKey;
      if ( *((_QWORD *)&v21 + 1) > 7u )
        v12 = (LPCWSTR *)lpSubKey[0];
      std::wstring::wstring(Src, v10, v11, v12, v21);
      v13 = -1;
      do
        ++v13;
      while ( a2[v13] );
      v14 = std::wstring::_Append<unsigned short>(Src, a2, v13);
      v22[0] = *(_OWORD *)v14;
      v15 = v22[0];
      v16 = *((_OWORD *)v14 + 1);
      *(_WORD *)v14 = 0;
      v14[2] = 0;
      v14[3] = 7;
      std::wstring::_Tidy_deallocate((char **)lpSubKey);
      *(_OWORD *)lpSubKey = v15;
      v21 = v16;
      v22[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v22[0]) = 0;
      std::wstring::_Tidy_deallocate((char **)v22);
      std::wstring::_Tidy_deallocate(Src);
    }
    v17 = (const WCHAR *)lpSubKey;
    if ( *((_QWORD *)&v21 + 1) > 7u )
      v17 = lpSubKey[0];
    v18 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, v17, a3, a4, lpData, cbData);
    std::wstring::_Tidy_deallocate((char **)lpSubKey);
  }
  catch ( std::bad_alloc )
  {
    return 14;
  }
  catch ( ... )
  {
    return 31;
  }
  return v18;
}

```

## disassembly

```asm
0x14003287c  mov     rax, rsp
0x14003287f  push    rbx
0x140032880  push    rsi
0x140032881  push    rdi
0x140032882  push    r14
0x140032884  push    r15
0x140032886  sub     rsp, 0D0h
0x14003288d  movaps  xmmword ptr [rax-38h], xmm6
0x140032891  movaps  xmmword ptr [rax-48h], xmm7
0x140032895  mov     rax, cs:__security_cookie
0x14003289c  xor     rax, rsp
0x14003289f  mov     [rsp+0F8h+var_50], rax
0x1400328a7  mov     esi, r9d
0x1400328aa  mov     rdi, r8
0x1400328ad  mov     rbx, rdx
0x1400328b0  mov     r14, [rsp+0F8h+arg_20]
0x1400328b8  xor     r15d, r15d
0x1400328bb  xorps   xmm0, xmm0
0x1400328be  movups  xmmword ptr [rsp+0F8h+lpSubKey], xmm0
0x1400328c3  xorps   xmm1, xmm1
0x1400328c6  movdqu  [rsp+0F8h+var_A0], xmm1
0x1400328cc  mov     r8, [rcx+10h]
0x1400328d0  cmp     qword ptr [rcx+18h], 7
0x1400328d5  jbe     short loc_1400328DA
0x1400328d7  mov     rcx, [rcx]
0x1400328da  mov     rdx, rcx
0x1400328dd  lea     rcx, [rsp+0F8h+lpSubKey]
0x1400328e2  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1400328e7  nop
0x1400328e8  test    rbx, rbx
0x1400328eb  jz      loc_1400329BE
0x1400328f1  cmp     [rbx], r15w
0x1400328f5  jz      loc_1400329BE
0x1400328fb  mov     rcx, qword ptr [rsp+0F8h+var_A0]
0x140032900  mov     rax, 7FFFFFFFFFFFFFFEh
0x14003290a  sub     rax, rcx
0x14003290d  cmp     rax, 1
0x140032911  jb      loc_140032A34
0x140032917  lea     r9, [rsp+0F8h+lpSubKey]
0x14003291c  cmp     qword ptr [rsp+0F8h+var_A0+8], 7
0x140032922  cmova   r9, [rsp+0F8h+lpSubKey]
0x140032928  mov     [rsp+0F8h+var_C8], 1
0x140032931  mov     [rsp+0F8h+lpData], rcx
0x140032936  lea     rcx, [rsp+0F8h+Src]
0x14003293e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x140032943  nop
0x140032944  or      r8, 0FFFFFFFFFFFFFFFFh
0x140032948  inc     r8
0x14003294b  cmp     [rbx+r8*2], r15w
0x140032950  jnz     short loc_140032948
0x140032952  mov     rdx, rbx
0x140032955  lea     rcx, [rsp+0F8h+Src]; Src
0x14003295d  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x140032962  movups  xmm7, xmmword ptr [rax]
0x140032965  movups  [rsp+0F8h+var_90], xmm7
0x14003296a  movups  xmm6, xmmword ptr [rax+10h]
0x14003296e  mov     [rax], r15w
0x140032972  mov     [rax+10h], r15
0x140032976  mov     qword ptr [rax+18h], 7
0x14003297e  lea     rcx, [rsp+0F8h+lpSubKey]
0x140032983  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140032988  movups  xmmword ptr [rsp+0F8h+lpSubKey], xmm7
0x14003298d  movups  [rsp+0F8h+var_A0], xmm6
0x140032992  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14003299a  movdqu  [rsp+0F8h+var_80], xmm0
0x1400329a0  mov     word ptr [rsp+0F8h+var_90], r15w
0x1400329a6  lea     rcx, [rsp+0F8h+var_90]
0x1400329ab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400329b0  nop
0x1400329b1  lea     rcx, [rsp+0F8h+Src]
0x1400329b9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400329be  lea     rdx, [rsp+0F8h+lpSubKey]
0x1400329c3  cmp     qword ptr [rsp+0F8h+var_A0+8], 7
0x1400329c9  cmova   rdx, [rsp+0F8h+lpSubKey]; lpSubKey
0x1400329cf  mov     eax, [rsp+0F8h+arg_28]
0x1400329d6  mov     [rsp+0F8h+cbData], eax; cbData
0x1400329da  mov     [rsp+0F8h+lpData], r14; lpData
0x1400329df  mov     r9d, esi; dwType
0x1400329e2  mov     r8, rdi; lpValueName
0x1400329e5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400329ec  call    cs:__imp_RegSetKeyValueW
0x1400329f2  mov     ebx, eax
0x1400329f4  lea     rcx, [rsp+0F8h+lpSubKey]
0x1400329f9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400329fe  nop
0x1400329ff  jmp     short loc_140032A05
0x140032a01  mov     ebx, [rsp+0F8h+var_B8]
0x140032a05  mov     eax, ebx
0x140032a07  mov     rcx, [rsp+0F8h+var_50]
0x140032a0f  xor     rcx, rsp; StackCookie
0x140032a12  call    __security_check_cookie
0x140032a17  lea     r11, [rsp+0F8h+var_28]
0x140032a1f  movaps  xmm6, xmmword ptr [r11-10h]
0x140032a24  movaps  xmm7, xmmword ptr [r11-20h]
0x140032a29  mov     rsp, r11
0x140032a2c  pop     r15
0x140032a2e  pop     r14
0x140032a30  pop     rdi
0x140032a31  pop     rsi
0x140032a32  pop     rbx
0x140032a33  retn
0x140032a34  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
