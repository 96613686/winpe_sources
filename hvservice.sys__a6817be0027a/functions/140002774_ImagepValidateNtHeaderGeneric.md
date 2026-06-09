# ImagepValidateNtHeaderGeneric

- ea: `0x140002774`
- end: `0x1400027b8`
- name: `ImagepValidateNtHeaderGeneric`
- size: `68`
- prototype: `char __fastcall(__int64, unsigned __int64, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002534`
- `0x140002654`

## callees

- `0x140002774`

## pseudocode

```c
char __fastcall ImagepValidateNtHeaderGeneric(__int64 a1, unsigned __int64 a2, unsigned __int64 *a3)
{
  char v3; // r10
  unsigned __int64 v4; // r9

  v3 = 0;
  *a3 = 0;
  if ( a2 >= 2 && *(_WORD *)a1 == 23117 )
  {
    v4 = *(int *)(a1 + 60);
    if ( v4 < 0x10000000 && v4 + 26 <= a2 && *(_DWORD *)(v4 + a1) == 17744 )
    {
      v3 = 1;
      *a3 = v4;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x140002774  xor     r10b, r10b
0x140002777  mov     qword ptr [r8], 0
0x14000277e  cmp     rdx, 2
0x140002782  jb      short loc_1400027B4
0x140002784  mov     eax, 5A4Dh
0x140002789  cmp     [rcx], ax
0x14000278c  jnz     short loc_1400027B4
0x14000278e  movsxd  r9, dword ptr [rcx+3Ch]
0x140002792  cmp     r9, 10000000h
0x140002799  jnb     short loc_1400027B4
0x14000279b  lea     rax, [r9+1Ah]
0x14000279f  cmp     rax, rdx
0x1400027a2  ja      short loc_1400027B4
0x1400027a4  cmp     dword ptr [r9+rcx], 4550h
0x1400027ac  jnz     short loc_1400027B4
0x1400027ae  mov     r10b, 1
0x1400027b1  mov     [r8], r9
0x1400027b4  mov     al, r10b
0x1400027b7  retn
```
