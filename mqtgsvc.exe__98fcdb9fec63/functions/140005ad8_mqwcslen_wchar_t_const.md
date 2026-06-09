# mqwcslen(wchar_t const *)

- ea: `0x140005ad8`
- end: `0x140005b16`
- name: `?mqwcslen@@YAIPEB_W@Z`
- size: `62`
- prototype: `unsigned __int64 __fastcall(const wchar_t *)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x140003f54`
- `0x140005b38`
- `0x140007594`
- `0x14000761c`
- `0x14000a5fc`
- `0x14000f068`
- `0x140015a60`
- `0x140018f98`
- `0x14001a2f0`
- `0x14001c2d4`

## callees

- `0x140001cc6`
- `0x140005ad8`

## import_xrefs

- `msvcrt!??0exception@@QEAA@XZ` at `0x140005af9`
- `msvcrt!??0exception@@QEAA@XZ` at `0x140005af9`

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
0x140005ad8  sub     rsp, 48h
0x140005adc  or      rax, 0FFFFFFFFFFFFFFFFh
0x140005ae0  inc     rax
0x140005ae3  cmp     word ptr [rcx+rax*2], 0
0x140005ae8  jnz     short loc_140005AE0
0x140005aea  mov     ecx, 0FFFFFFFFh
0x140005aef  cmp     rax, rcx
0x140005af2  jbe     short loc_140005B11
0x140005af4  lea     rcx, [rsp+48h+pExceptionObject]
0x140005af9  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x140005aff  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x140005b06  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140005b0b  call    _CxxThrowException_0
0x140005b11  add     rsp, 48h
0x140005b15  retn
```
