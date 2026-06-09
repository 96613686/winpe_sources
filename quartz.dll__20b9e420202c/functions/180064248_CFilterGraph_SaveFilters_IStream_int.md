# CFilterGraph::SaveFilters(IStream *,int)

- ea: `0x180064248`
- end: `0x180064790`
- name: `?SaveFilters@CFilterGraph@@AEAAJPEAUIStream@@H@Z`
- size: `1352`
- prototype: `int(CFilterGraph *__hidden this, struct IStream *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1800639e0`

## callees

- `0x180004924`
- `0x1800197c0`
- `0x1800388a0`
- `0x180039250`
- `0x1800640f4`
- `0x180064248`
- `0x18015e010`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18006428f`
- `KERNEL32!lstrlenW` at `0x1800643ed`
- `KERNEL32!lstrlenW` at `0x180064487`
- `KERNEL32!lstrlenW` at `0x180064526`
- `KERNEL32!lstrlenW` at `0x1800645a0`
- `KERNEL32!lstrlenW` at `0x18006463f`
- `KERNEL32!lstrlenW` at `0x18006428f`
- `KERNEL32!lstrlenW` at `0x1800643ed`
- `KERNEL32!lstrlenW` at `0x180064487`
- `KERNEL32!lstrlenW` at `0x180064526`
- `KERNEL32!lstrlenW` at `0x1800645a0`
- `KERNEL32!lstrlenW` at `0x18006463f`
- `ole32!CoTaskMemFree` at `0x18006454f`
- `ole32!CoTaskMemFree` at `0x180064668`
- `ole32!CoTaskMemFree` at `0x18006454f`
- `ole32!CoTaskMemFree` at `0x180064668`
- `ole32!StringFromGUID2` at `0x1800643cc`
- `ole32!StringFromGUID2` at `0x1800643cc`

## pseudocode

```c
__int64 __fastcall CFilterGraph::SaveFilters(CFilterGraph *this, struct IStream *a2, int a3)
{
  __int64 (__fastcall *v6)(struct IStream *, const WCHAR *, _QWORD, _QWORD); // rbx
  int v7; // eax
  __int64 result; // rax
  CBaseList *v9; // rcx
  int v10; // ebx
  struct __POSITION *v11; // r15
  unsigned int v12; // r14d
  _QWORD *v13; // rax
  _QWORD *v14; // rsi
  __int64 v15; // r8
  __int64 (__fastcall *v16)(struct IStream *, OLECHAR *, _QWORD, _QWORD); // rbx
  int v17; // eax
  __int64 (__fastcall ***v18)(_QWORD, GUID *, struct IPersistStream **); // rcx
  int v19; // eax
  __int64 (__fastcall *v20)(struct IStream *, const WCHAR *, _QWORD, _QWORD); // rbx
  int v21; // eax
  __int64 (__fastcall *v22)(struct IStream *, OLECHAR *, _QWORD, _QWORD); // rbx
  int v23; // eax
  int v24; // eax
  __int64 (__fastcall *v25)(struct IStream *, const WCHAR *, _QWORD, _QWORD); // rbx
  int v26; // eax
  __int64 (__fastcall *v27)(struct IStream *, OLECHAR *, _QWORD, _QWORD); // rbx
  int v28; // eax
  int v29; // eax
  CFilterGraph *v30; // rcx
  struct IPersistStream *v31; // rcx
  struct IPersistStream *v32; // [rsp+30h] [rbp-D0h] BYREF
  struct IPersistStream *v33; // [rsp+38h] [rbp-C8h] BYREF
  struct IPersistStream *v34; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v37; // [rsp+58h] [rbp-A8h] BYREF
  GUID rguid; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v39[96]; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR sz[264]; // [rsp+D0h] [rbp-30h] BYREF

  v6 = *(__int64 (__fastcall **)(struct IStream *, const WCHAR *, _QWORD, _QWORD))(*(_QWORD *)a2 + 32LL);
  v7 = lstrlenW(L"FILTERS\r\n");
  result = v6(a2, L"FILTERS\r\n", (unsigned int)(2 * v7), 0);
  v10 = result;
  if ( (int)result >= 0 )
  {
    v11 = (struct __POSITION *)*((_QWORD *)this + 38);
    v12 = 1;
    v35 = 0;
    v34 = 0;
    while ( v11 )
    {
      v13 = CBaseList::GetI(v9, v11);
      v11 = *(struct __POSITION **)v11;
      v14 = v13;
      *((_DWORD *)v13 + 4) = v12;
      StringCchPrintfW(sz, 0x107u, L"%04d ", v12);
      v10 = (*(__int64 (__fastcall **)(struct IStream *, OLECHAR *, __int64))(*(_QWORD *)a2 + 32LL))(a2, sz, 10);
      if ( v10 < 0 )
        break;
      StringCchPrintfW(sz, 0x107u, L"\"%ls\" ", v14[1]);
      v15 = -1;
      do
        ++v15;
      while ( sz[v15] );
      (*(void (__fastcall **)(struct IStream *, OLECHAR *, _QWORD, _QWORD))(*(_QWORD *)a2 + 32LL))(
        a2,
        sz,
        (unsigned int)(2 * v15),
        0);
      v10 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v14)(*v14, &IID_IPersist, &v35);
      if ( v10 < 0 )
        break;
      rguid = 0;
      v10 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v35 + 24LL))(v35, &rguid);
      if ( v10 < 0 )
        goto LABEL_34;
      v10 = StringFromGUID2(&rguid, sz, 39);
      if ( v10 < 0 )
        goto LABEL_34;
      v16 = *(__int64 (__fastcall **)(struct IStream *, OLECHAR *, _QWORD, _QWORD))(*(_QWORD *)a2 + 32LL);
      v17 = lstrlenW(sz);
      v10 = v16(a2, sz, (unsigned int)(2 * v17), 0);
      if ( v10 < 0 )
        goto LABEL_34;
      v10 = (*(__int64 (__fastcall **)(struct IStream *, const wchar_t *, __int64))(*(_QWORD *)a2 + 32LL))(a2, L" ", 2);
      if ( v10 < 0 )
        goto LABEL_34;
      v18 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IPersistStream **))*v14;
      v32 = 0;
      v33 = 0;
      v19 = (**v18)(v18, &IID_IFileSourceFilter, &v32);
      v10 = v19;
      if ( v19 != -2147467262 )
      {
        if ( v19 < 0 )
          goto LABEL_34;
        v20 = *(__int64 (__fastcall **)(struct IStream *, const WCHAR *, _QWORD, _QWORD))(*(_QWORD *)a2 + 32LL);
        v21 = lstrlenW(L"SOURCE ");
        v10 = v20(a2, L"SOURCE ", (unsigned int)(2 * v21), 0);
        if ( v10 < 0 )
        {
          v31 = v32;
LABEL_33:
          ((void (__fastcall *)(struct IPersistStream *))v31->lpVtbl->Release)(v31);
LABEL_34:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
          return (unsigned int)v10;
        }
        memset_0(v39, 0, 0x58u);
        pv = 0;
        v10 = ((__int64 (__fastcall *)(struct IPersistStream *, LPVOID *, _BYTE *))v32->lpVtbl->IsDirty)(v32, &pv, v39);
        ((void (__fastcall *)(struct IPersistStream *))v32->lpVtbl->Release)(v32);
        if ( v10 < 0 )
          goto LABEL_34;
        StringCchPrintfW(sz, 0x107u, L"\"%ls\" ", pv);
        v22 = *(__int64 (__fastcall **)(struct IStream *, OLECHAR *, _QWORD, _QWORD))(*(_QWORD *)a2 + 32LL);
        v23 = lstrlenW(sz);
        v10 = v22(a2, sz, (unsigned int)(2 * v23), 0);
        CoTaskMemFree(pv);
        if ( v10 < 0 )
          goto LABEL_34;
      }
      v24 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct IPersistStream **))*v14)(
              *v14,
              &IID_IFileSinkFilter,
              &v33);
      v10 = v24;
      if ( v24 != -2147467262 )
      {
        if ( v24 < 0 )
          goto LABEL_34;
        v25 = *(__int64 (__fastcall **)(struct IStream *, const WCHAR *, _QWORD, _QWORD))(*(_QWORD *)a2 + 32LL);
        v26 = lstrlenW(L"SINK ");
        v10 = v25(a2, L"SINK ", (unsigned int)(2 * v26), 0);
        if ( v10 < 0 )
        {
          v31 = v33;
          goto LABEL_33;
        }
        memset_0(v39, 0, 0x58u);
        v37 = 0;
        v10 = ((__int64 (__fastcall *)(struct IPersistStream *, LPVOID *, _BYTE *))v33->lpVtbl->IsDirty)(v33, &v37, v39);
        ((void (__fastcall *)(struct IPersistStream *))v33->lpVtbl->Release)(v33);
        if ( v10 < 0 )
          goto LABEL_34;
        StringCchPrintfW(sz, 0x107u, L"\"%ls\" ", v37);
        v27 = *(__int64 (__fastcall **)(struct IStream *, OLECHAR *, _QWORD, _QWORD))(*(_QWORD *)a2 + 32LL);
        v28 = lstrlenW(sz);
        v10 = v27(a2, sz, (unsigned int)(2 * v28), 0);
        CoTaskMemFree(v37);
        if ( v10 < 0 )
          goto LABEL_34;
      }
      v29 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct IPersistStream **))*v14)(
              *v14,
              &IID_IPersistStream,
              &v34);
      v10 = v29;
      if ( v29 == -2147467262 )
      {
        v10 = (*(__int64 (__fastcall **)(struct IStream *, const wchar_t *, __int64))(*(_QWORD *)a2 + 32LL))(
                a2,
                L"0000000000 \r\n",
                26);
        if ( v10 < 0 )
          goto LABEL_34;
      }
      else
      {
        if ( v29 < 0 )
          goto LABEL_34;
        v10 = CFilterGraph::SaveFilterPrivateData(v30, a2, v34, a3);
        if ( v10 < 0
          || (v10 = (*(__int64 (__fastcall **)(struct IStream *, const unsigned __int16 *, __int64))(*(_QWORD *)a2 + 32LL))(
                      a2,
                      L"\r\n",
                      4),
              v10 < 0) )
        {
          v31 = v34;
          goto LABEL_33;
        }
        ((void (__fastcall *)(struct IPersistStream *))v34->lpVtbl->Release)(v34);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      ++v12;
    }
    return (unsigned int)v10;
  }
  return result;
}

