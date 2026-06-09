# ReproduceRAFailure(_GUID *)

- ea: `0x180011c10`
- end: `0x180011df1`
- name: `?ReproduceRAFailure@@YAJPEAU_GUID@@@Z`
- size: `481`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000eea0`

## callees

- `0x180011c10`
- `0x180014660`
- `0x180014ee0`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180011d2a`
- `KERNEL32!SetEvent` at `0x180011d2a`
- `KERNEL32!OpenEventW` at `0x180011cc8`
- `KERNEL32!OpenEventW` at `0x180011d11`
- `KERNEL32!OpenEventW` at `0x180011cc8`
- `KERNEL32!OpenEventW` at `0x180011d11`
- `KERNEL32!GetProcessHeap` at `0x180011d91`
- `KERNEL32!GetProcessHeap` at `0x180011dac`
- `KERNEL32!GetProcessHeap` at `0x180011d91`
- `KERNEL32!GetProcessHeap` at `0x180011dac`
- `KERNEL32!CloseHandle` at `0x180011dc8`
- `KERNEL32!CloseHandle` at `0x180011dd6`
- `KERNEL32!CloseHandle` at `0x180011dc8`
- `KERNEL32!CloseHandle` at `0x180011dd6`
- `KERNEL32!HeapFree` at `0x180011da1`
- `KERNEL32!HeapFree` at `0x180011dba`
- `KERNEL32!HeapFree` at `0x180011da1`
- `KERNEL32!HeapFree` at `0x180011dba`
- `KERNEL32!WaitForSingleObject` at `0x180011d54`
- `KERNEL32!WaitForSingleObject` at `0x180011d54`

## pseudocode

```c
__int64 __fastcall ReproduceRAFailure(struct _GUID *a1)
{
  WCHAR *v2; // rdi
  HANDLE v3; // rsi
  HANDLE v4; // rbp
  signed int UniqueName; // eax
  const struct _EVENT_DESCRIPTOR *v6; // rdx
  CEventLogger *v7; // rcx
  unsigned int v8; // ebx
  signed int v9; // eax
  const struct _EVENT_DESCRIPTOR *v10; // rdx
  CEventLogger *v11; // rcx
  const struct _EVENT_DESCRIPTOR *v12; // rdx
  CEventLogger *v13; // rcx
  const struct _EVENT_DESCRIPTOR *v14; // rdx
  CEventLogger *v15; // rcx
  unsigned int v16; // r9d
  const struct _EVENT_DESCRIPTOR *v17; // rdx
  CEventLogger *v18; // rcx
  HANDLE ProcessHeap; // rax
  HANDLE v20; // rax
  LPCWSTR v22; // [rsp+58h] [rbp+10h] BYREF
  LPCWSTR lpName; // [rsp+60h] [rbp+18h] BYREF

  lpName = 0;
  v2 = 0;
  v22 = 0;
  v3 = 0;
  v4 = 0;
  UniqueName = GenerateUniqueName(L"Global\\RADiagEvent-ReproStart", a1, (unsigned __int16 **)&lpName);
  v8 = UniqueName;
  if ( UniqueName < 0 )
  {
    CEventLogger::LogError(
      v7,
      v6,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      0x3D5u,
      L"ReproduceRAFailure",
      UniqueName);
    goto LABEL_16;
  }
  v9 = GenerateUniqueName(L"Global\\RADiagEvent-ReproDone", a1, (unsigned __int16 **)&v22);
  v8 = v9;
  if ( v9 < 0 )
  {
    CEventLogger::LogError(
      v11,
      v10,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      0x3DAu,
      L"ReproduceRAFailure",
      v9);
    v2 = (WCHAR *)v22;
    goto LABEL_16;
  }
  v3 = OpenEventW(2u, 0, lpName);
  if ( !v3 )
  {
    CEventLogger::LogError(
      v13,
      v12,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      0x3E4u,
      L"ReproduceRAFailure",
      0);
    v2 = (WCHAR *)v22;
LABEL_15:
    v8 = -2147467259;
    goto LABEL_16;
  }
  v2 = (WCHAR *)v22;
  v4 = OpenEventW(0x100000u, 0, v22);
  if ( !v4 )
  {
    v16 = 1001;
LABEL_14:
    CEventLogger::LogError(
      v15,
      v14,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      v16,
      L"ReproduceRAFailure",
      0);
    goto LABEL_15;
  }
  if ( !SetEvent(v3) )
  {
    v8 = -2147467259;
    CEventLogger::LogError(
      v18,
      v17,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      0x3F0u,
      L"ReproduceRAFailure",
      0x80004005);
    goto LABEL_16;
  }
  if ( WaitForSingleObject(v4, 0x927C0u) )
  {
    v16 = 1019;
    goto LABEL_14;
  }
LABEL_16:
  if ( lpName )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)lpName);
  }
  if ( v2 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v2);
  }
  if ( v3 )
    CloseHandle(v3);
  if ( v4 )
    CloseHandle(v4);
  return v8;
}

```

