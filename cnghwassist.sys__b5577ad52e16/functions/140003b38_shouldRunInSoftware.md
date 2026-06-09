# shouldRunInSoftware

- ea: `0x140003b38`
- end: `0x140003bba`
- name: `shouldRunInSoftware`
- size: `130`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140003268`
- `0x140003520`
- `0x1400037ec`

## callees

- `0x140003b38`

## import_xrefs

- `ntoskrnl!KeBugCheck` at `0x140003b51`
- `ntoskrnl!KeBugCheck` at `0x140003b51`

## pseudocode

```c
char __fastcall shouldRunInSoftware(__int64 *a1)
{
  unsigned int v1; // r9d
  __int64 v3; // r8
  char v4; // cl
  unsigned int v5; // edx
  unsigned int i; // r8d
  unsigned int v7; // r10d

  v1 = *((_DWORD *)a1 + 32);
  if ( v1 >= 0x20 )
    KeBugCheck(0x6C746166u);
  v3 = *a1;
  v4 = 1;
  v5 = *(_DWORD *)(v3 + 28);
  if ( g_nSwThreadsRunning >= v5 )
  {
    if ( v5 )
      goto LABEL_7;
    if ( (*((_DWORD *)a1 + 23) & 1) == 0 )
      return 0;
    v5 = *(_DWORD *)(v3 + 56);
    if ( g_nSwThreadsRunning >= v5 )
    {
LABEL_7:
      for ( i = g_maxPrioritySoftware; i >= v1; --i )
      {
        v7 = g_SwThreadsRunning[i];
        if ( v5 <= v7 )
          return 0;
        v5 -= v7;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x140003b38  sub     rsp, 28h
0x140003b3c  mov     r9d, [rcx+80h]
0x140003b43  mov     rax, rcx
0x140003b46  cmp     r9d, 20h ; ' '
0x140003b4a  jb      short loc_140003B5E
0x140003b4c  mov     ecx, 6C746166h; BugCheckCode
0x140003b51  call    cs:__imp_KeBugCheck
0x140003b5e  mov     r8, [rcx]
0x140003b61  mov     cl, 1
0x140003b63  mov     r10d, cs:g_nSwThreadsRunning
0x140003b6a  mov     edx, [r8+1Ch]
0x140003b6e  cmp     r10d, edx
0x140003b71  jb      short loc_140003BB2
0x140003b73  test    edx, edx
0x140003b75  jnz     short loc_140003B87
0x140003b77  mov     eax, [rax+5Ch]
0x140003b7a  test    cl, al
0x140003b7c  jz      short loc_140003BB0
0x140003b7e  mov     edx, [r8+38h]
0x140003b82  cmp     r10d, edx
0x140003b85  jb      short loc_140003BB2
0x140003b87  mov     r8d, cs:g_maxPrioritySoftware
0x140003b8e  jmp     short loc_140003BA9
0x140003b90  mov     eax, r8d
0x140003b93  lea     r10, g_SwThreadsRunning
0x140003b9a  mov     r10d, [r10+rax*4]
0x140003b9e  cmp     edx, r10d
0x140003ba1  jbe     short loc_140003BB0
0x140003ba3  sub     edx, r10d
0x140003ba6  dec     r8d
0x140003ba9  cmp     r8d, r9d
0x140003bac  jnb     short loc_140003B90
0x140003bae  jmp     short loc_140003BB2
0x140003bb0  xor     cl, cl
0x140003bb2  mov     al, cl
0x140003bb4  add     rsp, 28h
0x140003bb8  retn
```