```

## disassembly

```asm
0x180064248  mov     [rsp-8+arg_18], rbx
0x18006424d  push    rbp
0x18006424e  push    rsi
0x18006424f  push    rdi
0x180064250  push    r12
0x180064252  push    r13
0x180064254  push    r14
0x180064256  push    r15
0x180064258  lea     rbp, [rsp-1F0h]
0x180064260  sub     rsp, 2F0h
0x180064267  mov     rax, cs:__security_cookie
0x18006426e  xor     rax, rsp
0x180064271  mov     [rbp+220h+var_40], rax
0x180064278  mov     rax, [rdx]
0x18006427b  mov     rsi, rcx
0x18006427e  lea     rcx, ?mFG_FiltersStringX@CFilterGraph@@0QBGB; "FILTERS\r\n"
0x180064285  mov     r12d, r8d
0x180064288  mov     rdi, rdx
0x18006428b  mov     rbx, [rax+20h]
0x18006428f  call    cs:__imp_lstrlenW
0x180064296  nop     dword ptr [rax+rax+00h]
0x18006429b  xor     r9d, r9d
0x18006429e  lea     rdx, ?mFG_FiltersStringX@CFilterGraph@@0QBGB; "FILTERS\r\n"
0x1800642a5  mov     rcx, rdi
0x1800642a8  lea     r8d, [rax+rax]
0x1800642ac  mov     rax, rbx
0x1800642af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800642b4  xor     r13d, r13d
0x1800642b7  mov     ebx, eax
0x1800642b9  test    eax, eax
0x1800642bb  js      loc_180064765
0x1800642c1  mov     r15, [rsi+130h]
0x1800642c8  lea     r14d, [r13+1]
0x1800642cc  mov     [rsp+320h+var_2D8], r13
0x1800642d1  mov     [rsp+320h+var_2E0], r13
0x1800642d6  test    r15, r15
0x1800642d9  jz      loc_180064763
0x1800642df  mov     rdx, r15; struct __POSITION *
0x1800642e2  call    ?GetI@CBaseList@@IEBAPEAXPEAU__POSITION@@@Z; CBaseList::GetI(__POSITION *)
0x1800642e7  mov     r15, [r15]
0x1800642ea  lea     r8, a04d; "%04d "
0x1800642f1  mov     r9d, r14d
0x1800642f4  lea     rcx, [rbp+220h+sz]; Buffer
0x1800642f8  mov     edx, 107h; unsigned __int64
0x1800642fd  mov     rsi, rax
0x180064300  mov     [rax+10h], r14d
0x180064304  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180064309  mov     rcx, [rdi]
0x18006430c  lea     rdx, [rbp+220h+sz]
0x180064310  xor     r9d, r9d
0x180064313  mov     rax, [rcx+20h]
0x180064317  mov     rcx, rdi
0x18006431a  lea     r8d, [r9+0Ah]
0x18006431e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064323  mov     ebx, eax
0x180064325  test    eax, eax
0x180064327  js      loc_180064763
0x18006432d  mov     r9, [rsi+8]
0x180064331  lea     r8, aLs_0; "\"%ls\" "
0x180064338  mov     edx, 107h; unsigned __int64
0x18006433d  lea     rcx, [rbp+220h+sz]; Buffer
0x180064341  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180064346  lea     rax, [rbp+220h+sz]
0x18006434a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006434e  inc     r8
0x180064351  cmp     [rax+r8*2], r13w
0x180064356  jnz     short loc_18006434E
0x180064358  mov     rax, [rdi]
0x18006435b  lea     rdx, [rbp+220h+sz]
0x18006435f  add     r8d, r8d
0x180064362  xor     r9d, r9d
0x180064365  mov     rcx, rdi
0x180064368  mov     rax, [rax+20h]
0x18006436c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064371  mov     rcx, [rsi]
0x180064374  lea     r8, [rsp+320h+var_2D8]
0x180064379  lea     rdx, IID_IPersist
0x180064380  mov     rax, [rcx]
0x180064383  mov     rax, [rax]
0x180064386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006438b  mov     ebx, eax
0x18006438d  test    eax, eax
0x18006438f  js      loc_180064763
0x180064395  mov     rcx, [rsp+320h+var_2D8]
0x18006439a  lea     rdx, [rsp+320h+rguid]
0x18006439f  xorps   xmm0, xmm0
0x1800643a2  movups  xmmword ptr [rsp+320h+rguid.Data1], xmm0
0x1800643a7  mov     rax, [rcx]
0x1800643aa  mov     rax, [rax+18h]
0x1800643ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800643b3  mov     ebx, eax
0x1800643b5  test    eax, eax
0x1800643b7  js      loc_180064752
0x1800643bd  mov     r8d, 27h ; '''; cchMax
0x1800643c3  lea     rdx, [rbp+220h+sz]; lpsz
0x1800643c7  lea     rcx, [rsp+320h+rguid]; rguid
0x1800643cc  call    cs:__imp_StringFromGUID2
0x1800643d3  nop     dword ptr [rax+rax+00h]
0x1800643d8  mov     ebx, eax
0x1800643da  test    eax, eax
0x1800643dc  js      loc_180064752
0x1800643e2  mov     rax, [rdi]
0x1800643e5  lea     rcx, [rbp+220h+sz]; lpString
0x1800643e9  mov     rbx, [rax+20h]
0x1800643ed  call    cs:__imp_lstrlenW
0x1800643f4  nop     dword ptr [rax+rax+00h]
0x1800643f9  xor     r9d, r9d
0x1800643fc  lea     rdx, [rbp+220h+sz]
0x180064400  mov     rcx, rdi
0x180064403  lea     r8d, [rax+rax]
0x180064407  mov     rax, rbx
0x18006440a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006440f  mov     ebx, eax
0x180064411  test    eax, eax
0x180064413  js      loc_180064752
0x180064419  mov     rax, [rdi]
0x18006441c  lea     rdx, asc_180176670; " "
0x180064423  xor     r9d, r9d
0x180064426  mov     rcx, rdi
0x180064429  mov     rax, [rax+20h]
0x18006442d  lea     r8d, [r9+2]
0x180064431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064436  mov     ebx, eax
0x180064438  test    eax, eax
0x18006443a  js      loc_180064752
0x180064440  mov     rcx, [rsi]
0x180064443  lea     r8, [rsp+320h+var_2F0]
0x180064448  mov     [rsp+320h+var_2F0], r13
0x18006444d  lea     rdx, IID_IFileSourceFilter
0x180064454  mov     [rsp+320h+var_2E8], r13
0x180064459  mov     rax, [rcx]
0x18006445c  mov     rax, [rax]
0x18006445f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064464  mov     ebx, eax
0x180064466  cmp     eax, 80004002h
0x18006446b  jz      loc_180064563
0x180064471  test    eax, eax
0x180064473  js      loc_180064752
0x180064479  mov     rax, [rdi]
0x18006447c  lea     rcx, aSource_1; "SOURCE "
0x180064483  mov     rbx, [rax+20h]
0x180064487  call    cs:__imp_lstrlenW
0x18006448e  nop     dword ptr [rax+rax+00h]
0x180064493  xor     r9d, r9d
0x180064496  lea     rdx, aSource_1; "SOURCE "
0x18006449d  mov     rcx, rdi
0x1800644a0  lea     r8d, [rax+rax]
0x1800644a4  mov     rax, rbx
0x1800644a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800644ac  mov     ebx, eax
0x1800644ae  test    eax, eax
0x1800644b0  js      loc_180064733
0x1800644b6  xor     edx, edx; Val
0x1800644b8  lea     rcx, [rsp+320h+var_2B0]; void *
0x1800644bd  lea     r8d, [rdx+58h]; Size
0x1800644c1  call    memset_0
0x1800644c6  mov     rcx, [rsp+320h+var_2F0]
0x1800644cb  lea     r8, [rsp+320h+var_2B0]
0x1800644d0  mov     [rsp+320h+pv], r13
0x1800644d5  lea     rdx, [rsp+320h+pv]
0x1800644da  mov     rax, [rcx]
0x1800644dd  mov     rax, [rax+20h]
0x1800644e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800644e6  mov     rcx, [rsp+320h+var_2F0]
0x1800644eb  mov     ebx, eax
0x1800644ed  mov     rax, [rcx]
0x1800644f0  mov     rax, [rax+10h]
0x1800644f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800644f9  test    ebx, ebx
0x1800644fb  js      loc_180064752
0x180064501  mov     r9, [rsp+320h+pv]
0x180064506  lea     r8, aLs_0; "\"%ls\" "
0x18006450d  mov     edx, 107h; unsigned __int64
0x180064512  lea     rcx, [rbp+220h+sz]; Buffer
0x180064516  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006451b  mov     rax, [rdi]
0x18006451e  lea     rcx, [rbp+220h+sz]; lpString
0x180064522  mov     rbx, [rax+20h]
0x180064526  call    cs:__imp_lstrlenW
0x18006452d  nop     dword ptr [rax+rax+00h]
0x180064532  xor     r9d, r9d
0x180064535  lea     rdx, [rbp+220h+sz]
0x180064539  mov     rcx, rdi
0x18006453c  lea     r8d, [rax+rax]
0x180064540  mov     rax, rbx
0x180064543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064548  mov     rcx, [rsp+320h+pv]; pv
0x18006454d  mov     ebx, eax
0x18006454f  call    cs:__imp_CoTaskMemFree
0x180064556  nop     dword ptr [rax+rax+00h]
0x18006455b  test    ebx, ebx
0x18006455d  js      loc_180064752
0x180064563  mov     rcx, [rsi]
0x180064566  lea     r8, [rsp+320h+var_2E8]
0x18006456b  lea     rdx, IID_IFileSinkFilter
0x180064572  mov     rax, [rcx]
0x180064575  mov     rax, [rax]
0x180064578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006457d  mov     ebx, eax
0x18006457f  cmp     eax, 80004002h
0x180064584  jz      loc_18006467C
0x18006458a  test    eax, eax
0x18006458c  js      loc_180064752
0x180064592  mov     rax, [rdi]
0x180064595  lea     rcx, aSink; "SINK "
0x18006459c  mov     rbx, [rax+20h]
0x1800645a0  call    cs:__imp_lstrlenW
0x1800645a7  nop     dword ptr [rax+rax+00h]
0x1800645ac  xor     r9d, r9d
0x1800645af  lea     rdx, aSink; "SINK "
0x1800645b6  mov     rcx, rdi
0x1800645b9  lea     r8d, [rax+rax]
0x1800645bd  mov     rax, rbx
0x1800645c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800645c5  mov     ebx, eax
0x1800645c7  test    eax, eax
0x1800645c9  js      loc_18006473A
0x1800645cf  xor     edx, edx; Val
0x1800645d1  lea     rcx, [rsp+320h+var_2B0]; void *
0x1800645d6  lea     r8d, [rdx+58h]; Size
0x1800645da  call    memset_0
0x1800645df  mov     rcx, [rsp+320h+var_2E8]
0x1800645e4  lea     r8, [rsp+320h+var_2B0]
0x1800645e9  mov     [rsp+320h+var_2C8], r13
0x1800645ee  lea     rdx, [rsp+320h+var_2C8]
0x1800645f3  mov     rax, [rcx]
0x1800645f6  mov     rax, [rax+20h]
0x1800645fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800645ff  mov     rcx, [rsp+320h+var_2E8]
0x180064604  mov     ebx, eax
0x180064606  mov     rax, [rcx]
0x180064609  mov     rax, [rax+10h]
0x18006460d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064612  test    ebx, ebx
0x180064614  js      loc_180064752
0x18006461a  mov     r9, [rsp+320h+var_2C8]
0x18006461f  lea     r8, aLs_0; "\"%ls\" "
0x180064626  mov     edx, 107h; unsigned __int64
0x18006462b  lea     rcx, [rbp+220h+sz]; Buffer
0x18006462f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180064634  mov     rax, [rdi]
0x180064637  lea     rcx, [rbp+220h+sz]; lpString
0x18006463b  mov     rbx, [rax+20h]
0x18006463f  call    cs:__imp_lstrlenW
0x180064646  nop     dword ptr [rax+rax+00h]
0x18006464b  xor     r9d, r9d
0x18006464e  lea     rdx, [rbp+220h+sz]
0x180064652  mov     rcx, rdi
0x180064655  lea     r8d, [rax+rax]
0x180064659  mov     rax, rbx
0x18006465c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064661  mov     rcx, [rsp+320h+var_2C8]; pv
0x180064666  mov     ebx, eax
0x180064668  call    cs:__imp_CoTaskMemFree
0x18006466f  nop     dword ptr [rax+rax+00h]
0x180064674  test    ebx, ebx
0x180064676  js      loc_180064752
0x18006467c  mov     rcx, [rsi]
0x18006467f  lea     r8, [rsp+320h+var_2E0]
0x180064684  lea     rdx, IID_IPersistStream
0x18006468b  mov     rax, [rcx]
0x18006468e  mov     rax, [rax]
0x180064691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064696  mov     ebx, eax
0x180064698  cmp     eax, 80004002h
0x18006469d  jnz     short loc_1800646C8
0x18006469f  mov     rax, [rdi]
0x1800646a2  lea     rdx, a0000000000; "0000000000 \r\n"
0x1800646a9  xor     r9d, r9d
0x1800646ac  mov     rcx, rdi
0x1800646af  mov     rax, [rax+20h]
0x1800646b3  lea     r8d, [r9+1Ah]
0x1800646b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800646bc  mov     ebx, eax
0x1800646be  test    eax, eax
0x1800646c0  js      loc_180064752
0x1800646c6  jmp     short loc_18006471A
0x1800646c8  test    eax, eax
0x1800646ca  js      loc_180064752
0x1800646d0  mov     r8, [rsp+320h+var_2E0]; struct IPersistStream *
0x1800646d5  mov     r9d, r12d; int
0x1800646d8  mov     rdx, rdi; struct IStream *
0x1800646db  call    ?SaveFilterPrivateData@CFilterGraph@@AEAAJPEAUIStream@@PEAUIPersistStream@@H@Z; CFilterGraph::SaveFilterPrivateData(IStream *,IPersistStream *,int)
0x1800646e0  mov     ebx, eax
0x1800646e2  test    eax, eax
0x1800646e4  js      short loc_180064741
0x1800646e6  mov     rax, [rdi]
0x1800646e9  lea     rdx, asc_1801766B4; "\r\n"
0x1800646f0  xor     r9d, r9d
0x1800646f3  mov     rcx, rdi
0x1800646f6  mov     rax, [rax+20h]
0x1800646fa  lea     r8d, [r9+4]
0x1800646fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064703  mov     ebx, eax
0x180064705  test    eax, eax
0x180064707  js      short loc_180064741
0x180064709  mov     rcx, [rsp+320h+var_2E0]
0x18006470e  mov     rax, [rcx]
0x180064711  mov     rax, [rax+10h]
0x180064715  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
