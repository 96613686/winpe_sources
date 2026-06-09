# CSessionBaseRO::ConstructTargetPath(SmartPtr<CFileRecord>,long,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)

- ea: `0x180009d70`
- end: `0x18000a0a4`
- name: `?ConstructTargetPath@CSessionBaseRO@@IEAAJV?$SmartPtr@VCFileRecord@@@@JAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z`
- size: `820`
- prototype: `__int64 __fastcall(__int64, _QWORD **, unsigned int, __int64, _QWORD *)`
- caller_count: `5`
- callee_count: `14`
- tags: ``

## callers

- `0x18000c450`
- `0x18000f728`
- `0x180012b44`
- `0x180013e14`
- `0x180024170`

## callees

- `0x180002c24`
- `0x1800062d0`
- `0x180007818`
- `0x180007a9c`
- `0x18000815c`
- `0x1800091a4`
- `0x180009258`
- `0x18000935c`
- `0x180009920`
- `0x180009d70`
- `0x18000a1ec`
- `0x180028508`
- `0x180031680`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180009ef0`
- `KERNEL32!GetLastError` at `0x180009ef0`
- `KERNEL32!FileTimeToSystemTime` at `0x180009ee6`
- `KERNEL32!FileTimeToSystemTime` at `0x180009ee6`

## pseudocode

```c
__int64 __fastcall CSessionBaseRO::ConstructTargetPath(
        __int64 a1,
        _QWORD **a2,
        unsigned int a3,
        __int64 a4,
        __int64 *a5)
{
  __int64 v5; // r12
  _QWORD **v7; // rdi
  __int64 v8; // r15
  signed int Name; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  char *v13; // rdx
  volatile signed __int32 *v14; // rcx
  int *v15; // rsi
  __int64 v16; // rbx
  signed int LastError; // eax
  int wDay; // [rsp+20h] [rbp-B8h]
  int wHour; // [rsp+28h] [rbp-B0h]
  int wMinute; // [rsp+30h] [rbp-A8h]
  int wSecond; // [rsp+38h] [rbp-A0h]
  __int64 v23; // [rsp+40h] [rbp-98h] BYREF
  int v24; // [rsp+48h] [rbp-90h]
  _QWORD **v25; // [rsp+50h] [rbp-88h]
  __int64 v26; // [rsp+58h] [rbp-80h] BYREF
  FILETIME FileTime; // [rsp+60h] [rbp-78h] BYREF
  int v28; // [rsp+68h] [rbp-70h] BYREF
  __int64 v29; // [rsp+70h] [rbp-68h]
  __int64 v30; // [rsp+78h] [rbp-60h]
  _SYSTEMTIME SystemTime; // [rsp+80h] [rbp-58h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = a1;
  v29 = a1;
  v25 = a2;
  v30 = a4;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v23);
  SystemTime = 0;
  FileTime = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v26);
  Name = CFileRecord::GetName(**v7, &v23);
  if ( Name >= 0 )
  {
    if ( a5 )
    {
      v13 = *(char **)(v8 + 56);
      v14 = (volatile signed __int32 *)(v13 - 24);
      v15 = (int *)(*a5 - 24);
      if ( v13 - 24 != (char *)v15 )
      {
        if ( v15[4] >= 0 && *(_QWORD *)v14 == *(_QWORD *)v15 )
        {
          v16 = (__int64)ATL::CSimpleStringT<unsigned short,0>::CloneData(v14);
          ATL::CStringData::Release((ATL::CStringData *)v15);
          *a5 = v16 + 24;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(a5, v13, *((_DWORD *)v13 - 4));
        }
      }
    }
    Name = (*(__int64 (__fastcall **)(_QWORD, _QWORD, FILETIME *))(**(_QWORD **)(v8 + 8) + 88LL))(
             *(_QWORD *)(v8 + 8),
             a3,
             &FileTime);
    if ( Name >= 0 )
    {
      if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
      {
        LastError = GetLastError();
        Name = LastError;
        if ( LastError > 0 )
          Name = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            43,
            WPP_f93405c69d16307d22252aee29235708_Traceguids,
            (unsigned int)Name);
        goto LABEL_32;
      }
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        wSecond = SystemTime.wSecond;
        wMinute = SystemTime.wMinute;
        wHour = SystemTime.wHour;
        wDay = SystemTime.wDay;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          (__int64)&v26,
          (__int64)L" (%04d_%02d_%02d %02d_%02d_%02d UTC)",
          SystemTime.wYear,
          SystemTime.wMonth,
          wDay,
          wHour,
          wMinute,
          wSecond);
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v28) )
        {
          v24 = v28;
          __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_180009F9B);
          Name = v24;
          if ( v24 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                44,
                (int)WPP_f93405c69d16307d22252aee29235708_Traceguids,
                v23,
                v24);
            v7 = v25;
            goto LABEL_32;
          }
          LODWORD(v8) = v29;
          v7 = v25;
          v5 = v30;
        }
      }
      Name = FhePathOperations::ConstructTargetPath(
               (__int64 *)((int)v8 + 56),
               (_QWORD *)(unsigned int)&v23,
               *(_DWORD *)(**v7 + 32LL),
               *(_DWORD *)(**v7 + 36LL),
               &v26,
               (_QWORD *)v5);
      if ( Name < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          (int)WPP_f93405c69d16307d22252aee29235708_Traceguids,
          v23,
          Name);
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 42;
        v12 = a3;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 41;
      v12 = *(unsigned int *)(**v7 + 16LL);
