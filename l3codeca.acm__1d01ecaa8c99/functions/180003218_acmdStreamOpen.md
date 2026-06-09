# acmdStreamOpen

- ea: `0x180003218`
- end: `0x180003303`
- name: `acmdStreamOpen`
- size: `235`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800036c0`

## callees

- `0x1800027dc`
- `0x180003218`
- `0x180003588`
- `0x1800035e8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800032d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800032d4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000326d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000326d`

## pseudocode

```c
__int64 __fastcall acmdStreamOpen(__int64 a1, __int64 a2)
{
  _WORD *v3; // rcx
  __int64 v5; // r11
  __int64 (__fastcall **v6)(__int64, __int64); // rsi
  __int64 v8; // rbx
  __int64 v9; // r11

  v3 = *(_WORD **)(a2 + 4);
  if ( *v3 == 1 )
  {
    if ( (unsigned int)((__int64 (*)(void))pcmIsValidFormat)() )
      l3audioIsValidFormat(v9);
  }
  else if ( *v3 == 85 && (unsigned int)l3audioIsValidFormat(v3) && (unsigned int)pcmIsValidFormat(v5) )
  {
    v6 = (__int64 (__fastcall **)(__int64, __int64))LocalAlloc(0x40u, 0x30u);
    if ( !v6 )
      return 7;
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 60));
    v6[2] = 0;
    *v6 = l3audioDecode;
    v6[3] = 0;
    *(_DWORD *)(a2 + 48) = 0;
    *(_QWORD *)(a2 + 52) = v6;
    if ( *v6 == l3audioDecode )
    {
      v8 = l3audioDecodeOpenStream(a1, a2);
      if ( !v8 && (*(_DWORD *)(a2 + 44) & 1) == 0 )
        return v8;
    }
    else
    {
      v8 = 512;
    }
    LocalFree(v6);
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 60));
    return v8;
  }
  return 512;
}

```

## disassembly

```asm
0x180003218  push    rbx
0x18000321a  push    rbp
0x18000321b  push    rsi
0x18000321c  push    r14
0x18000321e  sub     rsp, 28h
0x180003222  mov     r11, [rdx+0Ch]
0x180003226  mov     rbp, rcx
0x180003229  mov     rcx, [rdx+4]
0x18000322d  mov     r14, rdx
0x180003230  movzx   r8d, word ptr [rcx]
0x180003234  sub     r8d, 1
0x180003238  jz      loc_1800032E3
0x18000323e  cmp     r8d, 54h ; 'T'
0x180003242  jnz     loc_1800032F4
0x180003248  call    l3audioIsValidFormat
0x18000324d  test    eax, eax
0x18000324f  jz      loc_1800032F4
0x180003255  mov     rcx, r11
0x180003258  call    pcmIsValidFormat
0x18000325d  test    eax, eax
0x18000325f  jz      loc_1800032F4
0x180003265  mov     edx, 30h ; '0'; uBytes
0x18000326a  lea     ecx, [rdx+10h]; uFlags
0x18000326d  call    cs:__imp_LocalAlloc
0x180003273  mov     rsi, rax
0x180003276  test    rax, rax
0x180003279  jnz     short loc_180003280
0x18000327b  lea     eax, [rsi+7]
0x18000327e  jmp     short loc_1800032F9
0x180003280  lock inc dword ptr [rbp+3Ch]
0x180003284  lea     rax, l3audioDecode
0x18000328b  mov     qword ptr [rsi+10h], 0
0x180003293  mov     [rsi], rax
0x180003296  mov     qword ptr [rsi+18h], 0
0x18000329e  mov     dword ptr [r14+30h], 0
0x1800032a6  mov     [r14+34h], rsi
0x1800032aa  cmp     [rsi], rax
0x1800032ad  jnz     short loc_1800032CC
0x1800032af  mov     rdx, r14
0x1800032b2  mov     rcx, rbp
0x1800032b5  call    l3audioDecodeOpenStream
0x1800032ba  mov     rbx, rax
0x1800032bd  test    rax, rax
0x1800032c0  jnz     short loc_1800032D1
0x1800032c2  mov     eax, [r14+2Ch]
0x1800032c6  test    al, 1
0x1800032c8  jnz     short loc_1800032D1
0x1800032ca  jmp     short loc_1800032DE
0x1800032cc  mov     ebx, 200h
0x1800032d1  mov     rcx, rsi; hMem
0x1800032d4  call    cs:__imp_LocalFree
0x1800032da  lock dec dword ptr [rbp+3Ch]
0x1800032de  mov     rax, rbx
0x1800032e1  jmp     short loc_1800032F9
0x1800032e3  call    pcmIsValidFormat
0x1800032e8  test    eax, eax
0x1800032ea  jz      short loc_1800032F4
0x1800032ec  mov     rcx, r11
0x1800032ef  call    l3audioIsValidFormat
0x1800032f4  mov     eax, 200h
0x1800032f9  add     rsp, 28h
0x1800032fd  pop     r14
0x1800032ff  pop     rsi
0x180003300  pop     rbp
0x180003301  pop     rbx
0x180003302  retn
```
