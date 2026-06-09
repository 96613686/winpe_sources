# WcmCommon::Registry::Iterator<WcmCommon::Registry::Details::ValueIteratorData>::enumerateNext(void)

- ea: `0x18002da7c`
- end: `0x18002dbff`
- name: `?enumerateNext@?$Iterator@UValueIteratorData@Details@Registry@WcmCommon@@@Registry@WcmCommon@@AEAAXXZ`
- size: `387`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026924`
- `0x180027fbc`
- `0x1800282b0`

## callees

- `0x180007c90`
- `0x180008704`
- `0x1800172c8`
- `0x180026224`
- `0x180026d28`
- `0x1800270ec`
- `0x18002d9e8`
- `0x18002da7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002db20`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002db20`

## string_xrefs

- `0x18002dbae`: `onecore\private\net\inc\wcm\wcm_registry_iterator.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned int __fastcall WcmCommon::Registry::Iterator<WcmCommon::Registry::Details::ValueIteratorData>::enumerateNext(
        __int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rcx
  unsigned __int64 v4; // rbx
  __int64 v5; // rsi
  unsigned __int64 v6; // rax
  size_t v7; // rbx
  __int64 v8; // rsi
  unsigned int result; // eax
  LPWSTR v10; // rdx
  __int64 v11; // rbp
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rbx
  WCHAR *v14; // rax
  size_t v15; // rbx
  unsigned int lpReserved; // [rsp+20h] [rbp-98h]
  DWORD cchValueName; // [rsp+40h] [rbp-78h] BYREF
  _BYTE v18[8]; // [rsp+48h] [rbp-70h] BYREF
  _BYTE v19[32]; // [rsp+50h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v2 = a1 + 8;
  v3 = *(_QWORD *)(a1 + 8);
  v4 = (*(_QWORD *)(v2 + 16) - v3) >> 1;
  v5 = *(_QWORD *)(v2 + 8);
  v6 = (v5 - v3) >> 1;
  if ( v4 < v6 )
  {
    v5 = v3 + 2 * v4;
LABEL_5:
    *(_QWORD *)(v2 + 8) = v5;
    goto LABEL_6;
  }
  if ( v4 > v6 )
  {
    v7 = 2 * (v4 - v6);
    memset_0(*(void **)(v2 + 8), 0, v7);
    v5 += v7;
    goto LABEL_5;
  }
LABEL_6:
  v8 = (v5 - *(_QWORD *)v2) >> 1;
  while ( 1 )
  {
    cchValueName = v8;
    result = RegEnumValueW(*(HKEY *)a1, *(_DWORD *)(a1 + 36), *(LPWSTR *)v2, &cchValueName, 0, (LPDWORD)(a1 + 32), 0, 0);
    if ( !result )
      return result;
    if ( result != 234 )
    {
      if ( result != 259 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x15A,
          (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_registry_iterator.h",
          (const char *)result,
          lpReserved);
      WcmCommon::Registry::Details::ValueIteratorData::ValueIteratorData((WcmCommon::Registry::Details::ValueIteratorData *)v18);
      WcmCommon::Registry::Details::ValueIteratorData::operator=(a1, v18);
      return std::vector<wchar_t>::_Tidy(v19);
    }
    LODWORD(v8) = cchValueName + 1;
    v10 = *(LPWSTR *)v2;
    v11 = *(_QWORD *)(v2 + 8);
    v12 = (v11 - *(_QWORD *)v2) >> 1;
    v13 = cchValueName + 1;
    if ( v13 < v12 )
    {
      v14 = &v10[cchValueName + 1];
      goto LABEL_15;
    }
    if ( v13 > v12 )
    {
      if ( v13 <= (__int64)(*(_QWORD *)(v2 + 16) - (_QWORD)v10) >> 1 )
      {
        v15 = 2 * (v13 - v12);
        memset_0(*(void **)(v2 + 8), 0, v15);
        v14 = (WCHAR *)(v15 + v11);
LABEL_15:
        *(_QWORD *)(v2 + 8) = v14;
      }
      else
      {
        std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(v2, cchValueName + 1);
      }
    }
  }
}

```

## disassembly

