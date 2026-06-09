# DwmIsCompositionEnabled

- ea: `0x180002110`
- end: `0x1800021a4`
- name: `DwmIsCompositionEnabled`
- size: `148`
- prototype: `HRESULT __stdcall(BOOL *pfEnabled)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002110`
- `0x1800021b0`
- `0x180003370`
- `0x180017010`

## import_xrefs

- `ntdll!SbSelectProcedure` at `0x180002146`
- `ntdll!SbSelectProcedure` at `0x180002146`
- `USER32!IsThreadDesktopComposited` at `0x18000216b`
- `USER32!IsThreadDesktopComposited` at `0x18000216b`

## pseudocode

```c
HRESULT __stdcall DwmIsCompositionEnabled(BOOL *pfEnabled)
{
  void (__fastcall *v2)(int *); // rax
  int v4; // [rsp+30h] [rbp+8h] BYREF

  if ( pfEnabled )
  {
    v2 = (void (__fastcall *)(int *))qword_18001F860;
    v4 = 0;
    if ( qword_18001F860
      || (v2 = (void (__fastcall *)(int *))SbSelectProcedure(2880154539LL, 0, "kLsE", 0),
          (qword_18001F860 = (__int64)v2) != 0) )
    {
      v2(&v4);
    }
    if ( !(unsigned int)IsHighContrastMode() || v4 )
      *pfEnabled = IsThreadDesktopComposited();
    else
      *pfEnabled = 0;
    return 0;
  }
  else
  {
    DoStackCaptureDirect(-2147024809, 0x26u);
    return -2147024809;
  }
}

```

## disassembly

```asm
0x180002110  push    rbx
0x180002112  sub     rsp, 20h
0x180002116  mov     rbx, rcx
0x180002119  test    rcx, rcx
0x18000211c  jz      short loc_180002180
0x18000211e  mov     rax, cs:qword_18001F860
0x180002125  mov     [rsp+28h+arg_8], rdi
0x18000212a  xor     edi, edi
0x18000212c  mov     [rsp+28h+arg_0], edi
0x180002130  test    rax, rax
0x180002133  jnz     short loc_180002158
0x180002135  xor     r9d, r9d
0x180002138  lea     r8, g_SbModuleTable_DwmApiNamespace; "kLsE"
0x18000213f  xor     edx, edx
0x180002141  mov     ecx, 0ABABABABh
0x180002146  call    cs:__imp_SbSelectProcedure
0x18000214c  mov     cs:qword_18001F860, rax
0x180002153  test    rax, rax
0x180002156  jz      short loc_180002162
0x180002158  lea     rcx, [rsp+28h+arg_0]
0x18000215d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002162  call    IsHighContrastMode
0x180002167  test    eax, eax
0x180002169  jnz     short loc_18000219A
0x18000216b  call    cs:__imp_IsThreadDesktopComposited
0x180002171  mov     [rbx], eax
0x180002173  mov     eax, edi
0x180002175  mov     rdi, [rsp+28h+arg_8]
0x18000217a  add     rsp, 20h
0x18000217e  pop     rbx
0x18000217f  retn
0x180002180  mov     edx, 26h ; '&'; unsigned int
0x180002185  mov     ecx, 80070057h; int
0x18000218a  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x18000218f  mov     eax, 80070057h
0x180002194  add     rsp, 20h
0x180002198  pop     rbx
0x180002199  retn
0x18000219a  cmp     [rsp+28h+arg_0], edi
0x18000219e  jnz     short loc_18000216B
0x1800021a0  mov     [rbx], edi
0x1800021a2  jmp     short loc_180002173
```
