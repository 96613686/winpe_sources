# mqwcslen(wchar_t const *)

- ea: `0x180004d20`
- end: `0x180004d5e`
- name: `?mqwcslen@@YAIPEB_W@Z`
- size: `62`
- prototype: `unsigned __int64 __fastcall(const wchar_t *)`
- caller_count: `56`
- callee_count: `2`
- tags: ``

## callers

- `0x180003460`
- `0x180003640`
- `0x180004d88`
- `0x180004dfc`
- `0x180004fc4`
- `0x180005078`
- `0x180005930`
- `0x180005c10`
- `0x180005df4`
- `0x180006a50`
- `0x180006bec`
- `0x180006ef0`
- `0x1800084d0`
- `0x18000897c`
- `0x180008d68`
- `0x180009420`
- `0x1800097c8`
- `0x180009bb0`
- `0x180009c74`
- `0x180009d2c`
- `0x180009df8`
- `0x180009ee4`
- `0x18000a03c`
- `0x18000a300`
- `0x18000aa80`
- `0x18000aea0`
- `0x18000b310`
- `0x18000b5e0`
- `0x18000b760`
- `0x18000bb20`
- `0x18000bda0`
- `0x18000c340`
- `0x18000c4b0`
- `0x18000ce94`
- `0x18000d520`
- `0x18000e994`
- `0x18000f290`
- `0x18000f310`
- `0x18001519c`
- `0x1800158cc`
- `0x18001dfc0`
- `0x18001e04c`
- `0x18001e8ae`
- `0x18001ecef`
- `0x18001ee86`
- `0x18001efb1`
- `0x18001f159`
- `0x18001f2e5`
- `0x18001f3e7`
- `0x18001f81b`

## callees

- `0x180001ce6`
- `0x180004d20`

## import_xrefs

- `msvcrt!??0exception@@QEAA@XZ` at `0x180004d41`
- `msvcrt!??0exception@@QEAA@XZ` at `0x180004d41`

## pseudocode

```c
unsigned __int64 __fastcall mqwcslen(const wchar_t *a1)
{
  unsigned __int64 result; // rax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  result = -1;
  do
    ++result;
  while ( a1[result] );
  if ( result > 0xFFFFFFFF )
  {
    exception::exception((exception *)pExceptionObject);
    throw (exception *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180004d20  sub     rsp, 48h
0x180004d24  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004d28  inc     rax
0x180004d2b  cmp     word ptr [rcx+rax*2], 0
0x180004d30  jnz     short loc_180004D28
0x180004d32  mov     ecx, 0FFFFFFFFh
0x180004d37  cmp     rax, rcx
0x180004d3a  jbe     short loc_180004D59
0x180004d3c  lea     rcx, [rsp+48h+pExceptionObject]
0x180004d41  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x180004d47  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x180004d4e  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180004d53  call    _CxxThrowException_0
0x180004d59  add     rsp, 48h
0x180004d5d  retn
```
