# CSTShell::UpdateStore(void)

- ea: `0x180004f40`
- end: `0x1800050fe`
- name: `?UpdateStore@CSTShell@@UEAAJXZ`
- size: `446`
- prototype: `__int64 __fastcall(CSTShell *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004f40`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x18000503e`
- `IisRTL!PuDbgPrint` at `0x180005099`
- `IisRTL!PuDbgPrint` at `0x18000503e`
- `IisRTL!PuDbgPrint` at `0x180005099`

## string_xrefs

- `0x18000501a`: `CSTShell::UpdateStore`
- `0x180005080`: `CSTShell::UpdateStore`
- `0x180005025`: `inetsrv\iis\mb\config\src\core\dispenser\cshell.cpp`
- `0x180005092`: `inetsrv\iis\mb\config\src\core\dispenser\cshell.cpp`
- `0x180005079`: `Detailed errors found during validation using WritePlugin`

## pseudocode

```c
__int64 __fastcall CSTShell::UpdateStore(CSTShell *this)
{
  int v1; // esi
  unsigned int i; // edi
  int v4; // eax
  __int64 v5; // rcx
  __int64 (__fastcall *v6)(__int64, _QWORD, _QWORD, _QWORD, __int64, unsigned int, _QWORD); // rax
  __int64 v8; // rcx
  __int64 v9; // [rsp+20h] [rbp-48h]
  int v10; // [rsp+40h] [rbp-28h] BYREF
  _DWORD v11[4]; // [rsp+48h] [rbp-20h] BYREF

  v1 = 0;
  v10 = 0;
  if ( !*((_QWORD *)this + 12) )
    goto LABEL_20;
  for ( i = 0; ; ++i )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *))(**((_QWORD **)this + 9) + 96LL))(
           *((_QWORD *)this + 9),
           i,
           &v10);
    if ( v4 == -2145318890 )
      break;
    switch ( v10 )
    {
      case 1:
        v5 = *((_QWORD *)this + 12);
        v6 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64, unsigned int, _QWORD))(*(_QWORD *)v5 + 24LL);
        break;
      case 2:
        v5 = *((_QWORD *)this + 12);
        v6 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64, unsigned int, _QWORD))(*(_QWORD *)v5 + 32LL);
        break;
      case 3:
        v5 = *((_QWORD *)this + 12);
        v6 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64, unsigned int, _QWORD))(*(_QWORD *)v5 + 40LL);
        break;
      default:
        goto LABEL_11;
    }
    LODWORD(v9) = *((_DWORD *)this + 12);
    v4 = v6(v5, *((_QWORD *)this + 7), *((_QWORD *)this + 4), *((_QWORD *)this + 5), v9, i, *((_QWORD *)this + 8));
LABEL_11:
    if ( v4 < 0 )
    {
      v11[2] = -1;
      v11[0] = i;
      v11[1] = v4;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\config\\src\\core\\dispenser\\cshell.cpp",
          235,
          "CSTShell::UpdateStore",
          "Detailed error: hr = 0x%x",
          v4);
      (*(void (__fastcall **)(_QWORD, _DWORD *))(**((_QWORD **)this + 9) + 120LL))(*((_QWORD *)this + 9), v11);
      v1 = 1;
    }
  }
  if ( !v1 )
  {
LABEL_20:
    v8 = *((_QWORD *)this + 10);
    if ( v8 )
      return (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 40LL))(v8, *((_QWORD *)this + 8));
    else
      return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 112LL))(*((_QWORD *)this + 8));
  }
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\config\\src\\core\\dispenser\\cshell.cpp",
      244,
      "CSTShell::UpdateStore",
      "Detailed errors found during validation using WritePlugin");
  return 2149648415LL;
}

