# CCabFolder::MessageSFVCB(uint,unsigned __int64,__int64)

- ea: `0x18000ee40`
- end: `0x18000ee82`
- name: `?MessageSFVCB@CCabFolder@@UEAAJI_K_J@Z`
- size: `66`
- prototype: `__int64 __fastcall(CCabFolder *__hidden this, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000ee40`

## import_xrefs

- `SHELL32!__imp_Create_IEnumUICommand` at `0x18000ee6f`
- `SHELL32!__imp_Create_IEnumUICommand` at `0x18000ee6f`

## pseudocode

```c
__int64 __fastcall CCabFolder::MessageSFVCB(CCabFolder *this, int a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax

  if ( a2 == 46 )
  {
    *((_QWORD *)this + 7) = a4;
  }
  else
  {
    result = 2147500033LL;
    if ( a2 != 84 )
      return result;
    *(_OWORD *)a4 = 0;
    *(_QWORD *)(a4 + 16) = 0;
    Create_IEnumUICommand((char *)this - 16, &off_180014230, 2);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ee40  sub     rsp, 28h
0x18000ee44  cmp     edx, 2Eh ; '.'
0x18000ee47  jz      short loc_18000EE77
0x18000ee49  mov     eax, 80004001h
0x18000ee4e  cmp     edx, 54h ; 'T'
0x18000ee51  jnz     short loc_18000EE7D
0x18000ee53  xorps   xmm0, xmm0
0x18000ee56  lea     r8d, [rdx-52h]
0x18000ee5a  xor     eax, eax
0x18000ee5c  lea     rdx, off_180014230
0x18000ee63  movups  xmmword ptr [r9], xmm0
0x18000ee67  add     rcx, 0FFFFFFFFFFFFFFF0h
0x18000ee6b  mov     [r9+10h], rax
0x18000ee6f  call    cs:__imp_Create_IEnumUICommand
0x18000ee75  jmp     short loc_18000EE7B
0x18000ee77  mov     [rcx+38h], r9
0x18000ee7b  xor     eax, eax
0x18000ee7d  add     rsp, 28h
0x18000ee81  retn
```
