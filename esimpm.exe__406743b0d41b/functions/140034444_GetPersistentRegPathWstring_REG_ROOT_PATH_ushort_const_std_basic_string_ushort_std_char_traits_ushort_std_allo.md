# GetPersistentRegPathWstring(_REG_ROOT_PATH,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x140034444`
- end: `0x1400345a6`
- name: `?GetPersistentRegPathWstring@@YAKW4_REG_ROOT_PATH@@PEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int128 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140033e00`

## callees

- `0x140002f60`
- `0x140013df8`
- `0x14002a7dc`
- `0x140034444`

## import_xrefs

- `MobileNetworking!GetPersistentRegPath` at `0x1400344da`
- `MobileNetworking!GetPersistentRegPath` at `0x1400344da`

## pseudocode

```c
__int64 __fastcall GetPersistentRegPathWstring(unsigned int a1, __int64 a2, __int128 *a3)
{
  unsigned __int64 v5; // r9
  unsigned __int64 v6; // r8
  unsigned int v7; // esi
  unsigned int v8; // eax
  __int128 *p_Src; // rcx
  __int128 *v10; // r9
  unsigned int PersistentRegPath; // eax
  unsigned int v12; // ebx
  unsigned int v13; // ecx
  unsigned __int64 v14; // rdx
  __int128 *v15; // rcx
  int v17; // [rsp+20h] [rbp-48h] BYREF
  __int128 Src; // [rsp+28h] [rbp-40h] BYREF
  __int128 v19; // [rsp+38h] [rbp-30h]

  Src = 0;
  v5 = 0;
  *(_QWORD *)&v19 = 0;
  v6 = 7;
  *((_QWORD *)&v19 + 1) = 7;
  LOWORD(Src) = 0;
  v7 = 0;
  v8 = 512;
  v17 = 512;
  try
  {
    while ( 1 )
    {
      p_Src = &Src;
      if ( v8 > v5 )
      {
        std::wstring::append(&Src);
      }
      else
      {
        *(_QWORD *)&v19 = v8;
        if ( v6 > 7 )
          p_Src = (__int128 *)Src;
        *((_WORD *)p_Src + v8) = 0;
      }
      v10 = &Src;
      if ( *((_QWORD *)&v19 + 1) > 7u )
        v10 = (__int128 *)Src;
      PersistentRegPath = GetPersistentRegPath(a1, 0, &v17, v10);
      v12 = PersistentRegPath;
      if ( PersistentRegPath != 234 )
        break;
      v13 = v7++;
      if ( v13 >= 3 )
        break;
      v6 = *((_QWORD *)&v19 + 1);
      v5 = v19;
      v8 = v17;
    }
    if ( !PersistentRegPath )
    {
      v14 = (unsigned int)(v17 - 1);
      v15 = &Src;
      if ( v14 > (unsigned __int64)v19 )
      {
        std::wstring::append(&Src);
      }
      else
      {
        *(_QWORD *)&v19 = (unsigned int)(v17 - 1);
        if ( *((_QWORD *)&v19 + 1) > 7u )
          v15 = (__int128 *)Src;
        *((_WORD *)v15 + v14) = 0;
      }
      if ( a3 != &Src )
      {
        std::wstring::_Tidy_deallocate(a3);
        *a3 = Src;
        a3[1] = v19;
        *(_QWORD *)&v19 = 0;
        *((_QWORD *)&v19 + 1) = 7;
        LOWORD(Src) = 0;
      }
    }
    std::wstring::_Tidy_deallocate(&Src);
  }
  catch ( std::bad_alloc )
  {
    return 14;
  }
  catch ( ... )
  {
    return 31;
  }
  return v12;
}

```

## disassembly