## disassembly

```asm
0x180011c10  mov     rax, rsp
0x180011c13  mov     [rax+8], rbx
0x180011c17  mov     [rax+20h], rbp
0x180011c1b  push    rsi
0x180011c1c  push    rdi
0x180011c1d  push    r14
0x180011c1f  sub     rsp, 30h
0x180011c23  mov     r14, rcx
0x180011c26  mov     qword ptr [rax+18h], 0
0x180011c2e  mov     rdx, rcx; struct _GUID *
0x180011c31  lea     r8, [rax+18h]; unsigned __int16 **
0x180011c35  xor     edi, edi
0x180011c37  lea     rcx, aGlobalRadiagev; "Global\\RADiagEvent-ReproStart"
0x180011c3e  mov     [rax+10h], rdi
0x180011c42  xor     esi, esi
0x180011c44  xor     ebp, ebp
0x180011c46  call    ?GenerateUniqueName@@YAJPEAGPEAU_GUID@@PEAPEAG@Z; GenerateUniqueName(ushort *,_GUID *,ushort * *)
0x180011c4b  mov     ebx, eax
0x180011c4d  test    eax, eax
0x180011c4f  jns     short loc_180011C78
0x180011c51  mov     [rsp+48h+var_20], eax; unsigned int
0x180011c55  mov     r9d, 3D5h; unsigned int
0x180011c5b  lea     rax, aReproducerafai; "ReproduceRAFailure"
0x180011c62  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x180011c69  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180011c6e  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180011c73  jmp     loc_180011D89
0x180011c78  lea     r8, [rsp+48h+arg_8]; unsigned __int16 **
0x180011c7d  mov     rdx, r14; struct _GUID *
0x180011c80  lea     rcx, aGlobalRadiagev_0; "Global\\RADiagEvent-ReproDone"
0x180011c87  call    ?GenerateUniqueName@@YAJPEAGPEAU_GUID@@PEAPEAG@Z; GenerateUniqueName(ushort *,_GUID *,ushort * *)
0x180011c8c  mov     ebx, eax
0x180011c8e  test    eax, eax
0x180011c90  jns     short loc_180011CBE
0x180011c92  mov     [rsp+48h+var_20], eax; unsigned int
0x180011c96  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x180011c9d  lea     rax, aReproducerafai; "ReproduceRAFailure"
0x180011ca4  mov     r9d, 3DAh; unsigned int
0x180011caa  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180011caf  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180011cb4  mov     rdi, [rsp+48h+arg_8]
0x180011cb9  jmp     loc_180011D89
0x180011cbe  mov     r8, [rsp+48h+lpName]; lpName
0x180011cc3  xor     edx, edx; bInheritHandle
0x180011cc5  lea     ecx, [rdx+2]; dwDesiredAccess
0x180011cc8  call    cs:__imp_OpenEventW
0x180011cce  mov     rsi, rax
0x180011cd1  test    rax, rax
0x180011cd4  jnz     short loc_180011D02
0x180011cd6  lea     rax, aReproducerafai; "ReproduceRAFailure"
0x180011cdd  mov     [rsp+48h+var_20], edi; unsigned int
0x180011ce1  mov     r9d, 3E4h; unsigned int
0x180011ce7  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180011cec  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x180011cf3  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180011cf8  mov     rdi, [rsp+48h+arg_8]
0x180011cfd  jmp     loc_180011D84
0x180011d02  mov     rdi, [rsp+48h+arg_8]
0x180011d07  xor     edx, edx; bInheritHandle
0x180011d09  mov     r8, rdi; lpName
0x180011d0c  mov     ecx, 100000h; dwDesiredAccess
0x180011d11  call    cs:__imp_OpenEventW
0x180011d17  mov     rbp, rax
0x180011d1a  test    rax, rax
0x180011d1d  jnz     short loc_180011D27
0x180011d1f  mov     r9d, 3E9h
0x180011d25  jmp     short loc_180011D64
0x180011d27  mov     rcx, rsi; hEvent
0x180011d2a  call    cs:__imp_SetEvent
0x180011d30  test    eax, eax
0x180011d32  jnz     short loc_180011D4C
0x180011d34  mov     ebx, 80004005h
0x180011d39  mov     [rsp+48h+var_20], 80004005h
0x180011d41  mov     r9d, 3F0h
0x180011d47  jmp     loc_180011C5B
0x180011d4c  mov     edx, 927C0h; dwMilliseconds
0x180011d51  mov     rcx, rbp; hHandle
0x180011d54  call    cs:__imp_WaitForSingleObject
0x180011d5a  test    eax, eax
0x180011d5c  jz      short loc_180011D89
0x180011d5e  mov     r9d, 3FBh; unsigned int
0x180011d64  lea     rax, aReproducerafai; "ReproduceRAFailure"
0x180011d6b  mov     [rsp+48h+var_20], 0; unsigned int
0x180011d73  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x180011d7a  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x180011d7f  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180011d84  mov     ebx, 80004005h
0x180011d89  cmp     [rsp+48h+lpName], 0
0x180011d8f  jz      short loc_180011DA7
0x180011d91  call    cs:__imp_GetProcessHeap
0x180011d97  mov     r8, [rsp+48h+lpName]; lpMem
0x180011d9c  xor     edx, edx; dwFlags
0x180011d9e  mov     rcx, rax; hHeap
0x180011da1  call    cs:__imp_HeapFree
0x180011da7  test    rdi, rdi
0x180011daa  jz      short loc_180011DC0
0x180011dac  call    cs:__imp_GetProcessHeap
0x180011db2  mov     r8, rdi; lpMem
0x180011db5  xor     edx, edx; dwFlags
0x180011db7  mov     rcx, rax; hHeap
0x180011dba  call    cs:__imp_HeapFree
0x180011dc0  test    rsi, rsi
0x180011dc3  jz      short loc_180011DCE
0x180011dc5  mov     rcx, rsi; hObject
0x180011dc8  call    cs:__imp_CloseHandle
0x180011dce  test    rbp, rbp
0x180011dd1  jz      short loc_180011DDC
0x180011dd3  mov     rcx, rbp; hObject
0x180011dd6  call    cs:__imp_CloseHandle
0x180011ddc  mov     rbp, [rsp+48h+arg_18]
0x180011de1  mov     eax, ebx
0x180011de3  mov     rbx, [rsp+48h+arg_0]
0x180011de8  add     rsp, 30h
0x180011dec  pop     r14
0x180011dee  pop     rdi
0x180011def  pop     rsi
0x180011df0  retn
```
