# DusmMain::RegisterStopCallback(void)

- ea: `0x18001707c`
- end: `0x180017136`
- name: `?RegisterStopCallback@DusmMain@@AEAAXXZ`
- size: `186`
- prototype: `void __fastcall(DusmMain *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180016f44`

## callees

- `0x18001374c`
- `0x18001707c`
- `0x180017298`
- `0x1800172c8`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800170b5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800170b5`

## pseudocode

```c
void __fastcall DusmMain::RegisterStopCallback(DusmMain *this)
{
  DusmMain *v1; // rdi
  HANDLE EventW; // rax
  void *v3; // rdx
  const char *v4; // r9
  __int64 v5; // r8
  unsigned int v6; // eax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( qword_180068E48 && *(_QWORD *)(qword_180068E48 + 192) )
  {
    v1 = DusmMain::s_pInstance;
    EventW = CreateEventW(0, 0, 0, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)v1 + 48,
      EventW);
    v5 = *((_QWORD *)v1 + 6);
    if ( !v5 )
      wil::details::in1diag3::_Throw_NullAlloc(retaddr, v3, 0, v4);
    v6 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, __int64, void (__fastcall *)(void *, unsigned __int8)))(qword_180068E48 + 192))(
           (__int64)v1 + 40,
           L"DusmSvc",
           v5,
           DusmMain::ServiceStopCallback);
    if ( v6 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x52,
        (unsigned int)"onecoreuap\\net\\dusm\\svc\\svcmain.cpp",
        (const char *)v6,
        (unsigned int)v1);
  }
}

```

## disassembly

```asm
0x18001707c  mov     [rsp+arg_0], rbx
0x180017081  push    rdi
0x180017082  sub     rsp, 40h
0x180017086  mov     rax, cs:qword_180068E48
0x18001708d  test    rax, rax
0x180017090  jz      loc_18001712B
0x180017096  cmp     qword ptr [rax+0C0h], 0
0x18001709e  jz      loc_18001712B
0x1800170a4  mov     rdi, cs:?s_pInstance@DusmMain@@0PEAV1@EA; DusmMain * DusmMain::s_pInstance
0x1800170ab  xor     r9d, r9d; lpName
0x1800170ae  xor     r8d, r8d; bInitialState
0x1800170b1  xor     edx, edx; bManualReset
0x1800170b3  xor     ecx, ecx; lpEventAttributes
0x1800170b5  call    cs:__imp_CreateEventW
0x1800170bb  mov     rdx, rax
0x1800170be  lea     rcx, [rdi+30h]
0x1800170c2  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800170c7  mov     r8, [rdi+30h]; unsigned int
0x1800170cb  test    r8, r8
0x1800170ce  jnz     short loc_1800170DB
0x1800170d0  mov     rcx, [rsp+48h]; this
0x1800170d5  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800170db  mov     rax, cs:qword_180068E48
0x1800170e2  lea     rcx, [rdi+28h]
0x1800170e6  mov     [rsp+48h+var_20], 18h
0x1800170ee  lea     r9, ?ServiceStopCallback@DusmMain@@CAXPEAXE@Z; DusmMain::ServiceStopCallback(void *,uchar)
0x1800170f5  lea     rdx, ServiceName; "DusmSvc"
0x1800170fc  mov     qword ptr [rsp+48h+var_28], rdi; unsigned int
0x180017101  mov     rax, [rax+0C0h]
0x180017108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001710d  test    eax, eax
0x18001710f  jz      short loc_18001712B
0x180017111  mov     rcx, [rsp+48h]; this
0x180017116  lea     r8, aOnecoreuapNetD_8; "onecoreuap\\net\\dusm\\svc\\svcmain.cpp"
0x18001711d  mov     r9d, eax; char *
0x180017120  mov     edx, 52h ; 'R'; void *
0x180017125  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001712b  mov     rbx, [rsp+48h+arg_0]
0x180017130  add     rsp, 40h
0x180017134  pop     rdi
0x180017135  retn
```
