# CLTApp::BuildAppCmdLine(ISimpleTableWrite *,__MIDL___MIDL_itf_registrar_0000_0000_0001,ushort * *)

- ea: `0x18003abec`
- end: `0x18003ae80`
- name: `?BuildAppCmdLine@CLTApp@@AEAAJPEAUISimpleTableWrite@@W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@PEAPEAG@Z`
- size: `660`
- prototype: `signed int __fastcall(__int64, __int64, int, LPVOID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003c268`

## callees

- `0x180001e60`
- `0x180014ec8`
- `0x18003abec`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003acbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ae2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003acbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ae2f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003ae1b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003ae1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003ac90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003adc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003ac90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003adc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ad5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ad5c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18003ad52`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18003ad52`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x18003ad4a`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x18003ad4a`

## string_xrefs

- `0x18003ad98`: `\dllhst3g.exe /Processid:`
- `0x18003ad91`: `\dllhost.exe /Processid:`

## pseudocode

```c
signed int __fastcall CLTApp::BuildAppCmdLine(__int64 a1, __int64 a2, int a3, LPVOID *a4)
{
  signed int result; // eax
  __int64 v8; // rax
  unsigned __int64 v9; // rbx
  unsigned __int16 *v10; // rax
  int v11; // ebx
  UINT SystemWow64DirectoryW; // eax
  __int64 v13; // rdx
  const unsigned __int16 *v14; // rdi
  __int64 v15; // rax
  unsigned __int64 v16; // rsi
  void *v17; // rax
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD *v19; // [rsp+48h] [rbp-B8h]
  GUID *rguid; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[264]; // [rsp+B0h] [rbp-50h] BYREF

  pv = 0;
  result = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _QWORD, LPVOID *))(*(_QWORD *)a2 + 152LL))(
             a2,
             5,
             0,
             0,
             0,
             &pv);
  if ( result >= 0 )
  {
    if ( pv && *(_WORD *)pv )
    {
      v8 = -1;
      do
        ++v8;
      while ( *((_WORD *)pv + v8) );
      v9 = v8 + 1;
      v10 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v8 + 1, 2u));
      *a4 = v10;
      if ( v10 )
      {
        v11 = StringCchCopyW(v10, v9, (const unsigned __int16 *)pv);
        if ( v11 < 0 )
        {
          CoTaskMemFree(*a4);
          *a4 = 0;
        }
        return v11;
      }
      return -2147024882;
    }
    v19 = 0;
    rguid = 0;
    result = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a2 + 152LL))(a2, 27, 0);
    if ( result >= 0 )
    {
      result = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, GUID **))(*(_QWORD *)a2 + 152LL))(
                 a2,
                 0,
                 0,
                 0,
                 0,
                 &rguid);
      if ( result >= 0 )
      {
        if ( a3 == 1 )
          SystemWow64DirectoryW = GetSystemWow64DirectoryW(Buffer, 0x104u);
        else
          SystemWow64DirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
        if ( !SystemWow64DirectoryW )
        {
          result = GetLastError();
          if ( result > 0 )
            return (unsigned __int16)result | 0x80070000;
          return result;
        }
        v13 = -1;
        do
          ++v13;
        while ( Buffer[v13] );
        v14 = L"\\dllhst3g.exe /Processid:";
        if ( !*v19 )
          v14 = L"\\dllhost.exe /Processid:";
        v15 = -1;
        do
          ++v15;
        while ( v14[v15] );
        v16 = v13 + v15 + 40;
        v17 = CoTaskMemAlloc(saturated_mul(v16, 2u));
        pv = v17;
        if ( !v17 )
          return -2147024882;
        v11 = StringCchCopyW((unsigned __int16 *)v17, v16, Buffer);
        if ( v11 >= 0 )
        {
          v11 = StringCchCatW((unsigned __int16 *)pv, v16, v14);
          if ( v11 >= 0 )
          {
            if ( StringFromGUID2(rguid, sz, 39) )
            {
              v11 = StringCchCatW((unsigned __int16 *)pv, v16, sz);
              if ( v11 >= 0 )
              {
                *a4 = pv;
                return v11;
              }
            }
            else
            {
              v11 = -2147418113;
            }
          }
        }
        CoTaskMemFree(pv);
        return v11;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003abec  mov     [rsp-8+arg_0], rbx
0x18003abf1  push    rbp
0x18003abf2  push    rsi
0x18003abf3  push    rdi
0x18003abf4  push    r14
0x18003abf6  push    r15
0x18003abf8  lea     rbp, [rsp-1D0h]
0x18003ac00  sub     rsp, 2D0h
0x18003ac07  mov     rax, cs:__security_cookie
0x18003ac0e  xor     rax, rsp
0x18003ac11  mov     [rbp+1F0h+var_30], rax
0x18003ac18  mov     r14, r9
0x18003ac1b  mov     edi, r8d
0x18003ac1e  mov     rbx, rdx
0x18003ac21  xor     r15d, r15d
0x18003ac24  mov     [rsp+2F0h+pv], r15
0x18003ac29  mov     rax, [rdx]
0x18003ac2c  lea     rcx, [rsp+2F0h+pv]
0x18003ac31  mov     [rsp+2F0h+var_2C8], rcx
0x18003ac36  mov     [rsp+2F0h+var_2D0], r15
0x18003ac3b  xor     r9d, r9d
0x18003ac3e  xor     r8d, r8d
0x18003ac41  lea     edx, [r15+5]
0x18003ac45  mov     rcx, rbx
0x18003ac48  mov     rax, [rax+98h]
0x18003ac4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac54  test    eax, eax
0x18003ac56  js      loc_18003AE38
0x18003ac5c  mov     rdx, [rsp+2F0h+pv]
0x18003ac61  test    rdx, rdx
0x18003ac64  jz      short loc_18003ACCE
0x18003ac66  cmp     [rdx], r15w
0x18003ac6a  jz      short loc_18003ACCE
0x18003ac6c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003ac70  mov     rax, rcx
0x18003ac73  inc     rax
0x18003ac76  cmp     [rdx+rax*2], r15w
0x18003ac7b  jnz     short loc_18003AC73
0x18003ac7d  lea     rbx, [rax+1]
0x18003ac81  mov     eax, 2
0x18003ac86  mul     rbx
0x18003ac89  cmovb   rax, rcx
0x18003ac8d  mov     rcx, rax; cb
0x18003ac90  call    cs:__imp_CoTaskMemAlloc
0x18003ac96  mov     [r14], rax
0x18003ac99  test    rax, rax
0x18003ac9c  jz      loc_18003ADD9
0x18003aca2  mov     r8, [rsp+2F0h+pv]; unsigned __int16 *
0x18003aca7  mov     rdx, rbx; unsigned __int64
0x18003acaa  mov     rcx, rax; unsigned __int16 *
0x18003acad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003acb2  mov     ebx, eax
0x18003acb4  test    eax, eax
0x18003acb6  jns     loc_18003AE36
0x18003acbc  mov     rcx, [r14]; pv
0x18003acbf  call    cs:__imp_CoTaskMemFree
0x18003acc5  nop
0x18003acc6  mov     [r14], r15
0x18003acc9  jmp     loc_18003AE36
0x18003acce  mov     [rsp+2F0h+var_2A8], r15
0x18003acd3  mov     [rsp+2F0h+rguid], r15
0x18003acd8  mov     rax, [rbx]
0x18003acdb  lea     rcx, [rsp+2F0h+var_2A8]
0x18003ace0  mov     [rsp+2F0h+var_2C8], rcx
0x18003ace5  mov     [rsp+2F0h+var_2D0], r15
0x18003acea  xor     r9d, r9d
0x18003aced  xor     r8d, r8d
0x18003acf0  lea     edx, [r9+1Bh]
0x18003acf4  mov     rcx, rbx
0x18003acf7  mov     rax, [rax+98h]
0x18003acfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad03  test    eax, eax
0x18003ad05  js      loc_18003AE38
0x18003ad0b  mov     rax, [rbx]
0x18003ad0e  lea     rcx, [rsp+2F0h+rguid]
0x18003ad13  mov     [rsp+2F0h+var_2C8], rcx
0x18003ad18  mov     [rsp+2F0h+var_2D0], r15
0x18003ad1d  xor     r9d, r9d
0x18003ad20  xor     r8d, r8d
0x18003ad23  xor     edx, edx
0x18003ad25  mov     rcx, rbx
0x18003ad28  mov     rax, [rax+98h]
0x18003ad2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad34  test    eax, eax
0x18003ad36  js      loc_18003AE38
0x18003ad3c  mov     edx, 104h; uSize
0x18003ad41  lea     rcx, [rbp+1F0h+Buffer]; lpBuffer
0x18003ad45  cmp     edi, 1
0x18003ad48  jnz     short loc_18003AD52
0x18003ad4a  call    cs:__imp_GetSystemWow64DirectoryW
0x18003ad50  jmp     short loc_18003AD58
0x18003ad52  call    cs:__imp_GetSystemDirectoryW
0x18003ad58  test    eax, eax
0x18003ad5a  jnz     short loc_18003AD77
0x18003ad5c  call    cs:__imp_GetLastError
0x18003ad62  test    eax, eax
0x18003ad64  jle     loc_18003AE38
0x18003ad6a  movzx   eax, ax
0x18003ad6d  or      eax, 80070000h
0x18003ad72  jmp     loc_18003AE38
0x18003ad77  lea     rax, [rbp+1F0h+Buffer]
0x18003ad7b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003ad7f  mov     rdx, rcx
0x18003ad82  inc     rdx
0x18003ad85  cmp     [rax+rdx*2], r15w
0x18003ad8a  jnz     short loc_18003AD82
0x18003ad8c  mov     rax, [rsp+2F0h+var_2A8]
0x18003ad91  lea     r8, aDllhostExeProc; "\\dllhost.exe /Processid:"
0x18003ad98  lea     rdi, aDllhst3gExePro; "\\dllhst3g.exe /Processid:"
0x18003ad9f  cmp     [rax], r15d
0x18003ada2  cmovz   rdi, r8
0x18003ada6  mov     rax, rcx
0x18003ada9  inc     rax
0x18003adac  cmp     [rdi+rax*2], r15w
0x18003adb1  jnz     short loc_18003ADA9
0x18003adb3  lea     rsi, [rax+28h]
0x18003adb7  add     rsi, rdx
0x18003adba  mov     eax, 2
0x18003adbf  mul     rsi
0x18003adc2  cmovb   rax, rcx
0x18003adc6  mov     rcx, rax; cb
0x18003adc9  call    cs:__imp_CoTaskMemAlloc
0x18003adcf  mov     [rsp+2F0h+pv], rax
0x18003add4  test    rax, rax
0x18003add7  jnz     short loc_18003ADE0
0x18003add9  mov     eax, 8007000Eh
0x18003adde  jmp     short loc_18003AE38
0x18003ade0  lea     r8, [rbp+1F0h+Buffer]; unsigned __int16 *
0x18003ade4  mov     rdx, rsi; unsigned __int64
0x18003ade7  mov     rcx, rax; unsigned __int16 *
0x18003adea  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003adef  mov     ebx, eax
0x18003adf1  test    eax, eax
0x18003adf3  js      short loc_18003AE2A
0x18003adf5  mov     r8, rdi; unsigned __int16 *
0x18003adf8  mov     rdx, rsi; unsigned __int64
0x18003adfb  mov     rcx, [rsp+2F0h+pv]; unsigned __int16 *
0x18003ae00  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003ae05  mov     ebx, eax
0x18003ae07  test    eax, eax
0x18003ae09  js      short loc_18003AE2A
0x18003ae0b  mov     r8d, 27h ; '''; cchMax
0x18003ae11  lea     rdx, [rsp+2F0h+sz]; lpsz
0x18003ae16  mov     rcx, [rsp+2F0h+rguid]; rguid
0x18003ae1b  call    cs:__imp_StringFromGUID2
0x18003ae21  test    eax, eax
0x18003ae23  jnz     short loc_18003AE5E
0x18003ae25  mov     ebx, 8000FFFFh
0x18003ae2a  mov     rcx, [rsp+2F0h+pv]; pv
0x18003ae2f  call    cs:__imp_CoTaskMemFree
0x18003ae35  nop
0x18003ae36  mov     eax, ebx
0x18003ae38  mov     rcx, [rbp+1F0h+var_30]
0x18003ae3f  xor     rcx, rsp; StackCookie
0x18003ae42  call    __security_check_cookie
0x18003ae47  mov     rbx, [rsp+2F0h+arg_0]
0x18003ae4f  add     rsp, 2D0h
0x18003ae56  pop     r15
0x18003ae58  pop     r14
0x18003ae5a  pop     rdi
0x18003ae5b  pop     rsi
0x18003ae5c  pop     rbp
0x18003ae5d  retn
0x18003ae5e  lea     r8, [rsp+2F0h+sz]; unsigned __int16 *
0x18003ae63  mov     rdx, rsi; unsigned __int64
0x18003ae66  mov     rcx, [rsp+2F0h+pv]; unsigned __int16 *
0x18003ae6b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003ae70  mov     ebx, eax
0x18003ae72  test    eax, eax
0x18003ae74  js      short loc_18003AE2A
0x18003ae76  mov     rax, [rsp+2F0h+pv]
0x18003ae7b  mov     [r14], rax
0x18003ae7e  jmp     short loc_18003AE36
```
