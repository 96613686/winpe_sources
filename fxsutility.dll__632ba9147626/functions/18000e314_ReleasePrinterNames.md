# ReleasePrinterNames

- ea: `0x18000e314`
- end: `0x18000e3ab`
- name: `ReleasePrinterNames`
- size: `151`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000dfe4`
- `0x180010600`
- `0x18001067c`

## callees

- `0x180005eac`
- `0x180006318`
- `0x18000e314`

## pseudocode

```c
void __fastcall ReleasePrinterNames(LPVOID *lpMem, unsigned int a2)
{
  unsigned int v4; // ebp
  __int64 v5; // r14
  void *v6; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x28u, (const GUID *)WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids);
  }
  if ( a2 )
  {
    v4 = 0;
    v5 = 0;
    do
    {
      pMemFree(lpMem[2 * v5]);
      v6 = lpMem[2 * v5 + 1];
      lpMem[2 * v5] = 0;
      pMemFree(v6);
      ++v4;
      lpMem[2 * v5++ + 1] = 0;
    }
    while ( v4 < a2 );
    pMemFree(lpMem);
  }
}

```

## disassembly

```asm
0x18000e314  push    rbx
0x18000e316  push    rbp
0x18000e317  push    rsi
0x18000e318  push    rdi
0x18000e319  push    r14
0x18000e31b  sub     rsp, 20h
0x18000e31f  mov     esi, edx
0x18000e321  mov     rdi, rcx
0x18000e324  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e32b  lea     rax, WPP_GLOBAL_Control
0x18000e332  cmp     rcx, rax
0x18000e335  jz      short loc_18000E358
0x18000e337  test    byte ptr [rcx+1Ch], 2
0x18000e33b  jz      short loc_18000E358
0x18000e33d  cmp     byte ptr [rcx+19h], 5
0x18000e341  jb      short loc_18000E358
0x18000e343  mov     rcx, [rcx+10h]
0x18000e347  lea     r8, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids
0x18000e34e  mov     edx, 28h ; '('
0x18000e353  call    WPP_SF_
0x18000e358  test    esi, esi
0x18000e35a  jz      short loc_18000E3A0
0x18000e35c  xor     ebp, ebp
0x18000e35e  test    esi, esi
0x18000e360  jz      short loc_18000E398
0x18000e362  xor     r14d, r14d
0x18000e365  mov     rbx, r14
0x18000e368  add     rbx, rbx
0x18000e36b  mov     rcx, [rdi+rbx*8]; lpMem
0x18000e36f  call    pMemFree
0x18000e374  mov     rcx, [rdi+rbx*8+8]; lpMem
0x18000e379  mov     qword ptr [rdi+rbx*8], 0
0x18000e381  call    pMemFree
0x18000e386  inc     ebp
0x18000e388  mov     qword ptr [rdi+rbx*8+8], 0
0x18000e391  inc     r14
0x18000e394  cmp     ebp, esi
0x18000e396  jb      short loc_18000E365
0x18000e398  mov     rcx, rdi; lpMem
0x18000e39b  call    pMemFree
0x18000e3a0  add     rsp, 20h
0x18000e3a4  pop     r14
0x18000e3a6  pop     rdi
0x18000e3a7  pop     rsi
0x18000e3a8  pop     rbp
0x18000e3a9  pop     rbx
0x18000e3aa  retn
```
