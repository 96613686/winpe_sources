# IsQueueLocal(_bstr_t)

- ea: `0x14000fbcc`
- end: `0x14000fd9e`
- name: `?IsQueueLocal@@YA_NV_bstr_t@@@Z`
- size: `466`
- prototype: `char __fastcall(_bstr_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14000fe40`

## callees

- `0x1400030ac`
- `0x140003868`
- `0x140004f9c`
- `0x140006ac8`
- `0x140007a18`
- `0x14000f6a0`
- `0x14000fa84`
- `0x14000fbcc`
- `0x14001cf00`

## import_xrefs

- `KERNEL32!GetComputerNameW` at `0x14000fc1a`
- `KERNEL32!GetComputerNameW` at `0x14000fc1a`
- `KERNEL32!GetLastError` at `0x14000fc24`
- `KERNEL32!GetLastError` at `0x14000fc24`

## pseudocode

```c
char __fastcall IsQueueLocal(_bstr_t *a1)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  char v4; // bl
  char *v5; // rax
  char *v6; // r9
  __int64 v7; // rdx
  const wchar_t *i; // rcx
  char *v9; // rax
  __int64 v10; // r9
  __int64 v11; // rax
  const wchar_t *v12; // rdx
  const struct _bstr_t::Data_t **v13; // rax
  bool v14; // di
  _bstr_t::Data_t *nSize; // [rsp+20h] [rbp-49h] BYREF
  const struct _bstr_t::Data_t *v17; // [rsp+28h] [rbp-41h] BYREF
  char v18[8]; // [rsp+30h] [rbp-39h] BYREF
  _bstr_t *v19; // [rsp+38h] [rbp-31h]
  char v20[8]; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v21[2]; // [rsp+48h] [rbp-21h] BYREF
  __int64 v22; // [rsp+58h] [rbp-11h]
  unsigned __int64 v23; // [rsp+60h] [rbp-9h]
  WCHAR Buffer[20]; // [rsp+68h] [rbp-1h] BYREF

  v19 = a1;
  v17 = 0;
  memset(Buffer, 0, 32);
  LODWORD(nSize) = 16;
  if ( GetComputerNameW(Buffer, (LPDWORD)&nSize) )
    _bstr_t::operator=((_bstr_t *)&v17, Buffer);
  else
    GetLastError();
  if ( *(_QWORD *)a1 )
    v2 = **(_QWORD **)a1;
  else
    v2 = 0;
  std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(
    v20,
    v2);
  v4 = 1;
  if ( !v22 )
    goto LABEL_22;
  v5 = (char *)v21;
  v3 = v21[0];
  if ( v23 >= 8 )
    v5 = (char *)v21[0];
  v6 = (char *)v21;
  if ( v23 >= 8 )
    v6 = (char *)v21[0];
  while ( 2 )
  {
    if ( v6 < &v5[2 * v22] )
    {
      v7 = 1;
      for ( i = L"\\"; ; ++i )
      {
        if ( !v7 )
          goto LABEL_18;
        if ( *i == *(_WORD *)v6 )
          break;
        --v7;
      }
      if ( !i )
      {
LABEL_18:
        v6 += 2;
        continue;
      }
      v9 = (char *)v21;
      if ( v23 >= 8 )
        v9 = (char *)v21[0];
      v10 = (v6 - v9) >> 1;
    }
    else
    {
LABEL_22:
      v10 = -1;
    }
    break;
  }
  v11 = std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::substr(
          v20,
          Buffer,
          v3,
          v10);
  v12 = (const wchar_t *)(v11 + 8);
  if ( *(_QWORD *)(v11 + 32) >= 8u )
    v12 = *(const wchar_t **)v12;
  _bstr_t::_bstr_t((_bstr_t *)&nSize, v12);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(
    (__int64)Buffer,
    1,
    0);
  v13 = (const struct _bstr_t::Data_t **)_bstr_t::_bstr_t((_bstr_t *)v18, L".");
  v14 = !(unsigned int)_bstr_t::_Compare(&nSize, v13) || !(unsigned int)_bstr_t::_Compare(&nSize, &v17);
  _bstr_t::_Free((_bstr_t *)v18);
  _bstr_t::_Free((_bstr_t *)&nSize);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy((__int64)v20, 1, 0);
  if ( !v14 )
    v4 = 0;
  _bstr_t::_Free((_bstr_t *)&v17);
  _bstr_t::_Free(a1);
  return v4;
}

```

