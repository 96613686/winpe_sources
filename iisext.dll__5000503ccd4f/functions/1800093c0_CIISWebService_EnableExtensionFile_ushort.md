# CIISWebService::EnableExtensionFile(ushort *)

- ea: `0x1800093c0`
- end: `0x180009435`
- name: `?EnableExtensionFile@CIISWebService@@UEAAJPEAG@Z`
- size: `117`
- prototype: `__int64 __fastcall(struct IMSAdminBaseW **this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x1800093c0`
- `0x18000e330`
- `0x18000e380`
- `0x18000f1c0`
- `0x180010218`

## pseudocode

```c
__int64 __fastcall CIISWebService::EnableExtensionFile(struct IMSAdminBaseW **this, unsigned __int16 *a2)
{
  const unsigned __int16 *v5; // rsi
  int inited; // ebx
  _BYTE v7[80]; // [rsp+20h] [rbp-58h] BYREF

  if ( !a2 )
    return 2147500035LL;
  CSecConLib::CSecConLib((CSecConLib *)v7, this[15]);
  v5 = (const unsigned __int16 *)this[9];
  inited = CSecConLib::InternalInitIfNecessary((CSecConLib *)v7);
  if ( inited >= 0 )
    inited = CSecConLib::StatusExtensionFile((CSecConLib *)v7, 1, a2, v5);
  CSiteCreator::~CSiteCreator((CSiteCreator *)v7);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800093c0  mov     [rsp+arg_0], rbx
0x1800093c5  mov     [rsp+arg_8], rsi
0x1800093ca  push    rdi
0x1800093cb  sub     rsp, 70h
0x1800093cf  mov     rdi, rdx
0x1800093d2  mov     rbx, rcx
0x1800093d5  test    rdx, rdx
0x1800093d8  jnz     short loc_1800093E1
0x1800093da  mov     eax, 80004003h
0x1800093df  jmp     short loc_180009423
0x1800093e1  mov     rdx, [rcx+78h]; struct IMSAdminBaseW *
0x1800093e5  lea     rcx, [rsp+78h+var_58]; this
0x1800093ea  call    ??0CSecConLib@@QEAA@PEAUIMSAdminBaseW@@@Z; CSecConLib::CSecConLib(IMSAdminBaseW *)
0x1800093ef  mov     rsi, [rbx+48h]
0x1800093f3  lea     rcx, [rsp+78h+var_58]; this
0x1800093f8  call    ?InternalInitIfNecessary@CSecConLib@@AEAAJXZ; CSecConLib::InternalInitIfNecessary(void)
0x1800093fd  mov     ebx, eax
0x1800093ff  test    eax, eax
0x180009401  js      short loc_180009417
0x180009403  mov     r9, rsi; unsigned __int16 *
0x180009406  lea     rcx, [rsp+78h+var_58]; this
0x18000940b  mov     r8, rdi; unsigned __int16 *
0x18000940e  mov     dl, 1; bool
0x180009410  call    ?StatusExtensionFile@CSecConLib@@AEAAJ_NPEBG1@Z; CSecConLib::StatusExtensionFile(bool,ushort const *,ushort const *)
0x180009415  mov     ebx, eax
0x180009417  lea     rcx, [rsp+78h+var_58]; this
0x18000941c  call    ??1CSiteCreator@@UEAA@XZ; CSiteCreator::~CSiteCreator(void)
0x180009421  mov     eax, ebx
0x180009423  lea     r11, [rsp+78h+var_8]
0x180009428  mov     rbx, [r11+10h]
0x18000942c  mov     rsi, [r11+18h]
0x180009430  mov     rsp, r11
0x180009433  pop     rdi
0x180009434  retn
```
