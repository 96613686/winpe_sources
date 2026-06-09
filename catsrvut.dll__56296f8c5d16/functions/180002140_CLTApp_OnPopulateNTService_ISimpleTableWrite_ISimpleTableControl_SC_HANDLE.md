# CLTApp::OnPopulateNTService(ISimpleTableWrite *,ISimpleTableControl *,SC_HANDLE__ * *)

- ea: `0x180002140`
- end: `0x18000239f`
- name: `?OnPopulateNTService@CLTApp@@AEAAJPEAUISimpleTableWrite@@PEAUISimpleTableControl@@PEAPEAUSC_HANDLE__@@@Z`
- size: `607`
- prototype: `__int64 __fastcall(CLTApp *__hidden this, struct ISimpleTableWrite *, struct ISimpleTableControl *, struct SC_HANDLE__ **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180001f60`

## callees

- `0x180002140`
- `0x180055880`
- `0x180055940`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002321`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800022ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002321`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800022aa`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800022aa`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180002278`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180002278`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800021cc`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800021cc`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800021ea`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180002239`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800021ea`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180002239`

## pseudocode

```c
__int64 __fastcall CLTApp::OnPopulateNTService(
        CLTApp *this,
        struct ISimpleTableWrite *a2,
        struct ISimpleTableControl *a3,
        struct SC_HANDLE__ **a4)
{
  __int64 v4; // rax
  SC_HANDLE v5; // rbx
  __int64 (__fastcall *v8)(struct ISimpleTableWrite *, __int64, _QWORD, _QWORD, _QWORD, DWORD *); // rax
  signed int v9; // edi
  const WCHAR *v10; // rdx
  SC_HANDLE v11; // rax
  SC_HANDLE v12; // rsi
  unsigned __int64 v13; // rax
  void *v14; // rsp
  LPWSTR lpServiceStartName; // r12
  signed int v17; // eax
  signed int v18; // eax
  signed int LastError; // eax
  signed int v20; // eax
  struct _QUERY_SERVICE_CONFIGW pcbBytesNeeded; // [rsp+40h] [rbp+0h] BYREF

  v4 = *(_QWORD *)a2;
  v5 = *a4;
  pcbBytesNeeded.dwServiceType = 0;
  v8 = *(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, _QWORD, _QWORD, DWORD *))(v4 + 152);
  *(_QWORD *)&pcbBytesNeeded.dwErrorControl = 0;
  v9 = v8(a2, 6, 0, 0, 0, &pcbBytesNeeded.dwErrorControl);
  if ( v9 < 0 )
    goto LABEL_14;
  v10 = *(const WCHAR **)&pcbBytesNeeded.dwErrorControl;
  if ( !*(_QWORD *)&pcbBytesNeeded.dwErrorControl )
    goto LABEL_33;
  if ( v5 )
  {
LABEL_4:
    v11 = OpenServiceW(v5, v10, 1u);
    v12 = v11;
    if ( v11 )
    {
      if ( QueryServiceConfigW(v11, 0, 0, &pcbBytesNeeded.dwServiceType) )
      {
        v9 = -2147418113;
      }
      else
      {
        if ( GetLastError() == 122 )
          goto LABEL_7;
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        if ( v9 >= 0 )
        {
LABEL_7:
          v13 = pcbBytesNeeded.dwServiceType + 15LL;
          if ( v13 <= pcbBytesNeeded.dwServiceType )
            v13 = 0xFFFFFFFFFFFFFF0LL;
          v14 = alloca(v13 & 0xFFFFFFFFFFFFFFF0uLL);
          if ( QueryServiceConfigW(v12, &pcbBytesNeeded, pcbBytesNeeded.dwServiceType, &pcbBytesNeeded.dwServiceType) )
            goto LABEL_10;
          v20 = GetLastError();
          v9 = v20;
          if ( v20 > 0 )
            v9 = (unsigned __int16)v20 | 0x80070000;
          if ( v9 >= 0 )
          {
LABEL_10:
            lpServiceStartName = (LPWSTR)L"LocalSystem";
            if ( pcbBytesNeeded.lpServiceStartName )
              lpServiceStartName = pcbBytesNeeded.lpServiceStartName;
            v9 = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)a2 + 128LL))(a2);
            if ( v9 >= 0 )
            {
              v9 = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, LPWSTR))(*(_QWORD *)a2 + 160LL))(
                     a2,
                     8,
                     0,
                     lpServiceStartName);
              if ( v9 >= 0 )
                v9 = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)a2 + 144LL))(a2);
            }
          }
        }
      }
      CloseServiceHandle(v12);
      goto LABEL_14;
    }
    v17 = GetLastError();
    v9 = v17;
    if ( v17 == 5 )
    {
      v9 = -2147024891;
      goto LABEL_14;
    }
    if ( v17 != 1060 )
    {
      if ( v17 > 0 )
        v9 = (unsigned __int16)v17 | 0x80070000;
      goto LABEL_14;
    }
LABEL_33:
    v9 = 0;
    goto LABEL_14;
  }
  v5 = OpenSCManagerW(0, 0, 0x80000000);
  if ( v5 )
    goto LABEL_16;
  v18 = GetLastError();
  v9 = v18;
  if ( v18 > 0 )
    v9 = (unsigned __int16)v18 | 0x80070000;
  if ( v9 >= 0 )
  {
LABEL_16:
    v10 = *(const WCHAR **)&pcbBytesNeeded.dwErrorControl;
    goto LABEL_4;
  }
LABEL_14:
  *a4 = v5;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180002140  push    rbp
0x180002142  push    rbx
0x180002143  push    rsi
0x180002144  push    rdi
0x180002145  push    r12
0x180002147  push    r13
0x180002149  push    r14
0x18000214b  push    r15
0x18000214d  sub     rsp, 68h
0x180002151  lea     rbp, [rsp+40h]
0x180002156  mov     rax, cs:__security_cookie
0x18000215d  xor     rax, rbp
0x180002160  mov     [rbp+60h+var_50], rax
0x180002164  mov     rax, [rdx]
0x180002167  lea     rcx, [rbp+60h+lpServiceName]
0x18000216b  mov     rbx, [r9]
0x18000216e  mov     r14, rdx
0x180002171  xor     r12d, r12d
0x180002174  mov     [rsp+0A0h+var_78], rcx
0x180002179  mov     r15, r9
0x18000217c  mov     [rbp+60h+pcbBytesNeeded], r12d
0x180002180  mov     rax, [rax+98h]
0x180002187  xor     r9d, r9d
0x18000218a  xor     r8d, r8d
0x18000218d  mov     [rbp+60h+lpServiceName], r12
0x180002191  mov     edx, 6
0x180002196  mov     [rsp+0A0h+var_80], r12
0x18000219b  mov     rcx, r14
0x18000219e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021a3  mov     edi, eax
0x1800021a5  test    eax, eax
0x1800021a7  js      loc_18000227E
0x1800021ad  mov     rdx, [rbp+60h+lpServiceName]; lpServiceName
0x1800021b1  test    rdx, rdx
0x1800021b4  jz      loc_180002343
0x1800021ba  test    rbx, rbx
0x1800021bd  jz      loc_1800022A0
0x1800021c3  mov     r8d, 1; dwDesiredAccess
0x1800021c9  mov     rcx, rbx; hSCManager
0x1800021cc  call    cs:__imp_OpenServiceW
0x1800021d2  mov     rsi, rax
0x1800021d5  test    rax, rax
0x1800021d8  jz      loc_1800022C1
0x1800021de  lea     r9, [rbp+60h+pcbBytesNeeded]; pcbBytesNeeded
0x1800021e2  xor     r8d, r8d; cbBufSize
0x1800021e5  xor     edx, edx; lpServiceConfig
0x1800021e7  mov     rcx, rax; hService
0x1800021ea  call    cs:__imp_QueryServiceConfigW
0x1800021f0  test    eax, eax
0x1800021f2  jnz     loc_180002355
0x1800021f8  call    cs:__imp_GetLastError
0x1800021fe  cmp     eax, 7Ah ; 'z'
0x180002201  jnz     loc_1800022FF
0x180002207  mov     r8d, [rbp+60h+pcbBytesNeeded]
0x18000220b  lea     rax, [r8+0Fh]
0x18000220f  cmp     rax, r8
0x180002212  ja      short loc_18000221E
0x180002214  mov     rax, 0FFFFFFFFFFFFFF0h
0x18000221e  and     rax, 0FFFFFFFFFFFFFFF0h
0x180002222  call    _alloca_probe
0x180002227  sub     rsp, rax
0x18000222a  lea     r9, [rbp+60h+pcbBytesNeeded]; pcbBytesNeeded
0x18000222e  mov     rcx, rsi; hService
0x180002231  lea     r13, [rsp+0A0h+pcbBytesNeeded]
0x180002236  mov     rdx, r13; lpServiceConfig
0x180002239  call    cs:__imp_QueryServiceConfigW
0x18000223f  test    eax, eax
0x180002241  jz      loc_180002321
0x180002247  mov     rax, [r13+30h]
0x18000224b  lea     r12, aLocalsystem; "LocalSystem"
0x180002252  test    rax, rax
0x180002255  mov     rcx, r14
0x180002258  cmovnz  r12, rax
0x18000225c  mov     rax, [r14]
0x18000225f  mov     rax, [rax+80h]
0x180002266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000226b  mov     edi, eax
0x18000226d  test    eax, eax
0x18000226f  jns     loc_18000235F
0x180002275  mov     rcx, rsi; hSCObject
0x180002278  call    cs:__imp_CloseServiceHandle
0x18000227e  mov     [r15], rbx
0x180002281  mov     eax, edi
0x180002283  mov     rcx, [rbp+60h+var_50]
0x180002287  xor     rcx, rbp; StackCookie
0x18000228a  call    __security_check_cookie
0x18000228f  lea     rsp, [rbp+28h]
0x180002293  pop     r15
0x180002295  pop     r14
0x180002297  pop     r13
0x180002299  pop     r12
0x18000229b  pop     rdi
0x18000229c  pop     rsi
0x18000229d  pop     rbx
0x18000229e  pop     rbp
0x18000229f  retn
0x1800022a0  xor     edx, edx; lpDatabaseName
0x1800022a2  xor     ecx, ecx; lpMachineName
0x1800022a4  mov     r8d, 80000000h; dwDesiredAccess
0x1800022aa  call    cs:__imp_OpenSCManagerW
0x1800022b0  mov     rbx, rax
0x1800022b3  test    rax, rax
0x1800022b6  jz      short loc_1800022E4
0x1800022b8  mov     rdx, [rbp+60h+lpServiceName]
0x1800022bc  jmp     loc_1800021C3
0x1800022c1  call    cs:__imp_GetLastError
0x1800022c7  mov     edi, eax
0x1800022c9  cmp     eax, 5
0x1800022cc  jz      short loc_18000234B
0x1800022ce  cmp     eax, 424h
0x1800022d3  jz      short loc_180002343
0x1800022d5  test    eax, eax
0x1800022d7  jle     short loc_18000227E
0x1800022d9  movzx   edi, ax
0x1800022dc  or      edi, 80070000h
0x1800022e2  jmp     short loc_18000227E
0x1800022e4  call    cs:__imp_GetLastError
0x1800022ea  mov     edi, eax
0x1800022ec  test    eax, eax
0x1800022ee  jle     short loc_1800022F9
0x1800022f0  movzx   edi, ax
0x1800022f3  or      edi, 80070000h
0x1800022f9  test    edi, edi
0x1800022fb  js      short loc_18000227E
0x1800022fd  jmp     short loc_1800022B8
0x1800022ff  call    cs:__imp_GetLastError
0x180002305  mov     edi, eax
0x180002307  test    eax, eax
0x180002309  jle     short loc_180002314
0x18000230b  movzx   edi, ax
0x18000230e  or      edi, 80070000h
0x180002314  test    edi, edi
0x180002316  js      loc_180002275
0x18000231c  jmp     loc_180002207
0x180002321  call    cs:__imp_GetLastError
0x180002327  mov     edi, eax
0x180002329  test    eax, eax
0x18000232b  jle     short loc_180002336
0x18000232d  movzx   edi, ax
0x180002330  or      edi, 80070000h
0x180002336  test    edi, edi
0x180002338  js      loc_180002275
0x18000233e  jmp     loc_180002247
0x180002343  mov     edi, r12d
0x180002346  jmp     loc_18000227E
0x18000234b  mov     edi, 80070005h
0x180002350  jmp     loc_18000227E
0x180002355  mov     edi, 8000FFFFh
0x18000235a  jmp     loc_180002275
0x18000235f  mov     rax, [r14]
0x180002362  mov     r9, r12
0x180002365  xor     r8d, r8d
0x180002368  mov     edx, 8
0x18000236d  mov     rcx, r14
0x180002370  mov     rax, [rax+0A0h]
0x180002377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000237c  mov     edi, eax
0x18000237e  test    eax, eax
0x180002380  js      loc_180002275
0x180002386  mov     rax, [r14]
0x180002389  mov     rcx, r14
0x18000238c  mov     rax, [rax+90h]
0x180002393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002398  mov     edi, eax
0x18000239a  jmp     loc_180002275
```
