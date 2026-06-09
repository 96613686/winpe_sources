# HidServSetPnP

- ea: `0x18000351c`
- end: `0x18000358b`
- name: `HidServSetPnP`
- size: `111`
- prototype: `int __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002910`
- `0x180002e40`

## callees

- `0x18000351c`
- `0x180006978`
- `0x1800070f0`

## import_xrefs

- `USER32!PostMessageW` at `0x180003550`

## pseudocode

```c
int __fastcall HidServSetPnP(__int64 a1)
{
  int result; // eax
  __int64 v2; // rdx
  __int64 *v3; // rdx
  __int64 v4; // rbx

  if ( (_DWORD)a1 )
  {
    if ( !PnpEnabled )
    {
      PnpEnabled = 1;
      return PostMessageW(hWndHidServ, 0x8136u, 0, 0);
    }
  }
  else
  {
    v2 = HidDeviceList;
    PnpEnabled = 0;
    if ( HidDeviceList )
    {
      do
      {
        RemoveEntryFromList(a1, v2);
        v4 = *v3;
        result = StopHidDevice(v3);
        v2 = v4;
      }
      while ( v4 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000351c  push    rbx
0x18000351e  sub     rsp, 20h
0x180003522  test    ecx, ecx
0x180003524  jz      short loc_180003557
0x180003526  cmp     cs:PnpEnabled, 0
0x18000352d  jnz     short loc_180003585
0x18000352f  mov     rcx, cs:hWndHidServ
0x180003536  xor     r9d, r9d
0x180003539  xor     r8d, r8d
0x18000353c  mov     cs:PnpEnabled, 1
0x180003546  mov     edx, 8136h
0x18000354b  add     rsp, 20h
0x18000354f  pop     rbx
0x180003550  jmp     cs:__imp_PostMessageW
0x180003557  mov     rdx, cs:HidDeviceList
0x18000355e  mov     cs:PnpEnabled, 0
0x180003568  test    rdx, rdx
0x18000356b  jz      short loc_180003585
0x18000356d  call    RemoveEntryFromList
0x180003572  mov     rbx, [rdx]
0x180003575  mov     rcx, rdx
0x180003578  call    StopHidDevice
0x18000357d  mov     rdx, rbx
0x180003580  test    rbx, rbx
0x180003583  jnz     short loc_18000356D
0x180003585  add     rsp, 20h
0x180003589  pop     rbx
0x18000358a  retn
```
