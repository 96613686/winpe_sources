# CDSLObject::AddPages(int (*)(_PSP *,__int64),__int64)

- ea: `0x180056e50`
- end: `0x1800572db`
- name: `?AddPages@CDSLObject@@UEAAJP6AHPEAU_PSP@@_J@Z1@Z`
- size: `1163`
- prototype: `__int64 __fastcall(CDSLObject *__hidden this, int (*)(struct _PSP *, __int64), __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180013870`
- `0x18002ec0c`
- `0x18004b650`
- `0x18004baa0`
- `0x18004d950`
- `0x180055d3c`
- `0x180056438`
- `0x180056e50`
- `0x180087010`

## import_xrefs

- `SHELL32!DragQueryFileW` at `0x180056efe`
- `SHELL32!DragQueryFileW` at `0x180056f3b`
- `SHELL32!DragQueryFileW` at `0x180056efe`
- `SHELL32!DragQueryFileW` at `0x180056f3b`
- `ole32!CoTaskMemAlloc` at `0x180056f12`
- `ole32!CoTaskMemAlloc` at `0x1800570da`
- `ole32!CoTaskMemAlloc` at `0x180056f12`
- `ole32!CoTaskMemAlloc` at `0x1800570da`
- `ole32!CoInitialize` at `0x180056f4a`
- `ole32!CoInitialize` at `0x180056f4a`
- `ole32!CoTaskMemFree` at `0x1800570c7`
- `ole32!CoTaskMemFree` at `0x180057212`
- `ole32!CoTaskMemFree` at `0x1800570c7`
- `ole32!CoTaskMemFree` at `0x180057212`
- `ole32!CoCreateInstance` at `0x180056f9d`
- `ole32!CoCreateInstance` at `0x180056f9d`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CDSLObject::AddPages(CDSLObject *this, int (*a2)(struct _PSP *, __int64), __int64 a3)
{
  int v6; // edi
  __int64 v7; // rcx
  WCHAR *v8; // rax
  HRESULT v9; // eax
  const struct _GUID *v10; // rdx
  int v11; // eax
  int PropertyPages; // eax
  void *v13; // rcx
  LPVOID v14; // rax
  CDSLObject *v15; // rcx
  int v16; // eax
  __int64 v17; // r9
  unsigned int i; // esi
  LPVOID ppv; // [rsp+40h] [rbp-88h] BYREF
  int pExceptionObject; // [rsp+48h] [rbp-80h] BYREF
  int v22; // [rsp+4Ch] [rbp-7Ch] BYREF
  int v23; // [rsp+50h] [rbp-78h] BYREF
  int v24; // [rsp+54h] [rbp-74h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-70h] BYREF
  struct _PSP **v26; // [rsp+60h] [rbp-68h] BYREF
  __int128 v27; // [rsp+68h] [rbp-60h] BYREF
  __int128 v28; // [rsp+78h] [rbp-50h]
  __int128 v29; // [rsp+88h] [rbp-40h] BYREF
  __int64 v30; // [rsp+98h] [rbp-30h]
  unsigned int v31; // [rsp+E8h] [rbp+20h] BYREF

  v6 = 0;
  pv = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  LOWORD(v27) = 15;
  *(_QWORD *)&v28 = 0xFFFFFFFF00000001uLL;
  DWORD2(v28) = 1;
  v7 = *((_QWORD *)this + 125);
  if ( v7 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)v7 + 24LL))(v7, &v27, &v29);
    if ( v6 >= 0 && *((_QWORD *)&v29 + 1) && DragQueryFileW(*((HDROP *)&v29 + 1), 0xFFFFFFFF, 0, 0) == 1 )
    {
      v8 = (WCHAR *)CoTaskMemAlloc(0x20Au);
      *((_QWORD *)this + 127) = v8;
      if ( !v8 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(-2147024882, L"<CDSLObject::AddPages|OLEDB|ERR> ", 0x72u);
        pExceptionObject = -2147024882;
        throw (long *)&pExceptionObject;
      }
      DragQueryFileW(*((HDROP *)&v29 + 1), 0, v8, 0x104u);
      *((_BYTE *)this + 1032) = 1;
      if ( CoInitialize(0) < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(-2147467259, L"<CDSLObject::AddPages|OLEDB|ERR> ", 0x7Eu);
        *((_BYTE *)this + 1032) = 0;
      }
      ppv = 0;
      v9 = CoCreateInstance(&CLSID_MSDAINITIALIZE, 0, 1u, &IID_IDataInitialize, &ppv);
      if ( v9 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(v9, L"<CDSLObject::AddPages|OLEDB|ERR> ", 0xA7u);
      }
      else
      {
        (*(void (__fastcall **)(LPVOID, _QWORD, LPVOID *))(*(_QWORD *)ppv + 56LL))(ppv, *((_QWORD *)this + 127), &pv);
        (*(void (__fastcall **)(LPVOID, _QWORD, __int64, LPVOID, GUID *, char *))(*(_QWORD *)ppv + 24LL))(
          ppv,
          0,
          23,
          pv,
          &IID_IUnknown,
          (char *)this + 1024);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        ppv = 0;
      }
      v11 = CDSLObject::PrePropertySheet(
              (CDSLObject *)((char *)this - 24),
              v10,
              (struct IUnknown **)this + 128,
              2u,
              0,
              0,
              0,
              0);
      v6 = v11;
      if ( v11 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(v11, L"<CDSLObject::AddPages|OLEDB|ERR> ", 0xACu);
        v22 = v6;
        throw (long *)&v22;
      }
      *((_BYTE *)this + 984) = 1;
      v26 = 0;
      v31 = 0;
      PropertyPages = CDSLProviderInformation::GetPropertyPages(
                        (LPVOID *)(*((_QWORD *)this + 11) + 104LL * *((int *)this + 24)),
                        (CDSLObject *)((char *)this - 24),
                        &v26,
                        &v31);
      if ( PropertyPages < 0 )
      {
        v23 = PropertyPages;
        throw (long *)&v23;
      }
      v13 = (void *)*((_QWORD *)this + 29);
      if ( v13 )
        CoTaskMemFree(v13);
      v14 = CoTaskMemAlloc(8LL * (v31 + 1));
      *((_QWORD *)this + 29) = v14;
      if ( !v14 )
      {
        v24 = -2147024882;
        throw (long *)&v24;
      }
      *((_DWORD *)this + 60) = v31 + 1;
      **((_QWORD **)this + 29) = IsolationAwareCreatePropertySheetPageW((char *)this + 112);
      (*(void (__fastcall **)(char *))(*((_QWORD *)this + 3) + 8LL))((char *)this + 24);
      v16 = 0;
      if ( v31 )
      {
        do
        {
          v17 = (unsigned int)(v16 + 1);
          v15 = v26[v16];
          *(_QWORD *)(*((_QWORD *)this + 29) + 8 * v17) = v15;
          ++v16;
        }
        while ( (unsigned int)v17 < v31 );
      }
      for ( i = 0; i < *((_DWORD *)this + 60); ++i )
      {
        if ( !((unsigned int (__fastcall *)(_QWORD, __int64))a2)(*(_QWORD *)(*((_QWORD *)this + 29) + 8LL * i), a3) )
        {
          IsolationAwareDestroyPropertySheetPage(*(_QWORD *)(*((_QWORD *)this + 29) + 8LL * i));
          *(_QWORD *)(*((_QWORD *)this + 29) + 8LL * i) = 0;
          v6 = -2147467259;
          break;
        }
      }
      if ( CDSLObject::GetRegEntryForPassword(v15) )
        *((_BYTE *)this + 986) = 0;
      else
        *((_BYTE *)this + 987) = 1;
      if ( v6 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(v6, L"<CDSLObject::AddPages|OLEDB|ERR> ", 0xF2u);
        while ( i )
        {
          (*(void (__fastcall **)(char *))(*((_QWORD *)this + 3) + 16LL))((char *)this + 24);
          --i;
        }
      }
      CoTaskMemFree(pv);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180056e50  mov     r11, rsp
0x180056e53  mov     [r11+10h], rbx
0x180056e57  mov     [r11+18h], rsi
0x180056e5b  push    rdi
0x180056e5c  push    r12
0x180056e5e  push    r13
0x180056e60  push    r14
0x180056e62  push    r15
0x180056e64  sub     rsp, 0A0h
0x180056e6b  mov     r12, r8
0x180056e6e  mov     r13, rdx
0x180056e71  mov     rbx, rcx
0x180056e74  xor     r14d, r14d
0x180056e77  mov     edi, r14d
0x180056e7a  mov     [r11-70h], r14
0x180056e7e  xorps   xmm0, xmm0
0x180056e81  movups  [rsp+0C8h+var_60], xmm0
0x180056e86  movups  [rsp+0C8h+var_50], xmm0
0x180056e8b  xorps   xmm1, xmm1
0x180056e8e  xor     eax, eax
0x180056e90  movups  xmmword ptr [r11-40h], xmm1
0x180056e95  mov     [r11-30h], rax
0x180056e99  lea     eax, [r14+0Fh]
0x180056e9d  mov     word ptr [rsp+0C8h+var_60], ax
0x180056ea2  lea     r15d, [r14+1]
0x180056ea6  mov     [r11-50h], r15d
0x180056eaa  mov     dword ptr [rsp+0C8h+var_50+4], 0FFFFFFFFh
0x180056eb2  mov     [r11-48h], r15d
0x180056eb6  mov     rcx, [rcx+3E8h]
0x180056ebd  test    rcx, rcx
0x180056ec0  jz      loc_180057218
0x180056ec6  mov     rax, [rcx]
0x180056ec9  lea     r8, [r11-40h]
0x180056ecd  lea     rdx, [r11-60h]
0x180056ed1  mov     rax, [rax+18h]
0x180056ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056eda  mov     edi, eax
0x180056edc  test    eax, eax
0x180056ede  js      loc_180057218
0x180056ee4  mov     rcx, [rsp+0C8h+hDrop]; hDrop
0x180056eec  test    rcx, rcx
0x180056eef  jz      loc_180057218
0x180056ef5  xor     r9d, r9d; cch
0x180056ef8  xor     r8d, r8d; lpszFile
0x180056efb  or      edx, 0FFFFFFFFh; iFile
0x180056efe  call    cs:__imp_DragQueryFileW
0x180056f04  cmp     eax, r15d
0x180056f07  jnz     loc_180057218
0x180056f0d  mov     ecx, 20Ah; cb
0x180056f12  call    cs:__imp_CoTaskMemAlloc
0x180056f18  mov     [rbx+3F8h], rax
0x180056f1f  test    rax, rax
0x180056f22  jz      loc_180057237
0x180056f28  mov     r9d, 104h; cch
0x180056f2e  mov     r8, rax; lpszFile
0x180056f31  xor     edx, edx; iFile
0x180056f33  mov     rcx, [rsp+0C8h+hDrop]; hDrop
0x180056f3b  call    cs:__imp_DragQueryFileW
0x180056f41  mov     [rbx+408h], r15b
0x180056f48  xor     ecx, ecx; pvReserved
0x180056f4a  call    cs:__imp_CoInitialize
0x180056f50  test    eax, eax
0x180056f52  jns     short loc_180056F7B
0x180056f54  test    byte ptr cs:_bidGblFlags, 2
0x180056f5b  jz      short loc_180056F74
0x180056f5d  mov     r8d, 7Eh ; '~'; unsigned int
0x180056f63  lea     rdx, aCdslobjectAddp; "<CDSLObject::AddPages|OLEDB|ERR> "
0x180056f6a  mov     ecx, 80004005h; int
0x180056f6f  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180056f74  mov     [rbx+408h], r14b
0x180056f7b  mov     [rsp+0C8h+var_88], r14
0x180056f80  lea     rax, [rsp+0C8h+var_88]
0x180056f85  mov     [rsp+0C8h+ppv], rax; ppv
0x180056f8a  lea     r9, IID_IDataInitialize; riid
0x180056f91  mov     r8d, r15d; dwClsContext
0x180056f94  xor     edx, edx; pUnkOuter
0x180056f96  lea     rcx, CLSID_MSDAINITIALIZE; rclsid
0x180056f9d  call    cs:__imp_CoCreateInstance
0x180056fa3  mov     [rsp+0C8h+arg_0], eax
0x180056faa  test    eax, eax
0x180056fac  js      short loc_180057025
0x180056fae  mov     rcx, [rsp+0C8h+var_88]
0x180056fb3  mov     rax, [rcx]
0x180056fb6  lea     r8, [rsp+0C8h+pv]
0x180056fbb  mov     rdx, [rbx+3F8h]
0x180056fc2  mov     rax, [rax+38h]
0x180056fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056fcb  mov     [rsp+0C8h+arg_0], eax
0x180056fd2  mov     rcx, [rsp+0C8h+var_88]
0x180056fd7  mov     rax, [rcx]
0x180056fda  lea     rdx, [rbx+400h]
0x180056fe1  mov     [rsp+0C8h+var_A0], rdx
0x180056fe6  lea     rdx, IID_IUnknown
0x180056fed  mov     [rsp+0C8h+ppv], rdx
0x180056ff2  mov     r9, [rsp+0C8h+pv]
0x180056ff7  xor     edx, edx
0x180056ff9  lea     r8d, [rdx+17h]
0x180056ffd  mov     rax, [rax+18h]
0x180057001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057006  mov     [rsp+0C8h+arg_0], eax
0x18005700d  mov     rcx, [rsp+0C8h+var_88]
0x180057012  mov     rax, [rcx]
0x180057015  mov     rax, [rax+10h]
0x180057019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005701e  mov     [rsp+0C8h+var_88], r14
0x180057023  jmp     short loc_180057042
0x180057025  test    byte ptr cs:_bidGblFlags, 2
0x18005702c  jz      short loc_180057042
0x18005702e  mov     r8d, 0A7h; unsigned int
0x180057034  lea     rdx, aCdslobjectAddp; "<CDSLObject::AddPages|OLEDB|ERR> "
0x18005703b  mov     ecx, eax; int
0x18005703d  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180057042  lea     r8, [rbx+400h]; struct IUnknown **
0x180057049  mov     [rsp+0C8h+var_90], r14; struct IUnknown *
0x18005704e  mov     [rsp+0C8h+var_98], r14; unsigned __int16 *
0x180057053  mov     [rsp+0C8h+var_A0], r14; unsigned int *
0x180057058  mov     dword ptr [rsp+0C8h+ppv], r14d; unsigned int
0x18005705d  mov     r9d, 2; unsigned int
0x180057063  lea     rcx, [rbx-18h]; this
0x180057067  call    ?PrePropertySheet@CDSLObject@@QEAAJAEBU_GUID@@PEAPEAUIUnknown@@KKPEAKPEBGPEAU3@@Z; CDSLObject::PrePropertySheet(_GUID const &,IUnknown * *,ulong,ulong,ulong *,ushort const *,IUnknown *)
0x18005706c  mov     edi, eax
0x18005706e  mov     [rsp+0C8h+arg_0], eax
0x180057075  test    eax, eax
0x180057077  js      loc_180057279
0x18005707d  mov     [rbx+3D8h], r15b
0x180057084  mov     [rsp+0C8h+var_68], r14
0x180057089  mov     [rsp+0C8h+arg_18], r14d
0x180057091  movsxd  rax, dword ptr [rbx+60h]
0x180057095  imul    rcx, rax, 68h ; 'h'
0x180057099  add     rcx, [rbx+58h]; this
0x18005709d  lea     r9, [rsp+0C8h+arg_18]; unsigned int *
0x1800570a5  lea     r8, [rsp+0C8h+var_68]; struct _PSP ***
0x1800570aa  lea     rdx, [rbx-18h]; struct CDSLObject *
0x1800570ae  call    ?GetPropertyPages@CDSLProviderInformation@@QEAAJPEAVCDSLObject@@PEAPEAPEAU_PSP@@PEAK@Z; CDSLProviderInformation::GetPropertyPages(CDSLObject *,_PSP * * *,ulong *)
0x1800570b3  test    eax, eax
0x1800570b5  js      loc_1800572AB
0x1800570bb  mov     rcx, [rbx+0E8h]; pv
0x1800570c2  test    rcx, rcx
0x1800570c5  jz      short loc_1800570CD
0x1800570c7  call    cs:__imp_CoTaskMemFree
0x1800570cd  mov     ecx, [rsp+0C8h+arg_18]
0x1800570d4  inc     ecx
0x1800570d6  shl     rcx, 3; cb
0x1800570da  call    cs:__imp_CoTaskMemAlloc
0x1800570e0  mov     [rbx+0E8h], rax
0x1800570e7  test    rax, rax
0x1800570ea  jz      loc_1800572C0
0x1800570f0  mov     eax, [rsp+0C8h+arg_18]
0x1800570f7  inc     eax
0x1800570f9  mov     [rbx+0F0h], eax
0x1800570ff  lea     rcx, [rbx+70h]
0x180057103  call    IsolationAwareCreatePropertySheetPageW
0x180057108  mov     rcx, [rbx+0E8h]
0x18005710f  mov     [rcx], rax
0x180057112  lea     r15, [rbx+18h]
0x180057116  mov     rax, [r15]
0x180057119  mov     rcx, r15
0x18005711c  mov     rax, [rax+8]
0x180057120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057125  mov     eax, r14d
0x180057128  cmp     [rsp+0C8h+arg_18], r14d
0x180057130  jbe     short loc_180057159
0x180057132  lea     r9d, [rax+1]
0x180057136  mov     ecx, eax
0x180057138  mov     rdx, [rbx+0E8h]
0x18005713f  mov     rax, [rsp+0C8h+var_68]
0x180057144  mov     rcx, [rax+rcx*8]
0x180057148  mov     [rdx+r9*8], rcx
0x18005714c  mov     eax, r9d
0x18005714f  cmp     r9d, [rsp+0C8h+arg_18]
0x180057157  jb      short loc_180057132
0x180057159  mov     esi, r14d
0x18005715c  cmp     esi, [rbx+0F0h]
0x180057162  jnb     short loc_1800571AC
0x180057164  mov     r14d, esi
0x180057167  mov     rcx, [rbx+0E8h]
0x18005716e  mov     rdx, r12
0x180057171  mov     rcx, [rcx+r14*8]
0x180057175  mov     rax, r13
0x180057178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005717d  test    eax, eax
0x18005717f  jnz     short loc_1800571C1
0x180057181  mov     rcx, [rbx+0E8h]
0x180057188  mov     rcx, [rcx+r14*8]
0x18005718c  call    IsolationAwareDestroyPropertySheetPage
0x180057191  mov     rax, [rbx+0E8h]
0x180057198  mov     qword ptr [rax+r14*8], 0
0x1800571a0  mov     edi, 80004005h
0x1800571a5  mov     [rsp+0C8h+arg_0], edi
0x1800571ac  call    ?GetRegEntryForPassword@CDSLObject@@QEAAKXZ; CDSLObject::GetRegEntryForPassword(void)
0x1800571b1  xor     r14d, r14d
0x1800571b4  test    eax, eax
0x1800571b6  jz      short loc_1800571C5
0x1800571b8  mov     [rbx+3DAh], r14b
0x1800571bf  jmp     short loc_1800571CC
0x1800571c1  inc     esi
0x1800571c3  jmp     short loc_18005715C
0x1800571c5  mov     byte ptr [rbx+3DBh], 1
0x1800571cc  test    edi, edi
0x1800571ce  jns     short loc_180057204
0x1800571d0  test    byte ptr cs:_bidGblFlags, 2
0x1800571d7  jz      short loc_1800571ED
0x1800571d9  mov     r8d, 0F2h; unsigned int
0x1800571df  lea     rdx, aCdslobjectAddp; "<CDSLObject::AddPages|OLEDB|ERR> "
0x1800571e6  mov     ecx, edi; int
0x1800571e8  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800571ed  test    esi, esi
0x1800571ef  jz      short loc_180057204
0x1800571f1  mov     rax, [r15]
0x1800571f4  mov     rcx, r15
0x1800571f7  mov     rax, [rax+10h]
0x1800571fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057200  dec     esi
0x180057202  jmp     short loc_1800571ED
0x180057204  jmp     short loc_18005720D
0x180057206  mov     edi, [rsp+0C8h+arg_0]
0x18005720d  mov     rcx, [rsp+0C8h+pv]; pv
0x180057212  call    cs:__imp_CoTaskMemFree
0x180057218  mov     eax, edi
0x18005721a  lea     r11, [rsp+0C8h+var_28]
0x180057222  mov     rbx, [r11+38h]
0x180057226  mov     rsi, [r11+40h]
0x18005722a  mov     rsp, r11
0x18005722d  pop     r15
0x18005722f  pop     r14
0x180057231  pop     r13
0x180057233  pop     r12
0x180057235  pop     rdi
0x180057236  retn
0x180057237  test    byte ptr cs:_bidGblFlags, 2
0x18005723e  jz      short loc_180057255
0x180057240  lea     r8d, [r14+72h]; unsigned int
0x180057244  lea     rdx, aCdslobjectAddp; "<CDSLObject::AddPages|OLEDB|ERR> "
0x18005724b  mov     ecx, 8007000Eh; int
0x180057250  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180057255  mov     [rsp+0C8h+arg_0], 8007000Eh
0x180057260  mov     [rsp+0C8h+pExceptionObject], 8007000Eh
0x180057268  lea     rdx, _TI1J; pThrowInfo
0x18005726f  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x180057274  call    _CxxThrowException_0
0x180057279  test    byte ptr cs:_bidGblFlags, 2
0x180057280  jz      short loc_180057296
0x180057282  mov     r8d, 0ACh; unsigned int
0x180057288  lea     rdx, aCdslobjectAddp; "<CDSLObject::AddPages|OLEDB|ERR> "
0x18005728f  mov     ecx, eax; int
0x180057291  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180057296  mov     [rsp+0C8h+var_7C], edi
0x18005729a  lea     rdx, _TI1J; pThrowInfo
0x1800572a1  lea     rcx, [rsp+0C8h+var_7C]; pExceptionObject
0x1800572a6  call    _CxxThrowException_0
0x1800572ab  mov     [rsp+0C8h+var_78], eax
0x1800572af  lea     rdx, _TI1J; pThrowInfo
0x1800572b6  lea     rcx, [rsp+0C8h+var_78]; pExceptionObject
0x1800572bb  call    _CxxThrowException_0
0x1800572c0  mov     [rsp+0C8h+var_74], 8007000Eh
0x1800572c8  lea     rdx, _TI1J; pThrowInfo
0x1800572cf  lea     rcx, [rsp+0C8h+var_74]; pExceptionObject
0x1800572d4  call    _CxxThrowException_0
```
