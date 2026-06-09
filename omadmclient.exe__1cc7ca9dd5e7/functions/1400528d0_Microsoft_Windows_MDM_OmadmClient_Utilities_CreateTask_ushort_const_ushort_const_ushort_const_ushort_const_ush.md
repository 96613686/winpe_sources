# Microsoft::Windows::MDM::OmadmClient::Utilities::CreateTask(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x1400528d0`
- end: `0x14005290f`
- name: `?CreateTask@Utilities@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEBG0000K@Z`
- size: `63`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::Utilities *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `DMCmnUtils!DmCreateTask` at `0x1400528fc`
- `DMCmnUtils!DmCreateTask` at `0x1400528fc`

## pseudocode

```c
int __fastcall Microsoft::Windows::MDM::OmadmClient::Utilities::CreateTask(
        Microsoft::Windows::MDM::OmadmClient::Utilities *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        unsigned int a7)
{
  return DmCreateTask(a2, a3, a4, a5, a6, a7);
}

```

## disassembly

```asm
0x1400528d0  push    rbx
0x1400528d2  sub     rsp, 30h
0x1400528d6  mov     eax, [rsp+38h+arg_30]
0x1400528da  mov     r10, r9
0x1400528dd  mov     r9, [rsp+38h+arg_20]
0x1400528e2  mov     r11, r8
0x1400528e5  mov     [rsp+38h+var_10], eax
0x1400528e9  mov     rcx, rdx
0x1400528ec  mov     rax, [rsp+38h+arg_28]
0x1400528f1  mov     r8, r10
0x1400528f4  mov     rdx, r11
0x1400528f7  mov     [rsp+38h+var_18], rax
0x1400528fc  call    cs:__imp_?DmCreateTask@@YAJPEBG0000K@Z; DmCreateTask(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)
0x140052903  nop     dword ptr [rax+rax+00h]
0x140052908  add     rsp, 30h
0x14005290c  pop     rbx
0x14005290d  retn
```
