# NdfRunDllDiagnoseWithAnswerFile(HWND__ *,HINSTANCE__ *,char const *,int)

- ea: `0x18000e8c0`
- end: `0x18000eb20`
- name: `?NdfRunDllDiagnoseWithAnswerFile@@YAXPEAUHWND__@@PEAUHINSTANCE__@@PEBDH@Z`
- size: `608`
- prototype: `void __fastcall(HWND, HINSTANCE, const char *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x18000b95c`
- `0x18000bae8`
- `0x18000bb70`
- `0x18000bdc4`
- `0x18000d8f0`
- `0x18000e5c8`
- `0x18000e8c0`
- `0x18000f264`
- `0x180021010`

## import_xrefs

- `msvcrt!wcsstr` at `0x18000e974`
- `msvcrt!wcsstr` at `0x18000e974`

## pseudocode

```c
void __fastcall NdfRunDllDiagnoseWithAnswerFile(HWND a1, HINSTANCE a2, const char *a3)
{
  __int64 v4; // rax
  unsigned __int16 *v5; // rdi
  unsigned __int16 *v6; // rbx
  wchar_t *v7; // rsi
  wchar_t *v8; // rax
  __int64 v9; // r15
  volatile signed __int32 *v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  volatile signed __int32 *v14; // rdx
  volatile signed __int32 *v15; // [rsp+20h] [rbp-38h] BYREF
  unsigned __int16 *v16; // [rsp+28h] [rbp-30h] BYREF
  unsigned __int16 *v17; // [rsp+30h] [rbp-28h] BYREF
  wchar_t *Str; // [rsp+70h] [rbp+18h] BYREF

  if ( a3 )
  {
    v4 = ((__int64 (__fastcall *)(void ***, HINSTANCE))ATL::g_strmgr[3])(&ATL::g_strmgr, a2);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      Str = (wchar_t *)(v4 + 24);
      if ( (unsigned __int64)a3 >= 0x10000 )
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
          &Str,
          a3);
      else
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
          (ATL::CAtlBaseModule *)&Str,
          (unsigned __int16)a3);
      v5 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      v16 = v5;
      v6 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      v17 = v6;
      v7 = Str;
      if ( *((int *)Str - 4) >= 0 )
      {
        v8 = wcsstr(Str, L" ");
        if ( v8 )
        {
          v9 = v8 - v7;
          if ( (int)v9 > 0 )
          {
            if ( (int)v9 < *((_DWORD *)v7 - 4) )
            {
              v11 = *((_QWORD *)v7 - 3);
              if ( !v11 || (v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 32LL))(v11)) == 0 )
                v12 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                &v15,
                v7,
                (unsigned int)v9,
                v12);
              v10 = v15;
            }
            else
            {
              v10 = ATL::CSimpleStringT<unsigned short,0>::CloneData((volatile signed __int32 *)v7 - 6) + 6;
              v15 = v10;
            }
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
              &v17,
              &v15);
            if ( _InterlockedDecrement(v10 - 2) <= 0 )
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v10 - 3) + 8LL))(*((_QWORD *)v10 - 3));
            v13 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Right(
                    &Str,
                    &v15,
                    (unsigned int)(*((_DWORD *)v7 - 4) - v9 - 1));
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
              &v16,
              v13);
            v14 = v15 - 6;
            if ( _InterlockedDecrement(v15 - 2) <= 0 )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14);
            v5 = v16;
            v6 = v17;
          }
        }
      }
      if ( *((_DWORD *)v5 - 4) && *((_DWORD *)v6 - 4) )
        LaunchMSDT(v5, 0, v6);
      if ( _InterlockedDecrement((volatile signed __int32 *)v6 - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v6 - 3) + 8LL))(*((_QWORD *)v6 - 3));
      if ( _InterlockedDecrement((volatile signed __int32 *)v5 - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v5 - 3) + 8LL))(*((_QWORD *)v5 - 3));
      if ( _InterlockedDecrement((volatile signed __int32 *)v7 - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 - 3) + 8LL))(*((_QWORD *)v7 - 3));
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', 0) )
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000EB0C);
    }
  }
}

```

