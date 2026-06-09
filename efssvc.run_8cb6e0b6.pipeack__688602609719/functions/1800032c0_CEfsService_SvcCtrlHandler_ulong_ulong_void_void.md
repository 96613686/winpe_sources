# CEfsService::SvcCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x1800032c0`
- end: `0x180003318`
- name: `?SvcCtrlHandler@CEfsService@@CAKKKPEAX0@Z`
- size: `88`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180003250`
- `0x1800032c0`

## import_xrefs

- `EFSCORE!EfsDllOnSessionChange` at `0x1800032fa`
- `EFSCORE!EfsDllOnSessionChange` at `0x1800032fa`
- `EFSCORE!EfsDllOnSessionUserChange` at `0x1800032e6`
- `EFSCORE!EfsDllOnSessionUserChange` at `0x1800032e6`

## pseudocode

```c
__int64 __fastcall CEfsService::SvcCtrlHandler(
        DWORD dwControl,
        DWORD dwEventType,
        LPVOID lpEventData,
        CEfsService *lpContext)
{
  __int64 result; // rax
  DWORD v5; // ecx
  DWORD v6; // ecx

  result = 120;
  if ( lpContext )
  {
    v5 = dwControl - 1;
    if ( v5 )
    {
      v6 = v5 - 13;
      if ( v6 )
      {
        if ( v6 == 19 )
          EfsDllOnSessionUserChange(dwEventType, lpEventData);
      }
      else
      {
        EfsDllOnSessionChange(dwEventType, lpEventData);
      }
    }
    else
    {
      CEfsService::StopService(lpContext);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800032c0  sub     rsp, 28h
0x1800032c4  mov     r10d, edx
0x1800032c7  mov     eax, 78h ; 'x'
0x1800032cc  test    r9, r9
0x1800032cf  jz      short loc_180003312
0x1800032d1  sub     ecx, 1
0x1800032d4  jz      short loc_180003308
0x1800032d6  sub     ecx, 0Dh
0x1800032d9  jz      short loc_1800032F4
0x1800032db  cmp     ecx, 13h
0x1800032de  jnz     short loc_180003310
0x1800032e0  mov     rdx, r8
0x1800032e3  mov     ecx, r10d
0x1800032e6  call    cs:__imp_EfsDllOnSessionUserChange
0x1800032ed  nop     dword ptr [rax+rax+00h]
0x1800032f2  jmp     short loc_180003310
0x1800032f4  mov     rdx, r8
0x1800032f7  mov     ecx, r10d
0x1800032fa  call    cs:__imp_EfsDllOnSessionChange
0x180003301  nop     dword ptr [rax+rax+00h]
0x180003306  jmp     short loc_180003310
0x180003308  mov     rcx, r9; this
0x18000330b  call    ?StopService@CEfsService@@QEAAJXZ; CEfsService::StopService(void)
0x180003310  xor     eax, eax
0x180003312  add     rsp, 28h
0x180003316  retn
```
