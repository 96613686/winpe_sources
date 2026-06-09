# CGlassTerminal::SetGlassSessionIdInRegistry(ITSSession *)

- ea: `0x18000b254`
- end: `0x18000b3c9`
- name: `?SetGlassSessionIdInRegistry@CGlassTerminal@@AEAAJPEAUITSSession@@@Z`
- size: `373`
- prototype: `__int64 __fastcall(CGlassTerminal *__hidden this, struct ITSSession *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180075230`
- `0x180075250`

## callees

- `0x1800077a0`
- `0x18000b254`
- `0x18000bcc8`
- `0x18000c6b0`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b2bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b2bc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b35c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b35c`

## string_xrefs

- `0x18000b382`: `CGlassTerminal::SetGlassSessionIdInRegistry`
- `0x18000b2e5`: `OpenKey REG_CONTROL_TSERVER failed: 0x%x in %s`
- `0x18000b37b`: `WriteRegDWord REG_CONSOLE_SESSIONID failed: 0x%x in %s`

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
0x18000b254  mov     [rsp-18h+arg_0], rbx
0x18000b259  push    rbp
0x18000b25a  push    rsi
0x18000b25b  push    rdi
0x18000b25c  mov     rbp, rsp
0x18000b25f  sub     rsp, 60h
0x18000b263  mov     rdi, rdx
0x18000b266  mov     rsi, rcx
0x18000b269  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18000b270  mov     [rbp+var_30], rax
0x18000b274  mov     [rbp+var_28], 0
0x18000b27c  mov     [rbp+var_20], 0
0x18000b283  mov     [rbp+hKey], 0
0x18000b28b  or      eax, 0FFFFFFFFh
0x18000b28e  mov     [rbp+var_10], eax
0x18000b291  mov     [rbp+var_C], eax
0x18000b294  mov     [rbp+arg_18], 0
0x18000b29c  lea     rax, [rbp+hKey]
0x18000b2a0  mov     [rsp+60h+phkResult], rax; phkResult
0x18000b2a5  mov     r9d, 20006h; samDesired
0x18000b2ab  xor     r8d, r8d; ulOptions
0x18000b2ae  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x18000b2b5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b2bc  call    cs:__imp_RegOpenKeyExW
0x18000b2c3  nop     dword ptr [rax+rax+00h]
0x18000b2c8  mov     ebx, eax
0x18000b2ca  test    eax, eax
0x18000b2cc  jz      short loc_18000B2E1
0x18000b2ce  mov     [rbp+hKey], 0
0x18000b2d6  jle     short loc_18000B2E1
0x18000b2d8  movzx   ebx, ax
0x18000b2db  or      ebx, 80070000h
0x18000b2e1  test    ebx, ebx
0x18000b2e3  jns     short loc_18000B2F1
0x18000b2e5  lea     rdx, aOpenkeyRegCont; "OpenKey REG_CONTROL_TSERVER failed: 0x%"...
0x18000b2ec  jmp     loc_18000B382
0x18000b2f1  mov     ebx, 4
0x18000b2f6  test    rdi, rdi
0x18000b2f9  jz      short loc_18000B338
0x18000b2fb  mov     rax, [rdi]
0x18000b2fe  lea     rdx, [rbp+arg_18]
0x18000b302  mov     rcx, rdi
0x18000b305  mov     rax, [rax+68h]
0x18000b309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b30e  test    eax, eax
0x18000b310  js      short loc_18000B327
0x18000b312  mov     rcx, [rbp+arg_18]; struct ITerminal *
0x18000b316  call    ?IsLocalGlassTerminal@CGlassTerminal@@SAHPEAUITerminal@@@Z; CGlassTerminal::IsLocalGlassTerminal(ITerminal *)
0x18000b31b  test    eax, eax
0x18000b31d  jz      short loc_18000B338
0x18000b31f  mov     eax, [rsi+654h]
0x18000b325  jmp     short loc_18000B33B
0x18000b327  mov     r8d, eax
0x18000b32a  lea     rdx, aGetterminalFai_1; "getTerminal failed with 0x%08x"
0x18000b331  mov     ecx, ebx; int
0x18000b333  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b338  or      eax, 0FFFFFFFFh
0x18000b33b  mov     [rbp+Data], eax
0x18000b33e  mov     [rsp+60h+cbData], ebx; cbData
0x18000b342  lea     rax, [rbp+Data]
0x18000b346  mov     [rsp+60h+phkResult], rax; lpData
0x18000b34b  mov     r9d, ebx; dwType
0x18000b34e  xor     r8d, r8d; Reserved
0x18000b351  lea     rdx, ValueName; "GlassSessionId"
0x18000b358  mov     rcx, [rbp+hKey]; hKey
0x18000b35c  call    cs:__imp_RegSetValueExW
0x18000b363  nop     dword ptr [rax+rax+00h]
0x18000b368  mov     ebx, eax
0x18000b36a  test    eax, eax
0x18000b36c  jle     short loc_18000B377
0x18000b36e  movzx   ebx, ax
0x18000b371  or      ebx, 80070000h
0x18000b377  test    ebx, ebx
0x18000b379  jns     short loc_18000B397
0x18000b37b  lea     rdx, aWriteregdwordR; "WriteRegDWord REG_CONSOLE_SESSIONID fai"...
0x18000b382  lea     r9, aCglassterminal_2; "CGlassTerminal::SetGlassSessionIdInRegi"...
0x18000b389  mov     r8d, ebx
0x18000b38c  mov     ecx, 8; int
0x18000b391  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b396  nop
0x18000b397  mov     rcx, [rbp+arg_18]
0x18000b39b  test    rcx, rcx
0x18000b39e  jz      short loc_18000B3AD
0x18000b3a0  mov     rdx, [rcx]
0x18000b3a3  mov     rax, [rdx+10h]
0x18000b3a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3ac  nop
0x18000b3ad  lea     rcx, [rbp+var_30]; this
0x18000b3b1  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18000b3b6  mov     eax, ebx
0x18000b3b8  mov     rbx, [rsp+60h+arg_0]
0x18000b3c0  add     rsp, 60h
0x18000b3c4  pop     rdi
0x18000b3c5  pop     rsi
0x18000b3c6  pop     rbp
0x18000b3c7  retn
```
