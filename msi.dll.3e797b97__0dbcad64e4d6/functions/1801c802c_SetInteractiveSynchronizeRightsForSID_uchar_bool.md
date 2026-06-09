# SetInteractiveSynchronizeRightsForSID(uchar *,bool)

- ea: `0x1801c802c`
- end: `0x1801c8278`
- name: `?SetInteractiveSynchronizeRightsForSID@@YA_NPEAE_N@Z`
- size: `588`
- prototype: `bool __fastcall(unsigned __int8 *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1801629b4`

## callees

- `0x18000c4bc`
- `0x180014528`
- `0x180067fec`
- `0x1801c802c`
- `0x180266010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1801c821e`
- `KERNEL32!CloseHandle` at `0x1801c821e`
- `KERNEL32!GetLastError` at `0x1801c8092`
- `KERNEL32!GetLastError` at `0x1801c8092`
- `KERNEL32!LocalFree` at `0x1801c8233`
- `KERNEL32!LocalFree` at `0x1801c8248`
- `KERNEL32!LocalFree` at `0x1801c8233`
- `KERNEL32!LocalFree` at `0x1801c8248`
- `KERNEL32!GetCurrentProcessId` at `0x1801c8068`
- `KERNEL32!GetCurrentProcessId` at `0x1801c8068`
- `KERNEL32!OpenProcess` at `0x1801c807e`
- `KERNEL32!OpenProcess` at `0x1801c807e`

## string_xrefs

- `0x1801c813b`: `Unable to obtain process security information. Return code 0x%08x.`
- `0x1801c8190`: `ACL Creation for non-admin Synchronize rights failed with code 0x%08x.`
- `0x1801c81d3`: `Unable to set process security information. Return code 0x%08x.`

## pseudocode

```c
char __fastcall SetInteractiveSynchronizeRightsForSID(unsigned __int8 *a1)
{
  char v2; // bl
  DWORD CurrentProcessId; // eax
  HANDLE v4; // rax
  void *v5; // rdi
  DWORD LastError; // eax
  unsigned int v7; // eax
  const unsigned __int16 *v8; // r9
  _BYTE v10[8]; // [rsp+68h] [rbp+Fh] BYREF
  _DWORD v11[2]; // [rsp+70h] [rbp+17h] BYREF
  __int64 v12; // [rsp+78h] [rbp+1Fh]
  __int64 v13; // [rsp+80h] [rbp+27h]
  __int64 v14; // [rsp+88h] [rbp+2Fh]
  __int64 v15; // [rsp+90h] [rbp+37h]
  unsigned __int8 *v16; // [rsp+98h] [rbp+3Fh]
  HLOCAL v17; // [rsp+D0h] [rbp+77h] BYREF
  __int64 v18; // [rsp+D8h] [rbp+7Fh]

  v2 = 1;
  CElevate::CElevate((CElevate *)v10, 1);
  v17 = 0;
  v18 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v4 = OpenProcess(0x1FFFFFu, 1, CurrentProcessId);
  v5 = v4;
  if ( v4 )
  {
    v7 = ((__int64 (__fastcall *)(HANDLE, __int64, __int64))ADVAPI32::GetSecurityInfo)(v4, 6, 4);
    if ( v7 )
    {
      if ( g_dmDiagnosticMode )
      {
        v8 = L"Unable to obtain process security information. Return code 0x%08x.";
LABEL_14:
        DebugString(
          9,
          0,
          0,
          v8,
          (const unsigned __int16 *)v7,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
    }
    else
    {
      v12 = 0;
      v15 = 1;
      v11[0] = 0x100000;
      v11[1] = 1;
      v13 = 0;
      v14 = 0;
      v16 = a1;
      v7 = ((__int64 (__fastcall *)(__int64, _DWORD *, __int64, HLOCAL *))ADVAPI32::SetEntriesInAclW)(1, v11, v18, &v17);
      if ( v7 )
      {
        if ( g_dmDiagnosticMode )
        {
          v8 = L"ACL Creation for non-admin Synchronize rights failed with code 0x%08x.";
          goto LABEL_14;
        }
      }
      else
      {
        v7 = ((__int64 (__fastcall *)(void *, __int64, __int64))ADVAPI32::SetSecurityInfo)(v5, 6, 4);
        if ( !v7 )
        {
LABEL_16:
          CloseHandle(v5);
          goto LABEL_17;
        }
        if ( g_dmDiagnosticMode )
        {
          v8 = L"Unable to set process security information. Return code 0x%08x.";
          goto LABEL_14;
        }
      }
    }
    v2 = 0;
    goto LABEL_16;
  }
  LastError = GetLastError();
  if ( g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      L"Unable to get a handle to the current process. Return code 0x%08x.",
      (const unsigned __int16 *)LastError,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  v2 = 0;
LABEL_17:
  if ( v17 )
    LocalFree(v17);
  CElevate::~CElevate((CElevate *)v10);
  return v2;
}

```

