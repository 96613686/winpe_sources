# _ChangeNotifyHandlers(PSCNEVENT)

- ea: `0x180091d78`
- end: `0x180091e84`
- name: `?_ChangeNotifyHandlers@@YAJW4PSCNEVENT@@@Z`
- size: `268`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180035af0`
- `0x1800362d0`
- `0x180037120`
- `0x1800387e0`
- `0x180039330`

## callees

- `0x18006ed20`
- `0x180091d78`
- `0x180092160`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091e43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091e43`
- `SHCORE!__imp_QuerySourceCreateFromKeyEx` at `0x180091dc4`
- `SHCORE!__imp_QuerySourceCreateFromKeyEx` at `0x180091dc4`
- `SHCORE!__imp_GUIDFromStringW` at `0x180091e2c`
- `SHCORE!__imp_GUIDFromStringW` at `0x180091e2c`

## pseudocode

```c
__int64 _ChangeNotifyHandlers()
{
  int v0; // ebx
  __int64 v1; // rcx
  LPVOID pv; // [rsp+30h] [rbp-30h] BYREF
  __int64 v4; // [rsp+38h] [rbp-28h] BYREF
  __int64 v5; // [rsp+40h] [rbp-20h] BYREF
  __int128 v6; // [rsp+48h] [rbp-18h] BYREF

  v5 = 0;
  v0 = QuerySourceCreateFromKeyEx(
         -2147483646,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\PropertySystem\\ChangeNotifyHandlers",
         0,
         0,
         &GUID_7bc28ac2_0d9c_4941_bb9a_72becb184fac,
         &v5);
  if ( v0 >= 0 )
  {
    v4 = 0;
    v0 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 72LL))(v5, &v4);
    if ( v0 >= 0 )
    {
      for ( pv = 0;
            !(*(unsigned int (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v4 + 24LL))(v4, 1, &pv);
            CoTaskMemFree(pv) )
      {
        v6 = 0;
        if ( (unsigned int)GUIDFromStringW(pv, &v6) )
          _NotifyChangeNotifyHandler(v1, &v6);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180091d78  mov     [rsp-8+arg_0], rbx
0x180091d7d  push    rbp
0x180091d7e  mov     rbp, rsp
0x180091d81  sub     rsp, 60h
0x180091d85  mov     rax, cs:__security_cookie
0x180091d8c  xor     rax, rsp
0x180091d8f  mov     [rbp+var_8], rax
0x180091d93  lea     rax, [rbp+var_20]
0x180091d97  mov     [rbp+var_20], 0
0x180091d9f  mov     [rsp+60h+var_38], rax
0x180091da4  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180091dab  lea     rax, _GUID_7bc28ac2_0d9c_4941_bb9a_72becb184fac
0x180091db2  xor     r9d, r9d
0x180091db5  xor     r8d, r8d
0x180091db8  mov     [rsp+60h+var_40], rax
0x180091dbd  mov     rcx, 0FFFFFFFF80000002h
0x180091dc4  call    cs:__imp_QuerySourceCreateFromKeyEx
0x180091dca  mov     ebx, eax
0x180091dcc  test    eax, eax
0x180091dce  js      loc_180091E6B
0x180091dd4  mov     rcx, [rbp+var_20]
0x180091dd8  lea     rdx, [rbp+var_28]
0x180091ddc  mov     [rbp+var_28], 0
0x180091de4  mov     rax, [rcx]
0x180091de7  mov     rax, [rax+48h]
0x180091deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091df0  mov     ebx, eax
0x180091df2  test    eax, eax
0x180091df4  js      short loc_180091E5B
0x180091df6  mov     [rbp+pv], 0
0x180091dfe  mov     rcx, [rbp+var_28]
0x180091e02  lea     r8, [rbp+pv]
0x180091e06  xor     r9d, r9d
0x180091e09  mov     rax, [rcx]
0x180091e0c  lea     edx, [r9+1]
0x180091e10  mov     rax, [rax+18h]
0x180091e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091e19  test    eax, eax
0x180091e1b  jnz     short loc_180091E4B
0x180091e1d  mov     rcx, [rbp+pv]
0x180091e21  lea     rdx, [rbp+var_18]
0x180091e25  xorps   xmm0, xmm0
0x180091e28  movups  [rbp+var_18], xmm0
0x180091e2c  call    cs:__imp_GUIDFromStringW
0x180091e32  test    eax, eax
0x180091e34  jz      short loc_180091E3F
0x180091e36  lea     rdx, [rbp+var_18]
0x180091e3a  call    ?_NotifyChangeNotifyHandler@@YAJW4PSCNEVENT@@AEBU_GUID@@@Z; _NotifyChangeNotifyHandler(PSCNEVENT,_GUID const &)
0x180091e3f  mov     rcx, [rbp+pv]; pv
0x180091e43  call    cs:__imp_CoTaskMemFree
0x180091e49  jmp     short loc_180091DFE
0x180091e4b  mov     rcx, [rbp+var_28]
0x180091e4f  mov     rax, [rcx]
0x180091e52  mov     rax, [rax+10h]
0x180091e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091e5b  mov     rcx, [rbp+var_20]
0x180091e5f  mov     rax, [rcx]
0x180091e62  mov     rax, [rax+10h]
0x180091e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091e6b  mov     eax, ebx
0x180091e6d  mov     rcx, [rbp+var_8]
0x180091e71  xor     rcx, rsp; StackCookie
0x180091e74  call    __security_check_cookie
0x180091e79  mov     rbx, [rsp+60h+arg_0]
0x180091e7e  add     rsp, 60h
0x180091e82  pop     rbp
0x180091e83  retn
```
