# mwStatus

- ea: `0x180004d18`
- end: `0x1800050a8`
- name: `mwStatus`
- size: `912`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003614`

## callees

- `0x180003114`
- `0x1800035d0`
- `0x180004028`
- `0x180004d18`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180004f6b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180005007`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180004f6b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180005007`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004f78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005014`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004f78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005014`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004f60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004ffc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004f60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004ffc`
- `USER32!PostThreadMessageW` at `0x180004fab`
- `USER32!PostThreadMessageW` at `0x180004fab`

## pseudocode

```c
__int64 __fastcall mwStatus(__int64 a1, int a2, unsigned int *a3)
{
  unsigned int v5; // edx
  unsigned int v7; // eax
  unsigned int Device; // ebx
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned __int64 v16; // rcx
  __int64 v17; // r8
  unsigned int PlayRecPosition; // eax
  __int64 v19; // rcx
  __int64 v20; // rax
  unsigned int v21; // ecx
  __int64 v22; // rax
  bool v23; // zf
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rax
  _DWORD *v33; // r14
  _DWORD *v34; // rbp
  DWORD v35; // ecx
  int v36; // edx
  _WORD *v37; // rax
  unsigned int v38; // [rsp+48h] [rbp+10h] BYREF

  if ( (a2 & 0x100) == 0 )
    return 273;
  v5 = a2 & 0xFFFFFEFC;
  if ( (v5 & 0x10) != 0 && a3[4] - 1 > 1 || (v5 & 0x200) != 0 && a3[4] != 2 )
    return 284;
  v7 = a3[4];
  Device = 0;
  if ( v7 > 0x4001 )
  {
    v24 = v7 - 16386;
    if ( !v24 )
    {
      v19 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 168) + 2LL);
      goto LABEL_82;
    }
    v25 = v24 - 1;
    if ( !v25 )
    {
      v19 = *(unsigned int *)(*(_QWORD *)(a1 + 168) + 4LL);
      goto LABEL_82;
    }
    v26 = v25 - 1;
    if ( !v26 )
    {
      v19 = *(unsigned int *)(*(_QWORD *)(a1 + 168) + 8LL);
      goto LABEL_82;
    }
    v27 = v26 - 1;
    if ( !v27 )
    {
      v19 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 168) + 12LL);
      goto LABEL_82;
    }
    v28 = v27 - 1;
    if ( !v28 )
    {
      v37 = *(_WORD **)(a1 + 168);
      if ( *v37 != 1 )
        return 274;
      v20 = (unsigned __int16)v37[7];
      goto LABEL_77;
    }
    v29 = v28 - 1;
    if ( v29 )
    {
      v30 = v29 - 4177913;
      if ( v30 )
      {
        if ( v30 != 0x400000 )
          return 274;
        v31 = *(unsigned int *)(a1 + 36);
      }
      else
      {
        v31 = *(unsigned int *)(a1 + 40);
      }
      v32 = 75628543;
      if ( (_DWORD)v31 != -1 )
        v32 = v31;
      *((_QWORD *)a3 + 1) = v32;
      v23 = (_DWORD)v31 == -1;
LABEL_44:
      Device = 0x10000;
      if ( !v23 )
        return 0;
      return Device;
    }
    if ( (*(_BYTE *)(a1 + 4) & 0x40) == 0 || *(_DWORD *)(a1 + 32) == 2 )
    {
      v33 = (_DWORD *)(a1 + 32);
      v34 = (_DWORD *)(a1 + 32);
      if ( *(_DWORD *)(a1 + 32) != 2 )
      {
        v36 = *(_DWORD *)(a1 + 4);
        if ( (v36 & 0xC00) == 0 || (v36 & 0x2000) == 0 )
          return 322;
        if ( (v36 & 0x10) != 0 )
          goto LABEL_71;
        goto LABEL_69;
      }
    }
    else
    {
      do
      {
        LeaveCriticalSection(&CritSec);
        Sleep(0xAu);
        EnterCriticalSection(&CritSec);
      }
      while ( *(_DWORD *)(a1 + 32) != 2 );
      v33 = (_DWORD *)(a1 + 32);
      v34 = (_DWORD *)(a1 + 32);
    }
    v35 = *(_DWORD *)(a1 + 24);
    *(_DWORD *)(a1 + 28) = 0;
    PostThreadMessageW(v35, 0x401u, 0, 0);
    Device = mwGetDevice(a1);
    if ( Device )
      return Device;
    *(_DWORD *)(a1 + 4) = 11520;
    *v33 = 3;
    do
    {
LABEL_69:
      if ( *v34 == 2 )
        break;
      LeaveCriticalSection(&CritSec);
      Sleep(0xAu);
      EnterCriticalSection(&CritSec);
    }
    while ( (*(_BYTE *)(a1 + 4) & 0x10) == 0 );
LABEL_71:
    if ( *(_DWORD *)(a1 + 140) )
      return *(unsigned int *)(a1 + 140);
    v20 = *(unsigned int *)(a1 + 136);
    goto LABEL_77;
  }
  if ( v7 == 16385 )
  {
    v21 = **(unsigned __int16 **)(a1 + 168);
    v22 = 75497473;
    if ( (_WORD)v21 != 1 )
      v22 = v21;
    *((_QWORD *)a3 + 1) = v22;
    v23 = (_WORD)v21 == 1;
    goto LABEL_44;
  }
  v9 = v7 - 1;
  if ( !v9 )
  {
    if ( v5 )
    {
      if ( v5 != 16 )
        return 259;
      if ( a3[5] != 1 )
        return 282;
    }
    v20 = (unsigned int)bytes2time(a1, *(unsigned int *)(a1 + 76), *(unsigned int *)(a1 + 8));
LABEL_77:
    *((_QWORD *)a3 + 1) = v20;
    return Device;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    if ( v5 )
    {
      if ( v5 != 16 )
      {
        if ( v5 == 512 )
        {
LABEL_31:
          *((_QWORD *)a3 + 1) = 0;
          return Device;
        }
        return 259;
      }
      if ( a3[5] == 1 )
        goto LABEL_31;
      return 282;
    }
    v17 = *(unsigned int *)(a1 + 8);
    v38 = a3[2];
    PlayRecPosition = GetPlayRecPosition(a1, &v38, v17);
    v19 = v38;
    Device = PlayRecPosition;
LABEL_82:
    *((_QWORD *)a3 + 1) = v19;
    return Device;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
LABEL_27:
    *((_QWORD *)a3 + 1) = 1;
    return Device;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    if ( *(_DWORD *)(a1 + 32) == 3 )
    {
      if ( (*(_DWORD *)(a1 + 4) & 0x2028) != 0 )
        v16 = 529;
      else
        v16 = (~*(_WORD *)(a1 + 4) & 0x200 | 0x41C00uLL) >> 9;
    }
    else
    {
      v16 = 525;
    }
    *((_QWORD *)a3 + 1) = v16 | (v16 << 16);
    return 0x10000;
  }
  v13 = v12 - 1;
  if ( !v13 )
    goto LABEL_18;
  v14 = v13 - 1;
  if ( !v14 )
  {
    *((_QWORD *)a3 + 1) = *(unsigned __int16 *)(a1 + 8)
                        | ((unsigned __int64)(unsigned __int16)(*(_WORD *)(a1 + 8) + 533) << 16);
    return 0x10000;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
LABEL_18:
    *((_QWORD *)a3 + 1) = 34865153;
    return 0x10000;
  }
  if ( v15 == 1 )
    goto LABEL_27;
  return 274;
}

```

