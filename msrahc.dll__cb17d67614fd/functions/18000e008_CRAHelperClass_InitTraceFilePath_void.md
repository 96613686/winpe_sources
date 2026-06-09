# CRAHelperClass::InitTraceFilePath(void)

- ea: `0x18000e008`
- end: `0x18000e140`
- name: `?InitTraceFilePath@CRAHelperClass@@AEAAJXZ`
- size: `312`
- prototype: `__int64 __fastcall(CRAHelperClass *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e4d0`

## callees

- `0x18000e008`
- `0x180014660`
- `0x180014da0`
- `0x18001a5a2`
- `0x18001c010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000e078`
- `KERNEL32!GetProcessHeap` at `0x18000e078`
- `KERNEL32!HeapFree` at `0x18000e086`
- `KERNEL32!HeapFree` at `0x18000e086`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e0fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e123`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e0fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e123`

## string_xrefs

- `0x18000e039`: `CRAHelperClass::InitTraceFilePath`
- `0x18000e0e4`: `CRAHelperClass::InitTraceFilePath`

## pseudocode

```c
__int64 __fastcall CRAHelperClass::InitTraceFilePath(CRAHelperClass *this)
{
  const struct _EVENT_DESCRIPTOR *v2; // rdx
  CEventLogger *v3; // rcx
  unsigned int v4; // ebx
  unsigned __int16 **v5; // rdi
  void *v6; // rsi
  HANDLE ProcessHeap; // rax
  signed int v8; // eax
  const struct _EVENT_DESCRIPTOR *v9; // rdx
  CEventLogger *v10; // rcx
  unsigned int v11; // r9d
  unsigned __int16 *v12; // rcx
  LPVOID pv; // [rsp+30h] [rbp-98h] BYREF
  int v15; // [rsp+38h] [rbp-90h]
  unsigned __int16 *Src; // [rsp+40h] [rbp-88h]
  unsigned __int16 *v17; // [rsp+48h] [rbp-80h]

  memset_0(&pv, 0, 0x90u);
  if ( !*((_QWORD *)this + 23) )
  {
    CEventLogger::LogError(
      v3,
      v2,
      L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
      0x6C5u,
      L"CRAHelperClass::InitTraceFilePath",
      0);
    v4 = -2147467259;
    goto LABEL_10;
  }
  v5 = (unsigned __int16 **)((char *)this + 192);
  v6 = (void *)*((_QWORD *)this + 24);
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
    *v5 = 0;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, LPVOID *))(**((_QWORD **)this + 23) + 32LL))(
         *((_QWORD *)this + 23),
         L"NDFTraceFile",
         &pv);
  v4 = v8;
  if ( v8 >= 0 )
  {
    v8 = DuplicateString(Src, v5);
    v4 = v8;
    if ( v8 >= 0 )
      goto LABEL_10;
    v11 = 1744;
  }
  else
  {
    v11 = 1741;
  }
  CEventLogger::LogError(
    v10,
    v9,
    L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
    v11,
    L"CRAHelperClass::InitTraceFilePath",
    v8);
LABEL_10:
  CoTaskMemFree(pv);
  pv = 0;
  if ( v15 == 10 )
  {
    v12 = Src;
    goto LABEL_14;
  }
  if ( v15 == 14 )
  {
    v12 = v17;
LABEL_14:
    CoTaskMemFree(v12);
  }
  return v4;
}

```

## disassembly

```asm
0x18000e008  mov     [rsp+arg_0], rbx
0x18000e00d  mov     [rsp+arg_8], rsi
0x18000e012  push    rdi
0x18000e013  sub     rsp, 0C0h
0x18000e01a  mov     rbx, rcx
0x18000e01d  xor     edx, edx; Val
0x18000e01f  lea     rcx, [rsp+0C8h+pv]; void *
0x18000e024  mov     r8d, 90h; Size
0x18000e02a  call    memset_0
0x18000e02f  cmp     qword ptr [rbx+0B8h], 0
0x18000e037  jnz     short loc_18000E069
0x18000e039  lea     rax, aCrahelperclass_14; "CRAHelperClass::InitTraceFilePath"
0x18000e040  mov     [rsp+0C8h+var_A0], 0; unsigned int
0x18000e048  mov     r9d, 6C5h; unsigned int
0x18000e04e  mov     [rsp+0C8h+var_A8], rax; unsigned __int16 *
0x18000e053  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000e05a  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000e05f  mov     ebx, 80004005h
0x18000e064  jmp     loc_18000E0F5
0x18000e069  lea     rdi, [rbx+0C0h]
0x18000e070  mov     rsi, [rdi]
0x18000e073  test    rsi, rsi
0x18000e076  jz      short loc_18000E093
0x18000e078  call    cs:__imp_GetProcessHeap
0x18000e07e  mov     r8, rsi; lpMem
0x18000e081  xor     edx, edx; dwFlags
0x18000e083  mov     rcx, rax; hHeap
0x18000e086  call    cs:__imp_HeapFree
0x18000e08c  mov     qword ptr [rdi], 0
0x18000e093  mov     rcx, [rbx+0B8h]
0x18000e09a  lea     r8, [rsp+0C8h+pv]
0x18000e09f  lea     rdx, aNdftracefile; "NDFTraceFile"
0x18000e0a6  mov     rax, [rcx]
0x18000e0a9  mov     rax, [rax+20h]
0x18000e0ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0b2  mov     ebx, eax
0x18000e0b4  test    eax, eax
0x18000e0b6  jns     short loc_18000E0C0
0x18000e0b8  mov     r9d, 6CDh
0x18000e0be  jmp     short loc_18000E0D9
0x18000e0c0  mov     rcx, [rsp+0C8h+Src]; Src
0x18000e0c5  mov     rdx, rdi; unsigned __int16 **
0x18000e0c8  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x18000e0cd  mov     ebx, eax
0x18000e0cf  test    eax, eax
0x18000e0d1  jns     short loc_18000E0F5
0x18000e0d3  mov     r9d, 6D0h; unsigned int
0x18000e0d9  mov     [rsp+0C8h+var_A0], eax; unsigned int
0x18000e0dd  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000e0e4  lea     rax, aCrahelperclass_14; "CRAHelperClass::InitTraceFilePath"
0x18000e0eb  mov     [rsp+0C8h+var_A8], rax; unsigned __int16 *
0x18000e0f0  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000e0f5  mov     rcx, [rsp+0C8h+pv]; pv
0x18000e0fa  call    cs:__imp_CoTaskMemFree
0x18000e100  cmp     [rsp+0C8h+var_90], 0Ah
0x18000e105  mov     [rsp+0C8h+pv], 0
0x18000e10e  jz      short loc_18000E11E
0x18000e110  cmp     [rsp+0C8h+var_90], 0Eh
0x18000e115  jnz     short loc_18000E129
0x18000e117  mov     rcx, [rsp+0C8h+var_80]
0x18000e11c  jmp     short loc_18000E123
0x18000e11e  mov     rcx, [rsp+0C8h+Src]; pv
0x18000e123  call    cs:__imp_CoTaskMemFree
0x18000e129  lea     r11, [rsp+0C8h+var_8]
0x18000e131  mov     eax, ebx
0x18000e133  mov     rbx, [r11+10h]
0x18000e137  mov     rsi, [r11+18h]
0x18000e13b  mov     rsp, r11
0x18000e13e  pop     rdi
0x18000e13f  retn
```
