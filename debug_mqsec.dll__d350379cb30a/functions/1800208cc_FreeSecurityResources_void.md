# FreeSecurityResources(void)

- ea: `0x1800208cc`
- end: `0x1800209a2`
- name: `?FreeSecurityResources@@YAXXZ`
- size: `214`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800207c4`

## callees

- `0x1800208cc`

## import_xrefs

- `msvcrt!free` at `0x18002096d`
- `msvcrt!free` at `0x18002098b`
- `msvcrt!free` at `0x18002096d`
- `msvcrt!free` at `0x18002098b`
- `ADVAPI32!FreeSid` at `0x1800208dc`
- `ADVAPI32!FreeSid` at `0x1800208f9`
- `ADVAPI32!FreeSid` at `0x180020916`
- `ADVAPI32!FreeSid` at `0x180020933`
- `ADVAPI32!FreeSid` at `0x180020950`
- `ADVAPI32!FreeSid` at `0x1800208dc`
- `ADVAPI32!FreeSid` at `0x1800208f9`
- `ADVAPI32!FreeSid` at `0x180020916`
- `ADVAPI32!FreeSid` at `0x180020933`
- `ADVAPI32!FreeSid` at `0x180020950`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void FreeSecurityResources(void)
{
  if ( g_pAnonymSid )
  {
    FreeSid(g_pAnonymSid);
    g_pAnonymSid = 0;
  }
  if ( g_pWorldSid )
  {
    FreeSid(g_pWorldSid);
    g_pWorldSid = 0;
  }
  if ( g_pSystemSid )
  {
    FreeSid(g_pSystemSid);
    g_pSystemSid = 0;
  }
  if ( g_pNetworkServiceSid )
  {
    FreeSid(g_pNetworkServiceSid);
    g_pNetworkServiceSid = 0;
  }
  if ( g_pAdminSid )
  {
    FreeSid(g_pAdminSid);
    g_pAdminSid = 0;
  }
  if ( g_pProcessSid )
  {
    free(g_pProcessSid);
    g_pProcessSid = 0;
  }
  if ( g_pLocalMachineSid )
  {
    free(g_pLocalMachineSid);
    g_pLocalMachineSid = 0;
  }
}

```

## disassembly

```asm
0x1800208cc  sub     rsp, 28h
0x1800208d0  mov     rcx, cs:?g_pAnonymSid@@3PEAXEA; pSid
0x1800208d7  test    rcx, rcx
0x1800208da  jz      short loc_1800208ED
0x1800208dc  call    cs:__imp_FreeSid
0x1800208e2  mov     cs:?g_pAnonymSid@@3PEAXEA, 0; void * g_pAnonymSid
0x1800208ed  mov     rcx, cs:?g_pWorldSid@@3PEAXEA; pSid
0x1800208f4  test    rcx, rcx
0x1800208f7  jz      short loc_18002090A
0x1800208f9  call    cs:__imp_FreeSid
0x1800208ff  mov     cs:?g_pWorldSid@@3PEAXEA, 0; void * g_pWorldSid
0x18002090a  mov     rcx, cs:?g_pSystemSid@@3PEAXEA; pSid
0x180020911  test    rcx, rcx
0x180020914  jz      short loc_180020927
0x180020916  call    cs:__imp_FreeSid
0x18002091c  mov     cs:?g_pSystemSid@@3PEAXEA, 0; void * g_pSystemSid
0x180020927  mov     rcx, cs:?g_pNetworkServiceSid@@3PEAXEA; pSid
0x18002092e  test    rcx, rcx
0x180020931  jz      short loc_180020944
0x180020933  call    cs:__imp_FreeSid
0x180020939  mov     cs:?g_pNetworkServiceSid@@3PEAXEA, 0; void * g_pNetworkServiceSid
0x180020944  mov     rcx, cs:?g_pAdminSid@@3PEAXEA; pSid
0x18002094b  test    rcx, rcx
0x18002094e  jz      short loc_180020961
0x180020950  call    cs:__imp_FreeSid
0x180020956  mov     cs:?g_pAdminSid@@3PEAXEA, 0; void * g_pAdminSid
0x180020961  mov     rcx, cs:?g_pProcessSid@@3PEAXEA; Block
0x180020968  test    rcx, rcx
0x18002096b  jz      short loc_18002097F
0x18002096d  call    cs:__imp_free
0x180020973  nop
0x180020974  mov     cs:?g_pProcessSid@@3PEAXEA, 0; void * g_pProcessSid
0x18002097f  mov     rcx, cs:?g_pLocalMachineSid@@3PEAXEA; Block
0x180020986  test    rcx, rcx
0x180020989  jz      short loc_18002099D
0x18002098b  call    cs:__imp_free
0x180020991  nop
0x180020992  mov     cs:?g_pLocalMachineSid@@3PEAXEA, 0; void * g_pLocalMachineSid
0x18002099d  add     rsp, 28h
0x1800209a1  retn
```
