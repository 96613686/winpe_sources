# EnumServerStats(_MI_Context *)

- ea: `0x18000f9c4`
- end: `0x18000fc2d`
- name: `?EnumServerStats@@YAXPEAU_MI_Context@@@Z`
- size: `617`
- prototype: `void __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008dd0`

## callees

- `0x1800098c4`
- `0x18000bde0`
- `0x18000be78`
- `0x18000bff0`
- `0x18000cd6c`
- `0x18000eae4`
- `0x18000f488`
- `0x18000f534`
- `0x18000f9c4`
- `0x180014480`
- `0x18002285c`
- `0x180035b02`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000fc02`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000fc02`

## string_xrefs

- `0x18000fabe`: `mount`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall EnumServerStats(MI_Instance *self)
{
  unsigned int ServerStats; // eax
  enum _MI_Result v3; // ebx
  bool v4; // r15
  const struct _NFS_STAT *v5; // rdx
  __int64 v6; // rdx
  int v7; // edi
  const wchar_t *v8; // rcx
  const wchar_t *v9; // rax
  __int64 v10; // rcx
  const wchar_t *v11; // [rsp+30h] [rbp-D0h] BYREF
  struct _NFS_STAT *v12; // [rsp+38h] [rbp-C8h] BYREF
  struct _NFS_STAT *v13[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+50h] [rbp-B0h]
  _QWORD v15[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v16; // [rsp+68h] [rbp-98h]
  MI_Instance *v17; // [rsp+70h] [rbp-90h]
  int v18; // [rsp+78h] [rbp-88h]
  __int64 v19; // [rsp+7Ch] [rbp-84h]
  int v20; // [rsp+88h] [rbp-78h] BYREF
  int v21; // [rsp+8Ch] [rbp-74h]
  int v22; // [rsp+90h] [rbp-70h]
  _QWORD v23[5]; // [rsp+98h] [rbp-68h] BYREF
  MI_Instance selfa; // [rsp+C0h] [rbp-40h] BYREF
  int v25; // [rsp+110h] [rbp+10h]
  char v26; // [rsp+114h] [rbp+14h]
  int v27; // [rsp+128h] [rbp+28h]
  char v28; // [rsp+12Ch] [rbp+2Ch]

  *(_OWORD *)v13 = 0;
  v14 = 0;
  memset_0(&selfa, 0, 0x70u);
  v15[0] = &CWMIContext::`vftable';
  v17 = self;
  v15[1] = 0;
  v16 = 0;
  v19 = 0;
  v18 = 0;
  ServerStats = GetServerStats((__int64)v13);
  v3 = MapWinErrorToMIResult(ServerStats);
  if ( v3 == MI_RESULT_OK )
  {
    v4 = 0;
    v5 = v13[0];
    v12 = v13[0];
    while ( v5 != v13[1] )
    {
      _NFS_STAT::_NFS_STAT((_NFS_STAT *)&v20, v5);
      if ( self && self->ft )
        v7 = ((__int64 (__fastcall *)(MI_Instance *, void *, MI_Instance *))self->ft->IsA)(
               self,
               &MSFT_NfsStatistics_rtti,
               &selfa);
      else
        v7 = 4;
      v4 = v7 == 0;
      if ( v7 )
      {
        v3 = v7;
      }
      else
      {
        if ( v21 )
        {
          v8 = L"nfs";
          if ( v21 != 1 )
            v8 = 0;
        }
        else
        {
          v8 = L"mount";
        }
        v11 = v8;
        v3 = ((unsigned int (__fastcall *)(MI_Instance *, _QWORD, const wchar_t **, __int64, _DWORD))selfa.ft->SetElementAt)(
               &selfa,
               0,
               &v11,
               13,
               0);
        if ( v3 == MI_RESULT_OK )
        {
          v25 = v20;
          v26 = 1;
        }
      }
      if ( v3 == MI_RESULT_OK )
      {
        v27 = v22;
        v28 = 1;
        v9 = (const wchar_t *)v23;
        if ( v23[3] >= 8u )
          v9 = (const wchar_t *)v23[0];
        v11 = v9;
        v3 = ((unsigned int (__fastcall *)(MI_Instance *, __int64, const wchar_t **, __int64, _DWORD))selfa.ft->SetElementAt)(
               &selfa,
               2,
               &v11,
               13,
               0);
        if ( v3 == MI_RESULT_OK )
          v3 = MI_Instance_Destruct(self);
      }
      if ( !v7 )
      {
        v3 = MI_Instance_Destruct(&selfa);
        v4 = 0;
      }
      if ( v3 || CWMIContext::IsCanceled((CWMIContext *)v15) )
      {
        LOBYTE(v6) = 1;
        std::wstring::_Tidy(v23, v6, 0);
        break;
      }
      LOBYTE(v6) = 1;
      std::wstring::_Tidy(v23, v6, 0);
      std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_NFS_STAT>>>::operator++(&v12);
      v5 = v12;
    }
    if ( v4 )
      MI_Instance_Destruct(&selfa);
  }
  CWMIContext::PostResult((CWMIContext *)v15, v3);
  CWMIContext::~CWMIContext((CWMIContext *)v15);
  if ( v13[0] )
  {
    std::vector<_NFS_STAT>::_Destroy(v10, v13[0], v13[1]);
    operator delete(v13[0]);
  }
}

```

## disassembly

```asm
0x18000f9c4  mov     [rsp-8+arg_8], rbx
0x18000f9c9  mov     [rsp-8+arg_10], rdi
0x18000f9ce  push    rbp
0x18000f9cf  push    r14
0x18000f9d1  push    r15
0x18000f9d3  lea     rbp, [rsp-40h]
0x18000f9d8  sub     rsp, 140h
0x18000f9df  mov     rax, cs:__security_cookie
0x18000f9e6  xor     rax, rsp
0x18000f9e9  mov     [rbp+50h+var_20], rax
0x18000f9ed  mov     r14, rcx
0x18000f9f0  xorps   xmm0, xmm0
0x18000f9f3  movdqu  xmmword ptr [rsp+150h+var_110], xmm0
0x18000f9f9  mov     [rsp+150h+var_100], 0
0x18000fa02  xor     edx, edx; Val
0x18000fa04  lea     r8d, [rdx+70h]; Size
0x18000fa08  lea     rcx, [rbp+50h+self]; void *
0x18000fa0c  call    memset_0
0x18000fa11  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x18000fa18  mov     [rsp+150h+var_F8], rax
0x18000fa1d  mov     [rsp+150h+var_E0], r14
0x18000fa22  mov     [rsp+150h+var_F0], 0
0x18000fa2b  mov     [rsp+150h+var_E8], 0
0x18000fa32  mov     [rsp+150h+var_D4], 0
0x18000fa3b  mov     [rsp+150h+var_D8], 0
0x18000fa43  lea     rcx, [rsp+150h+var_110]
0x18000fa48  call    ?GetServerStats@@YAKAEAV?$vector@U_NFS_STAT@@V?$allocator@U_NFS_STAT@@@std@@@std@@@Z; GetServerStats(std::vector<_NFS_STAT> &)
0x18000fa4d  mov     ecx, eax; unsigned int
0x18000fa4f  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18000fa54  mov     ebx, eax
0x18000fa56  test    eax, eax
0x18000fa58  jnz     loc_18000FBCE
0x18000fa5e  xor     r15b, r15b
0x18000fa61  mov     rdx, [rsp+150h+var_110]; struct _NFS_STAT *
0x18000fa66  mov     [rsp+150h+var_118], rdx
0x18000fa6b  cmp     rdx, [rsp+150h+var_110+8]
0x18000fa70  jz      loc_18000FBC0
0x18000fa76  lea     rcx, [rbp+50h+var_C8]; this
0x18000fa7a  call    ??0_NFS_STAT@@QEAA@AEBU0@@Z; _NFS_STAT::_NFS_STAT(_NFS_STAT const &)
0x18000fa7f  nop
0x18000fa80  test    r14, r14
0x18000fa83  jz      short loc_18000FAA8
0x18000fa85  mov     rax, [r14]
0x18000fa88  test    rax, rax
0x18000fa8b  jz      short loc_18000FAA8
0x18000fa8d  lea     r8, [rbp+50h+self]
0x18000fa91  lea     rdx, MSFT_NfsStatistics_rtti
0x18000fa98  mov     rcx, r14
0x18000fa9b  mov     rax, [rax+18h]
0x18000fa9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000faa4  mov     edi, eax
0x18000faa6  jmp     short loc_18000FAAD
0x18000faa8  mov     edi, 4
0x18000faad  test    edi, edi
0x18000faaf  setz    r15b
0x18000fab3  test    edi, edi
0x18000fab5  jnz     short loc_18000FB14
0x18000fab7  mov     edx, [rbp+50h+var_C4]
0x18000faba  test    edx, edx
0x18000fabc  jnz     short loc_18000FAC7
0x18000fabe  lea     rcx, aMount; "mount"
0x18000fac5  jmp     short loc_18000FAD7
0x18000fac7  lea     rcx, aNfs_0; "nfs"
0x18000face  xor     eax, eax
0x18000fad0  cmp     edx, 1
0x18000fad3  cmovnz  rcx, rax
0x18000fad7  mov     [rsp+150h+var_120], rcx
0x18000fadc  mov     rax, [rbp+50h+self.ft]
0x18000fae0  mov     [rsp+150h+var_130], 0
0x18000fae8  mov     r9d, 0Dh
0x18000faee  lea     r8, [rsp+150h+var_120]
0x18000faf3  xor     edx, edx
0x18000faf5  lea     rcx, [rbp+50h+self]
0x18000faf9  mov     rax, [rax+50h]
0x18000fafd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb02  mov     ebx, eax
0x18000fb04  test    eax, eax
0x18000fb06  jnz     short loc_18000FB16
0x18000fb08  mov     eax, [rbp+50h+var_C8]
0x18000fb0b  mov     [rbp+50h+var_40], eax
0x18000fb0e  mov     [rbp+50h+var_3C], 1
0x18000fb12  jmp     short loc_18000FB16
0x18000fb14  mov     ebx, edi
0x18000fb16  test    ebx, ebx
0x18000fb18  jnz     short loc_18000FB6C
0x18000fb1a  mov     eax, [rbp+50h+var_C0]
0x18000fb1d  mov     [rbp+50h+var_28], eax
0x18000fb20  mov     [rbp+50h+var_24], 1
0x18000fb24  lea     rax, [rbp+50h+var_B8]
0x18000fb28  cmp     [rbp+50h+var_A0], 8
0x18000fb2d  cmovnb  rax, [rbp+50h+var_B8]
0x18000fb32  mov     [rsp+150h+var_120], rax
0x18000fb37  mov     rax, [rbp+50h+self.ft]
0x18000fb3b  mov     [rsp+150h+var_130], ebx
0x18000fb3f  lea     r9d, [rbx+0Dh]
0x18000fb43  lea     r8, [rsp+150h+var_120]
0x18000fb48  lea     edx, [rbx+2]
0x18000fb4b  lea     rcx, [rbp+50h+self]
0x18000fb4f  mov     rax, [rax+50h]
0x18000fb53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb58  mov     ebx, eax
0x18000fb5a  test    eax, eax
0x18000fb5c  jnz     short loc_18000FB6C
0x18000fb5e  lea     rdx, [rbp+50h+self]
0x18000fb62  mov     rcx, r14; self
0x18000fb65  call    MI_Instance_Destruct
0x18000fb6a  mov     ebx, eax
0x18000fb6c  test    edi, edi
0x18000fb6e  jnz     short loc_18000FB7E
0x18000fb70  lea     rcx, [rbp+50h+self]; self
0x18000fb74  call    MI_Instance_Destruct
0x18000fb79  mov     ebx, eax
0x18000fb7b  xor     r15b, r15b
0x18000fb7e  test    ebx, ebx
0x18000fb80  jnz     short loc_18000FBB2
0x18000fb82  lea     rcx, [rsp+150h+var_F8]; this
0x18000fb87  call    ?IsCanceled@CWMIContext@@UEAA_NXZ; CWMIContext::IsCanceled(void)
0x18000fb8c  test    al, al
0x18000fb8e  jnz     short loc_18000FBB2
0x18000fb90  xor     r8d, r8d
0x18000fb93  mov     dl, 1
0x18000fb95  lea     rcx, [rbp+50h+var_B8]
0x18000fb99  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000fb9e  lea     rcx, [rsp+150h+var_118]
0x18000fba3  call    ??E?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U_NFS_STAT@@@std@@@std@@@std@@QEAAAEAV01@XZ; std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_NFS_STAT>>>::operator++(void)
0x18000fba8  mov     rdx, [rsp+150h+var_118]
0x18000fbad  jmp     loc_18000FA6B
0x18000fbb2  xor     r8d, r8d
0x18000fbb5  mov     dl, 1
0x18000fbb7  lea     rcx, [rbp+50h+var_B8]
0x18000fbbb  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000fbc0  test    r15b, r15b
0x18000fbc3  jz      short loc_18000FBCE
0x18000fbc5  lea     rcx, [rbp+50h+self]; self
0x18000fbc9  call    MI_Instance_Destruct
0x18000fbce  mov     edx, ebx; enum _MI_Result
0x18000fbd0  lea     rcx, [rsp+150h+var_F8]; this
0x18000fbd5  call    ?PostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::PostResult(_MI_Result)
0x18000fbda  nop
0x18000fbdb  lea     rcx, [rsp+150h+var_F8]; this
0x18000fbe0  call    ??1CWMIContext@@UEAA@XZ; CWMIContext::~CWMIContext(void)
0x18000fbe5  nop
0x18000fbe6  cmp     [rsp+150h+var_110], 0
0x18000fbec  jz      short loc_18000FC08
0x18000fbee  mov     r8, [rsp+150h+var_110+8]
0x18000fbf3  mov     rdx, [rsp+150h+var_110]
0x18000fbf8  call    ?_Destroy@?$vector@U_NFS_STAT@@V?$allocator@U_NFS_STAT@@@std@@@std@@IEAAXPEAU_NFS_STAT@@0@Z; std::vector<_NFS_STAT>::_Destroy(_NFS_STAT *,_NFS_STAT *)
0x18000fbfd  mov     rcx, [rsp+150h+var_110]
0x18000fc02  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000fc08  mov     rcx, [rbp+50h+var_20]
0x18000fc0c  xor     rcx, rsp; StackCookie
0x18000fc0f  call    __security_check_cookie
0x18000fc14  lea     r11, [rsp+150h+var_10]
0x18000fc1c  mov     rbx, [r11+28h]
0x18000fc20  mov     rdi, [r11+30h]
0x18000fc24  mov     rsp, r11
0x18000fc27  pop     r15
0x18000fc29  pop     r14
0x18000fc2b  pop     rbp
0x18000fc2c  retn
```
