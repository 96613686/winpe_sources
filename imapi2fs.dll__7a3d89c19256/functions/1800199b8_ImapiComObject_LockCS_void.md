# ImapiComObject::LockCS(void)

- ea: `0x1800199b8`
- end: `0x1800199d1`
- name: `?LockCS@ImapiComObject@@IEAAXXZ`
- size: `25`
- prototype: `void __fastcall(ImapiComObject *__hidden this)`
- caller_count: `163`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800072d0`
- `0x18000aeb0`
- `0x18000d200`
- `0x18000eac0`
- `0x18000fd90`
- `0x180010530`
- `0x1800106a0`
- `0x180010a30`
- `0x180010b9c`
- `0x180010ce0`
- `0x180011070`
- `0x180011200`
- `0x180011400`
- `0x1800115d0`
- `0x1800118b0`
- `0x180012ad0`
- `0x180012d00`
- `0x180012f30`
- `0x180013500`
- `0x180013750`
- `0x180019dd0`
- `0x18001ce80`
- `0x18001d530`
- `0x18001edd0`
- `0x18001ef40`
- `0x18001f0b0`
- `0x180020360`
- `0x180020550`
- `0x1800208a0`
- `0x180021d10`
- `0x18002a6c0`
- `0x18002a900`
- `0x18002aab0`
- `0x18002aca0`
- `0x18003afa0`
- `0x18003b0d0`
- `0x18003b140`
- `0x18003b530`
- `0x18003b660`
- `0x18003b6d0`
- `0x18003b7c0`
- `0x18003b820`
- `0x18003b970`
- `0x18003b9d0`
- `0x18003bb00`
- `0x18003c660`
- `0x18003c9f0`
- `0x18003cdc0`
- `0x18003d360`
- `0x18003d540`

## callees

- `0x1800199b8`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800199c6`
- `KERNEL32!EnterCriticalSection` at `0x1800199c6`

## pseudocode

```c
void __fastcall ImapiComObject::LockCS(ImapiComObject *this)
{
  if ( *((_BYTE *)this + 16) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x1800199b8  sub     rsp, 28h
0x1800199bc  cmp     byte ptr [rcx+10h], 0
0x1800199c0  jz      short loc_1800199CC
0x1800199c2  add     rcx, 18h; lpCriticalSection
0x1800199c6  call    cs:__imp_EnterCriticalSection
0x1800199cc  add     rsp, 28h
0x1800199d0  retn
```
