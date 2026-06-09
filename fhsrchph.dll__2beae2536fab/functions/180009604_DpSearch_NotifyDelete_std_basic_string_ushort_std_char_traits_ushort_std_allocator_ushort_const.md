# DpSearch::NotifyDelete(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180009604`
- end: `0x180009788`
- name: `?NotifyDelete@DpSearch@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800099e4`

## callees

- `0x180001d04`
- `0x1800020d8`
- `0x180009604`
- `0x18000ab60`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000965f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000965f`

## pseudocode

```c
__int64 __fastcall DpSearch::NotifyDelete(__int64 a1, _QWORD *a2)
{
  __int64 *v2; // rdi
  __int64 v4; // rcx
  HRESULT Instance; // eax
  __int64 v7; // rcx
  int v8; // eax
  bool v9; // cf
  __int64 result; // rax
  _BYTE v11[4]; // [rsp+40h] [rbp-19h] BYREF
  int pExceptionObject; // [rsp+44h] [rbp-15h] BYREF
  _BYTE v13[4]; // [rsp+48h] [rbp-11h] BYREF
  _BYTE v14[4]; // [rsp+4Ch] [rbp-Dh] BYREF
  _QWORD v15[4]; // [rsp+50h] [rbp-9h] BYREF
  __int128 v16; // [rsp+70h] [rbp+17h] BYREF
  __int128 v17; // [rsp+80h] [rbp+27h] BYREF

  v2 = (__int64 *)(a1 + 24);
  v4 = *(_QWORD *)(a1 + 24);
  if ( !v4 )
  {
    Instance = CoCreateInstance(
                 &GUID_a7aa4814_7479_4047_bc99_32e757c8b850,
                 0,
                 0x17u,
                 &GUID_b5702e61_e75c_4b64_82a1_6cb4f832fccf,
                 (LPVOID *)(a1 + 16));
    if ( Instance < 0 )
    {
      ATL::CAtlException::CAtlException((ATL::CAtlException *)v11, Instance);
      throw (ATL::CAtlException *)v11;
    }
    v7 = *(_QWORD *)(a1 + 8);
    pExceptionObject = 0;
    v17 = 0;
    v16 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *, __int128 *, __int128 *, int *))(*(_QWORD *)v7 + 168LL))(
           v7,
           *(_QWORD *)(a1 + 16),
           &GUID_ab310581_ac80_11d1_8df3_00c04fb6ef58,
           v2,
           &v17,
           &v16,
           &pExceptionObject);
    if ( v8 < 0 )
    {
      ATL::CAtlException::CAtlException((ATL::CAtlException *)v11, v8);
      throw (ATL::CAtlException *)v11;
    }
    v4 = *v2;
  }
  v9 = a2[3] < 8u;
  v15[0] = 1;
  v15[1] = 0;
  if ( !v9 )
    a2 = (_QWORD *)*a2;
  v15[2] = a2;
  v15[3] = 0;
  result = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *, _BYTE *, _BYTE *))(*(_QWORD *)v4 + 40LL))(
             v4,
             1,
             v15,
             v14,
             v13);
  if ( (int)result < 0 )
  {
    ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, result);
    throw (ATL::CAtlException *)&pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180009604  mov     [rsp-8+arg_8], rbx
