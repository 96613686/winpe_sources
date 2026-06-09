# CIISWebService::EnableApplication(ushort *)

- ea: `0x180009360`
- end: `0x1800093b7`
- name: `?EnableApplication@CIISWebService@@UEAAJPEAG@Z`
- size: `87`
- prototype: `int(CIISWebService *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180009360`
- `0x18000e330`
- `0x18000e380`
- `0x18000ee40`

## pseudocode

```c
__int64 __fastcall CIISWebService::EnableApplication(CIISWebService *this, unsigned __int16 *a2)
{
  unsigned int v5; // ebx
  _BYTE v6[88]; // [rsp+20h] [rbp-58h] BYREF

  if ( !a2 )
    return 2147500035LL;
  CSecConLib::CSecConLib((CSecConLib *)v6, *((struct IMSAdminBaseW **)this + 15));
  v5 = CSecConLib::EnableApplication((CSecConLib *)v6, a2, *((const unsigned __int16 **)this + 9));
  CSiteCreator::~CSiteCreator((CSiteCreator *)v6);
  return v5;
}

```

## disassembly

```asm
0x180009360  mov     [rsp+arg_0], rbx
0x180009365  push    rdi
0x180009366  sub     rsp, 70h
0x18000936a  mov     rbx, rdx
0x18000936d  mov     rdi, rcx
0x180009370  test    rdx, rdx
0x180009373  jnz     short loc_18000937C
0x180009375  mov     eax, 80004003h
0x18000937a  jmp     short loc_1800093A9
0x18000937c  mov     rdx, [rcx+78h]; struct IMSAdminBaseW *
0x180009380  lea     rcx, [rsp+78h+var_58]; this
0x180009385  call    ??0CSecConLib@@QEAA@PEAUIMSAdminBaseW@@@Z; CSecConLib::CSecConLib(IMSAdminBaseW *)
0x18000938a  mov     r8, [rdi+48h]; unsigned __int16 *
0x18000938e  lea     rcx, [rsp+78h+var_58]; this
0x180009393  mov     rdx, rbx; unsigned __int16 *
0x180009396  call    ?EnableApplication@CSecConLib@@QEAAJPEBG0@Z; CSecConLib::EnableApplication(ushort const *,ushort const *)
0x18000939b  lea     rcx, [rsp+78h+var_58]; this
0x1800093a0  mov     ebx, eax
0x1800093a2  call    ??1CSiteCreator@@UEAA@XZ; CSiteCreator::~CSiteCreator(void)
0x1800093a7  mov     eax, ebx
0x1800093a9  mov     rbx, [rsp+78h+arg_0]
0x1800093b1  add     rsp, 70h
0x1800093b5  pop     rdi
0x1800093b6  retn
```
