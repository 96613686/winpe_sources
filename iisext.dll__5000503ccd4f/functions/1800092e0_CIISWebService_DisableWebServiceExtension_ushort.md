# CIISWebService::DisableWebServiceExtension(ushort *)

- ea: `0x1800092e0`
- end: `0x180009355`
- name: `?DisableWebServiceExtension@CIISWebService@@UEAAJPEAG@Z`
- size: `117`
- prototype: `int(CIISWebService *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x1800092e0`
- `0x18000e330`
- `0x18000e380`
- `0x18000f1c0`
- `0x1800103ac`

## pseudocode

```c
__int64 __fastcall CIISWebService::DisableWebServiceExtension(struct IMSAdminBaseW **this, unsigned __int16 *a2)
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
    inited = CSecConLib::StatusWServEx((CSecConLib *)v7, 0, a2, v5);
  CSiteCreator::~CSiteCreator((CSiteCreator *)v7);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800092e0  mov     [rsp+arg_0], rbx
0x1800092e5  mov     [rsp+arg_8], rsi
0x1800092ea  push    rdi
0x1800092eb  sub     rsp, 70h
0x1800092ef  mov     rdi, rdx
0x1800092f2  mov     rbx, rcx
0x1800092f5  test    rdx, rdx
0x1800092f8  jnz     short loc_180009301
0x1800092fa  mov     eax, 80004003h
0x1800092ff  jmp     short loc_180009343
0x180009301  mov     rdx, [rcx+78h]; struct IMSAdminBaseW *
0x180009305  lea     rcx, [rsp+78h+var_58]; this
0x18000930a  call    ??0CSecConLib@@QEAA@PEAUIMSAdminBaseW@@@Z; CSecConLib::CSecConLib(IMSAdminBaseW *)
0x18000930f  mov     rsi, [rbx+48h]
0x180009313  lea     rcx, [rsp+78h+var_58]; this
0x180009318  call    ?InternalInitIfNecessary@CSecConLib@@AEAAJXZ; CSecConLib::InternalInitIfNecessary(void)
0x18000931d  mov     ebx, eax
0x18000931f  test    eax, eax
0x180009321  js      short loc_180009337
0x180009323  mov     r9, rsi; unsigned __int16 *
0x180009326  lea     rcx, [rsp+78h+var_58]; this
0x18000932b  mov     r8, rdi; unsigned __int16 *
0x18000932e  xor     edx, edx; bool
0x180009330  call    ?StatusWServEx@CSecConLib@@AEAAJ_NPEBG1@Z; CSecConLib::StatusWServEx(bool,ushort const *,ushort const *)
0x180009335  mov     ebx, eax
0x180009337  lea     rcx, [rsp+78h+var_58]; this
0x18000933c  call    ??1CSiteCreator@@UEAA@XZ; CSiteCreator::~CSiteCreator(void)
0x180009341  mov     eax, ebx
0x180009343  lea     r11, [rsp+78h+var_8]
0x180009348  mov     rbx, [r11+10h]
0x18000934c  mov     rsi, [r11+18h]
0x180009350  mov     rsp, r11
0x180009353  pop     rdi
0x180009354  retn
```
