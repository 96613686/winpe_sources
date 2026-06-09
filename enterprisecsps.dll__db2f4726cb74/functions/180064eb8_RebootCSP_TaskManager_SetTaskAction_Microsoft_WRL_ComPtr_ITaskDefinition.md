# RebootCSP::TaskManager::SetTaskAction(Microsoft::WRL::ComPtr<ITaskDefinition> &)

- ea: `0x180064eb8`
- end: `0x1800652ed`
- name: `?SetTaskAction@TaskManager@RebootCSP@@AEAAJAEAV?$ComPtr@UITaskDefinition@@@WRL@Microsoft@@@Z`
- size: `1077`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180063d94`

## callees

- `0x180008de0`
- `0x1800091b0`
- `0x18000caf4`
- `0x18000d4d4`
- `0x18000f0c8`
- `0x180019fd8`
- `0x18002031c`
- `0x1800232e4`
- `0x18002d994`
- `0x180063558`
- `0x1800637f4`
- `0x180064eb8`
- `0x180065770`
- `0x1800657d4`
- `0x180107010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800650ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800650ea`
- `OLEAUT32!__imp_SysFreeString` at `0x18006502d`
- `OLEAUT32!__imp_SysFreeString` at `0x18006518d`
- `OLEAUT32!__imp_SysFreeString` at `0x180065252`
- `OLEAUT32!__imp_SysFreeString` at `0x18006502d`
- `OLEAUT32!__imp_SysFreeString` at `0x18006518d`
- `OLEAUT32!__imp_SysFreeString` at `0x180065252`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18006509c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800650cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18006509c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800650cb`

## string_xrefs

