# CheckForEndofHeaders(char *,ulong,ulong *)

- ea: `0x180008240`
- end: `0x180008298`
- name: `?CheckForEndofHeaders@@YAHPEADKPEAK@Z`
- size: `88`
- prototype: `__int64 __fastcall(char *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001d20`
- `0x180007d40`

## callees

- `0x180008240`

## pseudocode

```c
__int64 __fastcall CheckForEndofHeaders(char *a1, unsigned int a2, unsigned int *a3)
{
  __int64 v4; // r10
  unsigned int v5; // edx

  if ( a2 >= 2 )
  {
    if ( *a1 == 13 && a1[1] == 10 )
    {
      *a3 = 2;
      return 1;
    }
    v4 = 0;
    v5 = a2 - 2;
    while ( (unsigned int)v4 < v5 )
    {
      if ( a1[v4] == 10 && a1[(unsigned int)(v4 + 1)] == 13 && a1[(unsigned int)(v4 + 2)] == 10 )
      {
        *a3 = v4 + 3;
        return 1;
      }
      v4 = (unsigned int)(v4 + 1);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180008240  cmp     edx, 2
0x180008243  jb      short loc_180008295
0x180008245  cmp     byte ptr [rcx], 0Dh
0x180008248  jnz     short loc_18000825D
0x18000824a  cmp     byte ptr [rcx+1], 0Ah
0x18000824e  jnz     short loc_18000825D
0x180008250  mov     dword ptr [r8], 2
0x180008257  mov     eax, 1
0x18000825c  retn
0x18000825d  xor     r10d, r10d
0x180008260  add     edx, 0FFFFFFFEh
0x180008263  cmp     r10d, edx
0x180008266  jnb     short loc_180008295
0x180008268  cmp     byte ptr [r10+rcx], 0Ah
0x18000826d  jnz     short loc_180008283
0x18000826f  lea     eax, [r10+1]
0x180008273  cmp     byte ptr [rax+rcx], 0Dh
0x180008277  jnz     short loc_180008283
0x180008279  lea     eax, [r10+2]
0x18000827d  cmp     byte ptr [rax+rcx], 0Ah
0x180008281  jz      short loc_180008288
0x180008283  inc     r10d
0x180008286  jmp     short loc_180008263
0x180008288  lea     eax, [r10+3]
0x18000828c  mov     [r8], eax
0x18000828f  mov     eax, 1
0x180008294  retn
0x180008295  xor     eax, eax
0x180008297  retn
```
