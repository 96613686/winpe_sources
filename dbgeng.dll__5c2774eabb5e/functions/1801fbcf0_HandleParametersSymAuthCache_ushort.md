# HandleParametersSymAuthCache(ushort *)

- ea: `0x1801fbcf0`
- end: `0x1801fbe3e`
- name: `?HandleParametersSymAuthCache@@YAXPEAG@Z`
- size: `334`
- prototype: `void __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1801f8e40`

## callees

- `0x1800727b8`
- `0x1800b7104`
- `0x1801eb5cc`
- `0x1801fb6f4`
- `0x1801fbcf0`
- `0x180281aac`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801fbd35`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801fbd5b`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801fbd84`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801fbda3`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801fbd35`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801fbd5b`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801fbd84`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1801fbda3`
- `dbghelp!SymGetSymbolsNegativeAuthCache` at `0x1801fbdc9`
- `dbghelp!SymGetSymbolsNegativeAuthCache` at `0x1801fbdc9`

## string_xrefs

- `0x1801fbd2b`: `update`
- `0x1801fbdf8`: `Failed to set enabled parameter of the symbols negative authentication cache.\n`
- `0x1801fbe1f`: `Invalid parameters command. Valid is <update> <enabled> <true|false>.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall HandleParametersSymAuthCache(unsigned __int16 *a1)
{
  const wchar_t *NextWord; // rax
  const wchar_t *v3; // rax
  const wchar_t *v4; // rbx
  unsigned int v5; // ebx
  int SymbolsNegativeAuthCache; // [rsp+48h] [rbp+10h] BYREF
  int *v7; // [rsp+50h] [rbp+18h] BYREF

  SymbolsNegativeAuthCache = 0;
  v7 = &SymbolsNegativeAuthCache;
  if ( !PeekCmdChar() || (NextWord = GetNextWord(a1), _wcsicmp(NextWord, L"update")) )
  {
    lambda_9b0c418526e467fe411fae08bc038ffd_::operator()(&v7);
    return;
  }
  v3 = GetNextWord(a1);
  if ( _wcsicmp(v3, L"enabled") )
  {
    dprintf(L"Invalid parameters command. Valid is <update> <enabled> <true|false>.\n");
    return;
  }
  v4 = GetNextWord(a1);
  if ( _wcsicmp(v4, L"true") )
  {
    if ( _wcsicmp(v4, L"false") )
    {
      dprintf(L"Invalid value for enabled parameter. Valid values are: true, false.\n");
      return;
    }
    v5 = 0;
  }
  else
  {
    v5 = 1;
  }
  v7 = 0;
  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::MarkerService>::InternalRelease(&v7);
  SymbolsNegativeAuthCache = SymGetSymbolsNegativeAuthCache(&v7);
  if ( SymbolsNegativeAuthCache >= 0 )
  {
    SymbolsNegativeAuthCache = (*(__int64 (__fastcall **)(int *, _QWORD))(*(_QWORD *)v7 + 104LL))(v7, v5);
    if ( SymbolsNegativeAuthCache < 0 )
      dprintf(L"Failed to set enabled parameter of the symbols negative authentication cache.\n");
  }
  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::MarkerService>::InternalRelease(&v7);
}

```

## disassembly

