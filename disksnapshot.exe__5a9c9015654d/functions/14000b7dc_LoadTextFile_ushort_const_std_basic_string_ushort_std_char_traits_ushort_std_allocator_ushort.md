# LoadTextFile(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x14000b7dc`
- end: `0x14000ba6c`
- name: `?LoadTextFile@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `656`
- prototype: `__int64 __fastcall(wchar_t *FileName, _QWORD *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14000a604`
- `0x14000ba74`

## callees

- `0x140001c50`
- `0x1400052b0`
- `0x14000ae5c`
- `0x14000b7dc`
- `0x14000c310`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000b819`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000b842`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000b860`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000b87a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000b885`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000b91d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000b94c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000b819`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000b842`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000b860`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000b87a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000b885`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000b91d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000b94c`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x14000b82f`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen` at `0x14000b82f`
- `api-ms-win-crt-private-l1-1-0!_o__wstat64i32` at `0x14000b874`
- `api-ms-win-crt-private-l1-1-0!_o__wstat64i32` at `0x14000b874`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x14000ba3e`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x14000ba3e`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x14000b943`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x14000b943`

## pseudocode

```c
__int64 __fastcall LoadTextFile(wchar_t *FileName, _QWORD *Src)
{
  FILE *v4; // r15
  signed int v5; // esi
  size_t st_size; // r14
  unsigned __int64 v7; // rcx
  _QWORD *v8; // rcx
  unsigned __int64 v9; // rdx
  _QWORD *v10; // r8
  _WORD *v11; // rdi
  size_t i; // rcx
  _QWORD *v13; // rcx
  size_t v14; // rdi
  size_t v15; // rdx
  unsigned __int64 v16; // rdi
  _QWORD *v17; // rcx
  size_t v18; // rcx
  _QWORD *v19; // r8
  _WORD *v20; // rdi
  __int64 v21; // rdx
  _QWORD *v22; // rcx
  _stat64i32 Stat; // [rsp+40h] [rbp-58h] BYREF

  memset(&Stat, 0, sizeof(Stat));
  *(_DWORD *)_o__errno() = 0;
  v4 = _wfopen(FileName, L"rtS, ccs=UTF-8");
  if ( v4 )
  {
    *(_DWORD *)_o__errno() = 0;
    _wstat64i32(FileName, &Stat);
    if ( *(_DWORD *)_o__errno() )
    {
      v5 = *(_DWORD *)_o__errno();
      if ( v5 > 0 )
        v5 = (unsigned __int16)v5 | 0x80070000;
      goto LABEL_47;
    }
    v5 = 0;
    st_size = Stat.st_size;
    v7 = Src[2];
    if ( Stat.st_size > v7 )
    {
      v9 = Stat.st_size - v7;
      if ( v9 > Src[3] - v7 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(Src);
      }
      else
      {
        Src[2] = Stat.st_size;
        if ( Src[3] <= 7u )
          v10 = Src;
        else
          v10 = (_QWORD *)*Src;
        v11 = (_WORD *)v10 + v7;
        if ( v9 )
        {
          for ( i = st_size - v7; i; --i )
            *v11++ = 0;
        }
        *((_WORD *)v10 + st_size) = 0;
      }
    }
    else
    {
      Src[2] = Stat.st_size;
      if ( Src[3] <= 7u )
        v8 = Src;
      else
        v8 = (_QWORD *)*Src;
      *((_WORD *)v8 + st_size) = 0;
    }
    *(_DWORD *)_o__errno() = 0;
    if ( Src[3] <= 7u )
      v13 = Src;
    else
      v13 = (_QWORD *)*Src;
    v14 = fread(v13, 2u, st_size, v4);
    if ( *(_DWORD *)_o__errno() )
    {
      v5 = -2147467259;
LABEL_47:
      fclose(v4);
      return (unsigned int)v5;
    }
    v15 = v14 + 1;
    v16 = Src[2];
    if ( v15 > v16 )
    {
      v18 = v15 - v16;
      if ( v15 - v16 > Src[3] - v16 )
      {
        if ( __eh34_try(-1, 0) )
        {
          __eh34_scope_strut(0);
          std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(Src);
        }
        if ( __eh34_catch(0) )
        {
          if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
          {
            v5 = -2147024882;
            __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_14000BA32);
            goto LABEL_47;
          }
        }
      }
      else
      {
        Src[2] = v15;
        if ( Src[3] <= 7u )
          v19 = Src;
        else
          v19 = (_QWORD *)*Src;
        v20 = (_WORD *)v19 + v16;
        if ( v18 )
        {
          while ( v18 )
          {
            *v20++ = 0;
            --v18;
          }
        }
        *((_WORD *)v19 + v15) = 0;
      }
    }
    else
    {
      Src[2] = v15;
      if ( Src[3] <= 7u )
        v17 = Src;
      else
        v17 = (_QWORD *)*Src;
      *((_WORD *)v17 + v15) = 0;
    }
    v21 = Src[2];
    if ( Src[3] == v21 )
    {
      ((void (__usercall *)(void *@<rcx>, __int64))std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>)(
        Src,
        1);
    }
    else
    {
      Src[2] = v21 + 1;
      if ( Src[3] <= 7u )
        v22 = Src;
      else
        v22 = (_QWORD *)*Src;
      *((_WORD *)v22 + v21) = 10;
      *((_WORD *)v22 + v21 + 1) = 0;
    }
    std::wstring::shrink_to_fit(Src);
    goto LABEL_47;
  }
  v5 = *(_DWORD *)_o__errno();
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000b7dc  mov     [rsp+arg_10], rbx
0x14000b7e1  mov     [rsp+arg_18], rsi
0x14000b7e6  push    rdi
0x14000b7e7  push    r14
0x14000b7e9  push    r15
0x14000b7eb  sub     rsp, 80h
0x14000b7f2  mov     rax, cs:__security_cookie
0x14000b7f9  xor     rax, rsp
0x14000b7fc  mov     [rsp+98h+var_28], rax
0x14000b801  mov     rbx, rdx
0x14000b804  mov     rdi, rcx
0x14000b807  xorps   xmm0, xmm0
0x14000b80a  movups  xmmword ptr [rsp+98h+Stat.st_dev], xmm0
0x14000b80f  movups  xmmword ptr [rsp+98h+Stat.st_rdev], xmm0
0x14000b814  movups  xmmword ptr [rsp+98h+Stat.st_mtime], xmm0
0x14000b819  call    cs:__imp__o__errno
0x14000b81f  mov     dword ptr [rax], 0
0x14000b825  lea     rdx, aRtsCcsUtf8; "rtS, ccs=UTF-8"
0x14000b82c  mov     rcx, rdi; FileName
0x14000b82f  call    cs:__imp__wfopen
0x14000b835  mov     r15, rax
0x14000b838  mov     [rsp+98h+var_60], rax
0x14000b83d  test    rax, rax
0x14000b840  jnz     short loc_14000B860
0x14000b842  call    cs:__imp__o__errno
0x14000b848  mov     esi, [rax]
0x14000b84a  test    esi, esi
0x14000b84c  jle     loc_14000BA44
0x14000b852  movzx   esi, si
0x14000b855  or      esi, 80070000h
0x14000b85b  jmp     loc_14000BA44
0x14000b860  call    cs:__imp__o__errno
0x14000b866  mov     dword ptr [rax], 0
0x14000b86c  lea     rdx, [rsp+98h+Stat]; Stat
0x14000b871  mov     rcx, rdi; FileName
0x14000b874  call    cs:__imp__wstat64i32
0x14000b87a  call    cs:__imp__o__errno
0x14000b880  cmp     dword ptr [rax], 0
0x14000b883  jz      short loc_14000B8A3
0x14000b885  call    cs:__imp__o__errno
0x14000b88b  mov     esi, [rax]
0x14000b88d  test    esi, esi
0x14000b88f  jle     loc_14000BA3B
0x14000b895  movzx   esi, si
0x14000b898  or      esi, 80070000h
0x14000b89e  jmp     loc_14000BA3B
0x14000b8a3  xor     esi, esi
0x14000b8a5  movsxd  r14, [rsp+98h+Stat.st_size]
0x14000b8aa  mov     rcx, [rbx+10h]
0x14000b8ae  cmp     r14, rcx
0x14000b8b1  ja      short loc_14000B8CF
0x14000b8b3  mov     [rbx+10h], r14
0x14000b8b7  cmp     qword ptr [rbx+18h], 7
0x14000b8bc  jbe     short loc_14000B8C3
0x14000b8be  mov     rcx, [rbx]
0x14000b8c1  jmp     short loc_14000B8C6
0x14000b8c3  mov     rcx, rbx
0x14000b8c6  xor     eax, eax
0x14000b8c8  mov     [rcx+r14*2], ax
0x14000b8cd  jmp     short loc_14000B91D
0x14000b8cf  mov     rdx, r14
0x14000b8d2  sub     rdx, rcx
0x14000b8d5  mov     rax, [rbx+18h]
0x14000b8d9  sub     rax, rcx
0x14000b8dc  cmp     rdx, rax
0x14000b8df  ja      short loc_14000B911
0x14000b8e1  mov     [rbx+10h], r14
0x14000b8e5  cmp     qword ptr [rbx+18h], 7
0x14000b8ea  jbe     short loc_14000B8F1
0x14000b8ec  mov     r8, [rbx]
0x14000b8ef  jmp     short loc_14000B8F4
0x14000b8f1  mov     r8, rbx
0x14000b8f4  lea     rdi, [r8+rcx*2]
0x14000b8f8  test    rdx, rdx
0x14000b8fb  jz      short loc_14000B908
0x14000b8fd  xor     eax, eax
0x14000b8ff  movzx   eax, ax
0x14000b902  mov     rcx, rdx
0x14000b905  rep stosw
0x14000b908  xor     eax, eax
0x14000b90a  mov     [r8+r14*2], ax
0x14000b90f  jmp     short loc_14000B91D
0x14000b911  mov     r9, rdx
0x14000b914  mov     rcx, rbx; Src
0x14000b917  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x14000b91c  nop
0x14000b91d  call    cs:__imp__o__errno
0x14000b923  mov     dword ptr [rax], 0
0x14000b929  cmp     qword ptr [rbx+18h], 7
0x14000b92e  jbe     short loc_14000B935
0x14000b930  mov     rcx, [rbx]
0x14000b933  jmp     short loc_14000B938
0x14000b935  mov     rcx, rbx; Buffer
0x14000b938  mov     r9, r15; Stream
0x14000b93b  mov     r8, r14; ElementCount
0x14000b93e  mov     edx, 2; ElementSize
0x14000b943  call    cs:__imp_fread
0x14000b949  mov     rdi, rax
0x14000b94c  call    cs:__imp__o__errno
0x14000b952  cmp     dword ptr [rax], 0
0x14000b955  jz      short loc_14000B961
0x14000b957  mov     esi, 80004005h
0x14000b95c  jmp     loc_14000BA3B
0x14000b961  lea     rdx, [rdi+1]
0x14000b965  mov     rdi, [rbx+10h]
0x14000b969  cmp     rdx, rdi
0x14000b96c  ja      short loc_14000B989
0x14000b96e  mov     [rbx+10h], rdx
0x14000b972  cmp     qword ptr [rbx+18h], 7
0x14000b977  jbe     short loc_14000B97E
0x14000b979  mov     rcx, [rbx]
0x14000b97c  jmp     short loc_14000B981
0x14000b97e  mov     rcx, rbx
0x14000b981  xor     eax, eax
0x14000b983  mov     [rcx+rdx*2], ax
0x14000b987  jmp     short loc_14000B9D6
0x14000b989  mov     rcx, rdx
0x14000b98c  sub     rcx, rdi
0x14000b98f  mov     rax, [rbx+18h]
0x14000b993  sub     rax, rdi
0x14000b996  cmp     rcx, rax
0x14000b999  ja      short loc_14000B9C8
0x14000b99b  mov     [rbx+10h], rdx
0x14000b99f  cmp     qword ptr [rbx+18h], 7
0x14000b9a4  jbe     short loc_14000B9AB
0x14000b9a6  mov     r8, [rbx]
0x14000b9a9  jmp     short loc_14000B9AE
0x14000b9ab  mov     r8, rbx
0x14000b9ae  lea     rdi, [r8+rdi*2]
0x14000b9b2  test    rcx, rcx
0x14000b9b5  jz      short loc_14000B9BF
0x14000b9b7  xor     eax, eax
0x14000b9b9  movzx   eax, ax
0x14000b9bc  rep stosw
0x14000b9bf  xor     eax, eax
0x14000b9c1  mov     [r8+rdx*2], ax
0x14000b9c6  jmp     short loc_14000B9D6
0x14000b9c8  mov     r9, rcx
0x14000b9cb  mov     rdx, rcx
0x14000b9ce  mov     rcx, rbx; Src
0x14000b9d1  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x14000b9d6  mov     rdx, [rbx+10h]
0x14000b9da  mov     rax, [rbx+18h]
0x14000b9de  sub     rax, rdx
0x14000b9e1  mov     ecx, 1
0x14000b9e6  cmp     rax, rcx
0x14000b9e9  jb      short loc_14000BA10
0x14000b9eb  lea     rdi, [rdx+1]
0x14000b9ef  mov     [rbx+10h], rdi
0x14000b9f3  cmp     qword ptr [rbx+18h], 7
0x14000b9f8  jbe     short loc_14000B9FF
0x14000b9fa  mov     rcx, [rbx]
0x14000b9fd  jmp     short loc_14000BA02
0x14000b9ff  mov     rcx, rbx
0x14000ba02  mov     word ptr [rcx+rdx*2], 0Ah
0x14000ba08  xor     eax, eax
0x14000ba0a  mov     [rcx+rdi*2], ax
0x14000ba0e  jmp     short loc_14000BA27
0x14000ba10  mov     [rsp+98h+var_78], rcx; __int64
0x14000ba15  lea     r9, asc_14000EE8C; "\n"
0x14000ba1c  mov     rdx, rcx
0x14000ba1f  mov     rcx, rbx; Src
0x14000ba22  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x14000ba27  mov     rcx, rbx
0x14000ba2a  call    ?shrink_to_fit@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::wstring::shrink_to_fit(void)
0x14000ba2f  nop
0x14000ba30  jmp     short loc_14000BA3B
0x14000ba32  mov     esi, [rsp+98h+var_68]
0x14000ba36  mov     r15, [rsp+98h+var_60]
0x14000ba3b  mov     rcx, r15; Stream
0x14000ba3e  call    cs:__imp_fclose
0x14000ba44  mov     eax, esi
0x14000ba46  mov     rcx, [rsp+98h+var_28]
0x14000ba4b  xor     rcx, rsp; StackCookie
0x14000ba4e  call    __security_check_cookie
0x14000ba53  lea     r11, [rsp+98h+var_18]
0x14000ba5b  mov     rbx, [r11+30h]
0x14000ba5f  mov     rsi, [r11+38h]
0x14000ba63  mov     rsp, r11
0x14000ba66  pop     r15
0x14000ba68  pop     r14
0x14000ba6a  pop     rdi
0x14000ba6b  retn
```
