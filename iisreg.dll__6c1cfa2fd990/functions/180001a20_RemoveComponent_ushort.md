# RemoveComponent(ushort *)

- ea: `0x180001a20`
- end: `0x180001aa9`
- name: `?RemoveComponent@@YAJPEAG@Z`
- size: `137`
- prototype: `__int64 __fastcall(wchar_t *String2)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180001a20`
- `0x1800029c4`
- `0x180002b90`
- `0x180002e64`
- `0x180002f84`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180001a68`
- `msvcrt!_wcsicmp` at `0x180001a68`

## pseudocode

```c
__int64 __fastcall RemoveComponent(wchar_t *String2)
{
  unsigned int v2; // esi
  int v3; // r14d
  __int64 i; // rbx
  struct IIS_SETUP_REGISTRY_ENTRY (near **v5)[1]; // rdi
  struct IIS_SETUP_REGISTRY_ENTRY *v6; // rcx

  if ( String2 )
  {
    v2 = 0;
    v3 = Is64BitMachine();
    for ( i = 597; i != -1; --i )
    {
      v5 = &g_FileRegistrationList + 9 * i;
      if ( (!*((_DWORD *)v5 + 16) || v3) && !_wcsicmp((const wchar_t *)*v5, String2) )
      {
        v6 = (struct IIS_SETUP_REGISTRY_ENTRY *)(&g_FileRegistrationList + 9 * i);
        if ( v5[4] )
          RemoveRegistryValue(v6);
        else
          RemoveRegistryKey(v6);
      }
    }
  }
  else
  {
    v2 = -2147024809;
  }
  g_pDebug = (HGLOBAL)PuDeleteDebugPrintsObject();
  return v2;
}

```

## disassembly

```asm
0x180001a20  push    rbx
0x180001a22  push    rbp
0x180001a23  push    rsi
0x180001a24  push    rdi
0x180001a25  push    r14
0x180001a27  sub     rsp, 20h
0x180001a2b  mov     rbp, rcx
0x180001a2e  test    rcx, rcx
0x180001a31  jnz     short loc_180001A3A
0x180001a33  mov     esi, 80070057h
0x180001a38  jmp     short loc_180001A90
0x180001a3a  xor     esi, esi
0x180001a3c  call    ?Is64BitMachine@@YAHXZ; Is64BitMachine(void)
0x180001a41  mov     r14d, eax
0x180001a44  mov     ebx, 255h
0x180001a49  lea     rax, [rbx+rbx*8]
0x180001a4d  lea     rcx, ?g_FileRegistrationList@@3PAY00UIIS_SETUP_REGISTRY_ENTRY@@A; IIS_SETUP_REGISTRY_ENTRY (near * g_FileRegistrationList)[1]
0x180001a54  lea     rdi, [rcx+rax*8]
0x180001a58  cmp     [rdi+40h], esi
0x180001a5b  jz      short loc_180001A62
0x180001a5d  test    r14d, r14d
0x180001a60  jz      short loc_180001A87
0x180001a62  mov     rcx, [rdi]; String1
0x180001a65  mov     rdx, rbp; String2
0x180001a68  call    cs:__imp__wcsicmp
0x180001a6e  test    eax, eax
0x180001a70  jnz     short loc_180001A87
0x180001a72  mov     rcx, rdi; struct IIS_SETUP_REGISTRY_ENTRY *
0x180001a75  cmp     [rdi+20h], rsi
0x180001a79  jnz     short loc_180001A82
0x180001a7b  call    ?RemoveRegistryKey@@YAJPEAUIIS_SETUP_REGISTRY_ENTRY@@@Z; RemoveRegistryKey(IIS_SETUP_REGISTRY_ENTRY *)
0x180001a80  jmp     short loc_180001A87
0x180001a82  call    ?RemoveRegistryValue@@YAJPEAUIIS_SETUP_REGISTRY_ENTRY@@@Z; RemoveRegistryValue(IIS_SETUP_REGISTRY_ENTRY *)
0x180001a87  dec     rbx
0x180001a8a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001a8e  jnz     short loc_180001A49
0x180001a90  call    PuDeleteDebugPrintsObject
0x180001a95  mov     cs:g_pDebug, rax
0x180001a9c  mov     eax, esi
0x180001a9e  add     rsp, 20h
0x180001aa2  pop     r14
0x180001aa4  pop     rdi
0x180001aa5  pop     rsi
0x180001aa6  pop     rbp
0x180001aa7  pop     rbx
0x180001aa8  retn
```