LABEL_5:
      WPP_SF_dd(v10[2], v11, WPP_f93405c69d16307d22252aee29235708_Traceguids, v12, Name);
    }
  }
LABEL_32:
  ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v23 - 24));
  SmartPtr<CFileRecord>::~SmartPtr<CFileRecord>(v7);
  return (unsigned int)Name;
}

```

## disassembly

```asm
0x180009d70  push    rbx
0x180009d72  push    rsi
0x180009d73  push    rdi
0x180009d74  push    r12
0x180009d76  push    r13
0x180009d78  push    r14
0x180009d7a  push    r15
0x180009d7c  sub     rsp, 0A0h
0x180009d83  mov     rax, cs:__security_cookie
0x180009d8a  xor     rax, rsp
0x180009d8d  mov     [rsp+0D8h+var_48], rax
0x180009d95  mov     r12, r9
0x180009d98  mov     r13d, r8d
0x180009d9b  mov     rdi, rdx
0x180009d9e  mov     r15, rcx
0x180009da1  mov     r14, [rsp+0D8h+arg_20]
0x180009da9  mov     [rsp+0D8h+var_68], rcx
0x180009dae  mov     [rsp+0D8h+var_88], rdx
0x180009db3  mov     [rsp+0D8h+var_60], r9
0x180009db8  lea     rcx, [rsp+0D8h+var_98]
0x180009dbd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180009dc2  nop
0x180009dc3  xorps   xmm0, xmm0
0x180009dc6  movups  xmmword ptr [rsp+0D8h+SystemTime.wYear], xmm0
0x180009dce  mov     qword ptr [rsp+0D8h+FileTime.dwLowDateTime], 0
0x180009dd7  lea     rcx, [rsp+0D8h+var_80]
0x180009ddc  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180009de1  nop
0x180009de2  mov     rcx, [rdi]
0x180009de5  lea     rdx, [rsp+0D8h+var_98]
0x180009dea  mov     rcx, [rcx]
0x180009ded  call    ?GetName@CFileRecord@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CFileRecord::GetName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180009df2  mov     ebx, eax
0x180009df4  test    eax, eax
0x180009df6  jns     short loc_180009E41
0x180009df8  lea     rax, WPP_GLOBAL_Control
0x180009dff  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e06  cmp     rcx, rax
0x180009e09  jz      loc_18000A059
0x180009e0f  test    byte ptr [rcx+1Ch], 1
0x180009e13  jz      loc_18000A059
0x180009e19  mov     rax, [rdi]
0x180009e1c  mov     r9, [rax]
0x180009e1f  mov     edx, 29h ; ')'
0x180009e24  mov     r9d, [r9+10h]
0x180009e28  mov     dword ptr [rsp+0D8h+var_B8], ebx
0x180009e2c  lea     r8, WPP_f93405c69d16307d22252aee29235708_Traceguids
0x180009e33  mov     rcx, [rcx+10h]
0x180009e37  call    WPP_SF_dd
0x180009e3c  jmp     loc_18000A059
0x180009e41  test    r14, r14
0x180009e44  jz      short loc_180009E8D
0x180009e46  mov     rdx, [r15+38h]
0x180009e4a  lea     rcx, [rdx-18h]
0x180009e4e  mov     rsi, [r14]
0x180009e51  add     rsi, 0FFFFFFFFFFFFFFE8h
0x180009e55  cmp     rcx, rsi
0x180009e58  jz      short loc_180009E8D
0x180009e5a  cmp     dword ptr [rsi+10h], 0
0x180009e5e  jl      short loc_180009E81
0x180009e60  mov     rax, [rsi]
0x180009e63  cmp     [rcx], rax
0x180009e66  jnz     short loc_180009E81
0x180009e68  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180009e6d  mov     rbx, rax
0x180009e70  mov     rcx, rsi; this
0x180009e73  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180009e78  lea     rax, [rbx+18h]
0x180009e7c  mov     [r14], rax
0x180009e7f  jmp     short loc_180009E8D
0x180009e81  mov     r8d, [rdx-10h]
0x180009e85  mov     rcx, r14
0x180009e88  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180009e8d  mov     rcx, [r15+8]
0x180009e91  mov     rax, [rcx]
0x180009e94  lea     r8, [rsp+0D8h+FileTime]
0x180009e99  mov     edx, r13d
0x180009e9c  mov     rax, [rax+58h]
0x180009ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ea5  mov     ebx, eax
0x180009ea7  test    eax, eax
0x180009ea9  jns     short loc_180009ED9
0x180009eab  lea     rax, WPP_GLOBAL_Control
0x180009eb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180009eb9  cmp     rcx, rax
0x180009ebc  jz      loc_18000A059
0x180009ec2  test    byte ptr [rcx+1Ch], 1
0x180009ec6  jz      loc_18000A059
0x180009ecc  mov     edx, 2Ah ; '*'
0x180009ed1  mov     r9d, r13d
0x180009ed4  jmp     loc_180009E28
0x180009ed9  lea     rdx, [rsp+0D8h+SystemTime]; lpSystemTime
0x180009ee1  lea     rcx, [rsp+0D8h+FileTime]; lpFileTime
0x180009ee6  call    cs:__imp_FileTimeToSystemTime
0x180009eec  test    eax, eax
0x180009eee  jnz     short loc_180009F43
0x180009ef0  call    cs:__imp_GetLastError
0x180009ef6  mov     ebx, eax
0x180009ef8  test    eax, eax
0x180009efa  jle     short loc_180009F05
0x180009efc  movzx   ebx, ax
0x180009eff  or      ebx, 80070000h
0x180009f05  lea     rax, WPP_GLOBAL_Control
0x180009f0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f13  cmp     rcx, rax
0x180009f16  jz      loc_18000A059
0x180009f1c  test    byte ptr [rcx+1Ch], 1
0x180009f20  jz      loc_18000A059
0x180009f26  mov     edx, 2Bh ; '+'
0x180009f2b  mov     r9d, ebx
0x180009f2e  lea     r8, WPP_f93405c69d16307d22252aee29235708_Traceguids
0x180009f35  mov     rcx, [rcx+10h]
0x180009f39  call    WPP_SF_d
0x180009f3e  jmp     loc_18000A059
0x180009f43  movzx   eax, [rsp+0D8h+SystemTime.wSecond]
0x180009f4b  movzx   ecx, [rsp+0D8h+SystemTime.wMinute]
0x180009f53  movzx   edx, [rsp+0D8h+SystemTime.wHour]
0x180009f5b  movzx   r10d, [rsp+0D8h+SystemTime.wDay]
0x180009f64  movzx   r9d, [rsp+0D8h+SystemTime.wMonth]
0x180009f6d  movzx   r8d, [rsp+0D8h+SystemTime.wYear]
0x180009f76  mov     [rsp+0D8h+var_A0], eax
0x180009f7a  mov     [rsp+0D8h+var_A8], ecx
0x180009f7e  mov     dword ptr [rsp+0D8h+var_B0], edx
0x180009f82  mov     dword ptr [rsp+0D8h+var_B8], r10d
0x180009f87  lea     rdx, a04d02d02d02d02; " (%04d_%02d_%02d %02d_%02d_%02d UTC)"
0x180009f8e  lea     rcx, [rsp+0D8h+var_80]
0x180009f93  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180009f98  nop
0x180009f99  jmp     short loc_180009FF0
0x180009f9b  mov     ebx, [rsp+0D8h+var_90]
0x180009f9f  test    ebx, ebx
0x180009fa1  jns     short loc_180009FE1
0x180009fa3  lea     rax, WPP_GLOBAL_Control
0x180009faa  mov     rcx, cs:WPP_GLOBAL_Control
0x180009fb1  cmp     rcx, rax
0x180009fb4  jz      short loc_180009FDA
0x180009fb6  test    byte ptr [rcx+1Ch], 1
0x180009fba  jz      short loc_180009FDA
0x180009fbc  mov     edx, 2Ch ; ','
0x180009fc1  mov     dword ptr [rsp+0D8h+var_B8], ebx
0x180009fc5  mov     r9, [rsp+0D8h+var_98]
0x180009fca  lea     r8, WPP_f93405c69d16307d22252aee29235708_Traceguids
0x180009fd1  mov     rcx, [rcx+10h]
0x180009fd5  call    WPP_SF_Sd
0x180009fda  mov     rdi, [rsp+0D8h+var_88]
0x180009fdf  jmp     short loc_18000A059
0x180009fe1  mov     r15, [rsp+0D8h+var_68]
0x180009fe6  mov     rdi, [rsp+0D8h+var_88]
0x180009feb  mov     r12, [rsp+0D8h+var_60]
0x180009ff0  mov     rax, [rdi]
0x180009ff3  mov     r8, [rax]
0x180009ff6  lea     rcx, [r15+38h]
0x180009ffa  mov     [rsp+0D8h+var_B0], r12
0x180009fff  lea     rax, [rsp+0D8h+var_80]
0x18000a004  mov     [rsp+0D8h+var_B8], rax
0x18000a009  mov     r9d, [r8+24h]
0x18000a00d  mov     r8d, [r8+20h]
0x18000a011  lea     rdx, [rsp+0D8h+var_98]
0x18000a016  call    ?ConstructTargetPath@FhePathOperations@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0JJ0AEAV23@@Z; FhePathOperations::ConstructTargetPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long,long,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18000a01b  mov     ebx, eax
0x18000a01d  test    eax, eax
0x18000a01f  jns     short loc_18000A059
0x18000a021  lea     rax, WPP_GLOBAL_Control
0x18000a028  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a02f  cmp     rcx, rax
0x18000a032  jz      short loc_18000A059
0x18000a034  test    byte ptr [rcx+1Ch], 1
0x18000a038  jz      short loc_18000A059
0x18000a03a  mov     edx, 2Dh ; '-'
0x18000a03f  mov     dword ptr [rsp+0D8h+var_B8], ebx
0x18000a043  mov     r9, [rsp+0D8h+var_98]
0x18000a048  lea     r8, WPP_f93405c69d16307d22252aee29235708_Traceguids
0x18000a04f  mov     rcx, [rcx+10h]
0x18000a053  call    WPP_SF_Sd
0x18000a058  nop
0x18000a059  mov     rcx, [rsp+0D8h+var_80]
0x18000a05e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000a062  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000a067  nop
0x18000a068  mov     rcx, [rsp+0D8h+var_98]
0x18000a06d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000a071  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000a076  nop
0x18000a077  mov     rcx, rdi
0x18000a07a  call    ??1?$SmartPtr@VCFileRecord@@@@QEAA@XZ; SmartPtr<CFileRecord>::~SmartPtr<CFileRecord>(void)
0x18000a07f  mov     eax, ebx
0x18000a081  mov     rcx, [rsp+0D8h+var_48]
0x18000a089  xor     rcx, rsp; StackCookie
0x18000a08c  call    __security_check_cookie
0x18000a091  add     rsp, 0A0h
0x18000a098  pop     r15
0x18000a09a  pop     r14
0x18000a09c  pop     r13
0x18000a09e  pop     r12
0x18000a0a0  pop     rdi
0x18000a0a1  pop     rsi
0x18000a0a2  pop     rbx
0x18000a0a3  retn
```
