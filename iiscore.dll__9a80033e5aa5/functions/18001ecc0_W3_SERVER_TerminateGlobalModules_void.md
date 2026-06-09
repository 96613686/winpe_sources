# W3_SERVER::TerminateGlobalModules(void)

- ea: `0x18001ecc0`
- end: `0x18001ed9d`
- name: `?TerminateGlobalModules@W3_SERVER@@QEAAXXZ`
- size: `221`
- prototype: `void __fastcall(W3_SERVER *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001e7f0`

## callees

- `0x18000a340`
- `0x18001ab68`
- `0x18001aed0`
- `0x18001ecc0`
- `0x18002d07c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ed67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ed67`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001ed2b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001ed2b`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18001ed16`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18001ed16`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18001ece0`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18001ece0`
- `iisutil!?Clear@TREE_HASH_TABLE@@QEAAXXZ` at `0x18001eced`
- `iisutil!?Clear@TREE_HASH_TABLE@@QEAAXXZ` at `0x18001ecfa`
- `iisutil!?Clear@TREE_HASH_TABLE@@QEAAXXZ` at `0x18001eced`
- `iisutil!?Clear@TREE_HASH_TABLE@@QEAAXXZ` at `0x18001ecfa`
- `w3dt!UlAtqTerminate` at `0x18001ed78`
- `w3dt!UlAtqTerminate` at `0x18001ed78`
- `W3TP!ThreadPoolTerminate` at `0x18001ed7e`
- `W3TP!ThreadPoolTerminate` at `0x18001ed7e`

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
0x18001ecc0  mov     [rsp+arg_0], rbx
0x18001ecc5  push    rdi
0x18001ecc6  sub     rsp, 20h
0x18001ecca  xor     r8d, r8d
0x18001eccd  mov     rbx, rcx
0x18001ecd0  lea     edx, [r8+4]
0x18001ecd4  call    ?GlobalNotify@W3_SERVER@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; W3_SERVER::GlobalNotify(ulong,IHttpEventProvider *)
0x18001ecd9  lea     rcx, [rbx+520h]
0x18001ece0  call    cs:__imp_?Clear@CLKRHashTable@@QEAAXXZ; CLKRHashTable::Clear(void)
0x18001ece6  lea     rcx, [rbx+568h]
0x18001eced  call    cs:__imp_?Clear@TREE_HASH_TABLE@@QEAAXXZ; TREE_HASH_TABLE::Clear(void)
0x18001ecf3  lea     rcx, [rbx+590h]
0x18001ecfa  call    cs:__imp_?Clear@TREE_HASH_TABLE@@QEAAXXZ; TREE_HASH_TABLE::Clear(void)
0x18001ed00  mov     rdi, [rbx+5B8h]
0x18001ed07  test    rdi, rdi
0x18001ed0a  jz      short loc_18001ED4F
0x18001ed0c  mov     dword ptr [rdi+74h], 1
0x18001ed13  mov     rcx, rdi
0x18001ed16  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x18001ed1c  test    eax, eax
0x18001ed1e  jnz     short loc_18001ED26
0x18001ed20  cmp     dword ptr [rdi+70h], 1
0x18001ed24  jz      short loc_18001ED33
0x18001ed26  mov     ecx, 0C8h; dwMilliseconds
0x18001ed2b  call    cs:__imp_Sleep
0x18001ed31  jmp     short loc_18001ED13
0x18001ed33  mov     rcx, [rbx+5B8h]; this
0x18001ed3a  test    rcx, rcx
0x18001ed3d  jz      short loc_18001ED44
0x18001ed3f  call    ??_GCDirMonitor@@QEAAPEAXI@Z; CDirMonitor::`scalar deleting destructor'(uint)
0x18001ed44  mov     qword ptr [rbx+5B8h], 0
0x18001ed4f  lea     rcx, [rbx+230h]; this
0x18001ed56  call    ?FreeModules@MODULE_LIST@@QEAAXXZ; MODULE_LIST::FreeModules(void)
0x18001ed5b  mov     rcx, [rbx+698h]; hObject
0x18001ed62  test    rcx, rcx
0x18001ed65  jz      short loc_18001ED78
0x18001ed67  call    cs:__imp_CloseHandle
0x18001ed6d  mov     qword ptr [rbx+698h], 0
0x18001ed78  call    cs:__imp_?UlAtqTerminate@@YAXXZ; UlAtqTerminate(void)
0x18001ed7e  call    cs:__imp_?ThreadPoolTerminate@@YAJXZ; ThreadPoolTerminate(void)
0x18001ed84  mov     dword ptr [rbx+620h], 0
0x18001ed8e  mov     rbx, [rsp+28h+arg_0]
0x18001ed93  add     rsp, 20h
0x18001ed97  pop     rdi
0x18001ed98  jmp     ?Terminate@MODULE_DLL@@SAXXZ; MODULE_DLL::Terminate(void)
```
