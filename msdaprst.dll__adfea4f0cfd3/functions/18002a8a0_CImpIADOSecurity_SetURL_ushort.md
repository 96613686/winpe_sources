# CImpIADOSecurity::SetURL(ushort *)

- ea: `0x18002a8a0`
- end: `0x18002a919`
- name: `?SetURL@CImpIADOSecurity@@UEAAJPEAG@Z`
- size: `121`
- prototype: `int(CImpIADOSecurity *__hidden this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800157e0`
- `0x18002a140`

## callees

- `0x18002a108`
- `0x18002a1a0`
- `0x18002a8a0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002a8e3`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a8e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a8c7`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a8c7`

## pseudocode

```c
__int64 __fastcall CImpIADOSecurity::SetURL(struct CCriticalSection **this, unsigned __int16 *a2)
{
  OLECHAR *v4; // rcx
  BSTR v5; // rax
  unsigned int v6; // ebx
  char v8; // [rsp+30h] [rbp+8h] BYREF

  CMPCSAutoBlock::CMPCSAutoBlock((CMPCSAutoBlock *)&v8, this + 6);
  v4 = (OLECHAR *)this[4];
  if ( v4 )
  {
    SysFreeString(v4);
    this[4] = 0;
  }
  if ( !a2 || (v5 = SysAllocString(a2), (this[4] = (struct CCriticalSection *)v5) != 0) )
    v6 = 0;
  else
    v6 = -2147024882;
  CMPCSAutoBlock::~CMPCSAutoBlock((CMPCSAutoBlock *)&v8);
  return v6;
}

```

## disassembly

```asm
0x18002a8a0  mov     [rsp+arg_8], rbx
0x18002a8a5  push    rdi
0x18002a8a6  sub     rsp, 20h
0x18002a8aa  mov     rdi, rdx
0x18002a8ad  mov     rbx, rcx
0x18002a8b0  lea     rdx, [rcx+30h]; struct CCriticalSection **
0x18002a8b4  lea     rcx, [rsp+28h+arg_0]; this
0x18002a8b9  call    ??0CMPCSAutoBlock@@QEAA@PEAPEAVCCriticalSection@@@Z; CMPCSAutoBlock::CMPCSAutoBlock(CCriticalSection * *)
0x18002a8be  mov     rcx, [rbx+20h]; bstrString
0x18002a8c2  test    rcx, rcx
0x18002a8c5  jz      short loc_18002A8DB
0x18002a8c7  call    cs:__imp_SysFreeString
0x18002a8ce  nop     dword ptr [rax+rax+00h]
0x18002a8d3  mov     qword ptr [rbx+20h], 0
0x18002a8db  test    rdi, rdi
0x18002a8de  jz      short loc_18002A8FF
0x18002a8e0  mov     rcx, rdi; psz
0x18002a8e3  call    cs:__imp_SysAllocString
0x18002a8ea  nop     dword ptr [rax+rax+00h]
0x18002a8ef  mov     [rbx+20h], rax
0x18002a8f3  test    rax, rax
0x18002a8f6  jnz     short loc_18002A8FF
0x18002a8f8  mov     ebx, 8007000Eh
0x18002a8fd  jmp     short loc_18002A901
0x18002a8ff  xor     ebx, ebx
0x18002a901  lea     rcx, [rsp+28h+arg_0]; this
0x18002a906  call    ??1CMPCSAutoBlock@@QEAA@XZ; CMPCSAutoBlock::~CMPCSAutoBlock(void)
0x18002a90b  mov     eax, ebx
0x18002a90d  mov     rbx, [rsp+28h+arg_8]
0x18002a912  add     rsp, 20h
0x18002a916  pop     rdi
0x18002a917  retn
```
