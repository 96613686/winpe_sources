# DDMAdminInterfaceConnect

- ea: `0x180003a10`
- end: `0x18000411b`
- name: `DDMAdminInterfaceConnect`
- size: `1803`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003a10`
- `0x180007d00`
- `0x18000fef0`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180003b74`
- `KERNEL32!GetCurrentProcessId` at `0x180003b74`
- `KERNEL32!CloseHandle` at `0x180003d30`
- `KERNEL32!CloseHandle` at `0x180003e4c`
- `KERNEL32!CloseHandle` at `0x180004047`
- `KERNEL32!CloseHandle` at `0x1800040e2`
- `KERNEL32!CloseHandle` at `0x180003d30`
- `KERNEL32!CloseHandle` at `0x180003e4c`
- `KERNEL32!CloseHandle` at `0x180004047`
- `KERNEL32!CloseHandle` at `0x1800040e2`
- `KERNEL32!GetLastError` at `0x180003b61`
- `KERNEL32!GetLastError` at `0x180003bd0`
- `KERNEL32!GetLastError` at `0x180003d3c`
- `KERNEL32!GetLastError` at `0x180004053`
- `KERNEL32!GetLastError` at `0x180003b61`
- `KERNEL32!GetLastError` at `0x180003bd0`
- `KERNEL32!GetLastError` at `0x180003d3c`
- `KERNEL32!GetLastError` at `0x180004053`
- `KERNEL32!CreateEventW` at `0x180003b4d`
- `KERNEL32!CreateEventW` at `0x180003b4d`
- `KERNEL32!OpenProcess` at `0x180003bb8`
- `KERNEL32!OpenProcess` at `0x180003bb8`
- `KERNEL32!DuplicateHandle` at `0x180003d19`
- `KERNEL32!DuplicateHandle` at `0x180003d19`
- `KERNEL32!WaitForSingleObject` at `0x180004034`
- `KERNEL32!WaitForSingleObject` at `0x180004034`
- `KERNEL32!GetCurrentProcess` at `0x180003ced`
- `KERNEL32!GetCurrentProcess` at `0x180003ced`
- `RPCRT4!RpcImpersonateClient` at `0x180003b95`
- `RPCRT4!RpcImpersonateClient` at `0x180003b95`
- `RPCRT4!RpcRevertToSelf` at `0x180003c6d`
- `RPCRT4!RpcRevertToSelf` at `0x180003dda`
- `RPCRT4!RpcRevertToSelf` at `0x180003e63`
- `RPCRT4!RpcRevertToSelf` at `0x180003c6d`
- `RPCRT4!RpcRevertToSelf` at `0x180003dda`
- `RPCRT4!RpcRevertToSelf` at `0x180003e63`

## string_xrefs

- `0x180003bf1`: `DDMAdminInterfaceConnect: Failed to open process. error %d`

## pseudocode

