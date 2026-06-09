# CFirewallCplCore::GetBusinessObject(_GUID const &,_GUID const &,void * *)

- ea: `0x180008f80`
- end: `0x180009038`
- name: `?GetBusinessObject@CFirewallCplCore@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `184`
- prototype: `__int64 __fastcall(CFirewallCplCore *__hidden this, IID *rclsid, IID *riid, LPVOID *ppv)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010cc4`

## callees

- `0x180008e24`
- `0x180008f80`
- `0x18000994c`
- `0x180014430`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008fc7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008fc7`

## pseudocode

```c
__int64 __fastcall CFirewallCplCore::GetBusinessObject(CFirewallCplCore *this, IID *rclsid, IID *riid, LPVOID *ppv)
{
  int v8; // ebx

  if ( !ppv )
    return (unsigned int)-2147024809;
  *ppv = 0;
  if ( (int)CheckUserPermissions() >= 0 )
    return (unsigned int)CoCreateInstance(rclsid, 0, 1u, riid, ppv);
  v8 = CFirewallCplCore::Elevate(this);
  if ( v8 >= 0 )
    return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, IID *, IID *, LPVOID *))(**((_QWORD **)this + 9) + 40LL))(
                           *((_QWORD *)this + 9),
                           rclsid,
                           riid,
                           ppv);
  if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_d2517ed6f73e376c3e61f10cf36dc817_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180008f80  push    rbx
0x180008f82  push    rbp
0x180008f83  push    rsi
0x180008f84  push    rdi
0x180008f85  push    r14
0x180008f87  sub     rsp, 30h
0x180008f8b  mov     rdi, r9
0x180008f8e  mov     rbp, r8
0x180008f91  mov     r14, rdx
0x180008f94  mov     rsi, rcx
0x180008f97  test    r9, r9
0x180008f9a  jnz     short loc_180008FA6
0x180008f9c  mov     ebx, 80070057h
0x180008fa1  jmp     loc_18000902B
0x180008fa6  mov     qword ptr [r9], 0
0x180008fad  call    ?CheckUserPermissions@@YAJXZ; CheckUserPermissions(void)
0x180008fb2  test    eax, eax
0x180008fb4  js      short loc_180008FCF
0x180008fb6  xor     edx, edx; pUnkOuter
0x180008fb8  mov     [rsp+58h+ppv], rdi; ppv
0x180008fbd  mov     r9, rbp; riid
0x180008fc0  mov     rcx, r14; rclsid
0x180008fc3  lea     r8d, [rdx+1]; dwClsContext
0x180008fc7  call    cs:__imp_CoCreateInstance
0x180008fcd  jmp     short loc_180009029
0x180008fcf  mov     rcx, rsi; this
0x180008fd2  call    ?Elevate@CFirewallCplCore@@QEAAJXZ; CFirewallCplCore::Elevate(void)
0x180008fd7  mov     ebx, eax
0x180008fd9  test    eax, eax
0x180008fdb  jns     short loc_180009010
0x180008fdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180008fe4  lea     rax, WPP_GLOBAL_Control
0x180008feb  cmp     rcx, rax
0x180008fee  jz      short loc_18000902B
0x180008ff0  test    byte ptr [rcx+1Ch], 1
0x180008ff4  jz      short loc_18000902B
0x180008ff6  mov     rcx, [rcx+10h]
0x180008ffa  lea     r8, WPP_d2517ed6f73e376c3e61f10cf36dc817_Traceguids
0x180009001  mov     edx, 0Bh
0x180009006  mov     r9d, ebx
0x180009009  call    WPP_SF_d
0x18000900e  jmp     short loc_18000902B
0x180009010  mov     rcx, [rsi+48h]
0x180009014  mov     r9, rdi
0x180009017  mov     r8, rbp
0x18000901a  mov     rdx, r14
0x18000901d  mov     rax, [rcx]
0x180009020  mov     rax, [rax+28h]
0x180009024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009029  mov     ebx, eax
0x18000902b  mov     eax, ebx
0x18000902d  add     rsp, 30h
0x180009031  pop     r14
0x180009033  pop     rdi
0x180009034  pop     rsi
0x180009035  pop     rbp
0x180009036  pop     rbx
0x180009037  retn
```
