# I_GetProcessName

- ea: `0x18000f098`
- end: `0x18000f141`
- name: `I_GetProcessName`
- size: `169`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180006090`
- `0x180007420`
- `0x18000ed40`
- `0x1800102c0`
- `0x180010684`
- `0x1800106f0`
- `0x180019b84`
- `0x18001b728`
- `0x18001b784`

## callees

- `0x18000f098`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000f0c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000f0c0`

## pseudocode

```c
WCHAR *I_GetProcessName()
{
  __int64 v0; // rax
  WCHAR *result; // rax
  WCHAR *v2; // rdx
  WCHAR *v3; // rcx

  if ( !dword_18002AAF8 )
  {
    GetModuleFileNameW(0, &g_wsProcessFileName, 0x100u);
    v0 = -1;
    do
      ++v0;
    while ( *(&g_wsProcessFileName + v0) );
    result = &g_wsProcessFileName + v0;
    qword_18002AAF0 = (__int64)result;
    if ( result == &g_wsProcessFileName )
    {
      v3 = result;
LABEL_8:
      if ( *result != 92 )
        goto LABEL_9;
    }
    else
    {
      v2 = result;
      while ( 1 )
      {
        v3 = v2;
        if ( *result == 92 )
          break;
        result = v2 - 1;
        qword_18002AAF0 = (__int64)result;
        --v2;
        v3 = result;
        if ( result == &g_wsProcessFileName )
          goto LABEL_8;
      }
    }
    result = v3 + 1;
    qword_18002AAF0 = (__int64)(v3 + 1);
LABEL_9:
    dword_18002AAF8 = 1;
    return result;
  }
  return (WCHAR *)qword_18002AAF0;
}

```

## disassembly

```asm
0x18000f098  mov     [rsp+arg_0], rbx
0x18000f09d  push    rdi
0x18000f09e  sub     rsp, 20h
0x18000f0a2  mov     eax, cs:dword_18002AAF8
0x18000f0a8  xor     ebx, ebx
0x18000f0aa  test    eax, eax
0x18000f0ac  jnz     short loc_18000F12B
0x18000f0ae  lea     rdi, g_wsProcessFileName
0x18000f0b5  mov     r8d, 100h; nSize
0x18000f0bb  mov     rdx, rdi; lpFilename
0x18000f0be  xor     ecx, ecx; hModule
0x18000f0c0  call    cs:__imp_GetModuleFileNameW
0x18000f0c6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f0ca  inc     rax
0x18000f0cd  cmp     [rdi+rax*2], bx
0x18000f0d1  jnz     short loc_18000F0CA
0x18000f0d3  lea     rax, [rdi+rax*2]
0x18000f0d7  mov     r8d, 5Ch ; '\'
0x18000f0dd  mov     cs:qword_18002AAF0, rax
0x18000f0e4  cmp     rax, rdi
0x18000f0e7  jz      short loc_18000F126
0x18000f0e9  mov     rdx, rax
0x18000f0ec  mov     rcx, rdx
0x18000f0ef  cmp     r8w, [rax]
0x18000f0f3  jz      short loc_18000F134
0x18000f0f5  lea     rax, [rdx-2]
0x18000f0f9  mov     cs:qword_18002AAF0, rax
0x18000f100  mov     rdx, rax
0x18000f103  mov     rcx, rax
0x18000f106  cmp     rax, rdi
0x18000f109  jnz     short loc_18000F0EC
0x18000f10b  cmp     r8w, [rax]
0x18000f10f  jz      short loc_18000F134
0x18000f111  mov     cs:dword_18002AAF8, 1
0x18000f11b  mov     rbx, [rsp+28h+arg_0]
0x18000f120  add     rsp, 20h
0x18000f124  pop     rdi
0x18000f125  retn
0x18000f126  mov     rcx, rax
0x18000f129  jmp     short loc_18000F10B
0x18000f12b  mov     rax, cs:qword_18002AAF0
0x18000f132  jmp     short loc_18000F11B
0x18000f134  lea     rax, [rcx+2]
0x18000f138  mov     cs:qword_18002AAF0, rax
0x18000f13f  jmp     short loc_18000F111
```
