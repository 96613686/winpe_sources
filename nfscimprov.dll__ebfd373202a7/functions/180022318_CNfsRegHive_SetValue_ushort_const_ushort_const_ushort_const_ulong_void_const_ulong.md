# CNfsRegHive::SetValue(ushort const *,ushort const *,ushort const *,ulong,void const *,ulong)

- ea: `0x180022318`
- end: `0x18002237d`
- name: `?SetValue@CNfsRegHive@@QEAAJPEBG00KPEBXK@Z`
- size: `101`
- prototype: `int(CNfsRegHive *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const void *, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180011874`
- `0x180011ad4`
- `0x18001248c`
- `0x180012690`
- `0x1800272a0`

## callees

- `0x180022318`

## import_xrefs

- `ADVAPI32!RegSetKeyValueW` at `0x180022372`
- `ADVAPI32!RegSetKeyValueW` at `0x180022372`
- `CLUSAPI!ClusterRegSetValue` at `0x18002234c`
- `CLUSAPI!ClusterRegSetValue` at `0x18002234c`

## pseudocode

```c
LSTATUS __fastcall CNfsRegHive::SetValue(
        CNfsRegHive *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD dwType,
        BYTE *lpData,
        DWORD cbData)
{
  HKEY v7; // rcx

  if ( !*(_DWORD *)this || !a4 )
    return RegSetKeyValueW(HKEY_LOCAL_MACHINE, a2, a3, dwType, lpData, cbData);
  v7 = (HKEY)*((_QWORD *)this + 4);
  if ( v7 )
    return ClusterRegSetValue(v7, a4, dwType, lpData, cbData);
  else
    return 6;
}

```

## disassembly

```asm
0x180022318  sub     rsp, 38h
0x18002231c  cmp     dword ptr [rcx], 0
0x18002231f  mov     r10, r9
0x180022322  jz      short loc_180022354
0x180022324  test    r9, r9
0x180022327  jz      short loc_180022354
0x180022329  mov     rcx, [rcx+20h]; hKey
0x18002232d  test    rcx, rcx
0x180022330  jnz     short loc_180022337
0x180022332  lea     eax, [rcx+6]
0x180022335  jmp     short loc_180022378
0x180022337  mov     eax, [rsp+38h+arg_30]
0x18002233b  mov     rdx, r10; lpszValueName
0x18002233e  mov     r9, [rsp+38h+lpData]; lpData
0x180022343  mov     r8d, [rsp+38h+dwType]; dwType
0x180022348  mov     [rsp+38h+cbData], eax; cbData
0x18002234c  call    cs:__imp_ClusterRegSetValue
0x180022352  jmp     short loc_180022378
0x180022354  mov     eax, [rsp+38h+arg_30]
0x180022358  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002235f  mov     r9d, [rsp+38h+dwType]; dwType
0x180022364  mov     [rsp+38h+var_10], eax; cbData
0x180022368  mov     rax, [rsp+38h+lpData]
0x18002236d  mov     qword ptr [rsp+38h+cbData], rax; lpData
0x180022372  call    cs:__imp_RegSetKeyValueW
0x180022378  add     rsp, 38h
0x18002237c  retn
```
