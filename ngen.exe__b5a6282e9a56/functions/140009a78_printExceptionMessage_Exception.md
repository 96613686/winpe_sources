# printExceptionMessage(Exception *)

- ea: `0x140009a78`
- end: `0x140009c06`
- name: `?printExceptionMessage@@YAXPEAVException@@@Z`
- size: `398`
- prototype: `void __fastcall(struct Exception *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140015309`

## callees

- `0x140006a38`
- `0x140006e3c`
- `0x140006e90`
- `0x140009a78`
- `0x14000b010`
- `0x140013200`
- `0x140013f30`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140009bbc`
- `KERNEL32!HeapFree` at `0x140009bbc`
- `KERNEL32!GetProcessHeap` at `0x140009ba7`
- `KERNEL32!GetProcessHeap` at `0x140009ba7`

## string_xrefs

- `0x140009b6c`: `The most likely cause of this error is that NGen was invoked on a non-manifest module of a multi-module assembly.  The correct usage is to invoke NGen on the manifest module, which will cause native code generation to happen on the non-manifest modules as well.\n`
- `0x140009b7a`: `Administrator permissions are needed to use the selected options.  Use an administrator command prompt to complete these tasks.\n`

## pseudocode

```c
void __fastcall printExceptionMessage(struct Exception *a1)
{
  char v2; // di
  int v3; // eax
  bool v4; // r8
  void *v5; // rsi
  HANDLE ProcessHeap; // rax
  _DWORD *v7; // rbx
  BOOL v8; // edi
  __int64 v9; // rdx
  __int64 v10; // r9
  unsigned int CurrentExceptionCode; // eax
  int v12; // edx
  bool v13; // [rsp+20h] [rbp-288h] BYREF
  int v14; // [rsp+28h] [rbp-280h] BYREF
  _DWORD *v15; // [rsp+30h] [rbp-278h]
  int *v16; // [rsp+38h] [rbp-270h]
  BOOL v17; // [rsp+40h] [rbp-268h]
  _QWORD v18[3]; // [rsp+48h] [rbp-260h] BYREF
  _DWORD *v19; // [rsp+60h] [rbp-248h] BYREF
  _DWORD v20[2]; // [rsp+70h] [rbp-238h] BYREF
  int v21; // [rsp+78h] [rbp-230h]
  LPVOID lpMem; // [rsp+80h] [rbp-228h]
  __int16 v23; // [rsp+88h] [rbp-220h] BYREF

  v2 = 0;
  v14 = 0;
  v15 = 0;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    if ( __eh34_try(0, 1) )
    {
      __eh34_scope_strut(1);
      v16 = &v14;
      v21 = 0;
      lpMem = &v23;
      v20[1] = 512;
      v20[0] = 2;
      v23 = 0;
      (*(void (__fastcall **)(struct Exception *, _DWORD *))(*(_QWORD *)a1 + 24LL))(a1, v20);
      SString::ConvertToUnicode((SString *)v20);
      MachineWideLogger::LogF((MachineWideLogger *)&g_MachineWideLogger, L"%s\n", lpMem);
      SString::ConvertToUnicode((SString *)v20);
      Output((const unsigned __int16 *)lpMem);
      Output("\n");
      v3 = (*(__int64 (__fastcall **)(struct Exception *))(*(_QWORD *)a1 + 16LL))(a1);
      if ( v3 == -2147024891 )
      {
        Output(
          "Administrator permissions are needed to use the selected options.  Use an administrator command prompt to comp"
          "lete these tasks.\n");
      }
      else if ( v3 == -2146234344 )
      {
        Output(
          "The most likely cause of this error is that NGen was invoked on a non-manifest module of a multi-module assemb"
          "ly.  The correct usage is to invoke NGen on the manifest module, which will cause native code generation to ha"
          "ppen on the non-manifest modules as well.\n");
      }
      if ( (v21 & 8) != 0 )
      {
        v5 = lpMem;
        if ( lpMem )
        {
          ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
          if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
          {
            ProcessHeap = GetProcessHeap();
            `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
          }
          HeapFree(ProcessHeap, 0, v5);
        }
      }
    }
    if ( __eh34_catch(1) )
    {
      if ( __eh34_catch_type(1, &Exception * `RTTI Type Descriptor', (Exception **)&v19) )
      {
        Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)&v14);
        v15 = v19;
        throw;
      }
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_ellipsis(0) )
    {
      v18[1] = 0;
      v18[0] = &DelegatingException::`vftable';
      v18[2] = -1;
      v7 = v15;
      v16 = v15;
      v8 = v15 != 0;
      v17 = v8;
      ((void (__fastcall *)(Exception::HandlerState *, int, bool))Exception::HandlerState::SetupCatch)(
        (Exception::HandlerState *)&v14,
        1796,
        v4);
      Output("Unknown error occured\n");
      if ( !(unsigned int)CLRConfig::GetConfigValue(
                            (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_legacyCorruptedStateExceptionsPolicy,
                            v9,
                            &v13,
                            v10) )
      {
        CurrentExceptionCode = GetCurrentExceptionCode();
        if ( (unsigned int)IsProcessCorruptedStateException(CurrentExceptionCode, v12) )
        {
          v17 = 0;
          throw;
        }
      }
      if ( v8 )
      {
        if ( v7 && !(*(unsigned int (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 80LL))(v7) )
          (**(void (__fastcall ***)(_DWORD *, __int64))v7)(v7, 5);
        v17 = 0;
      }
      DelegatingException::~DelegatingException((DelegatingException *)v18);
      v2 = v14;
      __eh34_try_continuation(0, &loc_140009BC5);
    }
  }
  if ( (v2 & 2) != 0 )
  {
    if ( g_fpHandleStackOverflowAfterCatch )
      g_fpHandleStackOverflowAfterCatch();
  }
}

```

## disassembly

```asm
0x140009a78  mov     r11, rsp
0x140009a7b  mov     [r11+10h], rbx
0x140009a7f  mov     [r11+18h], rsi
0x140009a83  push    rdi
0x140009a84  sub     rsp, 2A0h
0x140009a8b  mov     rax, cs:__security_cookie
0x140009a92  xor     rax, rsp
0x140009a95  mov     [rsp+2A8h+var_18], rax
0x140009a9d  mov     rsi, rcx
0x140009aa0  xor     ebx, ebx
0x140009aa2  mov     edi, ebx
0x140009aa4  mov     [rsp+2A8h+var_280], ebx
0x140009aa8  mov     [rsp+2A8h+var_278], rbx
0x140009aad  lea     rax, [rsp+2A8h+var_280]
0x140009ab2  mov     [rsp+2A8h+var_270], rax
0x140009ab7  mov     [rsp+2A8h+var_238], ebx
0x140009abb  mov     [rsp+2A8h+var_234], ebx
0x140009abf  mov     [rsp+2A8h+var_230], ebx
0x140009ac3  mov     [r11-228h], rbx
0x140009aca  lea     rax, [r11-220h]
0x140009ad1  mov     [r11-228h], rax
0x140009ad8  mov     [rsp+2A8h+var_234], 200h
0x140009ae0  mov     [rsp+2A8h+var_238], 2
0x140009ae8  mov     rax, [r11-228h]
0x140009aef  mov     [rax], bx
0x140009af2  mov     rax, [rcx]
0x140009af5  lea     rdx, [rsp+2A8h+var_238]
0x140009afa  mov     rax, [rax+18h]
0x140009afe  call    cs:__guard_dispatch_icall_fptr
0x140009b04  lea     rcx, [rsp+2A8h+var_238]; this
0x140009b09  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140009b0e  mov     r8, [rsp+2A8h+lpMem]
0x140009b16  lea     rdx, aS_0; "%s\n"
0x140009b1d  lea     rcx, ?g_MachineWideLogger@@3VMachineWideLogger@@A; this
0x140009b24  call    ?LogF@MachineWideLogger@@QEAAXPEBGZZ; MachineWideLogger::LogF(ushort const *,...)
0x140009b29  lea     rcx, [rsp+2A8h+var_238]; this
0x140009b2e  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140009b33  mov     rcx, [rsp+2A8h+lpMem]; unsigned __int16 *
0x140009b3b  call    ?Output@@YAXPEBG@Z; Output(ushort const *)
0x140009b40  lea     rcx, asc_140017D14; "\n"
0x140009b47  call    ?Output@@YAXPEBD@Z; Output(char const *)
0x140009b4c  mov     rax, [rsi]
0x140009b4f  mov     rcx, rsi
0x140009b52  mov     rax, [rax+10h]
0x140009b56  call    cs:__guard_dispatch_icall_fptr
0x140009b5c  cmp     eax, 80070005h
0x140009b61  jz      short loc_140009B7A
0x140009b63  cmp     eax, 80131018h
0x140009b68  jz      short loc_140009B6C
0x140009b6a  jmp     short loc_140009B78
0x140009b6c  lea     rcx, aTheMostLikelyC; "The most likely cause of this error is "...
0x140009b73  call    ?Output@@YAXPEBD@Z; Output(char const *)
0x140009b78  jmp     short loc_140009B87
0x140009b7a  lea     rcx, aAdministratorP; "Administrator permissions are needed to"...
0x140009b81  call    ?Output@@YAXPEBD@Z; Output(char const *)
0x140009b86  nop
0x140009b87  test    byte ptr [rsp+2A8h+var_230], 8
0x140009b8c  jz      short loc_140009BC3
0x140009b8e  mov     rsi, [rsp+2A8h+lpMem]
0x140009b96  test    rsi, rsi
0x140009b99  jz      short loc_140009BC3
0x140009b9b  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x140009ba2  test    rax, rax
0x140009ba5  jnz     short loc_140009BB4
0x140009ba7  call    cs:__imp_GetProcessHeap
0x140009bad  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x140009bb4  mov     r8, rsi; lpMem
0x140009bb7  xor     edx, edx; dwFlags
0x140009bb9  mov     rcx, rax; hHeap
0x140009bbc  call    cs:__imp_HeapFree
0x140009bc2  nop
0x140009bc3  jmp     short loc_140009BC9
0x140009bc5  mov     edi, [rsp+2A8h+var_280]
0x140009bc9  test    dil, 2
0x140009bcd  jz      short loc_140009BE1
0x140009bcf  mov     rax, cs:?g_fpHandleStackOverflowAfterCatch@@3P6AXXZEA; void (*g_fpHandleStackOverflowAfterCatch)(void)
0x140009bd6  test    rax, rax
0x140009bd9  jz      short loc_140009BE1
0x140009bdb  call    cs:__guard_dispatch_icall_fptr
0x140009be1  mov     rcx, [rsp+2A8h+var_18]
0x140009be9  xor     rcx, rsp; StackCookie
0x140009bec  call    __security_check_cookie
0x140009bf1  lea     r11, [rsp+2A8h+var_8]
0x140009bf9  mov     rbx, [r11+18h]
0x140009bfd  mov     rsi, [r11+20h]
0x140009c01  mov     rsp, r11
0x140009c04  pop     rdi
0x140009c05  retn
```
