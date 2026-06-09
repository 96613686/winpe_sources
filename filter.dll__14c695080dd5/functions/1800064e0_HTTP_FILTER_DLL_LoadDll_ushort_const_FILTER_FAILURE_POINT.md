# HTTP_FILTER_DLL::LoadDll(ushort const *,FILTER_FAILURE_POINT *)

- ea: `0x1800064e0`
- end: `0x180006719`
- name: `?LoadDll@HTTP_FILTER_DLL@@QEAAJPEBGPEAW4FILTER_FAILURE_POINT@@@Z`
- size: `569`
- prototype: `signed int __fastcall(HTTP_FILTER_DLL *this, const unsigned __int16 *, enum FILTER_FAILURE_POINT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180006f50`

## callees

- `0x1800064e0`
- `0x18000c91e`
- `0x18000c970`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000655d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000655d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006620`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006635`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000664a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006620`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006635`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000664a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006570`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006570`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065f3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000654c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006584`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000654c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006584`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006534`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006534`
- `iisutil!PuDbgPrint` at `0x1800065ba`
- `iisutil!PuDbgPrint` at `0x1800065ba`

## string_xrefs

- `0x18000659c`: `servercommon\inetsrv\iis\iisrearc\iis70\isapifilters\filter.cxx`
- `0x180006591`: `HTTP_FILTER_DLL::LoadDll`
- `0x1800065ae`: `Unable to LoadLibraryEx ISAPI filter '%ws'.  Error = %d\n`

## pseudocode

