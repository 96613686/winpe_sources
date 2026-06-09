# CEXTLOG::GetRegParameters(char const *,void *)

- ea: `0x180004810`
- end: `0x1800049ff`
- name: `?GetRegParameters@CEXTLOG@@MEAAKPEBDPEAX@Z`
- size: `495`
- prototype: `unsigned int(CEXTLOG *__hidden this, const char *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001008`
- `0x180002410`
- `0x1800024d0`
- `0x180004810`
- `0x180010010`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x1800048c4`
- `IisRTL!PuDbgPrint` at `0x18000494f`
- `IisRTL!PuDbgPrint` at `0x1800048c4`
- `IisRTL!PuDbgPrint` at `0x18000494f`
- `IisRTL!??0ASCLOG_DATETIME_CACHE@@QEAA@XZ` at `0x1800049bc`
- `IisRTL!??0ASCLOG_DATETIME_CACHE@@QEAA@XZ` at `0x1800049bc`
- `KERNEL32!SetLastError` at `0x180004880`
- `KERNEL32!SetLastError` at `0x180004880`
- `KERNEL32!GetLastError` at `0x180004893`
- `KERNEL32!GetLastError` at `0x18000491e`
- `KERNEL32!GetLastError` at `0x180004893`
- `KERNEL32!GetLastError` at `0x18000491e`

## string_xrefs

- `0x1800048ab`: `inetsrv\iis\svcs\infocomm\log\plugin\extlogc.cpp`
- `0x180004936`: `inetsrv\iis\svcs\infocomm\log\plugin\extlogc.cpp`
- `0x1800048b2`: `Error %x on mb open\n`

## pseudocode

```c
__int64 __fastcall CEXTLOG::GetRegParameters(CEXTLOG *this, const char *a2, void *a3)
{
  int v6; // eax
  unsigned int v7; // r9d
  DWORD v8; // ecx
  DWORD v9; // eax
  unsigned int v10; // r9d
  DWORD LastError; // eax
  _DWORD *v12; // rbx
  ASCLOG_DATETIME_CACHE *v13; // rax
  ASCLOG_DATETIME_CACHE *v14; // rbx
  void *v16; // [rsp+40h] [rbp-38h] BYREF
  _DWORD v17[12]; // [rsp+48h] [rbp-30h] BYREF
  unsigned int v18; // [rsp+90h] [rbp+18h] BYREF

  CLogFileCtrl::GetRegParameters(this, a2, a3);
  v16 = a3;
  v17[0] = 0;
  v6 = (*(__int64 (__fastcall **)(void *, _QWORD, const char *, __int64, int, _DWORD *))(*(_QWORD *)a3 + 272LL))(
         a3,
         0,
         byte_180013080,
         1,
         5000,
         v17);
  v8 = v6;
  if ( v6 >= 0 )
  {
    v18 = 4;
    if ( !(unsigned int)MB::GetData((MB *)&v16, a2, 0xFADu, v7, 1u, (char *)this + 1576, &v18, 1u)
      && (g_dwDebugFlags & 3) != 0 )
    {
      LastError = GetLastError();
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\extlogc.cpp",
        535,
        "CEXTLOG::GetRegParameters",
        "Error %x on FieldMask GetDword\n",
        LastError);
    }
    v18 = 4;
    v12 = (_DWORD *)((char *)this + 1580);
    if ( !(unsigned int)MB::GetData((MB *)&v16, a2, 0xFAFu, v10, 1u, (char *)this + 1580, &v18, 1u) )
      *v12 = 0;
    if ( *v12 && !*((_QWORD *)this + 332) )
    {
      v13 = (ASCLOG_DATETIME_CACHE *)operator new(0x430u);
      v14 = v13;
      if ( v13 )
      {
        ASCLOG_DATETIME_CACHE::ASCLOG_DATETIME_CACHE(v13);
        *(_QWORD *)v14 = &ASCLOG_DATETIME_CACHE::`local vftable';
      }
      else
      {
        v14 = 0;
      }
      *((_QWORD *)this + 332) = v14;
    }
  }
  else
  {
    if ( (v6 & 0x1FFF0000) == 0x70000 )
      v8 = (unsigned __int16)v6;
    SetLastError(v8);
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v9 = GetLastError();
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\extlogc.cpp",
        525,
        "CEXTLOG::GetRegParameters",
        "Error %x on mb open\n",
        v9);
    }
  }
  if ( v17[0] )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 288LL))(v16);
  return 0;
}

```

## disassembly

```asm
0x180004810  push    rbx
0x180004812  push    rsi
0x180004813  push    rdi
0x180004814  push    r14
0x180004816  sub     rsp, 58h
0x18000481a  mov     rbx, r8
0x18000481d  mov     rsi, rdx
0x180004820  mov     rdi, rcx
0x180004823  call    ?GetRegParameters@CLogFileCtrl@@MEAAKPEBDPEAX@Z; CLogFileCtrl::GetRegParameters(char const *,void *)
0x180004828  mov     [rsp+78h+var_38], rbx
0x18000482d  lea     rcx, [rsp+78h+var_30]
0x180004832  mov     [rsp+78h+var_50], rcx
0x180004837  lea     r8, byte_180013080
0x18000483e  mov     [rsp+78h+var_30], 0
0x180004846  mov     r14d, 1
0x18000484c  mov     rax, [rbx]
0x18000484f  mov     r9d, r14d
0x180004852  xor     edx, edx
0x180004854  mov     [rsp+78h+var_58], 1388h
0x18000485c  mov     rcx, rbx
0x18000485f  mov     rax, [rax+110h]
0x180004866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000486b  mov     ecx, eax
0x18000486d  test    eax, eax
0x18000486f  jns     short loc_1800048CF
0x180004871  and     eax, 1FFF0000h
0x180004876  cmp     eax, 70000h
0x18000487b  jnz     short loc_180004880
0x18000487d  movzx   ecx, cx; dwErrCode
0x180004880  call    cs:__imp_SetLastError
0x180004886  test    byte ptr cs:g_dwDebugFlags, 3
0x18000488d  jz      loc_1800049D7
0x180004893  call    cs:__imp_GetLastError
0x180004899  mov     rcx, cs:g_pDebug
0x1800048a0  lea     r9, aCextlogGetregp; "CEXTLOG::GetRegParameters"
0x1800048a7  mov     dword ptr [rsp+78h+var_50], eax
0x1800048ab  lea     rdx, aInetsrvIisSvcs_1; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x1800048b2  lea     rax, aErrorXOnMbOpen; "Error %x on mb open\n"
0x1800048b9  mov     r8d, 20Dh
0x1800048bf  mov     qword ptr [rsp+78h+var_58], rax
0x1800048c4  call    cs:__imp_PuDbgPrint
0x1800048ca  jmp     loc_1800049D7
0x1800048cf  mov     [rsp+78h+var_40], r14d; unsigned int
0x1800048d4  lea     rcx, [rsp+78h+arg_10]
0x1800048dc  mov     [rsp+78h+var_48], rcx; unsigned int *
0x1800048e1  lea     rax, [rdi+628h]
0x1800048e8  mov     [rsp+78h+var_50], rax; void *
0x1800048ed  lea     rcx, [rsp+78h+var_38]; this
0x1800048f2  mov     ebx, 4
0x1800048f7  mov     [rsp+78h+var_58], r14d; unsigned int
0x1800048fc  mov     r8d, 0FADh; unsigned int
0x180004902  mov     [rsp+78h+arg_10], ebx
0x180004909  mov     rdx, rsi; char *
0x18000490c  call    ?GetData@MB@@QEAAHPEBDKKKPEAXPEAKK@Z; MB::GetData(char const *,ulong,ulong,ulong,void *,ulong *,ulong)
0x180004911  test    eax, eax
0x180004913  jnz     short loc_180004955
0x180004915  test    byte ptr cs:g_dwDebugFlags, 3
0x18000491c  jz      short loc_180004955
0x18000491e  call    cs:__imp_GetLastError
0x180004924  mov     rcx, cs:g_pDebug
0x18000492b  lea     r9, aCextlogGetregp; "CEXTLOG::GetRegParameters"
0x180004932  mov     dword ptr [rsp+78h+var_50], eax
0x180004936  lea     rdx, aInetsrvIisSvcs_1; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x18000493d  lea     rax, aErrorXOnFieldm; "Error %x on FieldMask GetDword\n"
0x180004944  mov     r8d, 217h
0x18000494a  mov     qword ptr [rsp+78h+var_58], rax
0x18000494f  call    cs:__imp_PuDbgPrint
0x180004955  mov     [rsp+78h+var_40], r14d; unsigned int
0x18000495a  lea     rax, [rsp+78h+arg_10]
0x180004962  mov     [rsp+78h+var_48], rax; unsigned int *
0x180004967  lea     rcx, [rsp+78h+var_38]; this
0x18000496c  mov     [rsp+78h+arg_10], ebx
0x180004973  mov     r8d, 0FAFh; unsigned int
0x180004979  lea     rbx, [rdi+62Ch]
0x180004980  mov     rdx, rsi; char *
0x180004983  mov     [rsp+78h+var_50], rbx; void *
0x180004988  mov     [rsp+78h+var_58], r14d; unsigned int
0x18000498d  call    ?GetData@MB@@QEAAHPEBDKKKPEAXPEAKK@Z; MB::GetData(char const *,ulong,ulong,ulong,void *,ulong *,ulong)
0x180004992  test    eax, eax
0x180004994  jnz     short loc_180004998
0x180004996  mov     [rbx], eax
0x180004998  cmp     dword ptr [rbx], 0
0x18000499b  jz      short loc_1800049D7
0x18000499d  cmp     qword ptr [rdi+0A60h], 0
0x1800049a5  jnz     short loc_1800049D7
0x1800049a7  mov     ecx, 430h; Size
0x1800049ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800049b1  mov     rbx, rax
0x1800049b4  test    rax, rax
0x1800049b7  jz      short loc_1800049CE
0x1800049b9  mov     rcx, rax
0x1800049bc  call    cs:__imp_??0ASCLOG_DATETIME_CACHE@@QEAA@XZ; ASCLOG_DATETIME_CACHE::ASCLOG_DATETIME_CACHE(void)
0x1800049c2  lea     rax, ??_SASCLOG_DATETIME_CACHE@@6B@; const ASCLOG_DATETIME_CACHE::`local vftable'
0x1800049c9  mov     [rbx], rax
0x1800049cc  jmp     short loc_1800049D0
0x1800049ce  xor     ebx, ebx
0x1800049d0  mov     [rdi+0A60h], rbx
0x1800049d7  mov     edx, [rsp+78h+var_30]
0x1800049db  test    edx, edx
0x1800049dd  jz      short loc_1800049F3
0x1800049df  mov     rcx, [rsp+78h+var_38]
0x1800049e4  mov     rax, [rcx]
0x1800049e7  mov     rax, [rax+120h]
0x1800049ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049f3  xor     eax, eax
0x1800049f5  add     rsp, 58h
0x1800049f9  pop     r14
0x1800049fb  pop     rdi
0x1800049fc  pop     rsi
0x1800049fd  pop     rbx
0x1800049fe  retn
```
