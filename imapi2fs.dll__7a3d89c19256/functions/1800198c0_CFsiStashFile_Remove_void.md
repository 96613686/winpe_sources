# CFsiStashFile::Remove(void)

- ea: `0x1800198c0`
- end: `0x180019983`
- name: `?Remove@CFsiStashFile@@QEAAXXZ`
- size: `195`
- prototype: `void __fastcall(CFsiStashFile *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180019058`

## callees

- `0x1800198c0`
- `0x180028568`
- `0x18002f228`

## import_xrefs

- `msvcrt!_wremove` at `0x180019945`
- `msvcrt!_wremove` at `0x180019945`

## pseudocode

```c
void __fastcall CFsiStashFile::Remove(CFsiStashFile *this)
{
  PVOID *v2; // rcx

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, &WPP_edf0fa5e3dfd39844942028c14a38019_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 2) - 16LL) )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 68) & 4) != 0 && *((_BYTE *)v2 + 65) >= 4u )
      WPP_SF_SS(
        (unsigned int)v2[7],
        18,
        (unsigned int)&WPP_edf0fa5e3dfd39844942028c14a38019_Traceguids,
        *((_QWORD *)this + 1),
        *((_QWORD *)this + 2));
    _wremove(*((const wchar_t **)this + 2));
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 68) & 8) != 0 && *((_BYTE *)v2 + 65) >= 5u )
    WPP_SF_(v2[7], 19, &WPP_edf0fa5e3dfd39844942028c14a38019_Traceguids);
}

```

## disassembly

```asm
0x1800198c0  mov     [rsp+arg_0], rbx
0x1800198c5  push    rdi
0x1800198c6  sub     rsp, 30h
0x1800198ca  mov     rbx, rcx
0x1800198cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800198d4  lea     rdi, WPP_GLOBAL_Control
0x1800198db  cmp     rcx, rdi
0x1800198de  jz      short loc_180019908
0x1800198e0  test    byte ptr [rcx+44h], 8
0x1800198e4  jz      short loc_180019908
0x1800198e6  cmp     byte ptr [rcx+41h], 5
0x1800198ea  jb      short loc_180019908
0x1800198ec  mov     rcx, [rcx+38h]
0x1800198f0  lea     r8, WPP_edf0fa5e3dfd39844942028c14a38019_Traceguids
0x1800198f7  mov     edx, 11h
0x1800198fc  call    WPP_SF_
0x180019901  mov     rcx, cs:WPP_GLOBAL_Control
0x180019908  mov     rax, [rbx+10h]
0x18001990c  cmp     dword ptr [rax-10h], 0
0x180019910  jz      short loc_180019952
0x180019912  cmp     rcx, rdi
0x180019915  jz      short loc_180019941
0x180019917  test    byte ptr [rcx+44h], 4
0x18001991b  jz      short loc_180019941
0x18001991d  cmp     byte ptr [rcx+41h], 4
0x180019921  jb      short loc_180019941
0x180019923  mov     r9, [rbx+8]
0x180019927  lea     r8, WPP_edf0fa5e3dfd39844942028c14a38019_Traceguids
0x18001992e  mov     rcx, [rcx+38h]
0x180019932  mov     edx, 12h
0x180019937  mov     [rsp+38h+var_18], rax
0x18001993c  call    WPP_SF_SS
0x180019941  mov     rcx, [rbx+10h]; FileName
0x180019945  call    cs:__imp__wremove
0x18001994b  mov     rcx, cs:WPP_GLOBAL_Control
0x180019952  cmp     rcx, rdi
0x180019955  jz      short loc_180019978
0x180019957  test    byte ptr [rcx+44h], 8
0x18001995b  jz      short loc_180019978
0x18001995d  cmp     byte ptr [rcx+41h], 5
0x180019961  jb      short loc_180019978
0x180019963  mov     rcx, [rcx+38h]
0x180019967  lea     r8, WPP_edf0fa5e3dfd39844942028c14a38019_Traceguids
0x18001996e  mov     edx, 13h
0x180019973  call    WPP_SF_
0x180019978  mov     rbx, [rsp+38h+arg_0]
0x18001997d  add     rsp, 30h
0x180019981  pop     rdi
0x180019982  retn
```
