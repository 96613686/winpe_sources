# CAsyncFile::Read(unsigned __int64,unsigned __int64,void const *,std::function<void (COverlappedFileOp const *,long)> const &)

- ea: `0x1800c1444`
- end: `0x1800c1704`
- name: `?Read@CAsyncFile@@QEAAJ_K0PEBXAEBV?$function@$$A6AXPEBVCOverlappedFileOp@@J@Z@std@@@Z`
- size: `704`
- prototype: `__int64 __usercall@<rax>(CAsyncFile *this@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180057cc4`
- `0x180058680`

## callees

- `0x18000c40c`
- `0x1800196f0`
- `0x1800a6d78`
- `0x1800c0f20`
- `0x1800c1444`
- `0x1800c1f8c`
- `0x1800c211c`
- `0x1800f82f0`
- `0x1800f8320`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c14a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c16a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c14a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c16a9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800c14ae`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800c16b7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800c14ae`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800c16b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CAsyncFile::Read(
        CAsyncFile *this,
        struct COverlappedFileOp *a2,
        unsigned __int64 a3,
        const char *a4,
        struct COverlappedFileOp *a5)
{
  char v8; // bl
  HANDLE CurrentThread; // rax
  _DWORD *v10; // rdi
  _DWORD *v11; // r15
  _DWORD *v12; // rdi
  struct COverlappedFileOp *v13; // rdi
  int v14; // eax
  unsigned int v15; // r14d
  __int64 v16; // rcx
  volatile signed __int32 *v17; // rsi
  volatile signed __int32 *v18; // rsi
  HANDLE v19; // rax
  __int64 result; // rax
  struct COverlappedFileOp *v21[2]; // [rsp+48h] [rbp-90h] BYREF
  _QWORD *v22; // [rsp+58h] [rbp-80h] BYREF
  volatile signed __int32 *v23; // [rsp+60h] [rbp-78h]
  _QWORD v24[2]; // [rsp+68h] [rbp-70h] BYREF
  int v25; // [rsp+78h] [rbp-60h]
  __int64 v26; // [rsp+80h] [rbp-58h]
  struct COverlappedFileOp *v27; // [rsp+88h] [rbp-50h]
  struct COverlappedFileOp *v28; // [rsp+90h] [rbp-48h] BYREF
  _DWORD *v29; // [rsp+98h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v28 = a2;
  v21[0] = a5;
  v8 = *((_BYTE *)this + 44) & 1;
  if ( v8 )
  {
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, 0x10000);
  }
  try
  {
    if ( a3 > 0xFFFFFFFF )
    {
      v15 = -2147024362;
    }
    else
    {
      v10 = operator new(0x28u);
      v10[2] = 1;
      v10[3] = 1;
      *(_QWORD *)v10 = &std::_Ref_count_obj2<std::vector<unsigned char>>::`vftable';
      v11 = v10 + 4;
      std::vector<unsigned char>::vector<unsigned char>(v10 + 4, (unsigned int)a3);
      v22 = v10 + 4;
      v23 = v10;
      v12 = operator new(0xA0u);
      v29 = v12;
      v12[2] = 1;
      v12[3] = 1;
      *(_QWORD *)v12 = &std::_Ref_count_obj2<COverlappedFileOp>::`vftable';
      COverlappedFileOp::COverlappedFileOp(
        (_DWORD)v12 + 16,
        (_DWORD)v28,
        (unsigned int)&v22,
        v11[2] - *v11,
        (__int64)this,
        (__int64)a4,
        (__int64)v21[0]);
      v21[0] = (struct COverlappedFileOp *)(v12 + 4);
      v21[1] = (struct COverlappedFileOp *)v12;
      CAsyncFile::_AddPending(this, v21);
      v24[0] = this;
      v24[1] = *v22;
      v25 = a3;
      v26 = 0;
      v13 = v21[0];
      v27 = v21[0];
      v14 = CFile::_InvokeFileMethod__CFile::Read_::_2_::_lambda_1___(this, v24);
      v15 = v14;
      if ( v14 < 0 )
      {
        if ( *((_QWORD *)v13 + 17) )
        {
          LODWORD(v29) = v14;
          v28 = v13;
          v16 = *((_QWORD *)v13 + 17);
          if ( !v16 )
            std::_Xbad_function_call();
          (*(void (__fastcall **)(__int64, struct COverlappedFileOp **, _DWORD **))(*(_QWORD *)v16 + 16LL))(
            v16,
            &v28,
            &v29);
        }
        v15 = 0;
        CAsyncFile::_RemovePending(this, v13);
      }
      v17 = (volatile signed __int32 *)v21[1];
      if ( v21[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v21[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
          if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
        }
      }
      v18 = v23;
      if ( v23 )
      {
        if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
          if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
        }
      }
    }
    if ( v8 )
    {
      v19 = GetCurrentThread();
      SetThreadPriority(v19, 0x20000);
    }
    result = v15;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x74,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\AsyncFile.cpp",
                           a4);
  }
  return result;
}

