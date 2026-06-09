# PmUpdateOffline(_DEVICE_EXTENSION *,uchar)

- ea: `0x14000bfa0`
- end: `0x14000bfc9`
- name: `?PmUpdateOffline@@YAXPEAU_DEVICE_EXTENSION@@E@Z`
- size: `41`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *, unsigned __int8)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x14000ab3c`

## callees

- `0x14000bfa0`

## pseudocode

```c
void __fastcall PmUpdateOffline(struct _DEVICE_EXTENSION *a1, char a2)
{
  char *v2; // r8
  char *i; // rcx
  int v4; // eax
  unsigned int v5; // eax

  v2 = (char *)a1 + 896;
  for ( i = (char *)*((_QWORD *)a1 + 112); i != v2; i = *(char **)i )
  {
    v4 = *((_DWORD *)i - 26);
    if ( a2 )
      v5 = v4 | 0x80;
    else
      v5 = v4 & 0xFFFFFF7F;
    *((_DWORD *)i - 26) = v5;
  }
}

```

## disassembly

```asm
0x14000bfa0  lea     r8, [rcx+380h]
0x14000bfa7  mov     rcx, [r8]
0x14000bfaa  jmp     short loc_14000BFC3
0x14000bfac  mov     eax, [rcx-68h]
0x14000bfaf  test    dl, dl
0x14000bfb1  jz      short loc_14000BFB9
0x14000bfb3  bts     eax, 7
0x14000bfb7  jmp     short loc_14000BFBD
0x14000bfb9  btr     eax, 7
0x14000bfbd  mov     [rcx-68h], eax
0x14000bfc0  mov     rcx, [rcx]
0x14000bfc3  cmp     rcx, r8
0x14000bfc6  jnz     short loc_14000BFAC
0x14000bfc8  retn
```
