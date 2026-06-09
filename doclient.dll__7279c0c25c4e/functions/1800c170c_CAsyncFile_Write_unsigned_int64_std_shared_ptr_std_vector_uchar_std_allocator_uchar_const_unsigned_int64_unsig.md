# CAsyncFile::Write(unsigned __int64,std::shared_ptr<std::vector<uchar,std::allocator<uchar>>> const &,unsigned __int64,unsigned __int64,std::function<void (COverlappedFileOp const *,long)> const &)

- ea: `0x1800c170c`
- end: `0x1800c1a66`
- name: `?Write@CAsyncFile@@QEAAJ_KAEBV?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@00AEBV?$function@$$A6AXPEBVCOverlappedFileOp@@J@Z@3@@Z`
- size: `858`
- prototype: `__int64 __usercall@<rax>(CAsyncFile *this@<rcx>, __int64, __int64)`
- caller_count: `4`
- callee_count: `12`
- tags: ``

## callers

- `0x180057134`
- `0x180057964`
- `0x1800f3890`
- `0x1800f452c`

## callees

- `0x1800196f0`
- `0x1800236f0`
- `0x180023bd4`
- `0x1800a1ea4`
- `0x1800a6e58`
- `0x1800c0f20`
- `0x1800c170c`
- `0x1800c1f8c`
- `0x1800c211c`
- `0x1800f82f0`
- `0x1800f8320`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c1771`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c1a0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c1771`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c1a0c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800c177f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800c1a1a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800c177f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800c1a1a`

## string_xrefs

- `0x1800c18e1`: `CAsyncFile::Write`
- `0x1800c18d4`: `CFile::Write failed with resource fault = %x, sleeping for %u ms before trying again`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CAsyncFile::Write(
        CAsyncFile *this,
        __int64 a2,
        _QWORD **a3,
        const char *a4,
        unsigned __int64 a5,
        __int64 a6)
{
  int v7; // r13d
  char v8; // bl
  HANDLE CurrentThread; // rax
  unsigned int v10; // r15d
  _DWORD *v11; // rdi
  struct COverlappedFileOp *v12; // rdi
  int v13; // eax
  unsigned int v14; // esi
  unsigned int v15; // eax
  int v16; // ecx
  _QWORD *v17; // rax
  volatile signed __int32 *v18; // rdi
  __int64 v19; // rcx
  volatile signed __int32 *v20; // rdi
  HANDLE v21; // rax
  __int64 result; // rax
  struct COverlappedFileOp *v23[2]; // [rsp+48h] [rbp-A0h] BYREF
  _QWORD **v24; // [rsp+58h] [rbp-90h]
  __int64 v25; // [rsp+60h] [rbp-88h]
  __int64 v26; // [rsp+68h] [rbp-80h]
  _QWORD v27[2]; // [rsp+70h] [rbp-78h] BYREF
  int v28; // [rsp+80h] [rbp-68h]
  __int64 v29; // [rsp+88h] [rbp-60h]
  struct COverlappedFileOp *v30; // [rsp+90h] [rbp-58h]
  char v31[8]; // [rsp+98h] [rbp-50h] BYREF
  char *v32; // [rsp+A0h] [rbp-48h] BYREF
  __int64 v33; // [rsp+A8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v32 = (char *)a4;
  v24 = a3;
  v26 = a2;
  v25 = a6;
  v7 = 0;
  LODWORD(v33) = 0;
  v8 = *((_BYTE *)this + 44) & 1;
  if ( v8 )
  {
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, 0x10000);
  }
  try
  {
    if ( a5 > 0xFFFFFFFF )
    {
      v14 = -2147024362;
    }
    else
    {
      v10 = 0;
      while ( 1 )
      {
        v11 = operator new(0xA0u);
        v33 = (__int64)v11;
        v11[2] = 1;
        v11[3] = 1;
        *(_QWORD *)v11 = &std::_Ref_count_obj2<COverlappedFileOp>::`vftable';
        COverlappedFileOp::COverlappedFileOp((_DWORD)v11 + 16, v26, (_DWORD)v24, a5, (__int64)this, 0, v25);
        v7 |= 1u;
        v23[0] = (struct COverlappedFileOp *)(v11 + 4);
        v23[1] = (struct COverlappedFileOp *)v11;
        CAsyncFile::_AddPending(this, v23);
        v27[0] = this;
        v27[1] = &v32[**v24];
        v28 = a5;
        v29 = 0;
        v12 = v23[0];
        v30 = v23[0];
        v13 = CFile::_InvokeFileMethod__CFile::Write_::_2_::_lambda_1___(this, v27);
        v14 = v13;
        if ( v13 >= 0 )
          break;
        if ( v13 != -2147024888
          && v13 != -2147023766
          && ((v15 = v13 + 2147023446, v15 > 5) || (v16 = 41, !_bittest(&v16, v15)))
          && v14 != -2147023080
          && v14 != -2147024875
          || (++v10, v10 >= 3) )
        {
          if ( *((_QWORD *)v12 + 17) )
          {
            LODWORD(v33) = v14;
            v32 = (char *)v12;
            v19 = *((_QWORD *)v12 + 17);
            if ( !v19 )
              std::_Xbad_function_call();
            (*(void (__fastcall **)(__int64, char **, __int64 *))(*(_QWORD *)v19 + 16LL))(v19, &v32, &v33);
          }
          v14 = 0;
          CAsyncFile::_RemovePending(this, v12);
          break;
        }
        CAsyncFile::_RemovePending(this, v12);
        LogMessage(
          3u,
          "CAsyncFile::Write",
          0x9Eu,
          "CFile::Write failed with resource fault = %x, sleeping for %u ms before trying again",
          v14,
          5000);
        v33 = 5000;
        v17 = (_QWORD *)std::_To_absolute_time<__int64,std::ratio<1,1000>>(v31, &v33);
        std::this_thread::sleep_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(v17);
        v18 = (volatile signed __int32 *)v23[1];
        if ( v23[1] && _InterlockedExchangeAdd((volatile signed __int32 *)v23[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
          if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
        }
      }
      v20 = (volatile signed __int32 *)v23[1];
      if ( v23[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v23[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
          if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
        }
      }
    }
    if ( v8 )
    {
      v21 = GetCurrentThread();
      SetThreadPriority(v21, 0x20000);
    }
    result = v14;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xAE,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\AsyncFile.cpp",
                           a4);
  }
  return result;
}