## disassembly

```asm
0x14000fbcc  push    rbp
0x14000fbce  push    rbx
0x14000fbcf  push    rsi
0x14000fbd0  push    rdi
0x14000fbd1  lea     rbp, [rsp-3Fh]
0x14000fbd6  sub     rsp, 0A8h
0x14000fbdd  mov     rax, cs:__security_cookie
0x14000fbe4  xor     rax, rsp
0x14000fbe7  mov     [rbp+57h+var_30], rax
0x14000fbeb  mov     rsi, rcx
0x14000fbee  mov     [rbp+57h+var_88], rcx
0x14000fbf2  mov     [rbp+57h+var_98], 0
0x14000fbfa  xor     eax, eax
0x14000fbfc  mov     [rbp+57h+Buffer], ax
0x14000fc00  xorps   xmm0, xmm0
0x14000fc03  movups  xmmword ptr [rbp+57h+var_56], xmm0
0x14000fc07  movups  xmmword ptr [rbp+57h+var_56+0Eh], xmm0
0x14000fc0b  mov     dword ptr [rbp+57h+nSize], 10h
0x14000fc12  lea     rdx, [rbp+57h+nSize]; nSize
0x14000fc16  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x14000fc1a  call    cs:__imp_GetComputerNameW
0x14000fc20  test    eax, eax
0x14000fc22  jnz     short loc_14000FC2C
0x14000fc24  call    cs:__imp_GetLastError
0x14000fc2a  jmp     short loc_14000FC39
0x14000fc2c  lea     rdx, [rbp+57h+Buffer]
0x14000fc30  lea     rcx, [rbp+57h+var_98]
0x14000fc34  call    ??4_bstr_t@@QEAAAEAV0@PEB_W@Z; _bstr_t::operator=(wchar_t const *)
0x14000fc39  mov     rax, [rsi]
0x14000fc3c  test    rax, rax
0x14000fc3f  jz      short loc_14000FC46
0x14000fc41  mov     rdx, [rax]
0x14000fc44  jmp     short loc_14000FC48
0x14000fc46  xor     edx, edx
0x14000fc48  lea     rcx, [rbp+57h+var_80]
0x14000fc4c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(wchar_t const *)
0x14000fc51  nop
0x14000fc52  mov     ebx, 1
0x14000fc57  mov     rcx, [rbp+57h+var_68]
0x14000fc5b  test    rcx, rcx
0x14000fc5e  jz      short loc_14000FCC5
0x14000fc60  lea     rax, [rbp+57h+var_78]
0x14000fc64  mov     r8, [rbp+57h+var_78]
0x14000fc68  mov     r10, [rbp+57h+var_60]
0x14000fc6c  cmp     r10, 8
0x14000fc70  cmovnb  rax, r8
0x14000fc74  lea     r11, [rax+rcx*2]
0x14000fc78  lea     r9, [rbp+57h+var_78]
0x14000fc7c  cmovnb  r9, r8
0x14000fc80  cmp     r9, r11
0x14000fc83  jnb     short loc_14000FCC5
0x14000fc85  mov     rdx, rbx
0x14000fc88  lea     rcx, asc_140022170; "\\"
0x14000fc8f  test    rdx, rdx
0x14000fc92  jz      short loc_14000FCAB
0x14000fc94  movzx   eax, word ptr [r9]
0x14000fc98  cmp     [rcx], ax
0x14000fc9b  jz      short loc_14000FCA6
0x14000fc9d  add     rcx, 2
0x14000fca1  sub     rdx, rbx
0x14000fca4  jmp     short loc_14000FC8F
0x14000fca6  test    rcx, rcx
0x14000fca9  jnz     short loc_14000FCB1
0x14000fcab  add     r9, 2
0x14000fcaf  jmp     short loc_14000FC80
0x14000fcb1  lea     rax, [rbp+57h+var_78]
0x14000fcb5  cmp     r10, 8
0x14000fcb9  cmovnb  rax, r8
0x14000fcbd  sub     r9, rax
0x14000fcc0  sar     r9, 1
0x14000fcc3  jmp     short loc_14000FCC9
0x14000fcc5  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000fcc9  lea     rdx, [rbp+57h+Buffer]
0x14000fccd  lea     rcx, [rbp+57h+var_80]
0x14000fcd1  call    ?substr@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEBA?AV12@_K0@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::substr(unsigned __int64,unsigned __int64)
0x14000fcd6  nop
0x14000fcd7  lea     rdx, [rax+8]
0x14000fcdb  cmp     qword ptr [rax+20h], 8
0x14000fce0  jb      short loc_14000FCE5
0x14000fce2  mov     rdx, [rdx]; wchar_t *
0x14000fce5  lea     rcx, [rbp+57h+nSize]; this
0x14000fce9  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x14000fcee  nop
0x14000fcef  xor     r8d, r8d
0x14000fcf2  mov     dl, bl
0x14000fcf4  lea     rcx, [rbp+57h+Buffer]
0x14000fcf8  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x14000fcfd  nop
0x14000fcfe  lea     rdx, asc_140022B44; "."
0x14000fd05  lea     rcx, [rbp+57h+var_90]; this
0x14000fd09  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x14000fd0e  mov     rdx, rax; struct _bstr_t *
0x14000fd11  lea     rcx, [rbp+57h+nSize]; this
0x14000fd15  call    ?_Compare@_bstr_t@@AEBAHAEBV1@@Z; _bstr_t::_Compare(_bstr_t const &)
0x14000fd1a  test    eax, eax
0x14000fd1c  jz      short loc_14000FD34
0x14000fd1e  lea     rdx, [rbp+57h+var_98]; struct _bstr_t *
0x14000fd22  lea     rcx, [rbp+57h+nSize]; this
0x14000fd26  call    ?_Compare@_bstr_t@@AEBAHAEBV1@@Z; _bstr_t::_Compare(_bstr_t const &)
0x14000fd2b  test    eax, eax
0x14000fd2d  jz      short loc_14000FD34
0x14000fd2f  xor     dil, dil
0x14000fd32  jmp     short loc_14000FD37
0x14000fd34  mov     dil, bl
0x14000fd37  lea     rcx, [rbp+57h+var_90]; this
0x14000fd3b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14000fd40  nop
0x14000fd41  lea     rcx, [rbp+57h+nSize]; this
0x14000fd45  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14000fd4a  nop
0x14000fd4b  test    dil, dil
0x14000fd4e  jz      short loc_14000FD61
0x14000fd50  xor     r8d, r8d
0x14000fd53  mov     dl, bl
0x14000fd55  lea     rcx, [rbp+57h+var_80]
0x14000fd59  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x14000fd5e  nop
0x14000fd5f  jmp     short loc_14000FD72
0x14000fd61  xor     r8d, r8d
0x14000fd64  mov     dl, bl
0x14000fd66  lea     rcx, [rbp+57h+var_80]
0x14000fd6a  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x14000fd6f  nop
0x14000fd70  xor     bl, bl
0x14000fd72  lea     rcx, [rbp+57h+var_98]; this
0x14000fd76  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14000fd7b  nop
0x14000fd7c  mov     rcx, rsi; this
0x14000fd7f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14000fd84  mov     al, bl
0x14000fd86  mov     rcx, [rbp+57h+var_30]
0x14000fd8a  xor     rcx, rsp; StackCookie
0x14000fd8d  call    __security_check_cookie
0x14000fd92  add     rsp, 0A8h
0x14000fd99  pop     rdi
0x14000fd9a  pop     rsi
0x14000fd9b  pop     rbx
0x14000fd9c  pop     rbp
0x14000fd9d  retn
```
