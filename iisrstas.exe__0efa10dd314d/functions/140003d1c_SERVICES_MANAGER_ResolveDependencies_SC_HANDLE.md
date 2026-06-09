# SERVICES_MANAGER::ResolveDependencies(SC_HANDLE__ *)

- ea: `0x140003d1c`
- end: `0x140003dbe`
- name: `?ResolveDependencies@SERVICES_MANAGER@@QEAAJPEAUSC_HANDLE__@@@Z`
- size: `162`
- prototype: `__int64 __fastcall(SERVICES_MANAGER *__hidden this, struct SC_HANDLE__ *)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140003674`
- `0x140004114`
- `0x1400042d8`
- `0x140004628`

## callees

- `0x140003d1c`
- `0x140003dc4`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x140003dad`
- `iisutil!PuDbgPrintError` at `0x140003dad`

## string_xrefs

- `0x140003d85`: `Unable to retrieve service name to list\n`
- `0x140003d91`: `SERVICES_MANAGER::ResolveDependencies`
- `0x140003da6`: `inetsrv\iis\svcs\restart\wasrsta\services.cxx`

## pseudocode

```c
__int64 __fastcall SERVICES_MANAGER::ResolveDependencies(SERVICES_MANAGER *this, SC_HANDLE a2)
{
  int v4; // ebx
  __int64 v5; // rsi

  if ( *((_DWORD *)this + 2) )
  {
    v4 = 0;
    v5 = 0;
    if ( *(_DWORD *)this )
    {
      while ( (unsigned int)v5 <= *((_DWORD *)this + 2) - 1 )
      {
        v4 = SERVICES_MANAGER::ResolveDependenciesRecursive(
               this,
               a2,
               *(unsigned __int16 **)(*((_QWORD *)this + 6) + 8 * v5),
               1);
        if ( v4 >= 0 )
        {
          v5 = (unsigned int)(v5 + 1);
          if ( (unsigned int)v5 < *(_DWORD *)this )
            continue;
        }
        return (unsigned int)v4;
      }
      v4 = -2147023483;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\svcs\\restart\\wasrsta\\services.cxx",
          172,
          "SERVICES_MANAGER::ResolveDependencies",
          -2147023483,
          "Unable to retrieve service name to list\n");
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140003d1c  push    rbx
0x140003d1e  push    rbp
0x140003d1f  push    rsi
0x140003d20  push    rdi
0x140003d21  sub     rsp, 38h
0x140003d25  cmp     dword ptr [rcx+8], 0
0x140003d29  mov     rbp, rdx
0x140003d2c  mov     rdi, rcx
0x140003d2f  jnz     short loc_140003D38
0x140003d31  mov     ebx, 80004005h
0x140003d36  jmp     short loc_140003DB3
0x140003d38  xor     ebx, ebx
0x140003d3a  xor     esi, esi
0x140003d3c  cmp     [rcx], ebx
0x140003d3e  jbe     short loc_140003DB3
0x140003d40  mov     eax, [rdi+8]
0x140003d43  dec     eax
0x140003d45  cmp     esi, eax
0x140003d47  ja      short loc_140003D70
0x140003d49  mov     r8, [rdi+30h]
0x140003d4d  mov     r9d, 1; int
0x140003d53  mov     rdx, rbp; struct SC_HANDLE__ *
0x140003d56  mov     rcx, rdi; this
0x140003d59  mov     r8, [r8+rsi*8]; unsigned __int16 *
0x140003d5d  call    ?ResolveDependenciesRecursive@SERVICES_MANAGER@@AEAAJPEAUSC_HANDLE__@@PEAGH@Z; SERVICES_MANAGER::ResolveDependenciesRecursive(SC_HANDLE__ *,ushort *,int)
0x140003d62  mov     ebx, eax
0x140003d64  test    eax, eax
0x140003d66  js      short loc_140003DB3
0x140003d68  inc     esi
0x140003d6a  cmp     esi, [rdi]
0x140003d6c  jb      short loc_140003D40
0x140003d6e  jmp     short loc_140003DB3
0x140003d70  test    cs:g_dwDebugFlags, 0Fh
0x140003d77  mov     ebx, 80070585h
0x140003d7c  jz      short loc_140003DB3
0x140003d7e  mov     rcx, cs:g_pDebug
0x140003d85  lea     rax, aUnableToRetrie; "Unable to retrieve service name to list"...
0x140003d8c  mov     [rsp+58h+var_30], rax
0x140003d91  lea     r9, aServicesManage; "SERVICES_MANAGER::ResolveDependencies"
0x140003d98  mov     r8d, 0ACh
0x140003d9e  mov     [rsp+58h+var_38], 80070585h
0x140003da6  lea     rdx, aInetsrvIisSvcs; "inetsrv\\iis\\svcs\\restart\\wasrsta\\s"...
0x140003dad  call    cs:__imp_PuDbgPrintError
0x140003db3  mov     eax, ebx
0x140003db5  add     rsp, 38h
0x140003db9  pop     rdi
0x140003dba  pop     rsi
0x140003dbb  pop     rbp
0x140003dbc  pop     rbx
0x140003dbd  retn
```
