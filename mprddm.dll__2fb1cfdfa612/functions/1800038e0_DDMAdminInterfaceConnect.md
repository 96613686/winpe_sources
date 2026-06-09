# DDMAdminInterfaceConnect

- ea: `0x1800038e0`
- end: `0x180003fab`
- name: `DDMAdminInterfaceConnect`
- size: `1739`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800038e0`
- `0x180007c50`
- `0x18000fa70`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180003a3c`
- `KERNEL32!GetCurrentProcessId` at `0x180003a3c`
- `KERNEL32!CloseHandle` at `0x180003c18`
- `KERNEL32!CloseHandle` at `0x180003c60`
- `KERNEL32!CloseHandle` at `0x180003d6a`
- `KERNEL32!CloseHandle` at `0x180003f79`
- `KERNEL32!CloseHandle` at `0x180003c18`
- `KERNEL32!CloseHandle` at `0x180003c60`
- `KERNEL32!CloseHandle` at `0x180003d6a`
- `KERNEL32!CloseHandle` at `0x180003f79`
- `KERNEL32!GetLastError` at `0x180003a2f`
- `KERNEL32!GetLastError` at `0x180003a83`
- `KERNEL32!GetLastError` at `0x180003c1e`
- `KERNEL32!GetLastError` at `0x180003c66`
- `KERNEL32!GetLastError` at `0x180003a2f`
- `KERNEL32!GetLastError` at `0x180003a83`
- `KERNEL32!GetLastError` at `0x180003c1e`
- `KERNEL32!GetLastError` at `0x180003c66`
- `KERNEL32!CreateEventW` at `0x180003a21`
- `KERNEL32!CreateEventW` at `0x180003a21`
- `KERNEL32!OpenProcess` at `0x180003a71`
- `KERNEL32!OpenProcess` at `0x180003a71`
- `KERNEL32!DuplicateHandle` at `0x180003c4f`
- `KERNEL32!DuplicateHandle` at `0x180003c4f`
- `KERNEL32!WaitForSingleObject` at `0x180003c07`
- `KERNEL32!WaitForSingleObject` at `0x180003c07`
- `KERNEL32!GetCurrentProcess` at `0x180003c29`
- `KERNEL32!GetCurrentProcess` at `0x180003c29`
- `RPCRT4!RpcImpersonateClient` at `0x180003a51`
- `RPCRT4!RpcImpersonateClient` at `0x180003a51`
- `RPCRT4!RpcRevertToSelf` at `0x180003b1a`
- `RPCRT4!RpcRevertToSelf` at `0x180003cfc`
- `RPCRT4!RpcRevertToSelf` at `0x180003d79`
- `RPCRT4!RpcRevertToSelf` at `0x180003b1a`
- `RPCRT4!RpcRevertToSelf` at `0x180003cfc`
- `RPCRT4!RpcRevertToSelf` at `0x180003d79`

## string_xrefs

- `0x180003a99`: `DDMAdminInterfaceConnect: Failed to open process. error %d`

## pseudocode

