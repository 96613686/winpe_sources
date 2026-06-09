# CIISWebService::RemoveApplication(ushort *)

- ea: `0x180009a10`
- end: `0x180009a67`
- name: `?RemoveApplication@CIISWebService@@UEAAJPEAG@Z`
- size: `87`
- prototype: `int(CIISWebService *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180009a10`
- `0x18000e330`
- `0x18000e380`
- `0x18000fb88`

## pseudocode

```c
__int64 __fastcall CIISWebService::RemoveApplication(CIISWebService *this, unsigned __int16 *a2)
{
  unsigned int v5; // ebx
  _BYTE v6[88]; // [rsp+20h] [rbp-58h] BYREF

  if ( !a2 )
    return 2147500035LL;
  CSecConLib::CSecConLib((CSecConLib *)v6, *((struct IMSAdminBaseW **)this + 15));
  v5 = CSecConLib::RemoveApplication((CSecConLib *)v6, a2, *((const unsigned __int16 **)this + 9));
  CSiteCreator::~CSiteCreator((CSiteCreator *)v6);
  return v5;
}

```

## disassembly

```asm
0x180009a10  mov     [rsp+arg_0], rbx
0x180009a15  push    rdi
0x180009a16  sub     rsp, 70h
0x180009a1a  mov     rbx, rdx
0x180009a1d  mov     rdi, rcx
0x180009a20  test    rdx, rdx
0x180009a23  jnz     short loc_180009A2C
0x180009a25  mov     eax, 80004003h
0x180009a2a  jmp     short loc_180009A59
0x180009a2c  mov     rdx, [rcx+78h]; struct IMSAdminBaseW *
0x180009a30  lea     rcx, [rsp+78h+var_58]; this
0x180009a35  call    ??0CSecConLib@@QEAA@PEAUIMSAdminBaseW@@@Z; CSecConLib::CSecConLib(IMSAdminBaseW *)
0x180009a3a  mov     r8, [rdi+48h]; unsigned __int16 *
0x180009a3e  lea     rcx, [rsp+78h+var_58]; this
0x180009a43  mov     rdx, rbx; unsigned __int16 *
0x180009a46  call    ?RemoveApplication@CSecConLib@@QEAAJPEBG0@Z; CSecConLib::RemoveApplication(ushort const *,ushort const *)
0x180009a4b  lea     rcx, [rsp+78h+var_58]; this
0x180009a50  mov     ebx, eax
0x180009a52  call    ??1CSiteCreator@@UEAA@XZ; CSiteCreator::~CSiteCreator(void)
0x180009a57  mov     eax, ebx
0x180009a59  mov     rbx, [rsp+78h+arg_0]
0x180009a61  add     rsp, 70h
0x180009a65  pop     rdi
0x180009a66  retn
```
