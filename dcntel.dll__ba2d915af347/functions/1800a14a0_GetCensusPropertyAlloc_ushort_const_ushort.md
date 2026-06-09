# GetCensusPropertyAlloc(ushort const *,ushort * *)

- ea: `0x1800a14a0`
- end: `0x1800a1704`
- name: `?GetCensusPropertyAlloc@@YAJPEBGPEAPEAG@Z`
- size: `612`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008dc0`
- `0x180009240`
- `0x18000962c`
- `0x180009694`
- `0x180009f14`
- `0x1800127f8`
- `0x180014f2c`
- `0x180016748`
- `0x180016db0`
- `0x18002b4f0`
- `0x18009d4e0`
- `0x18009e768`
- `0x1800a14a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800a151f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800a151f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a168a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a168a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a1607`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a1607`

## string_xrefs

- `0x1800a15d6`: `E_ACCESSDENIED`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall GetCensusPropertyAlloc(const unsigned __int16 *a1, LPVOID *a2)
{
  int v4; // ebx
  unsigned __int64 v5; // rsi
  unsigned __int16 *v6; // rax
  wchar_t *v7; // r8
  wchar_t S1[8]; // [rsp+38h] [rbp-270h] BYREF
  __int128 v10; // [rsp+48h] [rbp-260h]
  char *v11[5]; // [rsp+58h] [rbp-250h] BYREF
  _BYTE v12[528]; // [rsp+80h] [rbp-228h] BYREF

  v4 = -2147467259;
  *(_OWORD *)S1 = 0;
  v10 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)S1, &word_1801B4598, 0);
  memset_0(v12, 0, 0x20Au);
  if ( (unsigned int)_o_wcscpy_s(v12, 260, a1) || !a2 )
  {
    v4 = -2147024809;
    std::wstring::~wstring((char **)S1);
  }
  else
  {
    *a2 = 0;
    if ( dword_1802009C8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                       + *(unsigned int *)&tls_index)
                                     + 304LL) )
    {
      Init_thread_header(&dword_1802009C8);
      if ( dword_1802009C8 == -1 )
      {
        CtacProviders::CtacProviders((CtacProviders *)&stru_1802009D0);
        atexit(CtacProviders::GetInstance_::_2_::_dynamic_atexit_destructor_for__singleton__);
        Init_thread_footer(&dword_1802009C8);
      }
    }
    CtacProviders::GetAttribute(&stru_1802009D0);
    std::wstring::operator=(S1, v11);
    std::wstring::~wstring(v11);
    if ( (unsigned __int8)std::operator==<unsigned short>((wchar_t *)L"PROP_NOT_FOUND", S1) )
    {
      v4 = -2147217118;
      std::wstring::~wstring((char **)S1);
    }
    else if ( (unsigned __int8)std::operator==<unsigned short>((wchar_t *)L"E_ACCESSDENIED", S1) )
    {
      v4 = -2147024891;
      std::wstring::~wstring((char **)S1);
    }
    else
    {
      v5 = v10 + 1;
      v6 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v10 + 1));
      *a2 = v6;
      if ( v6 )
      {
        v7 = S1;
        if ( *((_QWORD *)&v10 + 1) > 7u )
          v7 = *(wchar_t **)S1;
        if ( (int)StringCchCopyW(v6, v5, v7) >= 0 )
          v4 = 0;
        std::wstring::~wstring((char **)S1);
        if ( *a2 && v4 < 0 )
        {
          CoTaskMemFree(*a2);
          *a2 = 0;
        }
      }
      else
      {
        v4 = -2147024882;
        std::wstring::~wstring((char **)S1);
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800a14a0  mov     [rsp+arg_10], rbx
0x1800a14a5  mov     [rsp+arg_18], rsi
0x1800a14aa  push    rdi
0x1800a14ab  sub     rsp, 2A0h
0x1800a14b2  mov     rax, cs:__security_cookie
0x1800a14b9  xor     rax, rsp
0x1800a14bc  mov     [rsp+2A8h+var_18], rax
0x1800a14c4  mov     rdi, rdx
0x1800a14c7  mov     rsi, rcx
0x1800a14ca  mov     [rsp+2A8h+var_280], rdx
0x1800a14cf  mov     ebx, 80004005h
0x1800a14d4  xorps   xmm0, xmm0
0x1800a14d7  movups  xmmword ptr [rsp+2A8h+S1], xmm0
0x1800a14dc  xorps   xmm1, xmm1
0x1800a14df  movdqu  [rsp+2A8h+var_260], xmm1
0x1800a14e5  xor     r8d, r8d
0x1800a14e8  lea     rdx, word_1801B4598
0x1800a14ef  lea     rcx, [rsp+2A8h+S1]
0x1800a14f4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800a14f9  nop
0x1800a14fa  xor     edx, edx; Val
0x1800a14fc  mov     r8d, 20Ah; Size
0x1800a1502  lea     rcx, [rsp+2A8h+var_228]; void *
0x1800a150a  call    memset_0
0x1800a150f  mov     r8, rsi
0x1800a1512  mov     edx, 104h
0x1800a1517  lea     rcx, [rsp+2A8h+var_228]
0x1800a151f  call    cs:__imp__o_wcscpy_s
0x1800a1525  test    eax, eax
0x1800a1527  jz      short loc_1800A153E
0x1800a1529  mov     ebx, 80070057h
0x1800a152e  lea     rcx, [rsp+2A8h+S1]
0x1800a1533  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a1538  nop
0x1800a1539  jmp     loc_1800A1697
0x1800a153e  test    rdi, rdi
0x1800a1541  jz      loc_1800A1663
0x1800a1547  mov     qword ptr [rdi], 0
0x1800a154e  mov     ecx, cs:_tls_index
0x1800a1554  mov     rax, gs:58h
0x1800a155d  mov     edx, 130h
0x1800a1562  mov     rax, [rax+rcx*8]
0x1800a1566  mov     ecx, [rdx+rax]
0x1800a1569  cmp     cs:dword_1802009C8, ecx
0x1800a156f  jg      loc_1800A16BE
0x1800a1575  lea     r8, [rsp+2A8h+var_228]
0x1800a157d  lea     rdx, [rsp+2A8h+var_250]
0x1800a1582  lea     rcx, stru_1802009D0; SRWLock
0x1800a1589  call    ?GetAttribute@CtacProviders@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; CtacProviders::GetAttribute(ushort const *)
0x1800a158e  lea     rdx, [rsp+2A8h+var_250]
0x1800a1593  lea     rcx, [rsp+2A8h+S1]
0x1800a1598  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800a159d  lea     rcx, [rsp+2A8h+var_250]
0x1800a15a2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a15a7  lea     rdx, [rsp+2A8h+S1]; S1
0x1800a15ac  lea     rcx, aPropNotFound; "PROP_NOT_FOUND"
0x1800a15b3  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NQEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator==<ushort>(ushort const * const,std::wstring const &)
0x1800a15b8  test    al, al
0x1800a15ba  jz      short loc_1800A15D1
0x1800a15bc  mov     ebx, 80041122h
0x1800a15c1  lea     rcx, [rsp+2A8h+S1]
0x1800a15c6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a15cb  nop
0x1800a15cc  jmp     loc_1800A1697
0x1800a15d1  lea     rdx, [rsp+2A8h+S1]; S1
0x1800a15d6  lea     rcx, aEAccessdenied; "E_ACCESSDENIED"
0x1800a15dd  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NQEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator==<ushort>(ushort const * const,std::wstring const &)
0x1800a15e2  test    al, al
0x1800a15e4  jz      short loc_1800A15FB
0x1800a15e6  mov     ebx, 80070005h
0x1800a15eb  lea     rcx, [rsp+2A8h+S1]
0x1800a15f0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a15f5  nop
0x1800a15f6  jmp     loc_1800A1697
0x1800a15fb  mov     rsi, qword ptr [rsp+2A8h+var_260]
0x1800a1600  inc     rsi
0x1800a1603  lea     rcx, [rsi+rsi]; cb
0x1800a1607  call    cs:__imp_CoTaskMemAlloc
0x1800a160d  mov     [rdi], rax
0x1800a1610  test    rax, rax
0x1800a1613  jnz     short loc_1800A1627
0x1800a1615  mov     ebx, 8007000Eh
0x1800a161a  lea     rcx, [rsp+2A8h+S1]
0x1800a161f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a1624  nop
0x1800a1625  jmp     short loc_1800A1697
0x1800a1627  lea     r8, [rsp+2A8h+S1]
0x1800a162c  cmp     qword ptr [rsp+2A8h+var_260+8], 7
0x1800a1632  cmova   r8, qword ptr [rsp+2A8h+S1]; unsigned __int16 *
0x1800a1638  mov     rdx, rsi; unsigned __int64
0x1800a163b  mov     rcx, rax; unsigned __int16 *
0x1800a163e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a1643  test    eax, eax
0x1800a1645  jns     short loc_1800A1654
0x1800a1647  lea     rcx, [rsp+2A8h+S1]
0x1800a164c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a1651  nop
0x1800a1652  jmp     short loc_1800A167E
0x1800a1654  xor     ebx, ebx
0x1800a1656  lea     rcx, [rsp+2A8h+S1]
0x1800a165b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a1660  nop
0x1800a1661  jmp     short loc_1800A167E
0x1800a1663  mov     ebx, 80070057h
0x1800a1668  lea     rcx, [rsp+2A8h+S1]
0x1800a166d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a1672  nop
0x1800a1673  jmp     short loc_1800A1697
0x1800a1675  mov     rdi, [rsp+2A8h+var_280]
0x1800a167a  mov     ebx, [rsp+2A8h+var_288]
0x1800a167e  mov     rcx, [rdi]; pv
0x1800a1681  test    rcx, rcx
0x1800a1684  jz      short loc_1800A1697
0x1800a1686  test    ebx, ebx
0x1800a1688  jns     short loc_1800A1697
0x1800a168a  call    cs:__imp_CoTaskMemFree
0x1800a1690  mov     qword ptr [rdi], 0
0x1800a1697  mov     eax, ebx
0x1800a1699  mov     rcx, [rsp+2A8h+var_18]
0x1800a16a1  xor     rcx, rsp; StackCookie
0x1800a16a4  call    __security_check_cookie
0x1800a16a9  lea     r11, [rsp+2A8h+var_8]
0x1800a16b1  mov     rbx, [r11+20h]
0x1800a16b5  mov     rsi, [r11+28h]
0x1800a16b9  mov     rsp, r11
0x1800a16bc  pop     rdi
0x1800a16bd  retn
0x1800a16be  lea     rcx, dword_1802009C8
0x1800a16c5  call    _Init_thread_header
0x1800a16ca  cmp     cs:dword_1802009C8, 0FFFFFFFFh
0x1800a16d1  jnz     loc_1800A1575
0x1800a16d7  lea     rcx, stru_1802009D0; this
0x1800a16de  call    ??0CtacProviders@@AEAA@XZ; CtacProviders::CtacProviders(void)
0x1800a16e3  lea     rcx, _CtacProviders__GetInstance____2____dynamic_atexit_destructor_for__singleton__; void (__cdecl *)()
0x1800a16ea  call    atexit
0x1800a16ef  nop
0x1800a16f0  lea     rcx, dword_1802009C8
0x1800a16f7  call    _Init_thread_footer
0x1800a16fc  nop
0x1800a16fd  jmp     loc_1800A1575
```
