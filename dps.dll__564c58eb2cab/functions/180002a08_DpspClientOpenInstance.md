# DpspClientOpenInstance

- ea: `0x180002a08`
- end: `0x180002db6`
- name: `DpspClientOpenInstance`
- size: `942`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800104f4`

## callees

- `0x180001010`
- `0x180002a08`
- `0x180006694`
- `0x1800069b0`
- `0x180006eec`
- `0x180009090`
- `0x180012934`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180002a31`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180002a31`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180002a4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180002aa8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180002aca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180002a4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180002aa8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180002aca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002c60`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002c6a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002c60`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002c6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002cff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002d09`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002d2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002d39`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002cff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002d09`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002d2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002d39`
- `ntdll!NtAlpcDisconnectPort` at `0x180002c90`
- `ntdll!NtAlpcDisconnectPort` at `0x180002c90`
- `ntdll!NtAlpcQueryInformation` at `0x180002cb3`
- `ntdll!NtAlpcQueryInformation` at `0x180002cb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002b72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002cd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002b72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002cd1`

## string_xrefs

- `0x180002a68`: `DpspClientOpenInstance`
- `0x180002d59`: `DpspClientOpenInstance`

## pseudocode

```c
__int64 __fastcall DpspClientOpenInstance(__int64 a1, __int64 a2)
{
  __int64 InstanceFromId; // rax
  __int64 v5; // rdi
  unsigned int v6; // ebx
  unsigned int v7; // r12d
  unsigned int v8; // r13d
  __int64 v9; // rax
  __int64 v10; // rsi
  int v11; // r8d
  HANDLE *v12; // r14
  char *v13; // rcx
  int Args; // eax
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rcx
  char *v18; // rcx
  void *v20; // [rsp+30h] [rbp-68h]
  __int128 v21; // [rsp+40h] [rbp-58h] BYREF

  v21 = 0;
  AcquireSRWLockShared(&g_SRWInstanceList);
  InstanceFromId = DpspGetInstanceFromId(a2 + 64, 0);
  v5 = InstanceFromId;
  if ( !InstanceFromId )
  {
    ReleaseSRWLockShared(&g_SRWInstanceList);
    v6 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
      (int)L"DpspClientOpenInstance",
      3794,
      (int)L"Error = %d",
      87);
LABEL_41:
    if ( a2 )
      *(_DWORD *)(a2 + 112) = v6;
    return v6;
  }
  v7 = 0;
  v8 = 0;
  _InterlockedIncrement((volatile signed __int32 *)(InstanceFromId + 72));
  v9 = DpspGetInstanceFromId(a2 + 128, 0);
  v10 = v9;
  if ( !v9 )
  {
    ReleaseSRWLockShared(&g_SRWInstanceList);
    v6 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
      (int)L"DpspClientOpenInstance",
      3811,
      (int)L"Error = %d",
      87);
    goto LABEL_38;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v9 + 72));
  ReleaseSRWLockShared(&g_SRWInstanceList);
  if ( _interlockedbittestandset((volatile signed __int32 *)(v5 + 104), 0xAu) )
  {
    v11 = 3831;
LABEL_37:
    v6 = -2147467259;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
      (int)L"DpspClientOpenInstance",
      v11,
      (int)L"Error = %d",
      5);
    goto LABEL_38;
  }
  v7 = 4;
  if ( _interlockedbittestandset((volatile signed __int32 *)(v10 + 104), 0xAu) )
  {
    v11 = 3843;
    goto LABEL_37;
  }
  v8 = 4;
  if ( (*(_DWORD *)(v5 + 104) & 0x20) != 0 )
  {
    v6 = -2147020579;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
      (int)L"DpspClientOpenInstance",
      3852,
      (int)L"Error = %d",
      221);
    goto LABEL_38;
  }
  if ( *(_QWORD *)(v5 + 96) != a1 )
  {
    v11 = 3861;
    goto LABEL_37;
  }
  if ( (*(_BYTE *)(a2 + 120) & 8) != 0 )
    _InterlockedOr((volatile signed __int32 *)(v5 + 104), 0x80u);
  if ( (*(_DWORD *)(v5 + 104) & 0x100) != 0 )
  {
    v6 = -2147020579;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
      (int)L"DpspClientOpenInstance",
      3875,
      (int)L"Error = %d",
      221);
    goto LABEL_38;
  }
  v12 = (HANDLE *)(v5 + 800);
  v13 = *(char **)(v5 + 800);
  if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v13);
    *v12 = 0;
  }
  Args = DpspRetrieveClientCredentials((RTL_SRWLOCK *)v5, a2, 0xEu, 0, (LPVOID)(v5 + 108), 0, v20, (PHANDLE)(v5 + 800));
  v6 = Args;
  if ( Args < 0 )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
      (int)L"DpspClientOpenInstance",
      3888,
      (int)L"Error = %d",
      Args);
    goto LABEL_38;
  }
  if ( *(_DWORD *)(v10 + 84) )
  {
    v11 = 3894;
    goto LABEL_37;
  }
  if ( *(_DWORD *)(v5 + 108) != *(_DWORD *)(v10 + 108) )
  {
    v6 = -2147024891;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
      (int)L"DpspClientOpenInstance",
      3903,
      (int)L"Error = %d",
      5);
    goto LABEL_38;
  }
  v15 = *(_QWORD *)(v10 + 1216);
  if ( !v15 )
  {
    v11 = 3911;
    goto LABEL_37;
  }
  v16 = DpspAccessCheck(*v12, *(PSECURITY_DESCRIPTOR *)(v15 + 32), 0x40000000u);
  v6 = v16;
  if ( v16 < 0 )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
      (int)L"DpspClientOpenInstance",
      3921,
      (int)L"Error = %d",
      v16);
    goto LABEL_38;
  }
  *(_DWORD *)(a2 + 124) = 208;
  v6 = DpspWriteOpenedInstanceToMessageBuffer(v10, a2);
  if ( (v6 & 0x80000000) != 0 )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
      (int)L"DpspClientOpenInstance",
      3932,
      (int)L"Error = %d",
      v6);
    goto LABEL_38;
  }
  AcquireSRWLockExclusive((PSRWLOCK)(v10 + 16));
  AcquireSRWLockExclusive((PSRWLOCK)(v5 + 16));
  if ( !*(_QWORD *)(v5 + 792) || (v17 = *(_QWORD *)(v10 + 792)) == 0 )
  {
    ReleaseSRWLockExclusive((PSRWLOCK)(v5 + 16));
    ReleaseSRWLockExclusive((PSRWLOCK)(v10 + 16));
    v11 = 3952;
    goto LABEL_37;
  }
  NtAlpcDisconnectPort(v17, 0);
  NtAlpcQueryInformation(*(_QWORD *)(v10 + 792), 0, &v21);
  *(_DWORD *)(v5 + 76) += DWORD1(v21);
  v18 = *(char **)(v10 + 792);
  if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v18);
    *(_QWORD *)(v10 + 792) = 0;
  }
  *(_QWORD *)(v10 + 792) = *(_QWORD *)(v5 + 792);
  *(_QWORD *)(v5 + 792) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)(v5 + 16));
  ReleaseSRWLockExclusive((PSRWLOCK)(v10 + 16));
  *(_QWORD *)(v10 + 96) = *(_QWORD *)(v5 + 96);
  DpspCloseInstance(v5, 7, 0, v6);
