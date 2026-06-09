# OpenDSLFileInternal(HWND__ *,HINSTANCE__ *,ushort *,int)

- ea: `0x18004de10`
- end: `0x18004e35a`
- name: `?OpenDSLFileInternal@@YAXPEAUHWND__@@PEAUHINSTANCE__@@PEAGH@Z`
- size: `1354`
- prototype: `void __fastcall(HWND, HINSTANCE, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180038500`

## callees

- `0x180013870`
- `0x180029560`
- `0x18002ec0c`
- `0x18004dd1c`
- `0x18004de10`
- `0x18007e700`
- `0x18007e7c0`
- `0x180087010`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18004df9b`
- `KERNEL32!CreateFileW` at `0x18004df9b`
- `KERNEL32!GetLastError` at `0x18004dfa7`
- `KERNEL32!GetLastError` at `0x18004dfa7`
- `KERNEL32!SetLastError` at `0x18004df78`
- `KERNEL32!SetLastError` at `0x18004df78`
- `KERNEL32!CloseHandle` at `0x18004dfbc`
- `KERNEL32!CloseHandle` at `0x18004dfbc`
- `ole32!CoUninitialize` at `0x18004e0ee`
- `ole32!CoUninitialize` at `0x18004e0ee`
- `ole32!CoInitialize` at `0x18004de69`
- `ole32!CoInitialize` at `0x18004de69`
- `ole32!CoTaskMemFree` at `0x18004df66`
- `ole32!CoTaskMemFree` at `0x18004e092`
- `ole32!CoTaskMemFree` at `0x18004df66`
- `ole32!CoTaskMemFree` at `0x18004e092`
- `ole32!CoCreateInstance` at `0x18004de8d`
- `ole32!CoCreateInstance` at `0x18004debd`
- `ole32!CoCreateInstance` at `0x18004de8d`
- `ole32!CoCreateInstance` at `0x18004debd`

## string_xrefs

- `0x18004df03`: `<OpenDSLFileInternal|OLEDB|ERR> `
- `0x18004e016`: `<OpenDSLFileInternal|OLEDB|ERR> `
- `0x18004e150`: `<OpenDSLFileInternal|OLEDB|ERR> `
- `0x18004e191`: `<OpenDSLFileInternal|OLEDB|ERR> `
- `0x18004e1f1`: `<OpenDSLFileInternal|OLEDB|ERR> `
- `0x18004e20f`: `<OpenDSLFileInternal|OLEDB|ERR> `
- `0x18004e26f`: `<OpenDSLFileInternal|OLEDB|ERR> `
- `0x18004e2cf`: `<OpenDSLFileInternal|OLEDB|ERR> `
- `0x18004e2ed`: `<OpenDSLFileInternal|OLEDB|ERR> `
- `0x18004e1ac`: `<OpenDSLFileInternal|Trace|HR> `
- `0x18004e22a`: `<OpenDSLFileInternal|Trace|HR> `
- `0x18004e28a`: `<OpenDSLFileInternal|Trace|HR> `
- `0x18004e308`: `<OpenDSLFileInternal|Trace|HR> `

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
void __fastcall OpenDSLFileInternal(HWND a1, HINSTANCE a2, unsigned __int16 *a3)
{
  HRESULT v5; // eax
  HRESULT v6; // eax
  HRESULT v7; // esi
  int v8; // eax
  unsigned int v9; // esi
  int v10; // esi
  unsigned int v11; // esi
  HANDLE FileW; // rax
  int v13; // esi
  __int64 v14; // r8
  int v15; // esi
  int v16; // eax
  LPVOID pv; // [rsp+58h] [rbp-10A0h] BYREF
  int v18; // [rsp+60h] [rbp-1098h]
  LPVOID ppv; // [rsp+68h] [rbp-1090h] BYREF
  __int64 v20; // [rsp+70h] [rbp-1088h] BYREF
  LPVOID v21; // [rsp+78h] [rbp-1080h] BYREF
  HRESULT pExceptionObject; // [rsp+80h] [rbp-1078h] BYREF
  HRESULT v23; // [rsp+84h] [rbp-1074h] BYREF
  unsigned int v24; // [rsp+88h] [rbp-1070h] BYREF
  int v25; // [rsp+8Ch] [rbp-106Ch] BYREF
  int v26; // [rsp+90h] [rbp-1068h] BYREF
  int v27; // [rsp+94h] [rbp-1064h] BYREF
  int v28; // [rsp+98h] [rbp-1060h] BYREF
  unsigned __int16 *v29; // [rsp+A0h] [rbp-1058h]

  v29 = a3;
  ppv = 0;
  v21 = 0;
  v20 = 0;
  pv = 0;
  v18 = 0;
  CoInitialize(0);
  v5 = CoCreateInstance(&CLSID_MSDAINITIALIZE, 0, 1u, &IID_IDataInitialize, &ppv);
  if ( v5 < 0 )
  {
    v18 = 1;
    pExceptionObject = v5;
    throw (long *)&pExceptionObject;
  }
  v6 = CoCreateInstance(&CLSID_DataLinks, 0, 1u, &IID_IDBPromptInitialize, &v21);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(v6, L"<OpenDSLFileInternal|OLEDB|ERR> ", 0x5Au);
    v18 = 1;
    v23 = v7;
    throw (long *)&v23;
  }
  v8 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, LPVOID *))(*(_QWORD *)ppv + 56LL))(ppv, a3, &pv);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(v8, L"<OpenDSLFileInternal|OLEDB|ERR> ", 0x66u);
    if ( !(unsigned int)IsFileEmpty(a3) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v9, L"<OpenDSLFileInternal|OLEDB|ERR> ", 0x68u);
        if ( (bidGblFlags & 2) != 0 )
          v9 = bidTraceHR(off_1800C83D0[0], 106505, L"<OpenDSLFileInternal|Trace|HR> ", v9);
      }
      v24 = v9;
      throw (long *)&v24;
    }
  }
  v10 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, LPVOID, GUID *, __int64 *))(*(_QWORD *)ppv + 24LL))(
          ppv,
          0,
          23,
          pv,
          &IID_IDBProperties,
          &v20);
  if ( v10 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(v10, L"<OpenDSLFileInternal|OLEDB|ERR> ", 0x77u);
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v10, L"<OpenDSLFileInternal|OLEDB|ERR> ", 0x77u);
        if ( (bidGblFlags & 2) != 0 )
          v10 = bidTraceHR(off_1800C83D0[0], 121865, L"<OpenDSLFileInternal|Trace|HR> ", (unsigned int)v10);
      }
    }
    v25 = v10;
    throw (long *)&v25;
  }
  CoTaskMemFree(pv);
  pv = 0;
  v11 = 66;
  SetLastError(0);
  FileW = CreateFileW(a3, 0x40000000u, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    if ( GetLastError() == 5 )
      v11 = 322;
  }
  else
  {
    CloseHandle(FileW);
  }
  v13 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, HWND, _QWORD, _DWORD, _QWORD, _QWORD, GUID *, __int64 *))(*(_QWORD *)v21 + 24LL))(
          v21,
          0,
          a1,
          v11,
          0,
          0,
          0,
          &IID_IDBProperties,
          &v20);
  if ( v13 == -2147217842 )
  {
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(-2147217842, L"<OpenDSLFileInternal|OLEDB|ERR> ", 0x9Bu);
  }
  else
  {
    if ( v13 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v13, L"<OpenDSLFileInternal|OLEDB|ERR> ", 0xA0u);
        if ( (bidGblFlags & 2) != 0 )
          v13 = bidTraceHR(off_1800C83D0[0], 163849, L"<OpenDSLFileInternal|Trace|HR> ", (unsigned int)v13);
      }
      v26 = v13;
      throw (long *)&v26;
    }
    LOBYTE(v14) = 1;
    v15 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, LPVOID *))(*(_QWORD *)ppv + 32LL))(ppv, v20, v14, &pv);
    if ( v15 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v15, L"<OpenDSLFileInternal|OLEDB|ERR> ", 0xA8u);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v15, L"<OpenDSLFileInternal|OLEDB|ERR> ", 0xA8u);
          if ( (bidGblFlags & 2) != 0 )
            v15 = bidTraceHR(off_1800C83D0[0], 172041, L"<OpenDSLFileInternal|Trace|HR> ", (unsigned int)v15);
        }
      }
      v27 = v15;
      throw (long *)&v27;
    }
    v16 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, LPVOID, __int64))(*(_QWORD *)ppv + 64LL))(
            ppv,
            a3,
            pv,
            4);
    if ( v16 < 0 )
    {
      v28 = v16;
      throw (long *)&v28;
    }
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  CoUninitialize();
}

```

