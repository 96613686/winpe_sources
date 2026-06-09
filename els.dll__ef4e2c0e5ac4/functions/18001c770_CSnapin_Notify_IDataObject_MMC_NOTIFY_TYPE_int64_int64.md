# CSnapin::Notify(IDataObject *,_MMC_NOTIFY_TYPE,__int64,__int64)

- ea: `0x18001c770`
- end: `0x18001cab8`
- name: `?Notify@CSnapin@@UEAAJPEAUIDataObject@@W4_MMC_NOTIFY_TYPE@@_J2@Z`
- size: `840`
- prototype: `__int64 __usercall@<rax>(CSnapin *__hidden this@<rcx>, struct IDataObject *@<rdx>, enum _MMC_NOTIFY_TYPE@<r8d>, __int64@<r9>, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x180001750`
- `0x180001910`
- `0x180001f64`
- `0x180002680`
- `0x1800050ac`
- `0x1800050fc`
- `0x180014b4c`
- `0x18001c770`
- `0x18001d714`
- `0x18001d874`
- `0x18001d948`
- `0x18001daf4`
- `0x18001f638`
- `0x180021060`
- `0x1800222d0`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18001c955`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18001c955`

## pseudocode

```c
__int64 __fastcall CSnapin::Notify(unsigned __int64 this, struct IDataObject *a2, int a3, __int64 a4, __int64 a5)
{
  unsigned int v9; // esi
  HCURSOR OwnDataObject; // r9
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  unsigned int v17; // ebx
  struct CDataObject *v18; // rax
  int v19; // ebx
  int v20; // ebx
  int v21; // ebx
  int v22; // ebx
  int v23; // ebx
  __int64 wstring; // rbx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rdx
  _QWORD *v34; // rdx
  unsigned int v35; // eax
  __int64 v36; // rdx
  _QWORD v38[4]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v39[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v40[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v41[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v42[32]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Buffer[264]; // [rsp+D0h] [rbp-30h] BYREF

  v9 = 0;
  OwnDataObject = 0;
  if ( a2 )
    OwnDataObject = (HCURSOR)ExtractOwnDataObject(a2);
  if ( a3 > 32789 )
  {
    v19 = a3 - 32790;
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( v20 )
      {
        v21 = v20 - 1;
        if ( v21 && (v22 = v21 - 1) != 0 )
        {
          v23 = v22 - 2;
          if ( v23 && v23 != 7 )
            return (unsigned int)-2147467263;
        }
        else if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) )
        {
          wstring = load_wstring(v42, 301);
          v25 = std::wstring::wstring(v41, Buffer);
          v26 = std::operator+<unsigned short>(v40, v25, L"\\help\\els.chm");
          v27 = std::operator+<unsigned short>(v39, v26, L"::");
          if ( *(_QWORD *)(wstring + 16) <= *(_QWORD *)(v27 + 24) - *(_QWORD *)(v27 + 16)
            || *(_QWORD *)(wstring + 24) - *(_QWORD *)(wstring + 16) < *(_QWORD *)(v27 + 16) )
          {
            v29 = std::wstring::append(v27, wstring, 0, -1);
          }
          else
          {
            v29 = std::wstring::insert(wstring, v28, v27);
          }
          std::wstring::wstring(v38, v29);
          LOBYTE(v30) = 1;
          std::wstring::_Tidy(v39, v30, 0);
          LOBYTE(v31) = 1;
          std::wstring::_Tidy(v40, v31, 0);
          LOBYTE(v32) = 1;
          std::wstring::_Tidy(v41, v32, 0);
          LOBYTE(v33) = 1;
          std::wstring::_Tidy(v42, v33, 0);
          v34 = v38;
          if ( v38[3] >= 8u )
            v34 = (_QWORD *)v38[0];
          v35 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)(this + 1656) + 24LL))(
                  *(_QWORD *)(this + 1656),
                  v34);
          LOBYTE(v36) = 1;
          v9 = v35;
          std::wstring::_Tidy(v38, v36, 0);
        }
        else
        {
          return (unsigned int)-2147418113;
        }
      }
    }
    else if ( OwnDataObject )
    {
      *(_QWORD *)(*(_QWORD *)(this + 1592) + 72LL) = this & -(__int64)(a4 != 0);
      return (unsigned int)CSnapin::_OnShow((CSnapin *)this, (struct CDataObject *)OwnDataObject, a4, OwnDataObject);
    }
  }
  else if ( a3 == 32789 )
  {
    if ( OwnDataObject )
    {
      if ( (_WORD)a4 && WORD1(a4) )
        *(_QWORD *)(*(_QWORD *)(this + 1592) + 72LL) = this;
      return (unsigned int)CSnapin::_OnSelect(
                             (CSnapin *)this,
                             (unsigned __int16)a4,
                             WORD1(a4),
                             (struct CDataObject *)OwnDataObject);
    }
  }
  else
  {
    v11 = a3 - 32769;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( !v12 )
        return (unsigned int)CSnapin::_InitializeResultBitmaps((CSnapin *)this);
      v13 = v12 - 2;
      if ( v13 )
      {
        v14 = v13 - 4;
        if ( v14 )
        {
          v15 = v14 - 2;
          if ( v15 )
          {
            if ( v15 == 8 )
              return (unsigned int)(*(__int64 (__fastcall **)(__int64, struct IDataObject *, __int64, __int64, __int64))(*(_QWORD *)(*(_QWORD *)(this + 1592) + 8LL) + 40LL))(
                                     *(_QWORD *)(this + 1592) + 8LL,
                                     a2,
                                     32786,
                                     a4,
                                     a5);
            return (unsigned int)-2147467263;
          }
          *(_QWORD *)(this + 1584) = 0;
        }
        else if ( OwnDataObject )
        {
          v17 = *((_DWORD *)OwnDataObject + 4);
          v18 = ExtractOwnDataObject(a2);
          if ( v18 )
          {
            if ( *((_DWORD *)v18 + 7) == 2 )
            {
              *(_DWORD *)(this + 1584) = v17;
              if ( !*(_DWORD *)(this + 1520) && !*(_QWORD *)(this + 1528) )
                return (unsigned int)CSnapin::_InvokePropertySheet((CSnapin *)this, v17, a2);
              CInspectorInfo::BringToForeground((CInspectorInfo *)(this + 1520));
            }
            else
            {
              return 1;
            }
          }
        }
      }
    }
    else if ( a4 )
    {
      *(_QWORD *)(*(_QWORD *)(this + 1592) + 72LL) = this;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18001c770  push    rbp
0x18001c772  push    rbx
0x18001c773  push    rsi
0x18001c774  push    rdi
0x18001c775  push    r12
0x18001c777  push    r14
0x18001c779  push    r15
0x18001c77b  lea     rbp, [rsp-1F0h]
0x18001c783  sub     rsp, 2F0h
0x18001c78a  mov     rax, cs:__security_cookie
0x18001c791  xor     rax, rsp
0x18001c794  mov     [rbp+220h+var_40], rax
0x18001c79b  xor     r12d, r12d
0x18001c79e  mov     r14, r9
0x18001c7a1  mov     ebx, r8d
0x18001c7a4  mov     r15, rdx
0x18001c7a7  mov     rdi, rcx
0x18001c7aa  mov     esi, r12d
0x18001c7ad  mov     r9d, r12d
0x18001c7b0  test    rdx, rdx
0x18001c7b3  jz      short loc_18001C7C0
0x18001c7b5  mov     rcx, rdx; struct IDataObject *
0x18001c7b8  call    ?ExtractOwnDataObject@@YAPEAVCDataObject@@PEAUIDataObject@@@Z; ExtractOwnDataObject(IDataObject *)
0x18001c7bd  mov     r9, rax; __int64
0x18001c7c0  mov     eax, 8015h
0x18001c7c5  cmp     ebx, eax
0x18001c7c7  jg      loc_18001C911
0x18001c7cd  jz      loc_18001C8CF
0x18001c7d3  sub     ebx, 8001h
0x18001c7d9  jz      loc_18001C8B6
0x18001c7df  sub     ebx, 1
0x18001c7e2  jz      loc_18001C8A9
0x18001c7e8  sub     ebx, 2
0x18001c7eb  jz      loc_18001CA95
0x18001c7f1  sub     ebx, 4
0x18001c7f4  jz      short loc_18001C847
0x18001c7f6  sub     ebx, 2
0x18001c7f9  jz      short loc_18001C83B
0x18001c7fb  cmp     ebx, 8
0x18001c7fe  jnz     loc_18001C942
0x18001c804  mov     rcx, [rdi+638h]
0x18001c80b  mov     r9, r14
0x18001c80e  add     rcx, 8
0x18001c812  mov     r8d, 8012h
0x18001c818  mov     rdx, r15
0x18001c81b  mov     rax, [rcx]
0x18001c81e  mov     r10, [rax+28h]
0x18001c822  mov     rax, [rbp+220h+arg_20]
0x18001c829  mov     [rsp+320h+var_300], rax
0x18001c82e  mov     rax, r10
0x18001c831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c836  jmp     loc_18001CA93
0x18001c83b  mov     [rdi+630h], r12
0x18001c842  jmp     loc_18001CA95
0x18001c847  test    r9, r9
0x18001c84a  jz      loc_18001CA95
0x18001c850  mov     ebx, [r9+10h]
0x18001c854  mov     rcx, r15; struct IDataObject *
0x18001c857  call    ?ExtractOwnDataObject@@YAPEAVCDataObject@@PEAUIDataObject@@@Z; ExtractOwnDataObject(IDataObject *)
0x18001c85c  test    rax, rax
0x18001c85f  jz      loc_18001CA95
0x18001c865  cmp     dword ptr [rax+1Ch], 2
0x18001c869  jz      short loc_18001C875
0x18001c86b  mov     esi, 1
0x18001c870  jmp     loc_18001CA95
0x18001c875  lea     rcx, [rdi+5F0h]; this
0x18001c87c  mov     [rdi+630h], ebx
0x18001c882  cmp     [rcx], r12d
0x18001c885  jnz     short loc_18001C89F
0x18001c887  cmp     [rcx+8], r12
0x18001c88b  jnz     short loc_18001C89F
0x18001c88d  mov     r8, r15; struct IDataObject *
0x18001c890  mov     edx, ebx; unsigned int
0x18001c892  mov     rcx, rdi; this
0x18001c895  call    ?_InvokePropertySheet@CSnapin@@AEAAJKPEAUIDataObject@@@Z; CSnapin::_InvokePropertySheet(ulong,IDataObject *)
0x18001c89a  jmp     loc_18001CA93
0x18001c89f  call    ?BringToForeground@CInspectorInfo@@QEAAXXZ; CInspectorInfo::BringToForeground(void)
0x18001c8a4  jmp     loc_18001CA95
0x18001c8a9  mov     rcx, rdi; this
0x18001c8ac  call    ?_InitializeResultBitmaps@CSnapin@@AEAAJXZ; CSnapin::_InitializeResultBitmaps(void)
0x18001c8b1  jmp     loc_18001CA93
0x18001c8b6  test    r14, r14
0x18001c8b9  jz      loc_18001CA95
0x18001c8bf  mov     rax, [rdi+638h]
0x18001c8c6  mov     [rax+48h], rdi
0x18001c8ca  jmp     loc_18001CA95
0x18001c8cf  test    r9, r9
0x18001c8d2  jz      loc_18001CA95
0x18001c8d8  test    r14w, r14w
0x18001c8dc  jz      short loc_18001C8F5
0x18001c8de  mov     rax, r14
0x18001c8e1  shr     rax, 10h
0x18001c8e5  test    ax, ax
0x18001c8e8  jz      short loc_18001C8F5
0x18001c8ea  mov     rax, [rdi+638h]
0x18001c8f1  mov     [rax+48h], rdi
0x18001c8f5  mov     rax, r14
0x18001c8f8  movzx   edx, r14w; int
0x18001c8fc  shr     rax, 10h
0x18001c900  mov     rcx, rdi; this
0x18001c903  movzx   r8d, ax; int
0x18001c907  call    ?_OnSelect@CSnapin@@AEAAJHHPEAVCDataObject@@@Z; CSnapin::_OnSelect(int,int,CDataObject *)
0x18001c90c  jmp     loc_18001CA93
0x18001c911  sub     ebx, 8016h
0x18001c917  jz      loc_18001CA69
0x18001c91d  sub     ebx, 1
0x18001c920  jz      loc_18001CA95
0x18001c926  sub     ebx, 1
0x18001c929  jz      short loc_18001C94C
0x18001c92b  sub     ebx, 1
0x18001c92e  jz      short loc_18001C94C
0x18001c930  sub     ebx, 2
0x18001c933  jz      loc_18001CA95
0x18001c939  cmp     ebx, 7
0x18001c93c  jz      loc_18001CA95
0x18001c942  mov     esi, 80004001h
0x18001c947  jmp     loc_18001CA95
0x18001c94c  mov     edx, 104h; uSize
0x18001c951  lea     rcx, [rbp+220h+Buffer]; lpBuffer
0x18001c955  call    cs:__imp_GetSystemWindowsDirectoryW
0x18001c95b  test    eax, eax
0x18001c95d  jz      loc_18001CA62
0x18001c963  mov     edx, 12Dh
0x18001c968  lea     rcx, [rbp+220h+var_270]
0x18001c96c  call    ?load_wstring@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z; load_wstring(int)
0x18001c971  lea     rdx, [rbp+220h+Buffer]
0x18001c975  mov     rbx, rax
0x18001c978  lea     rcx, [rbp+220h+var_290]
0x18001c97c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001c981  mov     rdx, rax
0x18001c984  lea     r8, aHelpElsChm; "\\help\\els.chm"
0x18001c98b  lea     rcx, [rsp+320h+var_2B0]
0x18001c990  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18001c995  mov     rdx, rax
0x18001c998  lea     r8, asc_180029A38; "::"
0x18001c99f  lea     rcx, [rsp+320h+var_2D0]
0x18001c9a4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18001c9a9  mov     rcx, [rax+18h]
0x18001c9ad  sub     rcx, [rax+10h]
0x18001c9b1  cmp     [rbx+10h], rcx
0x18001c9b5  jbe     short loc_18001C9D2
0x18001c9b7  mov     rcx, [rbx+18h]
0x18001c9bb  sub     rcx, [rbx+10h]
0x18001c9bf  cmp     rcx, [rax+10h]
0x18001c9c3  jb      short loc_18001C9D2
0x18001c9c5  mov     r8, rax
0x18001c9c8  mov     rcx, rbx
0x18001c9cb  call    ?insert@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KAEBV12@00@Z; std::wstring::insert(unsigned __int64,std::wstring const &,unsigned __int64,unsigned __int64)
0x18001c9d0  jmp     short loc_18001C9E4
0x18001c9d2  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001c9d6  xor     r8d, r8d
0x18001c9d9  mov     rdx, rbx
0x18001c9dc  mov     rcx, rax
0x18001c9df  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001c9e4  mov     rdx, rax
0x18001c9e7  lea     rcx, [rsp+320h+var_2F0]
0x18001c9ec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18001c9f1  xor     r8d, r8d
0x18001c9f4  lea     rcx, [rsp+320h+var_2D0]
0x18001c9f9  mov     dl, 1
0x18001c9fb  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ca00  xor     r8d, r8d
0x18001ca03  lea     rcx, [rsp+320h+var_2B0]
0x18001ca08  mov     dl, 1
0x18001ca0a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ca0f  xor     r8d, r8d
0x18001ca12  lea     rcx, [rbp+220h+var_290]
0x18001ca16  mov     dl, 1
0x18001ca18  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ca1d  xor     r8d, r8d
0x18001ca20  lea     rcx, [rbp+220h+var_270]
0x18001ca24  mov     dl, 1
0x18001ca26  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ca2b  mov     rcx, [rdi+678h]
0x18001ca32  lea     rdx, [rsp+320h+var_2F0]
0x18001ca37  cmp     [rsp+320h+var_2D8], 8
0x18001ca3d  cmovnb  rdx, [rsp+320h+var_2F0]
0x18001ca43  mov     rax, [rcx]
0x18001ca46  mov     rax, [rax+18h]
0x18001ca4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca4f  xor     r8d, r8d
0x18001ca52  lea     rcx, [rsp+320h+var_2F0]
0x18001ca57  mov     dl, 1
0x18001ca59  mov     esi, eax
0x18001ca5b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ca60  jmp     short loc_18001CA95
0x18001ca62  mov     esi, 8000FFFFh
0x18001ca67  jmp     short loc_18001CA95
0x18001ca69  test    r9, r9
0x18001ca6c  jz      short loc_18001CA95
0x18001ca6e  mov     rax, r14
0x18001ca71  mov     r8d, r14d; int
0x18001ca74  neg     rax
0x18001ca77  mov     rdx, r9; struct CDataObject *
0x18001ca7a  mov     rax, [rdi+638h]
0x18001ca81  sbb     rcx, rcx
0x18001ca84  and     rcx, rdi
0x18001ca87  mov     [rax+48h], rcx
0x18001ca8b  mov     rcx, rdi; this
0x18001ca8e  call    ?_OnShow@CSnapin@@AEAAJPEAVCDataObject@@H_J@Z; CSnapin::_OnShow(CDataObject *,int,__int64)
0x18001ca93  mov     esi, eax
0x18001ca95  mov     eax, esi
0x18001ca97  mov     rcx, [rbp+220h+var_40]
0x18001ca9e  xor     rcx, rsp; StackCookie
0x18001caa1  call    __security_check_cookie
0x18001caa6  add     rsp, 2F0h
0x18001caad  pop     r15
0x18001caaf  pop     r14
0x18001cab1  pop     r12
0x18001cab3  pop     rdi
0x18001cab4  pop     rsi
0x18001cab5  pop     rbx
0x18001cab6  pop     rbp
0x18001cab7  retn
```
