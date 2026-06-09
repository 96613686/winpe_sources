# ConfigApplyBounds

- ea: `0x14000a81c`
- end: `0x14000a9f4`
- name: `ConfigApplyBounds`
- size: `472`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140002670`
- `0x14000b1c0`

## callees

- `0x14000a81c`

## import_xrefs

- `ntoskrnl!KeQueryActiveProcessorCount` at `0x14000a99b`
- `ntoskrnl!KeQueryActiveProcessorCount` at `0x14000a99b`

## pseudocode

```c
__int64 ConfigApplyBounds()
{
  __int64 i; // rdi
  unsigned int v1; // edx
  __int64 v2; // rbx
  unsigned int v3; // ecx
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // r10d
  unsigned int v9; // eax
  unsigned int v10; // r8d
  unsigned int v11; // edx
  unsigned int v12; // ecx
  unsigned int v13; // r9d
  unsigned int v14; // eax
  unsigned int v15; // ecx
  int v16; // ecx
  __int64 result; // rax

  for ( i = 0; i != 3; ++i )
  {
    v1 = g_actualHardwareThreads;
    v2 = i << 6;
    if ( !g_actualHardwareThreads )
      v1 = 4;
    v3 = 0;
    if ( *(int *)((char *)g_config + v2) )
      v3 = *(int *)((char *)g_config + v2);
    if ( v3 < v1 )
      v1 = v3;
    *(int *)((char *)g_config + v2) = v1;
    v4 = *(int *)((char *)&g_config[1] + v2);
    if ( v4 > 0x40 )
    {
      if ( v4 >= 0x100000 )
        v4 = 0x100000;
    }
    else
    {
      v4 = 64;
    }
    *(int *)((char *)&g_config[1] + v2) = v4 & 0xFFFFFFC0;
    v5 = *(int *)((char *)&g_config[2] + v2);
    if ( v5 > 0x40 )
    {
      if ( v5 >= 0x100000 )
        v5 = 0x100000;
    }
    else
    {
      v5 = 64;
    }
    *(int *)((char *)&g_config[2] + v2) = v5 & 0xFFFFFFC0;
    v6 = *(int *)((char *)&g_config[3] + v2);
    if ( v6 > 0x40 )
    {
      if ( v6 >= 0x100000 )
        v6 = 0x100000;
    }
    else
    {
      v6 = 64;
    }
    *(int *)((char *)&g_config[3] + v2) = v6 & 0xFFFFFFC0;
    v7 = *(int *)((char *)&g_config[4] + v2);
    if ( v7 > 1 )
    {
      if ( v7 == -1 )
        v7 = -1;
    }
    else
    {
      v7 = 1;
    }
    v8 = 0;
    *(int *)((char *)&g_config[4] + v2) = v7;
    if ( *(int *)((char *)&g_config[7] + v2) )
      v8 = *(int *)((char *)&g_config[7] + v2);
    if ( v8 >= 8 )
      v8 = 8;
    *(int *)((char *)&g_config[7] + v2) = v8;
    v9 = *(int *)((char *)&g_config[8] + v2);
    if ( v9 > 0x400 )
    {
      if ( v9 >= 0x100000 )
        v9 = 0x100000;
    }
    else
    {
      v9 = 1024;
    }
    v10 = 0;
    *(int *)((char *)&g_config[8] + v2) = v9 & 0xFFFFFFF0;
    v11 = *(int *)((char *)&g_config[2] + v2);
    v12 = *(int *)((char *)&g_config[3] + v2);
    if ( *(int *)((char *)&g_config[9] + v2) )
      v10 = *(int *)((char *)&g_config[9] + v2);
    if ( v10 >= 8 )
      v10 = 8;
    v13 = 0;
    if ( *(int *)((char *)&g_config[10] + v2) )
      v13 = *(int *)((char *)&g_config[10] + v2);
    v14 = *(int *)((char *)&g_config[1] + v2);
    if ( v13 >= 0x1000 )
      v13 = 4096;
    if ( v12 <= v11 )
      v12 = *(int *)((char *)&g_config[2] + v2);
    *(int *)((char *)&g_config[3] + v2) = v12;
    if ( v14 <= v11 )
      v14 = v11;
    if ( v14 < v12 )
      v12 = v14;
    *(int *)((char *)&g_config[1] + v2) = v12;
    v15 = *(int *)((char *)&g_config[14] + v2);
    if ( v10 >= v8 )
      v10 = v8;
    *(int *)((char *)&g_config[9] + v2) = v10;
    if ( v15 >= v8 )
      v15 = v8;
    *(int *)((char *)&g_config[14] + v2) = v15;
    if ( v13 >= v11 )
      v13 = v11;
    *(int *)((char *)&g_config[10] + v2) = v13;
    *(int *)((char *)&g_config[13] + v2) = (v8 << 16) / *(int *)((char *)&g_config[4] + v2);
    if ( !v15 )
      *(int *)((char *)&g_config[14] + v2) = (KeQueryActiveProcessorCount(0) + 1) >> 1;
    v16 = *(int *)((char *)g_config + v2);
    if ( !(*(int *)((char *)&g_config[7] + v2) | v16) )
      *(int *)((char *)&g_config[7] + v2) = 1;
    result = (unsigned int)((1 << v16) - 1);
    *(int *)((char *)&g_config[12] + v2) = result;
  }
  return result;
}

