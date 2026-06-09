# wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x18000815c`
- end: `0x1800081fc`
- name: `??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `160`
- prototype: `__int64 __fastcall(__int64, _QWORD *, char, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008c58`

## callees

- `0x18000815c`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall wil::details::registry_watcher_state::registry_watcher_state(
        __int64 a1,
        _QWORD *a2,
        char a3,
        __int64 a4)
{
  if ( *(_QWORD *)(a4 + 112) )
  {
    *(_QWORD *)(a1 + 112) = a1 + 8;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a4 + 112) + 16LL))(*(_QWORD *)(a4 + 112));
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a4 + 112) + 24LL))(*(_QWORD *)(a4 + 112));
    *(_QWORD *)(a4 + 112) = 0;
  }
  else
  {
    *(_QWORD *)(a1 + 112) = 0;
  }
  *(_QWORD *)(a1 + 120) = *a2;
  *a2 = 0;
  *(_QWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_BYTE *)(a1 + 144) = a3;
  *(_DWORD *)(a1 + 148) = 1;
  *(_QWORD *)(a1 + 152) = 0;
  return a1;
}

```

## disassembly

```asm
0x18000815c  push    rbx
0x18000815e  push    rbp
0x18000815f  push    rsi
0x180008160  push    rdi
0x180008161  sub     rsp, 28h
0x180008165  cmp     qword ptr [r9+70h], 0
0x18000816a  mov     rsi, r9
0x18000816d  mov     bpl, r8b
0x180008170  mov     rdi, rdx
0x180008173  mov     rbx, rcx
0x180008176  jnz     short loc_180008182
0x180008178  mov     qword ptr [rcx+70h], 0
0x180008180  jmp     short loc_1800081B2
0x180008182  lea     rdx, [rcx+8]
0x180008186  mov     [rcx+70h], rdx
0x18000818a  mov     rcx, [r9+70h]
0x18000818e  mov     rax, [rcx]
0x180008191  mov     rax, [rax+10h]
0x180008195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000819a  mov     rcx, [rsi+70h]
0x18000819e  mov     rax, [rcx]
0x1800081a1  mov     rax, [rax+18h]
0x1800081a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081aa  mov     qword ptr [rsi+70h], 0
0x1800081b2  mov     rax, [rdi]
0x1800081b5  mov     [rbx+78h], rax
0x1800081b9  xor     eax, eax
0x1800081bb  mov     qword ptr [rdi], 0
0x1800081c2  mov     qword ptr [rbx+80h], 0
0x1800081cd  mov     qword ptr [rbx+88h], 0
0x1800081d8  mov     [rbx+90h], bpl
0x1800081df  mov     dword ptr [rbx+94h], 1
0x1800081e9  mov     [rbx+98h], rax
0x1800081f0  mov     rax, rbx
0x1800081f3  add     rsp, 28h
0x1800081f7  pop     rdi
0x1800081f8  pop     rsi
0x1800081f9  pop     rbp
0x1800081fa  pop     rbx
0x1800081fb  retn
```