0x180009609  mov     [rsp-8+arg_10], rsi
0x18000960e  push    rbp
0x18000960f  push    rdi
0x180009610  push    r14
0x180009612  lea     rbp, [rsp-47h]
0x180009617  sub     rsp, 0A0h
0x18000961e  mov     rax, cs:__security_cookie
0x180009625  xor     rax, rsp
0x180009628  mov     [rbp+57h+var_20], rax
0x18000962c  lea     rdi, [rcx+18h]
0x180009630  mov     rsi, rcx
0x180009633  mov     rcx, [rdi]
0x180009636  mov     rbx, rdx
0x180009639  test    rcx, rcx
0x18000963c  jnz     loc_1800096C8
0x180009642  lea     r8d, [rcx+17h]; dwClsContext
0x180009646  xor     edx, edx; pUnkOuter
0x180009648  lea     r14, [rsi+10h]
0x18000964c  lea     rcx, _GUID_a7aa4814_7479_4047_bc99_32e757c8b850; rclsid
0x180009653  mov     [rsp+0B0h+ppv], r14; ppv
0x180009658  lea     r9, _GUID_b5702e61_e75c_4b64_82a1_6cb4f832fccf; riid
0x18000965f  call    cs:__imp_CoCreateInstance
0x180009665  test    eax, eax
0x180009667  js      loc_180009750
0x18000966d  mov     rcx, [rsi+8]
0x180009671  lea     rdx, [rbp+57h+pExceptionObject]
0x180009675  mov     [rsp+0B0h+var_80], rdx
0x18000967a  lea     r8, _GUID_ab310581_ac80_11d1_8df3_00c04fb6ef58
0x180009681  xorps   xmm0, xmm0
0x180009684  mov     [rbp+57h+pExceptionObject], 0
0x18000968b  xorps   xmm1, xmm1
0x18000968e  lea     rdx, [rbp+57h+var_40]
0x180009692  mov     [rsp+0B0h+var_88], rdx
0x180009697  mov     r9, rdi
0x18000969a  movups  [rbp+57h+var_30], xmm0
0x18000969e  lea     rdx, [rbp+57h+var_30]
0x1800096a2  movups  [rbp+57h+var_40], xmm1
0x1800096a6  mov     rax, [rcx]
0x1800096a9  mov     [rsp+0B0h+ppv], rdx
0x1800096ae  mov     rdx, [r14]
0x1800096b1  mov     rax, [rax+0A8h]
0x1800096b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096bd  test    eax, eax
0x1800096bf  js      loc_18000976C
0x1800096c5  mov     rcx, [rdi]
0x1800096c8  cmp     qword ptr [rbx+18h], 8
0x1800096cd  mov     edx, 1
0x1800096d2  mov     [rbp+57h+var_60], rdx
0x1800096d6  mov     [rbp+57h+var_58], 0
0x1800096de  jb      short loc_1800096E3
0x1800096e0  mov     rbx, [rbx]
0x1800096e3  mov     [rbp+57h+var_50], rbx
0x1800096e7  lea     r8, [rbp+57h+var_68]
0x1800096eb  mov     [rbp+57h+var_48], 0
0x1800096f3  lea     r9, [rbp+57h+var_64]
0x1800096f7  mov     rax, [rcx]
0x1800096fa  mov     [rsp+0B0h+ppv], r8
0x1800096ff  lea     r8, [rbp+57h+var_60]
0x180009703  mov     rax, [rax+28h]
0x180009707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000970c  test    eax, eax
0x18000970e  js      short loc_180009734
0x180009710  mov     rcx, [rbp+57h+var_20]
0x180009714  xor     rcx, rsp; StackCookie
0x180009717  call    __security_check_cookie
0x18000971c  lea     r11, [rsp+0B0h+var_10]
0x180009724  mov     rbx, [r11+28h]
0x180009728  mov     rsi, [r11+30h]
0x18000972c  mov     rsp, r11
0x18000972f  pop     r14
0x180009731  pop     rdi
0x180009732  pop     rbp
0x180009733  retn
0x180009734  mov     edx, eax; int
0x180009736  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18000973a  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000973f  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x180009746  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000974a  call    _CxxThrowException_0
0x180009750  mov     edx, eax; int
0x180009752  lea     rcx, [rbp+57h+var_70]; this
0x180009756  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000975b  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x180009762  lea     rcx, [rbp+57h+var_70]; pExceptionObject
0x180009766  call    _CxxThrowException_0
0x18000976c  mov     edx, eax; int
0x18000976e  lea     rcx, [rbp+57h+var_70]; this
0x180009772  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x180009777  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000977e  lea     rcx, [rbp+57h+var_70]; pExceptionObject
0x180009782  call    _CxxThrowException_0
```
