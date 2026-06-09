# BDATuningModel::CSystemTuningSpaces::TuningSpacesForName(ushort *,ITuningSpaces * *)

- ea: `0x1800458b0`
- end: `0x180045d0c`
- name: `?TuningSpacesForName@CSystemTuningSpaces@BDATuningModel@@UEAAJPEAGPEAPEAUITuningSpaces@@@Z`
- size: `1116`
- prototype: `__int64 __fastcall(BDATuningModel::CSystemTuningSpaces *__hidden this, unsigned __int16 *, struct ITuningSpaces **)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180004b54`
- `0x180006b38`
- `0x18000e294`
- `0x18000ff74`
- `0x1800382d4`
- `0x180038680`
- `0x180038a00`
- `0x180039744`
- `0x1800397f8`
- `0x180039840`
- `0x1800458b0`
- `0x1800499d8`
- `0x180049a68`
- `0x1800f8010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800459d8`
- `ole32!CoCreateInstance` at `0x1800459d8`
- `OLEAUT32!__imp_SysFreeString` at `0x180045b40`
- `OLEAUT32!__imp_SysFreeString` at `0x180045bda`
- `OLEAUT32!__imp_SysFreeString` at `0x180045c62`
- `OLEAUT32!__imp_SysFreeString` at `0x180045cb2`
- `OLEAUT32!__imp_SysFreeString` at `0x180045b40`
- `OLEAUT32!__imp_SysFreeString` at `0x180045bda`
- `OLEAUT32!__imp_SysFreeString` at `0x180045c62`
- `OLEAUT32!__imp_SysFreeString` at `0x180045cb2`
- `KERNEL32!LeaveCriticalSection` at `0x180045991`
- `KERNEL32!LeaveCriticalSection` at `0x180045991`
- `KERNEL32!EnterCriticalSection` at `0x180045982`
- `KERNEL32!EnterCriticalSection` at `0x180045982`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall BDATuningModel::CSystemTuningSpaces::TuningSpacesForName(
        BDATuningModel::CSystemTuningSpaces *this,
        unsigned __int16 *a2,
        struct ITuningSpaces **a3)
{
  __int64 result; // rax
  BDATuningModel::CBaseThread *v7; // rbx
  int v8; // ebx
  __int64 v9; // rbx
  struct _RTL_CRITICAL_SECTION *v10; // rdi
  HRESULT Instance; // edi
  CTuningSpaces *v12; // rdi
  char *v13; // r14
  _QWORD *v14; // rax
  __int64 v15; // r8
  struct ITuningSpaces *v16; // rcx
  __int64 v17; // rsi
  int v18; // ebx
  __int64 v19; // rbx
  __int64 v20; // rax
  unsigned int v21; // [rsp+30h] [rbp-68h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-60h] BYREF
  __int64 v23; // [rsp+40h] [rbp-58h] BYREF
  __int64 v24; // [rsp+48h] [rbp-50h] BYREF
  __int64 i; // [rsp+50h] [rbp-48h] BYREF
  _BYTE v26[8]; // [rsp+58h] [rbp-40h] BYREF
  ComException *v27; // [rsp+60h] [rbp-38h] BYREF
  std::bad_alloc *v28; // [rsp+68h] [rbp-30h] BYREF
  std::exception *v29; // [rsp+70h] [rbp-28h] BYREF
  CTuningSpaces *v30; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v31; // [rsp+B8h] [rbp+20h] BYREF

