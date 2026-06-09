# CHttpReader::CheckIfRedirection(void)

- ea: `0x1800bc5e0`
- end: `0x1800bc9d2`
- name: `?CheckIfRedirection@CHttpReader@@IEAAHXZ`
- size: `1010`
- prototype: `__int64 __fastcall(CHttpReader *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1800bd044`

## callees

- `0x180006640`
- `0x180008cc0`
- `0x18000c7d0`
- `0x18001d7f0`
- `0x1800548e4`
- `0x180069f10`
- `0x18006c7f8`
- `0x18006c888`
- `0x180081adc`
- `0x18009c858`
- `0x18009c97c`
- `0x1800a7558`
- `0x1800bc5e0`
- `0x1800c12b4`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bc80b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bc80b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bc6d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bc836`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bc913`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bc6d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bc836`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bc913`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc61d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc628`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc63a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc6f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc721`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc72b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc733`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc92f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc61d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc628`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc63a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc6f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc721`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc72b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc733`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc92f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bc9a5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bc9a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CHttpReader::CheckIfRedirection(CHttpReader *this)
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
  (*(void (__fastcall **)(_QWORD, __int64, _QWORD, unsigned int *))(**((_QWORD **)this + 83) + 24LL))(
    *((_QWORD *)this + 83),
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
    v17 = 2370;
    v18 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v3 = operator new(saturated_mul((unsigned __int64)v19 >> 1, 2u));
  if ( !(*(unsigned int (__fastcall **)(_QWORD, __int64, void *, unsigned int *))(**((_QWORD **)this + 83) + 24LL))(
          *((_QWORD *)this + 83),
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
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, v3, v4);
    }
    if ( (int)GetLastError() > 0 )
      v5 = (unsigned __int16)GetLastError() | 0x80070000;
    else
      v5 = GetLastError();
    v15 = 0;
    pExceptionObject = &ComError::`vftable';
    v16 = v5;
    v17 = 2382;
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
           (__int64)this + 676,
           *((_QWORD *)this + 99),
           (__int64)this + ((*((_DWORD *)this + 65830) & 2) != 0 ? 263312LL : 263304LL),
           *((_DWORD *)this + 65831),
           *((_BYTE *)this + 263328),
           0);
  else
    v7 = 0;
  if ( (unsigned int)_o__wcsicmp(*(_QWORD *)(v7 + 1120), *(_QWORD *)(*((_QWORD *)this + 80) + 1120LL)) )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_qSS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        79,
        (unsigned int)WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids,
        (_DWORD)this,
        *((_QWORD *)this + 13) + 12LL,
        (__int64)v3);
    URL_INFO::Cleanup(*((URL_INFO **)this + 80));
    CHttpReader::GotoState(this, 0xDu, 0);
    v12 = (URL_INFO *)*((_QWORD *)this + 80);
    if ( v12 )
      URL_INFO::`scalar deleting destructor'(v12, v11);
    if ( v3
      && !HeapFree(hBitsHeap, 0, v3)
      && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v13 = GetLastError();
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, v3, v13);
    }
    *((_QWORD *)this + 80) = v7;
    URL_INFO::Connect(
      (const WCHAR **)v7,
      *((struct IHttpInterface **)this + 82),
      (CHttpReader *)((char *)this + 676),
      (struct _RTL_CRITICAL_SECTION *)((char *)this + 263136),
      *((_BYTE *)this + 263099));
    if ( URL_INFO::NeedsProxyDetection(*((URL_INFO **)this + 80)) )
    {
      CHttpReader::IncrementPendingAsyncOpsCount(this);
      SubmitThreadpoolWork(*((PTP_WORK *)this + 81));
    }
    else
    {
      CHttpReader::RecalcProxyStats(this);
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
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, v3, v9);
    }
    GenericStringHandle<unsigned short>::FreeIt(&v20);
    return 0;
  }
}

