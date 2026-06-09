# CNetpEventLogger::Initialize(_EVTLOGGER_INIT *)

- ea: `0x18002c374`
- end: `0x18002c512`
- name: `?Initialize@CNetpEventLogger@@AEAAJPEAU_EVTLOGGER_INIT@@@Z`
- size: `414`
- prototype: `__int64 __fastcall(CNetpEventLogger *__hidden this, struct _EVTLOGGER_INIT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180027960`

## callees

- `0x1800290b0`
- `0x18002c374`
- `0x1800415b0`
- `0x1800416c0`
- `0x180041874`
- `0x180042bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c4a9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c4a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c437`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002c42d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002c42d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c494`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c494`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18002c4d2`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18002c4d2`

## pseudocode

```c
signed int __fastcall CNetpEventLogger::Initialize(CNetpEventLogger *this, struct _EVTLOGGER_INIT *a2)
{
  const unsigned __int16 *v4; // rdx
  signed int result; // eax
  CNetpEventLogger *v6; // rcx
  CNetpEventLogger *v7; // rcx
  CNetpEventLogger *v8; // rcx
  __int64 v9; // rax
  unsigned int EventSuppressionTimeout; // esi
  __int64 v11; // rcx

  if ( !a2 )
    return -2147024809;
  v4 = (const unsigned __int16 *)*((_QWORD *)a2 + 2);
  if ( !v4 || !*((_QWORD *)a2 + 3) || !*((_QWORD *)a2 + 4) )
    return -2147024809;
  *((_DWORD *)this + 3) = *(_DWORD *)a2;
  *((_DWORD *)this + 5) = *((_DWORD *)a2 + 1);
  *((_DWORD *)this + 6) = *((_DWORD *)a2 + 2);
  *((_DWORD *)this + 4) = -1;
  result = CNetpEventLogger::MakeStringCopy(this, v4, (unsigned __int16 **)this + 8);
  if ( result >= 0 )
  {
    result = CNetpEventLogger::MakeStringCopy(v6, *((const unsigned __int16 **)a2 + 3), (unsigned __int16 **)this + 9);
    if ( result >= 0 )
    {
      result = CNetpEventLogger::MakeStringCopy(
                 v7,
                 *((const unsigned __int16 **)a2 + 4),
                 (unsigned __int16 **)this + 10);
      if ( result >= 0 )
      {
        result = CNetpEventLogger::MakeStringCopy(
                   v8,
                   *((const unsigned __int16 **)a2 + 5),
                   (unsigned __int16 **)this + 11);
        if ( result >= 0 )
        {
          if ( *((_DWORD *)a2 + 12) || GetModuleHandleExW(1u, *((LPCWSTR *)this + 11), (HMODULE *)this + 12) )
          {
            v9 = NetpEventlogOpen(*((wchar_t **)this + 8));
            *((_QWORD *)this + 4) = v9;
            if ( v9 )
            {
              EventSuppressionTimeout = 0;
              RegOpenKeyExW(HKEY_LOCAL_MACHINE, *((LPCWSTR *)this + 9), 0, 0x20019u, (PHKEY)this + 7);
              if ( *((_QWORD *)this + 7) )
                *((_QWORD *)this + 5) = CreateEventW(0, 0, 0, 0);
              v11 = *((_QWORD *)this + 5);
              if ( v11 )
                *((_QWORD *)this + 6) = RegisterWaitForSingleObjectEx(
                                          v11,
                                          CNetpEventLogger::WaitCallback,
                                          this,
                                          0xFFFFFFFFLL,
                                          128);
              if ( *((_QWORD *)this + 7) )
                EventSuppressionTimeout = CNetpEventLogger::ReadEventSuppressionTimeout(this);
              CNetpEventLogger::SetTimeout(this, EventSuppressionTimeout);
              CNetpEventLogger::DoRegChangeNotify(this);
              return 0;
            }
            else
            {
              return -2147024882;
            }
          }
          else
          {
            result = GetLastError();
            if ( result > 0 )
              return (unsigned __int16)result | 0x80070000;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002c374  push    rbx
0x18002c376  push    rsi
0x18002c377  push    rdi
0x18002c378  push    r14
0x18002c37a  push    r15
0x18002c37c  sub     rsp, 30h
0x18002c380  mov     rdi, rdx
0x18002c383  mov     rbx, rcx
0x18002c386  test    rdx, rdx
0x18002c389  jz      loc_18002C501
0x18002c38f  mov     rdx, [rdx+10h]; unsigned __int16 *
0x18002c393  test    rdx, rdx
0x18002c396  jz      loc_18002C501
0x18002c39c  cmp     qword ptr [rdi+18h], 0
0x18002c3a1  jz      loc_18002C501
0x18002c3a7  cmp     qword ptr [rdi+20h], 0
0x18002c3ac  jz      loc_18002C501
0x18002c3b2  mov     eax, [rdi]
0x18002c3b4  lea     r8, [rcx+40h]; unsigned __int16 **
0x18002c3b8  mov     [rcx+0Ch], eax
0x18002c3bb  mov     eax, [rdi+4]
0x18002c3be  mov     [rcx+14h], eax
0x18002c3c1  mov     eax, [rdi+8]
0x18002c3c4  mov     [rcx+18h], eax
0x18002c3c7  mov     dword ptr [rcx+10h], 0FFFFFFFFh
0x18002c3ce  call    ?MakeStringCopy@CNetpEventLogger@@AEAAJPEBGPEAPEAG@Z; CNetpEventLogger::MakeStringCopy(ushort const *,ushort * *)
0x18002c3d3  test    eax, eax
0x18002c3d5  js      loc_18002C506
0x18002c3db  mov     rdx, [rdi+18h]; unsigned __int16 *
0x18002c3df  lea     r8, [rbx+48h]; unsigned __int16 **
0x18002c3e3  call    ?MakeStringCopy@CNetpEventLogger@@AEAAJPEBGPEAPEAG@Z; CNetpEventLogger::MakeStringCopy(ushort const *,ushort * *)
0x18002c3e8  test    eax, eax
0x18002c3ea  js      loc_18002C506
0x18002c3f0  mov     rdx, [rdi+20h]; unsigned __int16 *
0x18002c3f4  lea     r8, [rbx+50h]; unsigned __int16 **
0x18002c3f8  call    ?MakeStringCopy@CNetpEventLogger@@AEAAJPEBGPEAPEAG@Z; CNetpEventLogger::MakeStringCopy(ushort const *,ushort * *)
0x18002c3fd  test    eax, eax
0x18002c3ff  js      loc_18002C506
0x18002c405  mov     rdx, [rdi+28h]; unsigned __int16 *
0x18002c409  lea     r8, [rbx+58h]; unsigned __int16 **
0x18002c40d  call    ?MakeStringCopy@CNetpEventLogger@@AEAAJPEBGPEAPEAG@Z; CNetpEventLogger::MakeStringCopy(ushort const *,ushort * *)
0x18002c412  test    eax, eax
0x18002c414  js      loc_18002C506
0x18002c41a  cmp     dword ptr [rdi+30h], 0
0x18002c41e  jnz     short loc_18002C452
0x18002c420  mov     rdx, [rbx+58h]; lpModuleName
0x18002c424  lea     r8, [rbx+60h]; phModule
0x18002c428  mov     ecx, 1; dwFlags
0x18002c42d  call    cs:__imp_GetModuleHandleExW
0x18002c433  test    eax, eax
0x18002c435  jnz     short loc_18002C452
0x18002c437  call    cs:__imp_GetLastError
0x18002c43d  test    eax, eax
0x18002c43f  jle     loc_18002C506
0x18002c445  movzx   eax, ax
0x18002c448  or      eax, 80070000h
0x18002c44d  jmp     loc_18002C506
0x18002c452  imul    edx, [rbx+10h], 3E8h
0x18002c459  mov     rcx, [rbx+40h]; Source
0x18002c45d  call    NetpEventlogOpen
0x18002c462  mov     [rbx+20h], rax
0x18002c466  test    rax, rax
0x18002c469  jnz     short loc_18002C475
0x18002c46b  mov     eax, 8007000Eh
0x18002c470  jmp     loc_18002C506
0x18002c475  mov     rdx, [rbx+48h]; lpSubKey
0x18002c479  lea     rdi, [rbx+38h]
0x18002c47d  mov     r9d, 20019h; samDesired
0x18002c483  mov     [rsp+58h+phkResult], rdi; phkResult
0x18002c488  xor     r8d, r8d; ulOptions
0x18002c48b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c492  xor     esi, esi
0x18002c494  call    cs:__imp_RegOpenKeyExW
0x18002c49a  cmp     [rdi], rsi
0x18002c49d  jz      short loc_18002C4B3
0x18002c49f  xor     r9d, r9d; lpName
0x18002c4a2  xor     r8d, r8d; bInitialState
0x18002c4a5  xor     edx, edx; bManualReset
0x18002c4a7  xor     ecx, ecx; lpEventAttributes
0x18002c4a9  call    cs:__imp_CreateEventW
0x18002c4af  mov     [rbx+28h], rax
0x18002c4b3  mov     rcx, [rbx+28h]
0x18002c4b7  test    rcx, rcx
0x18002c4ba  jz      short loc_18002C4DC
0x18002c4bc  or      r9d, 0FFFFFFFFh
0x18002c4c0  mov     dword ptr [rsp+58h+phkResult], 80h
0x18002c4c8  mov     r8, rbx
0x18002c4cb  lea     rdx, ?WaitCallback@CNetpEventLogger@@CAXPEAXE@Z; CNetpEventLogger::WaitCallback(void *,uchar)
0x18002c4d2  call    cs:__imp_RegisterWaitForSingleObjectEx
0x18002c4d8  mov     [rbx+30h], rax
0x18002c4dc  cmp     [rdi], rsi
0x18002c4df  jz      short loc_18002C4EB
0x18002c4e1  mov     rcx, rbx; this
0x18002c4e4  call    ?ReadEventSuppressionTimeout@CNetpEventLogger@@AEAAKXZ; CNetpEventLogger::ReadEventSuppressionTimeout(void)
0x18002c4e9  mov     esi, eax
0x18002c4eb  mov     edx, esi; unsigned int
0x18002c4ed  mov     rcx, rbx; this
0x18002c4f0  call    ?SetTimeout@CNetpEventLogger@@AEAAXK@Z; CNetpEventLogger::SetTimeout(ulong)
0x18002c4f5  mov     rcx, rbx; this
0x18002c4f8  call    ?DoRegChangeNotify@CNetpEventLogger@@AEAAXXZ; CNetpEventLogger::DoRegChangeNotify(void)
0x18002c4fd  xor     eax, eax
0x18002c4ff  jmp     short loc_18002C506
0x18002c501  mov     eax, 80070057h
0x18002c506  add     rsp, 30h
0x18002c50a  pop     r15
0x18002c50c  pop     r14
0x18002c50e  pop     rdi
0x18002c50f  pop     rsi
0x18002c510  pop     rbx
0x18002c511  retn
```
