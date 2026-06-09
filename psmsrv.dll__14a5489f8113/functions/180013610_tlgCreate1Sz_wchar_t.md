# _tlgCreate1Sz_wchar_t

- ea: `0x180013610`
- end: `0x18001364f`
- name: `_tlgCreate1Sz_wchar_t`
- size: `63`
- prototype: `__int64 __fastcall(__int64, char *)`
- caller_count: `31`
- callee_count: `1`
- tags: ``

## callers

- `0x1800037f4`
- `0x1800047b0`
- `0x180004d80`
- `0x180004f08`
- `0x1800051bc`
- `0x1800056e8`
- `0x180005b0c`
- `0x180005ed0`
- `0x1800065a0`
- `0x180006b7c`
- `0x180006e28`
- `0x1800070e4`
- `0x18000a750`
- `0x18000b4d8`
- `0x18000defc`
- `0x18000e2cc`
- `0x18000e3d0`
- `0x180010e64`
- `0x180011074`
- `0x180011260`
- `0x1800139d0`
- `0x180014800`
- `0x180016544`
- `0x180016990`
- `0x180016ed0`
- `0x1800180d0`
- `0x1800184a0`
- `0x18001dc40`
- `0x180024c90`
- `0x1800252e0`
- `0x180025460`

## callees

- `0x180013610`

## pseudocode

```c
__int64 __fastcall tlgCreate1Sz_wchar_t(__int64 a1, char *a2)
{
  __int64 v2; // rax
  __int64 result; // rax

  if ( a2 )
  {
    v2 = -1;
    while ( *(_WORD *)&a2[2 * v2++ + 2] != 0 )
      ;
    result = (unsigned int)(2 * v2 + 2);
  }
  else
  {
    a2 = byte_180034900;
    result = 2;
  }
  *(_QWORD *)a1 = a2;
  *(_DWORD *)(a1 + 8) = result;
  *(_DWORD *)(a1 + 12) = 0;
  return result;
}

```

## disassembly

```asm
0x180013610  test    rdx, rdx
0x180013613  jz      short loc_180013641
0x180013615  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001361c  nop     dword ptr [rax+00h]
0x180013620  cmp     word ptr [rdx+rax*2+2], 0
0x180013626  lea     rax, [rax+1]
0x18001362a  jnz     short loc_180013620
0x18001362c  lea     eax, ds:2[rax*2]
0x180013633  mov     [rcx], rdx
0x180013636  mov     [rcx+8], eax
0x180013639  mov     dword ptr [rcx+0Ch], 0
0x180013640  retn
0x180013641  lea     rdx, byte_180034900
0x180013648  mov     eax, 2
0x18001364d  jmp     short loc_180013633
```
