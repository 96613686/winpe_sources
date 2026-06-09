# MdaVerifyFcb

- ea: `0x140014760`
- end: `0x1400147e9`
- name: `MdaVerifyFcb`
- size: `137`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x140005de0`
- `0x140017d40`
- `0x14001a160`
- `0x14001a270`
- `0x14001a398`
- `0x14001a478`
- `0x14001a580`

## callees

- `0x1400029d0`
- `0x140014760`
- `0x1400159cc`
- `0x1400159fc`

## pseudocode

```c
__int64 __fastcall MdaVerifyFcb(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  unsigned int v7; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
  result = NfsGetAttributes(a2, a1, *(_QWORD *)(a3 + 8));
  v7 = result;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x140014760  push    rbx
0x140014762  push    rbp
0x140014763  push    rsi
0x140014764  push    rdi
0x140014765  sub     rsp, 28h
0x140014769  mov     rbx, r8
0x14001476c  mov     rdi, rdx
0x14001476f  mov     rsi, rcx
0x140014772  mov     rcx, cs:WPP_GLOBAL_Control
0x140014779  lea     rbp, WPP_GLOBAL_Control
0x140014780  cmp     rcx, rbp
0x140014783  jz      short loc_1400147A1
0x140014785  mov     eax, [rcx+2Ch]
0x140014788  test    al, 8
0x14001478a  jz      short loc_1400147A1
0x14001478c  mov     rcx, [rcx+18h]
0x140014790  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x140014797  mov     edx, 42h ; 'B'
0x14001479c  call    WPP_SF_
0x1400147a1  mov     r8, [rbx+8]
0x1400147a5  mov     rdx, rsi
0x1400147a8  mov     rcx, rdi
0x1400147ab  call    NfsGetAttributes
0x1400147b0  mov     ebx, eax
0x1400147b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400147b9  cmp     rcx, rbp
0x1400147bc  jz      short loc_1400147DF
0x1400147be  mov     eax, [rcx+2Ch]
0x1400147c1  test    al, 8
0x1400147c3  jz      short loc_1400147DD
0x1400147c5  mov     rcx, [rcx+18h]
0x1400147c9  lea     r8, WPP_f4041152215237eb07f0d7c0d4f54834_Traceguids
0x1400147d0  mov     edx, 43h ; 'C'
0x1400147d5  mov     r9d, ebx
0x1400147d8  call    WPP_SF_d
0x1400147dd  mov     eax, ebx
0x1400147df  add     rsp, 28h
0x1400147e3  pop     rdi
0x1400147e4  pop     rsi
0x1400147e5  pop     rbp
0x1400147e6  pop     rbx
0x1400147e7  retn
```