```c
DWORD __fastcall DDMAdminInterfaceConnect(__int64 a1, void *a2, int a3, DWORD CurrentProcessId)
{
  __int64 v6; // r15
  int v7; // r14d
  HANDLE EventW; // r12
  void (__fastcall **v10)(__int64); // rax
  void (__fastcall ***v11)(_QWORD); // rax
  void (__fastcall ***v12)(_QWORD); // rdi
  DWORD LastError; // esi
  int v14; // r15d
  HANDLE v15; // rbx
  __int64 v16; // rbx
  int v17; // eax
  unsigned int v18; // eax
  __int64 v19; // rbx
  int v20; // eax
  HANDLE CurrentProcess; // rax
  __int64 v23; // rbx
  int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  __int64 v27; // rbx
  int v28; // eax
  __int64 v29; // rax
  __int64 v30; // rbx
  int v31; // eax
  void (__fastcall ***v32)(_QWORD); // rax
  void (__fastcall ***v33)(_QWORD); // rbx
  HANDLE TargetHandle; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B0h]
  _BYTE v37[16]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v38; // [rsp+68h] [rbp-98h]
  _BYTE v39[16]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v40[16]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v41[16]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v42[16]; // [rsp+A8h] [rbp-58h] BYREF
  int v43; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v44; // [rsp+BCh] [rbp-44h]
  __int128 v45; // [rsp+CCh] [rbp-34h]
  int v46; // [rsp+DCh] [rbp-24h]
  int v47; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v48[2044]; // [rsp+E4h] [rbp-1Ch] BYREF

  v36 = a1;
  v6 = a1;
  TargetHandle = (HANDLE)-1LL;
  v7 = 0;
  v47 = 0;
  EventW = 0;
  memset_0(v48, 0, sizeof(v48));
  v43 = 0;
  v46 = 0;
  v44 = 0;
  v10 = *(void (__fastcall ***)(__int64))g_pIDimInterfaceTable;
  v45 = 0;
  v38 = 0;
  (*v10)(g_pIDimInterfaceTable);
  v11 = (void (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)g_pIDimInterfaceTable
                                                                                   + 64LL))(
                                         g_pIDimInterfaceTable,
                                         v6);
  v12 = v11;
  if ( v11 )
  {
    (**v11)(v11);
    if ( ((unsigned int (__fastcall *)(_QWORD))(*v12)[5])(v12) == 2 )
    {
      LastError = 0;
      v7 = 1;
LABEL_29:
      (*v12)[1](v12);
      v6 = v36;
      goto LABEL_30;
    }
    v14 = 1;
    if ( ((unsigned int (__fastcall *)(_QWORD))(*v12)[5])(v12) == 1 )
    {
      LastError = 910;
LABEL_7:
      v7 = 1;
      goto LABEL_29;
    }
    if ( ((unsigned __int8 (__fastcall *)(_QWORD))(*v12)[7])(v12) )
    {
      LastError = 617;
      goto LABEL_7;
    }
    if ( a2 )
    {
      LastError = RpcImpersonateClient(0);
      EventW = a2;
      if ( LastError )
        goto LABEL_29;
      v14 = 0;
    }
    else
    {
      if ( !a3 )
      {
        EventW = 0;
        goto LABEL_51;
      }
      EventW = CreateEventW(0, 0, 0, 0);
      if ( !EventW )
      {
        LastError = GetLastError();
        goto LABEL_29;
      }
      CurrentProcessId = GetCurrentProcessId();
    }
    v15 = OpenProcess(0xFFFFFu, 0, CurrentProcessId);
    if ( !v15 )
    {
      LastError = GetLastError();
      if ( (byte_1800C8404 & 8) != 0 )
      {
        LOWORD(v47) = 0;
        LOWORD(v43) = 0;
        FormatRRASErrorString(&v47, L"DDMAdminInterfaceConnect: Failed to open process. error %d", LastError);
        if ( (byte_1800C8404 & 8) != 0 )
        {
          v16 = ((__int64 (__fastcall *)(_QWORD))(*v12)[35])(v12);
          v17 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD), _BYTE *))(*v12)[45])(v12, v39);
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceError,
            (unsigned int)&v47,
            v17,
            v16,
            (__int64)&v43);
        }
      }
      if ( v14 )
        goto LABEL_28;
      v18 = RpcRevertToSelf();
      if ( !v18 )
        goto LABEL_28;
      if ( (byte_1800C8404 & 8) == 0 )
        goto LABEL_28;
      LOWORD(v47) = 0;
      LOWORD(v43) = 0;
      FormatRRASErrorString(&v47, L"DDMAdminInterfaceConnect: Failed to revert to self with error %d", v18);
      if ( (byte_1800C8404 & 8) == 0 )
        goto LABEL_28;
      v19 = ((__int64 (__fastcall *)(_QWORD))(*v12)[35])(v12);
      v20 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD), _BYTE *))(*v12)[45])(v12, v40);
LABEL_27:
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v47,
        v20,
        v19,
        (__int64)&v43);
LABEL_28:
      v7 = 0;
      goto LABEL_29;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !DuplicateHandle(v15, EventW, CurrentProcess, &TargetHandle, 0, 0, 2u) )
    {
      CloseHandle(v15);
      LastError = GetLastError();
      if ( (byte_1800C8404 & 8) != 0 )
      {
        LOWORD(v47) = 0;
        LOWORD(v43) = 0;
        FormatRRASErrorString(&v47, L"DDMAdminInterfaceConnect: Failed to duplicate handle. error %d", LastError);
        if ( (byte_1800C8404 & 8) != 0 )
        {
          v23 = ((__int64 (__fastcall *)(_QWORD))(*v12)[35])(v12);
          v24 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD), _BYTE *))(*v12)[45])(v12, v41);
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceError,
            (unsigned int)&v47,
            v24,
            v23,
            (__int64)&v43);
        }
      }
      if ( v14 )
        goto LABEL_28;
      v25 = RpcRevertToSelf();
      if ( !v25 )
        goto LABEL_28;
      if ( (byte_1800C8404 & 8) == 0 )
        goto LABEL_28;
      LOWORD(v47) = 0;
      LOWORD(v43) = 0;
      FormatRRASErrorString(&v47, L"DDMAdminInterfaceConnect: Failed to revert to self with error %d", v25);
      if ( (byte_1800C8404 & 8) == 0 )
        goto LABEL_28;
      v19 = ((__int64 (__fastcall *)(_QWORD))(*v12)[35])(v12);
      v20 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD), _BYTE *))(*v12)[45])(v12, v37);
      goto LABEL_27;
    }
    CloseHandle(v15);
    if ( !v14 )
    {
      v26 = RpcRevertToSelf();
      if ( v26 )
      {
        if ( (byte_1800C8404 & 8) != 0 )
        {
          LOWORD(v47) = 0;
          LOWORD(v43) = 0;
          FormatRRASErrorString(&v47, L"DDMAdminInterfaceConnect: Failed to revert to self with error %d", v26);
          if ( (byte_1800C8404 & 8) != 0 )
          {
            v27 = ((__int64 (__fastcall *)(_QWORD))(*v12)[35])(v12);
            v28 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD), _BYTE *))(*v12)[45])(v12, v37);
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceError,
              (unsigned int)&v47,
              v28,
              v27,
              (__int64)&v43);
          }
        }
        v7 = 0;
      }
    }
LABEL_51:
    ((void (__fastcall *)(void (__fastcall ***)(_QWORD), HANDLE))(*v12)[29])(v12, TargetHandle);
    LastError = RasConnectionInitiate(v12, 0);
    if ( LastError )
      (*v12)[30](v12);
    else
      LastError = 600;
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v47) = 0;
      LOWORD(v43) = 0;
      v29 = ((__int64 (__fastcall *)(_QWORD))(*v12)[35])(v12);
      FormatRRASErrorString(&v47, L"RasConnectionInitiate: To %ws dwRetCode=%d", v29, LastError);
      if ( (byte_1800C8404 & 0x10) != 0 )
      {
        v30 = ((__int64 (__fastcall *)(_QWORD))(*v12)[35])(v12);
        v31 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD), _BYTE *))(*v12)[45])(v12, v42);
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)&v47,
          v31,
          v30,
          (__int64)&v43);
      }
    }
    goto LABEL_29;
  }
  LastError = 6;
LABEL_30:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 16LL))(g_pIDimInterfaceTable);
  if ( !v7 && !a2 && a3 )
  {
    if ( LastError == 600 )
    {
      if ( WaitForSingleObject(EventW, 0xFFFFFFFF) == -1 )
      {
        CloseHandle(EventW);
        return GetLastError();
      }
      (**(void (__fastcall ***)(__int64))g_pIDimInterfaceTable)(g_pIDimInterfaceTable);
      v32 = (void (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)g_pIDimInterfaceTable
                                                                                       + 64LL))(
                                             g_pIDimInterfaceTable,
                                             v6);
      v33 = v32;
      if ( v32 )
      {
        (**v32)(v32);
        LastError = ((__int64 (__fastcall *)(_QWORD))(*v33)[3])(v33);
        (*v33)[1](v33);
      }
      else
      {
        LastError = 6;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 16LL))(g_pIDimInterfaceTable);
    }
    if ( EventW )
      CloseHandle(EventW);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800038e0  mov     [rsp-8+arg_10], rbx
0x1800038e5  push    rbp
0x1800038e6  push    rsi
0x1800038e7  push    rdi
0x1800038e8  push    r12
0x1800038ea  push    r13
0x1800038ec  push    r14
0x1800038ee  push    r15
0x1800038f0  lea     rbp, [rsp-7F0h]
0x1800038f8  sub     rsp, 8F0h
0x1800038ff  mov     rax, cs:__security_cookie
0x180003906  xor     rax, rsp
0x180003909  mov     [rbp+820h+var_40], rax
0x180003910  mov     esi, r8d
0x180003913  mov     [rsp+920h+var_8DC], r8d
0x180003918  mov     r13, rdx
0x18000391b  mov     [rsp+920h+var_8D0], rcx
0x180003920  mov     r15, rcx
0x180003923  mov     [rsp+920h+TargetHandle], 0FFFFFFFFFFFFFFFFh
0x18000392c  xor     eax, eax
0x18000392e  lea     rcx, [rbp+820h+var_83C]; void *
0x180003932  xor     r14d, r14d
0x180003935  mov     [rbp+820h+var_840], eax
0x180003938  xor     edx, edx; Val
0x18000393a  mov     [rsp+920h+var_8E0], r14d
0x18000393f  mov     r8d, 7FCh; Size
0x180003945  mov     ebx, r9d
0x180003948  xor     r12d, r12d
0x18000394b  call    memset_0
0x180003950  mov     rcx, cs:g_pIDimInterfaceTable
0x180003957  xor     eax, eax
0x180003959  xorps   xmm0, xmm0
0x18000395c  mov     [rbp+820h+var_868], eax
0x18000395f  mov     [rbp+820h+var_844], eax
0x180003962  movups  [rbp+820h+var_864], xmm0
0x180003966  mov     rax, [rcx]
0x180003969  movups  [rbp+820h+var_854], xmm0
0x18000396d  movups  [rsp+920h+var_8B8], xmm0
0x180003972  mov     rax, [rax]
0x180003975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000397a  mov     rcx, cs:g_pIDimInterfaceTable
0x180003981  mov     rdx, r15
0x180003984  mov     rax, [rcx]
0x180003987  mov     rax, [rax+40h]
0x18000398b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003990  mov     rdi, rax
0x180003993  test    rax, rax
0x180003996  jnz     short loc_1800039A0
0x180003998  lea     esi, [rax+6]
0x18000399b  jmp     loc_180003BC3
0x1800039a0  mov     rax, [rax]
0x1800039a3  mov     rcx, rdi
0x1800039a6  mov     rax, [rax]
0x1800039a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039ae  mov     rax, [rdi]
0x1800039b1  mov     rcx, rdi
0x1800039b4  mov     rax, [rax+28h]
0x1800039b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039bd  cmp     eax, 2
0x1800039c0  jnz     short loc_1800039CD
0x1800039c2  xor     esi, esi
0x1800039c4  lea     r14d, [rax-1]
0x1800039c8  jmp     loc_180003BAF
0x1800039cd  mov     rax, [rdi]
0x1800039d0  mov     rcx, rdi
0x1800039d3  mov     rax, [rax+28h]
0x1800039d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039dc  mov     r15d, 1
0x1800039e2  cmp     eax, r15d
0x1800039e5  jnz     short loc_1800039F4
0x1800039e7  mov     esi, 38Eh
0x1800039ec  mov     r14d, r15d
0x1800039ef  jmp     loc_180003BAF
0x1800039f4  mov     rax, [rdi]
0x1800039f7  mov     rcx, rdi
0x1800039fa  mov     rax, [rax+38h]
0x1800039fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a03  test    al, al
0x180003a05  jz      short loc_180003A0E
0x180003a07  mov     esi, 269h
0x180003a0c  jmp     short loc_1800039EC
0x180003a0e  test    r13, r13
0x180003a11  jnz     short loc_180003A4F
0x180003a13  test    esi, esi
0x180003a15  jz      short loc_180003A46
0x180003a17  xor     r9d, r9d; lpName
0x180003a1a  xor     r8d, r8d; bInitialState
0x180003a1d  xor     edx, edx; bManualReset
0x180003a1f  xor     ecx, ecx; lpEventAttributes
0x180003a21  call    cs:__imp_CreateEventW
0x180003a27  mov     r12, rax
0x180003a2a  test    rax, rax
0x180003a2d  jnz     short loc_180003A3C
0x180003a2f  call    cs:__imp_GetLastError
0x180003a35  mov     esi, eax
0x180003a37  jmp     loc_180003BAF
0x180003a3c  call    cs:__imp_GetCurrentProcessId
0x180003a42  mov     ebx, eax
0x180003a44  jmp     short loc_180003A67
0x180003a46  test    r13, r13
0x180003a49  jz      loc_180003E4D
0x180003a4f  xor     ecx, ecx; BindingHandle
0x180003a51  call    cs:__imp_RpcImpersonateClient
0x180003a57  mov     esi, eax
0x180003a59  mov     r12, r13
0x180003a5c  test    eax, eax
0x180003a5e  jnz     loc_180003BAF
0x180003a64  xor     r15d, r15d
0x180003a67  mov     r8d, ebx; dwProcessId
0x180003a6a  xor     edx, edx; bInheritHandle
0x180003a6c  mov     ecx, 0FFFFFh; dwDesiredAccess
0x180003a71  call    cs:__imp_OpenProcess
0x180003a77  mov     rbx, rax
0x180003a7a  test    rax, rax
0x180003a7d  jnz     loc_180003C29
0x180003a83  call    cs:__imp_GetLastError
0x180003a89  mov     r14b, 8
0x180003a8c  mov     esi, eax
0x180003a8e  test    cs:byte_1800C8404, r14b
0x180003a95  jz      short loc_180003B11
0x180003a97  xor     eax, eax
0x180003a99  lea     rdx, aDdmadmininterf_2; "DDMAdminInterfaceConnect: Failed to ope"...
0x180003aa0  mov     r8d, esi
0x180003aa3  mov     word ptr [rbp+820h+var_840], ax
0x180003aa7  lea     rcx, [rbp+820h+var_840]
0x180003aab  mov     word ptr [rbp+820h+var_868], ax
0x180003aaf  call    FormatRRASErrorString
0x180003ab4  test    cs:byte_1800C8404, r14b
0x180003abb  jz      short loc_180003B11
0x180003abd  mov     rax, [rdi]
0x180003ac0  mov     rcx, rdi
0x180003ac3  mov     rax, [rax+118h]
0x180003aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003acf  mov     rcx, [rdi]
0x180003ad2  lea     rdx, [rsp+920h+var_8A8]
0x180003ad7  mov     rbx, rax
0x180003ada  mov     rax, [rcx+168h]
0x180003ae1  mov     rcx, rdi
0x180003ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ae9  lea     rcx, [rbp+820h+var_868]
0x180003aed  mov     r9, rax
0x180003af0  mov     qword ptr [rsp+920h+bInheritHandle], rcx
0x180003af5  lea     r8, [rbp+820h+var_840]
0x180003af9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003b00  mov     qword ptr [rsp+920h+dwDesiredAccess], rbx
0x180003b05  lea     rdx, RasDdmParamTraceError
0x180003b0c  call    McTemplateU0zjzz_EventWriteTransfer
0x180003b11  test    r15d, r15d
0x180003b14  jnz     loc_180003BAA
0x180003b1a  call    cs:__imp_RpcRevertToSelf
0x180003b20  test    eax, eax
0x180003b22  jz      loc_180003BAA
0x180003b28  test    cs:byte_1800C8404, r14b
0x180003b2f  jz      short loc_180003BAA
0x180003b31  xor     ecx, ecx
0x180003b33  lea     rdx, aDdmadmininterf_1; "DDMAdminInterfaceConnect: Failed to rev"...
0x180003b3a  mov     word ptr [rbp+820h+var_840], cx
0x180003b3e  mov     r8d, eax
0x180003b41  mov     word ptr [rbp+820h+var_868], cx
0x180003b45  lea     rcx, [rbp+820h+var_840]
0x180003b49  call    FormatRRASErrorString
0x180003b4e  test    cs:byte_1800C8404, r14b
0x180003b55  jz      short loc_180003BAA
0x180003b57  mov     rax, [rdi]
0x180003b5a  mov     rcx, rdi
0x180003b5d  mov     rax, [rax+118h]
0x180003b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b69  mov     rdx, [rdi]
0x180003b6c  mov     rbx, rax
0x180003b6f  mov     rax, [rdx+168h]
0x180003b76  lea     rdx, [rbp+820h+var_898]
0x180003b7a  mov     rcx, rdi
0x180003b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b82  lea     rcx, [rbp+820h+var_868]
0x180003b86  mov     r9, rax
0x180003b89  mov     qword ptr [rsp+920h+bInheritHandle], rcx
0x180003b8e  lea     r8, [rbp+820h+var_840]
0x180003b92  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003b99  mov     qword ptr [rsp+920h+dwDesiredAccess], rbx
0x180003b9e  lea     rdx, RasDdmParamTraceError
0x180003ba5  call    McTemplateU0zjzz_EventWriteTransfer
0x180003baa  mov     r14d, [rsp+920h+var_8E0]
0x180003baf  mov     rax, [rdi]
0x180003bb2  mov     rcx, rdi
0x180003bb5  mov     rax, [rax+8]
0x180003bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bbe  mov     r15, [rsp+920h+var_8D0]
0x180003bc3  mov     rcx, cs:g_pIDimInterfaceTable
0x180003bca  mov     rax, [rcx]
0x180003bcd  mov     rax, [rax+10h]
0x180003bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bd6  test    r14d, r14d
0x180003bd9  jnz     loc_180003F7F
0x180003bdf  test    r13, r13
0x180003be2  jnz     loc_180003F7F
0x180003be8  cmp     [rsp+920h+var_8DC], r13d
0x180003bed  jz      loc_180003F7F
0x180003bf3  cmp     esi, 258h
0x180003bf9  jnz     loc_180003F71
0x180003bff  or      ebx, 0FFFFFFFFh
0x180003c02  mov     rcx, r12; hHandle
0x180003c05  mov     edx, ebx; dwMilliseconds
0x180003c07  call    cs:__imp_WaitForSingleObject
0x180003c0d  cmp     eax, ebx
0x180003c0f  jnz     loc_180003EFB
0x180003c15  mov     rcx, r12; hObject
0x180003c18  call    cs:__imp_CloseHandle
0x180003c1e  call    cs:__imp_GetLastError
0x180003c24  jmp     loc_180003F81
0x180003c29  call    cs:__imp_GetCurrentProcess
0x180003c2f  mov     [rsp+920h+dwOptions], 2; dwOptions
0x180003c37  lea     r9, [rsp+920h+TargetHandle]; lpTargetHandle
0x180003c3c  mov     r8, rax; hTargetProcessHandle
0x180003c3f  mov     [rsp+920h+bInheritHandle], r14d; bInheritHandle
0x180003c44  mov     rdx, r12; hSourceHandle
0x180003c47  mov     [rsp+920h+dwDesiredAccess], r14d; dwDesiredAccess
0x180003c4c  mov     rcx, rbx; hSourceProcessHandle
0x180003c4f  call    cs:__imp_DuplicateHandle
0x180003c55  mov     rcx, rbx; hObject
0x180003c58  test    eax, eax
0x180003c5a  jnz     loc_180003D6A
0x180003c60  call    cs:__imp_CloseHandle
0x180003c66  call    cs:__imp_GetLastError
0x180003c6c  mov     r14b, 8
0x180003c6f  mov     esi, eax
0x180003c71  test    cs:byte_1800C8404, r14b
0x180003c78  jz      short loc_180003CF3
0x180003c7a  xor     eax, eax
0x180003c7c  lea     rdx, aDdmadmininterf_3; "DDMAdminInterfaceConnect: Failed to dup"...
0x180003c83  mov     r8d, esi
0x180003c86  mov     word ptr [rbp+820h+var_840], ax
0x180003c8a  lea     rcx, [rbp+820h+var_840]
0x180003c8e  mov     word ptr [rbp+820h+var_868], ax
0x180003c92  call    FormatRRASErrorString
0x180003c97  test    cs:byte_1800C8404, r14b
0x180003c9e  jz      short loc_180003CF3
0x180003ca0  mov     rax, [rdi]
0x180003ca3  mov     rcx, rdi
0x180003ca6  mov     rax, [rax+118h]
0x180003cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cb2  mov     rcx, [rdi]
0x180003cb5  lea     rdx, [rbp+820h+var_888]
0x180003cb9  mov     rbx, rax
0x180003cbc  mov     rax, [rcx+168h]
0x180003cc3  mov     rcx, rdi
0x180003cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ccb  lea     rcx, [rbp+820h+var_868]
0x180003ccf  mov     r9, rax
0x180003cd2  mov     qword ptr [rsp+920h+bInheritHandle], rcx
0x180003cd7  lea     r8, [rbp+820h+var_840]
0x180003cdb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003ce2  mov     qword ptr [rsp+920h+dwDesiredAccess], rbx
0x180003ce7  lea     rdx, RasDdmParamTraceError
0x180003cee  call    McTemplateU0zjzz_EventWriteTransfer
0x180003cf3  test    r15d, r15d
0x180003cf6  jnz     loc_180003BAA
0x180003cfc  call    cs:__imp_RpcRevertToSelf
0x180003d02  test    eax, eax
0x180003d04  jz      loc_180003BAA
0x180003d0a  test    cs:byte_1800C8404, r14b
0x180003d11  jz      loc_180003BAA
0x180003d17  xor     ecx, ecx
0x180003d19  lea     rdx, aDdmadmininterf_1; "DDMAdminInterfaceConnect: Failed to rev"...
0x180003d20  mov     word ptr [rbp+820h+var_840], cx
0x180003d24  mov     r8d, eax
0x180003d27  mov     word ptr [rbp+820h+var_868], cx
0x180003d2b  lea     rcx, [rbp+820h+var_840]
0x180003d2f  call    FormatRRASErrorString
0x180003d34  test    cs:byte_1800C8404, r14b
0x180003d3b  jz      loc_180003BAA
0x180003d41  mov     rax, [rdi]
0x180003d44  mov     rcx, rdi
0x180003d47  mov     rax, [rax+118h]
0x180003d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d53  mov     rcx, [rdi]
0x180003d56  lea     rdx, [rsp+920h+var_8C8]
0x180003d5b  mov     rbx, rax
0x180003d5e  mov     rax, [rcx+168h]
0x180003d65  jmp     loc_180003B7A
0x180003d6a  call    cs:__imp_CloseHandle
0x180003d70  test    r15d, r15d
0x180003d73  jnz     loc_180003E12
0x180003d79  call    cs:__imp_RpcRevertToSelf
0x180003d7f  test    eax, eax
0x180003d81  jz      loc_180003E12
0x180003d87  mov     r14b, 8
0x180003d8a  test    cs:byte_1800C8404, r14b
0x180003d91  jz      short loc_180003E0D
0x180003d93  xor     ecx, ecx
0x180003d95  lea     rdx, aDdmadmininterf_1; "DDMAdminInterfaceConnect: Failed to rev"...
0x180003d9c  mov     word ptr [rbp+820h+var_840], cx
0x180003da0  mov     r8d, eax
0x180003da3  mov     word ptr [rbp+820h+var_868], cx
0x180003da7  lea     rcx, [rbp+820h+var_840]
0x180003dab  call    FormatRRASErrorString
0x180003db0  test    cs:byte_1800C8404, r14b
0x180003db7  jz      short loc_180003E0D
0x180003db9  mov     rax, [rdi]
0x180003dbc  mov     rcx, rdi
0x180003dbf  mov     rax, [rax+118h]
  ... truncated ...
```
