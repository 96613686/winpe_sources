# CManipulationManager::SetupMessageCallThreadInfo(IMessageSession *,long (*)(void *,void const *,int),CManipulationManager::MessageCallThreadInfo *)

- ea: `0x18015536c`
- end: `0x180155414`
- name: `?SetupMessageCallThreadInfo@CManipulationManager@@IEAAJPEAUIMessageSession@@P6AJPEAXPEBXH@ZPEAUMessageCallThreadInfo@1@@Z`
- size: `168`
- prototype: `__int64 __fastcall(CManipulationManager *__hidden this, struct IMessageSession *, int (*)(void *, const void *, int), struct CManipulationManager::MessageCallThreadInfo *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1801550a0`
- `0x1801eb5cc`

## callees

- `0x18002de54`
- `0x18015536c`
- `0x180204100`
- `0x1802b6010`

## import_xrefs

- `CoreMessaging!CoreUICallCreateEndpointHost` at `0x180155396`
- `CoreMessaging!CoreUICallCreateEndpointHost` at `0x1801553ba`
- `CoreMessaging!CoreUICallCreateEndpointHost` at `0x180155396`
- `CoreMessaging!CoreUICallCreateEndpointHost` at `0x1801553ba`

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
0x18015536c  push    rbx
0x18015536e  push    rbp
0x18015536f  push    rsi
0x180155370  push    rdi
0x180155371  push    r14
0x180155373  sub     rsp, 30h
0x180155377  mov     rbp, rcx
0x18015537a  mov     rdi, r9
0x18015537d  lea     rcx, [r9+8]
0x180155381  mov     r14, r8
0x180155384  mov     rsi, rdx
0x180155387  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18015538c  xor     r8d, r8d
0x18015538f  lea     rdx, [rdi+8]
0x180155393  mov     rcx, rsi
0x180155396  call    cs:__imp_CoreUICallCreateEndpointHost
0x18015539c  test    eax, eax
0x18015539e  js      short loc_1801553ED
0x1801553a0  lea     rcx, [rdi+10h]
0x1801553a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801553a9  mov     rcx, [rbp+10h]
0x1801553ad  lea     r8, [rdi+10h]
0x1801553b1  xor     edx, edx
0x1801553b3  mov     rcx, [rcx+1630h]
0x1801553ba  call    cs:__imp_CoreUICallCreateEndpointHost
0x1801553c0  test    eax, eax
0x1801553c2  js      short loc_1801553FA
0x1801553c4  mov     rax, [rsi]
0x1801553c7  mov     r9, rdi
0x1801553ca  mov     r8, rbp
0x1801553cd  mov     rdx, r14
0x1801553d0  mov     rcx, rsi
0x1801553d3  mov     rax, [rax+70h]
0x1801553d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801553dc  test    eax, eax
0x1801553de  js      short loc_180155407
0x1801553e0  xor     eax, eax
0x1801553e2  add     rsp, 30h
0x1801553e6  pop     r14
0x1801553e8  pop     rdi
0x1801553e9  pop     rsi
0x1801553ea  pop     rbp
0x1801553eb  pop     rbx
0x1801553ec  retn
0x1801553ed  mov     rdx, [rsp+58h]; void *
0x1801553f2  mov     ecx, eax; int
0x1801553f4  call    ModuleFailFastForHRESULT
0x1801553fa  mov     rdx, [rsp+58h]; void *
0x1801553ff  mov     ecx, eax; int
0x180155401  call    ModuleFailFastForHRESULT
0x180155407  mov     rdx, [rsp+58h]; void *
0x18015540c  mov     ecx, eax; int
0x18015540e  call    ModuleFailFastForHRESULT
```