```asm
0x18002da7c  push    rbx
0x18002da7e  push    rbp
0x18002da7f  push    rsi
0x18002da80  push    rdi
0x18002da81  push    r14
0x18002da83  push    r15
0x18002da85  sub     rsp, 88h
0x18002da8c  mov     rax, cs:__security_cookie
0x18002da93  xor     rax, rsp
0x18002da96  mov     [rsp+0B8h+var_48], rax
0x18002da9b  mov     r14, rcx
0x18002da9e  lea     rdi, [rcx+8]
0x18002daa2  mov     rcx, [rdi]
0x18002daa5  mov     rbx, [rdi+10h]
0x18002daa9  sub     rbx, rcx
0x18002daac  sar     rbx, 1
0x18002daaf  mov     rsi, [rdi+8]
0x18002dab3  mov     rax, rsi
0x18002dab6  sub     rax, rcx
0x18002dab9  sar     rax, 1
0x18002dabc  cmp     rbx, rax
0x18002dabf  jnb     short loc_18002DAC7
0x18002dac1  lea     rsi, [rcx+rbx*2]
0x18002dac5  jmp     short loc_18002DADF
0x18002dac7  jbe     short loc_18002DAE3
0x18002dac9  sub     rbx, rax
0x18002dacc  add     rbx, rbx
0x18002dacf  mov     r8, rbx; Size
0x18002dad2  xor     edx, edx; Val
0x18002dad4  mov     rcx, rsi; void *
0x18002dad7  call    memset_0
0x18002dadc  add     rsi, rbx
0x18002dadf  mov     [rdi+8], rsi
0x18002dae3  sub     rsi, [rdi]
0x18002dae6  sar     rsi, 1
0x18002dae9  lea     r15, [r14+20h]
0x18002daed  mov     [rsp+0B8h+cchValueName], esi
0x18002daf1  mov     [rsp+0B8h+lpcbData], 0; lpcbData
0x18002dafa  mov     [rsp+0B8h+lpData], 0; lpData
0x18002db03  mov     [rsp+0B8h+lpType], r15; lpType
0x18002db08  mov     [rsp+0B8h+lpReserved], 0; unsigned int
0x18002db11  lea     r9, [rsp+0B8h+cchValueName]; lpcchValueName
0x18002db16  mov     r8, [rdi]; lpValueName
0x18002db19  mov     edx, [r14+24h]; dwIndex
0x18002db1d  mov     rcx, [r14]; hKey
0x18002db20  call    cs:__imp_RegEnumValueW
0x18002db26  mov     edx, eax
0x18002db28  test    eax, eax
0x18002db2a  jz      loc_18002DBE2
0x18002db30  sub     edx, 0EAh
0x18002db36  jnz     short loc_18002DB9E
0x18002db38  mov     eax, [rsp+0B8h+cchValueName]
0x18002db3c  inc     eax
0x18002db3e  mov     esi, eax
0x18002db40  mov     rdx, [rdi]
0x18002db43  mov     rbp, [rdi+8]
0x18002db47  mov     rcx, rbp
0x18002db4a  sub     rcx, rdx
0x18002db4d  sar     rcx, 1
0x18002db50  mov     ebx, eax
0x18002db52  cmp     rbx, rcx
0x18002db55  jnb     short loc_18002DB5D
0x18002db57  lea     rax, [rdx+rax*2]
0x18002db5b  jmp     short loc_18002DB95
0x18002db5d  jbe     short loc_18002DAED
0x18002db5f  mov     rax, [rdi+10h]
0x18002db63  sub     rax, rdx
0x18002db66  sar     rax, 1
0x18002db69  cmp     rbx, rax
0x18002db6c  jbe     short loc_18002DB7E
0x18002db6e  mov     rdx, rbx
0x18002db71  mov     rcx, rdi
0x18002db74  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002db79  jmp     loc_18002DAED
0x18002db7e  sub     rbx, rcx
0x18002db81  add     rbx, rbx
0x18002db84  mov     r8, rbx; Size
0x18002db87  xor     edx, edx; Val
0x18002db89  mov     rcx, rbp; void *
0x18002db8c  call    memset_0
0x18002db91  lea     rax, [rbx+rbp]
0x18002db95  mov     [rdi+8], rax
0x18002db99  jmp     loc_18002DAED
0x18002db9e  cmp     edx, 19h
0x18002dba1  jz      short loc_18002DBC0
0x18002dba3  mov     rcx, [rsp+0B8h]; this
0x18002dbab  mov     r9d, eax; char *
0x18002dbae  lea     r8, aOnecorePrivate_1; "onecore\\private\\net\\inc\\wcm\\wcm_re"...
0x18002dbb5  mov     edx, 15Ah; void *
0x18002dbba  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002dbc0  lea     rcx, [rsp+0B8h+var_70]; this
0x18002dbc5  call    ??0ValueIteratorData@Details@Registry@WcmCommon@@QEAA@XZ; WcmCommon::Registry::Details::ValueIteratorData::ValueIteratorData(void)
0x18002dbca  lea     rdx, [rsp+0B8h+var_70]
0x18002dbcf  mov     rcx, r14
0x18002dbd2  call    ??4ValueIteratorData@Details@Registry@WcmCommon@@QEAAAEAU0123@AEBU0123@@Z; WcmCommon::Registry::Details::ValueIteratorData::operator=(WcmCommon::Registry::Details::ValueIteratorData const &)
0x18002dbd7  lea     rcx, [rsp+0B8h+var_68]
0x18002dbdc  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x18002dbe1  nop
0x18002dbe2  mov     rcx, [rsp+0B8h+var_48]
0x18002dbe7  xor     rcx, rsp; StackCookie
0x18002dbea  call    __security_check_cookie
0x18002dbef  add     rsp, 88h
0x18002dbf6  pop     r15
0x18002dbf8  pop     r14
0x18002dbfa  pop     rdi
0x18002dbfb  pop     rsi
0x18002dbfc  pop     rbp
0x18002dbfd  pop     rbx
0x18002dbfe  retn
```
