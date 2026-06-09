# UpdateShimImplStatus(ShimImplStatus,ushort *)

- ea: `0x180008a2c`
- end: `0x180008a84`
- name: `?UpdateShimImplStatus@@YAXW4ShimImplStatus@@PEAG@Z`
- size: `88`
- prototype: `void __high(enum ShimImplStatus, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180002a90`

## callees

- `0x180008a2c`
- `0x18000c1a8`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180008a42`
- `KERNEL32!EnterCriticalSection` at `0x180008a42`
- `KERNEL32!LeaveCriticalSection` at `0x180008a7d`

## string_xrefs

- `0x180008a55`: `mscoreei.dll`

## pseudocode

```c
void __fastcall UpdateShimImplStatus(int a1, const wchar_t *a2)
{
  EnterCriticalSection(&g_csInitShim);
  if ( !(_DWORD)g_shimImplStatus )
  {
    wcscpy_s(g_wszShimImplDllPath, 0x104u, a2);
    LODWORD(g_shimImplStatus) = a1;
  }
  LeaveCriticalSection(&g_csInitShim);
}

```

## disassembly

```asm
0x180008a2c  mov     [rsp+arg_0], rbx
0x180008a31  push    rdi
0x180008a32  sub     rsp, 20h
0x180008a36  mov     edi, ecx
0x180008a38  mov     rbx, rdx
0x180008a3b  lea     rcx, ?g_csInitShim@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180008a42  call    cs:__imp_EnterCriticalSection
0x180008a48  mov     eax, cs:?g_shimImplStatus@@3W4ShimImplStatus@@C; ShimImplStatus volatile g_shimImplStatus
0x180008a4e  test    eax, eax
0x180008a50  jnz     short loc_180008A6C
0x180008a52  mov     r8, rbx; Source
0x180008a55  lea     rcx, ?g_wszShimImplDllPath@@3PAGA; "mscoreei.dll"
0x180008a5c  mov     edx, 104h; SizeInWords
0x180008a61  call    wcscpy_s
0x180008a66  mov     cs:?g_shimImplStatus@@3W4ShimImplStatus@@C, edi; ShimImplStatus volatile g_shimImplStatus
0x180008a6c  lea     rcx, ?g_csInitShim@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csInitShim
0x180008a73  mov     rbx, [rsp+28h+arg_0]
0x180008a78  add     rsp, 20h
0x180008a7c  pop     rdi
0x180008a7d  jmp     cs:__imp_LeaveCriticalSection
```
