# executeCommand

- ea: `0x1400054b0`
- end: `0x1400056c1`
- name: `executeCommand`
- size: `529`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1400062e0`
- `0x1400064c0`

## callees

- `0x1400047b8`
- `0x14000488c`
- `0x140004f94`
- `0x140005148`
- `0x1400054b0`
- `0x140007120`
- `0x14000836c`
- `0x140008620`
- `0x14000a564`
- `0x14000dcf8`
- `0x14000df18`
- `0x14000dfd8`

## pseudocode

```c
__int64 __fastcall executeCommand(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  int v4; // r10d
  unsigned int v9; // ebx
  int v10; // r10d
  int v11; // r10d
  int v12; // r10d
  int v13; // r10d
  int v14; // r10d
  __int64 v16; // rax
  const char *v17; // r14
  __int64 v18; // rax
  const char *v19; // rdx
  int v20; // r10d
  int v21; // r10d
  int v22; // r10d
  int v23; // r10d
  int v24; // r10d
  int v25; // r10d

  v4 = *(_DWORD *)a2;
  if ( *(int *)a2 <= 7 )
  {
    if ( v4 != 7 )
    {
      v9 = 0;
      if ( !v4 )
        return 0;
      v10 = v4 - 1;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
          v12 = v11 - 1;
          if ( v12 )
          {
            v13 = v12 - 1;
            if ( !v13 )
              return doDump();
            v14 = v13 - 1;
            if ( v14 )
            {
              if ( v14 != 1 )
                return 0;
            }
            else if ( !(unsigned int)doFile(a1, a2, a3, a4) || !a3 )
            {
              if ( *(_QWORD *)(a2 + 4360) )
              {
                GLDestroyList();
                *(_QWORD *)(a2 + 4360) = 0;
              }
              return 0;
            }
            return 1;
          }
          v16 = VarFind(*(_QWORD *)(a1 + 16), a2 + 8, a4);
          if ( v16 )
          {
            VarDelete(v16);
            return 1;
          }
          return v9;
        }
        v17 = (const char *)(a2 + 8);
        v18 = VarFind(*(_QWORD *)(a1 + 16), a2 + 8, a4);
        if ( !v18 )
        {
          if ( !VarCreate(*(_QWORD **)(a1 + 16), v17, (__int64)DirectoryName, 5, 2, 0, a4) )
            return v9;
          return (unsigned int)setVariable(a1, v17, a2 + 40);
        }
        if ( (*(_BYTE *)(v18 + 20) & 2) != 0 )
        {
          v19 = "Cannot %1 a variable twice : %2";
        }
        else
        {
          if ( (*(_BYTE *)(v18 + 20) & 1) == 0 )
            return (unsigned int)setVariable(a1, v17, a2 + 40);
          v19 = "Cannot %1 a standard variable: %2";
        }
        ErrSet(a4, v19, "%s%s", "Define", v17);
        return v9;
      }
    }
    return 1;
  }
  v20 = v4 - 8;
  if ( !v20 )
    return modeInfAddLine(a1, *(_DWORD *)(a2 + 8), (const char *)(a2 + 12), a4);
  v21 = v20 - 1;
  if ( !v21 )
    return 0;
  v22 = v21 - 1;
  if ( !v22 )
    return 0;
  v23 = v22 - 1;
  if ( !v23 )
  {
    if ( (*(_BYTE *)(a2 + 10) & 1) != 0 )
      *(_DWORD *)(a1 + 208) = *(_WORD *)(a2 + 8) & 1;
    return 1;
  }
  v24 = v23 - 1;
  if ( !v24 )
    return doNew(a1, a2, a3, a4);
  v25 = v24 - 1;
  if ( !v25 )
  {
    if ( !(unsigned int)doReference() || !a3 )
    {
      if ( *(_QWORD *)(a2 + 264) )
      {
        GLDestroyList();
        *(_QWORD *)(a2 + 264) = 0;
      }
      return 0;
    }
    return 1;
  }
  if ( v25 != 1 )
    return 0;
  return setVariable(a1, a2 + 8, a2 + 40);
}

