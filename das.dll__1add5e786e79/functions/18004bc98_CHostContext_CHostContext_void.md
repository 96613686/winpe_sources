# CHostContext::~CHostContext(void)

- ea: `0x18004bc98`
- end: `0x18004bd48`
- name: `??1CHostContext@@IEAA@XZ`
- size: `176`
- prototype: `void __fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180024294`

## callees

- `0x180007500`
- `0x18002b560`
- `0x18004bc98`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bd21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bd21`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004bd2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004bd2f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18004bcae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18004bcae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004bd12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004bd12`
- `RPCRT4!RpcBindingFree` at `0x18004bcbd`
- `RPCRT4!RpcBindingFree` at `0x18004bcbd`

## pseudocode

```c
void __fastcall CHostContext::~CHostContext(RPC_BINDING_HANDLE *Binding)
{
  struct _TP_WAIT *v2; // rcx
  RPC_STATUS v3; // eax
  int v4; // edx
  int v5; // r8d
  RPC_BINDING_HANDLE v6; // rcx
  RPC_BINDING_HANDLE v7; // rdi
  HANDLE ProcessHeap; // rax

  v2 = (struct _TP_WAIT *)Binding[6];
  if ( v2 )
    CloseThreadpoolWait(v2);
  if ( *Binding )
  {
    v3 = RpcBindingFree(Binding);
    if ( v3 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v4,
          v5,
          14,
          &WPP_061eca0472ca35df833eac72ad0e5963_Traceguids,
          v3);
    }
  }
  v6 = Binding[1];
  if ( v6 )
    CloseHandle(v6);
  v7 = Binding[10];
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
  std::vector<std::shared_ptr<ProviderContext>>::_Tidy(Binding + 7);
}

```

## disassembly

```asm
0x18004bc98  mov     [rsp+arg_0], rbx
0x18004bc9d  push    rdi
0x18004bc9e  sub     rsp, 30h
0x18004bca2  mov     rbx, rcx
0x18004bca5  mov     rcx, [rcx+30h]; pwa
0x18004bca9  test    rcx, rcx
0x18004bcac  jz      short loc_18004BCB4
0x18004bcae  call    cs:__imp_CloseThreadpoolWait
0x18004bcb4  cmp     qword ptr [rbx], 0
0x18004bcb8  jz      short loc_18004BD09
0x18004bcba  mov     rcx, rbx; Binding
0x18004bcbd  call    cs:__imp_RpcBindingFree
0x18004bcc3  test    eax, eax
0x18004bcc5  jz      short loc_18004BD09
0x18004bcc7  lea     rcx, WPP_RECORDER_INITIALIZED
0x18004bcce  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18004bcd5  jz      short loc_18004BD09
0x18004bcd7  test    eax, eax
0x18004bcd9  js      short loc_18004BCE3
0x18004bcdb  movzx   eax, ax
0x18004bcde  or      eax, 80010000h
0x18004bce3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bcea  mov     r9d, 0Eh; int
0x18004bcf0  mov     dword ptr [rsp+38h+var_10], eax; char
0x18004bcf4  lea     rax, WPP_061eca0472ca35df833eac72ad0e5963_Traceguids
0x18004bcfb  mov     [rsp+38h+MessageGuid], rax; MessageGuid
0x18004bd00  mov     rcx, [rcx+28h]; int
0x18004bd04  call    WPP_RECORDER_SF_D
0x18004bd09  mov     rcx, [rbx+8]; hObject
0x18004bd0d  test    rcx, rcx
0x18004bd10  jz      short loc_18004BD18
0x18004bd12  call    cs:__imp_CloseHandle
0x18004bd18  mov     rdi, [rbx+50h]
0x18004bd1c  test    rdi, rdi
0x18004bd1f  jz      short loc_18004BD35
0x18004bd21  call    cs:__imp_GetProcessHeap
0x18004bd27  mov     r8, rdi; lpMem
0x18004bd2a  xor     edx, edx; dwFlags
0x18004bd2c  mov     rcx, rax; hHeap
0x18004bd2f  call    cs:__imp_HeapFree
0x18004bd35  lea     rcx, [rbx+38h]
0x18004bd39  mov     rbx, [rsp+38h+arg_0]
0x18004bd3e  add     rsp, 30h
0x18004bd42  pop     rdi
0x18004bd43  jmp     ?_Tidy@?$vector@V?$shared_ptr@VProviderContext@@@std@@V?$allocator@V?$shared_ptr@VProviderContext@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<ProviderContext>>::_Tidy(void)
```
