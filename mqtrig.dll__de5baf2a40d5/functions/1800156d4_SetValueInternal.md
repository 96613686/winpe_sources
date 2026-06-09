# SetValueInternal

- ea: `0x1800156d4`
- end: `0x18001573f`
- name: `SetValueInternal`
- size: `107`
- prototype: `__int64 __fastcall(struct RegEntry *, DWORD dwType, BYTE *lpData, DWORD cbData)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001519c`
- `0x18001634c`
- `0x180016bf0`
- `0x180019f58`
- `0x180020c85`

## callees

- `0x18000a2b8`
- `0x180014fc8`
- `0x1800156d4`
- `0x180015748`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18001570d`
- `ADVAPI32!RegSetValueExW` at `0x18001570d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SetValueInternal(struct RegEntry *a1, DWORD dwType, BYTE *lpData, DWORD cbData)
{
  int v8; // eax
  HKEY Key; // [rsp+60h] [rbp+8h] BYREF

  Key = CmCreateKey(a1, 2u);
  v8 = RegSetValueExW(Key, *((LPCWSTR *)a1 + 2), 0, dwType, lpData, cbData);
  if ( v8 )
  {
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    ThrowMissingValue(a1, v8);
  }
  CRegHandle::~CRegHandle(&Key);
}

```

## disassembly

```asm
0x1800156d4  push    rbx
0x1800156d6  push    rbp
0x1800156d7  push    rsi
0x1800156d8  push    rdi
0x1800156d9  sub     rsp, 38h
0x1800156dd  mov     ebx, r9d
0x1800156e0  mov     rdi, r8
0x1800156e3  mov     esi, edx
0x1800156e5  mov     rbp, rcx
0x1800156e8  mov     edx, 2; samDesired
0x1800156ed  call    ?CmCreateKey@@YAPEAUHKEY__@@AEBVRegEntry@@K@Z; CmCreateKey(RegEntry const &,ulong)
0x1800156f2  mov     [rsp+58h+arg_0], rax
0x1800156f7  mov     [rsp+58h+cbData], ebx; cbData
0x1800156fb  mov     [rsp+58h+lpData], rdi; lpData
0x180015700  mov     r9d, esi; dwType
0x180015703  xor     r8d, r8d; Reserved
0x180015706  mov     rdx, [rbp+10h]; lpValueName
0x18001570a  mov     rcx, rax; hKey
0x18001570d  call    cs:__imp_RegSetValueExW
0x180015713  test    eax, eax
0x180015715  jz      short loc_18001572C
0x180015717  jle     short loc_180015721
0x180015719  movzx   eax, ax
0x18001571c  or      eax, 80070000h
0x180015721  mov     edx, eax; int
0x180015723  mov     rcx, rbp; struct RegEntry *
0x180015726  call    ?ThrowMissingValue@@YAXAEBVRegEntry@@J@Z; ThrowMissingValue(RegEntry const &,long)
0x18001572b  nop
0x18001572c  lea     rcx, [rsp+58h+arg_0]; this
0x180015731  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x180015736  add     rsp, 38h
0x18001573a  pop     rdi
0x18001573b  pop     rsi
0x18001573c  pop     rbp
0x18001573d  pop     rbx
0x18001573e  retn
```