```

## disassembly

```asm
0x1800c170c  mov     [rsp+arg_8], rbx
0x1800c1711  mov     [rsp+arg_18], rsi
0x1800c1716  push    rdi
0x1800c1717  push    r12
0x1800c1719  push    r13
0x1800c171b  push    r14
0x1800c171d  push    r15
0x1800c171f  sub     rsp, 0C0h
0x1800c1726  mov     rax, cs:__security_cookie
0x1800c172d  xor     rax, rsp
0x1800c1730  mov     [rsp+0E8h+var_38], rax
0x1800c1738  mov     [rsp+0E8h+var_48], r9
0x1800c1740  mov     [rsp+0E8h+var_90], r8
0x1800c1745  mov     [rsp+0E8h+var_80], rdx
0x1800c174a  mov     r14, rcx
0x1800c174d  mov     rax, [rsp+0E8h+arg_28]
0x1800c1755  mov     [rsp+0E8h+var_88], rax
0x1800c175a  xor     r13d, r13d
0x1800c175d  mov     dword ptr [rsp+0E8h+var_40], r13d
0x1800c1765  mov     bl, [rcx+2Ch]
0x1800c1768  and     bl, 1
0x1800c176b  mov     [rsp+0E8h+var_A8], bl
0x1800c176f  jz      short loc_1800C1786
0x1800c1771  call    cs:__imp_GetCurrentThread
0x1800c1777  mov     rcx, rax; hThread
0x1800c177a  mov     edx, 10000h; nPriority
0x1800c177f  call    cs:__imp_SetThreadPriority
0x1800c1785  nop
0x1800c1786  mov     eax, 0FFFFFFFFh
0x1800c178b  mov     r12, [rsp+0E8h+arg_20]
0x1800c1793  cmp     r12, rax
0x1800c1796  ja      loc_1800C1A03
0x1800c179c  xor     r15d, r15d
0x1800c179f  mov     ecx, 0A0h; Size
0x1800c17a4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c17a9  mov     rdi, rax
0x1800c17ac  mov     [rsp+0E8h+var_40], rax
0x1800c17b4  mov     dword ptr [rax+8], 1
0x1800c17bb  mov     dword ptr [rax+0Ch], 1
0x1800c17c2  lea     rax, ??_7?$_Ref_count_obj2@VCOverlappedFileOp@@@std@@6B@; const std::_Ref_count_obj2<COverlappedFileOp>::`vftable'
0x1800c17c9  mov     [rdi], rax
0x1800c17cc  lea     rsi, [rdi+10h]
0x1800c17d0  mov     r9d, r12d
0x1800c17d3  mov     rax, [rsp+0E8h+var_88]
0x1800c17d8  mov     [rsp+0E8h+var_B8], rax
0x1800c17dd  mov     [rsp+0E8h+var_C0], 0
0x1800c17e6  mov     [rsp+0E8h+var_C8], r14
0x1800c17eb  mov     r8, [rsp+0E8h+var_90]
0x1800c17f0  mov     rdx, [rsp+0E8h+var_80]
0x1800c17f5  mov     rcx, rsi
0x1800c17f8  call    ??0COverlappedFileOp@@QEAA@_KAEBV?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@0PEBX2AEBV?$function@$$A6AXPEBVCOverlappedFileOp@@J@Z@2@@Z; COverlappedFileOp::COverlappedFileOp(unsigned __int64,std::shared_ptr<std::vector<uchar>> const &,unsigned __int64,void const *,void const *,std::function<void (COverlappedFileOp const *,long)> const &)
0x1800c17fd  nop
0x1800c17fe  xorps   xmm0, xmm0
0x1800c1801  movups  xmmword ptr [rsp+0E8h+var_A0], xmm0
0x1800c1806  or      r13d, 1
0x1800c180a  mov     [rsp+0E8h+var_A0], rsi
0x1800c180f  mov     [rsp+0E8h+var_A0+8], rdi
0x1800c1814  lea     rdx, [rsp+0E8h+var_A0]
0x1800c1819  mov     rcx, r14
0x1800c181c  call    ?_AddPending@CAsyncFile@@AEAAXAEBV?$shared_ptr@VCOverlappedFileOp@@@std@@@Z; CAsyncFile::_AddPending(std::shared_ptr<COverlappedFileOp> const &)
0x1800c1821  mov     [rsp+0E8h+var_78], r14
0x1800c1826  mov     rax, [rsp+0E8h+var_90]
0x1800c182b  mov     rax, [rax]
0x1800c182e  mov     rcx, [rax]
0x1800c1831  mov     rax, [rsp+0E8h+var_48]
0x1800c1839  add     rax, rcx
0x1800c183c  mov     [rsp+0E8h+var_70], rax
0x1800c1841  mov     [rsp+0E8h+var_68], r12d
0x1800c1849  mov     [rsp+0E8h+var_60], 0
0x1800c1855  mov     rdi, [rsp+0E8h+var_A0]
0x1800c185a  mov     [rsp+0E8h+var_58], rdi
0x1800c1862  lea     rdx, [rsp+0E8h+var_78]
0x1800c1867  mov     rcx, r14
0x1800c186a  call    CFile___InvokeFileMethod__CFile__Write____2____lambda_1___
0x1800c186f  mov     esi, eax
0x1800c1871  test    eax, eax
0x1800c1873  jns     loc_1800C19BC
0x1800c1879  cmp     eax, 80070008h
0x1800c187e  jz      short loc_1800C18AF
0x1800c1880  cmp     eax, 8007046Ah
0x1800c1885  jz      short loc_1800C18AF
0x1800c1887  add     eax, 7FF8FA56h
0x1800c188c  cmp     eax, 5
0x1800c188f  ja      short loc_1800C189B
0x1800c1891  mov     ecx, 29h ; ')'
0x1800c1896  bt      ecx, eax
0x1800c1899  jb      short loc_1800C18AF
0x1800c189b  cmp     esi, 80070718h
0x1800c18a1  jz      short loc_1800C18AF
0x1800c18a3  cmp     esi, 80070015h
0x1800c18a9  jnz     loc_1800C1969
0x1800c18af  inc     r15d
0x1800c18b2  cmp     r15d, 3
0x1800c18b6  jnb     loc_1800C1969
0x1800c18bc  mov     rdx, rdi; struct COverlappedFileOp *
0x1800c18bf  mov     rcx, r14; this
0x1800c18c2  call    ?_RemovePending@CAsyncFile@@AEAAXPEAVCOverlappedFileOp@@@Z; CAsyncFile::_RemovePending(COverlappedFileOp *)
0x1800c18c7  mov     edi, 1388h
0x1800c18cc  mov     dword ptr [rsp+0E8h+var_C0], edi
0x1800c18d0  mov     dword ptr [rsp+0E8h+var_C8], esi
0x1800c18d4  lea     r9, aCfileWriteFail; "CFile::Write failed with resource fault"...
0x1800c18db  mov     r8d, 9Eh; unsigned int
0x1800c18e1  lea     rdx, aCasyncfileWrit; "CAsyncFile::Write"
0x1800c18e8  mov     ecx, 3; unsigned __int8
0x1800c18ed  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800c18f2  mov     [rsp+0E8h+var_40], rdi
0x1800c18fa  lea     rdx, [rsp+0E8h+var_40]
0x1800c1902  lea     rcx, [rsp+0E8h+var_50]
0x1800c190a  call    ??$_To_absolute_time@_JU?$ratio@$00$0DOI@@std@@@std@@YA?A_PAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@0@@Z
0x1800c190f  mov     rcx, rax
0x1800c1912  call    ??$sleep_until@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@this_thread@std@@YAXAEBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@1@@Z; std::this_thread::sleep_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const &)
0x1800c1917  nop
0x1800c1918  mov     rdi, [rsp+0E8h+var_A0+8]
0x1800c191d  test    rdi, rdi
0x1800c1920  jz      loc_1800C179F
0x1800c1926  or      esi, 0FFFFFFFFh
0x1800c1929  mov     eax, esi
0x1800c192b  lock xadd [rdi+8], eax
0x1800c1930  add     eax, esi
0x1800c1932  jnz     loc_1800C179F
0x1800c1938  mov     rax, [rdi]
0x1800c193b  mov     rcx, rdi
0x1800c193e  mov     rax, [rax]
0x1800c1941  call    _guard_dispatch_icall
0x1800c1946  mov     eax, esi
0x1800c1948  lock xadd [rdi+0Ch], eax
0x1800c194d  add     eax, esi
0x1800c194f  jnz     loc_1800C179F
0x1800c1955  mov     rax, [rdi]
0x1800c1958  mov     rcx, rdi
0x1800c195b  mov     rax, [rax+8]
0x1800c195f  call    _guard_dispatch_icall
0x1800c1964  jmp     loc_1800C179F
0x1800c1969  cmp     qword ptr [rdi+88h], 0
0x1800c1971  jz      short loc_1800C19AE
0x1800c1973  mov     dword ptr [rsp+0E8h+var_40], esi
0x1800c197a  mov     [rsp+0E8h+var_48], rdi
0x1800c1982  mov     rcx, [rdi+88h]
0x1800c1989  test    rcx, rcx
0x1800c198c  jz      loc_1800C1A5F
0x1800c1992  mov     rax, [rcx]
0x1800c1995  lea     r8, [rsp+0E8h+var_40]
0x1800c199d  lea     rdx, [rsp+0E8h+var_48]
0x1800c19a5  mov     rax, [rax+10h]
0x1800c19a9  call    _guard_dispatch_icall
0x1800c19ae  xor     esi, esi
0x1800c19b0  mov     rdx, rdi; struct COverlappedFileOp *
0x1800c19b3  mov     rcx, r14; this
0x1800c19b6  call    ?_RemovePending@CAsyncFile@@AEAAXPEAVCOverlappedFileOp@@@Z; CAsyncFile::_RemovePending(COverlappedFileOp *)
0x1800c19bb  nop
0x1800c19bc  mov     rdi, [rsp+0E8h+var_A0+8]
0x1800c19c1  test    rdi, rdi
0x1800c19c4  jz      short loc_1800C1A08
0x1800c19c6  or      r14d, 0FFFFFFFFh
0x1800c19ca  mov     eax, r14d
0x1800c19cd  lock xadd [rdi+8], eax
0x1800c19d2  add     eax, r14d
0x1800c19d5  jnz     short loc_1800C1A08
0x1800c19d7  mov     rax, [rdi]
0x1800c19da  mov     rcx, rdi
0x1800c19dd  mov     rax, [rax]
0x1800c19e0  call    _guard_dispatch_icall
0x1800c19e5  mov     eax, r14d
0x1800c19e8  lock xadd [rdi+0Ch], eax
0x1800c19ed  add     eax, r14d
0x1800c19f0  jnz     short loc_1800C1A08
0x1800c19f2  mov     rax, [rdi]
0x1800c19f5  mov     rcx, rdi
0x1800c19f8  mov     rax, [rax+8]
0x1800c19fc  call    _guard_dispatch_icall
0x1800c1a01  jmp     short loc_1800C1A08
0x1800c1a03  mov     esi, 80070216h
0x1800c1a08  test    bl, bl
0x1800c1a0a  jz      short loc_1800C1A20
0x1800c1a0c  call    cs:__imp_GetCurrentThread
0x1800c1a12  mov     rcx, rax; hThread
0x1800c1a15  mov     edx, 20000h; nPriority
0x1800c1a1a  call    cs:__imp_SetThreadPriority
0x1800c1a20  mov     eax, esi
0x1800c1a22  jmp     short loc_1800C1A32
0x1800c1a24  mov     eax, dword ptr [rsp+0E8h+var_40]
0x1800c1a2b  jmp     short loc_1800C1A32
0x1800c1a2d  mov     eax, 8007000Eh
0x1800c1a32  mov     rcx, [rsp+0E8h+var_38]
0x1800c1a3a  xor     rcx, rsp; StackCookie
0x1800c1a3d  call    __security_check_cookie
0x1800c1a42  lea     r11, [rsp+0E8h+var_28]
0x1800c1a4a  mov     rbx, [r11+38h]
0x1800c1a4e  mov     rsi, [r11+48h]
0x1800c1a52  mov     rsp, r11
0x1800c1a55  pop     r15
0x1800c1a57  pop     r14
0x1800c1a59  pop     r13
0x1800c1a5b  pop     r12
0x1800c1a5d  pop     rdi
0x1800c1a5e  retn
0x1800c1a5f  call    ?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
```
