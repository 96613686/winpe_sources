# CComponents::Load(IStream *)

- ea: `0x1800352d0`
- end: `0x180035537`
- name: `?Load@CComponents@@UEAAJPEAUIStream@@@Z`
- size: `615`
- prototype: `__int64 __fastcall(CComponents *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018260`

## callees

- `0x180004640`
- `0x180006b38`
- `0x18000a3ec`
- `0x180013ff8`
- `0x18002a3f8`
- `0x1800326ac`
- `0x1800352d0`
- `0x1800f8010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800353f1`
- `ole32!CoCreateInstance` at `0x1800353f1`
- `KERNEL32!LeaveCriticalSection` at `0x18003539e`
- `KERNEL32!LeaveCriticalSection` at `0x1800353bc`
- `KERNEL32!LeaveCriticalSection` at `0x18003540b`
- `KERNEL32!LeaveCriticalSection` at `0x180035449`
- `KERNEL32!LeaveCriticalSection` at `0x18003548c`
- `KERNEL32!LeaveCriticalSection` at `0x1800354ea`
- `KERNEL32!LeaveCriticalSection` at `0x18003539e`
- `KERNEL32!LeaveCriticalSection` at `0x1800353bc`
- `KERNEL32!LeaveCriticalSection` at `0x18003540b`
- `KERNEL32!LeaveCriticalSection` at `0x180035449`
- `KERNEL32!LeaveCriticalSection` at `0x18003548c`
- `KERNEL32!LeaveCriticalSection` at `0x1800354ea`
- `KERNEL32!EnterCriticalSection` at `0x180035354`
- `KERNEL32!EnterCriticalSection` at `0x180035354`

## pseudocode

