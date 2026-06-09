# CS_CSPathPoints

- ea: `0x14005ebd8`
- end: `0x14005edb4`
- name: `CS_CSPathPoints`
- size: `476`
- prototype: ``
- caller_count: `19`
- callee_count: `3`
- tags: ``

## callers

- `0x14005a760`
- `0x1400617c0`
- `0x140065320`
- `0x140085c80`
- `0x140085ce0`
- `0x140085d40`
- `0x140085da0`
- `0x140085e00`
- `0x140085e60`
- `0x140085ec0`
- `0x1400860d0`
- `0x140086150`
- `0x1400861d0`
- `0x140086240`
- `0x1400862b0`
- `0x140086320`
- `0x140086390`
- `0x14008ddf0`
- `0x14008de40`

## callees

- `0x14003b6c8`
- `0x14005ebd8`
- `0x14006b1bc`

## pseudocode

```c
void __fastcall CS_CSPathPoints(int a1, __int64 a2, __int64 a3, int a4)
{
  int v5; // r10d
  __int64 v6; // rax
  __int64 *v7; // rdx
  int v8; // edx
  int v9; // ecx
  int v10; // r8d
  int v11; // ecx

  v5 = CS_pointCount;
  if ( firstPathBuffer )
  {
    if ( CS_pointCount < 3 && a4 )
    {
      CS_pointCount = 0;
      firstPathBuffer = 1;
      return;
    }
    CS_saveVertDir = 0;
    CS_savePrevCross = (__int64)fakePrevCross;
    dword_1400B6B74 = 0x7FFFFFFF;
    v6 = CS_pointArray;
    CS_pathMaxX = 0;
    CS_pathMinX = 0;
    CS_havePathCross = 0;
    if ( CS_xPathMin == 0x7FFFFFFF )
    {
      v8 = dword_1400B6C28;
      v9 = CS_pointArray;
      v10 = dword_1400B6C2C;
      if ( (int)CS_pointArray >= dword_1400B6C28 )
      {
        v9 = dword_1400B6C28;
        v8 = CS_pointArray;
      }
      CS_xPathMin = v9;
      CS_xPathMax = v8;
      v11 = HIDWORD(CS_pointArray);
      if ( SHIDWORD(CS_pointArray) >= dword_1400B6C2C )
      {
        v11 = dword_1400B6C2C;
        v10 = HIDWORD(CS_pointArray);
      }
      CS_yPathMax = v10;
      CS_yPathMin = v11;
    }
    else
    {
      if ( (int)CS_pointArray >= CS_xPathMin )
      {
        if ( (int)CS_pointArray > CS_xPathMax )
          CS_xPathMax = CS_pointArray;
      }
      else
      {
        CS_xPathMin = CS_pointArray;
      }
      if ( SHIDWORD(CS_pointArray) >= CS_yPathMin )
      {
        if ( SHIDWORD(CS_pointArray) > CS_yPathMax )
          CS_yPathMax = HIDWORD(CS_pointArray);
      }
      else
      {
        CS_yPathMin = HIDWORD(CS_pointArray);
      }
    }
    firstPoint = CS_pointArray;
    CS_saveHorizDir = 0;
    v7 = (__int64 *)&dword_1400B6C28;
    CS_savePrevPoint = CS_pointArray;
    v5 = CS_pointCount - 1;
  }
  else
  {
    v6 = firstPoint;
    v7 = &CS_pointArray;
  }
  if ( a4 )
  {
    if ( v7[v5 - 1] != __PAIR64__(HIDWORD(firstPoint), v6) )
      v7[v5++] = v6;
    if ( !firstPathBuffer || v5 >= 3 )
    {
      CS_BuildCrosses(a1, (_DWORD)v7, v5, a4);
      FinishPath();
    }
  }
  else
  {
    CS_BuildCrosses(a1, (_DWORD)v7, v5, 0);
    firstPathBuffer = 0;
  }
}

```

## disassembly

