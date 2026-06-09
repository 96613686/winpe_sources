# myUuidCreate(_GUID *)

- ea: `0x180019544`
- end: `0x180019590`
- name: `?myUuidCreate@@YAXPEAU_GUID@@@Z`
- size: `76`
- prototype: `void __fastcall(LPFILETIME lpSystemTimeAsFileTime)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180017fa0`
- `0x180017fe0`

## callees

- `0x180019544`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180019568`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180019568`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019574`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019574`
- `RPCRT4!UuidCreate` at `0x180019557`
- `RPCRT4!UuidCreate` at `0x180019557`

## pseudocode

```c
void __fastcall myUuidCreate(LPFILETIME lpSystemTimeAsFileTime)
{
  LPFILETIME v2; // rdi
  LPFILETIME i; // rbx

  *(_OWORD *)&lpSystemTimeAsFileTime->dwLowDateTime = 0;
  if ( UuidCreate((UUID *)lpSystemTimeAsFileTime) )
  {
    v2 = lpSystemTimeAsFileTime + 2;
    GetSystemTimeAsFileTime(lpSystemTimeAsFileTime);
    for ( i = lpSystemTimeAsFileTime + 1; i < v2; i = (LPFILETIME)((char *)i + 4) )
      i->dwLowDateTime = GetTickCount();
  }
}

```

## disassembly

```asm
0x180019544  mov     [rsp+arg_0], rbx
0x180019549  push    rdi
0x18001954a  sub     rsp, 20h
0x18001954e  xorps   xmm0, xmm0
0x180019551  mov     rbx, rcx
0x180019554  movups  xmmword ptr [rcx], xmm0
0x180019557  call    cs:__imp_UuidCreate
0x18001955d  test    eax, eax
0x18001955f  jz      short loc_180019585
0x180019561  mov     rcx, rbx; lpSystemTimeAsFileTime
0x180019564  lea     rdi, [rbx+10h]
0x180019568  call    cs:__imp_GetSystemTimeAsFileTime
0x18001956e  add     rbx, 8
0x180019572  jmp     short loc_180019580
0x180019574  call    cs:__imp_GetTickCount
0x18001957a  mov     [rbx], eax
0x18001957c  add     rbx, 4
0x180019580  cmp     rbx, rdi
0x180019583  jb      short loc_180019574
0x180019585  mov     rbx, [rsp+28h+arg_0]
0x18001958a  add     rsp, 20h
0x18001958e  pop     rdi
0x18001958f  retn
```