```c
DWORD __fastcall DDMAdminInterfaceConnect(__int64 a1, void *a2, int a3, DWORD CurrentProcessId)
{
  void *v5; // r14
  __int64 v6; // r15
  HANDLE EventW; // r12
  int v8; // r13d
  void (__fastcall **v10)(__int64); // rax
  void (__fastcall ***v11)(_QWORD); // rax
  void (__fastcall ***v12)(_QWORD); // rdi
  DWORD LastError; // esi
  int v14; // r15d
  HANDLE v15; // rbx
  DWORD v16; // eax
  __int64 v17; // rbx
  int v18; // eax
  unsigned int v19; // eax
  __int64 v20; // rbx
  int v21; // eax
  __int64 *v22; // rdx
  HANDLE CurrentProcess; // rax
  DWORD v24; // eax
  __int64 v25; // rbx
  int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  __int64 v29; // rbx
  int v30; // eax
  __int64 v31; // rax
  void (__fastcall ***v33)(_QWORD); // rax
  void (__fastcall ***v34)(_QWORD); // rbx
  HANDLE TargetHandle; // [rsp+48h] [rbp-B8h] BYREF
  void *v37; // [rsp+50h] [rbp-B0h]
  __int64 v38; // [rsp+58h] [rbp-A8h]
  char v39[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v40[16]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v41; // [rsp+80h] [rbp-80h]
  char v42[16]; // [rsp+90h] [rbp-70h] BYREF
  char v43[16]; // [rsp+A0h] [rbp-60h] BYREF
  char v44[16]; // [rsp+B0h] [rbp-50h] BYREF
  int v45; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v46; // [rsp+C4h] [rbp-3Ch]
  __int128 v47; // [rsp+D4h] [rbp-2Ch]
  int v48; // [rsp+E4h] [rbp-1Ch]
  int v49; // [rsp+F0h] [rbp-10h] BYREF
  char v50[2044]; // [rsp+F4h] [rbp-Ch] BYREF

  TargetHandle = (HANDLE)-1LL;
  v5 = a2;
  v37 = a2;
  v6 = a1;
  v38 = a1;
  v49 = 0;
  EventW = 0;
  v8 = 0;
  memset_0(v50, 0, sizeof(v50));
  v48 = 0;
  v45 = 0;
  v46 = 0;
  v10 = *(void (__fastcall ***)(__int64))g_pIDimInterfaceTable;
  v47 = 0;
  v41 = 0;
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
      v8 = 1;
LABEL_48:
      (*v12)[1](v12);
      v5 = v37;
      v6 = v38;
      goto LABEL_49;
    }
    v14 = 1;
    if ( ((unsigned int (__fastcall *)(_QWORD))(*v12)[5])(v12) == 1 )
    {
      LastError = 910;
LABEL_7:
      v8 = 1;
      goto LABEL_48;
    }
    if ( ((unsigned __int8 (__fastcall *)(_QWORD))(*v12)[7])(v12) )
    {
      LastError = 617;
      goto LABEL_7;
    }
    if ( v5 || !a3 )
    {
      EventW = v5;
      if ( !v5 )
        goto LABEL_41;
      LastError = RpcImpersonateClient(0);
      v14 = 0;
      if ( LastError )
        goto LABEL_48;
    }
    else
    {
      EventW = CreateEventW(0, 0, 0, 0);
      if ( !EventW )
      {
        LastError = GetLastError();
        goto LABEL_48;
      }
      CurrentProcessId = GetCurrentProcessId();
    }
    v15 = OpenProcess(0xFFFFFu, 0, CurrentProcessId);
    if ( !v15 )
    {
      v16 = GetLastError();
      LastError = v16;
      if ( (byte_1800CF404 & 8) != 0 )
      {
        LOWORD(v49) = 0;
        LOWORD(v45) = 0;
        FormatRRASErrorString(&v49, L"DDMAdminInterfaceConnect: Failed to open process. error %d", v16);
        if ( (byte_1800CF404 & 8) != 0 )
        {
          v17 = ((__int64 (__fastcall *)(_QWORD))(*v12)[35])(v12);
          v18 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD), char *))(*v12)[45])(v12, v39);
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceError,
            (unsigned int)&v49,
            v18,
            v17,
            (__int64)&v45);
        }
      }
      if ( v14 )
        goto LABEL_48;
      v19 = RpcRevertToSelf();
      if ( !v19 )
        goto LABEL_48;
      if ( (byte_1800CF404 & 8) == 0 )
        goto LABEL_48;
      LOWORD(v49) = 0;
      LOWORD(v45) = 0;
      FormatRRASErrorString(&v49, L"DDMAdminInterfaceConnect: Failed to revert to self with error %d", v19);
      if ( (byte_1800CF404 & 8) == 0 )
        goto LABEL_48;
      v20 = ((__int64 (__fastcall *)(_QWORD))(*v12)[35])(v12);
      v21 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD), char *))(*v12)[45])(v12, v42);
      goto LABEL_26;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !DuplicateHandle(v15, EventW, CurrentProcess, &TargetHandle, 0, 0, 2u) )
    {
      CloseHandle(v15);
      v24 = GetLastError();
      LastError = v24;
      if ( (byte_1800CF404 & 8) != 0 )
      {
        LOWORD(v49) = 0;
        LOWORD(v45) = 0;
        FormatRRASErrorString(&v49, L"DDMAdminInterfaceConnect: Failed to duplicate handle. error %d", v24);
        if ( (byte_1800CF404 & 8) != 0 )
        {
          v25 = ((__int64 (__fastcall *)(_QWORD))(*v12)[35])(v12);
          v26 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD), char *))(*v12)[45])(v12, v43);
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceError,
            (unsigned int)&v49,
            v26,
            v25,
            (__int64)&v45);
        }
      }
      if ( v14 )
        goto LABEL_48;
      v27 = RpcRevertToSelf();
      if ( !v27 )
        goto LABEL_48;
      if ( (byte_1800CF404 & 8) == 0 )
        goto LABEL_48;
      LOWORD(v49) = 0;
      LOWORD(v45) = 0;
      FormatRRASErrorString(&v49, L"DDMAdminInterfaceConnect: Failed to revert to self with error %d", v27);
      if ( (byte_1800CF404 & 8) == 0 )
        goto LABEL_48;
      v20 = ((__int64 (__fastcall *)(_QWORD))(*v12)[35])(v12);
      v21 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD), _BYTE *))(*v12)[45])(v12, v40);
LABEL_26:
      v22 = RasDdmParamTraceError;
LABEL_47:
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (_DWORD)v22,
        (unsigned int)&v49,
        v21,
        v20,
        (__int64)&v45);
      goto LABEL_48;
    }
    CloseHandle(v15);
    if ( !v14 )
    {
      v28 = RpcRevertToSelf();
      if ( v28 )
      {
        if ( (byte_1800CF404 & 8) != 0 )
        {
          LOWORD(v49) = 0;
          LOWORD(v45) = 0;
          FormatRRASErrorString(&v49, L"DDMAdminInterfaceConnect: Failed to revert to self with error %d", v28);
          if ( (byte_1800CF404 & 8) != 0 )
          {
            v29 = ((__int64 (__fastcall *)(_QWORD))(*v12)[35])(v12);
            v30 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD), _BYTE *))(*v12)[45])(v12, v40);
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDdmParamTraceError,
              (unsigned int)&v49,
              v30,
              v29,
              (__int64)&v45);
          }
        }
      }
    }
LABEL_41:
    ((void (__fastcall *)(void (__fastcall ***)(_QWORD), HANDLE))(*v12)[29])(v12, TargetHandle);
    LastError = RasConnectionInitiate(v12, 0);
    if ( LastError )
      (*v12)[30](v12);
    else
      LastError = 600;
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_48;
    LOWORD(v49) = 0;
    LOWORD(v45) = 0;
    v31 = ((__int64 (__fastcall *)(_QWORD))(*v12)[35])(v12);
    FormatRRASErrorString(&v49, L"RasConnectionInitiate: To %ws dwRetCode=%d", v31, LastError);
    if ( (byte_1800CF404 & 0x10) == 0 )
      goto LABEL_48;
    v20 = ((__int64 (__fastcall *)(_QWORD))(*v12)[35])(v12);
    v21 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD), char *))(*v12)[45])(v12, v44);
    v22 = RasDdmParamTraceInfo;
    goto LABEL_47;
  }
  LastError = 6;
LABEL_49:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)g_pIDimInterfaceTable + 16LL))(g_pIDimInterfaceTable);
  if ( !v8 && !v5 && a3 )
  {
    if ( LastError == 600 )
    {
      if ( WaitForSingleObject(EventW, 0xFFFFFFFF) == -1 )
      {
        CloseHandle(EventW);
        return GetLastError();
      }
      (**(void (__fastcall ***)(__int64))g_pIDimInterfaceTable)(g_pIDimInterfaceTable);
      v33 = (void (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)g_pIDimInterfaceTable
                                                                                       + 64LL))(
                                             g_pIDimInterfaceTable,
                                             v6);
      v34 = v33;
      if ( v33 )
      {
        (**v33)(v33);
        LastError = ((__int64 (__fastcall *)(_QWORD))(*v34)[3])(v34);
        (*v34)[1](v34);
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
0x180003a10  mov     [rsp-8+arg_10], rbx
0x180003a15  push    rbp
0x180003a16  push    rsi
0x180003a17  push    rdi
0x180003a18  push    r12
0x180003a1a  push    r13
0x180003a1c  push    r14
0x180003a1e  push    r15
0x180003a20  lea     rbp, [rsp-800h]
0x180003a28  sub     rsp, 900h
0x180003a2f  mov     rax, cs:__security_cookie
0x180003a36  xor     rax, rsp
0x180003a39  mov     [rbp+830h+var_40], rax
0x180003a40  or      [rsp+930h+TargetHandle], 0FFFFFFFFFFFFFFFFh
0x180003a46  xor     edi, edi
0x180003a48  mov     esi, r8d
0x180003a4b  mov     [rsp+930h+var_8F0], r8d
0x180003a50  mov     r14, rdx
0x180003a53  mov     [rsp+930h+var_8E0], rdx
0x180003a58  mov     r15, rcx
0x180003a5b  mov     [rsp+930h+var_8D8], rcx
0x180003a60  xor     edx, edx; Val
0x180003a62  mov     [rbp+830h+var_840], edi
0x180003a65  mov     r8d, 7FCh; Size
0x180003a6b  lea     rcx, [rbp+830h+var_83C]; void *
0x180003a6f  mov     r12d, edi
0x180003a72  mov     r13d, edi
0x180003a75  mov     ebx, r9d
0x180003a78  call    memset_0
0x180003a7d  mov     rcx, cs:g_pIDimInterfaceTable
0x180003a84  xor     eax, eax
0x180003a86  xorps   xmm0, xmm0
0x180003a89  mov     [rbp+830h+var_84C], eax
0x180003a8c  mov     [rbp+830h+var_870], edi
0x180003a8f  movups  [rbp+830h+var_86C], xmm0
0x180003a93  mov     rax, [rcx]
0x180003a96  movups  [rbp+830h+var_85C], xmm0
0x180003a9a  movups  [rbp+830h+var_8B0], xmm0
0x180003a9e  mov     rax, [rax]
0x180003aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aa6  mov     rcx, cs:g_pIDimInterfaceTable
0x180003aad  mov     rdx, r15
0x180003ab0  mov     rax, [rcx]
0x180003ab3  mov     rax, [rax+40h]
0x180003ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003abc  mov     rdi, rax
0x180003abf  test    rax, rax
0x180003ac2  jnz     short loc_180003ACC
0x180003ac4  lea     esi, [rax+6]
0x180003ac7  jmp     loc_180003FEF
0x180003acc  mov     rax, [rax]
0x180003acf  mov     rcx, rdi
0x180003ad2  mov     rax, [rax]
0x180003ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ada  mov     rax, [rdi]
0x180003add  mov     rcx, rdi
0x180003ae0  mov     rax, [rax+28h]
0x180003ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ae9  cmp     eax, 2
0x180003aec  jnz     short loc_180003AF9
0x180003aee  xor     esi, esi
0x180003af0  lea     r13d, [rax-1]
0x180003af4  jmp     loc_180003FD6
0x180003af9  mov     rax, [rdi]
0x180003afc  mov     rcx, rdi
0x180003aff  mov     rax, [rax+28h]
0x180003b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b08  mov     r15d, 1
0x180003b0e  cmp     eax, r15d
0x180003b11  jnz     short loc_180003B20
0x180003b13  mov     esi, 38Eh
0x180003b18  mov     r13d, r15d
0x180003b1b  jmp     loc_180003FD6
0x180003b20  mov     rax, [rdi]
0x180003b23  mov     rcx, rdi
0x180003b26  mov     rax, [rax+38h]
0x180003b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b2f  test    al, al
0x180003b31  jz      short loc_180003B3A
0x180003b33  mov     esi, 269h
0x180003b38  jmp     short loc_180003B18
0x180003b3a  test    r14, r14
0x180003b3d  jnz     short loc_180003B84
0x180003b3f  test    esi, esi
0x180003b41  jz      short loc_180003B84
0x180003b43  xor     r9d, r9d; lpName
0x180003b46  xor     r8d, r8d; bInitialState
0x180003b49  xor     edx, edx; bManualReset
0x180003b4b  xor     ecx, ecx; lpEventAttributes
0x180003b4d  call    cs:__imp_CreateEventW
0x180003b54  nop     dword ptr [rax+rax+00h]
0x180003b59  mov     r12, rax
0x180003b5c  test    rax, rax
0x180003b5f  jnz     short loc_180003B74
0x180003b61  call    cs:__imp_GetLastError
0x180003b68  nop     dword ptr [rax+rax+00h]
0x180003b6d  mov     esi, eax
0x180003b6f  jmp     loc_180003FD6
0x180003b74  call    cs:__imp_GetCurrentProcessId
0x180003b7b  nop     dword ptr [rax+rax+00h]
0x180003b80  mov     ebx, eax
0x180003b82  jmp     short loc_180003BAE
0x180003b84  mov     r12, r14
0x180003b87  xor     r14d, r14d
0x180003b8a  test    r12, r12
0x180003b8d  jz      loc_180003EFB
0x180003b93  xor     ecx, ecx; BindingHandle
0x180003b95  call    cs:__imp_RpcImpersonateClient
0x180003b9c  nop     dword ptr [rax+rax+00h]
0x180003ba1  mov     esi, eax
0x180003ba3  mov     r15d, r14d
0x180003ba6  test    eax, eax
0x180003ba8  jnz     loc_180003FD6
0x180003bae  mov     r8d, ebx; dwProcessId
0x180003bb1  xor     edx, edx; bInheritHandle
0x180003bb3  mov     ecx, 0FFFFFh; dwDesiredAccess
0x180003bb8  call    cs:__imp_OpenProcess
0x180003bbf  nop     dword ptr [rax+rax+00h]
0x180003bc4  mov     rbx, rax
0x180003bc7  test    rax, rax
0x180003bca  jnz     loc_180003CED
0x180003bd0  call    cs:__imp_GetLastError
0x180003bd7  nop     dword ptr [rax+rax+00h]
0x180003bdc  mov     r14b, 8
0x180003bdf  mov     esi, eax
0x180003be1  test    cs:byte_1800CF404, r14b
0x180003be8  jz      short loc_180003C64
0x180003bea  mov     r8d, eax
0x180003bed  mov     word ptr [rbp+830h+var_840], bx
0x180003bf1  lea     rdx, aDdmadmininterf_2; "DDMAdminInterfaceConnect: Failed to ope"...
0x180003bf8  mov     word ptr [rbp+830h+var_870], bx
0x180003bfc  lea     rcx, [rbp+830h+var_840]
0x180003c00  call    FormatRRASErrorString
0x180003c05  test    cs:byte_1800CF404, r14b
0x180003c0c  jz      short loc_180003C64
0x180003c0e  mov     rax, [rdi]
0x180003c11  mov     rcx, rdi
0x180003c14  mov     rax, [rax+118h]
0x180003c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c20  mov     rcx, [rdi]
0x180003c23  lea     rdx, [rsp+930h+var_8D0]
0x180003c28  mov     rbx, rax
0x180003c2b  mov     rax, [rcx+168h]
0x180003c32  mov     rcx, rdi
0x180003c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c3a  lea     rcx, [rbp+830h+var_870]
0x180003c3e  mov     r9, rax
0x180003c41  mov     qword ptr [rsp+930h+bInheritHandle], rcx
0x180003c46  lea     r8, [rbp+830h+var_840]
0x180003c4a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003c51  mov     qword ptr [rsp+930h+dwDesiredAccess], rbx
0x180003c56  lea     rdx, RasDdmParamTraceError
0x180003c5d  call    McTemplateU0zjzz_EventWriteTransfer
0x180003c62  xor     ebx, ebx
0x180003c64  test    r15d, r15d
0x180003c67  jnz     loc_180003FD6
0x180003c6d  call    cs:__imp_RpcRevertToSelf
0x180003c74  nop     dword ptr [rax+rax+00h]
0x180003c79  test    eax, eax
0x180003c7b  jz      loc_180003FD6
0x180003c81  test    cs:byte_1800CF404, r14b
0x180003c88  jz      loc_180003FD6
0x180003c8e  mov     r8d, eax
0x180003c91  mov     word ptr [rbp+830h+var_840], bx
0x180003c95  lea     rdx, aDdmadmininterf_1; "DDMAdminInterfaceConnect: Failed to rev"...
0x180003c9c  mov     word ptr [rbp+830h+var_870], bx
0x180003ca0  lea     rcx, [rbp+830h+var_840]
0x180003ca4  call    FormatRRASErrorString
0x180003ca9  test    cs:byte_1800CF404, r14b
0x180003cb0  jz      loc_180003FD6
0x180003cb6  mov     rax, [rdi]
0x180003cb9  mov     rcx, rdi
0x180003cbc  mov     rax, [rax+118h]
0x180003cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cc8  mov     rdx, [rdi]
0x180003ccb  mov     rbx, rax
0x180003cce  mov     rax, [rdx+168h]
0x180003cd5  lea     rdx, [rbp+830h+var_8A0]
0x180003cd9  mov     rcx, rdi
0x180003cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ce1  lea     rdx, RasDdmParamTraceError
0x180003ce8  jmp     loc_180003FB5
0x180003ced  call    cs:__imp_GetCurrentProcess
0x180003cf4  nop     dword ptr [rax+rax+00h]
0x180003cf9  mov     [rsp+930h+dwOptions], 2; dwOptions
0x180003d01  lea     r9, [rsp+930h+TargetHandle]; lpTargetHandle
0x180003d06  mov     r8, rax; hTargetProcessHandle
0x180003d09  mov     [rsp+930h+bInheritHandle], r14d; bInheritHandle
0x180003d0e  mov     rdx, r12; hSourceHandle
0x180003d11  mov     [rsp+930h+dwDesiredAccess], r14d; dwDesiredAccess
0x180003d16  mov     rcx, rbx; hSourceProcessHandle
0x180003d19  call    cs:__imp_DuplicateHandle
0x180003d20  nop     dword ptr [rax+rax+00h]
0x180003d25  mov     rcx, rbx; hObject
0x180003d28  test    eax, eax
0x180003d2a  jnz     loc_180003E4C
0x180003d30  call    cs:__imp_CloseHandle
0x180003d37  nop     dword ptr [rax+rax+00h]
0x180003d3c  call    cs:__imp_GetLastError
0x180003d43  nop     dword ptr [rax+rax+00h]
0x180003d48  mov     r14b, 8
0x180003d4b  xor     ebx, ebx
0x180003d4d  test    cs:byte_1800CF404, r14b
0x180003d54  mov     esi, eax
0x180003d56  jz      short loc_180003DD1
0x180003d58  mov     r8d, eax
0x180003d5b  mov     word ptr [rbp+830h+var_840], bx
0x180003d5f  lea     rdx, aDdmadmininterf_3; "DDMAdminInterfaceConnect: Failed to dup"...
0x180003d66  mov     word ptr [rbp+830h+var_870], bx
0x180003d6a  lea     rcx, [rbp+830h+var_840]
0x180003d6e  call    FormatRRASErrorString
0x180003d73  test    cs:byte_1800CF404, r14b
0x180003d7a  jz      short loc_180003DD1
0x180003d7c  mov     rax, [rdi]
0x180003d7f  mov     rcx, rdi
0x180003d82  mov     rax, [rax+118h]
0x180003d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d8e  mov     rcx, [rdi]
0x180003d91  lea     rdx, [rbp+830h+var_890]
0x180003d95  mov     rbx, rax
0x180003d98  mov     rax, [rcx+168h]
0x180003d9f  mov     rcx, rdi
0x180003da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003da7  lea     rcx, [rbp+830h+var_870]
0x180003dab  mov     r9, rax
0x180003dae  mov     qword ptr [rsp+930h+bInheritHandle], rcx
0x180003db3  lea     r8, [rbp+830h+var_840]
0x180003db7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003dbe  mov     qword ptr [rsp+930h+dwDesiredAccess], rbx
0x180003dc3  lea     rdx, RasDdmParamTraceError
0x180003dca  call    McTemplateU0zjzz_EventWriteTransfer
0x180003dcf  xor     ebx, ebx
0x180003dd1  test    r15d, r15d
0x180003dd4  jnz     loc_180003FD6
0x180003dda  call    cs:__imp_RpcRevertToSelf
0x180003de1  nop     dword ptr [rax+rax+00h]
0x180003de6  test    eax, eax
0x180003de8  jz      loc_180003FD6
0x180003dee  test    cs:byte_1800CF404, r14b
0x180003df5  jz      loc_180003FD6
0x180003dfb  mov     r8d, eax
0x180003dfe  mov     word ptr [rbp+830h+var_840], bx
0x180003e02  lea     rdx, aDdmadmininterf_1; "DDMAdminInterfaceConnect: Failed to rev"...
0x180003e09  mov     word ptr [rbp+830h+var_870], bx
0x180003e0d  lea     rcx, [rbp+830h+var_840]
0x180003e11  call    FormatRRASErrorString
0x180003e16  test    cs:byte_1800CF404, r14b
0x180003e1d  jz      loc_180003FD6
0x180003e23  mov     rax, [rdi]
0x180003e26  mov     rcx, rdi
0x180003e29  mov     rax, [rax+118h]
0x180003e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e35  mov     rcx, [rdi]
0x180003e38  lea     rdx, [rsp+930h+var_8C0]
0x180003e3d  mov     rbx, rax
0x180003e40  mov     rax, [rcx+168h]
0x180003e47  jmp     loc_180003CD9
0x180003e4c  call    cs:__imp_CloseHandle
0x180003e53  nop     dword ptr [rax+rax+00h]
0x180003e58  xor     ebx, ebx
0x180003e5a  test    r15d, r15d
0x180003e5d  jnz     loc_180003EFD
0x180003e63  call    cs:__imp_RpcRevertToSelf
0x180003e6a  nop     dword ptr [rax+rax+00h]
0x180003e6f  test    eax, eax
0x180003e71  jz      loc_180003EFD
0x180003e77  mov     r14b, 8
0x180003e7a  test    cs:byte_1800CF404, r14b
0x180003e81  jz      short loc_180003EFD
0x180003e83  mov     r8d, eax
0x180003e86  mov     word ptr [rbp+830h+var_840], bx
0x180003e8a  lea     rdx, aDdmadmininterf_1; "DDMAdminInterfaceConnect: Failed to rev"...
0x180003e91  mov     word ptr [rbp+830h+var_870], bx
0x180003e95  lea     rcx, [rbp+830h+var_840]
0x180003e99  call    FormatRRASErrorString
0x180003e9e  test    cs:byte_1800CF404, r14b
0x180003ea5  jz      short loc_180003EFD
0x180003ea7  mov     rax, [rdi]
0x180003eaa  mov     rcx, rdi
0x180003ead  mov     rax, [rax+118h]
0x180003eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eb9  mov     rcx, [rdi]
0x180003ebc  lea     rdx, [rsp+930h+var_8C0]
0x180003ec1  mov     rbx, rax
0x180003ec4  mov     rax, [rcx+168h]
0x180003ecb  mov     rcx, rdi
0x180003ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ed3  lea     rcx, [rbp+830h+var_870]
0x180003ed7  mov     r9, rax
0x180003eda  mov     qword ptr [rsp+930h+bInheritHandle], rcx
0x180003edf  lea     r8, [rbp+830h+var_840]
0x180003ee3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003eea  mov     qword ptr [rsp+930h+dwDesiredAccess], rbx
0x180003eef  lea     rdx, RasDdmParamTraceError
0x180003ef6  call    McTemplateU0zjzz_EventWriteTransfer
0x180003efb  xor     ebx, ebx
0x180003efd  mov     rax, [rdi]
0x180003f00  mov     rcx, rdi
0x180003f03  mov     rdx, [rsp+930h+TargetHandle]
0x180003f08  mov     rax, [rax+0E8h]
  ... truncated ...
```
