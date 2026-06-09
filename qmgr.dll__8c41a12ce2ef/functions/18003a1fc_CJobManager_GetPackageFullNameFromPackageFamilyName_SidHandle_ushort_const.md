# CJobManager::GetPackageFullNameFromPackageFamilyName(SidHandle,ushort const *)

- ea: `0x18003a1fc`
- end: `0x18003a852`
- name: `?GetPackageFullNameFromPackageFamilyName@CJobManager@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VSidHandle@@PEBG@Z`
- size: `1622`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001a6fc`
- `0x18003bf78`

## callees

- `0x180016d60`
- `0x18001d7f0`
- `0x18003a1fc`
- `0x18003abe4`
- `0x18003ca78`
- `0x18009d024`
- `0x18009d100`
- `0x1800b1160`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a6e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a6e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a32d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a3ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a32d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a3ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003a314`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003a3d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003a314`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003a3d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CJobManager::GetPackageFullNameFromPackageFamilyName(
        __int64 a1,
        __int64 a2,
        SidHandle *a3,
        const WCHAR *a4)
{
  HSTRING v4; // rdi
  HSTRING v5; // rbx
  const WCHAR *v6; // rcx
  unsigned __int64 v7; // r12
  unsigned __int64 v8; // rdx
  HRESULT v9; // r15d
  HRESULT v10; // r14d
  PCNZWCH v11; // r15
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  PCWSTR StringRawBuffer; // rax
  __int64 v19; // rbx
  _QWORD **v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 result; // rax
  _BYTE v25[8]; // [rsp+30h] [rbp-458h] BYREF
  HSTRING string; // [rsp+38h] [rbp-450h] BYREF
  __int64 v27; // [rsp+40h] [rbp-448h] BYREF
  __int64 v28; // [rsp+48h] [rbp-440h] BYREF
  __int64 v29; // [rsp+50h] [rbp-438h] BYREF
  __int64 v30; // [rsp+58h] [rbp-430h] BYREF
  HSTRING v31; // [rsp+60h] [rbp-428h] BYREF
  volatile signed __int32 *v32; // [rsp+68h] [rbp-420h]
  HSTRING v33[2]; // [rsp+70h] [rbp-418h] BYREF
  const ComError *v34; // [rsp+80h] [rbp-408h] BYREF
  void **pExceptionObject; // [rsp+90h] [rbp-3F8h] BYREF
  __int128 v36; // [rsp+98h] [rbp-3F0h]
  int v37; // [rsp+A8h] [rbp-3E0h]
  int v38; // [rsp+ACh] [rbp-3DCh]
  int v39; // [rsp+B0h] [rbp-3D8h]
  void **v40; // [rsp+F0h] [rbp-398h] BYREF
  __int128 v41; // [rsp+F8h] [rbp-390h]
  HRESULT v42; // [rsp+108h] [rbp-380h]
  int v43; // [rsp+10Ch] [rbp-37Ch]
  int v44; // [rsp+110h] [rbp-378h]
  void **v45; // [rsp+150h] [rbp-338h] BYREF
  __int128 v46; // [rsp+158h] [rbp-330h]
  HRESULT v47; // [rsp+168h] [rbp-320h]
  int v48; // [rsp+16Ch] [rbp-31Ch]
  int v49; // [rsp+170h] [rbp-318h]
  void **v50; // [rsp+1B0h] [rbp-2D8h] BYREF
  __int128 v51; // [rsp+1B8h] [rbp-2D0h]
  int v52; // [rsp+1C8h] [rbp-2C0h]
  int v53; // [rsp+1CCh] [rbp-2BCh]
  int v54; // [rsp+1D0h] [rbp-2B8h]
  void **v55; // [rsp+210h] [rbp-278h] BYREF
  __int128 v56; // [rsp+218h] [rbp-270h]
  int v57; // [rsp+228h] [rbp-260h]
  int v58; // [rsp+22Ch] [rbp-25Ch]
  int v59; // [rsp+230h] [rbp-258h]
  void **v60; // [rsp+270h] [rbp-218h] BYREF
  __int128 v61; // [rsp+278h] [rbp-210h]
  int v62; // [rsp+288h] [rbp-200h]
  int v63; // [rsp+28Ch] [rbp-1FCh]
  int v64; // [rsp+290h] [rbp-1F8h]
  void **v65; // [rsp+2D0h] [rbp-1B8h] BYREF
  __int128 v66; // [rsp+2D8h] [rbp-1B0h]
  int v67; // [rsp+2E8h] [rbp-1A0h]
  int v68; // [rsp+2ECh] [rbp-19Ch]
  int v69; // [rsp+2F0h] [rbp-198h]
  void **v70; // [rsp+330h] [rbp-158h] BYREF
  __int128 v71; // [rsp+338h] [rbp-150h]
  int v72; // [rsp+348h] [rbp-140h]
  int v73; // [rsp+34Ch] [rbp-13Ch]
  int v74; // [rsp+350h] [rbp-138h]
  void **v75; // [rsp+390h] [rbp-F8h] BYREF
  __int128 v76; // [rsp+398h] [rbp-F0h]
  int v77; // [rsp+3A8h] [rbp-E0h]
  int v78; // [rsp+3ACh] [rbp-DCh]
  int v79; // [rsp+3B0h] [rbp-D8h]
  void **v80; // [rsp+3F0h] [rbp-98h] BYREF
  __int128 v81; // [rsp+3F8h] [rbp-90h]
  int v82; // [rsp+408h] [rbp-80h]
  int v83; // [rsp+40Ch] [rbp-7Ch]
  int v84; // [rsp+410h] [rbp-78h]
  _QWORD **v85; // [rsp+490h] [rbp+8h] BYREF
  __int64 v86; // [rsp+498h] [rbp+10h]
  SidHandle *v87; // [rsp+4A0h] [rbp+18h]
  PCNZWCH sourceString; // [rsp+4A8h] [rbp+20h]

  sourceString = a4;
  v87 = a3;
  v86 = a2;
  v85 = (_QWORD **)a1;
  try
  {
    if ( !*(_QWORD *)(a1 + 1776) )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids);
      v36 = 0;
      pExceptionObject = &ComError::`vftable';
      v37 = -2145386389;
      v38 = 1499;
      v39 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v31 = *(HSTRING *)a3;
    v32 = (volatile signed __int32 *)*((_QWORD *)a3 + 1);
    _InterlockedAdd(v32, 1u);
    SidToSidString(&v30, &v31);
    v4 = 0;
    v31 = 0;
    v5 = 0;
    v33[0] = 0;
    v6 = (const WCHAR *)(v30 + 12);
    if ( v30 == -12 )
    {
      v9 = -2147467261;
      v7 = -1;
    }
    else
    {
      string = 0;
      v7 = -1;
      v8 = -1;
      do
        ++v8;
      while ( v6[v8] );
      if ( v8 > 0xFFFFFFFF )
      {
        v10 = -2147024362;
        v9 = -2147024362;
LABEL_16:
        if ( v9 < 0 )
        {
          v41 = 0;
          v40 = &ComError::`vftable';
          v42 = v9;
          v43 = 1506;
          v44 = 1;
          throw (ComError *)&v40;
        }
        v11 = sourceString;
        if ( sourceString )
        {
          string = 0;
          do
            ++v7;
          while ( sourceString[v7] );
          if ( v7 <= 0xFFFFFFFF )
          {
            v10 = WindowsCreateString(sourceString, v7, &string);
            if ( v10 >= 0 )
            {
              v5 = string;
              v33[0] = string;
              WindowsDeleteString(0);
            }
          }
        }
        else
        {
          v10 = -2147467261;
        }
        if ( v10 < 0 )
        {
          v46 = 0;
          v45 = &ComError::`vftable';
          v47 = v10;
          v48 = 1507;
          v49 = 1;
          throw (ComError *)&v45;
        }
        v29 = 0;
        v12 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, HSTRING, __int64 *))(*v85[222] + 160LL))(
                v85[222],
                v4,
                v5,
                &v29);
        if ( v12 < 0 )
        {
          v51 = 0;
          v50 = &ComError::`vftable';
          v52 = v12;
          v53 = 1513;
          v54 = 1;
          throw (ComError *)&v50;
        }
        v27 = 0;
        v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 48LL))(v29, &v27);
        if ( v13 < 0 )
        {
          v56 = 0;
          v55 = &ComError::`vftable';
          v57 = v13;
          v58 = 1516;
          v59 = 1;
          throw (ComError *)&v55;
        }
        v25[0] = 0;
        v14 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v27 + 56LL))(v27, v25);
        if ( v14 < 0 )
        {
          v61 = 0;
          v60 = &ComError::`vftable';
          v62 = v14;
          v63 = 1519;
          v64 = 1;
          throw (ComError *)&v60;
        }
        if ( !v25[0] )
        {
          if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              58,
              (unsigned int)&WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids,
              v30 + 12,
              (__int64)v11);
          v81 = 0;
          v80 = &ComError::`vftable';
          v82 = -2145386390;
          v83 = 1539;
          v84 = 1;
          throw (ComError *)&v80;
        }
        v28 = 0;
        v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 48LL))(v27, &v28);
        if ( v15 < 0 )
        {
          v66 = 0;
          v65 = &ComError::`vftable';
          v67 = v15;
          v68 = 1524;
          v69 = 1;
          throw (ComError *)&v65;
        }
        v85 = 0;
        v16 = (*(__int64 (__fastcall **)(__int64, _QWORD ***))(*(_QWORD *)v28 + 48LL))(v28, &v85);
        if ( v16 < 0 )
        {
          v71 = 0;
          v70 = &ComError::`vftable';
          v72 = v16;
          v73 = 1527;
          v74 = 1;
          throw (ComError *)&v70;
        }
        string = 0;
        v17 = ((__int64 (__fastcall *)(_QWORD **, HSTRING *))(*v85)[12])(v85, &string);
        if ( v17 < 0 )
        {
          v76 = 0;
          v75 = &ComError::`vftable';
          v77 = v17;
          v78 = 1530;
          v79 = 1;
          throw (ComError *)&v75;
        }
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v19 = v86;
        std::wstring::wstring(v86, StringRawBuffer);
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        v20 = v85;
        if ( v85 )
        {
          v85 = 0;
          ((void (__fastcall *)(_QWORD **))(*v20)[2])(v20);
        }
        v21 = v28;
        if ( v28 )
        {
          v28 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
        v22 = v27;
        if ( v27 )
        {
          v27 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        }
        v23 = v29;
        if ( v29 )
        {
          v29 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        }
        Windows::Internal::String::~String((Windows::Internal::String *)v33);
        Windows::Internal::String::~String((Windows::Internal::String *)&v31);
        GenericStringHandle<unsigned short>::FreeIt(&v30);
        SidHandle::~SidHandle(v87);
        return v19;
      }
      v9 = WindowsCreateString(v6, v8, &string);
      if ( v9 >= 0 )
      {
        v4 = string;
        v31 = string;
        WindowsDeleteString(0);
      }
    }
    v10 = -2147024362;
    goto LABEL_16;
  }
  catch ( const ComError *v34 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids,
        *((unsigned int *)v34 + 6),
        *((_DWORD *)v34 + 7));
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18003a1fc  mov     rax, rsp
0x18003a1ff  mov     [rax+20h], r9
0x18003a203  mov     [rax+18h], r8
0x18003a207  mov     [rax+10h], rdx
0x18003a20b  mov     [rax+8], rcx
0x18003a20f  push    rbx
0x18003a210  push    rsi
0x18003a211  push    rdi
0x18003a212  push    r12
0x18003a214  push    r13
0x18003a216  push    r14
0x18003a218  push    r15
0x18003a21a  sub     rsp, 450h
0x18003a221  xor     r14d, r14d
0x18003a224  cmp     [rcx+6F0h], r14
0x18003a22b  jnz     short loc_18003A2AA
0x18003a22d  lea     rax, WPP_GLOBAL_Control
0x18003a234  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a23b  cmp     rcx, rax
0x18003a23e  jz      short loc_18003A25A
0x18003a240  test    byte ptr [rcx+1Ch], 4
0x18003a244  jz      short loc_18003A25A
0x18003a246  lea     edx, [r14+39h]
0x18003a24a  lea     r8, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids
0x18003a251  mov     rcx, [rcx+10h]
0x18003a255  call    WPP_SF_
0x18003a25a  xorps   xmm0, xmm0
0x18003a25d  movups  [rsp+488h+var_3F0], xmm0
0x18003a265  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18003a26c  mov     [rsp+488h+pExceptionObject], rax
0x18003a274  mov     [rsp+488h+var_3E0], 8020006Bh
0x18003a27f  mov     [rsp+488h+var_3DC], 5DBh
0x18003a28a  mov     esi, 1
0x18003a28f  mov     [rsp+488h+var_3D8], esi
0x18003a296  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003a29d  lea     rcx, [rsp+488h+pExceptionObject]; pExceptionObject
0x18003a2a5  call    _CxxThrowException_0
0x18003a2aa  mov     rax, [r8]
0x18003a2ad  mov     [rsp+488h+var_428], rax
0x18003a2b2  mov     rax, [r8+8]
0x18003a2b6  mov     [rsp+488h+var_420], rax
0x18003a2bb  mov     esi, 1
0x18003a2c0  lock add [rax], esi
0x18003a2c3  lea     rdx, [rsp+488h+var_428]
0x18003a2c8  lea     rcx, [rsp+488h+var_430]
0x18003a2cd  call    ?SidToSidString@@YA?AV?$GenericStringHandle@G@@VSidHandle@@@Z; SidToSidString(SidHandle)
0x18003a2d2  nop
0x18003a2d3  mov     rdi, r14
0x18003a2d6  mov     [rsp+488h+var_428], r14
0x18003a2db  mov     rbx, r14
0x18003a2de  mov     [rsp+488h+var_418], rbx
0x18003a2e3  mov     rcx, [rsp+488h+var_430]
0x18003a2e8  add     rcx, 0Ch; sourceString
0x18003a2ec  jz      short loc_18003A340
0x18003a2ee  mov     [rsp+488h+string], r14
0x18003a2f3  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003a2f7  mov     rdx, r12
0x18003a2fa  inc     rdx; length
0x18003a2fd  cmp     [rcx+rdx*2], r14w
0x18003a302  jnz     short loc_18003A2FA
0x18003a304  mov     r13d, 0FFFFFFFFh
0x18003a30a  cmp     rdx, r13
0x18003a30d  ja      short loc_18003A335
0x18003a30f  lea     r8, [rsp+488h+string]; string
0x18003a314  call    cs:__imp_WindowsCreateString
0x18003a31a  mov     r15d, eax
0x18003a31d  test    eax, eax
0x18003a31f  js      short loc_18003A350
0x18003a321  mov     rdi, [rsp+488h+string]
0x18003a326  mov     [rsp+488h+var_428], rdi
0x18003a32b  xor     ecx, ecx; string
0x18003a32d  call    cs:__imp_WindowsDeleteString
0x18003a333  jmp     short loc_18003A350
0x18003a335  mov     r14d, 80070216h
0x18003a33b  mov     r15d, r14d
0x18003a33e  jmp     short loc_18003A356
0x18003a340  mov     r15d, 80004003h
0x18003a346  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003a34a  mov     r13d, 0FFFFFFFFh
0x18003a350  mov     r14d, 80070216h
0x18003a356  xor     eax, eax
0x18003a358  test    r15d, r15d
0x18003a35b  jns     short loc_18003A3A5
0x18003a35d  xorps   xmm0, xmm0
0x18003a360  movups  [rsp+488h+var_390], xmm0
0x18003a368  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18003a36f  mov     [rsp+488h+var_398], rax
0x18003a377  mov     [rsp+488h+var_380], r15d
0x18003a37f  mov     [rsp+488h+var_37C], 5E2h
0x18003a38a  mov     [rsp+488h+var_378], esi
0x18003a391  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003a398  lea     rcx, [rsp+488h+var_398]; pExceptionObject
0x18003a3a0  call    _CxxThrowException_0
0x18003a3a5  mov     r15, [rsp+488h+sourceString]
0x18003a3ad  test    r15, r15
0x18003a3b0  jz      short loc_18003A3F2
0x18003a3b2  mov     [rsp+488h+string], rax
0x18003a3b7  inc     r12
0x18003a3ba  cmp     [r15+r12*2], ax
0x18003a3bf  jnz     short loc_18003A3B7
0x18003a3c1  cmp     r12, r13
0x18003a3c4  ja      short loc_18003A3F8
0x18003a3c6  mov     edx, r12d; length
0x18003a3c9  lea     r8, [rsp+488h+string]; string
0x18003a3ce  mov     rcx, r15; sourceString
0x18003a3d1  call    cs:__imp_WindowsCreateString
0x18003a3d7  mov     r14d, eax
0x18003a3da  test    eax, eax
0x18003a3dc  js      short loc_18003A3F8
0x18003a3de  mov     rbx, [rsp+488h+string]
0x18003a3e3  mov     [rsp+488h+var_418], rbx
0x18003a3e8  xor     ecx, ecx; string
0x18003a3ea  call    cs:__imp_WindowsDeleteString
0x18003a3f0  jmp     short loc_18003A3F8
0x18003a3f2  mov     r14d, 80004003h
0x18003a3f8  xor     r12d, r12d
0x18003a3fb  test    r14d, r14d
0x18003a3fe  jns     short loc_18003A448
0x18003a400  xorps   xmm0, xmm0
0x18003a403  movups  [rsp+488h+var_330], xmm0
0x18003a40b  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18003a412  mov     [rsp+488h+var_338], rax
0x18003a41a  mov     [rsp+488h+var_320], r14d
0x18003a422  mov     [rsp+488h+var_31C], 5E3h
0x18003a42d  mov     [rsp+488h+var_318], esi
0x18003a434  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003a43b  lea     rcx, [rsp+488h+var_338]; pExceptionObject
0x18003a443  call    _CxxThrowException_0
0x18003a448  mov     [rsp+488h+var_438], r12
0x18003a44d  mov     rcx, [rsp+488h+arg_0]
0x18003a455  mov     rcx, [rcx+6F0h]
0x18003a45c  mov     rax, [rcx]
0x18003a45f  lea     r9, [rsp+488h+var_438]
0x18003a464  mov     r8, rbx
0x18003a467  mov     rdx, rdi
0x18003a46a  mov     rax, [rax+0A0h]
0x18003a471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a476  mov     ecx, eax
0x18003a478  test    eax, eax
0x18003a47a  jns     short loc_18003A4C3
0x18003a47c  xorps   xmm0, xmm0
0x18003a47f  movups  [rsp+488h+var_2D0], xmm0
0x18003a487  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18003a48e  mov     [rsp+488h+var_2D8], rax
0x18003a496  mov     [rsp+488h+var_2C0], ecx
0x18003a49d  mov     [rsp+488h+var_2BC], 5E9h
0x18003a4a8  mov     [rsp+488h+var_2B8], esi
0x18003a4af  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003a4b6  lea     rcx, [rsp+488h+var_2D8]; pExceptionObject
0x18003a4be  call    _CxxThrowException_0
0x18003a4c3  mov     [rsp+488h+var_448], r12
0x18003a4c8  mov     rcx, [rsp+488h+var_438]
0x18003a4cd  mov     rax, [rcx]
0x18003a4d0  lea     rdx, [rsp+488h+var_448]
0x18003a4d5  mov     rax, [rax+30h]
0x18003a4d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4de  mov     ecx, eax
0x18003a4e0  test    eax, eax
0x18003a4e2  jns     short loc_18003A52B
0x18003a4e4  xorps   xmm0, xmm0
0x18003a4e7  movups  [rsp+488h+var_270], xmm0
0x18003a4ef  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18003a4f6  mov     [rsp+488h+var_278], rax
0x18003a4fe  mov     [rsp+488h+var_260], ecx
0x18003a505  mov     [rsp+488h+var_25C], 5ECh
0x18003a510  mov     [rsp+488h+var_258], esi
0x18003a517  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003a51e  lea     rcx, [rsp+488h+var_278]; pExceptionObject
0x18003a526  call    _CxxThrowException_0
0x18003a52b  mov     [rsp+488h+var_458], r12b
0x18003a530  mov     rcx, [rsp+488h+var_448]
0x18003a535  mov     rax, [rcx]
0x18003a538  lea     rdx, [rsp+488h+var_458]
0x18003a53d  mov     rax, [rax+38h]
0x18003a541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a546  mov     ecx, eax
0x18003a548  test    eax, eax
0x18003a54a  jns     short loc_18003A593
0x18003a54c  xorps   xmm0, xmm0
0x18003a54f  movups  [rsp+488h+var_210], xmm0
0x18003a557  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18003a55e  mov     [rsp+488h+var_218], rax
0x18003a566  mov     [rsp+488h+var_200], ecx
0x18003a56d  mov     [rsp+488h+var_1FC], 5EFh
0x18003a578  mov     [rsp+488h+var_1F8], esi
0x18003a57f  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003a586  lea     rcx, [rsp+488h+var_218]; pExceptionObject
0x18003a58e  call    _CxxThrowException_0
0x18003a593  cmp     [rsp+488h+var_458], r12b
0x18003a598  jz      loc_18003A7B7
0x18003a59e  mov     [rsp+488h+var_440], r12
0x18003a5a3  mov     rcx, [rsp+488h+var_448]
0x18003a5a8  mov     rax, [rcx]
0x18003a5ab  lea     rdx, [rsp+488h+var_440]
0x18003a5b0  mov     rax, [rax+30h]
0x18003a5b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a5b9  mov     ecx, eax
0x18003a5bb  test    eax, eax
0x18003a5bd  jns     short loc_18003A606
0x18003a5bf  xorps   xmm0, xmm0
0x18003a5c2  movups  [rsp+488h+var_1B0], xmm0
0x18003a5ca  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18003a5d1  mov     [rsp+488h+var_1B8], rax
0x18003a5d9  mov     [rsp+488h+var_1A0], ecx
0x18003a5e0  mov     [rsp+488h+var_19C], 5F4h
0x18003a5eb  mov     [rsp+488h+var_198], esi
0x18003a5f2  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003a5f9  lea     rcx, [rsp+488h+var_1B8]; pExceptionObject
0x18003a601  call    _CxxThrowException_0
0x18003a606  mov     [rsp+488h+arg_0], r12
0x18003a60e  mov     rcx, [rsp+488h+var_440]
0x18003a613  mov     rax, [rcx]
0x18003a616  lea     rdx, [rsp+488h+arg_0]
0x18003a61e  mov     rax, [rax+30h]
0x18003a622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a627  mov     ecx, eax
0x18003a629  test    eax, eax
0x18003a62b  jns     short loc_18003A674
0x18003a62d  xorps   xmm0, xmm0
0x18003a630  movups  [rsp+488h+var_150], xmm0
0x18003a638  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18003a63f  mov     [rsp+488h+var_158], rax
0x18003a647  mov     [rsp+488h+var_140], ecx
0x18003a64e  mov     [rsp+488h+var_13C], 5F7h
0x18003a659  mov     [rsp+488h+var_138], esi
0x18003a660  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003a667  lea     rcx, [rsp+488h+var_158]; pExceptionObject
0x18003a66f  call    _CxxThrowException_0
0x18003a674  mov     [rsp+488h+string], r12
0x18003a679  mov     rcx, [rsp+488h+arg_0]
0x18003a681  mov     rax, [rcx]
0x18003a684  lea     rdx, [rsp+488h+string]
0x18003a689  mov     rax, [rax+60h]
0x18003a68d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a692  mov     ecx, eax
0x18003a694  test    eax, eax
0x18003a696  jns     short loc_18003A6DF
0x18003a698  xorps   xmm0, xmm0
0x18003a69b  movups  [rsp+488h+var_F0], xmm0
0x18003a6a3  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18003a6aa  mov     [rsp+488h+var_F8], rax
0x18003a6b2  mov     [rsp+488h+var_E0], ecx
0x18003a6b9  mov     [rsp+488h+var_DC], 5FAh
0x18003a6c4  mov     [rsp+488h+var_D8], esi
0x18003a6cb  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003a6d2  lea     rcx, [rsp+488h+var_F8]; pExceptionObject
0x18003a6da  call    _CxxThrowException_0
0x18003a6df  xor     edx, edx; length
0x18003a6e1  mov     rcx, [rsp+488h+string]; string
0x18003a6e6  call    cs:__imp_WindowsGetStringRawBuffer
0x18003a6ec  mov     rdx, rax
0x18003a6ef  mov     rbx, [rsp+488h+arg_8]
0x18003a6f7  mov     rcx, rbx
0x18003a6fa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003a6ff  nop
0x18003a700  lea     rcx, [rsp+488h+string]; this
0x18003a705  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18003a70a  nop
0x18003a70b  mov     rcx, [rsp+488h+arg_0]
0x18003a713  test    rcx, rcx
0x18003a716  jz      short loc_18003A72D
0x18003a718  mov     [rsp+488h+arg_0], r12
0x18003a720  mov     rax, [rcx]
0x18003a723  mov     rax, [rax+10h]
0x18003a727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a72c  nop
0x18003a72d  mov     rcx, [rsp+488h+var_440]
0x18003a732  test    rcx, rcx
0x18003a735  jz      short loc_18003A749
0x18003a737  mov     [rsp+488h+var_440], r12
0x18003a73c  mov     rax, [rcx]
0x18003a73f  mov     rax, [rax+10h]
0x18003a743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a748  nop
0x18003a749  mov     rcx, [rsp+488h+var_448]
0x18003a74e  test    rcx, rcx
0x18003a751  jz      short loc_18003A765
0x18003a753  mov     [rsp+488h+var_448], r12
0x18003a758  mov     rax, [rcx]
0x18003a75b  mov     rax, [rax+10h]
0x18003a75f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a764  nop
0x18003a765  mov     rcx, [rsp+488h+var_438]
0x18003a76a  test    rcx, rcx
0x18003a76d  jz      short loc_18003A781
0x18003a76f  mov     [rsp+488h+var_438], r12
0x18003a774  mov     rax, [rcx]
0x18003a777  mov     rax, [rax+10h]
0x18003a77b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a780  nop
0x18003a781  lea     rcx, [rsp+488h+var_418]; this
0x18003a786  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18003a78b  nop
0x18003a78c  lea     rcx, [rsp+488h+var_428]; this
0x18003a791  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18003a796  nop
0x18003a797  lea     rcx, [rsp+488h+var_430]
0x18003a79c  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x18003a7a1  nop
0x18003a7a2  mov     rcx, [rsp+488h+arg_10]; this
  ... truncated ...
```
