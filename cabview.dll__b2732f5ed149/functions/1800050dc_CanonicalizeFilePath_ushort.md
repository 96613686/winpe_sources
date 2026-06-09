# CanonicalizeFilePath(ushort *)

- ea: `0x1800050dc`
- end: `0x180005129`
- name: `?CanonicalizeFilePath@@YAXPEAG@Z`
- size: `77`
- prototype: `void __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004a70`
- `0x180004d90`

## callees

- `0x1800050dc`

## import_xrefs

- `SHLWAPI!__imp_PathIsValidCharW` at `0x180005103`
- `SHLWAPI!__imp_PathIsValidCharW` at `0x180005103`

## pseudocode

```c
void __fastcall CanonicalizeFilePath(unsigned __int16 *a1)
{
  unsigned __int16 *v1; // rbx
  unsigned __int16 i; // ax

  v1 = a1;
  for ( i = *a1; i; i = *v1 )
  {
    if ( i == 47 )
    {
      *v1 = 92;
    }
    else if ( !(unsigned int)PathIsValidCharW(i, 508) )
    {
      *v1 = 95;
    }
    ++v1;
  }
}

```

## disassembly

```asm
0x1800050dc  mov     [rsp+arg_0], rbx
0x1800050e1  push    rdi
0x1800050e2  sub     rsp, 20h
0x1800050e6  mov     rbx, rcx
0x1800050e9  movzx   eax, word ptr [rcx]
0x1800050ec  jmp     short loc_180005119
0x1800050ee  cmp     ax, 2Fh ; '/'
0x1800050f2  jnz     short loc_1800050FB
0x1800050f4  mov     word ptr [rbx], 5Ch ; '\'
0x1800050f9  jmp     short loc_180005112
0x1800050fb  mov     edx, 1FCh
0x180005100  movzx   ecx, ax
0x180005103  call    cs:__imp_PathIsValidCharW
0x180005109  test    eax, eax
0x18000510b  jnz     short loc_180005112
0x18000510d  mov     word ptr [rbx], 5Fh ; '_'
0x180005112  add     rbx, 2
0x180005116  movzx   eax, word ptr [rbx]
0x180005119  test    ax, ax
0x18000511c  jnz     short loc_1800050EE
0x18000511e  mov     rbx, [rsp+28h+arg_0]
0x180005123  add     rsp, 20h
0x180005127  pop     rdi
0x180005128  retn
```
