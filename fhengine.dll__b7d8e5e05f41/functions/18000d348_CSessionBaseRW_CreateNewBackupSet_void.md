# CSessionBaseRW::CreateNewBackupSet(void)

- ea: `0x18000d348`
- end: `0x18000d4ec`
- name: `?CreateNewBackupSet@CSessionBaseRW@@IEAAJXZ`
- size: `420`
- prototype: `__int64 __fastcall(CSessionBaseRW *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000eed8`
- `0x18001baf8`

## callees

- `0x180007818`
- `0x1800094ec`
- `0x18000d348`
- `0x180031680`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d394`
- `KERNEL32!GetLastError` at `0x18000d394`
- `KERNEL32!GetSystemTime` at `0x18000d37a`
- `KERNEL32!GetSystemTime` at `0x18000d37a`
- `KERNEL32!SystemTimeToFileTime` at `0x18000d38a`
- `KERNEL32!SystemTimeToFileTime` at `0x18000d38a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d480`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d480`

## pseudocode

```c
__int64 __fastcall CSessionBaseRW::CreateNewBackupSet(CSessionBaseRW *this)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  __int64 v4; // rbx
  __int64 (__fastcall *v5)(__int64, _QWORD, char *, __int64); // r14
  ATL::CComBSTR *v6; // rax
  BSTR bstrString; // [rsp+30h] [rbp-58h] BYREF
  struct _FILETIME FileTime; // [rsp+38h] [rbp-50h] BYREF
  int v10; // [rsp+40h] [rbp-48h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-40h] BYREF

  SystemTime = 0;
  FileTime = 0;
  GetSystemTime(&SystemTime);
  if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v3 = (*(__int64 (__fastcall **)(_QWORD, struct _FILETIME, char *))(**((_QWORD **)this + 2) + 80LL))(
             *((_QWORD *)this + 2),
             FileTime,
             (char *)this + 36);
      if ( (v3 & 0x80000000) == 0 )
      {
        *((struct _FILETIME *)this + 5) = FileTime;
        v4 = *((_QWORD *)this + 2);
        v5 = *(__int64 (__fastcall **)(__int64, _QWORD, char *, __int64))(*(_QWORD *)v4 + 168LL);
        v6 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"LastBSet");
        v3 = v5(v4, *(_QWORD *)v6, (char *)this + 36, 4);
        SysFreeString(bstrString);
        if ( (v3 & 0x80000000) == 0 )
        {
          if ( *((_DWORD *)this + 12) == -1 )
            *((_DWORD *)this + 12) = *((_DWORD *)this + 9) - 1;
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v3);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v3);
      }
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v10) )
      {
        LODWORD(bstrString) = v10;
        if ( v10 >= 0 )
        {
          v3 = (unsigned int)bstrString;
          __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000D4CF);
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              47,
              &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
              (unsigned int)v10);
          v3 = (unsigned int)bstrString;
          __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000D4CD);
        }
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x18000d348  push    rbx
0x18000d34a  push    rsi
0x18000d34b  push    rdi
0x18000d34c  push    r14
0x18000d34e  sub     rsp, 68h
0x18000d352  mov     rax, cs:__security_cookie
0x18000d359  xor     rax, rsp
0x18000d35c  mov     [rsp+88h+var_30], rax
0x18000d361  mov     rdi, rcx
0x18000d364  xorps   xmm0, xmm0
0x18000d367  movups  xmmword ptr [rsp+88h+SystemTime.wYear], xmm0
0x18000d36c  mov     qword ptr [rsp+88h+FileTime.dwLowDateTime], 0
0x18000d375  lea     rcx, [rsp+88h+SystemTime]; lpSystemTime
0x18000d37a  call    cs:__imp_GetSystemTime
0x18000d380  lea     rdx, [rsp+88h+FileTime]; lpFileTime
0x18000d385  lea     rcx, [rsp+88h+SystemTime]; lpSystemTime
0x18000d38a  call    cs:__imp_SystemTimeToFileTime
0x18000d390  test    eax, eax
0x18000d392  jnz     short loc_18000D3E0
0x18000d394  call    cs:__imp_GetLastError
0x18000d39a  mov     ebx, eax
0x18000d39c  test    eax, eax
0x18000d39e  jle     short loc_18000D3A9
0x18000d3a0  movzx   ebx, ax
0x18000d3a3  or      ebx, 80070000h
0x18000d3a9  lea     rax, WPP_GLOBAL_Control
0x18000d3b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3b7  cmp     rcx, rax
0x18000d3ba  jz      short loc_18000D3DB
0x18000d3bc  test    byte ptr [rcx+1Ch], 1
0x18000d3c0  jz      short loc_18000D3DB
0x18000d3c2  mov     edx, 2Ch ; ','
0x18000d3c7  mov     r9d, ebx
0x18000d3ca  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000d3d1  mov     rcx, [rcx+10h]
0x18000d3d5  call    WPP_SF_d
0x18000d3da  nop
0x18000d3db  jmp     loc_18000D4D3
0x18000d3e0  mov     rcx, [rdi+10h]
0x18000d3e4  lea     rsi, [rdi+24h]
0x18000d3e8  mov     rax, [rcx]
0x18000d3eb  mov     r8, rsi
0x18000d3ee  mov     rdx, qword ptr [rsp+88h+FileTime.dwLowDateTime]
0x18000d3f3  mov     rax, [rax+50h]
0x18000d3f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3fc  mov     ebx, eax
0x18000d3fe  test    eax, eax
0x18000d400  jns     short loc_18000D439
0x18000d402  lea     rax, WPP_GLOBAL_Control
0x18000d409  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d410  cmp     rcx, rax
0x18000d413  jz      short loc_18000D434
0x18000d415  test    byte ptr [rcx+1Ch], 1
0x18000d419  jz      short loc_18000D434
0x18000d41b  mov     edx, 2Dh ; '-'
0x18000d420  mov     r9d, ebx
0x18000d423  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000d42a  mov     rcx, [rcx+10h]
0x18000d42e  call    WPP_SF_d
0x18000d433  nop
0x18000d434  jmp     loc_18000D4D3
0x18000d439  mov     rax, qword ptr [rsp+88h+FileTime.dwLowDateTime]
0x18000d43e  mov     [rdi+28h], rax
0x18000d442  mov     rbx, [rdi+10h]
0x18000d446  mov     rax, [rbx]
0x18000d449  mov     r14, [rax+0A8h]
0x18000d450  lea     rdx, aLastbset; "LastBSet"
0x18000d457  lea     rcx, [rsp+88h+bstrString]; this
0x18000d45c  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000d461  nop
0x18000d462  mov     r9d, 4
0x18000d468  mov     r8, rsi
0x18000d46b  mov     rdx, [rax]
0x18000d46e  mov     rcx, rbx
0x18000d471  mov     rax, r14
0x18000d474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d479  mov     ebx, eax
0x18000d47b  mov     rcx, [rsp+88h+bstrString]; bstrString
0x18000d480  call    cs:__imp_SysFreeString
0x18000d486  test    ebx, ebx
0x18000d488  jns     short loc_18000D4BE
0x18000d48a  lea     rax, WPP_GLOBAL_Control
0x18000d491  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d498  cmp     rcx, rax
0x18000d49b  jz      short loc_18000D4BC
0x18000d49d  test    byte ptr [rcx+1Ch], 1
0x18000d4a1  jz      short loc_18000D4BC
0x18000d4a3  mov     edx, 2Eh ; '.'
0x18000d4a8  mov     r9d, ebx
0x18000d4ab  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000d4b2  mov     rcx, [rcx+10h]
0x18000d4b6  call    WPP_SF_d
0x18000d4bb  nop
0x18000d4bc  jmp     short loc_18000D4D3
0x18000d4be  cmp     dword ptr [rdi+30h], 0FFFFFFFFh
0x18000d4c2  jnz     short loc_18000D4CB
0x18000d4c4  mov     eax, [rsi]
0x18000d4c6  dec     eax
0x18000d4c8  mov     [rdi+30h], eax
0x18000d4cb  jmp     short loc_18000D4D3
0x18000d4cd  jmp     short $+2
0x18000d4cf  mov     ebx, dword ptr [rsp+88h+bstrString]
0x18000d4d3  mov     eax, ebx
0x18000d4d5  mov     rcx, [rsp+88h+var_30]
0x18000d4da  xor     rcx, rsp; StackCookie
0x18000d4dd  call    __security_check_cookie
0x18000d4e2  add     rsp, 68h
0x18000d4e6  pop     r14
0x18000d4e8  pop     rdi
0x18000d4e9  pop     rsi
0x18000d4ea  pop     rbx
0x18000d4eb  retn
```
