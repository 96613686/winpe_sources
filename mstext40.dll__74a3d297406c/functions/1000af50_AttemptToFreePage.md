# AttemptToFreePage

- ea: `0x1000af50`
- end: `0x1000afce`
- name: `AttemptToFreePage`
- size: `126`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1000afd0`
- `0x1000b200`

## callees

- `0x1000af50`

## import_xrefs

- `KERNEL32!GlobalUnlock` at `0x1000afb3`
- `KERNEL32!GlobalUnlock` at `0x1000afb3`
- `KERNEL32!GlobalFree` at `0x1000afba`
- `KERNEL32!GlobalFree` at `0x1000afba`

## pseudocode

```c
int __stdcall AttemptToFreePage(int a1)
{
  int v1; // eax
  int v2; // edx
  int v3; // edx
  int v4; // edx
  void *v5; // esi

  if ( *(_DWORD *)(a1 + 4) != 8180 )
    return 0;
  v1 = dword_10040F6C;
  v2 = 0;
  if ( !dword_10040F6C )
    goto LABEL_7;
  do
  {
    if ( v1 == a1 )
      break;
    v2 = v1;
    v1 = *(_DWORD *)(v1 + 8);
  }
  while ( v1 );
  if ( v2 )
    *(_DWORD *)(v2 + 8) = *(_DWORD *)(a1 + 8);
  else
LABEL_7:
    dword_10040F6C = *(_DWORD *)(a1 + 8);
  v3 = *(_DWORD *)(a1 - 4);
  if ( v3 )
    *(_DWORD *)(v3 + 8) = *(_DWORD *)(a1 - 8);
  else
    dword_10040F70 = *(_DWORD *)(a1 - 8);
  v4 = *(_DWORD *)(a1 - 8);
  if ( v4 )
    *(_DWORD *)(v4 + 12) = *(_DWORD *)(a1 - 4);
  v5 = *(void **)(a1 - 16);
  if ( v5 )
  {
    GlobalUnlock(*(HGLOBAL *)(a1 - 16));
    GlobalFree(v5);
  }
  return 1;
}

```

## disassembly

```asm
0x1000af50  mov     ecx, [esp+arg_0]
0x1000af54  cmp     dword ptr [ecx+4], 1FF4h
0x1000af5b  jnz     short loc_1000AFC9
0x1000af5d  mov     eax, dword_10040F6C
0x1000af62  xor     edx, edx
0x1000af64  test    eax, eax
0x1000af66  jz      short loc_1000AF81
0x1000af68  cmp     eax, ecx
0x1000af6a  jz      short loc_1000AF75
0x1000af6c  mov     edx, eax
0x1000af6e  mov     eax, [eax+8]
0x1000af71  test    eax, eax
0x1000af73  jnz     short loc_1000AF68
0x1000af75  test    edx, edx
0x1000af77  jz      short loc_1000AF81
0x1000af79  mov     eax, [ecx+8]
0x1000af7c  mov     [edx+8], eax
0x1000af7f  jmp     short loc_1000AF89
0x1000af81  mov     eax, [ecx+8]
0x1000af84  mov     dword_10040F6C, eax
0x1000af89  mov     edx, [ecx-4]
0x1000af8c  mov     eax, [ecx-8]
0x1000af8f  test    edx, edx
0x1000af91  jz      short loc_1000AF98
0x1000af93  mov     [edx+8], eax
0x1000af96  jmp     short loc_1000AF9D
0x1000af98  mov     dword_10040F70, eax
0x1000af9d  mov     edx, [ecx-8]
0x1000afa0  test    edx, edx
0x1000afa2  jz      short loc_1000AFAA
0x1000afa4  mov     eax, [ecx-4]
0x1000afa7  mov     [edx+0Ch], eax
0x1000afaa  push    esi
0x1000afab  mov     esi, [ecx-10h]
0x1000afae  test    esi, esi
0x1000afb0  jz      short loc_1000AFC0
0x1000afb2  push    esi; hMem
0x1000afb3  call    ds:__imp__GlobalUnlock@4; GlobalUnlock(x)
0x1000afb9  push    esi; hMem
0x1000afba  call    ds:__imp__GlobalFree@4; GlobalFree(x)
0x1000afc0  mov     eax, 1
0x1000afc5  pop     esi
0x1000afc6  retn    4
0x1000afc9  xor     eax, eax
0x1000afcb  retn    4
```
