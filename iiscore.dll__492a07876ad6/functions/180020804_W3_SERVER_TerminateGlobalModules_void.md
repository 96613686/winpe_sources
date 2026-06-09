# W3_SERVER::TerminateGlobalModules(void)

- ea: `0x180020804`
- end: `0x180020911`
- name: `?TerminateGlobalModules@W3_SERVER@@QEAAXXZ`
- size: `269`
- prototype: `void __fastcall(W3_SERVER *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800202bc`

## callees

- `0x18000ac10`
- `0x18001c268`
- `0x18001c5f0`
- `0x180020804`
- `0x18002fa44`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800208c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800208c9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180020887`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180020887`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002086c`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18002086c`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x180020824`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x180020824`
- `iisutil!?Clear@TREE_HASH_TABLE@@QEAAXXZ` at `0x180020837`
- `iisutil!?Clear@TREE_HASH_TABLE@@QEAAXXZ` at `0x18002084a`
- `iisutil!?Clear@TREE_HASH_TABLE@@QEAAXXZ` at `0x180020837`
- `iisutil!?Clear@TREE_HASH_TABLE@@QEAAXXZ` at `0x18002084a`
- `w3dt!UlAtqTerminate` at `0x1800208e0`
- `w3dt!UlAtqTerminate` at `0x1800208e0`
- `W3TP!ThreadPoolTerminate` at `0x1800208ec`
- `W3TP!ThreadPoolTerminate` at `0x1800208ec`

## pseudocode

```c
void __fastcall W3_SERVER::TerminateGlobalModules(W3_SERVER *this)
{
  CLKRHashTable *v2; // rdi
  unsigned int v3; // edx
  CDirMonitor *v4; // rcx
  void *v5; // rcx

  W3_SERVER::GlobalNotify((__int64)this, 4u, 0);
  CLKRHashTable::Clear((W3_SERVER *)((char *)this + 1312));
  TREE_HASH_TABLE::Clear((W3_SERVER *)((char *)this + 1384));
  TREE_HASH_TABLE::Clear((W3_SERVER *)((char *)this + 1424));
  v2 = (CLKRHashTable *)*((_QWORD *)this + 183);
  if ( v2 )
  {
    *((_DWORD *)v2 + 29) = 1;
    while ( CLKRHashTable::Size(v2) || *((_DWORD *)v2 + 28) != 1 )
      Sleep(0xC8u);
    v4 = (CDirMonitor *)*((_QWORD *)this + 183);
    if ( v4 )
      CDirMonitor::`scalar deleting destructor'(v4, v3);
    *((_QWORD *)this + 183) = 0;
  }
  MODULE_LIST::FreeModules((W3_SERVER *)((char *)this + 560));
  v5 = (void *)*((_QWORD *)this + 211);
  if ( v5 )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 211) = 0;
  }
  UlAtqTerminate();
  ThreadPoolTerminate();
  *((_DWORD *)this + 392) = 0;
  MODULE_DLL::Terminate();
}

```

## disassembly

```asm
0x180020804  mov     [rsp+arg_0], rbx
0x180020809  push    rdi
0x18002080a  sub     rsp, 20h
0x18002080e  xor     r8d, r8d
0x180020811  mov     rbx, rcx
0x180020814  lea     edx, [r8+4]
0x180020818  call    ?GlobalNotify@W3_SERVER@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; W3_SERVER::GlobalNotify(ulong,IHttpEventProvider *)
0x18002081d  lea     rcx, [rbx+520h]
0x180020824  call    cs:__imp_?Clear@CLKRHashTable@@QEAAXXZ; CLKRHashTable::Clear(void)
0x18002082b  nop     dword ptr [rax+rax+00h]
0x180020830  lea     rcx, [rbx+568h]
0x180020837  call    cs:__imp_?Clear@TREE_HASH_TABLE@@QEAAXXZ; TREE_HASH_TABLE::Clear(void)
0x18002083e  nop     dword ptr [rax+rax+00h]
0x180020843  lea     rcx, [rbx+590h]
0x18002084a  call    cs:__imp_?Clear@TREE_HASH_TABLE@@QEAAXXZ; TREE_HASH_TABLE::Clear(void)
0x180020851  nop     dword ptr [rax+rax+00h]
0x180020856  mov     rdi, [rbx+5B8h]
0x18002085d  test    rdi, rdi
0x180020860  jz      short loc_1800208B1
0x180020862  mov     dword ptr [rdi+74h], 1
0x180020869  mov     rcx, rdi
0x18002086c  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x180020873  nop     dword ptr [rax+rax+00h]
0x180020878  test    eax, eax
0x18002087a  jnz     short loc_180020882
0x18002087c  cmp     dword ptr [rdi+70h], 1
0x180020880  jz      short loc_180020895
0x180020882  mov     ecx, 0C8h; dwMilliseconds
0x180020887  call    cs:__imp_Sleep
0x18002088e  nop     dword ptr [rax+rax+00h]
0x180020893  jmp     short loc_180020869
0x180020895  mov     rcx, [rbx+5B8h]; this
0x18002089c  test    rcx, rcx
0x18002089f  jz      short loc_1800208A6
0x1800208a1  call    ??_GCDirMonitor@@QEAAPEAXI@Z; CDirMonitor::`scalar deleting destructor'(uint)
0x1800208a6  mov     qword ptr [rbx+5B8h], 0
0x1800208b1  lea     rcx, [rbx+230h]; this
0x1800208b8  call    ?FreeModules@MODULE_LIST@@QEAAXXZ; MODULE_LIST::FreeModules(void)
0x1800208bd  mov     rcx, [rbx+698h]; hObject
0x1800208c4  test    rcx, rcx
0x1800208c7  jz      short loc_1800208E0
0x1800208c9  call    cs:__imp_CloseHandle
0x1800208d0  nop     dword ptr [rax+rax+00h]
0x1800208d5  mov     qword ptr [rbx+698h], 0
0x1800208e0  call    cs:__imp_?UlAtqTerminate@@YAXXZ; UlAtqTerminate(void)
0x1800208e7  nop     dword ptr [rax+rax+00h]
0x1800208ec  call    cs:__imp_?ThreadPoolTerminate@@YAJXZ; ThreadPoolTerminate(void)
0x1800208f3  nop     dword ptr [rax+rax+00h]
0x1800208f8  mov     dword ptr [rbx+620h], 0
0x180020902  mov     rbx, [rsp+28h+arg_0]
0x180020907  add     rsp, 20h
0x18002090b  pop     rdi
0x18002090c  jmp     ?Terminate@MODULE_DLL@@SAXXZ; MODULE_DLL::Terminate(void)
```
