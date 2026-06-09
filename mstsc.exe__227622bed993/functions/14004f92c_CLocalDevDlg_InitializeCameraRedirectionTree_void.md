# CLocalDevDlg::InitializeCameraRedirectionTree(void)

- ea: `0x14004f92c`
- end: `0x140050104`
- name: `?InitializeCameraRedirectionTree@CLocalDevDlg@@AEAAXXZ`
- size: `2008`
- prototype: `void __fastcall(CLocalDevDlg *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x1400502ac`

## callees

- `0x140003b14`
- `0x140003b20`
- `0x140004703`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000cffc`
- `0x14000d078`
- `0x14004f92c`
- `0x1400512d8`
- `0x1400fa960`
- `0x140112010`

## import_xrefs

- `USER32!SendMessageW` at `0x14004fc43`
- `USER32!SendMessageW` at `0x14004fd63`
- `USER32!SendMessageW` at `0x14004fdf5`
- `USER32!SendMessageW` at `0x14004ff82`
- `USER32!SendMessageW` at `0x14004ffad`
- `USER32!SendMessageW` at `0x140050071`
- `USER32!SendMessageW` at `0x1400500ce`
- `USER32!SendMessageW` at `0x14004fc43`
- `USER32!SendMessageW` at `0x14004fd63`
- `USER32!SendMessageW` at `0x14004fdf5`
- `USER32!SendMessageW` at `0x14004ff82`
- `USER32!SendMessageW` at `0x14004ffad`
- `USER32!SendMessageW` at `0x140050071`
- `USER32!SendMessageW` at `0x1400500ce`
- `KERNEL32!GetLastError` at `0x14004faff`
- `KERNEL32!GetLastError` at `0x14004fb80`
- `KERNEL32!GetLastError` at `0x14004fc7f`
- `KERNEL32!GetLastError` at `0x14004faff`
- `KERNEL32!GetLastError` at `0x14004fb80`
- `KERNEL32!GetLastError` at `0x14004fc7f`
- `OLEAUT32!__imp_SysFreeString` at `0x14004fd72`
- `OLEAUT32!__imp_SysFreeString` at `0x14004fd72`

## string_xrefs

- `0x14004fbed`: `_pCameraConfigCollection->get_Count failed`
- `0x14004ff1e`: `_pCameraConfigCollection->get_ByIndex failed`
- `0x14004fe79`: `spCameraConfig->get_Redirected failed`
- `0x140050012`: `_pCameraConfigCollection->get_RedirectByDefault failed`
- `0x14004feec`: `spCameraConfig->get_DeviceExists failed`
- `0x14004feba`: `spCameraConfig->get_FriendlyName failed`

## pseudocode

```c
void __fastcall CLocalDevDlg::InitializeCameraRedirectionTree(CLocalDevDlg *this)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  DWORD LastError; // ebx
  unsigned int v6; // eax
  __int64 v7; // rdx
  int v8; // ebx
  unsigned int v9; // eax
  HWND v10; // rcx
  LRESULT v11; // rax
  struct _TREEITEM *v12; // r14
  int v13; // ebx
  int v14; // r15d
  int v15; // r12d
  unsigned int i; // esi
  __int64 v17; // rcx
  int v18; // r13d
  HWND v19; // rcx
  HWND v20; // rcx
  __int64 v21; // rcx
  unsigned int v22; // eax
  int v23; // edx
  const char *v24; // rcx
  __int64 v25; // rcx
  HWND v26; // rcx
  LRESULT v27; // r13
  int v28; // esi
  unsigned int v29; // eax
  HWND v30; // rcx
  int v31; // esi
  __int64 v32; // [rsp+30h] [rbp-A9h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-A1h] BYREF
  unsigned __int16 *v34; // [rsp+40h] [rbp-99h]
  void *Block; // [rsp+48h] [rbp-91h]
  LPARAM v36[2]; // [rsp+50h] [rbp-89h] BYREF
  __int128 v37; // [rsp+60h] [rbp-79h]
  __int128 v38; // [rsp+70h] [rbp-69h]
  __int64 v39; // [rsp+80h] [rbp-59h]
  LRESULT v40; // [rsp+88h] [rbp-51h]
  LPARAM lParam[2]; // [rsp+90h] [rbp-49h] BYREF
  int v42; // [rsp+A0h] [rbp-39h]
  void *v43; // [rsp+B8h] [rbp-21h]
  __int64 v44; // [rsp+D0h] [rbp-9h]
  __int16 v45; // [rsp+140h] [rbp+67h] BYREF
  __int16 v46; // [rsp+148h] [rbp+6Fh] BYREF
  __int16 v47; // [rsp+150h] [rbp+77h] BYREF
  unsigned int v48; // [rsp+158h] [rbp+7Fh] BYREF

  v48 = 0;
  memset_0(lParam, 0, 0x60u);
  *((_DWORD *)this + 127) = 0;
  if ( !*((_QWORD *)this + 58) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        WPP_03f103dd8adf3152876104925e3b4ead_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    return;
  }
  Block = operator new[](0x800u);
  if ( !Block )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        (unsigned int)WPP_03f103dd8adf3152876104925e3b4ead_Traceguids,
        v3,
        (__int64)"TCHAR[]");
    }
    return;
  }
  v34 = (unsigned __int16 *)operator new[](0x800u);
  if ( !v34 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        (unsigned int)WPP_03f103dd8adf3152876104925e3b4ead_Traceguids,
        v4,
        (__int64)"TCHAR[]");
    }
    goto LABEL_88;
  }
  if ( TSLoadString(*((HINSTANCE *)this + 61), 0x3464u, (unsigned __int16 *)Block, 1024) )
  {
    if ( TSLoadString(*((HINSTANCE *)this + 61), 0x3465u, v34, 1024) )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 58) + 32LL))(
             *((_QWORD *)this + 58),
             &v48);
      if ( v8 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            (unsigned int)WPP_03f103dd8adf3152876104925e3b4ead_Traceguids,
            v9,
            (__int64)"_pCameraConfigCollection->get_Count failed",
            v8);
        }
        goto LABEL_88;
      }
      v10 = (HWND)*((_QWORD *)this + 60);
      *(__m128i *)lParam = _mm_load_si128((const __m128i *)&_xmm_ffffffffffff0002ffffffffffff0000);
      v42 = 5;
      v43 = Block;
      v11 = SendMessageW(v10, 0x1132u, 0, (LPARAM)lParam);
      v12 = (struct _TREEITEM *)v11;
      if ( v11 )
      {
        v13 = 1;
        lParam[0] = v11;
        v14 = 1;
        *((_DWORD *)this + 127) = 1;
        v15 = 1;
        lParam[1] = -65534;
        for ( i = 0; i < v48; ++i )
        {
          v17 = *((_QWORD *)this + 58);
          v32 = 0;
          v47 = 0;
          bstrString = 0;
          v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v17 + 40LL))(v17, i, &v32);
          if ( v18 < 0 )
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_71;
            }
            v22 = RdpWppGetCurrentThreadActivityIdPrefix();
            v23 = 31;
            v24 = "_pCameraConfigCollection->get_ByIndex failed";