```

## disassembly

```asm
0x14000a81c  push    rbx
0x14000a81e  push    rbp
0x14000a81f  push    rsi
0x14000a820  push    rdi
0x14000a821  push    r13
0x14000a823  sub     rsp, 20h
0x14000a827  xor     edi, edi
0x14000a829  mov     ebp, 100000h
0x14000a82e  or      r8d, 0FFFFFFFFh
0x14000a832  mov     r11d, 1000h
0x14000a838  lea     r13d, [rdi+8]
0x14000a83c  mov     edx, cs:g_actualHardwareThreads
0x14000a842  lea     rsi, g_config
0x14000a849  mov     eax, 4
0x14000a84e  mov     rbx, rdi
0x14000a851  shl     rbx, 6
0x14000a855  test    edx, edx
0x14000a857  cmovz   edx, eax
0x14000a85a  xor     ecx, ecx
0x14000a85c  mov     eax, [rbx+rsi]
0x14000a85f  test    eax, eax
0x14000a861  cmovnz  ecx, eax
0x14000a864  cmp     ecx, edx
0x14000a866  cmovb   edx, ecx
0x14000a869  mov     [rbx+rsi], edx
0x14000a86c  mov     eax, [rbx+rsi+4]
0x14000a870  cmp     eax, 40h ; '@'
0x14000a873  ja      short loc_14000A87C
0x14000a875  mov     eax, 40h ; '@'
0x14000a87a  jmp     short loc_14000A881
0x14000a87c  cmp     eax, ebp
0x14000a87e  cmovnb  eax, ebp
0x14000a881  and     eax, 0FFFFFFC0h
0x14000a884  mov     [rbx+rsi+4], eax
0x14000a888  mov     eax, [rbx+rsi+8]
0x14000a88c  cmp     eax, 40h ; '@'
0x14000a88f  ja      short loc_14000A898
0x14000a891  mov     eax, 40h ; '@'
0x14000a896  jmp     short loc_14000A89D
0x14000a898  cmp     eax, ebp
0x14000a89a  cmovnb  eax, ebp
0x14000a89d  and     eax, 0FFFFFFC0h
0x14000a8a0  mov     [rbx+rsi+8], eax
0x14000a8a4  mov     eax, [rbx+rsi+0Ch]
0x14000a8a8  cmp     eax, 40h ; '@'
0x14000a8ab  ja      short loc_14000A8B4
0x14000a8ad  mov     eax, 40h ; '@'
0x14000a8b2  jmp     short loc_14000A8B9
0x14000a8b4  cmp     eax, ebp
0x14000a8b6  cmovnb  eax, ebp
0x14000a8b9  and     eax, 0FFFFFFC0h
0x14000a8bc  mov     [rbx+rsi+0Ch], eax
0x14000a8c0  mov     eax, [rbx+rsi+10h]
0x14000a8c4  cmp     eax, 1
0x14000a8c7  ja      short loc_14000A8D0
0x14000a8c9  mov     eax, 1
0x14000a8ce  jmp     short loc_14000A8D7
0x14000a8d0  cmp     eax, r8d
0x14000a8d3  cmovnb  eax, r8d
0x14000a8d7  xor     r10d, r10d
0x14000a8da  mov     [rbx+rsi+10h], eax
0x14000a8de  mov     eax, [rbx+rsi+1Ch]
0x14000a8e2  test    eax, eax
0x14000a8e4  cmovnz  r10d, eax
0x14000a8e8  cmp     r10d, r13d
0x14000a8eb  cmovnb  r10d, r13d
0x14000a8ef  mov     [rbx+rsi+1Ch], r10d
0x14000a8f4  mov     eax, [rbx+rsi+20h]
0x14000a8f8  cmp     eax, 400h
0x14000a8fd  ja      short loc_14000A906
0x14000a8ff  mov     eax, 400h
0x14000a904  jmp     short loc_14000A90B
0x14000a906  cmp     eax, ebp
0x14000a908  cmovnb  eax, ebp
0x14000a90b  and     eax, 0FFFFFFF0h
0x14000a90e  xor     r8d, r8d
0x14000a911  mov     [rbx+rsi+20h], eax
0x14000a915  mov     eax, [rbx+rsi+24h]
0x14000a919  test    eax, eax
0x14000a91b  mov     edx, [rbx+rsi+8]
0x14000a91f  mov     ecx, [rbx+rsi+0Ch]
0x14000a923  cmovnz  r8d, eax
0x14000a927  mov     eax, [rbx+rsi+28h]
0x14000a92b  cmp     r8d, r13d
0x14000a92e  cmovnb  r8d, r13d
0x14000a932  xor     r9d, r9d
0x14000a935  test    eax, eax
0x14000a937  cmovnz  r9d, eax
0x14000a93b  mov     eax, [rbx+rsi+4]
0x14000a93f  cmp     r9d, r11d
0x14000a942  cmovnb  r9d, r11d
0x14000a946  cmp     ecx, edx
0x14000a948  cmovbe  ecx, edx
0x14000a94b  cmp     eax, edx
0x14000a94d  mov     [rbx+rsi+0Ch], ecx
0x14000a951  cmovbe  eax, edx
0x14000a954  cmp     eax, ecx
0x14000a956  cmovb   ecx, eax
0x14000a959  cmp     r8d, r10d
0x14000a95c  mov     [rbx+rsi+4], ecx
0x14000a960  mov     ecx, [rbx+rsi+38h]
0x14000a964  cmovnb  r8d, r10d
0x14000a968  cmp     ecx, r10d
0x14000a96b  mov     [rbx+rsi+24h], r8d
0x14000a970  cmovnb  ecx, r10d
0x14000a974  cmp     r9d, edx
0x14000a977  mov     [rbx+rsi+38h], ecx
0x14000a97b  cmovnb  r9d, edx
0x14000a97f  shl     r10d, 10h
0x14000a983  xor     edx, edx
0x14000a985  mov     [rbx+rsi+28h], r9d
0x14000a98a  mov     eax, r10d
0x14000a98d  div     dword ptr [rbx+rsi+10h]
0x14000a991  mov     [rbx+rsi+34h], eax
0x14000a995  test    ecx, ecx
0x14000a997  jnz     short loc_14000A9B5
0x14000a999  xor     ecx, ecx; ActiveProcessors
0x14000a99b  call    cs:__imp_KeQueryActiveProcessorCount
0x14000a9a2  nop     dword ptr [rax+rax+00h]
0x14000a9a7  inc     eax
0x14000a9a9  mov     r11d, 1000h
0x14000a9af  shr     eax, 1
0x14000a9b1  mov     [rbx+rsi+38h], eax
0x14000a9b5  mov     ecx, [rbx+rsi]
0x14000a9b8  mov     eax, ecx
0x14000a9ba  or      eax, [rbx+rsi+1Ch]
0x14000a9be  jnz     short loc_14000A9C8
0x14000a9c0  mov     dword ptr [rbx+rsi+1Ch], 1
0x14000a9c8  mov     eax, 1
0x14000a9cd  inc     rdi
0x14000a9d0  shl     eax, cl
0x14000a9d2  mov     r8d, 0FFFFFFFFh
0x14000a9d8  dec     eax
0x14000a9da  mov     [rbx+rsi+30h], eax
0x14000a9de  cmp     rdi, 3
0x14000a9e2  jnz     loc_14000A83C
0x14000a9e8  add     rsp, 20h
0x14000a9ec  pop     r13
0x14000a9ee  pop     rdi
0x14000a9ef  pop     rsi
0x14000a9f0  pop     rbp
0x14000a9f1  pop     rbx
0x14000a9f2  retn
```