```c
signed int __fastcall HTTP_FILTER_DLL::LoadDll(
        HTTP_FILTER_DLL *this,
        const unsigned __int16 *a2,
        enum FILTER_FAILURE_POINT *a3)
{
  STRU *v6; // rdi
  signed int result; // eax
  const WCHAR *Str; // rax
  HMODULE Library; // rax
  signed int LastError; // ebx
  unsigned __int16 *v11; // rax
  FARPROC ProcAddress; // rax
  HMODULE v13; // rcx
  FARPROC v14; // rax
  HMODULE v15; // rcx
  FARPROC v16; // rax
  bool v17; // zf
  unsigned int (__fastcall *v18)(_DWORD *); // rax
  int v19; // edi
  int v20; // edx
  int v21; // eax
  struct _LIST_ENTRY *Flink; // rdx
  _DWORD v23[2]; // [rsp+40h] [rbp-138h] BYREF
  char v24; // [rsp+48h] [rbp-130h]
  int v25; // [rsp+14Ch] [rbp-2Ch]

  memset_0(v23, 0, 0x110u);
  if ( !a2 )
    return -2147024809;
  v6 = (HTTP_FILTER_DLL *)((char *)this + 72);
  result = STRU::Copy((HTTP_FILTER_DLL *)((char *)this + 72), a2);
  if ( result >= 0 )
  {
    *(_DWORD *)a3 = 1;
    Str = STRU::QueryStr((HTTP_FILTER_DLL *)((char *)this + 72));
    Library = LoadLibraryExW(Str, 0, 8u);
    *((_QWORD *)this + 3) = Library;
    if ( Library )
    {
      *(_DWORD *)a3 = 2;
      ProcAddress = GetProcAddress(*((HMODULE *)this + 3), "GetFilterVersion");
      v13 = (HMODULE)*((_QWORD *)this + 3);
      *((_QWORD *)this + 5) = ProcAddress;
      v14 = GetProcAddress(v13, "HttpFilterProc");
      v15 = (HMODULE)*((_QWORD *)this + 3);
      *((_QWORD *)this + 4) = v14;
      v16 = GetProcAddress(v15, "TerminateFilter");
      v17 = *((_QWORD *)this + 4) == 0;
      *((_QWORD *)this + 6) = v16;
      if ( v17 || !*((_QWORD *)this + 5) )
      {
        result = -2147024769;
        *((_QWORD *)this + 6) = 0;
      }
      else
      {
        *(_DWORD *)a3 = 3;
        v18 = (unsigned int (__fastcall *)(_DWORD *))*((_QWORD *)this + 5);
        v19 = 0;
        v25 = 0;
        v23[0] = 655360;
        v24 = 0;
        if ( v18(v23) )
        {
          v20 = v25;
          *(_DWORD *)a3 = 0;
          if ( (v20 & 3) == 0 )
          {
            v20 |= 3u;
            v25 = v20;
          }
          *((_DWORD *)this + 14) = v23[1];
          v21 = 0;
          if ( (v20 & 2) != 0 )
            v21 = v20;
          *((_DWORD *)this + 15) = v21;
          if ( (v20 & 1) != 0 )
            v19 = v20;
          *((_DWORD *)this + 16) = v19;
          Flink = HTTP_FILTER_DLL::sm_FilterHead.Flink;
          if ( HTTP_FILTER_DLL::sm_FilterHead.Flink->Blink != &HTTP_FILTER_DLL::sm_FilterHead )
            __fastfail(3u);
          *((_QWORD *)this + 1) = HTTP_FILTER_DLL::sm_FilterHead.Flink;
          *((_QWORD *)this + 2) = &HTTP_FILTER_DLL::sm_FilterHead;
          Flink->Blink = (struct _LIST_ENTRY *)((char *)this + 8);
          HTTP_FILTER_DLL::sm_FilterHead.Flink = (struct _LIST_ENTRY *)((char *)this + 8);
          return 0;
        }
        else
        {
          result = GetLastError();
          if ( result > 0 )
            return (unsigned __int16)result | 0x80070000;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        v11 = STRU::QueryStr(v6);
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapifilters\\filter.cxx",
          131,
          "HTTP_FILTER_DLL::LoadDll",
          "Unable to LoadLibraryEx ISAPI filter '%ws'.  Error = %d\n",
          v11,
          LastError);
      }
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      return LastError;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800064e0  push    rbx
0x1800064e2  push    rsi
0x1800064e3  push    r14
0x1800064e5  sub     rsp, 160h
0x1800064ec  mov     rax, cs:__security_cookie
0x1800064f3  xor     rax, rsp
0x1800064f6  mov     [rsp+178h+var_28], rax
0x1800064fe  mov     r14, r8
0x180006501  mov     rsi, rdx
0x180006504  mov     rbx, rcx
0x180006507  xor     edx, edx; Val
0x180006509  mov     r8d, 110h; Size
0x18000650f  lea     rcx, [rsp+178h+var_138]; void *
0x180006514  call    memset_0
0x180006519  test    rsi, rsi
0x18000651c  jz      loc_180006607
0x180006522  mov     [rsp+178h+arg_18], rdi
0x18000652a  mov     rdx, rsi
0x18000652d  lea     rdi, [rbx+48h]
0x180006531  mov     rcx, rdi
0x180006534  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000653a  test    eax, eax
0x18000653c  js      loc_1800065CF
0x180006542  mov     rcx, rdi
0x180006545  mov     dword ptr [r14], 1
0x18000654c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180006552  xor     edx, edx; hFile
0x180006554  mov     r8d, 8; dwFlags
0x18000655a  mov     rcx, rax; lpLibFileName
0x18000655d  call    cs:__imp_LoadLibraryExW
0x180006563  mov     [rbx+18h], rax
0x180006567  test    rax, rax
0x18000656a  jnz     loc_18000660E
0x180006570  call    cs:__imp_GetLastError
0x180006576  test    cs:g_dwDebugFlags, 3
0x18000657d  mov     ebx, eax
0x18000657f  jz      short loc_1800065C0
0x180006581  mov     rcx, rdi
0x180006584  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000658a  mov     rcx, cs:g_pDebug
0x180006591  lea     r9, aHttpFilterDllL; "HTTP_FILTER_DLL::LoadDll"
0x180006598  mov     [rsp+178h+var_148], ebx
0x18000659c  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800065a3  mov     [rsp+178h+var_150], rax
0x1800065a8  mov     r8d, 83h
0x1800065ae  lea     rax, aUnableToLoadli; "Unable to LoadLibraryEx ISAPI filter '%"...
0x1800065b5  mov     [rsp+178h+var_158], rax
0x1800065ba  call    cs:__imp_PuDbgPrint
0x1800065c0  test    ebx, ebx
0x1800065c2  jle     short loc_1800065CD
0x1800065c4  movzx   ebx, bx
0x1800065c7  or      ebx, 80070000h
0x1800065cd  mov     eax, ebx
0x1800065cf  mov     rdi, [rsp+178h+arg_18]
0x1800065d7  mov     rcx, [rsp+178h+var_28]
0x1800065df  xor     rcx, rsp; StackCookie
0x1800065e2  call    __security_check_cookie
0x1800065e7  add     rsp, 160h
0x1800065ee  pop     r14
0x1800065f0  pop     rsi
0x1800065f1  pop     rbx
0x1800065f2  retn
0x1800065f3  call    cs:__imp_GetLastError
0x1800065f9  test    eax, eax
0x1800065fb  jle     short loc_1800065CF
0x1800065fd  movzx   eax, ax
0x180006600  or      eax, 80070000h
0x180006605  jmp     short loc_1800065CF
0x180006607  mov     eax, 80070057h
0x18000660c  jmp     short loc_1800065D7
0x18000660e  mov     dword ptr [r14], 2
0x180006615  lea     rdx, ProcName; "GetFilterVersion"
0x18000661c  mov     rcx, [rbx+18h]; hModule
0x180006620  call    cs:__imp_GetProcAddress
0x180006626  mov     rcx, [rbx+18h]; hModule
0x18000662a  lea     rdx, aHttpfilterproc; "HttpFilterProc"
0x180006631  mov     [rbx+28h], rax
0x180006635  call    cs:__imp_GetProcAddress
0x18000663b  mov     rcx, [rbx+18h]; hModule
0x18000663f  lea     rdx, aTerminatefilte; "TerminateFilter"
0x180006646  mov     [rbx+20h], rax
0x18000664a  call    cs:__imp_GetProcAddress
0x180006650  cmp     qword ptr [rbx+20h], 0
0x180006655  mov     [rbx+30h], rax
0x180006659  jz      loc_180006709
0x18000665f  cmp     qword ptr [rbx+28h], 0
0x180006664  jz      loc_180006709
0x18000666a  mov     dword ptr [r14], 3
0x180006671  lea     rcx, [rsp+178h+var_138]
0x180006676  mov     rax, [rbx+28h]
0x18000667a  xor     edi, edi
0x18000667c  mov     [rsp+178h+var_2C], edi
0x180006683  mov     [rsp+178h+var_138], 0A0000h
0x18000668b  mov     [rsp+178h+var_130], 0
0x180006690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006695  test    eax, eax
0x180006697  jz      loc_1800065F3
0x18000669d  mov     edx, [rsp+178h+var_2C]
0x1800066a4  mov     [r14], edi
0x1800066a7  test    dl, 3
0x1800066aa  jnz     short loc_1800066B6
0x1800066ac  or      edx, 3
0x1800066af  mov     [rsp+178h+var_2C], edx
0x1800066b6  mov     eax, [rsp+178h+var_134]
0x1800066ba  lea     rcx, ?sm_FilterHead@HTTP_FILTER_DLL@@0U_LIST_ENTRY@@A; _LIST_ENTRY HTTP_FILTER_DLL::sm_FilterHead
0x1800066c1  mov     [rbx+38h], eax
0x1800066c4  test    dl, 2
0x1800066c7  mov     eax, edi
0x1800066c9  cmovnz  eax, edx
0x1800066cc  test    dl, 1
0x1800066cf  mov     [rbx+3Ch], eax
0x1800066d2  cmovnz  edi, edx
0x1800066d5  mov     [rbx+40h], edi
0x1800066d8  mov     rdx, cs:?sm_FilterHead@HTTP_FILTER_DLL@@0U_LIST_ENTRY@@A; _LIST_ENTRY HTTP_FILTER_DLL::sm_FilterHead
0x1800066df  cmp     [rdx+8], rcx
0x1800066e3  jz      short loc_1800066EC
0x1800066e5  mov     ecx, 3
0x1800066ea  int     29h; Win8: RtlFailFast(ecx)
0x1800066ec  lea     rax, [rbx+8]
0x1800066f0  mov     [rax], rdx
0x1800066f3  mov     [rax+8], rcx
0x1800066f7  mov     [rdx+8], rax
0x1800066fb  mov     cs:?sm_FilterHead@HTTP_FILTER_DLL@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY HTTP_FILTER_DLL::sm_FilterHead
0x180006702  xor     eax, eax
0x180006704  jmp     loc_1800065CF
0x180006709  xor     edi, edi
0x18000670b  mov     eax, 8007007Fh
0x180006710  mov     [rbx+30h], rdi
0x180006714  jmp     loc_1800065CF
```