```

## disassembly

```asm
0x1400054b0  push    rbx
0x1400054b2  push    rbp
0x1400054b3  push    rsi
0x1400054b4  push    rdi
0x1400054b5  push    r14
0x1400054b7  sub     rsp, 40h
0x1400054bb  mov     r10d, [rdx]
0x1400054be  mov     rbp, r9
0x1400054c1  mov     r14d, r8d
0x1400054c4  mov     rdi, rdx
0x1400054c7  mov     rsi, rcx
0x1400054ca  cmp     r10d, 7
0x1400054ce  jg      loc_14000560F
0x1400054d4  jz      loc_1400056A3
0x1400054da  xor     ebx, ebx
0x1400054dc  test    r10d, r10d
0x1400054df  jz      short loc_140005511
0x1400054e1  sub     r10d, 1
0x1400054e5  jz      loc_1400056A3
0x1400054eb  sub     r10d, 1
0x1400054ef  jz      loc_140005577
0x1400054f5  sub     r10d, 1
0x1400054f9  jz      short loc_14000554E
0x1400054fb  sub     r10d, 1
0x1400054ff  jz      short loc_140005544
0x140005501  sub     r10d, 1
0x140005505  jz      short loc_140005518
0x140005507  cmp     r10d, 1
0x14000550b  jz      loc_1400056A3
0x140005511  xor     eax, eax
0x140005513  jmp     loc_1400056B6
0x140005518  call    doFile
0x14000551d  test    eax, eax
0x14000551f  jz      short loc_14000552A
0x140005521  test    r14d, r14d
0x140005524  jnz     loc_1400056A3
0x14000552a  mov     rcx, [rdi+1108h]
0x140005531  test    rcx, rcx
0x140005534  jz      short loc_140005511
0x140005536  call    GLDestroyList
0x14000553b  mov     [rdi+1108h], rbx
0x140005542  jmp     short loc_140005511
0x140005544  call    doDump
0x140005549  jmp     loc_1400056B6
0x14000554e  mov     rcx, [rcx+10h]
0x140005552  add     rdx, 8
0x140005556  mov     r8, rbp
0x140005559  call    VarFind
0x14000555e  test    rax, rax
0x140005561  jz      short loc_140005570
0x140005563  mov     rcx, rax
0x140005566  call    VarDelete
0x14000556b  mov     ebx, 1
0x140005570  mov     eax, ebx
0x140005572  jmp     loc_1400056B6
0x140005577  mov     rcx, [rcx+10h]
0x14000557b  lea     r14, [rdx+8]
0x14000557f  mov     rdx, r14
0x140005582  mov     r8, rbp
0x140005585  call    VarFind
0x14000558a  test    rax, rax
0x14000558d  jnz     short loc_1400055D3
0x14000558f  mov     rcx, [rsi+10h]
0x140005593  lea     r9d, [rax+5]
0x140005597  mov     [rsp+68h+var_38], rbp
0x14000559c  lea     r8, DirectoryName
0x1400055a3  mov     [rsp+68h+var_40], rbx
0x1400055a8  mov     rdx, r14
0x1400055ab  mov     dword ptr [rsp+68h+var_48], 2
0x1400055b3  call    VarCreate
0x1400055b8  test    rax, rax
0x1400055bb  jz      short loc_140005570
0x1400055bd  lea     r8, [rdi+28h]
0x1400055c1  mov     r9, rbp
0x1400055c4  mov     rdx, r14
0x1400055c7  mov     rcx, rsi
0x1400055ca  call    setVariable
0x1400055cf  mov     ebx, eax
0x1400055d1  jmp     short loc_140005570
0x1400055d3  test    byte ptr [rax+14h], 2
0x1400055d7  jz      short loc_140005600
0x1400055d9  lea     rdx, aCannot1AVariab; "Cannot %1 a variable twice : %2"
0x1400055e0  lea     r8, aSS_1; "%s%s"
0x1400055e7  mov     [rsp+68h+var_48], r14
0x1400055ec  lea     r9, aDefine; "Define"
0x1400055f3  mov     rcx, rbp
0x1400055f6  call    ErrSet
0x1400055fb  jmp     loc_140005570
0x140005600  test    byte ptr [rax+14h], 1
0x140005604  jz      short loc_1400055BD
0x140005606  lea     rdx, aCannot1AStanda; "Cannot %1 a standard variable: %2"
0x14000560d  jmp     short loc_1400055E0
0x14000560f  sub     r10d, 8
0x140005613  jz      loc_1400056AA
0x140005619  sub     r10d, 1
0x14000561d  jz      loc_140005511
0x140005623  sub     r10d, 1
0x140005627  jz      loc_140005511
0x14000562d  sub     r10d, 1
0x140005631  jz      short loc_140005690
0x140005633  sub     r10d, 1
0x140005637  jz      short loc_140005689
0x140005639  sub     r10d, 1
0x14000563d  jz      short loc_140005658
0x14000563f  cmp     r10d, 1
0x140005643  jnz     loc_140005511
0x140005649  lea     r8, [rdx+28h]
0x14000564d  add     rdx, 8
0x140005651  call    setVariable
0x140005656  jmp     short loc_1400056B6
0x140005658  call    doReference
0x14000565d  xor     ebx, ebx
0x14000565f  test    eax, eax
0x140005661  jz      short loc_140005668
0x140005663  test    r14d, r14d
0x140005666  jnz     short loc_1400056A3
0x140005668  mov     rcx, [rdi+108h]
0x14000566f  test    rcx, rcx
0x140005672  jz      loc_140005511
0x140005678  call    GLDestroyList
0x14000567d  mov     [rdi+108h], rbx
0x140005684  jmp     loc_140005511
0x140005689  call    doNew
0x14000568e  jmp     short loc_1400056B6
0x140005690  test    byte ptr [rdx+0Ah], 1
0x140005694  jz      short loc_1400056A3
0x140005696  movzx   ecx, word ptr [rdx+8]
0x14000569a  and     ecx, 1
0x14000569d  mov     [rsi+0D0h], ecx
0x1400056a3  mov     eax, 1
0x1400056a8  jmp     short loc_1400056B6
0x1400056aa  lea     r8, [rdx+0Ch]
0x1400056ae  mov     edx, [rdx+8]
0x1400056b1  call    modeInfAddLine
0x1400056b6  add     rsp, 40h
0x1400056ba  pop     r14
0x1400056bc  pop     rdi
0x1400056bd  pop     rsi
0x1400056be  pop     rbp
0x1400056bf  pop     rbx
0x1400056c0  retn
```
