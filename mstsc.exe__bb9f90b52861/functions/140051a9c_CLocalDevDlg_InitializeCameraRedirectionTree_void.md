# CLocalDevDlg::InitializeCameraRedirectionTree(void)

- ea: `0x140051a9c`
- end: `0x140052274`
- name: `?InitializeCameraRedirectionTree@CLocalDevDlg@@AEAAXXZ`
- size: `2008`
- prototype: `void __fastcall(CLocalDevDlg *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x14005241c`

## callees

- `0x140003b14`
- `0x140003b20`
- `0x140004703`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000cffc`
- `0x14000d078`
- `0x140051a9c`
- `0x140053448`
- `0x1400fcad0`
- `0x140114010`

## import_xrefs

- `USER32!SendMessageW` at `0x140051db3`
- `USER32!SendMessageW` at `0x140051ed3`
- `USER32!SendMessageW` at `0x140051f65`
- `USER32!SendMessageW` at `0x1400520f2`
- `USER32!SendMessageW` at `0x14005211d`
- `USER32!SendMessageW` at `0x1400521e1`
- `USER32!SendMessageW` at `0x14005223e`
- `USER32!SendMessageW` at `0x140051db3`
- `USER32!SendMessageW` at `0x140051ed3`
- `USER32!SendMessageW` at `0x140051f65`
- `USER32!SendMessageW` at `0x1400520f2`
- `USER32!SendMessageW` at `0x14005211d`
- `USER32!SendMessageW` at `0x1400521e1`
- `USER32!SendMessageW` at `0x14005223e`
- `KERNEL32!GetLastError` at `0x140051c6f`
- `KERNEL32!GetLastError` at `0x140051cf0`
- `KERNEL32!GetLastError` at `0x140051def`
- `KERNEL32!GetLastError` at `0x140051c6f`
- `KERNEL32!GetLastError` at `0x140051cf0`
- `KERNEL32!GetLastError` at `0x140051def`
- `OLEAUT32!__imp_SysFreeString` at `0x140051ee2`
- `OLEAUT32!__imp_SysFreeString` at `0x140051ee2`

## string_xrefs

- `0x140051d5d`: `_pCameraConfigCollection->get_Count failed`
- `0x14005208e`: `_pCameraConfigCollection->get_ByIndex failed`
- `0x140051fe9`: `spCameraConfig->get_Redirected failed`
- `0x140052182`: `_pCameraConfigCollection->get_RedirectByDefault failed`
- `0x14005205c`: `spCameraConfig->get_DeviceExists failed`
- `0x14005202a`: `spCameraConfig->get_FriendlyName failed`

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
0x140051a9c  push    rbp
0x140051a9e  push    rbx
0x140051a9f  push    rsi
0x140051aa0  push    rdi
0x140051aa1  push    r12
0x140051aa3  push    r13
0x140051aa5  push    r14
0x140051aa7  push    r15
0x140051aa9  lea     rbp, [rsp-1Fh]
0x140051aae  sub     rsp, 0F8h
0x140051ab5  xor     r13d, r13d
0x140051ab8  mov     rdi, rcx
0x140051abb  xor     edx, edx; Val
0x140051abd  mov     [rbp+57h+arg_18], r13d
0x140051ac1  lea     rcx, [rbp+57h+lParam]; void *
0x140051ac5  lea     r8d, [r13+60h]; Size
0x140051ac9  call    memset_0
0x140051ace  mov     [rdi+1FCh], r13d
0x140051ad5  cmp     [rdi+1D0h], r13
0x140051adc  jnz     short loc_140051B33
0x140051ade  mov     rcx, cs:WPP_GLOBAL_Control
0x140051ae5  lea     rax, WPP_GLOBAL_Control
0x140051aec  cmp     rcx, rax
0x140051aef  jz      loc_140052260
0x140051af5  lea     ebx, [r13+1]
0x140051af9  test    [rcx+1Ch], bl
0x140051afc  jz      loc_140052260
0x140051b02  cmp     byte ptr [rcx+19h], 4
0x140051b06  jb      loc_140052260
0x140051b0c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051b11  mov     rcx, cs:WPP_GLOBAL_Control
0x140051b18  lea     edx, [rbx+17h]
0x140051b1b  mov     r9d, eax
0x140051b1e  lea     r8, WPP_03f103dd8adf3152876104925e3b4ead_Traceguids
0x140051b25  mov     rcx, [rcx+10h]
0x140051b29  call    WPP_SF_d
0x140051b2e  jmp     loc_140052260
0x140051b33  mov     ebx, 800h
0x140051b38  mov     ecx, ebx; unsigned __int64
0x140051b3a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140051b3f  mov     [rsp+130h+Block], rax
0x140051b44  test    rax, rax
0x140051b47  jnz     short loc_140051BA9
0x140051b49  mov     rcx, cs:WPP_GLOBAL_Control
0x140051b50  lea     rax, WPP_GLOBAL_Control
0x140051b57  cmp     rcx, rax
0x140051b5a  jz      loc_140052260
0x140051b60  test    byte ptr [rcx+1Ch], 8
0x140051b64  jz      loc_140052260
0x140051b6a  cmp     byte ptr [rcx+19h], 2
0x140051b6e  jb      loc_140052260
0x140051b74  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051b79  lea     rcx, aTchar_0; "TCHAR[]"
0x140051b80  mov     edx, 19h
0x140051b85  mov     [rsp+130h+var_110], rcx
0x140051b8a  lea     r8, WPP_03f103dd8adf3152876104925e3b4ead_Traceguids
0x140051b91  mov     rcx, cs:WPP_GLOBAL_Control
0x140051b98  mov     r9d, eax
0x140051b9b  mov     rcx, [rcx+10h]
0x140051b9f  call    WPP_SF_Ds
0x140051ba4  jmp     loc_140052260
0x140051ba9  mov     rcx, rbx; unsigned __int64
0x140051bac  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140051bb1  mov     [rsp+130h+var_F0], rax
0x140051bb6  test    rax, rax
0x140051bb9  jnz     short loc_140051C1B
0x140051bbb  mov     rcx, cs:WPP_GLOBAL_Control
0x140051bc2  lea     rax, WPP_GLOBAL_Control
0x140051bc9  cmp     rcx, rax
0x140051bcc  jz      loc_140052244
0x140051bd2  test    byte ptr [rcx+1Ch], 8
0x140051bd6  jz      loc_140052244
0x140051bdc  cmp     byte ptr [rcx+19h], 2
0x140051be0  jb      loc_140052244
0x140051be6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051beb  lea     rcx, aTchar_0; "TCHAR[]"
0x140051bf2  mov     edx, 1Ah
0x140051bf7  mov     [rsp+130h+var_110], rcx
0x140051bfc  lea     r8, WPP_03f103dd8adf3152876104925e3b4ead_Traceguids
0x140051c03  mov     rcx, cs:WPP_GLOBAL_Control
0x140051c0a  mov     r9d, eax
0x140051c0d  mov     rcx, [rcx+10h]
0x140051c11  call    WPP_SF_Ds
0x140051c16  jmp     loc_140052244
0x140051c1b  mov     rsi, [rsp+130h+Block]
0x140051c20  mov     ebx, 400h
0x140051c25  mov     rcx, [rdi+1E8h]; HINSTANCE
0x140051c2c  mov     r9d, ebx; int
0x140051c2f  mov     r8, rsi; unsigned __int16 *
0x140051c32  mov     edx, 3464h; unsigned int
0x140051c37  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x140051c3c  test    eax, eax
0x140051c3e  jnz     short loc_140051CA4
0x140051c40  mov     rcx, cs:WPP_GLOBAL_Control
0x140051c47  lea     rax, WPP_GLOBAL_Control
0x140051c4e  cmp     rcx, rax
0x140051c51  jz      loc_140052244
0x140051c57  mov     ebx, 1
0x140051c5c  test    [rcx+1Ch], bl
0x140051c5f  jz      loc_140052244
0x140051c65  cmp     byte ptr [rcx+19h], 2
0x140051c69  jb      loc_140052244
0x140051c6f  call    cs:__imp_GetLastError
0x140051c75  mov     ebx, eax
0x140051c77  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051c7c  mov     edx, 1Bh
0x140051c81  mov     rcx, cs:WPP_GLOBAL_Control
0x140051c88  lea     r8, WPP_03f103dd8adf3152876104925e3b4ead_Traceguids
0x140051c8f  mov     r9d, eax
0x140051c92  mov     dword ptr [rsp+130h+var_110], ebx
0x140051c96  mov     rcx, [rcx+10h]
0x140051c9a  call    WPP_SF_Dd
0x140051c9f  jmp     loc_140052244
0x140051ca4  mov     r8, [rsp+130h+var_F0]; unsigned __int16 *
0x140051ca9  mov     r9d, ebx; int
0x140051cac  mov     rcx, [rdi+1E8h]; HINSTANCE
0x140051cb3  mov     edx, 3465h; unsigned int
0x140051cb8  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x140051cbd  test    eax, eax
0x140051cbf  jnz     short loc_140051D07
0x140051cc1  mov     rcx, cs:WPP_GLOBAL_Control
0x140051cc8  lea     rax, WPP_GLOBAL_Control
0x140051ccf  cmp     rcx, rax
0x140051cd2  jz      loc_140052244
0x140051cd8  mov     ebx, 1
0x140051cdd  test    [rcx+1Ch], bl
0x140051ce0  jz      loc_140052244
0x140051ce6  cmp     byte ptr [rcx+19h], 2
0x140051cea  jb      loc_140052244
0x140051cf0  call    cs:__imp_GetLastError
0x140051cf6  mov     ebx, eax
0x140051cf8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051cfd  mov     edx, 1Ch
0x140051d02  jmp     loc_140051C81
0x140051d07  mov     rcx, [rdi+1D0h]
0x140051d0e  lea     rdx, [rbp+57h+arg_18]
0x140051d12  mov     rax, [rcx]
0x140051d15  mov     rax, [rax+20h]
0x140051d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140051d1e  mov     ebx, eax
0x140051d20  test    eax, eax
0x140051d22  jns     short loc_140051D88
0x140051d24  mov     rcx, cs:WPP_GLOBAL_Control
0x140051d2b  lea     rax, WPP_GLOBAL_Control
0x140051d32  cmp     rcx, rax
0x140051d35  jz      loc_140052244
0x140051d3b  test    byte ptr [rcx+1Ch], 8
0x140051d3f  jz      loc_140052244
0x140051d45  cmp     byte ptr [rcx+19h], 2
0x140051d49  jb      loc_140052244
0x140051d4f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051d54  mov     edx, 1Dh
0x140051d59  mov     [rsp+130h+var_108], ebx
0x140051d5d  lea     rcx, aPcameraconfigc_1; "_pCameraConfigCollection->get_Count fai"...
0x140051d64  mov     [rsp+130h+var_110], rcx
0x140051d69  lea     r8, WPP_03f103dd8adf3152876104925e3b4ead_Traceguids
0x140051d70  mov     rcx, cs:WPP_GLOBAL_Control
0x140051d77  mov     r9d, eax
0x140051d7a  mov     rcx, [rcx+10h]
0x140051d7e  call    WPP_SF_DsD
0x140051d83  jmp     loc_140052244
0x140051d88  movdqa  xmm0, cs:__xmm@ffffffffffff0002ffffffffffff0000
0x140051d90  lea     r9, [rbp+57h+lParam]; lParam
0x140051d94  mov     rcx, [rdi+1E0h]; hWnd
0x140051d9b  xor     r8d, r8d; wParam
0x140051d9e  mov     edx, 1132h; Msg
0x140051da3  movdqa  xmmword ptr [rbp+57h+lParam], xmm0
0x140051da8  mov     [rbp+57h+var_90], 5
0x140051daf  mov     [rbp+57h+var_78], rsi
0x140051db3  call    cs:__imp_SendMessageW
0x140051db9  mov     r14, rax
0x140051dbc  test    rax, rax
0x140051dbf  jnz     short loc_140051E05
0x140051dc1  mov     rcx, cs:WPP_GLOBAL_Control
0x140051dc8  lea     rax, WPP_GLOBAL_Control
0x140051dcf  cmp     rcx, rax
0x140051dd2  jz      loc_140052244
0x140051dd8  lea     ebx, [r14+1]
0x140051ddc  test    [rcx+1Ch], bl
0x140051ddf  jz      loc_140052244
0x140051de5  cmp     byte ptr [rcx+19h], 2
0x140051de9  jb      loc_140052244
0x140051def  call    cs:__imp_GetLastError
0x140051df5  mov     ebx, eax
0x140051df7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051dfc  lea     edx, [r14+1Eh]
0x140051e00  jmp     loc_140051C81
0x140051e05  mov     ebx, 1
0x140051e0a  mov     [rbp+57h+lParam], r14
0x140051e0e  mov     r15d, ebx
0x140051e11  mov     [rdi+1FCh], ebx
0x140051e17  mov     r12d, ebx
0x140051e1a  mov     [rbp+57h+lParam+8], 0FFFFFFFFFFFF0002h
0x140051e22  mov     esi, r13d
0x140051e25  cmp     esi, [rbp+57h+arg_18]
0x140051e28  jnb     loc_1400520E0
0x140051e2e  mov     rcx, [rdi+1D0h]
0x140051e35  lea     r8, [rsp+130h+var_100]
0x140051e3a  mov     [rsp+130h+var_100], r13
0x140051e3f  mov     edx, esi
0x140051e41  mov     [rbp+57h+arg_10], r13w
0x140051e46  mov     [rsp+130h+bstrString], r13
0x140051e4b  mov     rax, [rcx]
0x140051e4e  mov     rax, [rax+28h]
0x140051e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140051e57  mov     r13d, eax
0x140051e5a  test    eax, eax
0x140051e5c  js      loc_140052065
0x140051e62  mov     rcx, [rsp+130h+var_100]
0x140051e67  lea     rdx, [rbp+57h+arg_10]
0x140051e6b  mov     rax, [rcx]
0x140051e6e  mov     rax, [rax+48h]
0x140051e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140051e77  mov     r13d, eax
0x140051e7a  test    eax, eax
0x140051e7c  js      loc_140052033
0x140051e82  xor     r13d, r13d
0x140051e85  cmp     [rbp+57h+arg_10], r13w
0x140051e8a  jz      loc_140051F92
0x140051e90  mov     rcx, [rsp+130h+var_100]
0x140051e95  lea     rdx, [rsp+130h+bstrString]
0x140051e9a  mov     rax, [rcx]
0x140051e9d  mov     rax, [rax+18h]
0x140051ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140051ea6  mov     r13d, eax
0x140051ea9  test    eax, eax
0x140051eab  js      loc_140051FF5
0x140051eb1  mov     rax, [rsp+130h+bstrString]
0x140051eb6  lea     r9, [rbp+57h+lParam]; lParam
0x140051eba  mov     rcx, [rdi+1E0h]; hWnd
0x140051ec1  xor     r8d, r8d; wParam
0x140051ec4  mov     [rbp+57h+var_78], rax
0x140051ec8  mov     edx, 1132h; Msg
0x140051ecd  mov     eax, esi
0x140051ecf  mov     [rbp+57h+var_60], rax
0x140051ed3  call    cs:__imp_SendMessageW
0x140051ed9  mov     rcx, [rsp+130h+bstrString]; bstrString
0x140051ede  mov     [rbp+57h+var_A8], rax
0x140051ee2  call    cs:__imp_SysFreeString
0x140051ee8  xor     ecx, ecx
0x140051eea  mov     [rbp+57h+arg_0], cx
0x140051eee  mov     rcx, [rsp+130h+var_100]
0x140051ef3  mov     rdx, [rcx]
0x140051ef6  mov     rax, [rdx+40h]
0x140051efa  lea     rdx, [rbp+57h+arg_0]
0x140051efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140051f03  mov     r13d, eax
0x140051f06  test    eax, eax
0x140051f08  js      loc_140051FB4
0x140051f0e  xor     eax, eax
0x140051f10  lea     r9, [rsp+130h+var_E0]; lParam
0x140051f15  mov     [rbp+57h+var_B0], rax
0x140051f19  xorps   xmm0, xmm0
0x140051f1c  mov     rax, [rbp+57h+var_A8]
0x140051f20  mov     edx, 113Fh; Msg
0x140051f25  movups  xmmword ptr [rsp+130h+var_E0], xmm0
0x140051f2a  mov     [rsp+130h+var_E0+8], rax
0x140051f2f  movzx   eax, [rbp+57h+arg_0]
0x140051f33  neg     ax
0x140051f36  mov     dword ptr [rsp+130h+var_E0], 8
0x140051f3e  mov     eax, 1000h
0x140051f43  sbb     ecx, ecx
0x140051f45  xor     r8d, r8d; wParam
0x140051f48  and     ecx, eax
0x140051f4a  add     ecx, eax
0x140051f4c  movups  [rbp+57h+var_D0], xmm0
0x140051f50  mov     dword ptr [rbp+57h+var_D0], ecx
0x140051f53  mov     rcx, [rdi+1E0h]; hWnd
0x140051f5a  movups  [rbp+57h+var_C0], xmm0
0x140051f5e  mov     dword ptr [rbp+57h+var_D0+4], 0F000h
0x140051f65  call    cs:__imp_SendMessageW
0x140051f6b  movzx   eax, [rbp+57h+arg_0]
0x140051f6f  xor     r13d, r13d
0x140051f72  test    r12d, r12d
0x140051f75  jz      short loc_140051F7F
0x140051f77  mov     r12d, ebx
0x140051f7a  test    ax, ax
0x140051f7d  jz      short loc_140051F82
0x140051f7f  mov     r12d, r13d
0x140051f82  test    r15d, r15d
0x140051f85  jz      short loc_140051F8F
0x140051f87  mov     r15d, ebx
0x140051f8a  test    ax, ax
0x140051f8d  jnz     short loc_140051F92
0x140051f8f  mov     r15d, r13d
0x140051f92  mov     rcx, [rsp+130h+var_100]
0x140051f97  test    rcx, rcx
0x140051f9a  jz      short loc_140051FAD
0x140051f9c  mov     [rsp+130h+var_100], r13
0x140051fa1  mov     rax, [rcx]
0x140051fa4  mov     rax, [rax+10h]
0x140051fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140051fad  add     esi, ebx
0x140051faf  jmp     loc_140051E25
0x140051fb4  mov     rcx, cs:WPP_GLOBAL_Control
0x140051fbb  lea     rax, WPP_GLOBAL_Control
0x140051fc2  cmp     rcx, rax
0x140051fc5  jz      loc_1400520B9
0x140051fcb  test    byte ptr [rcx+1Ch], 8
0x140051fcf  jz      loc_1400520B9
  ... truncated ...
```
