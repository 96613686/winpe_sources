# FIFileInfoStateChange

- ea: `0x140014940`
- end: `0x1400149d9`
- name: `FIFileInfoStateChange`
- size: `153`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x14000d5cc`
- `0x1400148cc`
- `0x140018078`

## callees

- `0x140001da0`
- `0x140001f20`
- `0x14000df58`
- `0x140014940`

## pseudocode

```c
__int64 __fastcall FIFileInfoStateChange(int a1, int a2)
{
  int v2; // ebx
  unsigned int v4; // edi
  int v5; // edx
  int v6; // edx

  v2 = 0;
  v4 = 1;
  if ( a2 )
  {
    v5 = a2 - 1;
    if ( v5 )
    {
      v6 = v5 - 1;
      if ( v6 )
      {
        if ( v6 == 1 )
          v2 = 16;
      }
      else
      {
        v2 = 4;
      }
    }
    else
    {
      v2 = 2;
    }
  }
  else
  {
    v2 = 1;
  }
  FILockExclusiveAcquire((__int64)&qword_140009A78);
  if ( a1 == 1 )
  {
    if ( (dword_140009A74 & v2) == 0 )
    {
      dword_140009A70 = 1;
      dword_140009A74 |= v2;
      goto LABEL_16;
    }
LABEL_13:
    v4 = 0;
    goto LABEL_16;
  }
  if ( (dword_140009A74 & v2) == 0 )
    goto LABEL_13;
  dword_140009A74 &= ~v2;
  if ( !dword_140009A74 )
  {
    FIReleaseFileInfos();
    dword_140009A70 = 0;
  }
LABEL_16:
  FILockExclusiveRelease((__int64)&qword_140009A78);
  return v4;
}

```

## disassembly

```asm
0x140014940  push    rbx
0x140014942  push    rbp
0x140014943  push    rsi
0x140014944  push    rdi
0x140014945  sub     rsp, 28h
0x140014949  xor     ebx, ebx
0x14001494b  mov     ebp, ecx
0x14001494d  lea     edi, [rbx+1]
0x140014950  test    edx, edx
0x140014952  jz      short loc_140014973
0x140014954  sub     edx, edi
0x140014956  jz      short loc_14001496C
0x140014958  sub     edx, edi
0x14001495a  jz      short loc_140014965
0x14001495c  cmp     edx, edi
0x14001495e  jnz     short loc_140014975
0x140014960  lea     ebx, [rdi+0Fh]
0x140014963  jmp     short loc_140014975
0x140014965  mov     ebx, 4
0x14001496a  jmp     short loc_140014975
0x14001496c  mov     ebx, 2
0x140014971  jmp     short loc_140014975
0x140014973  mov     ebx, edi
0x140014975  lea     rsi, qword_140009A78
0x14001497c  mov     rcx, rsi
0x14001497f  call    FILockExclusiveAcquire
0x140014984  mov     eax, cs:dword_140009A74
0x14001498a  cmp     ebp, edi
0x14001498c  jnz     short loc_1400149A2
0x14001498e  test    ebx, eax
0x140014990  jnz     short loc_1400149A6
0x140014992  or      eax, ebx
0x140014994  mov     cs:dword_140009A70, edi
0x14001499a  mov     cs:dword_140009A74, eax
0x1400149a0  jmp     short loc_1400149C5
0x1400149a2  test    ebx, eax
0x1400149a4  jnz     short loc_1400149AA
0x1400149a6  xor     edi, edi
0x1400149a8  jmp     short loc_1400149C5
0x1400149aa  not     ebx
0x1400149ac  and     eax, ebx
0x1400149ae  mov     cs:dword_140009A74, eax
0x1400149b4  jnz     short loc_1400149C5
0x1400149b6  call    FIReleaseFileInfos
0x1400149bb  mov     cs:dword_140009A70, 0
0x1400149c5  mov     rcx, rsi
0x1400149c8  call    FILockExclusiveRelease
0x1400149cd  mov     eax, edi
0x1400149cf  add     rsp, 28h
0x1400149d3  pop     rdi
0x1400149d4  pop     rsi
0x1400149d5  pop     rbp
0x1400149d6  pop     rbx
0x1400149d7  retn
```
