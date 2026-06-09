# CHttpWriter::CheckIfRedirection(void)

- ea: `0x1800bc9d8`
- end: `0x1800bcdc1`
- name: `?CheckIfRedirection@CHttpWriter@@AEAAHXZ`
- size: `1001`
- prototype: `__int64 __fastcall(CHttpWriter *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800bd5c8`

## callees

- `0x180006640`
- `0x180008cc0`
- `0x18000c7d0`
- `0x18001d7f0`
- `0x1800548e4`
- `0x18006c7f8`
- `0x18006c888`
- `0x18009c858`
- `0x1800a7558`
- `0x1800bc9d8`
- `0x1800be794`
- `0x1800bf1cc`
- `0x1800c12b4`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bcc09`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bcc09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bcad3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bcc34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bcd02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bcad3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bcc34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bcd02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bca18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bca23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bca2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bca35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcaf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcb1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcb29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcb31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcc57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcd1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bca18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bca23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bca2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bca35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcaf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcb1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcb29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcb31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcc57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcd1e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bcd94`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bcd94`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CHttpWriter::CheckIfRedirection(CHttpWriter *this)
{
  unsigned int LastError; // eax
  void *v3; // rdi
  DWORD v4; // eax
  unsigned int v5; // eax
  LPVOID v6; // r10
  __int64 v7; // r14
  unsigned int v8; // edx
  DWORD v9; // eax
  unsigned int v11; // edx
  URL_INFO *v12; // rcx
  DWORD v13; // eax
  void **pExceptionObject; // [rsp+40h] [rbp-29h] BYREF
  __int128 v15; // [rsp+48h] [rbp-21h]
  unsigned int v16; // [rsp+58h] [rbp-11h]
  int v17; // [rsp+5Ch] [rbp-Dh]
  int v18; // [rsp+60h] [rbp-9h]
  unsigned int v19; // [rsp+D0h] [rbp+67h] BYREF
  __int64 v20; // [rsp+D8h] [rbp+6Fh] BYREF
  LPVOID v21; // [rsp+E0h] [rbp+77h]

  v19 = 0;
  (*(void (__fastcall **)(_QWORD, __int64, _QWORD, unsigned int *))(***((_QWORD ***)this + 89) + 24LL))(
    **((_QWORD **)this + 89),
    34,
    0,
    &v19);
  if ( GetLastError() != 122 )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80070000;
    else
      LastError = GetLastError();
    v15 = 0;
    pExceptionObject = &ComError::`vftable';
    v16 = LastError;
    v17 = 6851;
    v18 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v3 = operator new(saturated_mul((unsigned __int64)v19 >> 1, 2u));
  if ( !(*(unsigned int (__fastcall **)(_QWORD, __int64, void *, unsigned int *))(***((_QWORD ***)this + 89) + 24LL))(
          **((_QWORD **)this + 89),
          34,
          v3,
          &v19) )
  {
    if ( v3
      && !HeapFree(hBitsHeap, 0, v3)
      && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v4 = GetLastError();
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, v3, v4);
    }
    if ( (int)GetLastError() > 0 )
      v5 = (unsigned __int16)GetLastError() | 0x80070000;
    else
      v5 = GetLastError();
    v15 = 0;
    pExceptionObject = &ComError::`vftable';
    v16 = v5;
    v17 = 6864;
    v18 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v20 = GenericStringHandle<unsigned short>::NewString(v3);
  v6 = operator new(0x470u);
  v21 = v6;
  if ( v6 )
    v7 = URL_INFO::URL_INFO(
           (__int64)v6,
           (__int64)&v20,
           (__int64)this + 648,
           *((_QWORD *)this + 94),
           (__int64)this + ((*((_DWORD *)this + 282) & 2) != 0 ? 1120LL : 1112LL),
           *((_DWORD *)this + 347),
           *((_BYTE *)this + 1392),
           0);
  else
    v7 = 0;
  if ( (unsigned int)_o__wcsicmp(*(_QWORD *)(v7 + 1120), *(_QWORD *)(*((_QWORD *)this + 88) + 1120LL)) )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_qSS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        215,
        (unsigned int)&WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids,
        (_DWORD)this,
        *((_QWORD *)this + 13) + 12LL,
        (__int64)v3);
    URL_INFO::Cleanup(*((URL_INFO **)this + 88));
    v12 = (URL_INFO *)*((_QWORD *)this + 88);
    if ( v12 )
      URL_INFO::`scalar deleting destructor'(v12, v11);
    if ( v3
      && !HeapFree(hBitsHeap, 0, v3)
      && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v13 = GetLastError();
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, v3, v13);
    }
    *((_QWORD *)this + 88) = v7;
    URL_INFO::Connect(
      (const WCHAR **)v7,
      *((struct IHttpInterface **)this + 80),
      (CHttpWriter *)((char *)this + 648),
      (struct _RTL_CRITICAL_SECTION *)((char *)this + 952),
      *((_BYTE *)this + 632));
    if ( URL_INFO::NeedsProxyDetection(*((URL_INFO **)this + 88)) )
    {
      CHttpWriter::IncrementPendingAsyncOpsCount(this);
      SubmitThreadpoolWork(*((PTP_WORK *)this + 175));
    }
    else
    {
      CHttpWriter::RecalcProxyStats(this);
      *((_BYTE *)this + 56) = 1;
    }
    GenericStringHandle<unsigned short>::FreeIt(&v20);
    return 1;
  }
  else
  {
    URL_INFO::Cleanup((URL_INFO *)v7);
    URL_INFO::`scalar deleting destructor'((URL_INFO *)v7, v8);
    if ( v3
      && !HeapFree(hBitsHeap, 0, v3)
      && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v9 = GetLastError();
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, v3, v9);
    }
    GenericStringHandle<unsigned short>::FreeIt(&v20);
    return 0;
  }
}

```

## disassembly

```asm
0x1800bc9d8  push    rbp
0x1800bc9da  push    rbx
0x1800bc9db  push    rsi
0x1800bc9dc  push    rdi
0x1800bc9dd  push    r14
0x1800bc9df  lea     rbp, [rsp-37h]
0x1800bc9e4  sub     rsp, 0A0h
0x1800bc9eb  mov     rbx, rcx
0x1800bc9ee  mov     [rbp+57h+arg_0], 0
0x1800bc9f5  mov     rax, [rcx+2C8h]
0x1800bc9fc  mov     rcx, [rax]
0x1800bc9ff  mov     rax, [rcx]
0x1800bca02  lea     r9, [rbp+57h+arg_0]
0x1800bca06  xor     r8d, r8d
0x1800bca09  lea     esi, [r8+22h]
0x1800bca0d  mov     edx, esi
0x1800bca0f  mov     rax, [rax+18h]
0x1800bca13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bca18  call    cs:__imp_GetLastError
0x1800bca1e  cmp     eax, 7Ah ; 'z'
0x1800bca21  jz      short loc_1800BCA77
0x1800bca23  call    cs:__imp_GetLastError
0x1800bca29  test    eax, eax
0x1800bca2b  jg      short loc_1800BCA35
0x1800bca2d  call    cs:__imp_GetLastError
0x1800bca33  jmp     short loc_1800BCA43
0x1800bca35  call    cs:__imp_GetLastError
0x1800bca3b  movzx   eax, ax
0x1800bca3e  or      eax, 80070000h
0x1800bca43  xorps   xmm0, xmm0
0x1800bca46  movups  [rbp+57h+var_78], xmm0
0x1800bca4a  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800bca51  mov     [rbp+57h+pExceptionObject], rcx
0x1800bca55  mov     [rbp+57h+var_68], eax
0x1800bca58  mov     [rbp+57h+var_64], 1AC3h
0x1800bca5f  mov     [rbp+57h+var_60], 1
0x1800bca66  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800bca6d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800bca71  call    _CxxThrowException_0
0x1800bca77  mov     ecx, [rbp+57h+arg_0]
0x1800bca7a  shr     rcx, 1
0x1800bca7d  mov     eax, 2
0x1800bca82  mul     rcx
0x1800bca85  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800bca8c  cmovb   rax, rcx
0x1800bca90  mov     rcx, rax; dwBytes
0x1800bca93  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bca98  mov     rdi, rax
0x1800bca9b  mov     rcx, [rbx+2C8h]
0x1800bcaa2  mov     rcx, [rcx]
0x1800bcaa5  mov     r8, [rcx]
0x1800bcaa8  mov     rax, [r8+18h]
0x1800bcaac  lea     r9, [rbp+57h+arg_0]
0x1800bcab0  mov     r8, rdi
0x1800bcab3  mov     edx, esi
0x1800bcab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcaba  test    eax, eax
0x1800bcabc  jnz     loc_1800BCB73
0x1800bcac2  test    rdi, rdi
0x1800bcac5  jz      short loc_1800BCB1F
0x1800bcac7  mov     r8, rdi; lpMem
0x1800bcaca  xor     edx, edx; dwFlags
0x1800bcacc  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x1800bcad3  call    cs:__imp_HeapFree
0x1800bcad9  test    eax, eax
0x1800bcadb  jnz     short loc_1800BCB1F
0x1800bcadd  lea     rsi, WPP_GLOBAL_Control
0x1800bcae4  mov     rax, cs:WPP_GLOBAL_Control
0x1800bcaeb  cmp     rax, rsi
0x1800bcaee  jz      short loc_1800BCB1F
0x1800bcaf0  test    byte ptr [rax+1Ch], 4
0x1800bcaf4  jz      short loc_1800BCB1F
0x1800bcaf6  call    cs:__imp_GetLastError
0x1800bcafc  mov     edx, 0Bh
0x1800bcb01  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800bcb05  mov     r9, rdi
0x1800bcb08  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x1800bcb0f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcb16  mov     rcx, [rcx+10h]
0x1800bcb1a  call    WPP_SF_qD
0x1800bcb1f  call    cs:__imp_GetLastError
0x1800bcb25  test    eax, eax
0x1800bcb27  jg      short loc_1800BCB31
0x1800bcb29  call    cs:__imp_GetLastError
0x1800bcb2f  jmp     short loc_1800BCB3F
0x1800bcb31  call    cs:__imp_GetLastError
0x1800bcb37  movzx   eax, ax
0x1800bcb3a  or      eax, 80070000h
0x1800bcb3f  xorps   xmm0, xmm0
0x1800bcb42  movups  [rbp+57h+var_78], xmm0
0x1800bcb46  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800bcb4d  mov     [rbp+57h+pExceptionObject], rcx
0x1800bcb51  mov     [rbp+57h+var_68], eax
0x1800bcb54  mov     [rbp+57h+var_64], 1AD0h
0x1800bcb5b  mov     [rbp+57h+var_60], 1
0x1800bcb62  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800bcb69  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800bcb6d  call    _CxxThrowException_0
0x1800bcb73  mov     rcx, rdi
0x1800bcb76  call    ?NewString@?$GenericStringHandle@G@@CAPEAUStringData@1@PEBG@Z; GenericStringHandle<ushort>::NewString(ushort const *)
0x1800bcb7b  mov     [rbp+57h+arg_8], rax
0x1800bcb7f  mov     ecx, 470h; dwBytes
0x1800bcb84  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bcb89  mov     r10, rax
0x1800bcb8c  mov     [rbp+57h+arg_10], rax
0x1800bcb90  test    rax, rax
0x1800bcb93  jz      short loc_1800BCBF1
0x1800bcb95  mov     ecx, [rbx+468h]
0x1800bcb9b  and     cl, 2
0x1800bcb9e  neg     cl
0x1800bcba0  sbb     rdx, rdx
0x1800bcba3  and     edx, 8
0x1800bcba6  add     rdx, 458h
0x1800bcbad  add     rdx, rbx
0x1800bcbb0  lea     r8, [rbx+288h]; int
0x1800bcbb7  mov     [rsp+0C0h+var_88], 0; unsigned __int16 *
0x1800bcbc0  mov     al, [rbx+570h]
0x1800bcbc6  mov     [rsp+0C0h+var_90], al; char
0x1800bcbca  mov     eax, [rbx+56Ch]
0x1800bcbd0  mov     [rsp+0C0h+var_98], eax; int
0x1800bcbd4  mov     qword ptr [rsp+0C0h+var_A0], rdx; __int64
0x1800bcbd9  mov     r9, [rbx+2F0h]; int
0x1800bcbe0  lea     rdx, [rbp+57h+arg_8]; int
0x1800bcbe4  mov     rcx, r10; int
0x1800bcbe7  call    ??0URL_INFO@@QEAA@AEBV?$GenericStringHandle@G@@AEBUHttpSecurityData@@PEBUPROXY_SETTINGS@@AEBVTokenHandle@@K_NPEBG@Z; URL_INFO::URL_INFO(GenericStringHandle<ushort> const &,HttpSecurityData const &,PROXY_SETTINGS const *,TokenHandle const &,ulong,bool,ushort const *)
0x1800bcbec  mov     r14, rax
0x1800bcbef  jmp     short loc_1800BCBF4
0x1800bcbf1  xor     r14d, r14d
0x1800bcbf4  mov     rdx, [rbx+2C0h]
0x1800bcbfb  mov     rdx, [rdx+460h]
0x1800bcc02  mov     rcx, [r14+460h]
0x1800bcc09  call    cs:__imp__o__wcsicmp
0x1800bcc0f  test    eax, eax
0x1800bcc11  jnz     short loc_1800BCC91
0x1800bcc13  mov     rcx, r14; this
0x1800bcc16  call    ?Cleanup@URL_INFO@@QEAAXXZ; URL_INFO::Cleanup(void)
0x1800bcc1b  mov     rcx, r14; this
0x1800bcc1e  call    ??_GURL_INFO@@QEAAPEAXI@Z; URL_INFO::`scalar deleting destructor'(uint)
0x1800bcc23  test    rdi, rdi
0x1800bcc26  jz      short loc_1800BCC81
0x1800bcc28  mov     r8, rdi; lpMem
0x1800bcc2b  xor     edx, edx; dwFlags
0x1800bcc2d  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x1800bcc34  call    cs:__imp_HeapFree
0x1800bcc3a  test    eax, eax
0x1800bcc3c  jnz     short loc_1800BCC81
0x1800bcc3e  lea     rsi, WPP_GLOBAL_Control
0x1800bcc45  mov     rax, cs:WPP_GLOBAL_Control
0x1800bcc4c  cmp     rax, rsi
0x1800bcc4f  jz      short loc_1800BCC81
0x1800bcc51  test    byte ptr [rax+1Ch], 4
0x1800bcc55  jz      short loc_1800BCC81
0x1800bcc57  call    cs:__imp_GetLastError
0x1800bcc5d  mov     edx, 0Bh
0x1800bcc62  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800bcc66  mov     r9, rdi
0x1800bcc69  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x1800bcc70  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcc77  mov     rcx, [rcx+10h]
0x1800bcc7b  call    WPP_SF_qD
0x1800bcc80  nop
0x1800bcc81  lea     rcx, [rbp+57h+arg_8]
0x1800bcc85  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x1800bcc8a  xor     eax, eax
0x1800bcc8c  jmp     loc_1800BCDB3
0x1800bcc91  lea     rsi, WPP_GLOBAL_Control
0x1800bcc98  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcc9f  cmp     rcx, rsi
0x1800bcca2  jz      short loc_1800BCCD4
0x1800bcca4  test    byte ptr [rcx+1Ch], 1
0x1800bcca8  jz      short loc_1800BCCD4
0x1800bccaa  mov     rax, [rbx+68h]
0x1800bccae  add     rax, 0Ch
0x1800bccb2  mov     edx, 0D7h
0x1800bccb7  mov     qword ptr [rsp+0C0h+var_98], rdi
0x1800bccbc  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1800bccc1  mov     r9, rbx
0x1800bccc4  lea     r8, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids
0x1800bcccb  mov     rcx, [rcx+10h]
0x1800bcccf  call    WPP_SF_qSS
0x1800bccd4  mov     rcx, [rbx+2C0h]; this
0x1800bccdb  call    ?Cleanup@URL_INFO@@QEAAXXZ; URL_INFO::Cleanup(void)
0x1800bcce0  mov     rcx, [rbx+2C0h]; this
0x1800bcce7  test    rcx, rcx
0x1800bccea  jz      short loc_1800BCCF1
0x1800bccec  call    ??_GURL_INFO@@QEAAPEAXI@Z; URL_INFO::`scalar deleting destructor'(uint)
0x1800bccf1  test    rdi, rdi
0x1800bccf4  jz      short loc_1800BCD47
0x1800bccf6  mov     r8, rdi; lpMem
0x1800bccf9  xor     edx, edx; dwFlags
0x1800bccfb  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x1800bcd02  call    cs:__imp_HeapFree
0x1800bcd08  test    eax, eax
0x1800bcd0a  jnz     short loc_1800BCD47
0x1800bcd0c  mov     rax, cs:WPP_GLOBAL_Control
0x1800bcd13  cmp     rax, rsi
0x1800bcd16  jz      short loc_1800BCD47
0x1800bcd18  test    byte ptr [rax+1Ch], 4
0x1800bcd1c  jz      short loc_1800BCD47
0x1800bcd1e  call    cs:__imp_GetLastError
0x1800bcd24  mov     edx, 0Bh
0x1800bcd29  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800bcd2d  mov     r9, rdi
0x1800bcd30  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x1800bcd37  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bcd3e  mov     rcx, [rcx+10h]
0x1800bcd42  call    WPP_SF_qD
0x1800bcd47  mov     [rbx+2C0h], r14
0x1800bcd4e  lea     r9, [rbx+3B8h]; struct EidAsyncHelper *
0x1800bcd55  lea     r8, [rbx+288h]; struct HttpSecurityData *
0x1800bcd5c  mov     al, [rbx+278h]
0x1800bcd62  mov     [rsp+0C0h+var_A0], al; bool
0x1800bcd66  mov     rdx, [rbx+280h]; struct IHttpInterface *
0x1800bcd6d  mov     rcx, r14; this
0x1800bcd70  call    ?Connect@URL_INFO@@QEAAXPEAVIHttpInterface@@AEBUHttpSecurityData@@AEAVEidAsyncHelper@@_N@Z; URL_INFO::Connect(IHttpInterface *,HttpSecurityData const &,EidAsyncHelper &,bool)
0x1800bcd75  mov     rcx, [rbx+2C0h]; this
0x1800bcd7c  call    ?NeedsProxyDetection@URL_INFO@@QEAA_NXZ; URL_INFO::NeedsProxyDetection(void)
0x1800bcd81  mov     rcx, rbx; this
0x1800bcd84  test    al, al
0x1800bcd86  jz      short loc_1800BCD9C
0x1800bcd88  call    ?IncrementPendingAsyncOpsCount@CHttpWriter@@IEAAXXZ; CHttpWriter::IncrementPendingAsyncOpsCount(void)
0x1800bcd8d  mov     rcx, [rbx+578h]; pwk
0x1800bcd94  call    cs:__imp_SubmitThreadpoolWork
0x1800bcd9a  jmp     short loc_1800BCDA5
0x1800bcd9c  call    ?RecalcProxyStats@CHttpWriter@@AEAAXXZ; CHttpWriter::RecalcProxyStats(void)
0x1800bcda1  mov     byte ptr [rbx+38h], 1
0x1800bcda5  lea     rcx, [rbp+57h+arg_8]
0x1800bcda9  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x1800bcdae  mov     eax, 1
0x1800bcdb3  add     rsp, 0A0h
0x1800bcdba  pop     r14
0x1800bcdbc  pop     rdi
0x1800bcdbd  pop     rsi
0x1800bcdbe  pop     rbx
0x1800bcdbf  pop     rbp
0x1800bcdc0  retn
```
