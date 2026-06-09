# CEfsService::SvcCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x1800031a0`
- end: `0x1800031eb`
- name: `?SvcCtrlHandler@CEfsService@@CAKKKPEAX0@Z`
- size: `75`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000314c`
- `0x1800031a0`

## import_xrefs

- `EFSCORE!EfsDllOnSessionChange` at `0x1800031d4`
- `EFSCORE!EfsDllOnSessionChange` at `0x1800031d4`
- `EFSCORE!EfsDllOnSessionUserChange` at `0x1800031c6`
- `EFSCORE!EfsDllOnSessionUserChange` at `0x1800031c6`

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
0x1800031a0  sub     rsp, 28h
0x1800031a4  mov     r10d, edx
0x1800031a7  mov     eax, 78h ; 'x'
0x1800031ac  test    r9, r9
0x1800031af  jz      short loc_1800031E6
0x1800031b1  sub     ecx, 1
0x1800031b4  jz      short loc_1800031DC
0x1800031b6  sub     ecx, 0Dh
0x1800031b9  jz      short loc_1800031CE
0x1800031bb  cmp     ecx, 13h
0x1800031be  jnz     short loc_1800031E4
0x1800031c0  mov     rdx, r8
0x1800031c3  mov     ecx, r10d
0x1800031c6  call    cs:__imp_EfsDllOnSessionUserChange
0x1800031cc  jmp     short loc_1800031E4
0x1800031ce  mov     rdx, r8
0x1800031d1  mov     ecx, r10d
0x1800031d4  call    cs:__imp_EfsDllOnSessionChange
0x1800031da  jmp     short loc_1800031E4
0x1800031dc  mov     rcx, r9; this
0x1800031df  call    ?StopService@CEfsService@@QEAAJXZ; CEfsService::StopService(void)
0x1800031e4  xor     eax, eax
0x1800031e6  add     rsp, 28h
0x1800031ea  retn
```