```asm
0x1801fbcf0  mov     rax, rsp
0x1801fbcf3  push    rdi
0x1801fbcf4  sub     rsp, 30h
0x1801fbcf8  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x1801fbd00  mov     [rax+8], rbx
0x1801fbd04  mov     rbx, rcx
0x1801fbd07  xor     edi, edi
0x1801fbd09  mov     [rax+10h], edi
0x1801fbd0c  lea     rax, [rax+10h]
0x1801fbd10  mov     [rsp+38h+arg_10], rax
0x1801fbd15  call    ?PeekCmdChar@@YAGXZ; PeekCmdChar(void)
0x1801fbd1a  test    ax, ax
0x1801fbd1d  jz      loc_1801FBE28
0x1801fbd23  mov     rcx, rbx; unsigned __int16 *
0x1801fbd26  call    ?GetNextWord@@YAPEAGPEAG@Z; GetNextWord(ushort *)
0x1801fbd2b  lea     rdx, aUpdate; "update"
0x1801fbd32  mov     rcx, rax; String1
0x1801fbd35  call    cs:__imp__wcsicmp
0x1801fbd3c  nop     dword ptr [rax+rax+00h]
0x1801fbd41  test    eax, eax
0x1801fbd43  jnz     loc_1801FBE28
0x1801fbd49  mov     rcx, rbx; unsigned __int16 *
0x1801fbd4c  call    ?GetNextWord@@YAPEAGPEAG@Z; GetNextWord(ushort *)
0x1801fbd51  lea     rdx, aEnabled_0; "enabled"
0x1801fbd58  mov     rcx, rax; String1
0x1801fbd5b  call    cs:__imp__wcsicmp
0x1801fbd62  nop     dword ptr [rax+rax+00h]
0x1801fbd67  test    eax, eax
0x1801fbd69  jnz     loc_1801FBE1F
0x1801fbd6f  mov     rcx, rbx; unsigned __int16 *
0x1801fbd72  call    ?GetNextWord@@YAPEAGPEAG@Z; GetNextWord(ushort *)
0x1801fbd77  mov     rbx, rax
0x1801fbd7a  lea     rdx, aTrue; "true"
0x1801fbd81  mov     rcx, rax; String1
0x1801fbd84  call    cs:__imp__wcsicmp
0x1801fbd8b  nop     dword ptr [rax+rax+00h]
0x1801fbd90  test    eax, eax
0x1801fbd92  jnz     short loc_1801FBD99
0x1801fbd94  lea     ebx, [rdi+1]
0x1801fbd97  jmp     short loc_1801FBDB5
0x1801fbd99  lea     rdx, aFalse_0; "false"
0x1801fbda0  mov     rcx, rbx; String1
0x1801fbda3  call    cs:__imp__wcsicmp
0x1801fbdaa  nop     dword ptr [rax+rax+00h]
0x1801fbdaf  test    eax, eax
0x1801fbdb1  jnz     short loc_1801FBE11
0x1801fbdb3  mov     ebx, edi
0x1801fbdb5  mov     [rsp+38h+arg_10], rdi
0x1801fbdba  lea     rcx, [rsp+38h+arg_10]
0x1801fbdbf  call    ?InternalRelease@?$ComPtr@VMarkerService@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::MarkerService>::InternalRelease(void)
0x1801fbdc4  lea     rcx, [rsp+38h+arg_10]
0x1801fbdc9  call    cs:__imp_SymGetSymbolsNegativeAuthCache
0x1801fbdd0  nop     dword ptr [rax+rax+00h]
0x1801fbdd5  mov     [rsp+38h+arg_8], eax
0x1801fbdd9  test    eax, eax
0x1801fbddb  js      short loc_1801FBE05
0x1801fbddd  mov     rcx, [rsp+38h+arg_10]
0x1801fbde2  mov     rax, [rcx]
0x1801fbde5  mov     edx, ebx
0x1801fbde7  mov     rax, [rax+68h]
0x1801fbdeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fbdf0  mov     [rsp+38h+arg_8], eax
0x1801fbdf4  test    eax, eax
0x1801fbdf6  jns     short loc_1801FBE05
0x1801fbdf8  lea     rcx, aFailedToSetEna; "Failed to set enabled parameter of the "...
0x1801fbdff  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1801fbe04  nop
0x1801fbe05  lea     rcx, [rsp+38h+arg_10]
0x1801fbe0a  call    ?InternalRelease@?$ComPtr@VMarkerService@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::MarkerService>::InternalRelease(void)
0x1801fbe0f  jmp     short loc_1801FBE32
0x1801fbe11  lea     rcx, aInvalidValueFo_0; "Invalid value for enabled parameter. Va"...
0x1801fbe18  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1801fbe1d  jmp     short loc_1801FBE32
0x1801fbe1f  lea     rcx, aInvalidParamet; "Invalid parameters command. Valid is <u"...
0x1801fbe26  jmp     short loc_1801FBE18
0x1801fbe28  lea     rcx, [rsp+38h+arg_10]
0x1801fbe2d  call    _lambda_9b0c418526e467fe411fae08bc038ffd___operator__
0x1801fbe32  mov     rbx, [rsp+38h+arg_0]
0x1801fbe37  add     rsp, 30h
0x1801fbe3b  pop     rdi
0x1801fbe3c  retn
```
