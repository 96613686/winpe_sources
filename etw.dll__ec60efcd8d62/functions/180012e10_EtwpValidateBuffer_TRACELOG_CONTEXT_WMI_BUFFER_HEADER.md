# EtwpValidateBuffer(_TRACELOG_CONTEXT *,_WMI_BUFFER_HEADER *)

- ea: `0x180012e10`
- end: `0x180012e42`
- name: `?EtwpValidateBuffer@@YAEPEAU_TRACELOG_CONTEXT@@PEAU_WMI_BUFFER_HEADER@@@Z`
- size: `50`
- prototype: `bool __fastcall(struct _TRACELOG_CONTEXT *, struct _WMI_BUFFER_HEADER *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180010ed8`
- `0x18001118c`
- `0x180014b10`
- `0x180014e88`
- `0x18001502c`
- `0x180015328`

## callees

- `0x180012e10`

## pseudocode

```c
bool __fastcall EtwpValidateBuffer(struct _TRACELOG_CONTEXT *a1, struct _WMI_BUFFER_HEADER *a2)
{
  unsigned int v2; // eax

  if ( (*((_DWORD *)a1 + 27) & 0x4000000) != 0 )
  {
    if ( *(_DWORD *)a2 <= 0x48u )
      return 0;
    v2 = *((_DWORD *)a1 + 192);
    if ( *(_DWORD *)a2 > v2 )
      return 0;
  }
  else
  {
    v2 = *((_DWORD *)a1 + 192);
    if ( *(_DWORD *)a2 != v2 )
      return 0;
  }
  if ( *((_DWORD *)a2 + 12) < 0x48u )
    return 0;
  return *((_DWORD *)a2 + 12) <= v2;
}

```

## disassembly

```asm
0x180012e10  test    dword ptr [rcx+6Ch], 4000000h
0x180012e17  jz      short loc_180012E2B
0x180012e19  cmp     dword ptr [rdx], 48h ; 'H'
0x180012e1c  jbe     short loc_180012E28
0x180012e1e  mov     eax, [rcx+300h]
0x180012e24  cmp     [rdx], eax
0x180012e26  jbe     short loc_180012E35
0x180012e28  xor     al, al
0x180012e2a  retn
0x180012e2b  mov     eax, [rcx+300h]
0x180012e31  cmp     [rdx], eax
0x180012e33  jnz     short loc_180012E28
0x180012e35  cmp     dword ptr [rdx+30h], 48h ; 'H'
0x180012e39  jb      short loc_180012E28
0x180012e3b  cmp     [rdx+30h], eax
0x180012e3e  setbe   al
0x180012e41  retn
```
