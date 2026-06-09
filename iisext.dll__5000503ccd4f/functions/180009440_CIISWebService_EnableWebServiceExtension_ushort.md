# CIISWebService::EnableWebServiceExtension(ushort *)

- ea: `0x180009440`
- end: `0x1800094b5`
- name: `?EnableWebServiceExtension@CIISWebService@@UEAAJPEAG@Z`
- size: `117`
- prototype: `int(CIISWebService *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x180009440`
- `0x18000e330`
- `0x18000e380`
- `0x18000f1c0`
- `0x1800103ac`

## pseudocode

```c
__int64 __fastcall CIISWebService::EnableWebServiceExtension(struct IMSAdminBaseW **this, unsigned __int16 *a2)
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
    inited = CSecConLib::StatusWServEx((CSecConLib *)v7, 1, a2, v5);
  CSiteCreator::~CSiteCreator((CSiteCreator *)v7);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180009440  mov     [rsp+arg_0], rbx
0x180009445  mov     [rsp+arg_8], rsi
0x18000944a  push    rdi
0x18000944b  sub     rsp, 70h
0x18000944f  mov     rdi, rdx
0x180009452  mov     rbx, rcx
0x180009455  test    rdx, rdx
0x180009458  jnz     short loc_180009461
0x18000945a  mov     eax, 80004003h
0x18000945f  jmp     short loc_1800094A3
0x180009461  mov     rdx, [rcx+78h]; struct IMSAdminBaseW *
0x180009465  lea     rcx, [rsp+78h+var_58]; this
0x18000946a  call    ??0CSecConLib@@QEAA@PEAUIMSAdminBaseW@@@Z; CSecConLib::CSecConLib(IMSAdminBaseW *)
0x18000946f  mov     rsi, [rbx+48h]
0x180009473  lea     rcx, [rsp+78h+var_58]; this
0x180009478  call    ?InternalInitIfNecessary@CSecConLib@@AEAAJXZ; CSecConLib::InternalInitIfNecessary(void)
0x18000947d  mov     ebx, eax
0x18000947f  test    eax, eax
0x180009481  js      short loc_180009497
0x180009483  mov     r9, rsi; unsigned __int16 *
0x180009486  lea     rcx, [rsp+78h+var_58]; this
0x18000948b  mov     r8, rdi; unsigned __int16 *
0x18000948e  mov     dl, 1; bool
0x180009490  call    ?StatusWServEx@CSecConLib@@AEAAJ_NPEBG1@Z; CSecConLib::StatusWServEx(bool,ushort const *,ushort const *)
0x180009495  mov     ebx, eax
0x180009497  lea     rcx, [rsp+78h+var_58]; this
0x18000949c  call    ??1CSiteCreator@@UEAA@XZ; CSiteCreator::~CSiteCreator(void)
0x1800094a1  mov     eax, ebx
0x1800094a3  lea     r11, [rsp+78h+var_8]
0x1800094a8  mov     rbx, [r11+10h]
0x1800094ac  mov     rsi, [r11+18h]
0x1800094b0  mov     rsp, r11
0x1800094b3  pop     rdi
0x1800094b4  retn
```
