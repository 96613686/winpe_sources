# CIISWebService::AddDependency(ushort *,ushort *)

- ea: `0x1800086f0`
- end: `0x18000875b`
- name: `?AddDependency@CIISWebService@@UEAAJPEAG0@Z`
- size: `107`
- prototype: `int(CIISWebService *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x1800086f0`
- `0x18000e330`
- `0x18000e380`
- `0x18000e408`

## pseudocode

```c
__int64 __fastcall CIISWebService::AddDependency(CIISWebService *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  unsigned int v6; // ebx
  _BYTE v8[80]; // [rsp+20h] [rbp-58h] BYREF

  if ( !a2 || !a3 )
    return 2147500035LL;
  CSecConLib::CSecConLib((CSecConLib *)v8, *((struct IMSAdminBaseW **)this + 15));
  v6 = CSecConLib::AddDependency((CSecConLib *)v8, a2, a3, *((const unsigned __int16 **)this + 9));
  CSiteCreator::~CSiteCreator((CSiteCreator *)v8);
  return v6;
}

```

## disassembly

```asm
0x1800086f0  mov     [rsp+arg_0], rbx
0x1800086f5  mov     [rsp+arg_8], rsi
0x1800086fa  push    rdi
0x1800086fb  sub     rsp, 70h
0x1800086ff  mov     rbx, r8
0x180008702  mov     rdi, rdx
0x180008705  mov     rsi, rcx
0x180008708  test    rdx, rdx
0x18000870b  jz      short loc_180008744
0x18000870d  test    rbx, rbx
0x180008710  jz      short loc_180008744
0x180008712  mov     rdx, [rcx+78h]; struct IMSAdminBaseW *
0x180008716  lea     rcx, [rsp+78h+var_58]; this
0x18000871b  call    ??0CSecConLib@@QEAA@PEAUIMSAdminBaseW@@@Z; CSecConLib::CSecConLib(IMSAdminBaseW *)
0x180008720  mov     r9, [rsi+48h]; unsigned __int16 *
0x180008724  lea     rcx, [rsp+78h+var_58]; this
0x180008729  mov     r8, rbx; wchar_t *
0x18000872c  mov     rdx, rdi; Source
0x18000872f  call    ?AddDependency@CSecConLib@@QEAAJPEBG00@Z; CSecConLib::AddDependency(ushort const *,ushort const *,ushort const *)
0x180008734  lea     rcx, [rsp+78h+var_58]; this
0x180008739  mov     ebx, eax
0x18000873b  call    ??1CSiteCreator@@UEAA@XZ; CSiteCreator::~CSiteCreator(void)
0x180008740  mov     eax, ebx
0x180008742  jmp     short loc_180008749
0x180008744  mov     eax, 80004003h
0x180008749  lea     r11, [rsp+78h+var_8]
0x18000874e  mov     rbx, [r11+10h]
0x180008752  mov     rsi, [r11+18h]
0x180008756  mov     rsp, r11
0x180008759  pop     rdi
0x18000875a  retn
```