```

## disassembly

```asm
0x1800c1444  mov     [rsp+arg_8], rbx
0x1800c1449  mov     [rsp+arg_18], rsi
0x1800c144e  push    rdi
0x1800c144f  push    r12
0x1800c1451  push    r13
0x1800c1453  push    r14
0x1800c1455  push    r15
0x1800c1457  sub     rsp, 0B0h
0x1800c145e  mov     rax, cs:__security_cookie
0x1800c1465  xor     rax, rsp
0x1800c1468  mov     [rsp+0D8h+var_38], rax
0x1800c1470  mov     r13, r9
0x1800c1473  mov     r14, r8
0x1800c1476  mov     [rsp+0D8h+var_48], rdx
0x1800c147e  mov     rsi, rcx
0x1800c1481  mov     rax, [rsp+0D8h+arg_20]
0x1800c1489  mov     [rsp+0D8h+var_90], rax
0x1800c148e  mov     bl, [rcx+2Ch]
0x1800c1491  mov     r12d, 1
0x1800c1497  and     bl, r12b
0x1800c149a  mov     [rsp+0D8h+var_98], bl
0x1800c149e  jz      short loc_1800C14B5
0x1800c14a0  call    cs:__imp_GetCurrentThread
0x1800c14a6  mov     rcx, rax; hThread
0x1800c14a9  mov     edx, 10000h; nPriority
0x1800c14ae  call    cs:__imp_SetThreadPriority
0x1800c14b4  nop
0x1800c14b5  mov     eax, 0FFFFFFFFh
0x1800c14ba  cmp     r14, rax
0x1800c14bd  ja      loc_1800C169F
0x1800c14c3  mov     ecx, 28h ; '('; Size
0x1800c14c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c14cd  mov     rdi, rax
0x1800c14d0  mov     [rsp+0D8h+var_40], rax
0x1800c14d8  mov     [rax+8], r12d
0x1800c14dc  mov     [rax+0Ch], r12d
0x1800c14e0  lea     rax, ??_7?$_Ref_count_obj2@V?$vector@EV?$allocator@E@std@@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<uchar>>::`vftable'
0x1800c14e7  mov     [rdi], rax
0x1800c14ea  lea     r15, [rdi+10h]
0x1800c14ee  mov     edx, r14d
0x1800c14f1  mov     rcx, r15
0x1800c14f4  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800c14f9  nop
0x1800c14fa  xorps   xmm0, xmm0
0x1800c14fd  movups  [rsp+0D8h+var_80], xmm0
0x1800c1502  mov     qword ptr [rsp+0D8h+var_80], r15
0x1800c1507  mov     qword ptr [rsp+0D8h+var_80+8], rdi
0x1800c150c  mov     ecx, 0A0h; Size
0x1800c1511  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c1516  mov     rdi, rax
0x1800c1519  mov     [rsp+0D8h+var_40], rax
0x1800c1521  mov     [rax+8], r12d
0x1800c1525  mov     [rax+0Ch], r12d
0x1800c1529  lea     rax, ??_7?$_Ref_count_obj2@VCOverlappedFileOp@@@std@@6B@; const std::_Ref_count_obj2<COverlappedFileOp>::`vftable'
0x1800c1530  mov     [rdi], rax
0x1800c1533  lea     r12, [rdi+10h]
0x1800c1537  mov     r9, [r15+8]
0x1800c153b  sub     r9, [r15]
0x1800c153e  mov     rax, [rsp+0D8h+var_90]
0x1800c1543  mov     [rsp+0D8h+var_A8], rax
0x1800c1548  mov     [rsp+0D8h+var_B0], r13
0x1800c154d  mov     [rsp+0D8h+var_B8], rsi
0x1800c1552  lea     r8, [rsp+0D8h+var_80]
0x1800c1557  mov     rdx, [rsp+0D8h+var_48]
0x1800c155f  mov     rcx, r12
0x1800c1562  call    ??0COverlappedFileOp@@QEAA@_KAEBV?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@0PEBX2AEBV?$function@$$A6AXPEBVCOverlappedFileOp@@J@Z@2@@Z; COverlappedFileOp::COverlappedFileOp(unsigned __int64,std::shared_ptr<std::vector<uchar>> const &,unsigned __int64,void const *,void const *,std::function<void (COverlappedFileOp const *,long)> const &)
0x1800c1567  nop
0x1800c1568  xorps   xmm0, xmm0
0x1800c156b  movups  xmmword ptr [rsp+0D8h+var_90], xmm0
0x1800c1570  mov     [rsp+0D8h+var_90], r12
0x1800c1575  mov     [rsp+0D8h+var_90+8], rdi
0x1800c157a  lea     rdx, [rsp+0D8h+var_90]
0x1800c157f  mov     rcx, rsi
0x1800c1582  call    ?_AddPending@CAsyncFile@@AEAAXAEBV?$shared_ptr@VCOverlappedFileOp@@@std@@@Z; CAsyncFile::_AddPending(std::shared_ptr<COverlappedFileOp> const &)
0x1800c1587  mov     [rsp+0D8h+var_70], rsi
0x1800c158c  mov     rax, qword ptr [rsp+0D8h+var_80]
0x1800c1591  mov     rcx, [rax]
0x1800c1594  mov     [rsp+0D8h+var_68], rcx
0x1800c1599  mov     [rsp+0D8h+var_60], r14d
0x1800c159e  mov     [rsp+0D8h+var_58], 0
0x1800c15aa  mov     rdi, [rsp+0D8h+var_90]
0x1800c15af  mov     [rsp+0D8h+var_50], rdi
0x1800c15b7  lea     rdx, [rsp+0D8h+var_70]
0x1800c15bc  mov     rcx, rsi
0x1800c15bf  call    CFile___InvokeFileMethod__CFile__Read____2____lambda_1___
0x1800c15c4  mov     r14d, eax
0x1800c15c7  test    eax, eax
0x1800c15c9  jns     short loc_1800C161F
0x1800c15cb  cmp     qword ptr [rdi+88h], 0
0x1800c15d3  jz      short loc_1800C1610
0x1800c15d5  mov     dword ptr [rsp+0D8h+var_40], eax
0x1800c15dc  mov     [rsp+0D8h+var_48], rdi
0x1800c15e4  mov     rcx, [rdi+88h]
0x1800c15eb  test    rcx, rcx
0x1800c15ee  jz      loc_1800C16FD
0x1800c15f4  mov     rax, [rcx]
0x1800c15f7  lea     r8, [rsp+0D8h+var_40]
0x1800c15ff  lea     rdx, [rsp+0D8h+var_48]
0x1800c1607  mov     rax, [rax+10h]
0x1800c160b  call    _guard_dispatch_icall
0x1800c1610  xor     r14d, r14d
0x1800c1613  mov     rdx, rdi; struct COverlappedFileOp *
0x1800c1616  mov     rcx, rsi; this
0x1800c1619  call    ?_RemovePending@CAsyncFile@@AEAAXPEAVCOverlappedFileOp@@@Z; CAsyncFile::_RemovePending(COverlappedFileOp *)
0x1800c161e  nop
0x1800c161f  mov     rsi, [rsp+0D8h+var_90+8]
0x1800c1624  or      edi, 0FFFFFFFFh
0x1800c1627  test    rsi, rsi
0x1800c162a  jz      short loc_1800C1660
0x1800c162c  mov     eax, edi
0x1800c162e  lock xadd [rsi+8], eax
0x1800c1633  add     eax, edi
0x1800c1635  jnz     short loc_1800C1660
0x1800c1637  mov     rax, [rsi]
0x1800c163a  mov     rcx, rsi
0x1800c163d  mov     rax, [rax]
0x1800c1640  call    _guard_dispatch_icall
0x1800c1645  mov     eax, edi
0x1800c1647  lock xadd [rsi+0Ch], eax
0x1800c164c  add     eax, edi
0x1800c164e  jnz     short loc_1800C1660
0x1800c1650  mov     rax, [rsi]
0x1800c1653  mov     rcx, rsi
0x1800c1656  mov     rax, [rax+8]
0x1800c165a  call    _guard_dispatch_icall
0x1800c165f  nop
0x1800c1660  mov     rsi, qword ptr [rsp+0D8h+var_80+8]
0x1800c1665  test    rsi, rsi
0x1800c1668  jz      short loc_1800C16A5
0x1800c166a  mov     eax, edi
0x1800c166c  lock xadd [rsi+8], eax
0x1800c1671  add     eax, edi
0x1800c1673  jnz     short loc_1800C16A5
0x1800c1675  mov     rax, [rsi]
0x1800c1678  mov     rcx, rsi
0x1800c167b  mov     rax, [rax]
0x1800c167e  call    _guard_dispatch_icall
0x1800c1683  mov     eax, edi
0x1800c1685  lock xadd [rsi+0Ch], eax
0x1800c168a  add     eax, edi
0x1800c168c  jnz     short loc_1800C16A5
0x1800c168e  mov     rax, [rsi]
0x1800c1691  mov     rcx, rsi
0x1800c1694  mov     rax, [rax+8]
0x1800c1698  call    _guard_dispatch_icall
0x1800c169d  jmp     short loc_1800C16A5
0x1800c169f  mov     r14d, 80070216h
0x1800c16a5  test    bl, bl
0x1800c16a7  jz      short loc_1800C16BD
0x1800c16a9  call    cs:__imp_GetCurrentThread
0x1800c16af  mov     rcx, rax; hThread
0x1800c16b2  mov     edx, 20000h; nPriority
0x1800c16b7  call    cs:__imp_SetThreadPriority
0x1800c16bd  mov     eax, r14d
0x1800c16c0  jmp     short loc_1800C16D0
0x1800c16c2  mov     eax, dword ptr [rsp+0D8h+var_40]
0x1800c16c9  jmp     short loc_1800C16D0
0x1800c16cb  mov     eax, 8007000Eh
0x1800c16d0  mov     rcx, [rsp+0D8h+var_38]
0x1800c16d8  xor     rcx, rsp; StackCookie
0x1800c16db  call    __security_check_cookie
0x1800c16e0  lea     r11, [rsp+0D8h+var_28]
0x1800c16e8  mov     rbx, [r11+38h]
0x1800c16ec  mov     rsi, [r11+48h]
0x1800c16f0  mov     rsp, r11
0x1800c16f3  pop     r15
0x1800c16f5  pop     r14
0x1800c16f7  pop     r13
0x1800c16f9  pop     r12
0x1800c16fb  pop     rdi
0x1800c16fc  retn
0x1800c16fd  call    ?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
```
