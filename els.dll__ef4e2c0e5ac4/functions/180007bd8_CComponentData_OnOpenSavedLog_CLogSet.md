# CComponentData::_OnOpenSavedLog(CLogSet *)

- ea: `0x180007bd8`
- end: `0x180007edb`
- name: `?_OnOpenSavedLog@CComponentData@@AEAAJPEAVCLogSet@@@Z`
- size: `771`
- prototype: `__int64 __fastcall(CComponentData *this, struct CLogSet *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800056c0`

## callees

- `0x180001910`
- `0x180002928`
- `0x18000513c`
- `0x180007bd8`
- `0x180008dc8`
- `0x180009050`
- `0x180015e48`
- `0x1800165b0`
- `0x180017630`
- `0x180020430`
- `0x180022292`
- `0x1800222d0`
- `0x180024010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180007da8`
- `msvcrt!wcsncpy_s` at `0x180007de4`
- `msvcrt!wcsncpy_s` at `0x180007dff`
- `msvcrt!wcsncpy_s` at `0x180007da8`
- `msvcrt!wcsncpy_s` at `0x180007de4`
- `msvcrt!wcsncpy_s` at `0x180007dff`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CComponentData::_OnOpenSavedLog(CComponentData *this, struct CLogSet *a2)
{
  __int64 v4; // rdx
  int Str; // edi
  void *v6; // rax
  __int64 v7; // rax
  __int64 v8; // rbx
  const wchar_t *v9; // r8
  __int64 v10; // rax
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v13[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v14; // [rsp+48h] [rbp-B8h]
  int v15; // [rsp+4Ch] [rbp-B4h]
  __int64 v16; // [rsp+50h] [rbp-B0h]
  __int64 v17; // [rsp+58h] [rbp-A8h]
  __int64 v18; // [rsp+60h] [rbp-A0h]
  __int64 v19; // [rsp+68h] [rbp-98h]
  void *v20; // [rsp+70h] [rbp-90h]
  int v21; // [rsp+80h] [rbp-80h] BYREF
  __int64 v22; // [rsp+88h] [rbp-78h]
  HINSTANCE v23; // [rsp+90h] [rbp-70h]
  wchar_t *v24; // [rsp+98h] [rbp-68h]
  int v25; // [rsp+ACh] [rbp-54h]
  wchar_t *v26; // [rsp+B0h] [rbp-50h]
  int v27; // [rsp+B8h] [rbp-48h]
  int v28; // [rsp+E0h] [rbp-20h]
  unsigned __int16 *v29; // [rsp+F0h] [rbp-10h]
  unsigned __int64 (__fastcall *v30)(HWND, unsigned int, unsigned __int16 *, __int64); // [rsp+F8h] [rbp-8h]
  __int64 v31; // [rsp+100h] [rbp+0h]
  unsigned __int16 v32[260]; // [rsp+120h] [rbp+20h] BYREF
  wchar_t *v33[4]; // [rsp+328h] [rbp+228h] BYREF
  wchar_t Source[260]; // [rsp+348h] [rbp+248h] BYREF
  int v35; // [rsp+550h] [rbp+450h]
  int v36; // [rsp+554h] [rbp+454h]
  wchar_t v37; // [rsp+560h] [rbp+460h] BYREF
  char v38[526]; // [rsp+562h] [rbp+462h] BYREF
  wchar_t Destination[264]; // [rsp+770h] [rbp+670h] BYREF

  memset_0(&v21, 0, 0x98u);
  v12 = 0;
  v37 = 0;
  memset_0(v38, 0, 0x206u);
  std::wstring::wstring(v33);
  memset_0(Destination, 0, 0x104u);
  memset_0(v32, 0, 0x438u);
  (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 144) + 96LL))(*((_QWORD *)this + 144), &v12);
  Str = LoadStr(0x105u, Destination, 0x104u, 0);
  if ( Str >= 0 )
  {
    memset_0(&v21, 0, 0x98u);
    v21 = 152;
    v22 = v12;
    v23 = g_hinst;
    v24 = Destination;
    v25 = 1;
    v26 = &v37;
    v27 = 260;
    v28 = 530532;
    v31 = 107;
    v30 = CComponentData::_OpenDlgHookProc;
    v29 = v32;
    if ( (unsigned int)IsolationAwareGetOpenFileNameW(&v21) )
    {
      v6 = operator new(0x1318u);
      v20 = v6;
      if ( v6 && (v7 = CLogInfo::CLogInfo((__int64)v6, (__int64)this, (__int64)a2, v36, 1, v35), (v8 = v7) != 0) )
      {
        *(_WORD *)(v7 + 24) |= 0x508u;
        wcsncpy_s((wchar_t *)(v7 + 32), 0x105u, Source, 0x104u);
        CLogInfo::SetDisplayName((CLogInfo *)v8, v32);
        v9 = (const wchar_t *)v33;
        if ( v33[3] >= (wchar_t *)8 )
          v9 = v33[0];
        wcsncpy_s((wchar_t *)(v8 + 554), 0x105u, v9, 0x104u);
        wcsncpy_s((wchar_t *)(v8 + 1076), 0x105u, &v37, 0x104u);
        CLogSet::AddLogInfoToList(a2, (struct CLogInfo *)v8);
        v10 = *((_QWORD *)this + 142);
        if ( v10 )
        {
          v13[0] = 110;
          v16 = 0;
          v19 = 0;
          v18 = v10;
          v14 = 0;
          v15 = 1;
          v13[1] = -1;
          v17 = v8;
          Str = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 145) + 24LL))(
                  *((_QWORD *)this + 145),
                  v13);
          v4 = v19;
          *(_QWORD *)(v8 + 4856) = v19;
          if ( Str >= 0 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 144) + 88LL))(*((_QWORD *)this + 144));
        }
      }
      else
      {
        Str = -2147024882;
      }
    }
    else
    {
      IsolationAwareCommDlgExtendedError();
    }
  }
  LOBYTE(v4) = 1;
  std::wstring::_Tidy(v33, v4, 0);
  return (unsigned int)Str;
}

