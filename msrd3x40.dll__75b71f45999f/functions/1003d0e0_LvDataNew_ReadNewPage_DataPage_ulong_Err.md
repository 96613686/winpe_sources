# LvDataNew::ReadNewPage(DataPage &,ulong,Err &)

- ea: `0x1003d0e0`
- end: `0x1003d15d`
- name: `?ReadNewPage@LvDataNew@@QAEXAAVDataPage@@KAAVErr@@@Z`
- size: `125`
- prototype: `void __thiscall(LvDataNew *__hidden this, struct DataPage *, unsigned int, struct Err *)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1003c7a0`
- `0x1003cc10`
- `0x1003e640`

## callees

- `0x1000eb60`
- `0x10023690`
- `0x10023730`
- `0x1003d0e0`

## pseudocode

```c
void __thiscall LvDataNew::ReadNewPage(LvDataNew *this, struct DataPage *a2, unsigned int a3, void **a4)
{
  bool v5; // cc
  int v6; // ecx
  int v7; // eax
  LvDataNew *v8; // [esp+10h] [ebp-4h]

  v5 = *((_DWORD *)this + 521) < 4;
  v6 = *((_DWORD *)this + 517);
  v8 = this;
  if ( v5 )
  {
    v7 = (*(int (__thiscall **)(_DWORD))(**(_DWORD **)(v6 + 8) + 56))(*(_DWORD *)(v6 + 8));
    Database::ReadPageForUpdate(*(Database **)(v7 + 16), a2, a3 >> 8, a4, *((struct Transaction **)v8 + 523), 0);
  }
  else
  {
    Database::ReadPage(
      *(Database **)(*(_DWORD *)(*(_DWORD *)(v6 + 8) + 40) + 8),
      a2,
      a3 >> 8,
      1,
      a4,
      *(struct Transaction **)(*(_DWORD *)(v6 + 8) + 40));
  }
}

```

## disassembly

```asm
0x1003d0e0  mov     edi, edi
0x1003d0e2  push    ebp
0x1003d0e3  mov     ebp, esp
0x1003d0e5  sub     esp, 8
0x1003d0e8  push    ebx
0x1003d0e9  mov     ebx, [ebp+arg_4]
0x1003d0ec  mov     eax, ecx
0x1003d0ee  push    esi; unsigned int
0x1003d0ef  shr     ebx, 8
0x1003d0f2  push    edi; void *
0x1003d0f3  cmp     dword ptr [eax+824h], 4
0x1003d0fa  mov     ecx, [eax+814h]
0x1003d100  mov     [ebp+var_4], eax
0x1003d103  jge     short loc_1003D13C
0x1003d105  mov     edi, [ecx+8]
0x1003d108  mov     eax, [edi]
0x1003d10a  mov     esi, [eax+38h]
0x1003d10d  mov     ecx, esi
0x1003d10f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003d115  mov     ecx, edi
0x1003d117  call    esi
0x1003d119  mov     ecx, [ebp+var_4]
0x1003d11c  push    0; char
0x1003d11e  push    dword ptr [ecx+82Ch]; struct Transaction *
0x1003d124  mov     ecx, [eax+10h]; this
0x1003d127  push    [ebp+arg_8]; struct Err *
0x1003d12a  push    ebx; unsigned int
0x1003d12b  push    [ebp+arg_0]; struct PageRef *
0x1003d12e  call    ?ReadPageForUpdate@Database@@QAEXAAVPageRef@@KAAVErr@@PAVTransaction@@I@Z; Database::ReadPageForUpdate(PageRef &,ulong,Err &,Transaction *,uint)
0x1003d133  pop     edi
0x1003d134  pop     esi
0x1003d135  pop     ebx
0x1003d136  mov     esp, ebp
0x1003d138  pop     ebp
0x1003d139  retn    0Ch
0x1003d13c  mov     eax, [ecx+8]
0x1003d13f  mov     ecx, [eax+28h]
0x1003d142  push    ecx; struct Transaction *
0x1003d143  push    [ebp+arg_8]; struct Err *
0x1003d146  mov     ecx, [ecx+8]; this
0x1003d149  push    1; char
0x1003d14b  push    ebx; unsigned int
0x1003d14c  push    [ebp+arg_0]; struct PageRef *
0x1003d14f  call    ?ReadPage@Database@@QAEXAAVPageRef@@KIAAVErr@@PAVTransaction@@@Z; Database::ReadPage(PageRef &,ulong,uint,Err &,Transaction *)
0x1003d154  pop     edi
0x1003d155  pop     esi
0x1003d156  pop     ebx
0x1003d157  mov     esp, ebp
0x1003d159  pop     ebp
0x1003d15a  retn    0Ch
```