```

## disassembly

```asm
0x1800bc5e0  push    rbp
0x1800bc5e2  push    rbx
0x1800bc5e3  push    rsi
0x1800bc5e4  push    rdi
0x1800bc5e5  push    r14
0x1800bc5e7  lea     rbp, [rsp-37h]
0x1800bc5ec  sub     rsp, 0A0h
0x1800bc5f3  mov     rbx, rcx
0x1800bc5f6  mov     [rbp+57h+arg_0], 0
0x1800bc5fd  mov     rcx, [rcx+298h]
0x1800bc604  mov     rax, [rcx]
0x1800bc607  lea     r9, [rbp+57h+arg_0]
0x1800bc60b  xor     r8d, r8d
0x1800bc60e  lea     esi, [r8+22h]
0x1800bc612  mov     edx, esi
0x1800bc614  mov     rax, [rax+18h]
0x1800bc618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc61d  call    cs:__imp_GetLastError
0x1800bc623  cmp     eax, 7Ah ; 'z'
0x1800bc626  jz      short loc_1800BC67C
0x1800bc628  call    cs:__imp_GetLastError
0x1800bc62e  test    eax, eax
0x1800bc630  jg      short loc_1800BC63A
0x1800bc632  call    cs:__imp_GetLastError
0x1800bc638  jmp     short loc_1800BC648
0x1800bc63a  call    cs:__imp_GetLastError
0x1800bc640  movzx   eax, ax
0x1800bc643  or      eax, 80070000h
0x1800bc648  xorps   xmm0, xmm0
0x1800bc64b  movups  [rbp+57h+var_78], xmm0
0x1800bc64f  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800bc656  mov     [rbp+57h+pExceptionObject], rcx
0x1800bc65a  mov     [rbp+57h+var_68], eax
0x1800bc65d  mov     [rbp+57h+var_64], 942h
0x1800bc664  mov     [rbp+57h+var_60], 1
0x1800bc66b  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800bc672  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800bc676  call    _CxxThrowException_0
0x1800bc67c  mov     ecx, [rbp+57h+arg_0]
0x1800bc67f  shr     rcx, 1
0x1800bc682  mov     eax, 2
0x1800bc687  mul     rcx
0x1800bc68a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800bc691  cmovb   rax, rcx
0x1800bc695  mov     rcx, rax; dwBytes
0x1800bc698  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bc69d  mov     rdi, rax
0x1800bc6a0  mov     rcx, [rbx+298h]
0x1800bc6a7  mov     r8, [rcx]
0x1800bc6aa  mov     rax, [r8+18h]
0x1800bc6ae  lea     r9, [rbp+57h+arg_0]
0x1800bc6b2  mov     r8, rdi
0x1800bc6b5  mov     edx, esi
0x1800bc6b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc6bc  test    eax, eax
0x1800bc6be  jnz     loc_1800BC775
0x1800bc6c4  test    rdi, rdi
0x1800bc6c7  jz      short loc_1800BC721
0x1800bc6c9  mov     r8, rdi; lpMem
0x1800bc6cc  xor     edx, edx; dwFlags
0x1800bc6ce  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x1800bc6d5  call    cs:__imp_HeapFree
0x1800bc6db  test    eax, eax
0x1800bc6dd  jnz     short loc_1800BC721
0x1800bc6df  lea     rsi, WPP_GLOBAL_Control
0x1800bc6e6  mov     rax, cs:WPP_GLOBAL_Control
0x1800bc6ed  cmp     rax, rsi
0x1800bc6f0  jz      short loc_1800BC721
0x1800bc6f2  test    byte ptr [rax+1Ch], 4
0x1800bc6f6  jz      short loc_1800BC721
0x1800bc6f8  call    cs:__imp_GetLastError
0x1800bc6fe  mov     edx, 0Bh
0x1800bc703  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800bc707  mov     r9, rdi
0x1800bc70a  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x1800bc711  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc718  mov     rcx, [rcx+10h]
0x1800bc71c  call    WPP_SF_qD
0x1800bc721  call    cs:__imp_GetLastError
0x1800bc727  test    eax, eax
0x1800bc729  jg      short loc_1800BC733
0x1800bc72b  call    cs:__imp_GetLastError
0x1800bc731  jmp     short loc_1800BC741
0x1800bc733  call    cs:__imp_GetLastError
0x1800bc739  movzx   eax, ax
0x1800bc73c  or      eax, 80070000h
0x1800bc741  xorps   xmm0, xmm0
0x1800bc744  movups  [rbp+57h+var_78], xmm0
0x1800bc748  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800bc74f  mov     [rbp+57h+pExceptionObject], rcx
0x1800bc753  mov     [rbp+57h+var_68], eax
0x1800bc756  mov     [rbp+57h+var_64], 94Eh
0x1800bc75d  mov     [rbp+57h+var_60], 1
0x1800bc764  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800bc76b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800bc76f  call    _CxxThrowException_0
0x1800bc775  mov     rcx, rdi
0x1800bc778  call    ?NewString@?$GenericStringHandle@G@@CAPEAUStringData@1@PEBG@Z; GenericStringHandle<ushort>::NewString(ushort const *)
0x1800bc77d  mov     [rbp+57h+arg_8], rax
0x1800bc781  mov     ecx, 470h; dwBytes
0x1800bc786  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bc78b  mov     r10, rax
0x1800bc78e  mov     [rbp+57h+arg_10], rax
0x1800bc792  test    rax, rax
0x1800bc795  jz      short loc_1800BC7F3
0x1800bc797  mov     ecx, [rbx+40498h]
0x1800bc79d  and     cl, 2
0x1800bc7a0  neg     cl
0x1800bc7a2  sbb     rdx, rdx
0x1800bc7a5  and     edx, 8
0x1800bc7a8  add     rdx, 40488h
0x1800bc7af  add     rdx, rbx
0x1800bc7b2  lea     r8, [rbx+2A4h]; int
0x1800bc7b9  mov     [rsp+0C0h+var_88], 0; unsigned __int16 *
0x1800bc7c2  mov     al, [rbx+404A0h]
0x1800bc7c8  mov     [rsp+0C0h+var_90], al; char
0x1800bc7cc  mov     eax, [rbx+4049Ch]
0x1800bc7d2  mov     [rsp+0C0h+var_98], eax; int
0x1800bc7d6  mov     qword ptr [rsp+0C0h+var_A0], rdx; __int64
0x1800bc7db  mov     r9, [rbx+318h]; int
0x1800bc7e2  lea     rdx, [rbp+57h+arg_8]; int
0x1800bc7e6  mov     rcx, r10; int
0x1800bc7e9  call    ??0URL_INFO@@QEAA@AEBV?$GenericStringHandle@G@@AEBUHttpSecurityData@@PEBUPROXY_SETTINGS@@AEBVTokenHandle@@K_NPEBG@Z; URL_INFO::URL_INFO(GenericStringHandle<ushort> const &,HttpSecurityData const &,PROXY_SETTINGS const *,TokenHandle const &,ulong,bool,ushort const *)
0x1800bc7ee  mov     r14, rax
0x1800bc7f1  jmp     short loc_1800BC7F6
0x1800bc7f3  xor     r14d, r14d
0x1800bc7f6  mov     rdx, [rbx+280h]
0x1800bc7fd  mov     rdx, [rdx+460h]
0x1800bc804  mov     rcx, [r14+460h]
0x1800bc80b  call    cs:__imp__o__wcsicmp
0x1800bc811  test    eax, eax
0x1800bc813  jnz     short loc_1800BC893
0x1800bc815  mov     rcx, r14; this
0x1800bc818  call    ?Cleanup@URL_INFO@@QEAAXXZ; URL_INFO::Cleanup(void)
0x1800bc81d  mov     rcx, r14; this
0x1800bc820  call    ??_GURL_INFO@@QEAAPEAXI@Z; URL_INFO::`scalar deleting destructor'(uint)
0x1800bc825  test    rdi, rdi
0x1800bc828  jz      short loc_1800BC883
0x1800bc82a  mov     r8, rdi; lpMem
0x1800bc82d  xor     edx, edx; dwFlags
0x1800bc82f  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x1800bc836  call    cs:__imp_HeapFree
0x1800bc83c  test    eax, eax
0x1800bc83e  jnz     short loc_1800BC883
0x1800bc840  lea     rsi, WPP_GLOBAL_Control
0x1800bc847  mov     rax, cs:WPP_GLOBAL_Control
0x1800bc84e  cmp     rax, rsi
0x1800bc851  jz      short loc_1800BC883
0x1800bc853  test    byte ptr [rax+1Ch], 4
0x1800bc857  jz      short loc_1800BC883
0x1800bc859  call    cs:__imp_GetLastError
0x1800bc85f  mov     edx, 0Bh
0x1800bc864  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800bc868  mov     r9, rdi
0x1800bc86b  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x1800bc872  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc879  mov     rcx, [rcx+10h]
0x1800bc87d  call    WPP_SF_qD
0x1800bc882  nop
0x1800bc883  lea     rcx, [rbp+57h+arg_8]
0x1800bc887  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x1800bc88c  xor     eax, eax
0x1800bc88e  jmp     loc_1800BC9C4
0x1800bc893  lea     rsi, WPP_GLOBAL_Control
0x1800bc89a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc8a1  cmp     rcx, rsi
0x1800bc8a4  jz      short loc_1800BC8D6
0x1800bc8a6  test    byte ptr [rcx+1Ch], 1
0x1800bc8aa  jz      short loc_1800BC8D6
0x1800bc8ac  mov     rax, [rbx+68h]
0x1800bc8b0  add     rax, 0Ch
0x1800bc8b4  mov     edx, 4Fh ; 'O'
0x1800bc8b9  mov     qword ptr [rsp+0C0h+var_98], rdi
0x1800bc8be  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1800bc8c3  mov     r9, rbx
0x1800bc8c6  lea     r8, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids
0x1800bc8cd  mov     rcx, [rcx+10h]
0x1800bc8d1  call    WPP_SF_qSS
0x1800bc8d6  mov     rcx, [rbx+280h]; this
0x1800bc8dd  call    ?Cleanup@URL_INFO@@QEAAXXZ; URL_INFO::Cleanup(void)
0x1800bc8e2  xor     r8d, r8d; bool
0x1800bc8e5  lea     edx, [r8+0Dh]; unsigned int
0x1800bc8e9  mov     rcx, rbx; this
0x1800bc8ec  call    ?GotoState@CHttpReader@@IEAAXK_N@Z; CHttpReader::GotoState(ulong,bool)
0x1800bc8f1  mov     rcx, [rbx+280h]; this
0x1800bc8f8  test    rcx, rcx
0x1800bc8fb  jz      short loc_1800BC902
0x1800bc8fd  call    ??_GURL_INFO@@QEAAPEAXI@Z; URL_INFO::`scalar deleting destructor'(uint)
0x1800bc902  test    rdi, rdi
0x1800bc905  jz      short loc_1800BC958
0x1800bc907  mov     r8, rdi; lpMem
0x1800bc90a  xor     edx, edx; dwFlags
0x1800bc90c  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x1800bc913  call    cs:__imp_HeapFree
0x1800bc919  test    eax, eax
0x1800bc91b  jnz     short loc_1800BC958
0x1800bc91d  mov     rax, cs:WPP_GLOBAL_Control
0x1800bc924  cmp     rax, rsi
0x1800bc927  jz      short loc_1800BC958
0x1800bc929  test    byte ptr [rax+1Ch], 4
0x1800bc92d  jz      short loc_1800BC958
0x1800bc92f  call    cs:__imp_GetLastError
0x1800bc935  mov     edx, 0Bh
0x1800bc93a  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800bc93e  mov     r9, rdi
0x1800bc941  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x1800bc948  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc94f  mov     rcx, [rcx+10h]
0x1800bc953  call    WPP_SF_qD
0x1800bc958  mov     [rbx+280h], r14
0x1800bc95f  lea     r9, [rbx+403E0h]; struct EidAsyncHelper *
0x1800bc966  lea     r8, [rbx+2A4h]; struct HttpSecurityData *
0x1800bc96d  mov     al, [rbx+403BBh]
0x1800bc973  mov     [rsp+0C0h+var_A0], al; bool
0x1800bc977  mov     rdx, [rbx+290h]; struct IHttpInterface *
0x1800bc97e  mov     rcx, r14; this
0x1800bc981  call    ?Connect@URL_INFO@@QEAAXPEAVIHttpInterface@@AEBUHttpSecurityData@@AEAVEidAsyncHelper@@_N@Z; URL_INFO::Connect(IHttpInterface *,HttpSecurityData const &,EidAsyncHelper &,bool)
0x1800bc986  mov     rcx, [rbx+280h]; this
0x1800bc98d  call    ?NeedsProxyDetection@URL_INFO@@QEAA_NXZ; URL_INFO::NeedsProxyDetection(void)
0x1800bc992  mov     rcx, rbx; this
0x1800bc995  test    al, al
0x1800bc997  jz      short loc_1800BC9AD
0x1800bc999  call    ?IncrementPendingAsyncOpsCount@CHttpReader@@IEAAXXZ; CHttpReader::IncrementPendingAsyncOpsCount(void)
0x1800bc99e  mov     rcx, [rbx+288h]; pwk
0x1800bc9a5  call    cs:__imp_SubmitThreadpoolWork
0x1800bc9ab  jmp     short loc_1800BC9B6
0x1800bc9ad  call    ?RecalcProxyStats@CHttpReader@@IEAAXXZ; CHttpReader::RecalcProxyStats(void)
0x1800bc9b2  mov     byte ptr [rbx+38h], 1
0x1800bc9b6  lea     rcx, [rbp+57h+arg_8]
0x1800bc9ba  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x1800bc9bf  mov     eax, 1
0x1800bc9c4  add     rsp, 0A0h
0x1800bc9cb  pop     r14
0x1800bc9cd  pop     rdi
0x1800bc9ce  pop     rsi
0x1800bc9cf  pop     rbx
0x1800bc9d0  pop     rbp
0x1800bc9d1  retn
```
