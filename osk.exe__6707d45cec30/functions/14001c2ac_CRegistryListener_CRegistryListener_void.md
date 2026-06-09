# CRegistryListener::~CRegistryListener(void)

- ea: `0x14001c2ac`
- end: `0x14001c31b`
- name: `??1CRegistryListener@@QEAA@XZ`
- size: `111`
- prototype: `void __fastcall(CRegistryListener *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140007f54`
- `0x140025f2c`

## callees

- `0x14000519c`
- `0x140005c90`
- `0x140009524`
- `0x14001c2ac`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x14001c2de`
- `KERNEL32!WaitForSingleObject` at `0x14001c2de`
- `KERNEL32!SetEvent` at `0x14001c2ca`
- `KERNEL32!SetEvent` at `0x14001c2ca`

## pseudocode

```c
void __fastcall CRegistryListener::~CRegistryListener(CRegistryListener *this)
{
  void *v2; // rcx
  void *v3; // rcx

  *(_BYTE *)this = 1;
  v2 = (void *)*((_QWORD *)this + 4);
  if ( v2 )
    SetEvent(v2);
  v3 = (void *)*((_QWORD *)this + 5);
  if ( v3 )
    WaitForSingleObject(v3, 0x64u);
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 8) - 24LL));
  ATL::CHandle::~CHandle((CRegistryListener *)((char *)this + 40));
  ATL::CHandle::~CHandle((CRegistryListener *)((char *)this + 32));
  ATL::CRegKey::Close((CRegistryListener *)((char *)this + 8));
}

```

## disassembly

```asm
0x14001c2ac  mov     [rsp+arg_0], rbx
0x14001c2b1  mov     [rsp+arg_8], rsi
0x14001c2b6  push    rdi
0x14001c2b7  sub     rsp, 20h
0x14001c2bb  mov     rbx, rcx
0x14001c2be  mov     byte ptr [rcx], 1
0x14001c2c1  mov     rcx, [rcx+20h]; hEvent
0x14001c2c5  test    rcx, rcx
0x14001c2c8  jz      short loc_14001C2D0
0x14001c2ca  call    cs:__imp_SetEvent
0x14001c2d0  mov     rcx, [rbx+28h]; hHandle
0x14001c2d4  test    rcx, rcx
0x14001c2d7  jz      short loc_14001C2E4
0x14001c2d9  mov     edx, 64h ; 'd'; dwMilliseconds
0x14001c2de  call    cs:__imp_WaitForSingleObject
0x14001c2e4  mov     rcx, [rbx+40h]
0x14001c2e8  sub     rcx, 18h; this
0x14001c2ec  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001c2f1  lea     rcx, [rbx+28h]; this
0x14001c2f5  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x14001c2fa  lea     rcx, [rbx+20h]; this
0x14001c2fe  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x14001c303  lea     rcx, [rbx+8]; this
0x14001c307  mov     rbx, [rsp+28h+arg_0]
0x14001c30c  mov     rsi, [rsp+28h+arg_8]
0x14001c311  add     rsp, 20h
0x14001c315  pop     rdi
0x14001c316  jmp     ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
```
