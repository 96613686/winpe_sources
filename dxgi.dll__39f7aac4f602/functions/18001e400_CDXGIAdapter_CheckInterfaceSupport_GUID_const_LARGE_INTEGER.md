# CDXGIAdapter::CheckInterfaceSupport(_GUID const &,_LARGE_INTEGER *)

- ea: `0x18001e400`
- end: `0x18001e784`
- name: `?CheckInterfaceSupport@CDXGIAdapter@@UEAAJAEBU_GUID@@PEAT_LARGE_INTEGER@@@Z`
- size: `900`
- prototype: `int(CDXGIAdapter *__hidden this, const struct _GUID *, union _LARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180010d40`
- `0x18001d5fc`
- `0x18001e400`
- `0x18001e78c`
- `0x18001e7f0`
- `0x180037380`
- `0x180075fa0`
- `0x180076f20`
- `0x1800cb010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18001e645`
- `ntdll!EtwEventWrite` at `0x18001e645`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e67a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e67a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001e6d0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001e6d0`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001e65f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001e65f`

## string_xrefs

- `0x18001e670`: `D3D11CreateDevice`
- `0x18001e658`: `d3d11.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDXGIAdapter::CheckInterfaceSupport(
        CDXGIAdapter *this,
        const struct _GUID *a2,
        union _LARGE_INTEGER *a3)
{
  unsigned int v6; // edi
  unsigned __int16 *p_Data2; // rcx
  unsigned __int8 *Data4; // rdx
  unsigned __int8 *v9; // r8
  char v10; // r14
  unsigned int v11; // esi
  char v12; // bl
  __int64 v13; // r8
  int UMDFileNameInfo; // esi
  HMODULE LibraryW; // rbx
  FARPROC ProcAddress; // rax
  int IsEqualGUID; // eax
  CDXGIAdapter *v19; // [rsp+60h] [rbp-298h] BYREF
  char v20[4]; // [rsp+68h] [rbp-290h] BYREF
  int v21; // [rsp+6Ch] [rbp-28Ch]
  _com_error *v22; // [rsp+70h] [rbp-288h] BYREF
  _BYTE v23[4]; // [rsp+80h] [rbp-278h] BYREF
  WCHAR wstrFilename[262]; // [rsp+84h] [rbp-274h] BYREF
  _QWORD v25[4]; // [rsp+290h] [rbp-68h] BYREF
  union _LARGE_INTEGER *v26; // [rsp+2B0h] [rbp-48h]
  __int64 v27; // [rsp+2B8h] [rbp-40h]
  HMODULE v28; // [rsp+2C0h] [rbp-38h] BYREF

  try
  {
    v19 = this;
    v6 = 0;
    v20[0] = 0;
    if ( dword_180108134
      && (qword_180108120 & 0x4000000000000000LL) != 0
      && (qword_180108128 & 0x4000000000000000LL) == qword_180108128 )
    {
      v20[0] = 1;
      v25[0] = &v19;
      v25[1] = 8;
      v25[2] = a2;
      v25[3] = 16;
      v27 = 8;
      if ( a3 )
        v26 = a3;
      else
        v26 = (union _LARGE_INTEGER *)&v28;
      EtwEventWrite(DXGIEtwProviderGuid_Context, "z", 3, v25);
    }
    if ( a2->Data1 == -1686221681
      && (p_Data2 = &a2->Data2, *(_DWORD *)&a2->Data2 == *(_DWORD *)&GUID_9b7e4c8f_342c_4106_a19f_4f2704f689f0.Data2)
      && (Data4 = a2->Data4, *(_DWORD *)a2->Data4 == *(_DWORD *)GUID_9b7e4c8f_342c_4106_a19f_4f2704f689f0.Data4)
      && (v9 = &a2->Data4[4], *(_DWORD *)&a2->Data4[4] == *(_DWORD *)&GUID_9b7e4c8f_342c_4106_a19f_4f2704f689f0.Data4[4]) )
    {
      v10 = 1;
    }
    else
    {
      p_Data2 = &a2->Data2;
      Data4 = a2->Data4;
      v9 = &a2->Data4[4];
      if ( a2->Data1 == -1686221809
        && *(_DWORD *)p_Data2 == *(_DWORD *)&GUID_9b7e4c0f_342c_4106_a19f_4f2704f689f0.Data2
        && *(_DWORD *)Data4 == *(_DWORD *)GUID_9b7e4c0f_342c_4106_a19f_4f2704f689f0.Data4 )
      {
        v10 = 0;
        if ( *(_DWORD *)v9 == *(_DWORD *)&GUID_9b7e4c0f_342c_4106_a19f_4f2704f689f0.Data4[4] )
          goto LABEL_27;
      }
      else
      {
        v10 = 0;
      }
    }
    if ( !v10 )
    {
      if ( a2->Data1 == 1424783354
        && *(_DWORD *)p_Data2 == *(_DWORD *)&GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c.Data2
        && *(_DWORD *)Data4 == *(_DWORD *)GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c.Data4
        && *(_DWORD *)v9 == *(_DWORD *)&GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c.Data4[4] )
      {
        v11 = 0;
      }
      else
      {
        v11 = 0;
        DXGIThrowFailure(-2005270524);
      }
LABEL_9:
      if ( *((_DWORD *)this + 187) != -1
        || (IsEqualGUID = InlineIsEqualGUID(a2, &GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c), v12 = 1, !IsEqualGUID) )
      {
        v12 = 0;
      }
      memset_0(v23, 0, 0x20Cu);
      LOBYTE(v13) = v12;
      UMDFileNameInfo = CDXGIBaseAdapter::GetUMDFileNameInfo(this, v11, v13, v23);
      if ( UMDFileNameInfo >= 0 )
      {
        if ( !v10 )
        {
LABEL_18:
          if ( a3 )
            *a3 = CDXGIBaseAdapter::GetUMDVersion(wstrFilename);
          goto LABEL_51;
        }
        LODWORD(v19) = 41216;
        LibraryW = LoadLibraryW(L"d3d11.dll");
        v28 = LibraryW;
        ProcAddress = GetProcAddress(LibraryW, "D3D11CreateDevice");
        if ( ProcAddress )
          UMDFileNameInfo = ((__int64 (__fastcall *)(CDXGIAdapter *, _QWORD, _QWORD, _QWORD, CDXGIAdapter **, int, int, _QWORD, _QWORD, _QWORD))ProcAddress)(
                              this,
                              0,
                              0,
                              0,
                              &v19,
                              1,
                              7,
                              0,
                              0,
                              0);
        else
          UMDFileNameInfo = -2147024882;
        if ( LibraryW )
          FreeLibrary(LibraryW);
      }
      if ( UMDFileNameInfo < 0 )
        goto LABEL_51;
      goto LABEL_18;
    }
LABEL_27:
    v11 = 1;
    goto LABEL_9;
  }
  catch ( _com_error *v22 )
  {
    LODWORD(v19) = *((_DWORD *)v22 + 2);
    v6 = 0;
    UMDFileNameInfo = (int)v19;
  }
  catch ( std::bad_alloc )
  {
    LODWORD(v19) = -2147024882;
    UMDFileNameInfo = -2147024882;
    goto LABEL_48;
  }
LABEL_51:
  if ( UMDFileNameInfo < 0 )
  {
    if ( UMDFileNameInfo == -2147024882 || UMDFileNameInfo == -2005270523 )
    {
LABEL_48:
      v21 = UMDFileNameInfo;
      v6 = UMDFileNameInfo;
    }
    else
    {
      v21 = -2005270524;
      v6 = -2005270524;
    }
  }
  else
  {
    v21 = 0;
  }
  CETWEvent_IDXGIAdapter_CheckInterfaceSupport::~CETWEvent_IDXGIAdapter_CheckInterfaceSupport((CETWEvent_IDXGIAdapter_CheckInterfaceSupport *)v20);
  return v6;
}

```

