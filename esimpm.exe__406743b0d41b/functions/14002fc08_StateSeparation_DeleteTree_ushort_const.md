# StateSeparation::DeleteTree(ushort const *)

- ea: `0x14002fc08`
- end: `0x14002fd9b`
- name: `?DeleteTree@StateSeparation@@QEAAKPEBG@Z`
- size: `403`
- prototype: `__int64 __fastcall(StateSeparation *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14002f9e0`

## callees

- `0x140002f60`
- `0x140013df8`
- `0x140013e64`
- `0x140014700`
- `0x1400167fc`
- `0x14002690c`
- `0x14002fc08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x14002fd4e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x14002fd4e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StateSeparation::DeleteTree(StateSeparation *this, const unsigned __int16 *a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  LPCWSTR *v5; // r9
  __int64 v6; // r8
  __int64 v7; // rax
  __int128 v8; // xmm7
  __int128 v9; // xmm6
  const WCHAR *v10; // rdx
  unsigned int v11; // ebx
  LPCWSTR lpSubKey[2]; // [rsp+48h] [rbp-90h] BYREF
  __int128 v14; // [rsp+58h] [rbp-80h]
  _OWORD v15[2]; // [rsp+68h] [rbp-70h] BYREF
  _BYTE Src[32]; // [rsp+88h] [rbp-50h] BYREF

  *(_OWORD *)lpSubKey = 0;
  v14 = 0;
  if ( *((_QWORD *)this + 3) > 7u )
    this = *(StateSeparation **)this;
  try
  {
    std::wstring::_Construct<2,unsigned short const *>(lpSubKey, this);
    if ( a2 && *a2 )
    {
      if ( (_QWORD)v14 == 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      v5 = lpSubKey;
      if ( *((_QWORD *)&v14 + 1) > 7u )
        v5 = (LPCWSTR *)lpSubKey[0];
      std::wstring::wstring(Src, v3, v4, v5, v14);
      v6 = -1;
      do
        ++v6;
      while ( a2[v6] );
      v7 = std::wstring::_Append<unsigned short>(Src);
      v15[0] = *(_OWORD *)v7;
      v8 = v15[0];
      v9 = *(_OWORD *)(v7 + 16);
      *(_WORD *)v7 = 0;
      *(_QWORD *)(v7 + 16) = 0;
      *(_QWORD *)(v7 + 24) = 7;
      std::wstring::_Tidy_deallocate(lpSubKey);
      *(_OWORD *)lpSubKey = v8;
      v14 = v9;
      v15[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v15[0]) = 0;
      std::wstring::_Tidy_deallocate(v15);
      std::wstring::_Tidy_deallocate(Src);
    }
    v10 = (const WCHAR *)lpSubKey;
    if ( *((_QWORD *)&v14 + 1) > 7u )
      v10 = lpSubKey[0];
    v11 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, v10);
    std::wstring::_Tidy_deallocate(lpSubKey);
  }
  catch ( std::bad_alloc )
  {
    return 14;
  }
  catch ( ... )
  {
    return 31;
  }
  return v11;
}

```

## disassembly