## disassembly

```asm
0x180004d18  mov     [rsp+arg_0], rbx
0x180004d1d  mov     [rsp+arg_10], rbp
0x180004d22  push    rsi
0x180004d23  push    rdi
0x180004d24  push    r14
0x180004d26  sub     rsp, 20h
0x180004d2a  mov     rsi, r8
0x180004d2d  mov     rdi, rcx
0x180004d30  bt      edx, 8
0x180004d34  jnb     loc_18000508E
0x180004d3a  and     edx, 0FFFFFEFCh
0x180004d40  mov     r8d, 1
0x180004d46  test    dl, 10h
0x180004d49  jz      short loc_180004D56
0x180004d4b  mov     eax, [rsi+10h]
0x180004d4e  sub     eax, r8d
0x180004d51  cmp     eax, r8d
0x180004d54  ja      short loc_180004D67
0x180004d56  mov     r9d, 200h
0x180004d5c  test    r9d, edx
0x180004d5f  jz      short loc_180004D71
0x180004d61  cmp     dword ptr [rsi+10h], 2
0x180004d65  jz      short loc_180004D71
0x180004d67  mov     eax, 11Ch
0x180004d6c  jmp     loc_180005095
0x180004d71  mov     eax, [rsi+10h]
0x180004d74  xor     ebx, ebx
0x180004d76  mov     ecx, 4001h
0x180004d7b  cmp     eax, ecx
0x180004d7d  ja      loc_180004EE6
0x180004d83  jz      loc_180004EB8
0x180004d89  sub     eax, r8d
0x180004d8c  jz      loc_180004E7F
0x180004d92  sub     eax, r8d
0x180004d95  jz      loc_180004E3D
0x180004d9b  sub     eax, r8d
0x180004d9e  jz      loc_180004E34
0x180004da4  sub     eax, r8d
0x180004da7  jz      short loc_180004DF4
0x180004da9  sub     eax, r8d
0x180004dac  jz      short loc_180004DC7
0x180004dae  sub     eax, r8d
0x180004db1  jz      short loc_180004DD9
0x180004db3  sub     eax, r8d
0x180004db6  jz      short loc_180004DC7
0x180004db8  cmp     eax, r8d
0x180004dbb  jz      short loc_180004E34
0x180004dbd  mov     ebx, 112h
0x180004dc2  jmp     loc_180005093
0x180004dc7  mov     qword ptr [rsi+8], 2140001h
0x180004dcf  mov     ebx, 10000h
0x180004dd4  jmp     loc_180005093
0x180004dd9  movzx   edx, word ptr [rdi+8]
0x180004ddd  mov     eax, 215h
0x180004de2  add     eax, edx
0x180004de4  movzx   ecx, ax
0x180004de7  shl     rcx, 10h
0x180004deb  or      rcx, rdx
0x180004dee  mov     [rsi+8], rcx
0x180004df2  jmp     short loc_180004DCF
0x180004df4  cmp     dword ptr [rdi+20h], 3
0x180004df8  jnz     short loc_180004E1F
0x180004dfa  mov     eax, [rdi+4]
0x180004dfd  test    eax, 2028h
0x180004e02  jz      short loc_180004E0B
0x180004e04  mov     ecx, 211h
0x180004e09  jmp     short loc_180004E24
0x180004e0b  not     eax
0x180004e0d  mov     ecx, eax
0x180004e0f  and     rcx, r9
0x180004e12  or      rcx, 41C00h
0x180004e19  shr     rcx, 9
0x180004e1d  jmp     short loc_180004E24
0x180004e1f  mov     ecx, 20Dh
0x180004e24  mov     rax, rcx
0x180004e27  shl     rax, 10h
0x180004e2b  or      rax, rcx
0x180004e2e  mov     [rsi+8], rax
0x180004e32  jmp     short loc_180004DCF
0x180004e34  mov     [rsi+8], r8
0x180004e38  jmp     loc_180005093
0x180004e3d  test    edx, edx
0x180004e3f  jz      short loc_180004E5C
0x180004e41  cmp     edx, 10h
0x180004e44  jz      short loc_180004E54
0x180004e46  cmp     edx, r9d
0x180004e49  jnz     short loc_180004E88
0x180004e4b  mov     [rsi+8], rbx
0x180004e4f  jmp     loc_180005093
0x180004e54  cmp     [rsi+14h], r8d
0x180004e58  jz      short loc_180004E4B
0x180004e5a  jmp     short loc_180004E98
0x180004e5c  mov     eax, [rsi+8]
0x180004e5f  lea     rdx, [rsp+38h+arg_8]
0x180004e64  mov     r8d, [rdi+8]
0x180004e68  mov     rcx, rdi
0x180004e6b  mov     [rsp+38h+arg_8], eax
0x180004e6f  call    GetPlayRecPosition
0x180004e74  mov     ecx, [rsp+38h+arg_8]
0x180004e78  mov     ebx, eax
0x180004e7a  jmp     loc_180005088
0x180004e7f  test    edx, edx
0x180004e81  jz      short loc_180004EA2
0x180004e83  cmp     edx, 10h
0x180004e86  jz      short loc_180004E92
0x180004e88  mov     ebx, 103h
0x180004e8d  jmp     loc_180005093
0x180004e92  cmp     [rsi+14h], r8d
0x180004e96  jz      short loc_180004EA2
0x180004e98  mov     ebx, 11Ah
0x180004e9d  jmp     loc_180005093
0x180004ea2  mov     r8d, [rdi+8]
0x180004ea6  mov     rcx, rdi
0x180004ea9  mov     edx, [rdi+4Ch]
0x180004eac  call    bytes2time
0x180004eb1  mov     eax, eax
0x180004eb3  jmp     loc_180005052
0x180004eb8  mov     rax, [rdi+0A8h]
0x180004ebf  movzx   ecx, word ptr [rax]
0x180004ec2  mov     eax, 4800001h
0x180004ec7  cmp     cx, r8w
0x180004ecb  jz      short loc_180004ECF
0x180004ecd  mov     eax, ecx
0x180004ecf  mov     [rsi+8], rax
0x180004ed3  xor     eax, eax
0x180004ed5  cmp     cx, r8w
0x180004ed9  mov     ebx, 10000h
0x180004ede  cmovnz  ebx, eax
0x180004ee1  jmp     loc_180005093
0x180004ee6  sub     eax, 4002h
0x180004eeb  jz      loc_18000507D
0x180004ef1  sub     eax, r8d
0x180004ef4  jz      loc_180005071
0x180004efa  sub     eax, r8d
0x180004efd  jz      loc_180005065
0x180004f03  sub     eax, r8d
0x180004f06  jz      loc_180005058
0x180004f0c  sub     eax, r8d
0x180004f0f  jz      loc_18000503D
0x180004f15  sub     eax, r8d
0x180004f18  jz      short loc_180004F4D
0x180004f1a  sub     eax, 3FBFF9h
0x180004f1f  jz      short loc_180004F31
0x180004f21  cmp     eax, 400000h
0x180004f26  jnz     loc_180004DBD
0x180004f2c  mov     edx, [rdi+24h]
0x180004f2f  jmp     short loc_180004F34
0x180004f31  mov     edx, [rdi+28h]
0x180004f34  or      ecx, 0FFFFFFFFh
0x180004f37  mov     eax, 481FFFFh
0x180004f3c  cmp     edx, ecx
0x180004f3e  jz      short loc_180004F43
0x180004f40  mov     rax, rdx
0x180004f43  mov     [rsi+8], rax
0x180004f47  xor     eax, eax
0x180004f49  cmp     edx, ecx
0x180004f4b  jmp     short loc_180004ED9
0x180004f4d  test    byte ptr [rdi+4], 40h
0x180004f51  jz      short loc_180004F8D
0x180004f53  cmp     dword ptr [rdi+20h], 2
0x180004f57  jz      short loc_180004F8D
0x180004f59  lea     rcx, CritSec; lpCriticalSection
0x180004f60  call    cs:__imp_LeaveCriticalSection
0x180004f66  mov     ecx, 0Ah; dwMilliseconds
0x180004f6b  call    cs:__imp_Sleep
0x180004f71  lea     rcx, CritSec; lpCriticalSection
0x180004f78  call    cs:__imp_EnterCriticalSection
0x180004f7e  cmp     dword ptr [rdi+20h], 2
0x180004f82  jnz     short loc_180004F59
0x180004f84  lea     r14, [rdi+20h]
0x180004f88  mov     rbp, r14
0x180004f8b  jmp     short loc_180004F9A
0x180004f8d  lea     r14, [rdi+20h]
0x180004f91  cmp     dword ptr [r14], 2
0x180004f95  mov     rbp, r14
0x180004f98  jnz     short loc_180004FD3
0x180004f9a  mov     ecx, [rdi+18h]; idThread
0x180004f9d  xor     r9d, r9d; lParam
0x180004fa0  xor     r8d, r8d; wParam
0x180004fa3  mov     [rdi+1Ch], ebx
0x180004fa6  mov     edx, 401h; Msg
0x180004fab  call    cs:__imp_PostThreadMessageW
0x180004fb1  mov     rcx, rdi
0x180004fb4  call    mwGetDevice
0x180004fb9  mov     ebx, eax
0x180004fbb  test    eax, eax
0x180004fbd  jnz     loc_180005093
0x180004fc3  mov     dword ptr [rdi+4], 2D00h
0x180004fca  mov     dword ptr [r14], 3
0x180004fd1  jmp     short loc_180004FEF
0x180004fd3  mov     edx, [rdi+4]
0x180004fd6  test    edx, 0C00h
0x180004fdc  setnz   cl
0x180004fdf  bt      edx, 0Dh
0x180004fe3  setb    al
0x180004fe6  test    al, cl
0x180004fe8  jz      short loc_180005036
0x180004fea  test    dl, 10h
0x180004fed  jnz     short loc_180005020
0x180004fef  cmp     dword ptr [rbp+0], 2
0x180004ff3  jz      short loc_180005020
0x180004ff5  lea     rcx, CritSec; lpCriticalSection
0x180004ffc  call    cs:__imp_LeaveCriticalSection
0x180005002  mov     ecx, 0Ah; dwMilliseconds
0x180005007  call    cs:__imp_Sleep
0x18000500d  lea     rcx, CritSec; lpCriticalSection
0x180005014  call    cs:__imp_EnterCriticalSection
0x18000501a  test    byte ptr [rdi+4], 10h
0x18000501e  jz      short loc_180004FEF
0x180005020  mov     eax, [rdi+8Ch]
0x180005026  test    eax, eax
0x180005028  jz      short loc_18000502E
0x18000502a  mov     ebx, eax
0x18000502c  jmp     short loc_180005093
0x18000502e  mov     eax, [rdi+88h]
0x180005034  jmp     short loc_180005052
0x180005036  mov     ebx, 142h
0x18000503b  jmp     short loc_180005093
0x18000503d  mov     rax, [rdi+0A8h]
0x180005044  cmp     [rax], r8w
0x180005048  jnz     loc_180004DBD
0x18000504e  movzx   eax, word ptr [rax+0Eh]
0x180005052  mov     [rsi+8], rax
0x180005056  jmp     short loc_180005093
0x180005058  mov     rax, [rdi+0A8h]
0x18000505f  movzx   ecx, word ptr [rax+0Ch]
0x180005063  jmp     short loc_180005088
0x180005065  mov     rax, [rdi+0A8h]
0x18000506c  mov     ecx, [rax+8]
0x18000506f  jmp     short loc_180005088
0x180005071  mov     rax, [rdi+0A8h]
0x180005078  mov     ecx, [rax+4]
0x18000507b  jmp     short loc_180005088
0x18000507d  mov     rax, [rdi+0A8h]
0x180005084  movzx   ecx, word ptr [rax+2]
0x180005088  mov     [rsi+8], rcx
0x18000508c  jmp     short loc_180005093
0x18000508e  mov     ebx, 111h
0x180005093  mov     eax, ebx
0x180005095  mov     rbx, [rsp+38h+arg_0]
0x18000509a  mov     rbp, [rsp+38h+arg_10]
0x18000509f  add     rsp, 20h
0x1800050a3  pop     r14
0x1800050a5  pop     rdi
0x1800050a6  pop     rsi
0x1800050a7  retn
```
