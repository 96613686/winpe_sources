# CIISWebService::DeleteExtensionFileRecord(ushort *)

- ea: `0x180009200`
- end: `0x180009257`
- name: `?DeleteExtensionFileRecord@CIISWebService@@UEAAJPEAG@Z`
- size: `87`
- prototype: `__int64 __fastcall(CIISWebService *this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x180009200`
- `0x18000e330`
- `0x18000e380`
- `0x18000ec68`

## pseudocode

```c
__int64 __fastcall CIISWebService::DeleteExtensionFileRecord(CIISWebService *this, unsigned __int16 *a2)
{
  unsigned int v5; // ebx
  _BYTE v6[88]; // [rsp+20h] [rbp-58h] BYREF

  if ( !a2 )
    return 2147500035LL;
  CSecConLib::CSecConLib((CSecConLib *)v6, *((struct IMSAdminBaseW **)this + 15));
  v5 = CSecConLib::DeleteExtensionFileRecord((CSecConLib *)v6, a2, *((const unsigned __int16 **)this + 9));
  CSiteCreator::~CSiteCreator((CSiteCreator *)v6);
  return v5;
}

```

## disassembly

```asm
0x180009200  mov     [rsp+arg_0], rbx
0x180009205  push    rdi
0x180009206  sub     rsp, 70h
0x18000920a  mov     rbx, rdx
0x18000920d  mov     rdi, rcx
0x180009210  test    rdx, rdx
0x180009213  jnz     short loc_18000921C
0x180009215  mov     eax, 80004003h
0x18000921a  jmp     short loc_180009249
0x18000921c  mov     rdx, [rcx+78h]; struct IMSAdminBaseW *
0x180009220  lea     rcx, [rsp+78h+var_58]; this
0x180009225  call    ??0CSecConLib@@QEAA@PEAUIMSAdminBaseW@@@Z; CSecConLib::CSecConLib(IMSAdminBaseW *)
0x18000922a  mov     r8, [rdi+48h]; unsigned __int16 *
0x18000922e  lea     rcx, [rsp+78h+var_58]; this
0x180009233  mov     rdx, rbx; unsigned __int16 *
0x180009236  call    ?DeleteExtensionFileRecord@CSecConLib@@QEAAJPEBG0@Z; CSecConLib::DeleteExtensionFileRecord(ushort const *,ushort const *)
0x18000923b  lea     rcx, [rsp+78h+var_58]; this
0x180009240  mov     ebx, eax
0x180009242  call    ??1CSiteCreator@@UEAA@XZ; CSiteCreator::~CSiteCreator(void)
0x180009247  mov     eax, ebx
0x180009249  mov     rbx, [rsp+78h+arg_0]
0x180009251  add     rsp, 70h
0x180009255  pop     rdi
0x180009256  retn
```
