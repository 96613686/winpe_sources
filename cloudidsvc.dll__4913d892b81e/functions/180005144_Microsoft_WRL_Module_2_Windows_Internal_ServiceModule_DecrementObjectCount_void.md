# Microsoft::WRL::Module<2,Windows::Internal::ServiceModule>::DecrementObjectCount(void)

- ea: `0x180005144`
- end: `0x18000517f`
- name: `?DecrementObjectCount@?$Module@$01VServiceModule@Internal@Windows@@@WRL@Microsoft@@UEAAKXZ`
- size: `59`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005190`

## callees

- `0x180005144`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoReleaseServerProcess` at `0x180005151`
- `api-ms-win-core-com-l1-1-0!CoReleaseServerProcess` at `0x180005151`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Module<2,Windows::Internal::ServiceModule>::DecrementObjectCount(__int64 a1)
{
  ULONG v2; // ebx
  __int64 v3; // rcx

  v2 = CoReleaseServerProcess();
  if ( !v2 )
  {
    v3 = *(_QWORD *)(a1 + 8);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  }
  return v2;
}

```

## disassembly

```asm
0x180005144  mov     [rsp+arg_0], rbx
0x180005149  push    rdi
0x18000514a  sub     rsp, 20h
0x18000514e  mov     rdi, rcx
0x180005151  call    cs:__imp_CoReleaseServerProcess
0x180005157  mov     ebx, eax
0x180005159  test    eax, eax
0x18000515b  jnz     short loc_180005172
0x18000515d  mov     rcx, [rdi+8]
0x180005161  test    rcx, rcx
0x180005164  jz      short loc_180005172
0x180005166  mov     rdx, [rcx]
0x180005169  mov     rax, [rdx+8]
0x18000516d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005172  mov     eax, ebx
0x180005174  mov     rbx, [rsp+28h+arg_0]
0x180005179  add     rsp, 20h
0x18000517d  pop     rdi
0x18000517e  retn
```