```asm
0x14005ebd8  sub     rsp, 38h
0x14005ebdc  cmp     cs:firstPathBuffer, 0
0x14005ebe3  mov     r11, rcx
0x14005ebe6  mov     r10d, cs:CS_pointCount
0x14005ebed  jnz     short loc_14005EC20
0x14005ebef  mov     rax, cs:firstPoint
0x14005ebf6  lea     rdx, CS_pointArray
0x14005ebfd  test    r9d, r9d
0x14005ec00  jnz     loc_14005ECF6
0x14005ec06  mov     r8d, r10d
0x14005ec09  mov     rcx, r11
0x14005ec0c  call    CS_BuildCrosses
0x14005ec11  mov     cs:firstPathBuffer, 0
0x14005ec1b  add     rsp, 38h
0x14005ec1f  retn
0x14005ec20  cmp     r10d, 3
0x14005ec24  jl      loc_14005ED32
0x14005ec2a  mov     ecx, cs:CS_xPathMin
0x14005ec30  xor     eax, eax
0x14005ec32  mov     cs:CS_saveVertDir, ax
0x14005ec39  lea     rax, fakePrevCross
0x14005ec40  mov     cs:CS_savePrevCross, rax
0x14005ec47  mov     eax, 7FFFFFFFh
0x14005ec4c  mov     cs:dword_1400B6B74, eax
0x14005ec52  cmp     ecx, eax
0x14005ec54  mov     rax, cs:CS_pointArray
0x14005ec5b  mov     cs:CS_pathMaxX, 0
0x14005ec66  mov     cs:CS_pathMinX, 0
0x14005ec71  mov     cs:CS_havePathCross, 0
0x14005ec7b  jnz     loc_14005ED54
0x14005ec81  mov     edx, cs:dword_1400B6C28
0x14005ec87  mov     ecx, eax
0x14005ec89  mov     r8d, cs:dword_1400B6C2C
0x14005ec90  cmp     eax, edx
0x14005ec92  cmovge  ecx, edx
0x14005ec95  cmovge  edx, eax
0x14005ec98  mov     cs:CS_xPathMin, ecx
0x14005ec9e  mov     cs:CS_xPathMax, edx
0x14005eca4  mov     edx, dword ptr cs:CS_pointArray+4
0x14005ecaa  cmp     edx, r8d
0x14005ecad  mov     ecx, edx
0x14005ecaf  cmovge  ecx, r8d
0x14005ecb3  cmovge  r8d, edx
0x14005ecb7  mov     cs:CS_yPathMax, r8d
0x14005ecbe  mov     cs:CS_yPathMin, ecx
0x14005ecc4  xor     ecx, ecx
0x14005ecc6  mov     cs:firstPoint, rax
0x14005eccd  mov     cs:CS_saveHorizDir, cx
0x14005ecd4  lea     rdx, dword_1400B6C28
0x14005ecdb  mov     rcx, rax
0x14005ecde  mov     dword ptr cs:CS_savePrevPoint, eax
0x14005ece4  shr     rcx, 20h
0x14005ece8  mov     dword ptr cs:CS_savePrevPoint+4, ecx
0x14005ecee  dec     r10d
0x14005ecf1  jmp     loc_14005EBFD
0x14005ecf6  movsxd  r8, r10d
0x14005ecf9  cmp     [rdx+r8*8-8], eax
0x14005ecfe  jz      loc_14005ED9E
0x14005ed04  mov     [rdx+r8*8], rax
0x14005ed08  inc     r10d
0x14005ed0b  cmp     cs:firstPathBuffer, 0
0x14005ed12  jz      short loc_14005ED1E
0x14005ed14  cmp     r10d, 3
0x14005ed18  jl      loc_14005EC1B
0x14005ed1e  mov     r8d, r10d
0x14005ed21  mov     rcx, r11
0x14005ed24  call    CS_BuildCrosses
0x14005ed29  add     rsp, 38h
0x14005ed2d  jmp     FinishPath
0x14005ed32  test    r9d, r9d
0x14005ed35  jz      loc_14005EC2A
0x14005ed3b  mov     cs:CS_pointCount, 0
0x14005ed45  mov     cs:firstPathBuffer, 1
0x14005ed4f  jmp     loc_14005EC1B
0x14005ed54  cmp     eax, ecx
0x14005ed56  jge     short loc_14005ED60
0x14005ed58  mov     cs:CS_xPathMin, eax
0x14005ed5e  jmp     short loc_14005ED6E
0x14005ed60  cmp     eax, cs:CS_xPathMax
0x14005ed66  jle     short loc_14005ED6E
0x14005ed68  mov     cs:CS_xPathMax, eax
0x14005ed6e  mov     ecx, dword ptr cs:CS_pointArray+4
0x14005ed74  cmp     ecx, cs:CS_yPathMin
0x14005ed7a  jge     short loc_14005ED87
0x14005ed7c  mov     cs:CS_yPathMin, ecx
0x14005ed82  jmp     loc_14005ECC4
0x14005ed87  cmp     ecx, cs:CS_yPathMax
0x14005ed8d  jle     loc_14005ECC4
0x14005ed93  mov     cs:CS_yPathMax, ecx
0x14005ed99  jmp     loc_14005ECC4
0x14005ed9e  mov     ecx, dword ptr cs:firstPoint+4
0x14005eda4  cmp     [rdx+r8*8-4], ecx
0x14005eda9  jz      loc_14005ED0B
0x14005edaf  jmp     loc_14005ED04
```