```c
__int64 __fastcall CComponents::Load(CComponents *this, struct IStream *a2)
{
  __int64 result; // rax
  int i; // r14d
  int v6; // esi
  HRESULT v7; // esi
  int v8; // esi
  int v9; // [rsp+30h] [rbp-78h] BYREF
  int v10; // [rsp+34h] [rbp-74h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-70h] BYREF
  _QWORD v12[4]; // [rsp+40h] [rbp-68h] BYREF
  IID rclsid; // [rsp+60h] [rbp-48h] BYREF

  v9 = 0;
  v10 = 0;
  result = ((__int64 (__fastcall *)(struct IStream *, int *, __int64, int *))a2->lpVtbl->Read)(a2, &v9, 4, &v10);
  if ( (int)result >= 0 )
  {
    if ( v10 == 4 )
    {
      v12[2] = (char *)this + 128;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
      for ( i = 0; i < v9; ++i )
      {
        rclsid = GUID_NULL;
        v6 = ((__int64 (__fastcall *)(struct IStream *, IID *, __int64, int *))a2->lpVtbl->Read)(a2, &rclsid, 16, &v10);
        if ( v6 < 0 )
        {
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
          return (unsigned int)v6;
        }
        if ( !IsValidCLSID(&rclsid) )
        {
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
          return 2147942405LL;
        }
        ppv = 0;
        v7 = CoCreateInstance(&rclsid, 0, 3u, &IID_IPersistStreamInit, &ppv);
        if ( v7 < 0 )
        {
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
          return (unsigned int)v7;
        }
        ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>(
          v12,
          ppv);
        if ( !v12[0] )
        {
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v12);
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
          return 2147549183LL;
        }
        v8 = (*(__int64 (__fastcall **)(LPVOID, struct IStream *))(*(_QWORD *)ppv + 40LL))(ppv, a2);
        if ( v8 < 0 )
        {
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v12);
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
          return (unsigned int)v8;
        }
        if ( *((_QWORD *)this + 14) == *((_QWORD *)this + 15) )
        {
          std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>::_Emplace_reallocate<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980> const &>(
            (char *)this + 104,
            *((_QWORD *)this + 14),
            v12);
        }
        else
        {
          ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>(
            *((_QWORD *)this + 14),
            v12);
          *((_QWORD *)this + 14) += 8LL;
        }
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v12);
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
      }
      *((_BYTE *)this + 96) = 1;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
      return 0;
    }
    else
    {
      return 2147549183LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800352d0  mov     r11, rsp
0x1800352d3  mov     [r11+18h], rbx
0x1800352d7  mov     [r11+20h], rsi
0x1800352db  push    rdi
0x1800352dc  push    r14
0x1800352de  push    r15
0x1800352e0  sub     rsp, 90h
0x1800352e7  mov     rax, cs:__security_cookie
0x1800352ee  xor     rax, rsp
0x1800352f1  mov     [rsp+0A8h+var_28], rax
0x1800352f9  mov     r15, rdx
0x1800352fc  mov     rdi, rcx
0x1800352ff  mov     [rsp+0A8h+var_78], 0
0x180035307  mov     [rsp+0A8h+var_74], 0
0x18003530f  mov     rax, [rdx]
0x180035312  lea     r9, [r11-74h]
0x180035316  mov     r8d, 4
0x18003531c  lea     rdx, [r11-78h]
0x180035320  mov     rcx, r15
0x180035323  mov     rax, [rax+18h]
0x180035327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003532c  test    eax, eax
0x18003532e  js      loc_18003550D
0x180035334  cmp     [rsp+0A8h+var_74], 4
0x180035339  jz      short loc_180035345
0x18003533b  mov     eax, 8000FFFFh
0x180035340  jmp     loc_18003550D
0x180035345  lea     rbx, [rdi+80h]
0x18003534c  mov     [rsp+0A8h+var_58], rbx
0x180035351  mov     rcx, rbx; lpCriticalSection
0x180035354  call    cs:__imp_EnterCriticalSection
0x18003535a  nop
0x18003535b  xor     r14d, r14d
0x18003535e  cmp     r14d, [rsp+0A8h+var_78]
0x180035363  jge     loc_1800354E3
0x180035369  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180035370  movdqu  xmmword ptr [rsp+0A8h+rclsid.Data1], xmm0
0x180035376  mov     rax, [r15]
0x180035379  lea     r9, [rsp+0A8h+var_74]
0x18003537e  mov     r8d, 10h
0x180035384  lea     rdx, [rsp+0A8h+rclsid]
0x180035389  mov     rcx, r15
0x18003538c  mov     rax, [rax+18h]
0x180035390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035395  mov     esi, eax
0x180035397  test    eax, eax
0x180035399  jns     short loc_1800353AB
0x18003539b  mov     rcx, rbx; lpCriticalSection
0x18003539e  call    cs:__imp_LeaveCriticalSection
0x1800353a4  mov     eax, esi
0x1800353a6  jmp     loc_18003550D
0x1800353ab  lea     rcx, [rsp+0A8h+rclsid]; struct _GUID *
0x1800353b0  call    ?IsValidCLSID@@YAHAEBU_GUID@@@Z; IsValidCLSID(_GUID const &)
0x1800353b5  test    eax, eax
0x1800353b7  jnz     short loc_1800353CC
0x1800353b9  mov     rcx, rbx; lpCriticalSection
0x1800353bc  call    cs:__imp_LeaveCriticalSection
0x1800353c2  mov     eax, 80070005h
0x1800353c7  jmp     loc_18003550D
0x1800353cc  mov     [rsp+0A8h+var_70], 0
0x1800353d5  lea     rax, [rsp+0A8h+var_70]
0x1800353da  mov     [rsp+0A8h+ppv], rax; ppv
0x1800353df  lea     r9, IID_IPersistStreamInit; riid
0x1800353e6  xor     edx, edx; pUnkOuter
0x1800353e8  lea     r8d, [rdx+3]; dwClsContext
0x1800353ec  lea     rcx, [rsp+0A8h+rclsid]; rclsid
0x1800353f1  call    cs:__imp_CoCreateInstance
0x1800353f7  mov     esi, eax
0x1800353f9  test    eax, eax
0x1800353fb  jns     short loc_180035418
0x1800353fd  lea     rcx, [rsp+0A8h+var_70]
0x180035402  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180035407  nop
0x180035408  mov     rcx, rbx; lpCriticalSection
0x18003540b  call    cs:__imp_LeaveCriticalSection
0x180035411  mov     eax, esi
0x180035413  jmp     loc_18003550D
0x180035418  mov     rdx, [rsp+0A8h+var_70]
0x18003541d  lea     rcx, [rsp+0A8h+var_68]
0x180035422  call    ??0?$CComQIPtr@UIComponent@@$1?_GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>(IUnknown *)
0x180035427  nop
0x180035428  cmp     [rsp+0A8h+var_68], 0
0x18003542e  jnz     short loc_180035459
0x180035430  lea     rcx, [rsp+0A8h+var_68]
0x180035435  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18003543a  nop
0x18003543b  lea     rcx, [rsp+0A8h+var_70]
0x180035440  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180035445  nop
0x180035446  mov     rcx, rbx; lpCriticalSection
0x180035449  call    cs:__imp_LeaveCriticalSection
0x18003544f  mov     eax, 8000FFFFh
0x180035454  jmp     loc_18003550D
0x180035459  mov     rcx, [rsp+0A8h+var_70]
0x18003545e  mov     rax, [rcx]
0x180035461  mov     rdx, r15
0x180035464  mov     rax, [rax+28h]
0x180035468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003546d  mov     esi, eax
0x18003546f  test    eax, eax
0x180035471  jns     short loc_180035496
0x180035473  lea     rcx, [rsp+0A8h+var_68]
0x180035478  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18003547d  nop
0x18003547e  lea     rcx, [rsp+0A8h+var_70]
0x180035483  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180035488  nop
0x180035489  mov     rcx, rbx; lpCriticalSection
0x18003548c  call    cs:__imp_LeaveCriticalSection
0x180035492  mov     eax, esi
0x180035494  jmp     short loc_18003550D
0x180035496  mov     rax, [rdi+70h]
0x18003549a  cmp     rax, [rdi+78h]
0x18003549e  jz      short loc_1800354B4
0x1800354a0  lea     rdx, [rsp+0A8h+var_68]
0x1800354a5  mov     rcx, rax
0x1800354a8  call    ??0?$CComQIPtr@UIMSVidGraphSegment@@$1?_GUID_238dec54_adeb_4005_a349_f772b9afebc4@@3U__s_GUID@@B@ATL@@QEAA@AEBV01@@Z; ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>(ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4> const &)
0x1800354ad  add     qword ptr [rdi+70h], 8
0x1800354b2  jmp     short loc_1800354C6
0x1800354b4  lea     r8, [rsp+0A8h+var_68]
0x1800354b9  mov     rdx, rax
0x1800354bc  lea     rcx, [rdi+68h]
0x1800354c0  call    ??$_Emplace_reallocate@AEBV?$CComQIPtr@UIComponent@@$1?_GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@@?$vector@V?$CComQIPtr@UIComponent@@$1?_GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@V?$allocator@V?$CComQIPtr@UIComponent@@$1?_GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@@std@@@std@@AEAAPEAV?$CComQIPtr@UIComponent@@$1?_GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@QEAV23@AEBV23@@Z; std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>::_Emplace_reallocate<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980> const &>(ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980> * const,ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980> const &)
0x1800354c5  nop
0x1800354c6  lea     rcx, [rsp+0A8h+var_68]
0x1800354cb  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800354d0  nop
0x1800354d1  lea     rcx, [rsp+0A8h+var_70]
0x1800354d6  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800354db  inc     r14d
0x1800354de  jmp     loc_18003535E
0x1800354e3  mov     byte ptr [rdi+60h], 1
0x1800354e7  mov     rcx, rbx; lpCriticalSection
0x1800354ea  call    cs:__imp_LeaveCriticalSection
0x1800354f0  nop
0x1800354f1  xor     eax, eax
0x1800354f3  jmp     short loc_18003550D
0x1800354f5  mov     eax, [rsp+0A8h+var_60]
0x1800354f9  jmp     short loc_180035506
0x1800354fb  mov     eax, [rsp+0A8h+var_78]
0x1800354ff  jmp     short loc_180035506
0x180035501  mov     eax, 8007000Eh
0x180035506  jmp     short loc_18003550D
0x180035508  mov     eax, 8000FFFFh
0x18003550d  mov     rcx, [rsp+0A8h+var_28]
0x180035515  xor     rcx, rsp; StackCookie
0x180035518  call    __security_check_cookie
0x18003551d  lea     r11, [rsp+0A8h+var_18]
0x180035525  mov     rbx, [r11+30h]
0x180035529  mov     rsi, [r11+38h]
0x18003552d  mov     rsp, r11
0x180035530  pop     r15
0x180035532  pop     r14
0x180035534  pop     rdi
0x180035535  retn
```
