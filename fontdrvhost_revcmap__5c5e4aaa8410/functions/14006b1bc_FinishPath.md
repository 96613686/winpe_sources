# FinishPath

- ea: `0x14006b1bc`
- end: `0x14006b3c4`
- name: `FinishPath`
- size: `520`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14005ebd8`

## callees

- `0x1400595cc`
- `0x1400599b0`
- `0x140059a48`
- `0x140059a78`
- `0x14005e23c`
- `0x1400675a0`
- `0x14006b1bc`

## pseudocode

```c
void FinishPath()
{
  __int64 v0; // rcx
  int v1; // edi
  char *v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rsi
  int v6; // eax
  int v7; // eax
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rax
  int v11; // ecx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx

  v0 = startLink;
  v1 = CS_havePathCross;
  if ( (*(_WORD *)startLink & 0x2000) == 0 )
  {
    os_raise(0xFFFFFFFFLL, 0);
    v0 = startLink;
  }
  v2 = (char *)CS_currentCross - 24;
  if ( (char *)CS_currentCross - 24 != (_BYTE *)v0 )
  {
    *(_DWORD *)(v0 + 20) = (_DWORD)v2 - v0;
    v3 = NewLinkCross();
    oldStartLink = startLink;
    *(_DWORD *)(v3 + 16) = startLink - v3 + 24;
    v4 = NewLinkCross();
    v5 = oldStartLink;
    startLink = v4;
    *(_DWORD *)(oldStartLink + 16) = v4 - oldStartLink + 24;
    v6 = *((_DWORD *)v2 + 4);
    if ( v6 < CS_xPathMin )
      CS_xPathMin = *((_DWORD *)v2 + 4);
    if ( v6 > CS_xPathMax )
      CS_xPathMax = v6;
    v7 = *((_DWORD *)v2 + 5);
    if ( v7 < CS_yPathMin )
      CS_yPathMin = *((_DWORD *)v2 + 5);
    if ( v7 > CS_yPathMax )
      CS_yPathMax = v7;
    if ( v1 )
    {
      if ( (*(_WORD *)v2 & 0x2000) != 0 )
        v2 = (char *)CS_BackPathCross((__int64)v2);
      v8 = CS_ForwPathCross((__int64)v2);
      FixCrossFlags(v2, v8);
      v9 = v5 + 24;
      v10 = CS_PathXtraCross(v5 + 24, 1);
      v11 = *(_DWORD *)(v5 + 40);
      if ( v11 > *(_DWORD *)(v10 + 16) )
      {
        if ( CS_saveHorizDir == 1 )
          goto LABEL_18;
      }
      else
      {
        if ( v11 != *(_DWORD *)(v10 + 16) )
        {
          if ( CS_saveHorizDir == 2 )
          {
LABEL_18:
            v9 = CS_pathMinX;
LABEL_19:
            v12 = CS_pathMaxX;
LABEL_20:
            v13 = v9;
            if ( v9 )
            {
              if ( *(_QWORD *)(v9 + 8) )
              {
                do
                  v13 = *(_QWORD *)(v13 + 8);
                while ( *(_QWORD *)(v13 + 8) );
              }
              *(_QWORD *)(v13 + 8) = minXInflections;
              minXInflections = v9;
            }
            v14 = v12;
            if ( v12 )
            {
              if ( *(_QWORD *)(v12 + 8) )
              {
                do
                  v14 = *(_QWORD *)(v14 + 8);
                while ( *(_QWORD *)(v14 + 8) );
              }
              *(_QWORD *)(v14 + 8) = maxXInflections;
              maxXInflections = v12;
            }
            goto LABEL_28;
          }
          goto LABEL_31;
        }
        if ( CS_saveHorizDir == 3 )
          goto LABEL_18;
        if ( CS_saveHorizDir == 1 )
        {
LABEL_31:
          *(_QWORD *)(v5 + 32) = CS_pathMinX;
          CS_pathMinX = v5 + 24;
          goto LABEL_19;
        }
      }
      v12 = v5 + 24;
      *(_QWORD *)(v5 + 32) = CS_pathMaxX;
      CS_pathMaxX = v5 + 24;
      v9 = CS_pathMinX;
      goto LABEL_20;
    }
  }
LABEL_28:
  CS_pointCount = 0;
  firstPathBuffer = 1;
}