- `0x180064f1d`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\reboot\taskmanager.cpp`
- `0x180064f6d`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\reboot\taskmanager.cpp`
- `0x180064faf`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\reboot\taskmanager.cpp`
- `0x18006506c`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\reboot\taskmanager.cpp`
- `0x1800651ca`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\reboot\taskmanager.cpp`
- `0x180065121`: `\System32\`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall RebootCSP::TaskManager::SetTaskAction(__int64 a1, __int64 *a2)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, __int64 *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, _QWORD *); // rbx
  int v9; // eax
  int v10; // eax
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64); // rdi
  const unsigned __int16 *v13; // rax
  int v14; // edi
  BSTR *v15; // rbx
  BSTR v16; // rcx
  __int64 v17; // rdx
  UINT SystemWindowsDirectoryW; // eax
  signed int LastError; // eax
  __int64 v20; // rbx
  __int64 (__fastcall *v21)(__int64); // rdi
  const unsigned __int16 *v22; // rax
  BSTR *v23; // rbx
  BSTR v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rbx
  __int64 (__fastcall *v27)(__int64); // rdi
  const unsigned __int16 *v28; // rax
  BSTR *v29; // rbx
  BSTR v30; // rcx
  __int64 v32; // [rsp+20h] [rbp-29h] BYREF
  _QWORD v33[2]; // [rsp+28h] [rbp-21h] BYREF
  void *Block; // [rsp+38h] [rbp-11h] BYREF
  __int64 v35; // [rsp+40h] [rbp-9h] BYREF
  LPWSTR lpBuffer; // [rsp+48h] [rbp-1h] BYREF
  __int64 v37; // [rsp+50h] [rbp+7h]
  _BYTE v38[32]; // [rsp+60h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v35 = 0;
  v3 = *a2;
  v4 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a2 + 136LL);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v35);
  v5 = v4(v3, &v35);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v33[0] = 0;
    v7 = v35;
    v8 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v35 + 96LL);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(v33);
    v9 = v8(v7, 0, v33);
    v6 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF9,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\taskmanager.cpp",
        (const char *)(unsigned int)v9,
        v32);
LABEL_5:
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(v33);
      goto LABEL_46;
    }
    v32 = 0;
    v10 = Microsoft::WRL::ComPtr<IAction>::As<IExecAction>(v33, &v32);
    v6 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFC,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\taskmanager.cpp",
        (const char *)(unsigned int)v10,
        v32);
LABEL_8:
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v32);
      goto LABEL_5;
    }
    v11 = v32;
    v12 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 88LL);
    v13 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    _bstr_t::_bstr_t((_bstr_t *)&Block, v13);
    v14 = v12(v11);
    v15 = (BSTR *)Block;
    if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v15 )
    {
      if ( *v15 )
      {
        SysFreeString(*v15);
        *v15 = 0;
      }
      v16 = v15[1];
      if ( v16 )
      {
        operator delete(v16);
        v15[1] = 0;
      }
      operator delete(v15);
    }
    if ( v14 >= 0 )
    {
      GetSystemWindowsDirectoryW(0, 0);
      std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>(&lpBuffer);
      std::vector<unsigned short>::resize(&lpBuffer, v17);
      SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(lpBuffer, (v37 - (__int64)lpBuffer) >> 1);
      if ( SystemWindowsDirectoryW + 1 != (v37 - (__int64)lpBuffer) >> 1 )
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        std::vector<unsigned short>::_Tidy(&lpBuffer);
        goto LABEL_8;
      }
      std::wstring::wstring(v38, lpBuffer);
      std::wstring::append(v38, L"\\System32\\");
      v20 = v32;
      v21 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 120LL);
      v22 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38);
      _bstr_t::_bstr_t((_bstr_t *)&Block, v22);
      v14 = v21(v20);
      v23 = (BSTR *)Block;
      if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v23 )
      {
        if ( *v23 )
        {
          SysFreeString(*v23);
          *v23 = 0;
        }
        v24 = v23[1];
        if ( v24 )
        {
          operator delete(v24);
          v23[1] = 0;
        }
        operator delete(v23);
      }
      if ( v14 >= 0 )
      {
        v26 = v32;
        v27 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 104LL);
        v28 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 32);
        _bstr_t::_bstr_t((_bstr_t *)&Block, v28);
        v14 = v27(v26);
        v29 = (BSTR *)Block;
        if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 4, 0xFFFFFFFF) == 1 && v29 )
        {
          if ( *v29 )
          {
            SysFreeString(*v29);
            *v29 = 0;
          }
          v30 = v29[1];
          if ( v30 )
          {
            operator delete(v30);
            v29[1] = 0;
          }
          operator delete(v29);
        }
        if ( v14 >= 0 )
        {
          std::wstring::~wstring(v38);
          std::vector<unsigned short>::_Tidy(&lpBuffer);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v32);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(v33);
          v6 = 0;
          goto LABEL_46;
        }
        v25 = 271;
      }
      else
      {
        v25 = 269;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\taskmanager.cpp",
        (const char *)(unsigned int)v14,
        v32);
      std::wstring::~wstring(v38);
      std::vector<unsigned short>::_Tidy(&lpBuffer);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFE,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\taskmanager.cpp",
        (const char *)(unsigned int)v14,
        v32);
    }
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v32);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(v33);
    v6 = v14;
    goto LABEL_46;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xF6,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\taskmanager.cpp",
    (const char *)(unsigned int)v5,
    v32);
LABEL_46:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v35);
  return v6;
}

```

## disassembly

