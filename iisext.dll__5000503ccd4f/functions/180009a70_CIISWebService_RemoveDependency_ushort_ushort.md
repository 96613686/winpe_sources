# CIISWebService::RemoveDependency(ushort *,ushort *)

- ea: `0x180009a70`
- end: `0x180009adb`
- name: `?RemoveDependency@CIISWebService@@UEAAJPEAG0@Z`
- size: `107`
- prototype: `int(CIISWebService *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180009a70`
- `0x18000e330`
- `0x18000e380`
- `0x18000fd64`

## pseudocode

```c
__int64 __fastcall CIISWebService::RemoveDependency(CIISWebService *this, unsigned __int16 *a2, char *a3)
{
  unsigned int v6; // ebx
  _BYTE v8[80]; // [rsp+20h] [rbp-58h] BYREF

  if ( !a2 || !a3 )
    return 2147500035LL;
  CSecConLib::CSecConLib((CSecConLib *)v8, *((struct IMSAdminBaseW **)this + 15));
  v6 = CSecConLib::RemoveDependency((CSecConLib *)v8, a2, a3, *((const unsigned __int16 **)this + 9));
  CSiteCreator::~CSiteCreator((CSiteCreator *)v8);
  return v6;
}

```

## disassembly

```asm
0x180009a70  mov     [rsp+arg_0], rbx
0x180009a75  mov     [rsp+arg_8], rsi
0x180009a7a  push    rdi
0x180009a7b  sub     rsp, 70h
0x180009a7f  mov     rbx, r8
0x180009a82  mov     rdi, rdx
0x180009a85  mov     rsi, rcx
0x180009a88  test    rdx, rdx
0x180009a8b  jz      short loc_180009AC4
0x180009a8d  test    rbx, rbx
0x180009a90  jz      short loc_180009AC4
0x180009a92  mov     rdx, [rcx+78h]; struct IMSAdminBaseW *
0x180009a96  lea     rcx, [rsp+78h+var_58]; this
0x180009a9b  call    ??0CSecConLib@@QEAA@PEAUIMSAdminBaseW@@@Z; CSecConLib::CSecConLib(IMSAdminBaseW *)
0x180009aa0  mov     r9, [rsi+48h]; unsigned __int16 *
0x180009aa4  lea     rcx, [rsp+78h+var_58]; this
0x180009aa9  mov     r8, rbx; unsigned __int16 *
0x180009aac  mov     rdx, rdi; String1
0x180009aaf  call    ?RemoveDependency@CSecConLib@@QEAAJPEBG00@Z; CSecConLib::RemoveDependency(ushort const *,ushort const *,ushort const *)
0x180009ab4  lea     rcx, [rsp+78h+var_58]; this
0x180009ab9  mov     ebx, eax
0x180009abb  call    ??1CSiteCreator@@UEAA@XZ; CSiteCreator::~CSiteCreator(void)
0x180009ac0  mov     eax, ebx
0x180009ac2  jmp     short loc_180009AC9
0x180009ac4  mov     eax, 80004003h
0x180009ac9  lea     r11, [rsp+78h+var_8]
0x180009ace  mov     rbx, [r11+10h]
0x180009ad2  mov     rsi, [r11+18h]
0x180009ad6  mov     rsp, r11
0x180009ad9  pop     rdi
0x180009ada  retn
```
