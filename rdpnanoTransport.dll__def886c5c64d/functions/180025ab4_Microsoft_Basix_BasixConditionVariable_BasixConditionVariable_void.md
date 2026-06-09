# Microsoft::Basix::BasixConditionVariable::BasixConditionVariable(void)

- ea: `0x180025ab4`
- end: `0x180025b41`
- name: `??0BasixConditionVariable@Basix@Microsoft@@QEAA@XZ`
- size: `141`
- prototype: `__int64 __fastcall(Microsoft::Basix::BasixConditionVariable *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180025be4`
- `0x18028c74c`
- `0x18029426c`

## callees

- `0x180024700`
- `0x180025ab4`
- `0x1802e9b68`
- `0x18032f050`
- `0x180330b40`

## import_xrefs

- `KERNEL32!CreateEventA` at `0x180025ad7`
- `KERNEL32!CreateEventA` at `0x180025ad7`

## string_xrefs

- `0x180025b03`: `Failed to create Windows event handle`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Microsoft::Basix::BasixConditionVariable *__fastcall Microsoft::Basix::BasixConditionVariable::BasixConditionVariable(
        Microsoft::Basix::BasixConditionVariable *this)
{
  HANDLE EventA; // rax
  _BYTE v4[32]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v5[32]; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[136]; // [rsp+60h] [rbp-88h] BYREF

  *(_QWORD *)this = 0;
  EventA = CreateEventA(0, 0, 0, 0);
  *(_QWORD *)this = EventA;
  if ( !EventA )
  {
    std::string::string(v4, "C:\\__w\\1\\s\\src\\libbasix\\publicinc\\libbasix/synch.h");
    std::string::string(v5, "Failed to create Windows event handle");
    Microsoft::Basix::Exception::Exception(pExceptionObject, v5, v4, 35);
    throw (Microsoft::Basix::Exception *)pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x180025ab4  push    rbx
0x180025ab6  mov     eax, 0E0h
0x180025abb  call    _alloca_probe
0x180025ac0  sub     rsp, rax
0x180025ac3  mov     rbx, rcx
0x180025ac6  mov     qword ptr [rcx], 0
0x180025acd  xor     r9d, r9d; lpName
0x180025ad0  xor     r8d, r8d; bInitialState
0x180025ad3  xor     edx, edx; bManualReset
0x180025ad5  xor     ecx, ecx; lpEventAttributes
0x180025ad7  call    cs:__imp_CreateEventA
0x180025add  mov     [rbx], rax
0x180025ae0  test    rax, rax
0x180025ae3  jz      short loc_180025AF1
0x180025ae5  mov     rax, rbx
0x180025ae8  add     rsp, 0E0h
0x180025aef  pop     rbx
0x180025af0  retn
0x180025af1  lea     rdx, aCW1SSrcLibbasi_36; "C:\\__w\\1\\s\\src\\libbasix\\publicinc"...
0x180025af8  lea     rcx, [rsp+0E8h+var_C8]
0x180025afd  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180025b02  nop
0x180025b03  lea     rdx, aFailedToCreate_11; "Failed to create Windows event handle"
0x180025b0a  lea     rcx, [rsp+0E8h+var_A8]
0x180025b0f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180025b14  nop
0x180025b15  mov     r9d, 23h ; '#'
0x180025b1b  lea     r8, [rsp+0E8h+var_C8]
0x180025b20  lea     rdx, [rsp+0E8h+var_A8]
0x180025b25  lea     rcx, [rsp+0E8h+pExceptionObject]
0x180025b2a  call    ??0Exception@Basix@Microsoft@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0_K@Z; Microsoft::Basix::Exception::Exception(std::string const &,std::string const &,unsigned __int64)
0x180025b2f  lea     rdx, _TI4?AVException@Basix@Microsoft@@; pThrowInfo
0x180025b36  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x180025b3b  call    _CxxThrowException
```
