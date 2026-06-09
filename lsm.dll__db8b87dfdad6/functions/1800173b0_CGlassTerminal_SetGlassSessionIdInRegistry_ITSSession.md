# CGlassTerminal::SetGlassSessionIdInRegistry(ITSSession *)

- ea: `0x1800173b0`
- end: `0x180017518`
- name: `?SetGlassSessionIdInRegistry@CGlassTerminal@@AEAAJPEAUITSSession@@@Z`
- size: `360`
- prototype: `__int64 __fastcall(CGlassTerminal *__hidden this, struct ITSSession *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180071100`
- `0x180071120`

## callees

- `0x1800074c0`
- `0x1800173b0`
- `0x180017da0`
- `0x1800186a0`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017418`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017418`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800174b2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800174b2`

## string_xrefs

- `0x1800174d2`: `CGlassTerminal::SetGlassSessionIdInRegistry`
- `0x18001743b`: `OpenKey REG_CONTROL_TSERVER failed: 0x%x in %s`
- `0x1800174cb`: `WriteRegDWord REG_CONSOLE_SESSIONID failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CGlassTerminal::SetGlassSessionIdInRegistry(CGlassTerminal *this, struct ITSSession *a2)
{
  LSTATUS v4; // eax
  signed int v5; // ebx
  int v6; // eax
  int v7; // eax
  LSTATUS v8; // eax
  _QWORD v10[2]; // [rsp+30h] [rbp-30h] BYREF
  int v11; // [rsp+40h] [rbp-20h]
  HKEY hKey; // [rsp+48h] [rbp-18h] BYREF
  int v13; // [rsp+50h] [rbp-10h]
  int v14; // [rsp+54h] [rbp-Ch]
  int Data; // [rsp+90h] [rbp+30h] BYREF
  struct ITerminal *v16; // [rsp+98h] [rbp+38h] BYREF

  v10[0] = &CRegistry::`vftable';
  v10[1] = 0;
  v11 = 0;
  hKey = 0;
  v13 = -1;
  v14 = -1;
  v16 = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20006u, &hKey);
  v5 = v4;
  if ( v4 )
  {
    hKey = 0;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
  }
  if ( v5 < 0 )
  {
    _DbgPrintMessage(
      8,
      "OpenKey REG_CONTROL_TSERVER failed: 0x%x in %s",
      (unsigned int)v5,
      "CGlassTerminal::SetGlassSessionIdInRegistry");
    goto LABEL_16;
  }
  if ( !a2 )
    goto LABEL_11;
  v6 = (*(__int64 (__fastcall **)(struct ITSSession *, struct ITerminal **))(*(_QWORD *)a2 + 104LL))(a2, &v16);
  if ( v6 < 0 )
  {
    _DbgPrintMessage(4, "getTerminal failed with 0x%08x", v6);
    goto LABEL_11;
  }
  if ( !(unsigned int)CGlassTerminal::IsLocalGlassTerminal(v16) )
  {
LABEL_11:
    v7 = -1;
    goto LABEL_12;
  }
  v7 = *((_DWORD *)this + 405);
LABEL_12:
  Data = v7;
  v8 = RegSetValueExW(hKey, L"GlassSessionId", 0, 4u, (const BYTE *)&Data, 4u);
  v5 = v8;
  if ( v8 > 0 )
    v5 = (unsigned __int16)v8 | 0x80070000;
  if ( v5 < 0 )
    _DbgPrintMessage(
      8,
      "WriteRegDWord REG_CONSOLE_SESSIONID failed: 0x%x in %s",
      (unsigned int)v5,
      "CGlassTerminal::SetGlassSessionIdInRegistry");
LABEL_16:
  if ( v16 )
    (*(void (__fastcall **)(struct ITerminal *))(*(_QWORD *)v16 + 16LL))(v16);
  CRegistry::~CRegistry((CRegistry *)v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800173b0  mov     [rsp-18h+arg_0], rbx
0x1800173b5  push    rbp
0x1800173b6  push    rsi
0x1800173b7  push    rdi
0x1800173b8  mov     rbp, rsp
0x1800173bb  sub     rsp, 60h
0x1800173bf  mov     rdi, rdx
0x1800173c2  mov     rsi, rcx
0x1800173c5  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x1800173cc  mov     [rbp+var_30], rax
0x1800173d0  mov     [rbp+var_28], 0
0x1800173d8  mov     [rbp+var_20], 0
0x1800173df  mov     [rbp+hKey], 0
0x1800173e7  or      eax, 0FFFFFFFFh
0x1800173ea  mov     [rbp+var_10], eax
0x1800173ed  mov     [rbp+var_C], eax
0x1800173f0  mov     [rbp+arg_18], 0
0x1800173f8  lea     rax, [rbp+hKey]
0x1800173fc  mov     [rsp+60h+phkResult], rax; phkResult
0x180017401  mov     r9d, 20006h; samDesired
0x180017407  xor     r8d, r8d; ulOptions
0x18001740a  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x180017411  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017418  call    cs:__imp_RegOpenKeyExW
0x18001741e  mov     ebx, eax
0x180017420  test    eax, eax
0x180017422  jz      short loc_180017437
0x180017424  mov     [rbp+hKey], 0
0x18001742c  jle     short loc_180017437
0x18001742e  movzx   ebx, ax
0x180017431  or      ebx, 80070000h
0x180017437  test    ebx, ebx
0x180017439  jns     short loc_180017447
0x18001743b  lea     rdx, aOpenkeyRegCont; "OpenKey REG_CONTROL_TSERVER failed: 0x%"...
0x180017442  jmp     loc_1800174D2
0x180017447  mov     ebx, 4
0x18001744c  test    rdi, rdi
0x18001744f  jz      short loc_18001748E
0x180017451  mov     rax, [rdi]
0x180017454  lea     rdx, [rbp+arg_18]
0x180017458  mov     rcx, rdi
0x18001745b  mov     rax, [rax+68h]
0x18001745f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017464  test    eax, eax
0x180017466  js      short loc_18001747D
0x180017468  mov     rcx, [rbp+arg_18]; struct ITerminal *
0x18001746c  call    ?IsLocalGlassTerminal@CGlassTerminal@@SAHPEAUITerminal@@@Z; CGlassTerminal::IsLocalGlassTerminal(ITerminal *)
0x180017471  test    eax, eax
0x180017473  jz      short loc_18001748E
0x180017475  mov     eax, [rsi+654h]
0x18001747b  jmp     short loc_180017491
0x18001747d  mov     r8d, eax
0x180017480  lea     rdx, aGetterminalFai_1; "getTerminal failed with 0x%08x"
0x180017487  mov     ecx, ebx; int
0x180017489  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001748e  or      eax, 0FFFFFFFFh
0x180017491  mov     [rbp+Data], eax
0x180017494  mov     [rsp+60h+cbData], ebx; cbData
0x180017498  lea     rax, [rbp+Data]
0x18001749c  mov     [rsp+60h+phkResult], rax; lpData
0x1800174a1  mov     r9d, ebx; dwType
0x1800174a4  xor     r8d, r8d; Reserved
0x1800174a7  lea     rdx, aGlasssessionid; "GlassSessionId"
0x1800174ae  mov     rcx, [rbp+hKey]; hKey
0x1800174b2  call    cs:__imp_RegSetValueExW
0x1800174b8  mov     ebx, eax
0x1800174ba  test    eax, eax
0x1800174bc  jle     short loc_1800174C7
0x1800174be  movzx   ebx, ax
0x1800174c1  or      ebx, 80070000h
0x1800174c7  test    ebx, ebx
0x1800174c9  jns     short loc_1800174E7
0x1800174cb  lea     rdx, aWriteregdwordR; "WriteRegDWord REG_CONSOLE_SESSIONID fai"...
0x1800174d2  lea     r9, aCglassterminal_2; "CGlassTerminal::SetGlassSessionIdInRegi"...
0x1800174d9  mov     r8d, ebx
0x1800174dc  mov     ecx, 8; int
0x1800174e1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800174e6  nop
0x1800174e7  mov     rcx, [rbp+arg_18]
0x1800174eb  test    rcx, rcx
0x1800174ee  jz      short loc_1800174FD
0x1800174f0  mov     rdx, [rcx]
0x1800174f3  mov     rax, [rdx+10h]
0x1800174f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174fc  nop
0x1800174fd  lea     rcx, [rbp+var_30]; this
0x180017501  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180017506  mov     eax, ebx
0x180017508  mov     rbx, [rsp+60h+arg_0]
0x180017510  add     rsp, 60h
0x180017514  pop     rdi
0x180017515  pop     rsi
0x180017516  pop     rbp
0x180017517  retn
```
