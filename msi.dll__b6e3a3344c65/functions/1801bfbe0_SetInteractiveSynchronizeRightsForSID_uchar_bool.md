# SetInteractiveSynchronizeRightsForSID(uchar *,bool)

- ea: `0x1801bfbe0`
- end: `0x1801bfe07`
- name: `?SetInteractiveSynchronizeRightsForSID@@YA_NPEAE_N@Z`
- size: `551`
- prototype: `bool __fastcall(unsigned __int8 *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18015cd14`

## callees

- `0x180025904`
- `0x180025a18`
- `0x180068680`
- `0x1801bfbe0`
- `0x18025c010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1801bfdc0`
- `KERNEL32!CloseHandle` at `0x1801bfdc0`
- `KERNEL32!GetLastError` at `0x1801bfc3a`
- `KERNEL32!GetLastError` at `0x1801bfc3a`
- `KERNEL32!LocalFree` at `0x1801bfdcf`
- `KERNEL32!LocalFree` at `0x1801bfdde`
- `KERNEL32!LocalFree` at `0x1801bfdcf`
- `KERNEL32!LocalFree` at `0x1801bfdde`
- `KERNEL32!GetCurrentProcessId` at `0x1801bfc1c`
- `KERNEL32!GetCurrentProcessId` at `0x1801bfc1c`
- `KERNEL32!OpenProcess` at `0x1801bfc2c`
- `KERNEL32!OpenProcess` at `0x1801bfc2c`

## string_xrefs

