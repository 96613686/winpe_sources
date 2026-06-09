# DestroyUserPreferences

- ea: `0x18000929c`
- end: `0x180009360`
- name: `DestroyUserPreferences`
- size: `196`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180005d70`
- `0x180009918`
- `0x180009a30`
- `0x18000a0c4`

## callees

- `0x1800089c0`
- `0x18000929c`
- `0x18000aba4`
- `0x18000b0ce`

## pseudocode

```c
void *__fastcall DestroyUserPreferences(HGLOBAL *a1)
{
  void *result; // rax

  if ( a1 )
  {
    if ( *((_DWORD *)a1 + 44) )
    {
      DtlDestroyList(a1[9]);
      DtlDestroyList(a1[14]);
      DtlDestroyList(a1[15]);
      DtlDestroyList(a1[17]);
      DtlDestroyList(a1[18]);
      DtlDestroyList(a1[19]);
      Free0(a1[12]);
      Free0(a1[13]);
      Free0(a1[10]);
      Free0(a1[21]);
    }
    return memset_0(a1, 0, 0xB8u);
  }
  return result;
}

```

## disassembly

```asm
0x18000929c  test    rcx, rcx
0x18000929f  jz      locret_18000935F
0x1800092a5  push    rbx
0x1800092a6  sub     rsp, 20h
0x1800092aa  cmp     dword ptr [rcx+0B0h], 0
0x1800092b1  mov     rbx, rcx
0x1800092b4  jz      loc_18000934A
0x1800092ba  mov     rcx, [rcx+48h]; hMem
0x1800092be  lea     rdx, DestroyCallbackNode
0x1800092c5  call    DtlDestroyList
0x1800092ca  mov     rcx, [rbx+70h]; hMem
0x1800092ce  lea     rdx, DestroyPszNode
0x1800092d5  call    DtlDestroyList
0x1800092da  mov     rcx, [rbx+78h]; hMem
0x1800092de  lea     rdx, DestroyPszNode
0x1800092e5  call    DtlDestroyList
0x1800092ea  mov     rcx, [rbx+88h]; hMem
0x1800092f1  lea     rdx, DestroyPszNode
0x1800092f8  call    DtlDestroyList
0x1800092fd  mov     rcx, [rbx+90h]; hMem
0x180009304  lea     rdx, DestroyPszNode
0x18000930b  call    DtlDestroyList
0x180009310  mov     rcx, [rbx+98h]; hMem
0x180009317  lea     rdx, DestroyLocationNode
0x18000931e  call    DtlDestroyList
0x180009323  mov     rcx, [rbx+60h]
0x180009327  call    Free0
0x18000932c  mov     rcx, [rbx+68h]
0x180009330  call    Free0
0x180009335  mov     rcx, [rbx+50h]
0x180009339  call    Free0
0x18000933e  mov     rcx, [rbx+0A8h]
0x180009345  call    Free0
0x18000934a  xor     edx, edx; Val
0x18000934c  mov     r8d, 0B8h; Size
0x180009352  mov     rcx, rbx; void *
0x180009355  call    memset_0
0x18000935a  add     rsp, 20h
0x18000935e  pop     rbx
0x18000935f  retn
```