## disassembly

```asm
0x18004de10  mov     [rsp+arg_8], rbx
0x18004de15  mov     [rsp+arg_18], rsi
0x18004de1a  push    r13
0x18004de1c  push    r14
0x18004de1e  push    r15
0x18004de20  mov     eax, 10E0h
0x18004de25  call    _alloca_probe
0x18004de2a  sub     rsp, rax
0x18004de2d  mov     rax, cs:__security_cookie
0x18004de34  xor     rax, rsp
0x18004de37  mov     [rsp+10F8h+var_28], rax
0x18004de3f  mov     r14, r8
0x18004de42  mov     r15, rcx
0x18004de45  mov     [rsp+10F8h+var_1058], r8
0x18004de4d  xor     ebx, ebx
0x18004de4f  mov     [rsp+10F8h+var_1090], rbx
0x18004de54  mov     [rsp+10F8h+var_1080], rbx
0x18004de59  mov     [rsp+10F8h+var_1088], rbx
0x18004de5e  mov     [rsp+10F8h+pv], rbx
0x18004de63  mov     [rsp+10F8h+var_1098], ebx
0x18004de67  xor     ecx, ecx; pvReserved
0x18004de69  call    cs:__imp_CoInitialize
0x18004de6f  lea     rax, [rsp+10F8h+var_1090]
0x18004de74  mov     [rsp+10F8h+ppv], rax; ppv
0x18004de79  lea     r9, IID_IDataInitialize; riid
0x18004de80  xor     edx, edx; pUnkOuter
0x18004de82  lea     r8d, [rbx+1]; dwClsContext
0x18004de86  lea     rcx, CLSID_MSDAINITIALIZE; rclsid
0x18004de8d  call    cs:__imp_CoCreateInstance
0x18004de93  mov     [rsp+10F8h+var_10A8], eax
0x18004de97  test    eax, eax
0x18004de99  js      loc_18004E11E
0x18004de9f  lea     rax, [rsp+10F8h+var_1080]
0x18004dea4  mov     [rsp+10F8h+ppv], rax; ppv
0x18004dea9  lea     r9, IID_IDBPromptInitialize; riid
0x18004deb0  xor     edx, edx; pUnkOuter
0x18004deb2  lea     r8d, [rdx+1]; dwClsContext
0x18004deb6  lea     rcx, CLSID_DataLinks; rclsid
0x18004debd  call    cs:__imp_CoCreateInstance
0x18004dec3  mov     esi, eax
0x18004dec5  mov     [rsp+10F8h+var_10A8], eax
0x18004dec9  test    eax, eax
0x18004decb  js      loc_18004E141
0x18004ded1  mov     rcx, [rsp+10F8h+var_1090]
0x18004ded6  mov     rax, [rcx]
0x18004ded9  lea     r8, [rsp+10F8h+pv]
0x18004dede  mov     rdx, r14
0x18004dee1  mov     rax, [rax+38h]
0x18004dee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004deea  mov     esi, eax
0x18004deec  mov     [rsp+10F8h+var_10A8], eax
0x18004def0  test    eax, eax
0x18004def2  jns     short loc_18004DF21
0x18004def4  test    byte ptr cs:_bidGblFlags, 2
0x18004defb  jz      short loc_18004DF11
0x18004defd  mov     r8d, 66h ; 'f'; unsigned int
0x18004df03  lea     rdx, aOpendslfileint; "<OpenDSLFileInternal|OLEDB|ERR> "
0x18004df0a  mov     ecx, eax; int
0x18004df0c  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004df11  mov     rcx, r14; unsigned __int16 *
0x18004df14  call    ?IsFileEmpty@@YAHPEBG@Z; IsFileEmpty(ushort const *)
0x18004df19  test    eax, eax
0x18004df1b  jz      loc_18004E181
0x18004df21  mov     rcx, [rsp+10F8h+var_1090]
0x18004df26  mov     rax, [rcx]
0x18004df29  lea     rdx, [rsp+10F8h+var_1088]
0x18004df2e  mov     qword ptr [rsp+10F8h+dwFlagsAndAttributes], rdx
0x18004df33  lea     r13, IID_IDBProperties
0x18004df3a  mov     [rsp+10F8h+ppv], r13
0x18004df3f  mov     r9, [rsp+10F8h+pv]
0x18004df44  xor     edx, edx
0x18004df46  lea     r8d, [rdx+17h]
0x18004df4a  mov     rax, [rax+18h]
0x18004df4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df53  mov     esi, eax
0x18004df55  mov     [rsp+10F8h+var_10A8], eax
0x18004df59  test    eax, eax
0x18004df5b  js      loc_18004E1E1
0x18004df61  mov     rcx, [rsp+10F8h+pv]; pv
0x18004df66  call    cs:__imp_CoTaskMemFree
0x18004df6c  mov     [rsp+10F8h+pv], rbx
0x18004df71  mov     esi, 42h ; 'B'
0x18004df76  xor     ecx, ecx; dwErrCode
0x18004df78  call    cs:__imp_SetLastError
0x18004df7e  mov     [rsp+10F8h+hTemplateFile], rbx; hTemplateFile
0x18004df83  mov     [rsp+10F8h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18004df87  lea     r8d, [rsi-3Fh]; dwShareMode
0x18004df8b  mov     dword ptr [rsp+10F8h+ppv], r8d; dwCreationDisposition
0x18004df90  xor     r9d, r9d; lpSecurityAttributes
0x18004df93  mov     edx, 40000000h; dwDesiredAccess
0x18004df98  mov     rcx, r14; lpFileName
0x18004df9b  call    cs:__imp_CreateFileW
0x18004dfa1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004dfa5  jnz     short loc_18004DFB9
0x18004dfa7  call    cs:__imp_GetLastError
0x18004dfad  cmp     eax, 5
0x18004dfb0  jnz     short loc_18004DFC2
0x18004dfb2  mov     esi, 142h
0x18004dfb7  jmp     short loc_18004DFC2
0x18004dfb9  mov     rcx, rax; hObject
0x18004dfbc  call    cs:__imp_CloseHandle
0x18004dfc2  mov     rcx, [rsp+10F8h+var_1080]
0x18004dfc7  mov     rax, [rcx]
0x18004dfca  lea     rdx, [rsp+10F8h+var_1088]
0x18004dfcf  mov     [rsp+10F8h+var_10B8], rdx
0x18004dfd4  mov     [rsp+10F8h+var_10C0], r13
0x18004dfd9  mov     [rsp+10F8h+hTemplateFile], rbx
0x18004dfde  mov     qword ptr [rsp+10F8h+dwFlagsAndAttributes], rbx
0x18004dfe3  mov     dword ptr [rsp+10F8h+ppv], ebx
0x18004dfe7  mov     r9d, esi
0x18004dfea  mov     r8, r15
0x18004dfed  xor     edx, edx
0x18004dfef  mov     rax, [rax+18h]
0x18004dff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dff8  mov     esi, eax
0x18004dffa  mov     [rsp+10F8h+var_10A8], eax
0x18004dffe  mov     ecx, 80040E4Eh; int
0x18004e003  cmp     eax, ecx
0x18004e005  jnz     short loc_18004E025
0x18004e007  test    byte ptr cs:_bidGblFlags, 2
0x18004e00e  jz      short loc_18004E023
0x18004e010  mov     r8d, 9Bh; unsigned int
0x18004e016  lea     rdx, aOpendslfileint; "<OpenDSLFileInternal|OLEDB|ERR> "
0x18004e01d  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004e022  nop
0x18004e023  jmp     short loc_18004E088
0x18004e025  test    esi, esi
0x18004e027  js      loc_18004E25F
0x18004e02d  mov     rcx, [rsp+10F8h+var_1090]
0x18004e032  mov     rax, [rcx]
0x18004e035  lea     r9, [rsp+10F8h+pv]
0x18004e03a  mov     r8b, 1
0x18004e03d  mov     rdx, [rsp+10F8h+var_1088]
0x18004e042  mov     rax, [rax+20h]
0x18004e046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e04b  mov     esi, eax
0x18004e04d  mov     [rsp+10F8h+var_10A8], eax
0x18004e051  test    eax, eax
0x18004e053  js      loc_18004E2BF
0x18004e059  mov     rcx, [rsp+10F8h+var_1090]
0x18004e05e  mov     rax, [rcx]
0x18004e061  mov     r9d, 4
0x18004e067  mov     r8, [rsp+10F8h+pv]
0x18004e06c  mov     rdx, r14
0x18004e06f  mov     rax, [rax+40h]
0x18004e073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e078  mov     [rsp+10F8h+var_10A8], eax
0x18004e07c  test    eax, eax
0x18004e07e  js      loc_18004E33D
0x18004e084  jmp     short loc_18004E088
0x18004e086  xor     ebx, ebx
0x18004e088  mov     rcx, [rsp+10F8h+pv]; pv
0x18004e08d  test    rcx, rcx
0x18004e090  jz      short loc_18004E09D
0x18004e092  call    cs:__imp_CoTaskMemFree
0x18004e098  mov     [rsp+10F8h+pv], rbx
0x18004e09d  mov     rcx, [rsp+10F8h+var_1088]
0x18004e0a2  test    rcx, rcx
0x18004e0a5  jz      short loc_18004E0B8
0x18004e0a7  mov     rax, [rcx]
0x18004e0aa  mov     rax, [rax+10h]
0x18004e0ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0b3  mov     [rsp+10F8h+var_1088], rbx
0x18004e0b8  mov     rcx, [rsp+10F8h+var_1090]
0x18004e0bd  test    rcx, rcx
0x18004e0c0  jz      short loc_18004E0D3
0x18004e0c2  mov     rax, [rcx]
0x18004e0c5  mov     rax, [rax+10h]
0x18004e0c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0ce  mov     [rsp+10F8h+var_1090], rbx
0x18004e0d3  mov     rcx, [rsp+10F8h+var_1080]
0x18004e0d8  test    rcx, rcx
0x18004e0db  jz      short loc_18004E0EE
0x18004e0dd  mov     rax, [rcx]
0x18004e0e0  mov     rax, [rax+10h]
0x18004e0e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0e9  mov     [rsp+10F8h+var_1080], rbx
0x18004e0ee  call    cs:__imp_CoUninitialize
0x18004e0f4  mov     rcx, [rsp+10F8h+var_28]
0x18004e0fc  xor     rcx, rsp; StackCookie
0x18004e0ff  call    __security_check_cookie
0x18004e104  lea     r11, [rsp+10F8h+var_18]
0x18004e10c  mov     rbx, [r11+28h]
0x18004e110  mov     rsi, [r11+38h]
0x18004e114  mov     rsp, r11
0x18004e117  pop     r15
0x18004e119  pop     r14
0x18004e11b  pop     r13
0x18004e11d  retn
0x18004e11e  mov     [rsp+10F8h+var_1098], 1
0x18004e126  mov     [rsp+10F8h+pExceptionObject], eax
0x18004e12d  lea     rdx, _TI1J; pThrowInfo
0x18004e134  lea     rcx, [rsp+10F8h+pExceptionObject]; pExceptionObject
0x18004e13c  call    _CxxThrowException_0
0x18004e141  test    byte ptr cs:_bidGblFlags, 2
0x18004e148  jz      short loc_18004E15E
0x18004e14a  mov     r8d, 5Ah ; 'Z'; unsigned int
0x18004e150  lea     rdx, aOpendslfileint; "<OpenDSLFileInternal|OLEDB|ERR> "
0x18004e157  mov     ecx, eax; int
0x18004e159  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004e15e  mov     [rsp+10F8h+var_1098], 1
0x18004e166  mov     [rsp+10F8h+var_1074], esi
0x18004e16d  lea     rdx, _TI1J; pThrowInfo
0x18004e174  lea     rcx, [rsp+10F8h+var_1074]; pExceptionObject
0x18004e17c  call    _CxxThrowException_0
0x18004e181  mov     eax, cs:_bidGblFlags
0x18004e187  test    al, 2
0x18004e189  jz      short loc_18004E1C6
0x18004e18b  mov     r8d, 68h ; 'h'; unsigned int
0x18004e191  lea     rdx, aOpendslfileint; "<OpenDSLFileInternal|OLEDB|ERR> "
0x18004e198  mov     ecx, esi; int
0x18004e19a  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004e19f  mov     eax, cs:_bidGblFlags
0x18004e1a5  test    al, 2
0x18004e1a7  jz      short loc_18004E1C6
0x18004e1a9  mov     r9d, esi
0x18004e1ac  lea     r8, aOpendslfileint_0; "<OpenDSLFileInternal|Trace|HR> "
0x18004e1b3  mov     edx, 1A009h
0x18004e1b8  mov     rcx, cs:off_1800C83D0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004e1bf  call    _bidTraceHR
0x18004e1c4  mov     esi, eax
0x18004e1c6  mov     [rsp+10F8h+var_1070], esi
0x18004e1cd  lea     rdx, _TI1J; pThrowInfo
0x18004e1d4  lea     rcx, [rsp+10F8h+var_1070]; pExceptionObject
0x18004e1dc  call    _CxxThrowException_0
0x18004e1e1  mov     eax, cs:_bidGblFlags
0x18004e1e7  test    al, 2
0x18004e1e9  jz      short loc_18004E244
0x18004e1eb  mov     r8d, 77h ; 'w'; unsigned int
0x18004e1f1  lea     rdx, aOpendslfileint; "<OpenDSLFileInternal|OLEDB|ERR> "
0x18004e1f8  mov     ecx, esi; int
0x18004e1fa  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004e1ff  mov     eax, cs:_bidGblFlags
0x18004e205  test    al, 2
0x18004e207  jz      short loc_18004E244
0x18004e209  mov     r8d, 77h ; 'w'; unsigned int
0x18004e20f  lea     rdx, aOpendslfileint; "<OpenDSLFileInternal|OLEDB|ERR> "
0x18004e216  mov     ecx, esi; int
0x18004e218  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004e21d  mov     eax, cs:_bidGblFlags
0x18004e223  test    al, 2
0x18004e225  jz      short loc_18004E244
0x18004e227  mov     r9d, esi
0x18004e22a  lea     r8, aOpendslfileint_0; "<OpenDSLFileInternal|Trace|HR> "
0x18004e231  mov     edx, 1DC09h
0x18004e236  mov     rcx, cs:off_1800C83D0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004e23d  call    _bidTraceHR
0x18004e242  mov     esi, eax
0x18004e244  mov     [rsp+10F8h+var_106C], esi
0x18004e24b  lea     rdx, _TI1J; pThrowInfo
0x18004e252  lea     rcx, [rsp+10F8h+var_106C]; pExceptionObject
0x18004e25a  call    _CxxThrowException_0
0x18004e25f  mov     eax, cs:_bidGblFlags
0x18004e265  test    al, 2
0x18004e267  jz      short loc_18004E2A4
0x18004e269  mov     r8d, 0A0h; unsigned int
0x18004e26f  lea     rdx, aOpendslfileint; "<OpenDSLFileInternal|OLEDB|ERR> "
0x18004e276  mov     ecx, esi; int
0x18004e278  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004e27d  mov     eax, cs:_bidGblFlags
0x18004e283  test    al, 2
0x18004e285  jz      short loc_18004E2A4
0x18004e287  mov     r9d, esi
0x18004e28a  lea     r8, aOpendslfileint_0; "<OpenDSLFileInternal|Trace|HR> "
0x18004e291  mov     edx, 28009h
0x18004e296  mov     rcx, cs:off_1800C83D0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004e29d  call    _bidTraceHR
0x18004e2a2  mov     esi, eax
0x18004e2a4  mov     [rsp+10F8h+var_1068], esi
0x18004e2ab  lea     rdx, _TI1J; pThrowInfo
0x18004e2b2  lea     rcx, [rsp+10F8h+var_1068]; pExceptionObject
0x18004e2ba  call    _CxxThrowException_0
0x18004e2bf  mov     eax, cs:_bidGblFlags
0x18004e2c5  test    al, 2
0x18004e2c7  jz      short loc_18004E322
0x18004e2c9  mov     r8d, 0A8h; unsigned int
0x18004e2cf  lea     rdx, aOpendslfileint; "<OpenDSLFileInternal|OLEDB|ERR> "
0x18004e2d6  mov     ecx, esi; int
0x18004e2d8  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004e2dd  mov     eax, cs:_bidGblFlags
0x18004e2e3  test    al, 2
0x18004e2e5  jz      short loc_18004E322
0x18004e2e7  mov     r8d, 0A8h; unsigned int
0x18004e2ed  lea     rdx, aOpendslfileint; "<OpenDSLFileInternal|OLEDB|ERR> "
0x18004e2f4  mov     ecx, esi; int
0x18004e2f6  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004e2fb  mov     eax, cs:_bidGblFlags
0x18004e301  test    al, 2
0x18004e303  jz      short loc_18004E322
0x18004e305  mov     r9d, esi
0x18004e308  lea     r8, aOpendslfileint_0; "<OpenDSLFileInternal|Trace|HR> "
0x18004e30f  mov     edx, 2A009h
0x18004e314  mov     rcx, cs:off_1800C83D0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004e31b  call    _bidTraceHR
0x18004e320  mov     esi, eax
0x18004e322  mov     [rsp+10F8h+var_1064], esi
0x18004e329  lea     rdx, _TI1J; pThrowInfo
0x18004e330  lea     rcx, [rsp+10F8h+var_1064]; pExceptionObject
0x18004e338  call    _CxxThrowException_0
0x18004e33d  mov     [rsp+10F8h+var_1060], eax
  ... truncated ...
```
