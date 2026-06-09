# CLogFileCtrl::WriteLogDirectives(ulong)

- ea: `0x180003300`
- end: `0x18000336d`
- name: `?WriteLogDirectives@CLogFileCtrl@@MEAAHK@Z`
- size: `109`
- prototype: `__int64 __fastcall(CLogFileCtrl *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003300`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x180003359`
- `IisRTL!PuDbgPrint` at `0x180003359`
- `KERNEL32!SetLastError` at `0x180003323`
- `KERNEL32!SetLastError` at `0x180003323`

## string_xrefs

- `0x180003339`: `Unable to write directive\n`
- `0x180003340`: `CLogFileCtrl::WriteLogDirectives`
- `0x180003352`: `inetsrv\iis\svcs\infocomm\log\plugin\filectl.cpp`

## pseudocode

```c
__int64 __fastcall CLogFileCtrl::WriteLogDirectives(CLogFileCtrl *this, unsigned int a2)
{
  if ( *((_QWORD *)this + 13) >= 0xFFFFFFFF
    || *((_QWORD *)this + 12) + (unsigned __int64)a2 < *((unsigned int *)this + 26) )
  {
    return 1;
  }
  SetLastError(0x7Au);
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\filectl.cpp",
      813,
      "CLogFileCtrl::WriteLogDirectives",
      "Unable to write directive\n");
  return 0;
}

```

## disassembly

```asm
0x180003300  sub     rsp, 38h
0x180003304  cmp     dword ptr [rcx+6Ch], 0
0x180003308  jnz     short loc_180003363
0x18000330a  cmp     dword ptr [rcx+68h], 0FFFFFFFFh
0x18000330e  jz      short loc_180003363
0x180003310  mov     eax, [rcx+68h]
0x180003313  mov     edx, edx
0x180003315  add     rdx, [rcx+60h]
0x180003319  cmp     rdx, rax
0x18000331c  jb      short loc_180003363
0x18000331e  mov     ecx, 7Ah ; 'z'; dwErrCode
0x180003323  call    cs:__imp_SetLastError
0x180003329  test    byte ptr cs:g_dwDebugFlags, 3
0x180003330  jz      short loc_18000335F
0x180003332  mov     rcx, cs:g_pDebug
0x180003339  lea     rax, aUnableToWriteD; "Unable to write directive\n"
0x180003340  lea     r9, aClogfilectrlWr; "CLogFileCtrl::WriteLogDirectives"
0x180003347  mov     [rsp+38h+var_18], rax
0x18000334c  mov     r8d, 32Dh
0x180003352  lea     rdx, aInetsrvIisSvcs_0; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x180003359  call    cs:__imp_PuDbgPrint
0x18000335f  xor     eax, eax
0x180003361  jmp     short loc_180003368
0x180003363  mov     eax, 1
0x180003368  add     rsp, 38h
0x18000336c  retn
```