```asm
0x14002fc08  mov     rax, rsp
0x14002fc0b  mov     [rax+18h], rbx
0x14002fc0f  push    rdi
0x14002fc10  sub     rsp, 0D0h
0x14002fc17  movaps  xmmword ptr [rax-18h], xmm6
0x14002fc1b  movaps  xmmword ptr [rax-28h], xmm7
0x14002fc1f  mov     rax, cs:__security_cookie
0x14002fc26  xor     rax, rsp
0x14002fc29  mov     [rsp+0D8h+var_30], rax
0x14002fc31  mov     rbx, rdx
0x14002fc34  xor     edi, edi
0x14002fc36  xorps   xmm0, xmm0
0x14002fc39  movups  xmmword ptr [rsp+0D8h+lpSubKey], xmm0
0x14002fc3e  xorps   xmm1, xmm1
0x14002fc41  movdqu  [rsp+0D8h+var_80], xmm1
0x14002fc47  mov     r8, [rcx+10h]
0x14002fc4b  cmp     qword ptr [rcx+18h], 7
0x14002fc50  jbe     short loc_14002FC55
0x14002fc52  mov     rcx, [rcx]
0x14002fc55  mov     rdx, rcx
0x14002fc58  lea     rcx, [rsp+0D8h+lpSubKey]
0x14002fc5d  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x14002fc62  nop
0x14002fc63  test    rbx, rbx
0x14002fc66  jz      loc_14002FD36
0x14002fc6c  cmp     [rbx], di
0x14002fc6f  jz      loc_14002FD36
0x14002fc75  mov     rcx, qword ptr [rsp+0D8h+var_80]
0x14002fc7a  mov     rax, 7FFFFFFFFFFFFFFEh
0x14002fc84  sub     rax, rcx
0x14002fc87  cmp     rax, 1
0x14002fc8b  jb      loc_14002FD94
0x14002fc91  lea     r9, [rsp+0D8h+lpSubKey]
0x14002fc96  cmp     qword ptr [rsp+0D8h+var_80+8], 7
0x14002fc9c  cmova   r9, [rsp+0D8h+lpSubKey]
0x14002fca2  mov     [rsp+0D8h+var_A8], 1
0x14002fcab  mov     [rsp+0D8h+var_B8], rcx
0x14002fcb0  lea     rcx, [rsp+0D8h+Src]
0x14002fcb8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x14002fcbd  nop
0x14002fcbe  or      r8, 0FFFFFFFFFFFFFFFFh
0x14002fcc2  inc     r8
0x14002fcc5  cmp     [rbx+r8*2], di
0x14002fcca  jnz     short loc_14002FCC2
0x14002fccc  mov     rdx, rbx
0x14002fccf  lea     rcx, [rsp+0D8h+Src]; Src
0x14002fcd7  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x14002fcdc  movups  xmm7, xmmword ptr [rax]
0x14002fcdf  movups  [rsp+0D8h+var_70], xmm7
0x14002fce4  movups  xmm6, xmmword ptr [rax+10h]
0x14002fce8  mov     [rax], di
0x14002fceb  mov     [rax+10h], rdi
0x14002fcef  mov     qword ptr [rax+18h], 7
0x14002fcf7  lea     rcx, [rsp+0D8h+lpSubKey]
0x14002fcfc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002fd01  movups  xmmword ptr [rsp+0D8h+lpSubKey], xmm7
0x14002fd06  movups  [rsp+0D8h+var_80], xmm6
0x14002fd0b  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14002fd13  movdqu  [rsp+0D8h+var_60], xmm0
0x14002fd19  mov     word ptr [rsp+0D8h+var_70], di
0x14002fd1e  lea     rcx, [rsp+0D8h+var_70]
0x14002fd23  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002fd28  nop
0x14002fd29  lea     rcx, [rsp+0D8h+Src]
0x14002fd31  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002fd36  lea     rdx, [rsp+0D8h+lpSubKey]
0x14002fd3b  cmp     qword ptr [rsp+0D8h+var_80+8], 7
0x14002fd41  cmova   rdx, [rsp+0D8h+lpSubKey]; lpSubKey
0x14002fd47  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002fd4e  call    cs:__imp_RegDeleteTreeW
0x14002fd54  mov     ebx, eax
0x14002fd56  lea     rcx, [rsp+0D8h+lpSubKey]
0x14002fd5b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002fd60  nop
0x14002fd61  jmp     short loc_14002FD67
0x14002fd63  mov     ebx, [rsp+0D8h+var_98]
0x14002fd67  mov     eax, ebx
0x14002fd69  mov     rcx, [rsp+0D8h+var_30]
0x14002fd71  xor     rcx, rsp; StackCookie
0x14002fd74  call    __security_check_cookie
0x14002fd79  lea     r11, [rsp+0D8h+var_8]
0x14002fd81  mov     rbx, [r11+20h]
0x14002fd85  movaps  xmm6, xmmword ptr [r11-10h]
0x14002fd8a  movaps  xmm7, xmmword ptr [r11-20h]
0x14002fd8f  mov     rsp, r11
0x14002fd92  pop     rdi
0x14002fd93  retn
0x14002fd94  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