```asm
0x180064eb8  mov     [rsp-8+arg_10], rbx
0x180064ebd  mov     [rsp-8+arg_18], rsi
0x180064ec2  push    rbp
0x180064ec3  push    rdi
0x180064ec4  push    r12
0x180064ec6  lea     rbp, [rsp-47h]
0x180064ecb  sub     rsp, 90h
0x180064ed2  mov     rax, cs:__security_cookie
0x180064ed9  xor     rax, rsp
0x180064edc  mov     [rbp+57h+var_20], rax
0x180064ee0  mov     rsi, rcx
0x180064ee3  mov     [rbp+57h+var_60], 0
0x180064eeb  mov     rdi, [rdx]
0x180064eee  mov     rax, [rdi]
0x180064ef1  mov     rbx, [rax+88h]
0x180064ef8  lea     rcx, [rbp+57h+var_60]
0x180064efc  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ
0x180064f01  lea     rdx, [rbp+57h+var_60]
0x180064f05  mov     rcx, rdi
0x180064f08  mov     rax, rbx
0x180064f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064f10  mov     ebx, eax
0x180064f12  test    eax, eax
0x180064f14  jns     short loc_180064F33
0x180064f16  mov     rcx, [rbp+5Fh]; this
0x180064f1a  mov     r9d, eax; char *
0x180064f1d  lea     r8, aOnecoreuapAdmi_58
0x180064f24  mov     edx, 0F6h; void *
0x180064f29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180064f2e  jmp     loc_1800652BD
0x180064f33  mov     [rbp+57h+var_78], 0
0x180064f3b  mov     rdi, [rbp+57h+var_60]
0x180064f3f  mov     rax, [rdi]
0x180064f42  mov     rbx, [rax+60h]
0x180064f46  lea     rcx, [rbp+57h+var_78]
0x180064f4a  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ
0x180064f4f  lea     r8, [rbp+57h+var_78]
0x180064f53  xor     edx, edx
0x180064f55  mov     rcx, rdi
0x180064f58  mov     rax, rbx
0x180064f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064f60  mov     ebx, eax
0x180064f62  test    eax, eax
0x180064f64  jns     short loc_180064F8D
0x180064f66  mov     rcx, [rbp+5Fh]; this
0x180064f6a  mov     r9d, eax; char *
0x180064f6d  lea     r8, aOnecoreuapAdmi_58
0x180064f74  mov     edx, 0F9h; void *
0x180064f79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180064f7e  nop
0x180064f7f  lea     rcx, [rbp+57h+var_78]
0x180064f83  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ
0x180064f88  jmp     loc_1800652BD
0x180064f8d  mov     [rbp+57h+var_80], 0
0x180064f95  lea     rdx, [rbp+57h+var_80]
0x180064f99  lea     rcx, [rbp+57h+var_78]
0x180064f9d  call    ??$As@UIExecAction@@@?$ComPtr@UIAction@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIExecAction@@@WRL@Microsoft@@@Details@12@@Z
0x180064fa2  mov     ebx, eax
0x180064fa4  test    eax, eax
0x180064fa6  jns     short loc_180064FCC
0x180064fa8  mov     rcx, [rbp+5Fh]; this
0x180064fac  mov     r9d, eax; char *
0x180064faf  lea     r8, aOnecoreuapAdmi_58
0x180064fb6  mov     edx, 0FCh; void *
0x180064fbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180064fc0  nop
0x180064fc1  lea     rcx, [rbp+57h+var_80]
0x180064fc5  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ
0x180064fca  jmp     short loc_180064F7F
0x180064fcc  mov     rbx, [rbp+57h+var_80]
0x180064fd0  mov     rax, [rbx]
0x180064fd3  mov     rdi, [rax+58h]
0x180064fd7  mov     rcx, rsi
0x180064fda  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ
0x180064fdf  mov     rdx, rax; unsigned __int16 *
0x180064fe2  lea     rcx, [rbp+57h+Block]; this
0x180064fe6  call    ??0_bstr_t@@QEAA@PEBG@Z
0x180064feb  nop
0x180064fec  mov     rdx, [rax]
0x180064fef  test    rdx, rdx
0x180064ff2  jz      short loc_180064FF7
0x180064ff4  mov     rdx, [rdx]
0x180064ff7  mov     rcx, rbx
0x180064ffa  mov     rax, rdi
0x180064ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065002  mov     edi, eax
0x180065004  mov     r12d, 18h
0x18006500a  mov     rbx, [rbp+57h+Block]
0x18006500e  test    rbx, rbx
0x180065011  jz      short loc_180065061
0x180065013  or      ecx, 0FFFFFFFFh
0x180065016  lock xadd [rbx+10h], ecx
0x18006501b  cmp     ecx, 1
0x18006501e  jnz     short loc_180065061
0x180065020  test    rbx, rbx
0x180065023  jz      short loc_180065061
0x180065025  mov     rcx, [rbx]; bstrString
0x180065028  test    rcx, rcx
0x18006502b  jz      short loc_180065040
0x18006502d  call    cs:__imp_SysFreeString
0x180065034  nop     dword ptr [rax+rax+00h]
0x180065039  mov     qword ptr [rbx], 0
0x180065040  mov     rcx, [rbx+8]; Block
0x180065044  test    rcx, rcx
0x180065047  jz      short loc_180065056
0x180065049  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x18006504e  mov     qword ptr [rbx+8], 0
0x180065056  mov     rdx, r12
0x180065059  mov     rcx, rbx; Block
0x18006505c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x180065061  test    edi, edi
0x180065063  jns     short loc_180065098
0x180065065  mov     rcx, [rbp+5Fh]; this
0x180065069  mov     r9d, edi; char *
0x18006506c  lea     r8, aOnecoreuapAdmi_58
0x180065073  mov     edx, 0FEh; void *
0x180065078  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x18006507d  nop
0x18006507e  lea     rcx, [rbp+57h+var_80]
0x180065082  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ
0x180065087  nop
0x180065088  lea     rcx, [rbp+57h+var_78]
0x18006508c  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ
0x180065091  mov     ebx, edi
0x180065093  jmp     loc_1800652BD
0x180065098  xor     edx, edx; uSize
0x18006509a  xor     ecx, ecx; lpBuffer
0x18006509c  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800650a3  nop     dword ptr [rax+rax+00h]
0x1800650a8  mov     edx, eax
0x1800650aa  lea     rcx, [rbp+57h+lpBuffer]
0x1800650ae  call    ??0?$vector@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@3@@std@@QEAA@XZ
0x1800650b3  nop
0x1800650b4  lea     rcx, [rbp+57h+lpBuffer]
0x1800650b8  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z
0x1800650bd  mov     rcx, [rbp+57h+lpBuffer]; lpBuffer
0x1800650c1  mov     rdx, [rbp+57h+var_50]
0x1800650c5  sub     rdx, rcx
0x1800650c8  sar     rdx, 1; uSize
0x1800650cb  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800650d2  nop     dword ptr [rax+rax+00h]
0x1800650d7  mov     rdx, [rbp+57h+var_50]
0x1800650db  sub     rdx, [rbp+57h+lpBuffer]
0x1800650df  sar     rdx, 1
0x1800650e2  lea     ecx, [rax+1]
0x1800650e5  cmp     rcx, rdx
0x1800650e8  jz      short loc_180065113
0x1800650ea  call    cs:__imp_GetLastError
0x1800650f1  nop     dword ptr [rax+rax+00h]
0x1800650f6  mov     ebx, eax
0x1800650f8  test    eax, eax
0x1800650fa  jle     short loc_180065105
0x1800650fc  movzx   ebx, ax
0x1800650ff  or      ebx, 80070000h
0x180065105  lea     rcx, [rbp+57h+lpBuffer]
0x180065109  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ
0x18006510e  jmp     loc_180064FC1
0x180065113  mov     rdx, [rbp+57h+lpBuffer]
0x180065117  lea     rcx, [rbp+57h+var_40]
0x18006511b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z
0x180065120  nop
0x180065121  lea     rdx, aSystem32
0x180065128  lea     rcx, [rbp+57h+var_40]
0x18006512c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z
0x180065131  mov     rbx, [rbp+57h+var_80]
0x180065135  mov     rax, [rbx]
0x180065138  mov     rdi, [rax+78h]
0x18006513c  lea     rcx, [rbp+57h+var_40]
0x180065140  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ
0x180065145  mov     rdx, rax; unsigned __int16 *
0x180065148  lea     rcx, [rbp+57h+Block]; this
0x18006514c  call    ??0_bstr_t@@QEAA@PEBG@Z
0x180065151  nop
0x180065152  mov     rdx, [rax]
0x180065155  test    rdx, rdx
0x180065158  jz      short loc_18006515D
0x18006515a  mov     rdx, [rdx]
0x18006515d  mov     rcx, rbx
0x180065160  mov     rax, rdi
0x180065163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065168  mov     edi, eax
0x18006516a  mov     rbx, [rbp+57h+Block]
0x18006516e  test    rbx, rbx
0x180065171  jz      short loc_1800651C1
0x180065173  or      ecx, 0FFFFFFFFh
0x180065176  lock xadd [rbx+10h], ecx
0x18006517b  cmp     ecx, 1
0x18006517e  jnz     short loc_1800651C1
0x180065180  test    rbx, rbx
0x180065183  jz      short loc_1800651C1
0x180065185  mov     rcx, [rbx]; bstrString
0x180065188  test    rcx, rcx
0x18006518b  jz      short loc_1800651A0
0x18006518d  call    cs:__imp_SysFreeString
0x180065194  nop     dword ptr [rax+rax+00h]
0x180065199  mov     qword ptr [rbx], 0
0x1800651a0  mov     rcx, [rbx+8]; Block
0x1800651a4  test    rcx, rcx
0x1800651a7  jz      short loc_1800651B6
0x1800651a9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x1800651ae  mov     qword ptr [rbx+8], 0
0x1800651b6  mov     rdx, r12
0x1800651b9  mov     rcx, rbx; Block
0x1800651bc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x1800651c1  test    edi, edi
0x1800651c3  jns     short loc_1800651F6
0x1800651c5  mov     edx, 10Dh; void *
0x1800651ca  lea     r8, aOnecoreuapAdmi_58
0x1800651d1  mov     r9d, edi; char *
0x1800651d4  mov     rcx, [rbp+5Fh]; this
0x1800651d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x1800651dd  nop
0x1800651de  lea     rcx, [rbp+57h+var_40]
0x1800651e2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x1800651e7  nop
0x1800651e8  lea     rcx, [rbp+57h+lpBuffer]
0x1800651ec  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ
0x1800651f1  jmp     loc_18006507E
0x1800651f6  mov     rbx, [rbp+57h+var_80]
0x1800651fa  mov     rax, [rbx]
0x1800651fd  mov     rdi, [rax+68h]
0x180065201  lea     rcx, [rsi+20h]
0x180065205  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ
0x18006520a  mov     rdx, rax; unsigned __int16 *
0x18006520d  lea     rcx, [rbp+57h+Block]; this
0x180065211  call    ??0_bstr_t@@QEAA@PEBG@Z
0x180065216  nop
0x180065217  mov     rdx, [rax]
0x18006521a  test    rdx, rdx
0x18006521d  jz      short loc_180065222
0x18006521f  mov     rdx, [rdx]
0x180065222  mov     rcx, rbx
0x180065225  mov     rax, rdi
0x180065228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006522d  mov     edi, eax
0x18006522f  mov     rbx, [rbp+57h+Block]
0x180065233  test    rbx, rbx
0x180065236  jz      short loc_180065286
0x180065238  or      ecx, 0FFFFFFFFh
0x18006523b  lock xadd [rbx+10h], ecx
0x180065240  cmp     ecx, 1
0x180065243  jnz     short loc_180065286
0x180065245  test    rbx, rbx
0x180065248  jz      short loc_180065286
0x18006524a  mov     rcx, [rbx]; bstrString
0x18006524d  test    rcx, rcx
0x180065250  jz      short loc_180065265
0x180065252  call    cs:__imp_SysFreeString
0x180065259  nop     dword ptr [rax+rax+00h]
0x18006525e  mov     qword ptr [rbx], 0
0x180065265  mov     rcx, [rbx+8]; Block
0x180065269  test    rcx, rcx
0x18006526c  jz      short loc_18006527B
0x18006526e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x180065273  mov     qword ptr [rbx+8], 0
0x18006527b  mov     rdx, r12
0x18006527e  mov     rcx, rbx; Block
0x180065281  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x180065286  test    edi, edi
0x180065288  jns     short loc_180065294
0x18006528a  mov     edx, 10Fh
0x18006528f  jmp     loc_1800651CA
0x180065294  lea     rcx, [rbp+57h+var_40]
0x180065298  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x18006529d  nop
0x18006529e  lea     rcx, [rbp+57h+lpBuffer]
0x1800652a2  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ
0x1800652a7  nop
0x1800652a8  lea     rcx, [rbp+57h+var_80]
0x1800652ac  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ
0x1800652b1  nop
0x1800652b2  lea     rcx, [rbp+57h+var_78]
0x1800652b6  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ
0x1800652bb  xor     ebx, ebx
0x1800652bd  lea     rcx, [rbp+57h+var_60]
0x1800652c1  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ
0x1800652c6  mov     eax, ebx
0x1800652c8  mov     rcx, [rbp+57h+var_20]
0x1800652cc  xor     rcx, rsp; StackCookie
0x1800652cf  call    __security_check_cookie
0x1800652d4  lea     r11, [rsp+0A0h+var_10]
0x1800652dc  mov     rbx, [r11+30h]
0x1800652e0  mov     rsi, [r11+38h]
0x1800652e4  mov     rsp, r11
0x1800652e7  pop     r12
0x1800652e9  pop     rdi
0x1800652ea  pop     rbp
0x1800652eb  retn
```
