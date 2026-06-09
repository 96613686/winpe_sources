# PubSebiUpdateLevelEventRpc(void *,uchar)

- ea: `0x1801727a8`
- end: `0x18017289b`
- name: `?PubSebiUpdateLevelEventRpc@@YAJPEAXE@Z`
- size: `243`
- prototype: `__int64 __fastcall(struct _SEB_RPC_PUBLISH_DATA *, unsigned __int8)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801726d4`
- `0x1801ecb14`

## callees

- `0x1801727a8`
- `0x1801729f0`
- `0x180172b64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801727fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801727fb`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1801727f5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1801727f5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180172841`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180172841`
- `RPCRT4!NdrClientCall3` at `0x180172831`
- `RPCRT4!NdrClientCall3` at `0x180172831`

## pseudocode

```c
__int64 __fastcall PubSebiUpdateLevelEventRpc(struct _SEB_RPC_PUBLISH_DATA *a1, unsigned __int8 a2)
{
  int v2; // esi
  ContextTable *v4; // rcx
  int RpcBindingHandle; // ebx
  void *v6; // rbx
  int v7; // eax
  bool v8; // zf
  int v10; // eax
  int v11; // ecx
  int v12; // eax
  void *v13; // [rsp+40h] [rbp+8h] BYREF

  v2 = a2;
  v13 = 0;
  if ( !a1 )
  {
    LOWORD(RpcBindingHandle) = 87;
    return (unsigned __int16)RpcBindingHandle | 0x80070000;
  }
  RpcBindingHandle = PubSebiGetRpcBindingHandle(&v13);
  if ( !RpcBindingHandle )
  {
    v6 = ContextTable::Find(v4, a1);
    if ( !v6 )
    {
      LOWORD(RpcBindingHandle) = 6;
      return (unsigned __int16)RpcBindingHandle | 0x80070000;
    }
    RtlAcquireSRWLockExclusive(a1);
    *((_DWORD *)a1 + 2) = GetCurrentThreadId();
    v7 = *((_DWORD *)a1 + 3);
    if ( (_BYTE)v2 )
    {
      v8 = v7 == 0;
    }
    else
    {
      if ( !v7 )
      {
        RpcBindingHandle = 50;
LABEL_9:
        RtlReleaseSRWLockExclusive(a1);
        *((_DWORD *)a1 + 2) = 0;
        goto LABEL_10;
      }
      v8 = v7 == 1;
    }
    if ( !v8
      || (RpcBindingHandle = (unsigned int)NdrClientCall3(
                                             (MIDL_STUBLESS_PROXY_INFO *)&CSystemEventBrokerPublisher_ProxyInfo,
                                             1u,
                                             0,
                                             v13,
                                             v2,
                                             v6).Pointer) == 0 )
    {
      v10 = *((_DWORD *)a1 + 3);
      v11 = v10 - 1;
      v12 = v10 + 1;
      if ( !(_BYTE)v2 )
        v12 = v11;
      RpcBindingHandle = 0;
      *((_DWORD *)a1 + 3) = v12;
    }
    goto LABEL_9;
  }
LABEL_10:
  if ( RpcBindingHandle > 0 )
    return (unsigned __int16)RpcBindingHandle | 0x80070000;
  return (unsigned int)RpcBindingHandle;
}

```

## disassembly

```asm
0x1801727a8  mov     rax, rsp
0x1801727ab  mov     [rax+10h], rbx
0x1801727af  mov     [rax+18h], rsi
0x1801727b3  push    rdi
0x1801727b4  sub     rsp, 30h
0x1801727b8  movzx   esi, dl
0x1801727bb  mov     rdi, rcx
0x1801727be  mov     qword ptr [rax+8], 0
0x1801727c6  test    rcx, rcx
0x1801727c9  jz      loc_18017286D
0x1801727cf  lea     rcx, [rax+8]; void **
0x1801727d3  call    ?PubSebiGetRpcBindingHandle@@YAJPEAPEAX@Z; PubSebiGetRpcBindingHandle(void * *)
0x1801727d8  mov     ebx, eax
0x1801727da  test    eax, eax
0x1801727dc  jnz     short loc_18017284E
0x1801727de  mov     rdx, rdi; struct _SEB_RPC_PUBLISH_DATA *
0x1801727e1  call    ?Find@ContextTable@@QEAAPEAXPEAU_SEB_RPC_PUBLISH_DATA@@@Z; ContextTable::Find(_SEB_RPC_PUBLISH_DATA *)
0x1801727e6  mov     rbx, rax
0x1801727e9  test    rax, rax
0x1801727ec  jz      loc_180172874
0x1801727f2  mov     rcx, rdi
0x1801727f5  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1801727fb  call    cs:__imp_GetCurrentThreadId
0x180172801  mov     [rdi+8], eax
0x180172804  mov     edx, 1; nProcNum
0x180172809  mov     eax, [rdi+0Ch]
0x18017280c  test    sil, sil
0x18017280f  jnz     short loc_180172882
0x180172811  test    eax, eax
0x180172813  jz      short loc_18017287B
0x180172815  cmp     eax, edx
0x180172817  jnz     short loc_180172886
0x180172819  mov     r9, [rsp+38h+arg_0]
0x18017281e  lea     rcx, ?CSystemEventBrokerPublisher_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180172825  mov     [rsp+38h+var_10], rbx
0x18017282a  xor     r8d, r8d; pReturnValue
0x18017282d  mov     [rsp+38h+var_18], esi
0x180172831  call    cs:__imp_NdrClientCall3
0x180172837  mov     rbx, rax
0x18017283a  test    eax, eax
0x18017283c  jz      short loc_180172886
0x18017283e  mov     rcx, rdi
0x180172841  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180172847  mov     dword ptr [rdi+8], 0
0x18017284e  test    ebx, ebx
0x180172850  jle     short loc_18017285B
0x180172852  movzx   ebx, bx
0x180172855  or      ebx, 80070000h
0x18017285b  mov     rsi, [rsp+38h+arg_10]
0x180172860  mov     eax, ebx
0x180172862  mov     rbx, [rsp+38h+arg_8]
0x180172867  add     rsp, 30h
0x18017286b  pop     rdi
0x18017286c  retn
0x18017286d  mov     ebx, 57h ; 'W'
0x180172872  jmp     short loc_180172852
0x180172874  mov     ebx, 6
0x180172879  jmp     short loc_180172852
0x18017287b  mov     ebx, 32h ; '2'
0x180172880  jmp     short loc_18017283E
0x180172882  test    eax, eax
0x180172884  jmp     short loc_180172817
0x180172886  mov     eax, [rdi+0Ch]
0x180172889  lea     ecx, [rax-1]
0x18017288c  inc     eax
0x18017288e  test    sil, sil
0x180172891  cmovz   eax, ecx
0x180172894  xor     ebx, ebx
0x180172896  mov     [rdi+0Ch], eax
0x180172899  jmp     short loc_18017283E
```
