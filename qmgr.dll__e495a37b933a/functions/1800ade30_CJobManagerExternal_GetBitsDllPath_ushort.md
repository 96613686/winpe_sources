# CJobManagerExternal::GetBitsDllPath(ushort * *)

- ea: `0x1800ade30`
- end: `0x1800adf04`
- name: `?GetBitsDllPath@CJobManagerExternal@@UEAAJPEAPEAG@Z`
- size: `212`
- prototype: `__int64 __fastcall(CJobManagerExternal *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000a680`
- `0x1800ade30`
- `0x1800b1b18`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800ade81`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800ade81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ade8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ade8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ade5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ade5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800adea3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800adea3`

## pseudocode

```c
__int64 __fastcall CJobManagerExternal::GetBitsDllPath(CJobManagerExternal *this, LPVOID *a2)
{
  int v3; // esi
  int v4; // edx
  signed int v5; // ebx
  int v6; // r8d
  unsigned __int16 *v7; // rax
  signed int LastError; // eax
  const wchar_t *v9; // rax

  *a2 = 0;
  v3 = (int)this;
  v5 = CJobManager::CheckClientAccess(this);
  if ( v5 >= 0 )
  {
    v7 = (unsigned __int16 *)CoTaskMemAlloc(0x20Au);
    *a2 = v7;
    if ( v7 )
    {
      if ( !GetModuleFileNameW((HMODULE)g_hInstance, v7, 0x105u) )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        CoTaskMemFree(*a2);
        *a2 = 0;
      }
    }
    else
    {
      v5 = -2147024882;
    }
  }
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v9 = L"NULL";
    if ( *a2 )
      v9 = (const wchar_t *)*a2;
    WPP_SF_qDDS(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v6, v3 - 16, v5, v5, (__int64)v9);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800ade30  mov     [rsp+arg_0], rbx
0x1800ade35  mov     [rsp+arg_8], rsi
0x1800ade3a  push    rdi
0x1800ade3b  sub     rsp, 40h
0x1800ade3f  mov     rdi, rdx
0x1800ade42  mov     qword ptr [rdx], 0
0x1800ade49  mov     rsi, rcx
0x1800ade4c  call    ?CheckClientAccess@CJobManager@@QEAAJXZ; CJobManager::CheckClientAccess(void)
0x1800ade51  mov     ebx, eax
0x1800ade53  test    eax, eax
0x1800ade55  js      short loc_1800ADEB0
0x1800ade57  mov     ecx, 20Ah; cb
0x1800ade5c  call    cs:__imp_CoTaskMemAlloc
0x1800ade62  mov     [rdi], rax
0x1800ade65  test    rax, rax
0x1800ade68  jnz     short loc_1800ADE71
0x1800ade6a  mov     ebx, 8007000Eh
0x1800ade6f  jmp     short loc_1800ADEB0
0x1800ade71  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x1800ade78  mov     r8d, 105h; nSize
0x1800ade7e  mov     rdx, rax; lpFilename
0x1800ade81  call    cs:__imp_GetModuleFileNameW
0x1800ade87  test    eax, eax
0x1800ade89  jnz     short loc_1800ADEB0
0x1800ade8b  call    cs:__imp_GetLastError
0x1800ade91  mov     ebx, eax
0x1800ade93  test    eax, eax
0x1800ade95  jle     short loc_1800ADEA0
0x1800ade97  movzx   ebx, ax
0x1800ade9a  or      ebx, 80070000h
0x1800adea0  mov     rcx, [rdi]; pv
0x1800adea3  call    cs:__imp_CoTaskMemFree
0x1800adea9  mov     qword ptr [rdi], 0
0x1800adeb0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800adeb7  lea     rax, WPP_GLOBAL_Control
0x1800adebe  cmp     rcx, rax
0x1800adec1  jz      short loc_1800ADEF2
0x1800adec3  test    byte ptr [rcx+1Ch], 8
0x1800adec7  jz      short loc_1800ADEF2
0x1800adec9  cmp     qword ptr [rdi], 0
0x1800adecd  lea     rax, aNull_1; "NULL"
0x1800aded4  mov     rcx, [rcx+10h]
0x1800aded8  lea     r9, [rsi-10h]
0x1800adedc  cmovnz  rax, [rdi]
0x1800adee0  mov     [rsp+48h+var_18], rax
0x1800adee5  mov     [rsp+48h+var_20], ebx
0x1800adee9  mov     [rsp+48h+var_28], ebx
0x1800adeed  call    WPP_SF_qDDS
0x1800adef2  mov     rsi, [rsp+48h+arg_8]
0x1800adef7  mov     eax, ebx
0x1800adef9  mov     rbx, [rsp+48h+arg_0]
0x1800adefe  add     rsp, 40h
0x1800adf02  pop     rdi
0x1800adf03  retn
```
