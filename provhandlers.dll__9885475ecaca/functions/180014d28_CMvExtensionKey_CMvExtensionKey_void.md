# CMvExtensionKey::~CMvExtensionKey(void)

- ea: `0x180014d28`
- end: `0x180014d60`
- name: `??1CMvExtensionKey@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(CMvExtensionKey *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180013d68`
- `0x180014910`

## callees

- `0x180014d28`
- `0x180015934`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014d3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014d3d`

## pseudocode

```c
void __fastcall CMvExtensionKey::~CMvExtensionKey(CMvExtensionKey *this)
{
  HKEY v2; // rcx
  struct IMVKey **v3; // rcx

  v2 = (HKEY)*((_QWORD *)this + 78);
  if ( v2 )
    RegCloseKey(v2);
  v3 = (struct IMVKey **)*((_QWORD *)this + 76);
  if ( v3 )
    ReleaseKeyArray(v3, *((_DWORD *)this + 154));
}

```

## disassembly

```asm
0x180014d28  push    rbx
0x180014d2a  sub     rsp, 20h
0x180014d2e  mov     rbx, rcx
0x180014d31  mov     rcx, [rcx+270h]; hKey
0x180014d38  test    rcx, rcx
0x180014d3b  jz      short loc_180014D43
0x180014d3d  call    cs:__imp_RegCloseKey
0x180014d43  mov     rcx, [rbx+260h]; struct IMVKey **
0x180014d4a  test    rcx, rcx
0x180014d4d  jz      short loc_180014D5A
0x180014d4f  mov     edx, [rbx+268h]; unsigned int
0x180014d55  call    ?ReleaseKeyArray@@YAXPEAPEAUIMVKey@@K@Z; ReleaseKeyArray(IMVKey * *,ulong)
0x180014d5a  add     rsp, 20h
0x180014d5e  pop     rbx
0x180014d5f  retn
```
