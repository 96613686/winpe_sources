# myGetComputerNames(ushort * *,ushort * *)

- ea: `0x18001e2a4`
- end: `0x18001e353`
- name: `?myGetComputerNames@@YAJPEAPEAG0@Z`
- size: `175`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c15c`
- `0x18001e920`

## callees

- `0x18001e2a4`
- `0x180021438`
- `0x180029754`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e2d6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e2d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e336`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e336`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001e300`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001e300`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001e2f0`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001e32d`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001e2f0`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001e32d`

## pseudocode

```c
__int64 __fastcall myGetComputerNames(unsigned __int16 **a1, unsigned __int16 **a2)
{
  WCHAR *v4; // rax
  unsigned __int16 *v5; // rdi
  unsigned int v6; // ebx
  unsigned int MachineDnsName; // eax
  unsigned int v8; // ecx
  DWORD nSize; // [rsp+30h] [rbp+8h] BYREF

  *a2 = 0;
  *a1 = 0;
  nSize = 16;
  v4 = (WCHAR *)LocalAlloc(0, 0x20u);
  v5 = v4;
  if ( v4 )
  {
    if ( GetComputerNameW(v4, &nSize) )
    {
      MachineDnsName = myGetMachineDnsName(a1);
      v6 = MachineDnsName;
      if ( !MachineDnsName )
      {
        *a2 = v5;
        return v6;
      }
      v8 = 246284698;
    }
    else
    {
      MachineDnsName = myHLastError();
      v6 = MachineDnsName;
      v8 = 246022554;
    }
    CSPrintErrorLineFile(v8, MachineDnsName);
    LocalFree(v5);
  }
  else
  {
    v6 = -2147024882;
    CSPrintErrorLineFile(0xEA5019Au, -2147024882);
  }
  return v6;
}

```

## disassembly

```asm
0x18001e2a4  mov     [rsp+arg_8], rbx
0x18001e2a9  mov     [rsp+arg_10], rsi
0x18001e2ae  push    rdi
0x18001e2af  sub     rsp, 20h
0x18001e2b3  mov     rsi, rdx
0x18001e2b6  mov     qword ptr [rdx], 0
0x18001e2bd  mov     rbx, rcx
0x18001e2c0  mov     qword ptr [rcx], 0
0x18001e2c7  mov     edx, 20h ; ' '; uBytes
0x18001e2cc  mov     [rsp+28h+nSize], 10h
0x18001e2d4  xor     ecx, ecx; uFlags
0x18001e2d6  call    cs:__imp_LocalAlloc
0x18001e2dc  mov     rdi, rax
0x18001e2df  test    rax, rax
0x18001e2e2  jnz     short loc_18001E2F8
0x18001e2e4  mov     ebx, 8007000Eh
0x18001e2e9  mov     ecx, 0EA5019Ah
0x18001e2ee  mov     edx, ebx
0x18001e2f0  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001e2f6  jmp     short loc_18001E341
0x18001e2f8  lea     rdx, [rsp+28h+nSize]; nSize
0x18001e2fd  mov     rcx, rdi; lpBuffer
0x18001e300  call    cs:__imp_GetComputerNameW
0x18001e306  test    eax, eax
0x18001e308  jnz     short loc_18001E318
0x18001e30a  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001e30f  mov     ebx, eax
0x18001e311  mov     ecx, 0EAA019Ah
0x18001e316  jmp     short loc_18001E32B
0x18001e318  mov     rcx, rbx; unsigned __int16 **
0x18001e31b  call    ?myGetMachineDnsName@@YAJPEAPEAG@Z; myGetMachineDnsName(ushort * *)
0x18001e320  mov     ebx, eax
0x18001e322  test    eax, eax
0x18001e324  jz      short loc_18001E33E
0x18001e326  mov     ecx, 0EAE019Ah
0x18001e32b  mov     edx, eax
0x18001e32d  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001e333  mov     rcx, rdi; hMem
0x18001e336  call    cs:__imp_LocalFree
0x18001e33c  jmp     short loc_18001E341
0x18001e33e  mov     [rsi], rdi
0x18001e341  mov     rsi, [rsp+28h+arg_10]
0x18001e346  mov     eax, ebx
0x18001e348  mov     rbx, [rsp+28h+arg_8]
0x18001e34d  add     rsp, 20h
0x18001e351  pop     rdi
0x18001e352  retn
```