## disassembly

```asm
0x18000e8c0  test    r8, r8
0x18000e8c3  jz      locret_18000EB1F
0x18000e8c9  mov     [rsp+arg_0], rbx
0x18000e8ce  mov     [rsp+arg_8], rsi
0x18000e8d3  push    rdi
0x18000e8d4  push    r14
0x18000e8d6  push    r15
0x18000e8d8  sub     rsp, 40h
0x18000e8dc  mov     rbx, r8
0x18000e8df  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000e8e6  lea     r14, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000e8ed  mov     rcx, r14
0x18000e8f0  mov     rax, [rax+18h]
0x18000e8f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8f9  add     rax, 18h
0x18000e8fd  mov     [rsp+58h+Str], rax
0x18000e902  lea     rcx, [rsp+58h+Str]
0x18000e907  cmp     rbx, 10000h
0x18000e90e  jnb     short loc_18000E91A
0x18000e910  movzx   edx, bx
0x18000e913  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)
0x18000e918  jmp     short loc_18000E923
0x18000e91a  mov     rdx, rbx
0x18000e91d  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x18000e922  nop
0x18000e923  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000e92a  mov     rcx, r14
0x18000e92d  mov     rax, [rax+18h]
0x18000e931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e936  lea     rdi, [rax+18h]
0x18000e93a  mov     [rsp+58h+var_30], rdi
0x18000e93f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000e946  mov     rcx, r14
0x18000e949  mov     rax, [rax+18h]
0x18000e94d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e952  lea     rbx, [rax+18h]
0x18000e956  mov     [rsp+58h+var_28], rbx
0x18000e95b  mov     rsi, [rsp+58h+Str]
0x18000e960  cmp     dword ptr [rsi-10h], 0
0x18000e964  jl      loc_18000EA85
0x18000e96a  lea     rdx, SubStr; " "
0x18000e971  mov     rcx, rsi; Str
0x18000e974  call    cs:__imp_wcsstr
0x18000e97a  mov     r15, rax
0x18000e97d  test    rax, rax
0x18000e980  jz      loc_18000EA85
0x18000e986  sub     r15, rsi
0x18000e989  sar     r15, 1
0x18000e98c  test    r15d, r15d
0x18000e98f  jle     loc_18000EA85
0x18000e995  cmp     r15d, [rsi-10h]
0x18000e999  jl      short loc_18000E9AF
0x18000e99b  lea     rcx, [rsi-18h]
0x18000e99f  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18000e9a4  lea     rbx, [rax+18h]
0x18000e9a8  mov     [rsp+58h+var_38], rbx
0x18000e9ad  jmp     short loc_18000E9F4
0x18000e9af  mov     rcx, [rsi-18h]
0x18000e9b3  test    rcx, rcx
0x18000e9b6  jz      short loc_18000E9C9
0x18000e9b8  mov     rax, [rcx]
0x18000e9bb  mov     rax, [rax+20h]
0x18000e9bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9c4  test    rax, rax
0x18000e9c7  jnz     short loc_18000E9DC
0x18000e9c9  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000e9d0  mov     rcx, r14
0x18000e9d3  mov     rax, [rax+20h]
0x18000e9d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9dc  mov     r9, rax
0x18000e9df  mov     r8d, r15d
0x18000e9e2  mov     rdx, rsi
0x18000e9e5  lea     rcx, [rsp+58h+var_38]
0x18000e9ea  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBGHPEAUIAtlStringMgr@1@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *,int,ATL::IAtlStringMgr *)
0x18000e9ef  mov     rbx, [rsp+58h+var_38]
0x18000e9f4  lea     rdx, [rsp+58h+var_38]
0x18000e9f9  lea     rcx, [rsp+58h+var_28]
0x18000e9fe  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000ea03  nop
0x18000ea04  lea     rdx, [rbx-18h]
0x18000ea08  or      r14d, 0FFFFFFFFh
0x18000ea0c  mov     eax, r14d
0x18000ea0f  lock xadd [rdx+10h], eax
0x18000ea14  add     eax, r14d
0x18000ea17  test    eax, eax
0x18000ea19  jg      short loc_18000EA2A
0x18000ea1b  mov     rcx, [rdx]
0x18000ea1e  mov     rax, [rcx]
0x18000ea21  mov     rax, [rax+8]
0x18000ea25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea2a  mov     r8d, [rsi-10h]
0x18000ea2e  sub     r8d, r15d
0x18000ea31  dec     r8d
0x18000ea34  lea     rdx, [rsp+58h+var_38]
0x18000ea39  lea     rcx, [rsp+58h+Str]
0x18000ea3e  call    ?Right@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Right(int)
0x18000ea43  nop
0x18000ea44  mov     rdx, rax
0x18000ea47  lea     rcx, [rsp+58h+var_30]
0x18000ea4c  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000ea51  nop
0x18000ea52  mov     rdx, [rsp+58h+var_38]
0x18000ea57  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000ea5b  mov     eax, r14d
0x18000ea5e  lock xadd [rdx+10h], eax
0x18000ea63  add     eax, r14d
0x18000ea66  test    eax, eax
0x18000ea68  jg      short loc_18000EA79
0x18000ea6a  mov     rcx, [rdx]
0x18000ea6d  mov     rax, [rcx]
0x18000ea70  mov     rax, [rax+8]
0x18000ea74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea79  mov     rdi, [rsp+58h+var_30]
0x18000ea7e  mov     rbx, [rsp+58h+var_28]
0x18000ea83  jmp     short loc_18000EA89
0x18000ea85  or      r14d, 0FFFFFFFFh
0x18000ea89  cmp     dword ptr [rdi-10h], 0
0x18000ea8d  jz      short loc_18000EAA3
0x18000ea8f  cmp     dword ptr [rbx-10h], 0
0x18000ea93  jz      short loc_18000EAA3
0x18000ea95  mov     r8, rbx; unsigned __int16 *
0x18000ea98  xor     edx, edx; HWND
0x18000ea9a  mov     rcx, rdi; unsigned __int16 *
0x18000ea9d  call    ?LaunchMSDT@@YAJPEBGPEAUHWND__@@0@Z; LaunchMSDT(ushort const *,HWND__ *,ushort const *)
0x18000eaa2  nop
0x18000eaa3  lea     rdx, [rbx-18h]
0x18000eaa7  mov     eax, r14d
0x18000eaaa  lock xadd [rdx+10h], eax
0x18000eaaf  add     eax, r14d
0x18000eab2  test    eax, eax
0x18000eab4  jg      short loc_18000EAC6
0x18000eab6  mov     rcx, [rdx]
0x18000eab9  mov     rax, [rcx]
0x18000eabc  mov     rax, [rax+8]
0x18000eac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eac5  nop
0x18000eac6  lea     rdx, [rdi-18h]
0x18000eaca  mov     eax, r14d
0x18000eacd  lock xadd [rdx+10h], eax
0x18000ead2  add     eax, r14d
0x18000ead5  test    eax, eax
0x18000ead7  jg      short loc_18000EAE9
0x18000ead9  mov     rcx, [rdx]
0x18000eadc  mov     rax, [rcx]
0x18000eadf  mov     rax, [rax+8]
0x18000eae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eae8  nop
0x18000eae9  lea     rdx, [rsi-18h]
0x18000eaed  mov     eax, r14d
0x18000eaf0  lock xadd [rdx+10h], eax
0x18000eaf5  add     eax, r14d
0x18000eaf8  test    eax, eax
0x18000eafa  jg      short loc_18000EB0C
0x18000eafc  mov     rcx, [rdx]
0x18000eaff  mov     rax, [rcx]
0x18000eb02  mov     rax, [rax+8]
0x18000eb06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb0b  nop
0x18000eb0c  mov     rbx, [rsp+58h+arg_0]
0x18000eb11  mov     rsi, [rsp+58h+arg_8]
0x18000eb16  add     rsp, 40h
0x18000eb1a  pop     r15
0x18000eb1c  pop     r14
0x18000eb1e  pop     rdi
0x18000eb1f  retn
```