## disassembly

```asm
0x1801c802c  mov     [rsp-8+arg_0], rbx
0x1801c8031  mov     [rsp-8+arg_8], rsi
0x1801c8036  push    rbp
0x1801c8037  push    rdi
0x1801c8038  push    r14
0x1801c803a  lea     rbp, [rsp-47h]
0x1801c803f  sub     rsp, 0A0h
0x1801c8046  mov     rsi, rcx
0x1801c8049  mov     ebx, 1
0x1801c804e  mov     dl, bl; bool
0x1801c8050  lea     rcx, [rbp+57h+var_48]; this
0x1801c8054  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x1801c8059  xor     r14d, r14d
0x1801c805c  mov     [rbp+57h+arg_10], r14
0x1801c8060  mov     [rbp+57h+arg_18], r14
0x1801c8064  mov     [rbp+57h+hMem], r14
0x1801c8068  call    cs:__imp_GetCurrentProcessId
0x1801c806f  nop     dword ptr [rax+rax+00h]
0x1801c8074  mov     edx, ebx; bInheritHandle
0x1801c8076  mov     ecx, 1FFFFFh; dwDesiredAccess
0x1801c807b  mov     r8d, eax; dwProcessId
0x1801c807e  call    cs:__imp_OpenProcess
0x1801c8085  nop     dword ptr [rax+rax+00h]
0x1801c808a  mov     rdi, rax
0x1801c808d  test    rax, rax
0x1801c8090  jnz     short loc_1801C80F4
0x1801c8092  call    cs:__imp_GetLastError
0x1801c8099  nop     dword ptr [rax+rax+00h]
0x1801c809e  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x1801c80a5  jz      short loc_1801C80EC
0x1801c80a7  mov     [rsp+0B0h+var_58], r14; void *
0x1801c80ac  lea     rcx, aNull; "(NULL)"
0x1801c80b3  mov     [rsp+0B0h+var_60], r14d; unsigned int
0x1801c80b8  lea     r9, aUnableToGetAHa; "Unable to get a handle to the current p"...
0x1801c80bf  mov     [rsp+0B0h+var_68], rcx; unsigned __int16 *
0x1801c80c4  xor     edx, edx; unsigned __int16
0x1801c80c6  mov     [rsp+0B0h+var_70], rcx; unsigned __int16 *
0x1801c80cb  xor     r8d, r8d; int
0x1801c80ce  mov     [rsp+0B0h+var_78], rcx; unsigned __int16 *
0x1801c80d3  mov     [rsp+0B0h+var_80], rcx; unsigned __int16 *
0x1801c80d8  mov     [rsp+0B0h+var_88], rcx; unsigned __int16 *
0x1801c80dd  lea     ecx, [rbx+8]; int
0x1801c80e0  mov     eax, eax
0x1801c80e2  mov     [rsp+0B0h+var_90], rax; unsigned __int16 *
0x1801c80e7  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801c80ec  mov     bl, r14b
0x1801c80ef  jmp     loc_1801C822A
0x1801c80f4  xor     r9d, r9d
0x1801c80f7  lea     rax, [rbp+57h+hMem]
0x1801c80fb  mov     [rsp+0B0h+var_78], rax
0x1801c8100  mov     rcx, rdi
0x1801c8103  lea     rax, [rbp+57h+arg_18]
0x1801c8107  mov     [rsp+0B0h+var_80], r14
0x1801c810c  mov     [rsp+0B0h+var_88], rax
0x1801c8111  mov     rax, cs:?GetSecurityInfo@ADVAPI32@@3P6AKPEAXW4_SE_OBJECT_TYPE@@KPEAPEAX2PEAPEAU_ACL@@32@ZEA; ulong (*ADVAPI32::GetSecurityInfo)(void *,_SE_OBJECT_TYPE,ulong,void * *,void * *,_ACL * *,_ACL * *,void * *)
0x1801c8118  lea     edx, [r9+6]
0x1801c811c  lea     r8d, [r9+4]
0x1801c8120  mov     [rsp+0B0h+var_90], r14
0x1801c8125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c812a  test    eax, eax
0x1801c812c  jz      short loc_1801C8147
0x1801c812e  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x1801c8135  jz      loc_1801C8218
0x1801c813b  lea     r9, aUnableToObtain_1; "Unable to obtain process security infor"...
0x1801c8142  jmp     loc_1801C81DA
0x1801c8147  mov     r8, [rbp+57h+arg_18]
0x1801c814b  lea     r9, [rbp+57h+arg_10]
0x1801c814f  mov     rax, cs:?SetEntriesInAclW@ADVAPI32@@3P6AKKPEAU_EXPLICIT_ACCESS_W@@PEAU_ACL@@PEAPEAU3@@ZEA; ulong (*ADVAPI32::SetEntriesInAclW)(ulong,_EXPLICIT_ACCESS_W *,_ACL *,_ACL * *)
0x1801c8156  lea     rdx, [rbp+57h+var_40]
0x1801c815a  mov     ecx, ebx
0x1801c815c  mov     [rbp+57h+var_38], r14
0x1801c8160  mov     [rbp+57h+var_20], rbx
0x1801c8164  mov     [rbp+57h+var_40], 100000h
0x1801c816b  mov     [rbp+57h+var_3C], ebx
0x1801c816e  mov     [rbp+57h+var_30], r14
0x1801c8172  mov     [rbp+57h+var_28], r14
0x1801c8176  mov     [rbp+57h+var_18], rsi
0x1801c817a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c817f  test    eax, eax
0x1801c8181  jz      short loc_1801C8199
0x1801c8183  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x1801c818a  jz      loc_1801C8218
0x1801c8190  lea     r9, aAclCreationFor; "ACL Creation for non-admin Synchronize "...
0x1801c8197  jmp     short loc_1801C81DA
0x1801c8199  mov     rax, [rbp+57h+arg_10]
0x1801c819d  xor     r9d, r9d
0x1801c81a0  mov     [rsp+0B0h+var_80], r14
0x1801c81a5  mov     rcx, rdi
0x1801c81a8  mov     [rsp+0B0h+var_88], rax
0x1801c81ad  mov     rax, cs:?SetSecurityInfo@ADVAPI32@@3P6AKPEAXW4_SE_OBJECT_TYPE@@K00PEAU_ACL@@2@ZEA; ulong (*ADVAPI32::SetSecurityInfo)(void *,_SE_OBJECT_TYPE,ulong,void *,void *,_ACL *,_ACL *)
0x1801c81b4  lea     edx, [r9+6]
0x1801c81b8  mov     [rsp+0B0h+var_90], r14
0x1801c81bd  lea     r8d, [r9+4]
0x1801c81c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c81c6  test    eax, eax
0x1801c81c8  jz      short loc_1801C821B
0x1801c81ca  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x1801c81d1  jz      short loc_1801C8218
0x1801c81d3  lea     r9, aUnableToSetPro; "Unable to set process security informat"...
0x1801c81da  mov     [rsp+0B0h+var_58], r14; void *
0x1801c81df  lea     rcx, aNull; "(NULL)"
0x1801c81e6  mov     [rsp+0B0h+var_60], r14d; unsigned int
0x1801c81eb  xor     edx, edx; unsigned __int16
0x1801c81ed  mov     [rsp+0B0h+var_68], rcx; unsigned __int16 *
0x1801c81f2  xor     r8d, r8d; int
0x1801c81f5  mov     [rsp+0B0h+var_70], rcx; unsigned __int16 *
0x1801c81fa  mov     [rsp+0B0h+var_78], rcx; unsigned __int16 *
0x1801c81ff  mov     [rsp+0B0h+var_80], rcx; unsigned __int16 *
0x1801c8204  mov     [rsp+0B0h+var_88], rcx; unsigned __int16 *
0x1801c8209  lea     ecx, [rdx+9]; int
0x1801c820c  mov     eax, eax
0x1801c820e  mov     [rsp+0B0h+var_90], rax; unsigned __int16 *
0x1801c8213  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801c8218  mov     bl, r14b
0x1801c821b  mov     rcx, rdi; hObject
0x1801c821e  call    cs:__imp_CloseHandle
0x1801c8225  nop     dword ptr [rax+rax+00h]
0x1801c822a  mov     rcx, [rbp+57h+hMem]; hMem
0x1801c822e  test    rcx, rcx
0x1801c8231  jz      short loc_1801C823F
0x1801c8233  call    cs:__imp_LocalFree
0x1801c823a  nop     dword ptr [rax+rax+00h]
0x1801c823f  mov     rcx, [rbp+57h+arg_10]; hMem
0x1801c8243  test    rcx, rcx
0x1801c8246  jz      short loc_1801C8254
0x1801c8248  call    cs:__imp_LocalFree
0x1801c824f  nop     dword ptr [rax+rax+00h]
0x1801c8254  lea     rcx, [rbp+57h+var_48]; this
0x1801c8258  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x1801c825d  lea     r11, [rsp+0B0h+var_10]
0x1801c8265  mov     al, bl
0x1801c8267  mov     rbx, [r11+20h]
0x1801c826b  mov     rsi, [r11+28h]
0x1801c826f  mov     rsp, r11
0x1801c8272  pop     r14
0x1801c8274  pop     rdi
0x1801c8275  pop     rbp
0x1801c8276  retn
```