```asm
0x140034444  mov     [rsp+arg_8], rbx
0x140034449  push    rsi
0x14003444a  push    rdi
0x14003444b  push    r14
0x14003444d  sub     rsp, 50h
0x140034451  mov     rax, cs:__security_cookie
0x140034458  xor     rax, rsp
0x14003445b  mov     [rsp+68h+var_20], rax
0x140034460  mov     rdi, r8
0x140034463  mov     r14d, ecx
0x140034466  xorps   xmm0, xmm0
0x140034469  movups  [rsp+68h+Src], xmm0
0x14003446e  xor     r9d, r9d
0x140034471  mov     qword ptr [rsp+68h+var_30], r9
0x140034476  lea     r8d, [r9+7]
0x14003447a  mov     qword ptr [rsp+68h+var_30+8], r8
0x14003447f  xor     eax, eax
0x140034481  mov     word ptr [rsp+68h+Src], ax
0x140034486  xor     esi, esi
0x140034488  mov     eax, 200h
0x14003448d  mov     [rsp+68h+var_48], eax
0x140034491  mov     edx, eax
0x140034493  lea     rcx, [rsp+68h+Src]; Src
0x140034498  cmp     rdx, r9
0x14003449b  ja      short loc_1400344B4
0x14003449d  mov     qword ptr [rsp+68h+var_30], rdx
0x1400344a2  cmp     r8, 7
0x1400344a6  cmova   rcx, qword ptr [rsp+68h+Src]
0x1400344ac  xor     eax, eax
0x1400344ae  mov     [rcx+rdx*2], ax
0x1400344b2  jmp     short loc_1400344BF
0x1400344b4  xor     r8d, r8d
0x1400344b7  sub     rdx, r9
0x1400344ba  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x1400344bf  lea     r9, [rsp+68h+Src]
0x1400344c4  cmp     qword ptr [rsp+68h+var_30+8], 7
0x1400344ca  cmova   r9, qword ptr [rsp+68h+Src]
0x1400344d0  lea     r8, [rsp+68h+var_48]
0x1400344d5  xor     edx, edx
0x1400344d7  mov     ecx, r14d
0x1400344da  call    cs:__imp_GetPersistentRegPath
0x1400344e0  mov     ebx, eax
0x1400344e2  cmp     eax, 0EAh
0x1400344e7  jnz     short loc_140034502
0x1400344e9  mov     ecx, esi
0x1400344eb  inc     esi
0x1400344ed  cmp     ecx, 3
0x1400344f0  jnb     short loc_140034502
0x1400344f2  mov     r8, qword ptr [rsp+68h+var_30+8]
0x1400344f7  mov     r9, qword ptr [rsp+68h+var_30]
0x1400344fc  mov     eax, [rsp+68h+var_48]
0x140034500  jmp     short loc_140034491
0x140034502  test    eax, eax
0x140034504  jnz     short loc_140034578
0x140034506  mov     edx, [rsp+68h+var_48]
0x14003450a  dec     edx
0x14003450c  lea     rcx, [rsp+68h+Src]; Src
0x140034511  cmp     rdx, qword ptr [rsp+68h+var_30]
0x140034516  ja      short loc_14003452F
0x140034518  mov     qword ptr [rsp+68h+var_30], rdx
0x14003451d  cmp     qword ptr [rsp+68h+var_30+8], 7
0x140034523  cmova   rcx, qword ptr [rsp+68h+Src]
0x140034529  mov     [rcx+rdx*2], ax
0x14003452d  jmp     short loc_14003453C
0x14003452f  xor     r8d, r8d
0x140034532  sub     rdx, qword ptr [rsp+68h+var_30]
0x140034537  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x14003453c  lea     rax, [rsp+68h+Src]
0x140034541  cmp     rdi, rax
0x140034544  jz      short loc_140034578
0x140034546  mov     rcx, rdi
0x140034549  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003454e  movups  xmm0, [rsp+68h+Src]
0x140034553  movups  xmmword ptr [rdi], xmm0
0x140034556  movups  xmm1, [rsp+68h+var_30]
0x14003455b  movups  xmmword ptr [rdi+10h], xmm1
0x14003455f  mov     qword ptr [rsp+68h+var_30], 0
0x140034568  mov     qword ptr [rsp+68h+var_30+8], 7
0x140034571  xor     eax, eax
0x140034573  mov     word ptr [rsp+68h+Src], ax
0x140034578  lea     rcx, [rsp+68h+Src]
0x14003457d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140034582  nop
0x140034583  jmp     short loc_140034589
0x140034585  mov     ebx, [rsp+68h+var_48]
0x140034589  mov     eax, ebx
0x14003458b  mov     rcx, [rsp+68h+var_20]
0x140034590  xor     rcx, rsp; StackCookie
0x140034593  call    __security_check_cookie
0x140034598  mov     rbx, [rsp+68h+arg_8]
0x14003459d  add     rsp, 50h
0x1400345a1  pop     r14
0x1400345a3  pop     rdi
0x1400345a4  pop     rsi
0x1400345a5  retn
```
