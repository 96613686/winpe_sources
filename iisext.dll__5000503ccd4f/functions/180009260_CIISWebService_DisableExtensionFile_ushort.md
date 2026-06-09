# CIISWebService::DisableExtensionFile(ushort *)

- ea: `0x180009260`
- end: `0x1800092d5`
- name: `?DisableExtensionFile@CIISWebService@@UEAAJPEAG@Z`
- size: `117`
- prototype: `int(CIISWebService *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x180009260`
- `0x18000e330`
- `0x18000e380`
- `0x18000f1c0`
- `0x180010218`

## pseudocode

```c
__int64 __fastcall CIISWebService::DisableExtensionFile(struct IMSAdminBaseW **this, unsigned __int16 *a2)
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
    inited = CSecConLib::StatusExtensionFile((CSecConLib *)v7, 0, a2, v5);
  CSiteCreator::~CSiteCreator((CSiteCreator *)v7);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180009260  mov     [rsp+arg_0], rbx
0x180009265  mov     [rsp+arg_8], rsi
0x18000926a  push    rdi
0x18000926b  sub     rsp, 70h
0x18000926f  mov     rdi, rdx
0x180009272  mov     rbx, rcx
0x180009275  test    rdx, rdx
0x180009278  jnz     short loc_180009281
0x18000927a  mov     eax, 80004003h
0x18000927f  jmp     short loc_1800092C3
0x180009281  mov     rdx, [rcx+78h]; struct IMSAdminBaseW *
0x180009285  lea     rcx, [rsp+78h+var_58]; this
0x18000928a  call    ??0CSecConLib@@QEAA@PEAUIMSAdminBaseW@@@Z; CSecConLib::CSecConLib(IMSAdminBaseW *)
0x18000928f  mov     rsi, [rbx+48h]
0x180009293  lea     rcx, [rsp+78h+var_58]; this
0x180009298  call    ?InternalInitIfNecessary@CSecConLib@@AEAAJXZ; CSecConLib::InternalInitIfNecessary(void)
0x18000929d  mov     ebx, eax
0x18000929f  test    eax, eax
0x1800092a1  js      short loc_1800092B7
0x1800092a3  mov     r9, rsi; unsigned __int16 *
0x1800092a6  lea     rcx, [rsp+78h+var_58]; this
0x1800092ab  mov     r8, rdi; unsigned __int16 *
0x1800092ae  xor     edx, edx; bool
0x1800092b0  call    ?StatusExtensionFile@CSecConLib@@AEAAJ_NPEBG1@Z; CSecConLib::StatusExtensionFile(bool,ushort const *,ushort const *)
0x1800092b5  mov     ebx, eax
0x1800092b7  lea     rcx, [rsp+78h+var_58]; this
0x1800092bc  call    ??1CSiteCreator@@UEAA@XZ; CSiteCreator::~CSiteCreator(void)
0x1800092c1  mov     eax, ebx
0x1800092c3  lea     r11, [rsp+78h+var_8]
0x1800092c8  mov     rbx, [r11+10h]
0x1800092cc  mov     rsi, [r11+18h]
0x1800092d0  mov     rsp, r11
0x1800092d3  pop     rdi
0x1800092d4  retn
```
