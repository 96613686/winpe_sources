# MDIResetDecompressionGlobal

- ea: `0x18000936c`
- end: `0x1800093f8`
- name: `MDIResetDecompressionGlobal`
- size: `140`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800063a0`

## callees

- `0x180008f3c`
- `0x18000936c`
- `0x180015d84`

## pseudocode

```c
__int64 __fastcall MDIResetDecompressionGlobal(__int64 a1)
{
  __int64 v3; // rcx
  _QWORD *v4; // rax

  switch ( *(_WORD *)(a1 + 266) & 0xF )
  {
    case 0:
      return 1;
    case 1:
      if ( **(_DWORD **)(a1 + 96) == 1128875085 )
        return 1;
      v4 = *(_QWORD **)a1;
      goto LABEL_12;
    case 2:
      if ( !(unsigned int)QDIResetDecompression(*(_QWORD *)(a1 + 96)) )
        return 1;
LABEL_11:
      v4 = *(_QWORD **)a1;
LABEL_12:
      *v4 = 7;
      goto LABEL_13;
    case 3:
      v3 = *(_QWORD *)(a1 + 96);
      if ( *(_DWORD *)v3 == 1128875084 )
      {
        LZX_DecodeNewGroup(*(_QWORD *)(v3 + 72));
        return 1;
      }
      goto LABEL_11;
    case 15:
      return 1;
  }
  v4 = *(_QWORD **)a1;
  **(_QWORD **)a1 = 6;
LABEL_13:
  *((_DWORD *)v4 + 2) = 1;
  return 0;
}

```

## disassembly

```asm
0x18000936c  push    rbx
0x18000936e  sub     rsp, 20h
0x180009372  movzx   edx, word ptr [rcx+10Ah]
0x180009379  mov     rbx, rcx
0x18000937c  and     edx, 0Fh
0x18000937f  jz      short loc_180009395
0x180009381  sub     edx, 1
0x180009384  jz      short loc_1800093B7
0x180009386  sub     edx, 1
0x180009389  jz      short loc_1800093E9
0x18000938b  sub     edx, 1
0x18000938e  jz      short loc_1800093A0
0x180009390  cmp     edx, 0Ch
0x180009393  jnz     short loc_1800093DD
0x180009395  mov     eax, 1
0x18000939a  add     rsp, 20h
0x18000939e  pop     rbx
0x18000939f  retn
0x1800093a0  mov     rcx, [rcx+60h]
0x1800093a4  cmp     dword ptr [rcx], 4349444Ch
0x1800093aa  jnz     short loc_1800093C8
0x1800093ac  mov     rcx, [rcx+48h]
0x1800093b0  call    LZX_DecodeNewGroup
0x1800093b5  jmp     short loc_180009395
0x1800093b7  mov     rax, [rcx+60h]
0x1800093bb  cmp     dword ptr [rax], 4349444Dh
0x1800093c1  jz      short loc_180009395
0x1800093c3  mov     rax, [rcx]
0x1800093c6  jmp     short loc_1800093CB
0x1800093c8  mov     rax, [rbx]
0x1800093cb  mov     qword ptr [rax], 7
0x1800093d2  mov     dword ptr [rax+8], 1
0x1800093d9  xor     eax, eax
0x1800093db  jmp     short loc_18000939A
0x1800093dd  mov     rax, [rcx]
0x1800093e0  mov     qword ptr [rax], 6
0x1800093e7  jmp     short loc_1800093D2
0x1800093e9  mov     rcx, [rcx+60h]
0x1800093ed  call    QDIResetDecompression
0x1800093f2  test    eax, eax
0x1800093f4  jz      short loc_180009395
0x1800093f6  jmp     short loc_1800093C8
```
