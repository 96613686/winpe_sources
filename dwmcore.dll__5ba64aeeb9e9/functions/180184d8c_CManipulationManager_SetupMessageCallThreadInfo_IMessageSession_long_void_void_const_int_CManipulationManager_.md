# CManipulationManager::SetupMessageCallThreadInfo(IMessageSession *,long (*)(void *,void const *,int),CManipulationManager::MessageCallThreadInfo *)

- ea: `0x180184d8c`
- end: `0x180184e34`
- name: `?SetupMessageCallThreadInfo@CManipulationManager@@IEAAJPEAUIMessageSession@@P6AJPEAXPEBXH@ZPEAUMessageCallThreadInfo@1@@Z`
- size: `168`
- prototype: `__int64 __fastcall(CManipulationManager *__hidden this, struct IMessageSession *, int (*)(void *, const void *, int), struct CManipulationManager::MessageCallThreadInfo *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180184ac0`
- `0x1801eb1ac`

## callees

- `0x180049470`
- `0x180184d8c`
- `0x180204120`
- `0x1802b6010`

## import_xrefs

- `CoreMessaging!CoreUICallCreateEndpointHost` at `0x180184db6`
- `CoreMessaging!CoreUICallCreateEndpointHost` at `0x180184dda`
- `CoreMessaging!CoreUICallCreateEndpointHost` at `0x180184db6`
- `CoreMessaging!CoreUICallCreateEndpointHost` at `0x180184dda`

## pseudocode

```c
__int64 __fastcall CManipulationManager::SetupMessageCallThreadInfo(
        CManipulationManager *this,
        struct IMessageSession *a2,
        int (*a3)(void *, const void *, int),
        struct CManipulationManager::MessageCallThreadInfo *a4)
{
  int EndpointHost; // eax
  int v9; // eax
  int v10; // eax
  void *retaddr; // [rsp+58h] [rbp+0h]

  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)a4 + 8);
  EndpointHost = CoreUICallCreateEndpointHost(a2, (char *)a4 + 8, 0);
  if ( EndpointHost < 0 )
    ModuleFailFastForHRESULT(EndpointHost, retaddr);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)a4 + 16);
  v9 = CoreUICallCreateEndpointHost(*(_QWORD *)(*((_QWORD *)this + 2) + 5680LL), 0, (char *)a4 + 16);
  if ( v9 < 0 )
    ModuleFailFastForHRESULT(v9, retaddr);
  v10 = (*(__int64 (__fastcall **)(struct IMessageSession *, int (*)(void *, const void *, int), CManipulationManager *, struct CManipulationManager::MessageCallThreadInfo *))(*(_QWORD *)a2 + 112LL))(
          a2,
          a3,
          this,
          a4);
  if ( v10 < 0 )
    ModuleFailFastForHRESULT(v10, retaddr);
  return 0;
}

```

## disassembly

```asm
0x180184d8c  push    rbx
0x180184d8e  push    rbp
0x180184d8f  push    rsi
0x180184d90  push    rdi
0x180184d91  push    r14
0x180184d93  sub     rsp, 30h
0x180184d97  mov     rbp, rcx
0x180184d9a  mov     rdi, r9
0x180184d9d  lea     rcx, [r9+8]
0x180184da1  mov     r14, r8
0x180184da4  mov     rsi, rdx
0x180184da7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180184dac  xor     r8d, r8d
0x180184daf  lea     rdx, [rdi+8]
0x180184db3  mov     rcx, rsi
0x180184db6  call    cs:__imp_CoreUICallCreateEndpointHost
0x180184dbc  test    eax, eax
0x180184dbe  js      short loc_180184E0D
0x180184dc0  lea     rcx, [rdi+10h]
0x180184dc4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180184dc9  mov     rcx, [rbp+10h]
0x180184dcd  lea     r8, [rdi+10h]
0x180184dd1  xor     edx, edx
0x180184dd3  mov     rcx, [rcx+1630h]
0x180184dda  call    cs:__imp_CoreUICallCreateEndpointHost
0x180184de0  test    eax, eax
0x180184de2  js      short loc_180184E1A
0x180184de4  mov     rax, [rsi]
0x180184de7  mov     r9, rdi
0x180184dea  mov     r8, rbp
0x180184ded  mov     rdx, r14
0x180184df0  mov     rcx, rsi
0x180184df3  mov     rax, [rax+70h]
0x180184df7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184dfc  test    eax, eax
0x180184dfe  js      short loc_180184E27
0x180184e00  xor     eax, eax
0x180184e02  add     rsp, 30h
0x180184e06  pop     r14
0x180184e08  pop     rdi
0x180184e09  pop     rsi
0x180184e0a  pop     rbp
0x180184e0b  pop     rbx
0x180184e0c  retn
0x180184e0d  mov     rdx, [rsp+58h]; void *
0x180184e12  mov     ecx, eax; int
0x180184e14  call    ModuleFailFastForHRESULT
0x180184e1a  mov     rdx, [rsp+58h]; void *
0x180184e1f  mov     ecx, eax; int
0x180184e21  call    ModuleFailFastForHRESULT
0x180184e27  mov     rdx, [rsp+58h]; void *
0x180184e2c  mov     ecx, eax; int
0x180184e2e  call    ModuleFailFastForHRESULT
```