  if ( !a3 )
    return 2147500035LL;
  try
  {
    v31 = 0;
    if ( !*((_DWORD *)this + 28) )
    {
      v7 = (BDATuningModel::CBaseThread *)operator new(0x90u);
      BDATuningModel::CBaseThread::CBaseThread(v7);
      *(_QWORD *)v7 = &BDATuningModel::CRegExThread::`vftable';
      *((_QWORD *)v7 + 16) = 0;
      *((_DWORD *)v7 + 34) = 0;
      *((_QWORD *)this + 15) = v7;
      if ( !BDATuningModel::CBaseThread::Create(v7) )
      {
LABEL_5:
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v31);
        return 2147549183LL;
      }
      v8 = BDATuningModel::CBaseThread::CallWorker(*((BDATuningModel::CBaseThread **)this + 15), 1u);
      if ( v8 < 0 )
      {
LABEL_13:
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v31);
        return (unsigned int)v8;
      }
      v9 = *((_QWORD *)this + 15);
      v10 = (struct _RTL_CRITICAL_SECTION *)(v9 + 88);
      EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 88));
      LODWORD(v9) = *(_DWORD *)(v9 + 136);
      LeaveCriticalSection(v10);
      *((_DWORD *)this + 28) = v9;
      if ( !(_DWORD)v9 )
        goto LABEL_5;
    }
    if ( !*((_QWORD *)this + 13) )
    {
      Instance = CoCreateInstance(
                   &CLSID_StdGlobalInterfaceTable,
                   0,
                   1u,
                   &GUID_00000146_0000_0000_c000_000000000046,
                   (LPVOID *)this + 13);
      if ( Instance < 0 )
      {
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v31);
        return (unsigned int)Instance;
      }
    }
    v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, __int64 *))(**((_QWORD **)this + 13) + 40LL))(
           *((_QWORD *)this + 13),
           *((unsigned int *)this + 28),
           &GUID_3f4daca0_160d_11d2_a8e9_00104b365c9f,
           &v31);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v31 + 64LL))(v31, a2);
      if ( v8 >= 0 )
      {
        v30 = (CTuningSpaces *)operator new(0x68u);
        v12 = CTuningSpaces::CTuningSpaces(v30);
        v13 = (char *)this + 8;
        for ( i = **((_QWORD **)this + 1);
              ;
              std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,ATL::CComQIPtr<IDispatch,&__s_GUID const _GUID_00020400_0000_0000_c000_000000000046>>>>,std::_Iterator_base0>::operator++(&i) )
        {
          v14 = (_QWORD *)std::_Tree<std::_Tmap_traits<ATL::CComBSTR,unsigned long,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,unsigned long>>,0>>::end(
                            v13,
                            v26);
          if ( v15 == *v14 )
            break;
          v17 = std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,ATL::CComVariant>>>>::operator*(&i);
          if ( ((*(_WORD *)(v17 + 8) - 9) & 0xFFFB) != 0 )
          {
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v31);
            return 2147549183LL;
          }
          ATL::CComQIPtr<ITuningSpace,&__s_GUID const _GUID_061c6e30_e622_11d2_9493_00c04f72d980>::CComQIPtr<ITuningSpace,&__s_GUID const _GUID_061c6e30_e622_11d2_9493_00c04f72d980>(
            &v23,
            *(_QWORD *)(v17 + 16));
          bstrString = 0;
          if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v23 + 72LL))(v23, &bstrString) < 0 )
          {
            SysFreeString(bstrString);
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v23);
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v31);
            return 2147549183LL;
          }
          v24 = 0;
          LOWORD(v30) = 0;
          if ( (*(int (__fastcall **)(__int64, BSTR, CTuningSpaces **))(*(_QWORD *)v31 + 112LL))(v31, bstrString, &v30) >= 0
            && (_WORD)v30 == 0xFFFF )
          {
            goto LABEL_30;
          }
          if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v23 + 56LL))(v23, &bstrString) < 0 )
          {
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v24);
            SysFreeString(bstrString);
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v23);
            ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v31);
            return 2147549183LL;
          }
          if ( (*(int (__fastcall **)(__int64, BSTR, CTuningSpaces **))(*(_QWORD *)v31 + 112LL))(v31, bstrString, &v30) >= 0
            && (_WORD)v30 == 0xFFFF )
          {
LABEL_30:
            v18 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 200LL))(v23, &v24);
            if ( v18 < 0 )
            {
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v24);
              SysFreeString(bstrString);
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v23);
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v31);
              return (unsigned int)v18;
            }
            v19 = v24;
            v20 = std::map<unsigned long,ATL::CComVariant>::operator[]((char *)v12 + 32, v17);
            ATL::CComVariant::operator=(v20, v19);
          }
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v24);
          SysFreeString(bstrString);
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v23);
        }
        if ( v12 )
          v16 = (struct ITuningSpaces *)((char *)v12 + 24);
        else
          v16 = 0;
        *a3 = v16;
        ((void (__fastcall *)(struct ITuningSpaces *))v16->lpVtbl->AddRef)(v16);
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v31);
        return 0;
      }
    }
    goto LABEL_13;
  }
  catch ( long v21 )
  {
    return v21;
  }
  catch ( ComException *v27 )
  {
    return *(unsigned int *)v27;
  }
  catch ( std::bad_alloc *v28 )
  {
    return 2147942414LL;
  }
  catch ( std::exception *v29 )
  {
    return 2147549183LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800458b0  mov     [rsp+arg_0], rbx
0x1800458b5  mov     [rsp+arg_8], rsi
0x1800458ba  push    rdi
0x1800458bb  push    r14
0x1800458bd  push    r15
0x1800458bf  sub     rsp, 80h
0x1800458c6  mov     r15, r8
0x1800458c9  mov     r14, rdx
0x1800458cc  mov     rsi, rcx
0x1800458cf  test    r8, r8
0x1800458d2  jnz     short loc_1800458DE
0x1800458d4  mov     eax, 80004003h
0x1800458d9  jmp     loc_180045CF2
0x1800458de  mov     [rsp+98h+arg_18], 0
0x1800458ea  cmp     dword ptr [rcx+70h], 0
0x1800458ee  jnz     loc_1800459B5
0x1800458f4  mov     ecx, 90h; Size
0x1800458f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800458fe  mov     rbx, rax
0x180045901  mov     rcx, rax; this
0x180045904  call    ??0CBaseThread@BDATuningModel@@QEAA@K@Z; BDATuningModel::CBaseThread::CBaseThread(ulong)
0x180045909  lea     rax, ??_7CRegExThread@BDATuningModel@@6B@; const BDATuningModel::CRegExThread::`vftable'
0x180045910  mov     [rbx], rax
0x180045913  mov     qword ptr [rbx+80h], 0
0x18004591e  mov     dword ptr [rbx+88h], 0
0x180045928  mov     [rsi+78h], rbx
0x18004592c  mov     rcx, rbx; this
0x18004592f  call    ?Create@CBaseThread@BDATuningModel@@QEAAHXZ; BDATuningModel::CBaseThread::Create(void)
0x180045934  test    eax, eax
0x180045936  jnz     short loc_18004594F
0x180045938  lea     rcx, [rsp+98h+arg_18]
0x180045940  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180045945  mov     eax, 8000FFFFh
0x18004594a  jmp     loc_180045CF2
0x18004594f  mov     edx, 1; unsigned int
0x180045954  mov     rcx, [rsi+78h]; this
0x180045958  call    ?CallWorker@CBaseThread@BDATuningModel@@QEAAKK@Z; BDATuningModel::CBaseThread::CallWorker(ulong)
0x18004595d  mov     ebx, eax
0x18004595f  test    eax, eax
0x180045961  jns     short loc_180045977
0x180045963  lea     rcx, [rsp+98h+arg_18]
0x18004596b  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180045970  mov     eax, ebx
0x180045972  jmp     loc_180045CF2
0x180045977  mov     rbx, [rsi+78h]
0x18004597b  lea     rdi, [rbx+58h]
0x18004597f  mov     rcx, rdi; lpCriticalSection
0x180045982  call    cs:__imp_EnterCriticalSection
0x180045988  mov     ebx, [rbx+88h]
0x18004598e  mov     rcx, rdi; lpCriticalSection
0x180045991  call    cs:__imp_LeaveCriticalSection
0x180045997  mov     [rsi+70h], ebx
0x18004599a  test    ebx, ebx
0x18004599c  jnz     short loc_1800459B5
0x18004599e  lea     rcx, [rsp+98h+arg_18]
0x1800459a6  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800459ab  mov     eax, 8000FFFFh
0x1800459b0  jmp     loc_180045CF2
0x1800459b5  lea     rbx, [rsi+68h]
0x1800459b9  cmp     qword ptr [rbx], 0
0x1800459bd  jnz     short loc_1800459F8
0x1800459bf  mov     [rsp+98h+ppv], rbx; ppv
0x1800459c4  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800459cb  xor     edx, edx; pUnkOuter
0x1800459cd  lea     r8d, [rdx+1]; dwClsContext
0x1800459d1  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1800459d8  call    cs:__imp_CoCreateInstance
0x1800459de  mov     edi, eax
0x1800459e0  test    eax, eax
0x1800459e2  jns     short loc_1800459F8
0x1800459e4  lea     rcx, [rsp+98h+arg_18]
0x1800459ec  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800459f1  mov     eax, edi
0x1800459f3  jmp     loc_180045CF2
0x1800459f8  mov     rcx, [rbx]
0x1800459fb  mov     rax, [rcx]
0x1800459fe  lea     r9, [rsp+98h+arg_18]
0x180045a06  lea     r8, _GUID_3f4daca0_160d_11d2_a8e9_00104b365c9f
0x180045a0d  mov     edx, [rsi+70h]
0x180045a10  mov     rax, [rax+28h]
0x180045a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a19  mov     ebx, eax
0x180045a1b  test    eax, eax
0x180045a1d  jns     short loc_180045A33
0x180045a1f  lea     rcx, [rsp+98h+arg_18]
0x180045a27  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180045a2c  mov     eax, ebx
0x180045a2e  jmp     loc_180045CF2
0x180045a33  mov     rcx, [rsp+98h+arg_18]
0x180045a3b  mov     rax, [rcx]
0x180045a3e  mov     rdx, r14
0x180045a41  mov     rax, [rax+40h]
0x180045a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a4a  mov     ebx, eax
0x180045a4c  test    eax, eax
0x180045a4e  jns     short loc_180045A64
0x180045a50  lea     rcx, [rsp+98h+arg_18]
0x180045a58  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180045a5d  mov     eax, ebx
0x180045a5f  jmp     loc_180045CF2
0x180045a64  mov     ecx, 68h ; 'h'; Size
0x180045a69  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045a6e  mov     [rsp+98h+arg_10], rax
0x180045a76  mov     rcx, rax; this
0x180045a79  call    ??0CTuningSpaces@@QEAA@XZ; CTuningSpaces::CTuningSpaces(void)
0x180045a7e  mov     rdi, rax
0x180045a81  lea     r14, [rsi+8]
0x180045a85  mov     r8, [r14]
0x180045a88  mov     r8, [r8]
0x180045a8b  mov     [rsp+98h+var_48], r8
0x180045a90  lea     rdx, [rsp+98h+var_40]
0x180045a95  mov     rcx, r14
0x180045a98  call    ?end@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@KU?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@K@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@K@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ulong,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ulong>>,0>>::end(void)
0x180045a9d  cmp     r8, [rax]
0x180045aa0  jnz     short loc_180045AD3
0x180045aa2  test    rdi, rdi
0x180045aa5  jz      short loc_180045AAD
0x180045aa7  lea     rcx, [rdi+18h]
0x180045aab  jmp     short loc_180045AAF
0x180045aad  xor     ecx, ecx
0x180045aaf  mov     [r15], rcx
0x180045ab2  mov     rax, [rcx]
0x180045ab5  mov     rax, [rax+8]
0x180045ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045abe  nop
0x180045abf  lea     rcx, [rsp+98h+arg_18]
0x180045ac7  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180045acc  xor     eax, eax
0x180045ace  jmp     loc_180045CF2
0x180045ad3  lea     rcx, [rsp+98h+var_48]
0x180045ad8  call    ??D?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKVCComVariant@ATL@@@std@@@std@@@std@@@std@@QEBAAEAU?$pair@$$CBKVCComVariant@ATL@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,ATL::CComVariant>>>>::operator*(void)
0x180045add  mov     rsi, rax
0x180045ae0  movzx   ecx, word ptr [rax+8]
0x180045ae4  sub     cx, 9
0x180045ae8  mov     eax, 0FFFBh
0x180045aed  test    ax, cx
0x180045af0  jz      short loc_180045B09
0x180045af2  lea     rcx, [rsp+98h+arg_18]
0x180045afa  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180045aff  mov     eax, 8000FFFFh
0x180045b04  jmp     loc_180045CF2
0x180045b09  mov     rdx, [rsi+10h]
0x180045b0d  lea     rcx, [rsp+98h+var_58]
0x180045b12  call    ??0?$CComQIPtr@UITuningSpace@@$1?_GUID_061c6e30_e622_11d2_9493_00c04f72d980@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<ITuningSpace,&__s_GUID const _GUID_061c6e30_e622_11d2_9493_00c04f72d980>::CComQIPtr<ITuningSpace,&__s_GUID const _GUID_061c6e30_e622_11d2_9493_00c04f72d980>(IUnknown *)
0x180045b17  nop
0x180045b18  mov     [rsp+98h+bstrString], 0
0x180045b21  mov     rcx, [rsp+98h+var_58]
0x180045b26  mov     rax, [rcx]
0x180045b29  lea     rdx, [rsp+98h+bstrString]
0x180045b2e  mov     rax, [rax+48h]
0x180045b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b37  test    eax, eax
0x180045b39  jns     short loc_180045B69
0x180045b3b  mov     rcx, [rsp+98h+bstrString]; bstrString
0x180045b40  call    cs:__imp_SysFreeString
0x180045b46  nop
0x180045b47  lea     rcx, [rsp+98h+var_58]
0x180045b4c  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180045b51  nop
0x180045b52  lea     rcx, [rsp+98h+arg_18]
0x180045b5a  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180045b5f  mov     eax, 8000FFFFh
0x180045b64  jmp     loc_180045CF2
0x180045b69  mov     [rsp+98h+var_50], 0
0x180045b72  xor     eax, eax
0x180045b74  mov     word ptr [rsp+98h+arg_10], ax
0x180045b7c  mov     rcx, [rsp+98h+arg_18]
0x180045b84  mov     rax, [rcx]
0x180045b87  lea     r8, [rsp+98h+arg_10]
0x180045b8f  mov     rdx, [rsp+98h+bstrString]
0x180045b94  mov     rax, [rax+70h]
0x180045b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b9d  test    eax, eax
0x180045b9f  js      short loc_180045BB0
0x180045ba1  cmp     word ptr [rsp+98h+arg_10], 0FFFFh
0x180045baa  jz      loc_180045C33
0x180045bb0  mov     rcx, [rsp+98h+var_58]
0x180045bb5  mov     rax, [rcx]
0x180045bb8  lea     rdx, [rsp+98h+bstrString]
0x180045bbd  mov     rax, [rax+38h]
0x180045bc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045bc6  test    eax, eax
0x180045bc8  jns     short loc_180045C03
0x180045bca  lea     rcx, [rsp+98h+var_50]
0x180045bcf  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180045bd4  nop
0x180045bd5  mov     rcx, [rsp+98h+bstrString]; bstrString
0x180045bda  call    cs:__imp_SysFreeString
0x180045be0  nop
0x180045be1  lea     rcx, [rsp+98h+var_58]
0x180045be6  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180045beb  nop
0x180045bec  lea     rcx, [rsp+98h+arg_18]
0x180045bf4  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180045bf9  mov     eax, 8000FFFFh
0x180045bfe  jmp     loc_180045CF2
0x180045c03  mov     rcx, [rsp+98h+arg_18]
0x180045c0b  mov     rax, [rcx]
0x180045c0e  lea     r8, [rsp+98h+arg_10]
0x180045c16  mov     rdx, [rsp+98h+bstrString]
0x180045c1b  mov     rax, [rax+70h]
0x180045c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c24  test    eax, eax
0x180045c26  js      short loc_180045CA2
0x180045c28  cmp     word ptr [rsp+98h+arg_10], 0FFFFh
0x180045c31  jnz     short loc_180045CA2
0x180045c33  mov     rcx, [rsp+98h+var_58]
0x180045c38  mov     rax, [rcx]
0x180045c3b  lea     rdx, [rsp+98h+var_50]
0x180045c40  mov     rax, [rax+0C8h]
0x180045c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045c4c  mov     ebx, eax
0x180045c4e  test    eax, eax
0x180045c50  jns     short loc_180045C85
0x180045c52  lea     rcx, [rsp+98h+var_50]
0x180045c57  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180045c5c  nop
0x180045c5d  mov     rcx, [rsp+98h+bstrString]; bstrString
0x180045c62  call    cs:__imp_SysFreeString
0x180045c68  nop
0x180045c69  lea     rcx, [rsp+98h+var_58]
0x180045c6e  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180045c73  nop
0x180045c74  lea     rcx, [rsp+98h+arg_18]
0x180045c7c  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180045c81  mov     eax, ebx
0x180045c83  jmp     short loc_180045CF2
0x180045c85  mov     rbx, [rsp+98h+var_50]
0x180045c8a  lea     rcx, [rdi+20h]
0x180045c8e  mov     rdx, rsi
0x180045c91  call    ??A?$map@KVCComVariant@ATL@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKVCComVariant@ATL@@@std@@@4@@std@@QEAAAEAVCComVariant@ATL@@$$QEAK@Z; std::map<ulong,ATL::CComVariant>::operator[](ulong &&)
0x180045c96  mov     rdx, rbx
0x180045c99  mov     rcx, rax
0x180045c9c  call    ??4CComVariant@ATL@@QEAAAEAV01@PEAUIDispatch@@@Z; ATL::CComVariant::operator=(IDispatch *)
0x180045ca1  nop
0x180045ca2  lea     rcx, [rsp+98h+var_50]
0x180045ca7  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180045cac  nop
0x180045cad  mov     rcx, [rsp+98h+bstrString]; bstrString
0x180045cb2  call    cs:__imp_SysFreeString
0x180045cb8  nop
0x180045cb9  lea     rcx, [rsp+98h+var_58]
0x180045cbe  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180045cc3  lea     rcx, [rsp+98h+var_48]
0x180045cc8  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$CComQIPtr@UIDispatch@@$1?_GUID_00020400_0000_0000_c000_000000000046@@3U__s_GUID@@B@ATL@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,ATL::CComQIPtr<IDispatch,&__s_GUID const _GUID_00020400_0000_0000_c000_000000000046>>>>,std::_Iterator_base0>::operator++(void)
0x180045ccd  mov     r8, [rsp+98h+var_48]
0x180045cd2  jmp     loc_180045A90
0x180045cd7  mov     eax, [rsp+98h+var_68]
0x180045cdb  jmp     short loc_180045CF2
0x180045cdd  mov     eax, dword ptr [rsp+98h+arg_10]
0x180045ce4  jmp     short loc_180045CF2
0x180045ce6  mov     eax, 8007000Eh
0x180045ceb  jmp     short loc_180045CF2
0x180045ced  mov     eax, 8000FFFFh
0x180045cf2  lea     r11, [rsp+98h+var_18]
0x180045cfa  mov     rbx, [r11+20h]
0x180045cfe  mov     rsi, [r11+28h]
0x180045d02  mov     rsp, r11
0x180045d05  pop     r15
0x180045d07  pop     r14
0x180045d09  pop     rdi
0x180045d0a  retn
```