LABEL_70:
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v23,
              (unsigned int)WPP_03f103dd8adf3152876104925e3b4ead_Traceguids,
              v22,
              (__int64)v24,
              v18);
            goto LABEL_71;
          }
          v18 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v32 + 72LL))(v32, &v47);
          if ( v18 < 0 )
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_71;
            }
            v22 = RdpWppGetCurrentThreadActivityIdPrefix();
            v23 = 32;
            v24 = "spCameraConfig->get_DeviceExists failed";
            goto LABEL_70;
          }
          if ( v47 )
          {
            v18 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v32 + 24LL))(v32, &bstrString);
            if ( v18 < 0 )
            {
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_71;
              }
              v22 = RdpWppGetCurrentThreadActivityIdPrefix();
              v23 = 33;
              v24 = "spCameraConfig->get_FriendlyName failed";
              goto LABEL_70;
            }
            v19 = (HWND)*((_QWORD *)this + 60);
            v43 = bstrString;
            v44 = i;
            v40 = SendMessageW(v19, 0x1132u, 0, (LPARAM)lParam);
            SysFreeString(bstrString);
            v45 = 0;
            v18 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v32 + 64LL))(v32, &v45);
            if ( v18 < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v22 = RdpWppGetCurrentThreadActivityIdPrefix();
                v23 = 34;
                v24 = "spCameraConfig->get_Redirected failed";
                goto LABEL_70;
              }
