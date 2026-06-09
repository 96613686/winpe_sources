# ICGetInfo

- ea: `0x180002df0`
- end: `0x180002e85`
- name: `ICGetInfo`
- size: `149`
- prototype: `LONG_PTR __stdcall(HIC hic, ICINFO *picinfo, DWORD cb)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002e90`
- `0x1800047f0`
- `0x1800065e0`
- `0x1800076c4`

## callees

- `0x180002df0`
- `0x180003a60`
- `0x180003ae4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180002e62`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180002e62`
- `WINMM!GetDriverModuleHandle` at `0x180002e50`
- `WINMM!GetDriverModuleHandle` at `0x180002e50`

## pseudocode

```c
LONG_PTR __stdcall ICGetInfo(HIC hic, ICINFO *picinfo, DWORD cb)
{
  DWORD_PTR v3; // rsi
  __int64 v7; // rcx
  __int64 v8; // r9
  HDRVR v9; // rcx
  HMODULE DriverModuleHandle; // rax

  v3 = cb;
  if ( cb < 0x238 )
    return 0;
  if ( !(unsigned int)ICValid(hic) )
    return -8;
  *(_QWORD *)&picinfo->dwSize = v8;
  picinfo->szDriver[0] = 0;
  *(_QWORD *)&picinfo->fccHandler = 0;
  picinfo->dwVersionICM = 260;
  picinfo->dwVersion = 0;
  picinfo->szDescription[0] = 0;
  picinfo->szName[0] = 0;
  v9 = *(HDRVR *)(v7 + 24);
  if ( v9 )
  {
    DriverModuleHandle = GetDriverModuleHandle(v9);
    GetModuleFileNameW(DriverModuleHandle, picinfo->szDriver, 0x80u);
  }
  return ICSendMessage(hic, 0x5002u, (DWORD_PTR)picinfo, v3);
}

```

## disassembly

```asm
0x180002df0  push    rbx
0x180002df2  push    rsi
0x180002df3  push    rdi
0x180002df4  push    r14
0x180002df6  sub     rsp, 28h
0x180002dfa  mov     r9d, 238h
0x180002e00  mov     esi, r8d
0x180002e03  mov     rbx, rdx
0x180002e06  mov     rdi, rcx
0x180002e09  cmp     r8d, r9d
0x180002e0c  jnb     short loc_180002E12
0x180002e0e  xor     eax, eax
0x180002e10  jmp     short loc_180002E7B
0x180002e12  call    ICValid
0x180002e17  xor     edx, edx
0x180002e19  test    eax, eax
0x180002e1b  jnz     short loc_180002E23
0x180002e1d  lea     rax, [rdx-8]
0x180002e21  jmp     short loc_180002E7B
0x180002e23  lea     r14, [rbx+138h]
0x180002e2a  mov     [rbx], r9
0x180002e2d  mov     [r14], dx
0x180002e31  mov     [rbx+8], rdx
0x180002e35  mov     dword ptr [rbx+14h], 104h
0x180002e3c  mov     [rbx+10h], edx
0x180002e3f  mov     [rbx+38h], dx
0x180002e43  mov     [rbx+18h], dx
0x180002e47  mov     rcx, [rcx+18h]; hDriver
0x180002e4b  test    rcx, rcx
0x180002e4e  jz      short loc_180002E68
0x180002e50  call    cs:__imp_GetDriverModuleHandle
0x180002e56  mov     r8d, 80h; nSize
0x180002e5c  mov     rdx, r14; lpFilename
0x180002e5f  mov     rcx, rax; hModule
0x180002e62  call    cs:__imp_GetModuleFileNameW
0x180002e68  mov     r9, rsi; dw2
0x180002e6b  mov     r8, rbx; dw1
0x180002e6e  mov     edx, 5002h; msg
0x180002e73  mov     rcx, rdi; hic
0x180002e76  call    ICSendMessage
0x180002e7b  add     rsp, 28h
0x180002e7f  pop     r14
0x180002e81  pop     rdi
0x180002e82  pop     rsi
0x180002e83  pop     rbx
0x180002e84  retn
```
