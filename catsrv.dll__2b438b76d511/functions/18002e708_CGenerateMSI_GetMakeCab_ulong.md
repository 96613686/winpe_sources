# CGenerateMSI::_GetMakeCab(ulong)

- ea: `0x18002e708`
- end: `0x18002e87f`
- name: `?_GetMakeCab@CGenerateMSI@@QEAAJK@Z`
- size: `375`
- prototype: `__int64 __fastcall(CGenerateMSI *__hidden this, unsigned int)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002b600`
- `0x18002b820`
- `0x18002c050`
- `0x18002c300`
- `0x18002cc60`
- `0x18002cef0`

## callees

- `0x18002d540`
- `0x18002e708`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e746`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e798`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e746`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e798`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002e73a`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002e78e`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002e73a`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002e78e`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18002e7e7`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18002e7e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e7bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e7bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e76d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002e76d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CGenerateMSI::_GetMakeCab(CGenerateMSI *this, unsigned int a2)
{
  signed int v2; // edi
  _QWORD *v3; // r14
  DWORD TempPathW; // eax
  DWORD v7; // ebx
  signed int v8; // eax
  WCHAR *v9; // rax
  signed int LastError; // eax
  void *v12; // rcx
  __int64 v13; // rbx
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  v3 = (_QWORD *)((char *)this + 616);
  v14 = 0;
  if ( !*((_QWORD *)this + 77) )
  {
    TempPathW = GetTempPathW(0, 0);
    v7 = TempPathW;
    if ( TempPathW )
    {
      v9 = (WCHAR *)CoTaskMemAlloc(2LL * (TempPathW + 260));
      *((_QWORD *)this + 78) = v9;
      if ( !v9 )
        return 2147942414LL;
      if ( GetTempPathW(v7, v9) && GetTempFileNameW(*((LPCWSTR *)this + 78), L"COM", 0, *((LPWSTR *)this + 78)) )
      {
        v2 = ATL::CComObject<CMakeCab>::CreateInstance(&v14);
        if ( v2 >= 0 )
        {
          v13 = v14;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
          v2 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v13)(v13, &IID_IMakeCab, v3);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          if ( v2 >= 0 )
            return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int))(*(_QWORD *)*v3 + 24LL))(
                                   *v3,
                                   *((_QWORD *)this + 78),
                                   0,
                                   0,
                                   (a2 >> 7) & 1);
        }
      }
      else
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        v12 = (void *)*((_QWORD *)this + 78);
        if ( v12 )
        {
          CoTaskMemFree(v12);
          *((_QWORD *)this + 78) = 0;
        }
      }
    }
    else
    {
      v8 = GetLastError();
      v2 = v8;
      if ( v8 > 0 )
        return (unsigned __int16)v8 | 0x80070000;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002e708  mov     [rsp+arg_8], rbx
0x18002e70d  mov     [rsp+arg_10], rbp
0x18002e712  push    rsi
0x18002e713  push    rdi
0x18002e714  push    r14
0x18002e716  sub     rsp, 30h
0x18002e71a  xor     edi, edi
0x18002e71c  lea     r14, [rcx+268h]
0x18002e723  mov     ebp, edx
0x18002e725  mov     rsi, rcx
0x18002e728  mov     [rsp+48h+arg_0], rdi
0x18002e72d  cmp     [r14], rdi
0x18002e730  jnz     loc_18002E86A
0x18002e736  xor     edx, edx; lpBuffer
0x18002e738  xor     ecx, ecx; nBufferLength
0x18002e73a  call    cs:__imp_GetTempPathW
0x18002e740  mov     ebx, eax
0x18002e742  test    eax, eax
0x18002e744  jnz     short loc_18002E764
0x18002e746  call    cs:__imp_GetLastError
0x18002e74c  mov     edi, eax
0x18002e74e  test    eax, eax
0x18002e750  jle     loc_18002E86A
0x18002e756  movzx   edi, ax
0x18002e759  or      edi, 80070000h
0x18002e75f  jmp     loc_18002E86A
0x18002e764  lea     ecx, [rax+104h]
0x18002e76a  add     rcx, rcx; cb
0x18002e76d  call    cs:__imp_CoTaskMemAlloc
0x18002e773  mov     [rsi+270h], rax
0x18002e77a  test    rax, rax
0x18002e77d  jnz     short loc_18002E789
0x18002e77f  mov     eax, 8007000Eh
0x18002e784  jmp     loc_18002E86C
0x18002e789  mov     rdx, rax; lpBuffer
0x18002e78c  mov     ecx, ebx; nBufferLength
0x18002e78e  call    cs:__imp_GetTempPathW
0x18002e794  test    eax, eax
0x18002e796  jnz     short loc_18002E7D3
0x18002e798  call    cs:__imp_GetLastError
0x18002e79e  mov     edi, eax
0x18002e7a0  test    eax, eax
0x18002e7a2  jle     short loc_18002E7AD
0x18002e7a4  movzx   edi, ax
0x18002e7a7  or      edi, 80070000h
0x18002e7ad  mov     rcx, [rsi+270h]; pv
0x18002e7b4  test    rcx, rcx
0x18002e7b7  jz      loc_18002E86A
0x18002e7bd  call    cs:__imp_CoTaskMemFree
0x18002e7c3  mov     qword ptr [rsi+270h], 0
0x18002e7ce  jmp     loc_18002E86A
0x18002e7d3  mov     rcx, [rsi+270h]; lpPathName
0x18002e7da  lea     rdx, aCom_1; "COM"
0x18002e7e1  mov     r9, rcx; lpTempFileName
0x18002e7e4  xor     r8d, r8d; uUnique
0x18002e7e7  call    cs:__imp_GetTempFileNameW
0x18002e7ed  test    eax, eax
0x18002e7ef  jz      short loc_18002E798
0x18002e7f1  lea     rcx, [rsp+48h+arg_0]
0x18002e7f6  call    ?CreateInstance@?$CComObject@VCMakeCab@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CMakeCab>::CreateInstance(ATL::CComObject<CMakeCab> * *)
0x18002e7fb  mov     edi, eax
0x18002e7fd  test    eax, eax
0x18002e7ff  js      short loc_18002E86A
0x18002e801  mov     rbx, [rsp+48h+arg_0]
0x18002e806  mov     rcx, rbx
0x18002e809  mov     rax, [rbx]
0x18002e80c  mov     rax, [rax+8]
0x18002e810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e815  mov     rax, [rbx]
0x18002e818  lea     rdx, IID_IMakeCab
0x18002e81f  mov     r8, r14
0x18002e822  mov     rcx, rbx
0x18002e825  mov     rax, [rax]
0x18002e828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e82d  mov     edi, eax
0x18002e82f  mov     rcx, rbx
0x18002e832  mov     rax, [rbx]
0x18002e835  mov     rax, [rax+10h]
0x18002e839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e83e  test    edi, edi
0x18002e840  js      short loc_18002E86A
0x18002e842  mov     rcx, [r14]
0x18002e845  xor     r9d, r9d
0x18002e848  mov     rdx, [rsi+270h]
0x18002e84f  xor     r8d, r8d
0x18002e852  shr     ebp, 7
0x18002e855  and     ebp, 1
0x18002e858  mov     rax, [rcx]
0x18002e85b  mov     [rsp+48h+var_28], ebp
0x18002e85f  mov     rax, [rax+18h]
0x18002e863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e868  mov     edi, eax
0x18002e86a  mov     eax, edi
0x18002e86c  mov     rbx, [rsp+48h+arg_8]
0x18002e871  mov     rbp, [rsp+48h+arg_10]
0x18002e876  add     rsp, 30h
0x18002e87a  pop     r14
0x18002e87c  pop     rdi
0x18002e87d  pop     rsi
0x18002e87e  retn
```