LABEL_71:
              v25 = v32;
              if ( v32 )
              {
                v32 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
              }
              goto LABEL_88;
            }
            v39 = 0;
            v36[1] = v40;
            v36[0] = 8;
            v37 = 0;
            LODWORD(v37) = v45 != 0 ? 0x2000 : 4096;
            v20 = (HWND)*((_QWORD *)this + 60);
            v38 = 0;
            DWORD1(v37) = 61440;
            SendMessageW(v20, 0x113Fu, 0, (LPARAM)v36);
            if ( !v15 || (v15 = 1, v45) )
              v15 = 0;
            if ( !v14 || (v14 = 1, !v45) )
              v14 = 0;
          }
          v21 = v32;
          if ( v32 )
          {
            v32 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          }
        }
        SendMessageW(*((HWND *)this + 60), 0x1113u, 0, (LPARAM)v12);
        v26 = (HWND)*((_QWORD *)this + 60);
        v43 = v34;
        v44 = 0xFFFFFFFFLL;
        v27 = SendMessageW(v26, 0x1132u, 0, (LPARAM)lParam);
        v46 = 0;
        v28 = (*(__int64 (__fastcall **)(_QWORD, __int16 *))(**((_QWORD **)this + 58) + 80LL))(
                *((_QWORD *)this + 58),
                &v46);
        if ( v28 >= 0 )
        {
          v39 = 0;
          v37 = 0;
          LODWORD(v37) = v46 != 0 ? 0x2000 : 4096;
          v30 = (HWND)*((_QWORD *)this + 60);
          v36[0] = 8;
          v38 = 0;
          v36[1] = v27;
          DWORD1(v37) = 61440;
          SendMessageW(v30, 0x113Fu, 0, (LPARAM)v36);
          if ( !v15 || (v31 = 1, v46) )
            v31 = 0;
          if ( !v14 || !v46 )
            v13 = 0;
          CLocalDevDlg::ReportChange(this, v12, 0);
          if ( !v13 && !v31 || *((_DWORD *)this + 128) )
            SendMessageW(*((HWND *)this + 60), 0x1102u, 2u, (LPARAM)v12);
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v29 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            (unsigned int)WPP_03f103dd8adf3152876104925e3b4ead_Traceguids,
            v29,
            (__int64)"_pCameraConfigCollection->get_RedirectByDefault failed",
            v28);
        }
        goto LABEL_88;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        v6 = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 30;
        goto LABEL_21;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 28;
      goto LABEL_21;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 27;
LABEL_21:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_03f103dd8adf3152876104925e3b4ead_Traceguids, v6, LastError);
  }
LABEL_88:
  operator delete(Block);
  if ( v34 )
    operator delete(v34);
}