- `0x1801bfcdd`: `Unable to obtain process security information. Return code 0x%08x.`
- `0x1801bfd32`: `ACL Creation for non-admin Synchronize rights failed with code 0x%08x.`
- `0x1801bfd75`: `Unable to set process security information. Return code 0x%08x.`

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
0x1801bfbe0  mov     [rsp-8+arg_0], rbx
0x1801bfbe5  mov     [rsp-8+arg_8], rsi
0x1801bfbea  push    rbp
0x1801bfbeb  push    rdi
0x1801bfbec  push    r14
0x1801bfbee  lea     rbp, [rsp-47h]
0x1801bfbf3  sub     rsp, 0A0h
0x1801bfbfa  mov     rsi, rcx
0x1801bfbfd  mov     ebx, 1
0x1801bfc02  mov     dl, bl; bool
0x1801bfc04  lea     rcx, [rbp+57h+var_48]; this
0x1801bfc08  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x1801bfc0d  xor     r14d, r14d
0x1801bfc10  mov     [rbp+57h+arg_10], r14
0x1801bfc14  mov     [rbp+57h+arg_18], r14
0x1801bfc18  mov     [rbp+57h+hMem], r14
0x1801bfc1c  call    cs:__imp_GetCurrentProcessId
0x1801bfc22  mov     edx, ebx; bInheritHandle
0x1801bfc24  mov     ecx, 1FFFFFh; dwDesiredAccess
0x1801bfc29  mov     r8d, eax; dwProcessId
0x1801bfc2c  call    cs:__imp_OpenProcess
0x1801bfc32  mov     rdi, rax
0x1801bfc35  test    rax, rax
0x1801bfc38  jnz     short loc_1801BFC96
0x1801bfc3a  call    cs:__imp_GetLastError
0x1801bfc40  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x1801bfc47  jz      short loc_1801BFC8E
0x1801bfc49  mov     [rsp+0B0h+var_58], r14; void *
0x1801bfc4e  lea     rcx, aNull; "(NULL)"
0x1801bfc55  mov     [rsp+0B0h+var_60], r14d; unsigned int
0x1801bfc5a  lea     r9, aUnableToGetAHa; "Unable to get a handle to the current p"...
0x1801bfc61  mov     [rsp+0B0h+var_68], rcx; unsigned __int16 *
0x1801bfc66  xor     edx, edx; unsigned __int16
0x1801bfc68  mov     [rsp+0B0h+var_70], rcx; unsigned __int16 *
0x1801bfc6d  xor     r8d, r8d; int
0x1801bfc70  mov     [rsp+0B0h+var_78], rcx; unsigned __int16 *
0x1801bfc75  mov     [rsp+0B0h+var_80], rcx; unsigned __int16 *
0x1801bfc7a  mov     [rsp+0B0h+var_88], rcx; unsigned __int16 *
0x1801bfc7f  lea     ecx, [rbx+8]; int
0x1801bfc82  mov     eax, eax
0x1801bfc84  mov     [rsp+0B0h+var_90], rax; unsigned __int16 *
0x1801bfc89  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801bfc8e  mov     bl, r14b
0x1801bfc91  jmp     loc_1801BFDC6
0x1801bfc96  xor     r9d, r9d
0x1801bfc99  lea     rax, [rbp+57h+hMem]
0x1801bfc9d  mov     [rsp+0B0h+var_78], rax
0x1801bfca2  mov     rcx, rdi
0x1801bfca5  lea     rax, [rbp+57h+arg_18]
0x1801bfca9  mov     [rsp+0B0h+var_80], r14
0x1801bfcae  mov     [rsp+0B0h+var_88], rax
0x1801bfcb3  mov     rax, cs:?GetSecurityInfo@ADVAPI32@@3P6AKPEAXW4_SE_OBJECT_TYPE@@KPEAPEAX2PEAPEAU_ACL@@32@ZEA; ulong (*ADVAPI32::GetSecurityInfo)(void *,_SE_OBJECT_TYPE,ulong,void * *,void * *,_ACL * *,_ACL * *,void * *)
0x1801bfcba  lea     edx, [r9+6]
0x1801bfcbe  lea     r8d, [r9+4]
0x1801bfcc2  mov     [rsp+0B0h+var_90], r14
0x1801bfcc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bfccc  test    eax, eax
0x1801bfcce  jz      short loc_1801BFCE9
0x1801bfcd0  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x1801bfcd7  jz      loc_1801BFDBA
0x1801bfcdd  lea     r9, aUnableToObtain_1; "Unable to obtain process security infor"...
0x1801bfce4  jmp     loc_1801BFD7C
0x1801bfce9  mov     r8, [rbp+57h+arg_18]
0x1801bfced  lea     r9, [rbp+57h+arg_10]
0x1801bfcf1  mov     rax, cs:?SetEntriesInAclW@ADVAPI32@@3P6AKKPEAU_EXPLICIT_ACCESS_W@@PEAU_ACL@@PEAPEAU3@@ZEA; ulong (*ADVAPI32::SetEntriesInAclW)(ulong,_EXPLICIT_ACCESS_W *,_ACL *,_ACL * *)
0x1801bfcf8  lea     rdx, [rbp+57h+var_40]
0x1801bfcfc  mov     ecx, ebx
0x1801bfcfe  mov     [rbp+57h+var_38], r14
0x1801bfd02  mov     [rbp+57h+var_20], rbx
0x1801bfd06  mov     [rbp+57h+var_40], 100000h
0x1801bfd0d  mov     [rbp+57h+var_3C], ebx
0x1801bfd10  mov     [rbp+57h+var_30], r14
0x1801bfd14  mov     [rbp+57h+var_28], r14
0x1801bfd18  mov     [rbp+57h+var_18], rsi
0x1801bfd1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bfd21  test    eax, eax
0x1801bfd23  jz      short loc_1801BFD3B
0x1801bfd25  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x1801bfd2c  jz      loc_1801BFDBA
0x1801bfd32  lea     r9, aAclCreationFor; "ACL Creation for non-admin Synchronize "...
0x1801bfd39  jmp     short loc_1801BFD7C
0x1801bfd3b  mov     rax, [rbp+57h+arg_10]
0x1801bfd3f  xor     r9d, r9d
0x1801bfd42  mov     [rsp+0B0h+var_80], r14
0x1801bfd47  mov     rcx, rdi
0x1801bfd4a  mov     [rsp+0B0h+var_88], rax
0x1801bfd4f  mov     rax, cs:?SetSecurityInfo@ADVAPI32@@3P6AKPEAXW4_SE_OBJECT_TYPE@@K00PEAU_ACL@@2@ZEA; ulong (*ADVAPI32::SetSecurityInfo)(void *,_SE_OBJECT_TYPE,ulong,void *,void *,_ACL *,_ACL *)
0x1801bfd56  lea     edx, [r9+6]
0x1801bfd5a  mov     [rsp+0B0h+var_90], r14
0x1801bfd5f  lea     r8d, [r9+4]
0x1801bfd63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bfd68  test    eax, eax
0x1801bfd6a  jz      short loc_1801BFDBD
0x1801bfd6c  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x1801bfd73  jz      short loc_1801BFDBA
0x1801bfd75  lea     r9, aUnableToSetPro; "Unable to set process security informat"...
0x1801bfd7c  mov     [rsp+0B0h+var_58], r14; void *
0x1801bfd81  lea     rcx, aNull; "(NULL)"
0x1801bfd88  mov     [rsp+0B0h+var_60], r14d; unsigned int
0x1801bfd8d  xor     edx, edx; unsigned __int16
0x1801bfd8f  mov     [rsp+0B0h+var_68], rcx; unsigned __int16 *
0x1801bfd94  xor     r8d, r8d; int
0x1801bfd97  mov     [rsp+0B0h+var_70], rcx; unsigned __int16 *
0x1801bfd9c  mov     [rsp+0B0h+var_78], rcx; unsigned __int16 *
0x1801bfda1  mov     [rsp+0B0h+var_80], rcx; unsigned __int16 *
0x1801bfda6  mov     [rsp+0B0h+var_88], rcx; unsigned __int16 *
0x1801bfdab  lea     ecx, [rdx+9]; int
0x1801bfdae  mov     eax, eax
0x1801bfdb0  mov     [rsp+0B0h+var_90], rax; unsigned __int16 *
0x1801bfdb5  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801bfdba  mov     bl, r14b
0x1801bfdbd  mov     rcx, rdi; hObject
0x1801bfdc0  call    cs:__imp_CloseHandle
0x1801bfdc6  mov     rcx, [rbp+57h+hMem]; hMem
0x1801bfdca  test    rcx, rcx
0x1801bfdcd  jz      short loc_1801BFDD5
0x1801bfdcf  call    cs:__imp_LocalFree
0x1801bfdd5  mov     rcx, [rbp+57h+arg_10]; hMem
0x1801bfdd9  test    rcx, rcx
0x1801bfddc  jz      short loc_1801BFDE4
0x1801bfdde  call    cs:__imp_LocalFree
0x1801bfde4  lea     rcx, [rbp+57h+var_48]; this
0x1801bfde8  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x1801bfded  lea     r11, [rsp+0B0h+var_10]
0x1801bfdf5  mov     al, bl
0x1801bfdf7  mov     rbx, [r11+20h]
0x1801bfdfb  mov     rsi, [r11+28h]
0x1801bfdff  mov     rsp, r11
0x1801bfe02  pop     r14
0x1801bfe04  pop     rdi
0x1801bfe05  pop     rbp
0x1801bfe06  retn
```