```

## disassembly

```asm
0x14006b1bc  push    rbx
0x14006b1be  push    rsi
0x14006b1bf  push    rdi
0x14006b1c0  push    r14
0x14006b1c2  push    r15
0x14006b1c4  sub     rsp, 20h
0x14006b1c8  mov     rcx, cs:startLink
0x14006b1cf  mov     r15d, 2000h
0x14006b1d5  mov     edi, cs:CS_havePathCross
0x14006b1db  test    [rcx], r15w
0x14006b1df  jnz     short loc_14006B1F2
0x14006b1e1  xor     edx, edx
0x14006b1e3  or      ecx, 0FFFFFFFFh
0x14006b1e6  call    os_raise
0x14006b1eb  mov     rcx, cs:startLink
0x14006b1f2  mov     rbx, cs:CS_currentCross
0x14006b1f9  mov     r14d, 1
0x14006b1ff  add     rbx, 0FFFFFFFFFFFFFFE8h
0x14006b203  cmp     rbx, rcx
0x14006b206  jz      loc_14006B34A
0x14006b20c  mov     eax, ebx
0x14006b20e  sub     eax, ecx
0x14006b210  mov     [rcx+14h], eax
0x14006b213  call    NewLinkCross
0x14006b218  mov     rdx, cs:startLink
0x14006b21f  mov     ecx, edx
0x14006b221  mov     cs:oldStartLink, rdx
0x14006b228  sub     ecx, eax
0x14006b22a  add     ecx, 18h
0x14006b22d  mov     [rax+10h], ecx
0x14006b230  call    NewLinkCross
0x14006b235  mov     rsi, cs:oldStartLink
0x14006b23c  mov     cs:startLink, rax
0x14006b243  sub     eax, esi
0x14006b245  add     eax, 18h
0x14006b248  mov     [rsi+10h], eax
0x14006b24b  mov     eax, [rbx+10h]
0x14006b24e  cmp     eax, cs:CS_xPathMin
0x14006b254  jge     short loc_14006B25C
0x14006b256  mov     cs:CS_xPathMin, eax
0x14006b25c  cmp     eax, cs:CS_xPathMax
0x14006b262  jle     short loc_14006B26A
0x14006b264  mov     cs:CS_xPathMax, eax
0x14006b26a  mov     eax, [rbx+14h]
0x14006b26d  cmp     eax, cs:CS_yPathMin
0x14006b273  jge     short loc_14006B27B
0x14006b275  mov     cs:CS_yPathMin, eax
0x14006b27b  cmp     eax, cs:CS_yPathMax
0x14006b281  jle     short loc_14006B289
0x14006b283  mov     cs:CS_yPathMax, eax
0x14006b289  test    edi, edi
0x14006b28b  jz      loc_14006B34A
0x14006b291  test    [rbx], r15w
0x14006b295  jz      short loc_14006B2A2
0x14006b297  mov     rcx, rbx
0x14006b29a  call    CS_BackPathCross
0x14006b29f  mov     rbx, rax
0x14006b2a2  mov     rcx, rbx
0x14006b2a5  call    CS_ForwPathCross
0x14006b2aa  mov     rdx, rax
0x14006b2ad  mov     rcx, rbx
0x14006b2b0  call    FixCrossFlags
0x14006b2b5  lea     rbx, [rsi+18h]
0x14006b2b9  mov     edx, r14d
0x14006b2bc  mov     rcx, rbx
0x14006b2bf  call    CS_PathXtraCross
0x14006b2c4  mov     ecx, [rbx+10h]
0x14006b2c7  cmp     ecx, [rax+10h]
0x14006b2ca  jg      loc_14006B395
0x14006b2d0  jz      loc_14006B367
0x14006b2d6  cmp     cs:CS_saveHorizDir, 2
0x14006b2de  jnz     loc_14006B37E
0x14006b2e4  mov     rbx, cs:CS_pathMinX
0x14006b2eb  mov     rdx, cs:CS_pathMaxX
0x14006b2f2  mov     rcx, rbx
0x14006b2f5  test    rbx, rbx
0x14006b2f8  jz      short loc_14006B31E
0x14006b2fa  cmp     qword ptr [rbx+8], 0
0x14006b2ff  jz      short loc_14006B30C
0x14006b301  mov     rcx, [rcx+8]
0x14006b305  cmp     qword ptr [rcx+8], 0
0x14006b30a  jnz     short loc_14006B301
0x14006b30c  mov     rax, cs:minXInflections
0x14006b313  mov     [rcx+8], rax
0x14006b317  mov     cs:minXInflections, rbx
0x14006b31e  mov     rcx, rdx
0x14006b321  test    rdx, rdx
0x14006b324  jz      short loc_14006B34A
0x14006b326  cmp     qword ptr [rdx+8], 0
0x14006b32b  jz      short loc_14006B338
0x14006b32d  mov     rcx, [rcx+8]
0x14006b331  cmp     qword ptr [rcx+8], 0
0x14006b336  jnz     short loc_14006B32D
0x14006b338  mov     rax, cs:maxXInflections
0x14006b33f  mov     [rcx+8], rax
0x14006b343  mov     cs:maxXInflections, rdx
0x14006b34a  mov     cs:CS_pointCount, 0
0x14006b354  mov     cs:firstPathBuffer, r14d
0x14006b35b  add     rsp, 20h
0x14006b35f  pop     r15
0x14006b361  pop     r14
0x14006b363  pop     rdi
0x14006b364  pop     rsi
0x14006b365  pop     rbx
0x14006b366  retn
0x14006b367  movzx   eax, cs:CS_saveHorizDir
0x14006b36e  cmp     ax, 3
0x14006b372  jz      loc_14006B2E4
0x14006b378  cmp     ax, r14w
0x14006b37c  jnz     short loc_14006B3A3
0x14006b37e  mov     rax, cs:CS_pathMinX
0x14006b385  mov     [rbx+8], rax
0x14006b389  mov     cs:CS_pathMinX, rbx
0x14006b390  jmp     loc_14006B2EB
0x14006b395  cmp     cs:CS_saveHorizDir, r14w
0x14006b39d  jz      loc_14006B2E4
0x14006b3a3  mov     rax, cs:CS_pathMaxX
0x14006b3aa  mov     rdx, rbx
0x14006b3ad  mov     [rbx+8], rax
0x14006b3b1  mov     cs:CS_pathMaxX, rbx
0x14006b3b8  mov     rbx, cs:CS_pathMinX
0x14006b3bf  jmp     loc_14006B2F2
```