```

## disassembly

```asm
0x14004f92c  push    rbp
0x14004f92e  push    rbx
0x14004f92f  push    rsi
0x14004f930  push    rdi
0x14004f931  push    r12
0x14004f933  push    r13
0x14004f935  push    r14
0x14004f937  push    r15
0x14004f939  lea     rbp, [rsp-1Fh]
0x14004f93e  sub     rsp, 0F8h
0x14004f945  xor     r13d, r13d
0x14004f948  mov     rdi, rcx
0x14004f94b  xor     edx, edx; Val
0x14004f94d  mov     [rbp+57h+arg_18], r13d
0x14004f951  lea     rcx, [rbp+57h+lParam]; void *
0x14004f955  lea     r8d, [r13+60h]; Size
0x14004f959  call    memset_0
0x14004f95e  mov     [rdi+1FCh], r13d
0x14004f965  cmp     [rdi+1D0h], r13
0x14004f96c  jnz     short loc_14004F9C3
0x14004f96e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f975  lea     rax, WPP_GLOBAL_Control
0x14004f97c  cmp     rcx, rax
0x14004f97f  jz      loc_1400500F0
0x14004f985  lea     ebx, [r13+1]
0x14004f989  test    [rcx+1Ch], bl
0x14004f98c  jz      loc_1400500F0
0x14004f992  cmp     byte ptr [rcx+19h], 4
0x14004f996  jb      loc_1400500F0
0x14004f99c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004f9a1  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f9a8  lea     edx, [rbx+17h]
0x14004f9ab  mov     r9d, eax
0x14004f9ae  lea     r8, WPP_03f103dd8adf3152876104925e3b4ead_Traceguids
0x14004f9b5  mov     rcx, [rcx+10h]
0x14004f9b9  call    WPP_SF_d
0x14004f9be  jmp     loc_1400500F0
0x14004f9c3  mov     ebx, 800h
0x14004f9c8  mov     ecx, ebx; unsigned __int64
0x14004f9ca  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14004f9cf  mov     [rsp+130h+Block], rax
0x14004f9d4  test    rax, rax
0x14004f9d7  jnz     short loc_14004FA39
0x14004f9d9  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f9e0  lea     rax, WPP_GLOBAL_Control
0x14004f9e7  cmp     rcx, rax
0x14004f9ea  jz      loc_1400500F0
0x14004f9f0  test    byte ptr [rcx+1Ch], 8
0x14004f9f4  jz      loc_1400500F0
0x14004f9fa  cmp     byte ptr [rcx+19h], 2
0x14004f9fe  jb      loc_1400500F0
0x14004fa04  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004fa09  lea     rcx, aTchar_0; "TCHAR[]"
0x14004fa10  mov     edx, 19h
0x14004fa15  mov     [rsp+130h+var_110], rcx
0x14004fa1a  lea     r8, WPP_03f103dd8adf3152876104925e3b4ead_Traceguids
0x14004fa21  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fa28  mov     r9d, eax
0x14004fa2b  mov     rcx, [rcx+10h]
0x14004fa2f  call    WPP_SF_Ds
0x14004fa34  jmp     loc_1400500F0
0x14004fa39  mov     rcx, rbx; unsigned __int64
0x14004fa3c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14004fa41  mov     [rsp+130h+var_F0], rax
0x14004fa46  test    rax, rax
0x14004fa49  jnz     short loc_14004FAAB
0x14004fa4b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fa52  lea     rax, WPP_GLOBAL_Control
0x14004fa59  cmp     rcx, rax
0x14004fa5c  jz      loc_1400500D4
0x14004fa62  test    byte ptr [rcx+1Ch], 8
0x14004fa66  jz      loc_1400500D4
0x14004fa6c  cmp     byte ptr [rcx+19h], 2
0x14004fa70  jb      loc_1400500D4
0x14004fa76  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004fa7b  lea     rcx, aTchar_0; "TCHAR[]"
0x14004fa82  mov     edx, 1Ah
0x14004fa87  mov     [rsp+130h+var_110], rcx
0x14004fa8c  lea     r8, WPP_03f103dd8adf3152876104925e3b4ead_Traceguids
0x14004fa93  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fa9a  mov     r9d, eax
0x14004fa9d  mov     rcx, [rcx+10h]
0x14004faa1  call    WPP_SF_Ds
0x14004faa6  jmp     loc_1400500D4
0x14004faab  mov     rsi, [rsp+130h+Block]
0x14004fab0  mov     ebx, 400h
0x14004fab5  mov     rcx, [rdi+1E8h]; HINSTANCE
0x14004fabc  mov     r9d, ebx; int
0x14004fabf  mov     r8, rsi; unsigned __int16 *
0x14004fac2  mov     edx, 3464h; unsigned int
0x14004fac7  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x14004facc  test    eax, eax
0x14004face  jnz     short loc_14004FB34
0x14004fad0  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fad7  lea     rax, WPP_GLOBAL_Control
0x14004fade  cmp     rcx, rax
0x14004fae1  jz      loc_1400500D4
0x14004fae7  mov     ebx, 1
0x14004faec  test    [rcx+1Ch], bl
0x14004faef  jz      loc_1400500D4
0x14004faf5  cmp     byte ptr [rcx+19h], 2
0x14004faf9  jb      loc_1400500D4
0x14004faff  call    cs:__imp_GetLastError
0x14004fb05  mov     ebx, eax
0x14004fb07  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004fb0c  mov     edx, 1Bh
0x14004fb11  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fb18  lea     r8, WPP_03f103dd8adf3152876104925e3b4ead_Traceguids
0x14004fb1f  mov     r9d, eax
0x14004fb22  mov     dword ptr [rsp+130h+var_110], ebx
0x14004fb26  mov     rcx, [rcx+10h]
0x14004fb2a  call    WPP_SF_Dd
0x14004fb2f  jmp     loc_1400500D4
0x14004fb34  mov     r8, [rsp+130h+var_F0]; unsigned __int16 *
0x14004fb39  mov     r9d, ebx; int
0x14004fb3c  mov     rcx, [rdi+1E8h]; HINSTANCE
0x14004fb43  mov     edx, 3465h; unsigned int
0x14004fb48  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x14004fb4d  test    eax, eax
0x14004fb4f  jnz     short loc_14004FB97
0x14004fb51  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fb58  lea     rax, WPP_GLOBAL_Control
0x14004fb5f  cmp     rcx, rax
0x14004fb62  jz      loc_1400500D4
0x14004fb68  mov     ebx, 1
0x14004fb6d  test    [rcx+1Ch], bl
0x14004fb70  jz      loc_1400500D4
0x14004fb76  cmp     byte ptr [rcx+19h], 2
0x14004fb7a  jb      loc_1400500D4
0x14004fb80  call    cs:__imp_GetLastError
0x14004fb86  mov     ebx, eax
0x14004fb88  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004fb8d  mov     edx, 1Ch
0x14004fb92  jmp     loc_14004FB11
0x14004fb97  mov     rcx, [rdi+1D0h]
0x14004fb9e  lea     rdx, [rbp+57h+arg_18]
0x14004fba2  mov     rax, [rcx]
0x14004fba5  mov     rax, [rax+20h]
0x14004fba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fbae  mov     ebx, eax
0x14004fbb0  test    eax, eax
0x14004fbb2  jns     short loc_14004FC18
0x14004fbb4  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fbbb  lea     rax, WPP_GLOBAL_Control
0x14004fbc2  cmp     rcx, rax
0x14004fbc5  jz      loc_1400500D4
0x14004fbcb  test    byte ptr [rcx+1Ch], 8
0x14004fbcf  jz      loc_1400500D4
0x14004fbd5  cmp     byte ptr [rcx+19h], 2
0x14004fbd9  jb      loc_1400500D4
0x14004fbdf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004fbe4  mov     edx, 1Dh
0x14004fbe9  mov     [rsp+130h+var_108], ebx
0x14004fbed  lea     rcx, aPcameraconfigc_1; "_pCameraConfigCollection->get_Count fai"...
0x14004fbf4  mov     [rsp+130h+var_110], rcx
0x14004fbf9  lea     r8, WPP_03f103dd8adf3152876104925e3b4ead_Traceguids
0x14004fc00  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fc07  mov     r9d, eax
0x14004fc0a  mov     rcx, [rcx+10h]
0x14004fc0e  call    WPP_SF_DsD
0x14004fc13  jmp     loc_1400500D4
0x14004fc18  movdqa  xmm0, cs:__xmm@ffffffffffff0002ffffffffffff0000
0x14004fc20  lea     r9, [rbp+57h+lParam]; lParam
0x14004fc24  mov     rcx, [rdi+1E0h]; hWnd
0x14004fc2b  xor     r8d, r8d; wParam
0x14004fc2e  mov     edx, 1132h; Msg
0x14004fc33  movdqa  xmmword ptr [rbp+57h+lParam], xmm0
0x14004fc38  mov     [rbp+57h+var_90], 5
0x14004fc3f  mov     [rbp+57h+var_78], rsi
0x14004fc43  call    cs:__imp_SendMessageW
0x14004fc49  mov     r14, rax
0x14004fc4c  test    rax, rax
0x14004fc4f  jnz     short loc_14004FC95
0x14004fc51  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fc58  lea     rax, WPP_GLOBAL_Control
0x14004fc5f  cmp     rcx, rax
0x14004fc62  jz      loc_1400500D4
0x14004fc68  lea     ebx, [r14+1]
0x14004fc6c  test    [rcx+1Ch], bl
0x14004fc6f  jz      loc_1400500D4
0x14004fc75  cmp     byte ptr [rcx+19h], 2
0x14004fc79  jb      loc_1400500D4
0x14004fc7f  call    cs:__imp_GetLastError
0x14004fc85  mov     ebx, eax
0x14004fc87  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004fc8c  lea     edx, [r14+1Eh]
0x14004fc90  jmp     loc_14004FB11
0x14004fc95  mov     ebx, 1
0x14004fc9a  mov     [rbp+57h+lParam], r14
0x14004fc9e  mov     r15d, ebx
0x14004fca1  mov     [rdi+1FCh], ebx
0x14004fca7  mov     r12d, ebx
0x14004fcaa  mov     [rbp+57h+lParam+8], 0FFFFFFFFFFFF0002h
0x14004fcb2  mov     esi, r13d
0x14004fcb5  cmp     esi, [rbp+57h+arg_18]
0x14004fcb8  jnb     loc_14004FF70
0x14004fcbe  mov     rcx, [rdi+1D0h]
0x14004fcc5  lea     r8, [rsp+130h+var_100]
0x14004fcca  mov     [rsp+130h+var_100], r13
0x14004fccf  mov     edx, esi
0x14004fcd1  mov     [rbp+57h+arg_10], r13w
0x14004fcd6  mov     [rsp+130h+bstrString], r13
0x14004fcdb  mov     rax, [rcx]
0x14004fcde  mov     rax, [rax+28h]
0x14004fce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fce7  mov     r13d, eax
0x14004fcea  test    eax, eax
0x14004fcec  js      loc_14004FEF5
0x14004fcf2  mov     rcx, [rsp+130h+var_100]
0x14004fcf7  lea     rdx, [rbp+57h+arg_10]
0x14004fcfb  mov     rax, [rcx]
0x14004fcfe  mov     rax, [rax+48h]
0x14004fd02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fd07  mov     r13d, eax
0x14004fd0a  test    eax, eax
0x14004fd0c  js      loc_14004FEC3
0x14004fd12  xor     r13d, r13d
0x14004fd15  cmp     [rbp+57h+arg_10], r13w
0x14004fd1a  jz      loc_14004FE22
0x14004fd20  mov     rcx, [rsp+130h+var_100]
0x14004fd25  lea     rdx, [rsp+130h+bstrString]
0x14004fd2a  mov     rax, [rcx]
0x14004fd2d  mov     rax, [rax+18h]
0x14004fd31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fd36  mov     r13d, eax
0x14004fd39  test    eax, eax
0x14004fd3b  js      loc_14004FE85
0x14004fd41  mov     rax, [rsp+130h+bstrString]
0x14004fd46  lea     r9, [rbp+57h+lParam]; lParam
0x14004fd4a  mov     rcx, [rdi+1E0h]; hWnd
0x14004fd51  xor     r8d, r8d; wParam
0x14004fd54  mov     [rbp+57h+var_78], rax
0x14004fd58  mov     edx, 1132h; Msg
0x14004fd5d  mov     eax, esi
0x14004fd5f  mov     [rbp+57h+var_60], rax
0x14004fd63  call    cs:__imp_SendMessageW
0x14004fd69  mov     rcx, [rsp+130h+bstrString]; bstrString
0x14004fd6e  mov     [rbp+57h+var_A8], rax
0x14004fd72  call    cs:__imp_SysFreeString
0x14004fd78  xor     ecx, ecx
0x14004fd7a  mov     [rbp+57h+arg_0], cx
0x14004fd7e  mov     rcx, [rsp+130h+var_100]
0x14004fd83  mov     rdx, [rcx]
0x14004fd86  mov     rax, [rdx+40h]
0x14004fd8a  lea     rdx, [rbp+57h+arg_0]
0x14004fd8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fd93  mov     r13d, eax
0x14004fd96  test    eax, eax
0x14004fd98  js      loc_14004FE44
0x14004fd9e  xor     eax, eax
0x14004fda0  lea     r9, [rsp+130h+var_E0]; lParam
0x14004fda5  mov     [rbp+57h+var_B0], rax
0x14004fda9  xorps   xmm0, xmm0
0x14004fdac  mov     rax, [rbp+57h+var_A8]
0x14004fdb0  mov     edx, 113Fh; Msg
0x14004fdb5  movups  xmmword ptr [rsp+130h+var_E0], xmm0
0x14004fdba  mov     [rsp+130h+var_E0+8], rax
0x14004fdbf  movzx   eax, [rbp+57h+arg_0]
0x14004fdc3  neg     ax
0x14004fdc6  mov     dword ptr [rsp+130h+var_E0], 8
0x14004fdce  mov     eax, 1000h
0x14004fdd3  sbb     ecx, ecx
0x14004fdd5  xor     r8d, r8d; wParam
0x14004fdd8  and     ecx, eax
0x14004fdda  add     ecx, eax
0x14004fddc  movups  [rbp+57h+var_D0], xmm0
0x14004fde0  mov     dword ptr [rbp+57h+var_D0], ecx
0x14004fde3  mov     rcx, [rdi+1E0h]; hWnd
0x14004fdea  movups  [rbp+57h+var_C0], xmm0
0x14004fdee  mov     dword ptr [rbp+57h+var_D0+4], 0F000h
0x14004fdf5  call    cs:__imp_SendMessageW
0x14004fdfb  movzx   eax, [rbp+57h+arg_0]
0x14004fdff  xor     r13d, r13d
0x14004fe02  test    r12d, r12d
0x14004fe05  jz      short loc_14004FE0F
0x14004fe07  mov     r12d, ebx
0x14004fe0a  test    ax, ax
0x14004fe0d  jz      short loc_14004FE12
0x14004fe0f  mov     r12d, r13d
0x14004fe12  test    r15d, r15d
0x14004fe15  jz      short loc_14004FE1F
0x14004fe17  mov     r15d, ebx
0x14004fe1a  test    ax, ax
0x14004fe1d  jnz     short loc_14004FE22
0x14004fe1f  mov     r15d, r13d
0x14004fe22  mov     rcx, [rsp+130h+var_100]
0x14004fe27  test    rcx, rcx
0x14004fe2a  jz      short loc_14004FE3D
0x14004fe2c  mov     [rsp+130h+var_100], r13
0x14004fe31  mov     rax, [rcx]
0x14004fe34  mov     rax, [rax+10h]
0x14004fe38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004fe3d  add     esi, ebx
0x14004fe3f  jmp     loc_14004FCB5
0x14004fe44  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fe4b  lea     rax, WPP_GLOBAL_Control
0x14004fe52  cmp     rcx, rax
0x14004fe55  jz      loc_14004FF49
0x14004fe5b  test    byte ptr [rcx+1Ch], 8
0x14004fe5f  jz      loc_14004FF49
  ... truncated ...
```
