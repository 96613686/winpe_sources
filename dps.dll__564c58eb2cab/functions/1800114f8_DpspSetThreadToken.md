# DpspSetThreadToken

- ea: `0x1800114f8`
- end: `0x18001157a`
- name: `DpspSetThreadToken`
- size: `130`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800118f0`
- `0x180011c6c`

## callees

- `0x180009090`
- `0x1800114f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011532`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011532`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011528`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011528`

## string_xrefs

- `0x18001155f`: `DpspSetThreadToken`

## pseudocode

```c
__int64 __fastcall DpspSetThreadToken(__int64 a1)
{
  signed int Args; // ebx
  void *v2; // rdx
  signed int LastError; // eax

  if ( a1 )
  {
    v2 = *(void **)(a1 + 800);
    Args = 0;
    if ( v2 && !SetThreadToken(0, v2) )
    {
      LastError = GetLastError();
      Args = LastError;
      if ( LastError > 0 )
        Args = (unsigned __int16)LastError | 0x80070000;
      if ( Args < 0 )
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpssrv.cpp",
          (int)L"DpspSetThreadToken",
          166,
          (int)L"Error = %d",
          Args);
    }
  }
  else
  {
    Args = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpssrv.cpp",
      (int)L"DpspSetThreadToken",
      158,
      (int)L"Error = %d",
      87);
  }
  return (unsigned int)Args;
}

```

## disassembly

```asm
0x1800114f8  push    rbx
0x1800114fa  sub     rsp, 30h
0x1800114fe  test    rcx, rcx
0x180011501  jnz     short loc_180011518
0x180011503  mov     ebx, 80070057h
0x180011508  mov     dword ptr [rsp+38h+Args], 57h ; 'W'
0x180011510  mov     r8d, 9Eh
0x180011516  jmp     short loc_180011558
0x180011518  mov     rdx, [rcx+320h]; Token
0x18001151f  xor     ebx, ebx
0x180011521  test    rdx, rdx
0x180011524  jz      short loc_180011572
0x180011526  xor     ecx, ecx; Thread
0x180011528  call    cs:__imp_SetThreadToken
0x18001152e  test    eax, eax
0x180011530  jnz     short loc_180011572
0x180011532  call    cs:__imp_GetLastError
0x180011538  mov     ebx, eax
0x18001153a  test    eax, eax
0x18001153c  jle     short loc_180011547
0x18001153e  movzx   ebx, ax
0x180011541  or      ebx, 80070000h
0x180011547  test    ebx, ebx
0x180011549  jns     short loc_180011572
0x18001154b  movzx   ecx, bx
0x18001154e  mov     r8d, 0A6h; int
0x180011554  mov     dword ptr [rsp+38h+Args], ecx; Args
0x180011558  lea     r9, aErrorD; "Error = %d"
0x18001155f  lea     rdx, aDpspsetthreadt; "DpspSetThreadToken"
0x180011566  lea     rcx, aClientcoreBase_5; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18001156d  call    WdipTraceError
0x180011572  mov     eax, ebx
0x180011574  add     rsp, 30h
0x180011578  pop     rbx
0x180011579  retn
```