```

## disassembly

```asm
0x180007bd8  mov     [rsp-8+arg_10], rbx
0x180007bdd  push    rbp
0x180007bde  push    rsi
0x180007bdf  push    rdi
0x180007be0  push    r14
0x180007be2  push    r15
0x180007be4  lea     rbp, [rsp-890h]
0x180007bec  sub     rsp, 990h
0x180007bf3  mov     rax, cs:__security_cookie
0x180007bfa  xor     rax, rsp
0x180007bfd  mov     [rbp+8B0h+var_30], rax
0x180007c04  mov     r14, rdx
0x180007c07  mov     rsi, rcx
0x180007c0a  mov     ebx, 98h
0x180007c0f  mov     r8d, ebx; Size
0x180007c12  xor     edx, edx; Val
0x180007c14  lea     rcx, [rbp+8B0h+var_930]; void *
0x180007c18  call    memset_0
0x180007c1d  mov     [rsp+9B0h+var_980], 0
0x180007c26  xor     eax, eax
0x180007c28  mov     [rbp+8B0h+var_450], ax
0x180007c2f  xor     edx, edx; Val
0x180007c31  mov     r8d, 206h; Size
0x180007c37  lea     rcx, [rbp+8B0h+var_44E]; void *
0x180007c3e  call    memset_0
0x180007c43  lea     rcx, [rbp+8B0h+var_688]
0x180007c4a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180007c4f  nop
0x180007c50  lea     r15d, [rbx+6Ch]
0x180007c54  mov     r8d, r15d; Size
0x180007c57  xor     edx, edx; Val
0x180007c59  lea     rcx, [rbp+8B0h+Destination]; void *
0x180007c60  call    memset_0
0x180007c65  xor     edx, edx; Val
0x180007c67  mov     r8d, 438h; Size
0x180007c6d  lea     rcx, [rbp+8B0h+var_890]; void *
0x180007c71  call    memset_0
0x180007c76  mov     rcx, [rsi+480h]
0x180007c7d  mov     rax, [rcx]
0x180007c80  lea     rdx, [rsp+9B0h+var_980]
0x180007c85  mov     rax, [rax+60h]
0x180007c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c8e  xor     r9d, r9d; Source
0x180007c91  mov     r8d, r15d; SizeInWords
0x180007c94  lea     rdx, [rbp+8B0h+Destination]; Destination
0x180007c9b  lea     ecx, [rbx+6Dh]; uID
0x180007c9e  call    ?LoadStr@@YAJKPEAGKPEBG@Z; LoadStr(ulong,ushort *,ulong,ushort const *)
0x180007ca3  mov     edi, eax
0x180007ca5  test    eax, eax
0x180007ca7  js      loc_180007EA2
0x180007cad  mov     r8d, ebx; Size
0x180007cb0  xor     edx, edx; Val
0x180007cb2  lea     rcx, [rbp+8B0h+var_930]; void *
0x180007cb6  call    memset_0
0x180007cbb  mov     [rbp+8B0h+var_930], ebx
0x180007cbe  mov     rcx, [rsp+9B0h+var_980]
0x180007cc3  mov     [rbp+8B0h+var_928], rcx
0x180007cc7  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x180007cce  mov     [rbp+8B0h+var_920], rcx
0x180007cd2  lea     rax, [rbp+8B0h+Destination]
0x180007cd9  mov     [rbp+8B0h+var_918], rax
0x180007cdd  mov     [rbp+8B0h+var_904], 1
0x180007ce4  lea     rax, [rbp+8B0h+var_450]
0x180007ceb  mov     [rbp+8B0h+var_900], rax
0x180007cef  mov     [rbp+8B0h+var_8F8], r15d
0x180007cf3  mov     [rbp+8B0h+var_8D0], 81864h
0x180007cfa  mov     [rbp+8B0h+var_8B0], 6Bh ; 'k'
0x180007d02  lea     rax, ?_OpenDlgHookProc@CComponentData@@CA_KPEAUHWND__@@I_K_J@Z; CComponentData::_OpenDlgHookProc(HWND__ *,uint,unsigned __int64,__int64)
0x180007d09  mov     [rbp+8B0h+var_8B8], rax
0x180007d0d  lea     rax, [rbp+8B0h+var_890]
0x180007d11  mov     [rbp+8B0h+var_8C0], rax
0x180007d15  lea     rcx, [rbp+8B0h+var_930]
0x180007d19  call    IsolationAwareGetOpenFileNameW
0x180007d1e  test    eax, eax
0x180007d20  jnz     short loc_180007D2C
0x180007d22  call    IsolationAwareCommDlgExtendedError
0x180007d27  jmp     loc_180007EA2
0x180007d2c  mov     ecx, 1318h; Size
0x180007d31  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007d36  mov     [rsp+9B0h+var_940], rax
0x180007d3b  test    rax, rax
0x180007d3e  jz      loc_180007E9D
0x180007d44  mov     ecx, [rbp+8B0h+var_460]
0x180007d4a  mov     [rsp+9B0h+var_988], ecx
0x180007d4e  mov     [rsp+9B0h+var_990], 1
0x180007d56  mov     r9d, [rbp+8B0h+var_45C]
0x180007d5d  mov     r8, r14
0x180007d60  mov     rdx, rsi
0x180007d63  mov     rcx, rax
0x180007d66  call    ??0CLogInfo@@QEAA@PEAVCComponentData@@PEAVCLogSet@@W4EVENTLOGTYPE@@HH@Z; CLogInfo::CLogInfo(CComponentData *,CLogSet *,EVENTLOGTYPE,int,int)
0x180007d6b  mov     rbx, rax
0x180007d6e  test    rax, rax
0x180007d71  jz      loc_180007E9D
0x180007d77  movzx   edx, word ptr [rax+18h]
0x180007d7b  mov     r15d, 8
0x180007d81  or      dx, r15w
0x180007d85  or      dx, 100h
0x180007d8a  or      dx, 400h
0x180007d8f  mov     [rax+18h], dx
0x180007d93  lea     rcx, [rax+20h]; Destination
0x180007d97  mov     r9d, 104h; MaxCount
0x180007d9d  lea     r8, [rbp+8B0h+Source]; Source
0x180007da4  lea     edx, [r9+1]; SizeInWords
0x180007da8  call    cs:__imp_wcsncpy_s
0x180007dae  lea     rdx, [rbp+8B0h+var_890]; unsigned __int16 *
0x180007db2  mov     rcx, rbx; this
0x180007db5  call    ?SetDisplayName@CLogInfo@@QEAAXPEBG@Z; CLogInfo::SetDisplayName(ushort const *)
0x180007dba  lea     r8, [rbp+8B0h+var_688]
0x180007dc1  cmp     [rbp+8B0h+var_670], r15
0x180007dc8  cmovnb  r8, [rbp+8B0h+var_688]; Source
0x180007dd0  lea     rcx, [rbx+22Ah]; Destination
0x180007dd7  mov     r15d, 104h
0x180007ddd  mov     r9d, r15d; MaxCount
0x180007de0  lea     edx, [r15+1]; SizeInWords
0x180007de4  call    cs:__imp_wcsncpy_s
0x180007dea  lea     rcx, [rbx+434h]; Destination
0x180007df1  mov     r9d, r15d; MaxCount
0x180007df4  lea     r8, [rbp+8B0h+var_450]; Source
0x180007dfb  lea     edx, [r15+1]; SizeInWords
0x180007dff  call    cs:__imp_wcsncpy_s
0x180007e05  mov     rdx, rbx; struct CLogInfo *
0x180007e08  mov     rcx, r14; this
0x180007e0b  call    ?AddLogInfoToList@CLogSet@@QEAAXPEAVCLogInfo@@@Z; CLogSet::AddLogInfoToList(CLogInfo *)
0x180007e10  mov     rax, [rsi+470h]
0x180007e17  test    rax, rax
0x180007e1a  jz      loc_180007EA2
0x180007e20  mov     [rsp+9B0h+var_978], 6Eh ; 'n'
0x180007e29  mov     [rsp+9B0h+var_960], 0
0x180007e32  mov     [rsp+9B0h+var_948], 0
0x180007e3b  mov     [rsp+9B0h+var_950], rax
0x180007e40  mov     [rsp+9B0h+var_968], 0
0x180007e48  mov     [rsp+9B0h+var_964], 1
0x180007e50  mov     [rsp+9B0h+var_970], 0FFFFFFFFFFFFFFFFh
0x180007e59  mov     [rsp+9B0h+var_958], rbx
0x180007e5e  mov     rcx, [rsi+488h]
0x180007e65  mov     rax, [rcx]
0x180007e68  lea     rdx, [rsp+9B0h+var_978]
0x180007e6d  mov     rax, [rax+18h]
0x180007e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e76  mov     edi, eax
0x180007e78  mov     rdx, [rsp+9B0h+var_948]
0x180007e7d  mov     [rbx+12F8h], rdx
0x180007e84  test    eax, eax
0x180007e86  js      short loc_180007EA2
0x180007e88  mov     rcx, [rsi+480h]
0x180007e8f  mov     rax, [rcx]
0x180007e92  mov     rax, [rax+58h]
0x180007e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e9b  jmp     short loc_180007EA2
0x180007e9d  mov     edi, 8007000Eh
0x180007ea2  xor     r8d, r8d
0x180007ea5  mov     dl, 1
0x180007ea7  lea     rcx, [rbp+8B0h+var_688]
0x180007eae  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180007eb3  mov     eax, edi
0x180007eb5  mov     rcx, [rbp+8B0h+var_30]
0x180007ebc  xor     rcx, rsp; StackCookie
0x180007ebf  call    __security_check_cookie
0x180007ec4  mov     rbx, [rsp+9B0h+arg_10]
0x180007ecc  add     rsp, 990h
0x180007ed3  pop     r15
0x180007ed5  pop     r14
0x180007ed7  pop     rdi
0x180007ed8  pop     rsi
0x180007ed9  pop     rbp
0x180007eda  retn
```
