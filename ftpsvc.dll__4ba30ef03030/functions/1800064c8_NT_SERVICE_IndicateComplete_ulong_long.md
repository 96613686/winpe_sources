# NT_SERVICE::IndicateComplete(ulong,long)

- ea: `0x1800064c8`
- end: `0x180006603`
- name: `?IndicateComplete@NT_SERVICE@@AEAAJKJ@Z`
- size: `315`
- prototype: `__int64 __fastcall(NT_SERVICE *__hidden this, unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006978`

## callees

- `0x1800064c8`
- `0x180006890`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800065c2`
- `KERNEL32!LeaveCriticalSection` at `0x1800065c2`
- `KERNEL32!EnterCriticalSection` at `0x180006514`
- `KERNEL32!EnterCriticalSection` at `0x180006514`
- `KERNEL32!GetLastError` at `0x1800065aa`
- `KERNEL32!GetLastError` at `0x1800065aa`
- `ADVAPI32!SetServiceStatus` at `0x180006561`
- `ADVAPI32!SetServiceStatus` at `0x180006561`
- `iisutil!PuDbgPrint` at `0x1800065a4`
- `iisutil!PuDbgPrint` at `0x1800065a4`

## string_xrefs

- `0x18000659d`: `inetsrv\iis\iisrearc\ftp\server\core\nt_service.cxx`
- `0x18000658b`: `NT_SERVICE::IndicateComplete`

## pseudocode

```c
__int64 __fastcall NT_SERVICE::IndicateComplete(NT_SERVICE *this, unsigned int a2, int a3)
{
  int v6; // eax
  struct _RTL_CRITICAL_SECTION *v7; // rbp
  int v8; // ecx
  unsigned int v9; // ebx
  signed int LastError; // eax
  DWORD v12; // edx

  if ( *((_DWORD *)this + 156) && *((_QWORD *)this + 1) )
  {
    if ( a2 <= 7 && (v6 = 146, _bittest(&v6, a2)) )
    {
      v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 584);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 584));
      *((_DWORD *)this + 5) = a2;
      *((_DWORD *)this + 4) = 32;
      if ( a3 >= 0 )
      {
        v8 = 0;
      }
      else
      {
        v8 = (unsigned __int16)a3;
        if ( (a3 & 0x1FFF0000) != 0x70000 )
          v8 = a3;
      }
      *((_DWORD *)this + 7) = v8;
      *(_QWORD *)((char *)this + 36) = 0;
      if ( a2 == 4 )
        *((_DWORD *)this + 6) = 7;
      if ( SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 1), (LPSERVICE_STATUS)((char *)this + 16)) )
      {
        v9 = 0;
      }
      else
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\nt_service.cxx",
            346,
            "NT_SERVICE::IndicateComplete",
            "Address = %x\n",
            (_DWORD)this + 16);
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
      }
      LeaveCriticalSection(v7);
      return v9;
    }
    else
    {
      return 2147942487LL;
    }
  }
  else
  {
    if ( a3 >= 0 )
    {
      v12 = 0;
    }
    else
    {
      v12 = (unsigned __int16)a3;
      if ( (a3 & 0x1FFF0000) != 0x70000 )
        v12 = a3;
    }
    NT_SERVICE::ReportFatalServiceStartupError((const unsigned __int16 *)this + 22, v12);
    return 0;
  }
}

