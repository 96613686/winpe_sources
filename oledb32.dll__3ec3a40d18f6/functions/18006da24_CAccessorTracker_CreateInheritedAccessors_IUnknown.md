# CAccessorTracker::CreateInheritedAccessors(IUnknown *)

- ea: `0x18006da24`
- end: `0x18006dd5d`
- name: `?CreateInheritedAccessors@CAccessorTracker@@QEAAJPEAUIUnknown@@@Z`
- size: `825`
- prototype: `__int64 __fastcall(CAccessorTracker *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18006f554`

## callees

- `0x180013870`
- `0x180029560`
- `0x18002ec0c`
- `0x18006da24`
- `0x18006dec0`
- `0x180087010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18006dc7c`
- `ole32!CoTaskMemFree` at `0x18006dc8c`
- `ole32!CoTaskMemFree` at `0x18006dca1`
- `ole32!CoTaskMemFree` at `0x18006dc7c`
- `ole32!CoTaskMemFree` at `0x18006dc8c`
- `ole32!CoTaskMemFree` at `0x18006dca1`

## string_xrefs

- `0x18006da7f`: `<CAccessorTracker::CreateInheritedAccessors|OLEDB|ERR> `
- `0x18006da9d`: `<CAccessorTracker::CreateInheritedAccessors|OLEDB|ERR> `
- `0x18006db1a`: `<CAccessorTracker::CreateInheritedAccessors|OLEDB|ERR> `
- `0x18006db38`: `<CAccessorTracker::CreateInheritedAccessors|OLEDB|ERR> `
- `0x18006dab8`: `<CAccessorTracker::CreateInheritedAccessors|Trace|HR> `
- `0x18006db53`: `<CAccessorTracker::CreateInheritedAccessors|Trace|HR> `
- `0x18006dd2b`: `<CAccessorTracker::CreateInheritedAccessors|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CAccessorTracker::CreateInheritedAccessors(CAccessorTracker *this, struct IUnknown *a2)
{
  int v3; // edi
  int v4; // edi
  __int64 v5; // rbx
  __int64 v6; // r14
  char *v7; // r15
  unsigned int v8; // eax
  unsigned int i; // r14d
  __int64 v10; // r12
  __int64 v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  __int64 j; // rax
  int v16; // ebx
  int pExceptionObject; // [rsp+40h] [rbp-58h] BYREF
  int v18; // [rsp+44h] [rbp-54h] BYREF
  unsigned int v19; // [rsp+48h] [rbp-50h] BYREF
  __int64 v20; // [rsp+50h] [rbp-48h] BYREF
  __int64 v21; // [rsp+58h] [rbp-40h]
  __int64 v22; // [rsp+60h] [rbp-38h] BYREF
  __int64 v23[6]; // [rsp+68h] [rbp-30h] BYREF
  int v24; // [rsp+A8h] [rbp+10h] BYREF
  unsigned int v25; // [rsp+B0h] [rbp+18h]
  LPVOID pv; // [rsp+B8h] [rbp+20h] BYREF

  v21 = 0;
  v22 = 0;
  try
  {
    v3 = ((__int64 (*)(void))a2->lpVtbl->QueryInterface)();
    if ( v3 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v3, L"<CAccessorTracker::CreateInheritedAccessors|OLEDB|ERR> ", 0x7Au);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v3, L"<CAccessorTracker::CreateInheritedAccessors|OLEDB|ERR> ", 0x7Au);
          if ( (bidGblFlags & 2) != 0 )
            v3 = bidTraceHR(
                   off_1800C8490[0],
                   124937,
                   L"<CAccessorTracker::CreateInheritedAccessors|Trace|HR> ",
                   (unsigned int)v3);
        }
      }
      pExceptionObject = v3;
      throw (long *)&pExceptionObject;
    }
    v4 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this)(*(_QWORD *)this, &IID_IAccessor, &v22);
    if ( v4 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v4, L"<CAccessorTracker::CreateInheritedAccessors|OLEDB|ERR> ", 0x7Cu);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v4, L"<CAccessorTracker::CreateInheritedAccessors|OLEDB|ERR> ", 0x7Cu);
          if ( (bidGblFlags & 2) != 0 )
            v4 = bidTraceHR(
                   off_1800C8490[0],
                   126985,
                   L"<CAccessorTracker::CreateInheritedAccessors|Trace|HR> ",
                   (unsigned int)v4);
        }
      }
      v18 = v4;
      throw (long *)&v18;
    }
    v5 = **((_QWORD **)this + 1);
    while ( v5 != *((_QWORD *)this + 1) )
    {
      v24 = 0;
      v20 = 0;
      pv = 0;
      v23[0] = *(_QWORD *)(v5 + 32);
      v6 = *(unsigned int *)(v5 + 40);
      v4 = (*(__int64 (__fastcall **)(__int64, __int64, int *, __int64 *, LPVOID *))(*(_QWORD *)v22 + 40LL))(
             v22,
             v23[0],
             &v24,
             &v20,
             &pv);
      if ( v4 < 0 )
        break;
      v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, LPVOID, __int64, __int64 *, _QWORD))(*(_QWORD *)v21 + 32LL))(
             v21,
             v24 & 0xFFFFFFEB | 0x10,
             v20,
             pv,
             v6,
             v23,
             0);
      v7 = (char *)pv;
      v8 = v20;
      v25 = v20;
      for ( i = 0; i < v8; ++i )
      {
        v10 = 88LL * i;
        v11 = *(_QWORD *)&v7[v10 + 32];
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        v12 = *(void **)&v7[v10 + 40];
        if ( v12 )
          CoTaskMemFree(v12);
        v13 = *(void **)&v7[v10 + 48];
        if ( v13 )
          CoTaskMemFree(v13);
        v8 = v25;
      }
      CoTaskMemFree(v7);
      if ( v4 < 0 )
        break;
      if ( !*(_BYTE *)(v5 + 25) )
      {
        if ( *(_BYTE *)(*(_QWORD *)(v5 + 16) + 25LL) )
        {
          for ( j = *(_QWORD *)(v5 + 8); !*(_BYTE *)(j + 25) && v5 == *(_QWORD *)(j + 16); j = *(_QWORD *)(j + 8) )
            v5 = j;
        }
        else
        {
          j = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,unsigned long>>>::_Min();
        }
        v5 = j;
      }
    }
  }
  catch ( long v19 )
  {
    if ( (bidGblFlags & 2) != 0 && off_1800C8B70[0] )
    {
      v16 = v19;
      bidTraceA(off_1800C8490[0], 167936, off_1800C8B70[0], v19);
    }
    else
    {
      v16 = v19;
    }
    v24 = v16;
    v4 = v24;
  }
  catch ( ... )
  {
    if ( (bidGblFlags & 2) != 0 && off_1800C8B68[0] )
      bidTraceA(off_1800C8490[0], 173056, off_1800C8B68[0], 0);
    v24 = -2147418113;
    v4 = v24;
  }
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(
                           off_1800C8490[0],
                           187401,
                           L"<CAccessorTracker::CreateInheritedAccessors|Trace|HR> ",
                           (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18006da24  mov     r11, rsp
0x18006da27  mov     [r11+8], rbx
0x18006da2b  push    rdi
0x18006da2c  push    r12
0x18006da2e  push    r13
0x18006da30  push    r14
0x18006da32  push    r15
0x18006da34  sub     rsp, 70h
0x18006da38  mov     r9, rdx
0x18006da3b  mov     r13, rcx
0x18006da3e  mov     qword ptr [r11-40h], 0
0x18006da46  mov     qword ptr [r11-38h], 0
0x18006da4e  mov     rax, [rdx]
0x18006da51  lea     r8, [r11-40h]
0x18006da55  lea     rdx, IID_IAccessor
0x18006da5c  mov     rcx, r9
0x18006da5f  mov     rax, [rax]
0x18006da62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006da67  mov     edi, eax
0x18006da69  test    eax, eax
0x18006da6b  jns     short loc_18006DAE7
0x18006da6d  mov     eax, cs:_bidGblFlags
0x18006da73  mov     bl, 2
0x18006da75  test    bl, al
0x18006da77  jz      short loc_18006DAD2
0x18006da79  mov     r8d, 7Ah ; 'z'; unsigned int
0x18006da7f  lea     rdx, aCaccessortrack_0; "<CAccessorTracker::CreateInheritedAcces"...
0x18006da86  mov     ecx, edi; int
0x18006da88  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006da8d  mov     eax, cs:_bidGblFlags
0x18006da93  test    bl, al
0x18006da95  jz      short loc_18006DAD2
0x18006da97  mov     r8d, 7Ah ; 'z'; unsigned int
0x18006da9d  lea     rdx, aCaccessortrack_0; "<CAccessorTracker::CreateInheritedAcces"...
0x18006daa4  mov     ecx, edi; int
0x18006daa6  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006daab  mov     eax, cs:_bidGblFlags
0x18006dab1  test    bl, al
0x18006dab3  jz      short loc_18006DAD2
0x18006dab5  mov     r9d, edi
0x18006dab8  lea     r8, aCaccessortrack_2; "<CAccessorTracker::CreateInheritedAcces"...
0x18006dabf  mov     edx, 1E809h
0x18006dac4  mov     rcx, cs:off_1800C8490; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006dacb  call    _bidTraceHR
0x18006dad0  mov     edi, eax
0x18006dad2  mov     [rsp+98h+pExceptionObject], edi
0x18006dad6  lea     rdx, _TI1J; pThrowInfo
0x18006dadd  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18006dae2  call    _CxxThrowException_0
0x18006dae7  mov     rcx, [r13+0]
0x18006daeb  mov     rax, [rcx]
0x18006daee  lea     r8, [rsp+98h+var_38]
0x18006daf3  lea     rdx, IID_IAccessor
0x18006dafa  mov     rax, [rax]
0x18006dafd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006db02  mov     edi, eax
0x18006db04  test    eax, eax
0x18006db06  jns     short loc_18006DB82
0x18006db08  mov     eax, cs:_bidGblFlags
0x18006db0e  mov     bl, 2
0x18006db10  test    bl, al
0x18006db12  jz      short loc_18006DB6D
0x18006db14  mov     r8d, 7Ch ; '|'; unsigned int
0x18006db1a  lea     rdx, aCaccessortrack_0; "<CAccessorTracker::CreateInheritedAcces"...
0x18006db21  mov     ecx, edi; int
0x18006db23  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006db28  mov     eax, cs:_bidGblFlags
0x18006db2e  test    bl, al
0x18006db30  jz      short loc_18006DB6D
0x18006db32  mov     r8d, 7Ch ; '|'; unsigned int
0x18006db38  lea     rdx, aCaccessortrack_0; "<CAccessorTracker::CreateInheritedAcces"...
0x18006db3f  mov     ecx, edi; int
0x18006db41  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006db46  mov     eax, cs:_bidGblFlags
0x18006db4c  test    bl, al
0x18006db4e  jz      short loc_18006DB6D
0x18006db50  mov     r9d, edi
0x18006db53  lea     r8, aCaccessortrack_2; "<CAccessorTracker::CreateInheritedAcces"...
0x18006db5a  mov     edx, 1F009h
0x18006db5f  mov     rcx, cs:off_1800C8490; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006db66  call    _bidTraceHR
0x18006db6b  mov     edi, eax
0x18006db6d  mov     [rsp+98h+var_54], edi
0x18006db71  lea     rdx, _TI1J; pThrowInfo
0x18006db78  lea     rcx, [rsp+98h+var_54]; pExceptionObject
0x18006db7d  call    _CxxThrowException_0
0x18006db82  mov     rbx, [r13+8]
0x18006db86  mov     rbx, [rbx]
0x18006db89  cmp     rbx, [r13+8]
0x18006db8d  jz      loc_18006DCE7
0x18006db93  mov     [rsp+98h+arg_8], 0
0x18006db9e  mov     [rsp+98h+var_48], 0
0x18006dba7  mov     [rsp+98h+pv], 0
0x18006dbb3  mov     rdx, [rbx+20h]
0x18006dbb7  mov     [rsp+98h+var_30], rdx
0x18006dbbc  mov     r14d, [rbx+28h]
0x18006dbc0  mov     rcx, [rsp+98h+var_38]
0x18006dbc5  mov     rax, [rcx]
0x18006dbc8  lea     r8, [rsp+98h+pv]
0x18006dbd0  mov     [rsp+98h+var_78], r8
0x18006dbd5  lea     r9, [rsp+98h+var_48]
0x18006dbda  lea     r8, [rsp+98h+arg_8]
0x18006dbe2  mov     rax, [rax+28h]
0x18006dbe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dbeb  mov     edi, eax
0x18006dbed  test    eax, eax
0x18006dbef  js      loc_18006DCE7
0x18006dbf5  mov     rcx, [rsp+98h+var_40]
0x18006dbfa  mov     rax, [rcx]
0x18006dbfd  mov     edx, [rsp+98h+arg_8]
0x18006dc04  and     edx, 0FFFFFFFBh
0x18006dc07  or      edx, 10h
0x18006dc0a  mov     [rsp+98h+var_68], 0
0x18006dc13  lea     r9, [rsp+98h+var_30]
0x18006dc18  mov     [rsp+98h+var_70], r9
0x18006dc1d  mov     [rsp+98h+var_78], r14
0x18006dc22  mov     r9, [rsp+98h+pv]
0x18006dc2a  mov     r8, [rsp+98h+var_48]
0x18006dc2f  mov     rax, [rax+20h]
0x18006dc33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dc38  mov     edi, eax
0x18006dc3a  mov     r15, [rsp+98h+pv]
0x18006dc42  mov     eax, dword ptr [rsp+98h+var_48]
0x18006dc46  mov     [rsp+98h+arg_10], eax
0x18006dc4d  xor     r14d, r14d
0x18006dc50  cmp     r14d, eax
0x18006dc53  jnb     short loc_18006DC9E
0x18006dc55  mov     eax, r14d
0x18006dc58  imul    r12, rax, 58h ; 'X'
0x18006dc5c  mov     rcx, [r12+r15+20h]
0x18006dc61  test    rcx, rcx
0x18006dc64  jz      short loc_18006DC72
0x18006dc66  mov     rax, [rcx]
0x18006dc69  mov     rax, [rax+10h]
0x18006dc6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dc72  mov     rcx, [r12+r15+28h]; pv
0x18006dc77  test    rcx, rcx
0x18006dc7a  jz      short loc_18006DC82
0x18006dc7c  call    cs:__imp_CoTaskMemFree
0x18006dc82  mov     rcx, [r12+r15+30h]; pv
0x18006dc87  test    rcx, rcx
0x18006dc8a  jz      short loc_18006DC92
0x18006dc8c  call    cs:__imp_CoTaskMemFree
0x18006dc92  inc     r14d
0x18006dc95  mov     eax, [rsp+98h+arg_10]
0x18006dc9c  jmp     short loc_18006DC50
0x18006dc9e  mov     rcx, r15; pv
0x18006dca1  call    cs:__imp_CoTaskMemFree
0x18006dca7  test    edi, edi
0x18006dca9  js      short loc_18006DCE7
0x18006dcab  cmp     byte ptr [rbx+19h], 0
0x18006dcaf  jnz     loc_18006DB89
0x18006dcb5  mov     rcx, [rbx+10h]
0x18006dcb9  cmp     byte ptr [rcx+19h], 0
0x18006dcbd  jnz     short loc_18006DCCC
0x18006dcbf  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KK@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CB_KK@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ulong>>>::_Min(std::_Tree_node<std::pair<unsigned __int64 const,ulong>,void *> *)
0x18006dcc4  mov     rbx, rax
0x18006dcc7  jmp     loc_18006DB89
0x18006dccc  mov     rax, [rbx+8]
0x18006dcd0  jmp     short loc_18006DCDF
0x18006dcd2  cmp     rbx, [rax+10h]
0x18006dcd6  jnz     short loc_18006DCC4
0x18006dcd8  mov     rbx, rax
0x18006dcdb  mov     rax, [rax+8]
0x18006dcdf  cmp     byte ptr [rax+19h], 0
0x18006dce3  jz      short loc_18006DCD2
0x18006dce5  jmp     short loc_18006DCC4
0x18006dce7  jmp     short loc_18006DCF2
0x18006dce9  jmp     short $+2
0x18006dceb  mov     edi, [rsp+98h+arg_8]
0x18006dcf2  mov     rcx, [rsp+98h+var_40]
0x18006dcf7  test    rcx, rcx
0x18006dcfa  jz      short loc_18006DD08
0x18006dcfc  mov     rax, [rcx]
0x18006dcff  mov     rax, [rax+10h]
0x18006dd03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dd08  mov     rcx, [rsp+98h+var_38]
0x18006dd0d  test    rcx, rcx
0x18006dd10  jz      short loc_18006DD1E
0x18006dd12  mov     rax, [rcx]
0x18006dd15  mov     rax, [rax+10h]
0x18006dd19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dd1e  mov     bl, 2
0x18006dd20  test    byte ptr cs:_bidGblFlags, bl
0x18006dd26  jz      short loc_18006DD45
0x18006dd28  mov     r9d, edi
0x18006dd2b  lea     r8, aCaccessortrack_2; "<CAccessorTracker::CreateInheritedAcces"...
0x18006dd32  mov     edx, 2DC09h
0x18006dd37  mov     rcx, cs:off_1800C8490; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006dd3e  call    _bidTraceHR
0x18006dd43  mov     edi, eax
0x18006dd45  mov     eax, edi
0x18006dd47  mov     rbx, [rsp+98h+arg_0]
0x18006dd4f  add     rsp, 70h
0x18006dd53  pop     r15
0x18006dd55  pop     r14
0x18006dd57  pop     r13
0x18006dd59  pop     r12
0x18006dd5b  pop     rdi
0x18006dd5c  retn
```