LABEL_38:
  DpspCloseInstance(v5, 7, v7, v6);
  if ( v10 )
    DpspCloseInstance(v10, 7, v8, v6);
  if ( (v6 & 0x80000000) != 0 )
    goto LABEL_41;
  return v6;
}

```

## disassembly

```asm
0x180002a08  push    rbx
0x180002a0a  push    rbp
0x180002a0b  push    rsi
0x180002a0c  push    rdi
0x180002a0d  push    r12
0x180002a0f  push    r13
0x180002a11  push    r14
0x180002a13  push    r15
0x180002a15  sub     rsp, 58h
0x180002a19  mov     rbx, rcx
0x180002a1c  lea     r14, g_SRWInstanceList
0x180002a23  xorps   xmm0, xmm0
0x180002a26  mov     rcx, r14; SRWLock
0x180002a29  mov     rbp, rdx
0x180002a2c  movups  [rsp+98h+var_58], xmm0
0x180002a31  call    cs:__imp_AcquireSRWLockShared
0x180002a37  lea     rcx, [rbp+40h]
0x180002a3b  xor     edx, edx
0x180002a3d  call    DpspGetInstanceFromId
0x180002a42  mov     rdi, rax
0x180002a45  test    rax, rax
0x180002a48  jnz     short loc_180002A85
0x180002a4a  mov     rcx, r14; SRWLock
0x180002a4d  call    cs:__imp_ReleaseSRWLockShared
0x180002a53  lea     r9, aErrorD; "Error = %d"
0x180002a5a  mov     dword ptr [rsp+98h+Args], 57h ; 'W'; Args
0x180002a62  mov     r8d, 0ED2h; int
0x180002a68  lea     rdx, aDpspclientopen; "DpspClientOpenInstance"
0x180002a6f  lea     rcx, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180002a76  mov     ebx, 80070057h
0x180002a7b  call    WdipTraceError
0x180002a80  jmp     loc_180002D9B
0x180002a85  xor     r12d, r12d
0x180002a88  xor     r13d, r13d
0x180002a8b  lock inc dword ptr [rax+48h]
0x180002a8f  lea     rcx, [rbp+80h]
0x180002a96  xor     edx, edx
0x180002a98  call    DpspGetInstanceFromId
0x180002a9d  mov     rsi, rax
0x180002aa0  mov     rcx, r14; SRWLock
0x180002aa3  test    rax, rax
0x180002aa6  jnz     short loc_180002AC6
0x180002aa8  call    cs:__imp_ReleaseSRWLockShared
0x180002aae  mov     r8d, 0EE3h
0x180002ab4  mov     dword ptr [rsp+98h+Args], 57h ; 'W'
0x180002abc  mov     ebx, 80070057h
0x180002ac1  jmp     loc_180002D52
0x180002ac6  lock inc dword ptr [rax+48h]
0x180002aca  call    cs:__imp_ReleaseSRWLockShared
0x180002ad0  lock bts dword ptr [rdi+68h], 0Ah
0x180002ad6  jnb     short loc_180002AE3
0x180002ad8  mov     r8d, 0EF7h
0x180002ade  jmp     loc_180002D45
0x180002ae3  lock bts dword ptr [rsi+68h], 0Ah
0x180002ae9  mov     r12d, 4
0x180002aef  jnb     short loc_180002AFC
0x180002af1  mov     r8d, 0F03h
0x180002af7  jmp     loc_180002D45
0x180002afc  mov     eax, [rdi+68h]
0x180002aff  mov     r13d, r12d
0x180002b02  test    al, 20h
0x180002b04  jz      short loc_180002B1E
0x180002b06  mov     ebx, 800710DDh
0x180002b0b  mov     dword ptr [rsp+98h+Args], 10DDh
0x180002b13  mov     r8d, 0F0Ch
0x180002b19  jmp     loc_180002D52
0x180002b1e  cmp     [rdi+60h], rbx
0x180002b22  jz      short loc_180002B2F
0x180002b24  mov     r8d, 0F15h
0x180002b2a  jmp     loc_180002D45
0x180002b2f  test    byte ptr [rbp+78h], 8
0x180002b33  jz      short loc_180002B3D
0x180002b35  lock or dword ptr [rdi+68h], 80h
0x180002b3d  mov     eax, [rdi+68h]
0x180002b40  bt      eax, 8
0x180002b44  jnb     short loc_180002B5E
0x180002b46  mov     ebx, 800710DDh
0x180002b4b  mov     dword ptr [rsp+98h+Args], 10DDh
0x180002b53  mov     r8d, 0F23h
0x180002b59  jmp     loc_180002D52
0x180002b5e  lea     r14, [rdi+320h]
0x180002b65  mov     rcx, [r14]; hObject
0x180002b68  lea     rax, [rcx-1]
0x180002b6c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002b70  ja      short loc_180002B7F
0x180002b72  call    cs:__imp_CloseHandle
0x180002b78  mov     qword ptr [r14], 0
0x180002b7f  xor     r9d, r9d
0x180002b82  mov     [rsp+98h+var_60], r14
0x180002b87  lea     r15, [rdi+6Ch]
0x180002b8b  mov     [rsp+98h+var_70], 0
0x180002b94  mov     rdx, rbp
0x180002b97  mov     qword ptr [rsp+98h+Args], r15
0x180002b9c  mov     rcx, rdi
0x180002b9f  lea     r8d, [r9+0Eh]
0x180002ba3  call    DpspRetrieveClientCredentials
0x180002ba8  mov     ebx, eax
0x180002baa  test    eax, eax
0x180002bac  jns     short loc_180002BC0
0x180002bae  movzx   eax, ax
0x180002bb1  mov     r8d, 0F30h
0x180002bb7  mov     dword ptr [rsp+98h+Args], eax
0x180002bbb  jmp     loc_180002D52
0x180002bc0  cmp     dword ptr [rsi+54h], 0
0x180002bc4  jz      short loc_180002BD1
0x180002bc6  mov     r8d, 0F36h
0x180002bcc  jmp     loc_180002D45
0x180002bd1  mov     eax, [rsi+6Ch]
0x180002bd4  cmp     [r15], eax
0x180002bd7  jz      short loc_180002BF1
0x180002bd9  mov     ebx, 80070005h
0x180002bde  mov     dword ptr [rsp+98h+Args], 5
0x180002be6  mov     r8d, 0F3Fh
0x180002bec  jmp     loc_180002D52
0x180002bf1  mov     rdx, [rsi+4C0h]
0x180002bf8  test    rdx, rdx
0x180002bfb  jnz     short loc_180002C08
0x180002bfd  mov     r8d, 0F47h
0x180002c03  jmp     loc_180002D45
0x180002c08  mov     rdx, [rdx+20h]; pSecurityDescriptor
0x180002c0c  mov     r8d, 40000000h
0x180002c12  mov     rcx, [r14]; ClientToken
0x180002c15  call    DpspAccessCheck
0x180002c1a  mov     ebx, eax
0x180002c1c  test    eax, eax
0x180002c1e  jns     short loc_180002C32
0x180002c20  movzx   eax, ax
0x180002c23  mov     r8d, 0F51h
0x180002c29  mov     dword ptr [rsp+98h+Args], eax
0x180002c2d  jmp     loc_180002D52
0x180002c32  mov     rdx, rbp
0x180002c35  mov     dword ptr [rbp+7Ch], 0D0h
0x180002c3c  mov     rcx, rsi
0x180002c3f  call    DpspWriteOpenedInstanceToMessageBuffer
0x180002c44  mov     ebx, eax
0x180002c46  test    eax, eax
0x180002c48  jns     short loc_180002C5C
0x180002c4a  movzx   eax, bx
0x180002c4d  mov     r8d, 0F5Ch
0x180002c53  mov     dword ptr [rsp+98h+Args], eax
0x180002c57  jmp     loc_180002D52
0x180002c5c  lea     rcx, [rsi+10h]; SRWLock
0x180002c60  call    cs:__imp_AcquireSRWLockExclusive
0x180002c66  lea     rcx, [rdi+10h]; SRWLock
0x180002c6a  call    cs:__imp_AcquireSRWLockExclusive
0x180002c70  cmp     qword ptr [rdi+318h], 0
0x180002c78  jz      loc_180002D2B
0x180002c7e  mov     rcx, [rsi+318h]
0x180002c85  test    rcx, rcx
0x180002c88  jz      loc_180002D2B
0x180002c8e  xor     edx, edx
0x180002c90  call    cs:__imp_NtAlpcDisconnectPort
0x180002c96  mov     rcx, [rsi+318h]
0x180002c9d  lea     r8, [rsp+98h+var_58]
0x180002ca2  mov     r9d, 10h
0x180002ca8  mov     qword ptr [rsp+98h+Args], 0
0x180002cb1  xor     edx, edx
0x180002cb3  call    cs:__imp_NtAlpcQueryInformation
0x180002cb9  mov     eax, dword ptr [rsp+98h+var_58+4]
0x180002cbd  add     [rdi+4Ch], eax
0x180002cc0  mov     rcx, [rsi+318h]; hObject
0x180002cc7  lea     rax, [rcx-1]
0x180002ccb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002ccf  ja      short loc_180002CE2
0x180002cd1  call    cs:__imp_CloseHandle
0x180002cd7  mov     qword ptr [rsi+318h], 0
0x180002ce2  mov     rax, [rdi+318h]
0x180002ce9  lea     rcx, [rdi+10h]; SRWLock
0x180002ced  mov     [rsi+318h], rax
0x180002cf4  mov     qword ptr [rdi+318h], 0
0x180002cff  call    cs:__imp_ReleaseSRWLockExclusive
0x180002d05  lea     rcx, [rsi+10h]; SRWLock
0x180002d09  call    cs:__imp_ReleaseSRWLockExclusive
0x180002d0f  mov     rax, [rdi+60h]
0x180002d13  xor     r8d, r8d
0x180002d16  mov     r9d, ebx
0x180002d19  mov     [rsi+60h], rax
0x180002d1d  mov     rcx, rdi
0x180002d20  lea     edx, [r8+7]
0x180002d24  call    DpspCloseInstance
0x180002d29  jmp     short loc_180002D6C
0x180002d2b  lea     rcx, [rdi+10h]; SRWLock
0x180002d2f  call    cs:__imp_ReleaseSRWLockExclusive
0x180002d35  lea     rcx, [rsi+10h]; SRWLock
0x180002d39  call    cs:__imp_ReleaseSRWLockExclusive
0x180002d3f  mov     r8d, 0F70h; int
0x180002d45  mov     dword ptr [rsp+98h+Args], 4005h; Args
0x180002d4d  mov     ebx, 80004005h
0x180002d52  lea     r9, aErrorD; "Error = %d"
0x180002d59  lea     rdx, aDpspclientopen; "DpspClientOpenInstance"
0x180002d60  lea     rcx, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180002d67  call    WdipTraceError
0x180002d6c  mov     r9d, ebx
0x180002d6f  mov     r8d, r12d
0x180002d72  mov     edx, 7
0x180002d77  mov     rcx, rdi
0x180002d7a  call    DpspCloseInstance
0x180002d7f  test    rsi, rsi
0x180002d82  jz      short loc_180002D97
0x180002d84  mov     r9d, ebx
0x180002d87  mov     r8d, r13d
0x180002d8a  mov     edx, 7
0x180002d8f  mov     rcx, rsi
0x180002d92  call    DpspCloseInstance
0x180002d97  test    ebx, ebx
0x180002d99  jns     short loc_180002DA3
0x180002d9b  test    rbp, rbp
0x180002d9e  jz      short loc_180002DA3
0x180002da0  mov     [rbp+70h], ebx
0x180002da3  mov     eax, ebx
0x180002da5  add     rsp, 58h
0x180002da9  pop     r15
0x180002dab  pop     r14
0x180002dad  pop     r13
0x180002daf  pop     r12
0x180002db1  pop     rdi
0x180002db2  pop     rsi
0x180002db3  pop     rbp
0x180002db4  pop     rbx
0x180002db5  retn
```
