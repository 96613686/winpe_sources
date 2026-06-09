# NotifyMultipleDevicesNeedReboot(void)

- ea: `0x18000bde4`
- end: `0x18000be91`
- name: `?NotifyMultipleDevicesNeedReboot@@YAJXZ`
- size: `173`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000b868`

## callees

- `0x1800037c4`
- `0x18000bde4`
- `0x18000c008`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be44`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bdfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bdfa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000be6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000be79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000be6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000be79`

## string_xrefs

- `0x18000bdf3`: `pnpui.dll`

## pseudocode

```c
__int64 NotifyMultipleDevicesNeedReboot(void)
{
  HMODULE ModuleHandleW; // rbx
  unsigned __int16 *v1; // rsi
  signed int v2; // eax
  unsigned int v3; // ebx
  const unsigned __int16 *v4; // rax
  const unsigned __int16 *v5; // r8
  const unsigned __int16 *v6; // r9
  unsigned __int16 *v7; // rdi
  signed int LastError; // eax

  ModuleHandleW = GetModuleHandleW(L"pnpui.dll");
  v1 = ShellConstructMessageString(ModuleHandleW, (const unsigned __int16 *)0x25B);
  if ( v1 )
  {
    v4 = ShellConstructMessageString(ModuleHandleW, (const unsigned __int16 *)0x25E);
    v7 = (unsigned __int16 *)v4;
    if ( v4 )
    {
      v3 = ShowNotifyToast(v1, v4, v5, v6);
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    LocalFree(v1);
    if ( v7 )
      LocalFree(v7);
  }
  else
  {
    v2 = GetLastError();
    v3 = v2;
    if ( v2 > 0 )
      return (unsigned __int16)v2 | 0x80070000;
  }
  return v3;
}

```

## disassembly

```asm
0x18000bde4  mov     [rsp+arg_0], rbx
0x18000bde9  mov     [rsp+arg_8], rsi
0x18000bdee  push    rdi
0x18000bdef  sub     rsp, 30h
0x18000bdf3  lea     rcx, ModuleName; "pnpui.dll"
0x18000bdfa  call    cs:__imp_GetModuleHandleW
0x18000be00  mov     rcx, rax; HINSTANCE
0x18000be03  mov     edx, 25Bh; unsigned __int16 *
0x18000be08  mov     rbx, rax
0x18000be0b  call    ?ShellConstructMessageString@@YAPEAGPEAUHINSTANCE__@@PEBGZZ; ShellConstructMessageString(HINSTANCE__ *,ushort const *,...)
0x18000be10  mov     rsi, rax
0x18000be13  test    rax, rax
0x18000be16  jnz     short loc_18000BE2F
0x18000be18  call    cs:__imp_GetLastError
0x18000be1e  mov     ebx, eax
0x18000be20  test    eax, eax
0x18000be22  jle     short loc_18000BE7F
0x18000be24  movzx   ebx, ax
0x18000be27  or      ebx, 80070000h
0x18000be2d  jmp     short loc_18000BE7F
0x18000be2f  mov     edx, 25Eh; unsigned __int16 *
0x18000be34  mov     rcx, rbx; HINSTANCE
0x18000be37  call    ?ShellConstructMessageString@@YAPEAGPEAUHINSTANCE__@@PEBGZZ; ShellConstructMessageString(HINSTANCE__ *,ushort const *,...)
0x18000be3c  mov     rdi, rax
0x18000be3f  test    rax, rax
0x18000be42  jnz     short loc_18000BE5B
0x18000be44  call    cs:__imp_GetLastError
0x18000be4a  mov     ebx, eax
0x18000be4c  test    eax, eax
0x18000be4e  jle     short loc_18000BE68
0x18000be50  movzx   ebx, ax
0x18000be53  or      ebx, 80070000h
0x18000be59  jmp     short loc_18000BE68
0x18000be5b  mov     rdx, rdi; unsigned __int16 *
0x18000be5e  mov     rcx, rsi; unsigned __int16 *
0x18000be61  call    ?ShowNotifyToast@@YAJPEBG00000@Z; ShowNotifyToast(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000be66  mov     ebx, eax
0x18000be68  mov     rcx, rsi; hMem
0x18000be6b  call    cs:__imp_LocalFree
0x18000be71  test    rdi, rdi
0x18000be74  jz      short loc_18000BE7F
0x18000be76  mov     rcx, rdi; hMem
0x18000be79  call    cs:__imp_LocalFree
0x18000be7f  mov     rsi, [rsp+38h+arg_8]
0x18000be84  mov     eax, ebx
0x18000be86  mov     rbx, [rsp+38h+arg_0]
0x18000be8b  add     rsp, 30h
0x18000be8f  pop     rdi
0x18000be90  retn
```
