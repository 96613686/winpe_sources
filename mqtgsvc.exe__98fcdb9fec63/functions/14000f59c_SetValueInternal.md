# SetValueInternal

- ea: `0x14000f59c`
- end: `0x14000f615`
- name: `SetValueInternal`
- size: `121`
- prototype: `void __fastcall(struct RegEntry *, __int64, const BYTE *, DWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000f068`

## callees

- `0x14000ce94`
- `0x14000ee94`
- `0x14000f59c`
- `0x14000f61c`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x14000f5dc`
- `ADVAPI32!RegSetValueExW` at `0x14000f5dc`

## pseudocode

```c
void __fastcall SetValueInternal(struct RegEntry *a1, __int64 a2, const BYTE *a3, DWORD a4)
{
  int v7; // eax
  HKEY Key; // [rsp+40h] [rbp+8h] BYREF

  Key = CmCreateKey(a1, 2u);
  v7 = RegSetValueExW(Key, *((LPCWSTR *)a1 + 2), 0, 1u, a3, a4);
  if ( v7 )
  {
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    ThrowMissingValue(a1, v7);
  }
  CRegHandle::~CRegHandle(&Key);
}

```

## disassembly

```asm
0x14000f59c  mov     [rsp+arg_8], rbx
0x14000f5a1  mov     [rsp+arg_10], rsi
0x14000f5a6  push    rdi
0x14000f5a7  sub     rsp, 30h
0x14000f5ab  mov     ebx, r9d
0x14000f5ae  mov     rdi, r8
0x14000f5b1  mov     rsi, rcx
0x14000f5b4  mov     edx, 2; samDesired
0x14000f5b9  call    ?CmCreateKey@@YAPEAUHKEY__@@AEBVRegEntry@@K@Z; CmCreateKey(RegEntry const &,ulong)
0x14000f5be  mov     [rsp+38h+arg_0], rax
0x14000f5c3  mov     [rsp+38h+cbData], ebx; cbData
0x14000f5c7  mov     [rsp+38h+lpData], rdi; lpData
0x14000f5cc  mov     r9d, 1; dwType
0x14000f5d2  xor     r8d, r8d; Reserved
0x14000f5d5  mov     rdx, [rsi+10h]; lpValueName
0x14000f5d9  mov     rcx, rax; hKey
0x14000f5dc  call    cs:__imp_RegSetValueExW
0x14000f5e2  test    eax, eax
0x14000f5e4  jz      short loc_14000F5FB
0x14000f5e6  jle     short loc_14000F5F0
0x14000f5e8  movzx   eax, ax
0x14000f5eb  or      eax, 80070000h
0x14000f5f0  mov     edx, eax; int
0x14000f5f2  mov     rcx, rsi; struct RegEntry *
0x14000f5f5  call    ?ThrowMissingValue@@YAXAEBVRegEntry@@J@Z; ThrowMissingValue(RegEntry const &,long)
0x14000f5fa  nop
0x14000f5fb  lea     rcx, [rsp+38h+arg_0]; this
0x14000f600  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x14000f605  mov     rbx, [rsp+38h+arg_8]
0x14000f60a  mov     rsi, [rsp+38h+arg_10]
0x14000f60f  add     rsp, 30h
0x14000f613  pop     rdi
0x14000f614  retn
```