```

## disassembly

```asm
0x1800064c8  push    rbx
0x1800064ca  push    rbp
0x1800064cb  push    rsi
0x1800064cc  push    rdi
0x1800064cd  push    r14
0x1800064cf  sub     rsp, 30h
0x1800064d3  cmp     dword ptr [rcx+270h], 0
0x1800064da  mov     edi, r8d
0x1800064dd  mov     esi, edx
0x1800064df  mov     rbx, rcx
0x1800064e2  jz      loc_1800065D3
0x1800064e8  cmp     qword ptr [rcx+8], 0
0x1800064ed  jz      loc_1800065D3
0x1800064f3  cmp     edx, 7
0x1800064f6  ja      loc_1800065CC
0x1800064fc  mov     eax, 92h
0x180006501  bt      eax, edx
0x180006504  jnb     loc_1800065CC
0x18000650a  lea     rbp, [rcx+248h]
0x180006511  mov     rcx, rbp; lpCriticalSection
0x180006514  call    cs:__imp_EnterCriticalSection
0x18000651a  lea     r14, [rbx+10h]
0x18000651e  mov     [r14+4], esi
0x180006522  mov     dword ptr [r14], 20h ; ' '
0x180006529  test    edi, edi
0x18000652b  jns     short loc_180006541
0x18000652d  mov     eax, edi
0x18000652f  movzx   ecx, di
0x180006532  and     eax, 1FFF0000h
0x180006537  cmp     eax, 70000h
0x18000653c  cmovnz  ecx, edi
0x18000653f  jmp     short loc_180006543
0x180006541  xor     ecx, ecx
0x180006543  mov     [rbx+1Ch], ecx
0x180006546  mov     qword ptr [rbx+24h], 0
0x18000654e  cmp     esi, 4
0x180006551  jnz     short loc_18000655A
0x180006553  mov     dword ptr [rbx+18h], 7
0x18000655a  mov     rcx, [rbx+8]; hServiceStatus
0x18000655e  mov     rdx, r14; lpServiceStatus
0x180006561  call    cs:__imp_SetServiceStatus
0x180006567  test    eax, eax
0x180006569  jz      short loc_18000656F
0x18000656b  xor     ebx, ebx
0x18000656d  jmp     short loc_1800065BF
0x18000656f  test    byte ptr cs:g_dwDebugFlags, 3
0x180006576  jz      short loc_1800065AA
0x180006578  mov     rcx, cs:g_pDebug
0x18000657f  lea     rax, aAddressX; "Address = %x\n"
0x180006586  mov     [rsp+58h+var_30], r14
0x18000658b  lea     r9, aNtServiceIndic; "NT_SERVICE::IndicateComplete"
0x180006592  mov     r8d, 15Ah
0x180006598  mov     [rsp+58h+var_38], rax
0x18000659d  lea     rdx, aInetsrvIisIisr_38; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x1800065a4  call    cs:__imp_PuDbgPrint
0x1800065aa  call    cs:__imp_GetLastError
0x1800065b0  mov     ebx, eax
0x1800065b2  test    eax, eax
0x1800065b4  jle     short loc_1800065BF
0x1800065b6  movzx   ebx, ax
0x1800065b9  or      ebx, 80070000h
0x1800065bf  mov     rcx, rbp; lpCriticalSection
0x1800065c2  call    cs:__imp_LeaveCriticalSection
0x1800065c8  mov     eax, ebx
0x1800065ca  jmp     short loc_1800065F8
0x1800065cc  mov     eax, 80070057h
0x1800065d1  jmp     short loc_1800065F8
0x1800065d3  test    edi, edi
0x1800065d5  jns     short loc_1800065EB
0x1800065d7  mov     eax, edi
0x1800065d9  movzx   edx, di
0x1800065dc  and     eax, 1FFF0000h
0x1800065e1  cmp     eax, 70000h
0x1800065e6  cmovnz  edx, edi
0x1800065e9  jmp     short loc_1800065ED
0x1800065eb  xor     edx, edx; unsigned int
0x1800065ed  add     rcx, 2Ch ; ','; unsigned __int16 *
0x1800065f1  call    ?ReportFatalServiceStartupError@NT_SERVICE@@SAXPEBGK@Z; NT_SERVICE::ReportFatalServiceStartupError(ushort const *,ulong)
0x1800065f6  xor     eax, eax
0x1800065f8  add     rsp, 30h
0x1800065fc  pop     r14
0x1800065fe  pop     rdi
0x1800065ff  pop     rsi
0x180006600  pop     rbp
0x180006601  pop     rbx
0x180006602  retn
```
