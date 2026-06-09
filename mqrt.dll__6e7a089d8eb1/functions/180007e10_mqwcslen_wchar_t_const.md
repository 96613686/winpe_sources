# mqwcslen(wchar_t const *)

- ea: `0x180007e10`
- end: `0x180007e4e`
- name: `?mqwcslen@@YAIPEB_W@Z`
- size: `62`
- prototype: `unsigned int __fastcall(const wchar_t *)`
- caller_count: `35`
- callee_count: `2`
- tags: ``

## callers

- `0x1800054a8`
- `0x180006790`
- `0x180008b7c`
- `0x180008d34`
- `0x180008f4c`
- `0x1800090f4`
- `0x1800094b4`
- `0x18000a364`
- `0x18000bbe0`
- `0x18000d3e4`
- `0x18000d520`
- `0x18000d580`
- `0x18000d74c`
- `0x18000fcf0`
- `0x1800138d4`
- `0x180013bdc`
- `0x180013c74`
- `0x180013d20`
- `0x180013dc8`
- `0x18001522c`
- `0x180016278`
- `0x180016944`
- `0x180017edc`
- `0x180019450`
- `0x180019ed4`
- `0x18001b5fc`
- `0x18001c188`
- `0x18001c688`
- `0x18001c914`
- `0x18001ca5c`
- `0x180021488`
- `0x180021e3c`
- `0x1800223fc`
- `0x18002259c`
- `0x180022eb4`

## callees

- `0x1800022d6`
- `0x180007e10`

## import_xrefs

- `msvcrt!??0exception@@QEAA@XZ` at `0x180007e31`
- `msvcrt!??0exception@@QEAA@XZ` at `0x180007e31`

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
0x180007e10  sub     rsp, 48h
0x180007e14  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007e18  inc     rax
0x180007e1b  cmp     word ptr [rcx+rax*2], 0
0x180007e20  jnz     short loc_180007E18
0x180007e22  mov     ecx, 0FFFFFFFFh
0x180007e27  cmp     rax, rcx
0x180007e2a  jbe     short loc_180007E49
0x180007e2c  lea     rcx, [rsp+48h+pExceptionObject]
0x180007e31  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x180007e37  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x180007e3e  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180007e43  call    _CxxThrowException_0
0x180007e49  add     rsp, 48h
0x180007e4d  retn
```