```

## disassembly

```asm
0x180004f40  mov     [rsp+arg_8], rbx
0x180004f45  mov     [rsp+arg_10], rsi
0x180004f4a  push    rdi
0x180004f4b  sub     rsp, 60h
0x180004f4f  mov     rax, cs:__security_cookie
0x180004f56  xor     rax, rsp
0x180004f59  mov     [rsp+68h+var_10], rax
0x180004f5e  xor     esi, esi
0x180004f60  mov     [rsp+68h+var_28], 0
0x180004f68  mov     rbx, rcx
0x180004f6b  cmp     [rcx+60h], rsi
0x180004f6f  jz      loc_1800050A6
0x180004f75  xor     edi, edi
0x180004f77  mov     rcx, [rbx+48h]
0x180004f7b  lea     r8, [rsp+68h+var_28]
0x180004f80  mov     edx, edi
0x180004f82  mov     rax, [rcx]
0x180004f85  mov     rax, [rax+60h]
0x180004f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f8e  cmp     eax, 80210816h
0x180004f93  jz      loc_180005065
0x180004f99  mov     ecx, [rsp+68h+var_28]
0x180004f9d  sub     ecx, 1
0x180004fa0  jz      short loc_180004FC6
0x180004fa2  sub     ecx, 1
0x180004fa5  jz      short loc_180004FB9
0x180004fa7  cmp     ecx, 1
0x180004faa  jnz     short loc_180004FF6
0x180004fac  mov     rcx, [rbx+60h]
0x180004fb0  mov     rax, [rcx]
0x180004fb3  mov     rax, [rax+28h]
0x180004fb7  jmp     short loc_180004FD1
0x180004fb9  mov     rcx, [rbx+60h]
0x180004fbd  mov     rax, [rcx]
0x180004fc0  mov     rax, [rax+20h]
0x180004fc4  jmp     short loc_180004FD1
0x180004fc6  mov     rcx, [rbx+60h]
0x180004fca  mov     rax, [rcx]
0x180004fcd  mov     rax, [rax+18h]
0x180004fd1  mov     rdx, [rbx+40h]
0x180004fd5  mov     r9, [rbx+28h]
0x180004fd9  mov     r8, [rbx+20h]
0x180004fdd  mov     [rsp+68h+var_38], rdx
0x180004fe2  mov     edx, [rbx+30h]
0x180004fe5  mov     [rsp+68h+var_40], edi
0x180004fe9  mov     dword ptr [rsp+68h+var_48], edx
0x180004fed  mov     rdx, [rbx+38h]
0x180004ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ff6  test    eax, eax
0x180004ff8  jns     short loc_18000505E
0x180004ffa  test    byte ptr cs:g_dwDebugFlags, 3
0x180005001  mov     [rsp+68h+var_18], 0FFFFFFFFh
0x180005009  mov     [rsp+68h+var_20], edi
0x18000500d  mov     [rsp+68h+var_1C], eax
0x180005011  jz      short loc_180005044
0x180005013  mov     rcx, cs:g_pDebug
0x18000501a  lea     r9, aCstshellUpdate; "CSTShell::UpdateStore"
0x180005021  mov     [rsp+68h+var_40], eax
0x180005025  lea     rdx, aInetsrvIisMbCo_16; "inetsrv\\iis\\mb\\config\\src\\core\\di"...
0x18000502c  lea     rax, aDetailedErrorH; "Detailed error: hr = 0x%x"
0x180005033  mov     r8d, 0EBh
0x180005039  mov     [rsp+68h+var_48], rax
0x18000503e  call    cs:__imp_PuDbgPrint
0x180005044  mov     rcx, [rbx+48h]
0x180005048  lea     rdx, [rsp+68h+var_20]
0x18000504d  mov     rax, [rcx]
0x180005050  mov     rax, [rax+78h]
0x180005054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005059  mov     esi, 1
0x18000505e  inc     edi
0x180005060  jmp     loc_180004F77
0x180005065  test    esi, esi
0x180005067  jz      short loc_1800050A6
0x180005069  test    byte ptr cs:g_dwDebugFlags, 3
0x180005070  jz      short loc_18000509F
0x180005072  mov     rcx, cs:g_pDebug
0x180005079  lea     rax, aDetailedErrors; "Detailed errors found during validation"...
0x180005080  lea     r9, aCstshellUpdate; "CSTShell::UpdateStore"
0x180005087  mov     [rsp+68h+var_48], rax
0x18000508c  mov     r8d, 0F4h
0x180005092  lea     rdx, aInetsrvIisMbCo_16; "inetsrv\\iis\\mb\\config\\src\\core\\di"...
0x180005099  call    cs:__imp_PuDbgPrint
0x18000509f  mov     eax, 8021081Fh
0x1800050a4  jmp     short loc_1800050DF
0x1800050a6  mov     rcx, [rbx+50h]
0x1800050aa  test    rcx, rcx
0x1800050ad  jz      short loc_1800050C1
0x1800050af  mov     rax, [rcx]
0x1800050b2  mov     rdx, [rbx+40h]
0x1800050b6  mov     rax, [rax+28h]
0x1800050ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050bf  jmp     short loc_1800050D1
0x1800050c1  mov     rcx, [rbx+40h]
0x1800050c5  mov     rax, [rcx]
0x1800050c8  mov     rax, [rax+70h]
0x1800050cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050d1  test    eax, eax
0x1800050d3  js      short loc_1800050DF
0x1800050d5  test    esi, esi
0x1800050d7  mov     ecx, 8021081Fh
0x1800050dc  cmovnz  eax, ecx
0x1800050df  mov     rcx, [rsp+68h+var_10]
0x1800050e4  xor     rcx, rsp; StackCookie
0x1800050e7  call    __security_check_cookie
0x1800050ec  lea     r11, [rsp+68h+var_8]
0x1800050f1  mov     rbx, [r11+18h]
0x1800050f5  mov     rsi, [r11+20h]
0x1800050f9  mov     rsp, r11
0x1800050fc  pop     rdi
0x1800050fd  retn
```