## disassembly

```asm
0x18001e400  mov     [rsp+arg_8], rbx
0x18001e405  push    rsi
0x18001e406  push    rdi
0x18001e407  push    r12
0x18001e409  push    r14
0x18001e40b  push    r15
0x18001e40d  sub     rsp, 2D0h
0x18001e414  mov     rax, cs:__security_cookie
0x18001e41b  xor     rax, rsp
0x18001e41e  mov     [rsp+2F8h+var_30], rax
0x18001e426  mov     r15, r8
0x18001e429  mov     rbx, rdx
0x18001e42c  mov     r12, rcx
0x18001e42f  mov     [rsp+2F8h+var_298], rcx
0x18001e434  xor     edi, edi
0x18001e436  mov     [rsp+2F8h+var_290], dil
0x18001e43b  cmp     cs:dword_180108134, edi
0x18001e441  jnz     loc_18001E5AC
0x18001e447  cmp     dword ptr [rbx], 9B7E4C8Fh
0x18001e44d  jz      loc_18001E535
0x18001e453  lea     rcx, [rbx+4]
0x18001e457  lea     rdx, [rbx+8]
0x18001e45b  lea     r8, [rbx+0Ch]
0x18001e45f  cmp     dword ptr [rbx], 9B7E4C0Fh
0x18001e465  jz      loc_18001E574
0x18001e46b  mov     r14b, dil
0x18001e46e  test    r14b, r14b
0x18001e471  jnz     loc_18001E5A2
0x18001e477  cmp     dword ptr [rbx], 54EC77FAh
0x18001e47d  jz      loc_18001E6DB
0x18001e483  mov     esi, edi
0x18001e485  mov     ecx, 887A0004h; int
0x18001e48a  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x18001e48f  cmp     dword ptr [r12+2ECh], 0FFFFFFFFh
0x18001e498  jz      loc_18001E729
0x18001e49e  mov     bl, dil
0x18001e4a1  xor     edx, edx; Val
0x18001e4a3  mov     r8d, 20Ch; Size
0x18001e4a9  lea     rcx, [rsp+2F8h+var_278]; void *
0x18001e4b1  call    memset_0
0x18001e4b6  lea     r9, [rsp+2F8h+var_278]
0x18001e4be  mov     r8b, bl
0x18001e4c1  mov     edx, esi
0x18001e4c3  mov     rcx, r12
0x18001e4c6  call    ?GetUMDFileNameInfo@CDXGIBaseAdapter@@QEAAJW4_KMTUMDVERSION@@_NPEAU_D3DKMT_UMDFILENAMEINFO@@@Z; CDXGIBaseAdapter::GetUMDFileNameInfo(_KMTUMDVERSION,bool,_D3DKMT_UMDFILENAMEINFO *)
0x18001e4cb  mov     esi, eax
0x18001e4cd  test    eax, eax
0x18001e4cf  jns     short loc_18001E515
0x18001e4d1  test    esi, esi
0x18001e4d3  jns     short loc_18001E51E
0x18001e4d5  test    esi, esi
0x18001e4d7  js      loc_18001E752
0x18001e4dd  mov     [rsp+2F8h+var_28C], edi
0x18001e4e1  lea     rcx, [rsp+2F8h+var_290]; this
0x18001e4e6  call    ??1CETWEvent_IDXGIAdapter_CheckInterfaceSupport@@QEAA@XZ; CETWEvent_IDXGIAdapter_CheckInterfaceSupport::~CETWEvent_IDXGIAdapter_CheckInterfaceSupport(void)
0x18001e4eb  mov     eax, edi
0x18001e4ed  mov     rcx, [rsp+2F8h+var_30]
0x18001e4f5  xor     rcx, rsp; StackCookie
0x18001e4f8  call    __security_check_cookie
0x18001e4fd  mov     rbx, [rsp+2F8h+arg_8]
0x18001e505  add     rsp, 2D0h
0x18001e50c  pop     r15
0x18001e50e  pop     r14
0x18001e510  pop     r12
0x18001e512  pop     rdi
0x18001e513  pop     rsi
0x18001e514  retn
0x18001e515  test    r14b, r14b
0x18001e518  jnz     loc_18001E650
0x18001e51e  test    r15, r15
0x18001e521  jz      short loc_18001E4D5
0x18001e523  lea     rcx, [rsp+2F8h+wstrFilename]; lpwstrFilename
0x18001e52b  call    ?GetUMDVersion@CDXGIBaseAdapter@@SA?AT_LARGE_INTEGER@@QEAG@Z; CDXGIBaseAdapter::GetUMDVersion(ushort * const)
0x18001e530  mov     [r15], rax
0x18001e533  jmp     short loc_18001E4D5
0x18001e535  lea     rcx, [rbx+4]
0x18001e539  mov     eax, dword ptr cs:_GUID_9b7e4c8f_342c_4106_a19f_4f2704f689f0.Data2
0x18001e53f  cmp     [rcx], eax
0x18001e541  jnz     loc_18001E453
0x18001e547  lea     rdx, [rbx+8]
0x18001e54b  mov     eax, dword ptr cs:_GUID_9b7e4c8f_342c_4106_a19f_4f2704f689f0.Data4
0x18001e551  cmp     [rdx], eax
0x18001e553  jnz     loc_18001E453
0x18001e559  lea     r8, [rbx+0Ch]
0x18001e55d  mov     eax, dword ptr cs:_GUID_9b7e4c8f_342c_4106_a19f_4f2704f689f0.Data4+4
0x18001e563  cmp     [r8], eax
0x18001e566  jnz     loc_18001E453
0x18001e56c  mov     r14b, 1
0x18001e56f  jmp     loc_18001E46E
0x18001e574  mov     eax, dword ptr cs:_GUID_9b7e4c0f_342c_4106_a19f_4f2704f689f0.Data2
0x18001e57a  cmp     [rcx], eax
0x18001e57c  jnz     loc_18001E46B
0x18001e582  mov     eax, dword ptr cs:_GUID_9b7e4c0f_342c_4106_a19f_4f2704f689f0.Data4
0x18001e588  cmp     [rdx], eax
0x18001e58a  jnz     loc_18001E46B
0x18001e590  mov     eax, dword ptr cs:_GUID_9b7e4c0f_342c_4106_a19f_4f2704f689f0.Data4+4
0x18001e596  mov     r14b, dil
0x18001e599  cmp     [r8], eax
0x18001e59c  jnz     loc_18001E46E
0x18001e5a2  mov     esi, 1
0x18001e5a7  jmp     loc_18001E48F
0x18001e5ac  mov     rdx, 4000000000000000h
0x18001e5b6  test    cs:qword_180108120, rdx
0x18001e5bd  jz      loc_18001E447
0x18001e5c3  mov     rax, cs:qword_180108128
0x18001e5ca  and     rax, rdx
0x18001e5cd  cmp     rax, cs:qword_180108128
0x18001e5d4  jnz     loc_18001E447
0x18001e5da  mov     [rsp+2F8h+var_290], 1
0x18001e5df  lea     rax, [rsp+2F8h+var_298]
0x18001e5e4  mov     [rsp+2F8h+var_68], rax
0x18001e5ec  mov     [rsp+2F8h+var_60], 8
0x18001e5f8  mov     [rsp+2F8h+var_58], rbx
0x18001e600  mov     [rsp+2F8h+var_50], 10h
0x18001e60c  mov     [rsp+2F8h+var_40], 8
0x18001e618  test    r15, r15
0x18001e61b  jz      loc_18001E714
0x18001e621  mov     [rsp+2F8h+var_48], r15
0x18001e629  lea     r9, [rsp+2F8h+var_68]
0x18001e631  mov     r8d, 3
0x18001e637  lea     rdx, IDXGIAdapter_CheckInterfaceSupport_Start; "z"
0x18001e63e  mov     rcx, cs:DXGIEtwProviderGuid_Context
0x18001e645  call    cs:__imp_EtwEventWrite
0x18001e64b  jmp     loc_18001E447
0x18001e650  mov     dword ptr [rsp+2F8h+var_298], 0A100h
0x18001e658  lea     rcx, aD3d11Dll; "d3d11.dll"
0x18001e65f  call    cs:__imp_LoadLibraryW
0x18001e665  mov     rbx, rax
0x18001e668  mov     [rsp+2F8h+var_38], rax
0x18001e670  lea     rdx, aD3d11createdev_0; "D3D11CreateDevice"
0x18001e677  mov     rcx, rax; hModule
0x18001e67a  call    cs:__imp_GetProcAddress
0x18001e680  test    rax, rax
0x18001e683  jz      loc_18001E70D
0x18001e689  mov     [rsp+2F8h+var_2B0], rdi
0x18001e68e  mov     [rsp+2F8h+var_2B8], rdi
0x18001e693  mov     [rsp+2F8h+var_2C0], rdi
0x18001e698  mov     [rsp+2F8h+var_2C8], 7
0x18001e6a0  mov     [rsp+2F8h+var_2D0], 1
0x18001e6a8  lea     rcx, [rsp+2F8h+var_298]
0x18001e6ad  mov     [rsp+2F8h+var_2D8], rcx
0x18001e6b2  xor     r9d, r9d
0x18001e6b5  xor     r8d, r8d
0x18001e6b8  xor     edx, edx
0x18001e6ba  mov     rcx, r12
0x18001e6bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6c2  mov     esi, eax
0x18001e6c4  test    rbx, rbx
0x18001e6c7  jz      loc_18001E4D1
0x18001e6cd  mov     rcx, rbx; hLibModule
0x18001e6d0  call    cs:__imp_FreeLibrary
0x18001e6d6  jmp     loc_18001E4D1
0x18001e6db  mov     eax, dword ptr cs:_GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c.Data2
0x18001e6e1  cmp     [rcx], eax
0x18001e6e3  jnz     loc_18001E483
0x18001e6e9  mov     eax, dword ptr cs:_GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c.Data4
0x18001e6ef  cmp     [rdx], eax
0x18001e6f1  jnz     loc_18001E483
0x18001e6f7  mov     eax, dword ptr cs:_GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c.Data4+4
0x18001e6fd  cmp     [r8], eax
0x18001e700  jnz     loc_18001E483
0x18001e706  mov     esi, edi
0x18001e708  jmp     loc_18001E48F
0x18001e70d  mov     esi, 8007000Eh
0x18001e712  jmp     short loc_18001E6C4
0x18001e714  lea     rax, [rsp+2F8h+var_38]
0x18001e71c  mov     [rsp+2F8h+var_48], rax
0x18001e724  jmp     loc_18001E629
0x18001e729  lea     rdx, _GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c; struct _GUID *
0x18001e730  mov     rcx, rbx; struct _GUID *
0x18001e733  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18001e738  test    eax, eax
0x18001e73a  mov     bl, 1
0x18001e73c  jnz     loc_18001E4A1
0x18001e742  jmp     loc_18001E49E
0x18001e747  xor     edi, edi
0x18001e749  mov     esi, dword ptr [rsp+2F8h+var_298]
0x18001e74d  jmp     loc_18001E4D5
0x18001e752  cmp     esi, 8007000Eh
0x18001e758  jz      short loc_18001E778
0x18001e75a  cmp     esi, 887A0005h
0x18001e760  jz      short loc_18001E778
0x18001e762  mov     [rsp+2F8h+var_28C], 887A0004h
0x18001e76a  mov     edi, 887A0004h
0x18001e76f  jmp     loc_18001E4E1
0x18001e774  mov     esi, dword ptr [rsp+2F8h+var_298]
0x18001e778  mov     [rsp+2F8h+var_28C], esi
0x18001e77c  mov     edi, esi
0x18001e77e  jmp     loc_18001E4E1
```
