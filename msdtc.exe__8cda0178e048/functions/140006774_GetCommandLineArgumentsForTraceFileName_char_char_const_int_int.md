# GetCommandLineArgumentsForTraceFileName(char *,char * * const,int,int)

- ea: `0x140006774`
- end: `0x14000683c`
- name: `?GetCommandLineArgumentsForTraceFileName@@YAHPEADQEAPEADHH@Z`
- size: `200`
- prototype: `__int64 __fastcall(char *, char **const)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140006844`

## callees

- `0x140006774`

## pseudocode

```c
__int64 __fastcall GetCommandLineArgumentsForTraceFileName(char *a1, char **const a2)
{
  char *v3; // r9
  __int64 v4; // r8
  char *v5; // rax
  unsigned __int64 v6; // r10
  unsigned int v7; // r8d
  int v8; // edx
  unsigned int v9; // ebx
  __int64 v10; // rax
  char *v11; // rcx
  __int64 v12; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx

  v3 = a1;
  if ( a1 )
  {
    v4 = 260;
    v5 = a1;
    do
    {
      if ( !*v5 )
        break;
      ++v5;
      --v4;
    }
    while ( v4 );
    v6 = (260 - v4) & -(__int64)(v4 != 0);
    if ( v4 )
    {
      v7 = 0;
      v8 = 0;
      v9 = 0;
      if ( !v6 )
        return v7;
      while ( v8 <= 260 )
      {
        if ( *v3 == 32 )
        {
          if ( v8 > 0 )
          {
            v10 = (int)v7++;
            v11 = a2[v10];
            v12 = v8;
            v8 = 0;
            v11[v12] = 0;
            if ( v7 == 1 )
              return v7;
          }
        }
        else
        {
          v14 = v8++;
          a2[v7][v14] = *v3;
        }
        ++v9;
        ++v3;
        if ( v9 >= v6 )
        {
          if ( v8 )
          {
            v15 = (int)v7++;
            a2[v15][v8] = 0;
          }
          return v7;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140006774  mov     [rsp+arg_0], rbx
0x140006779  mov     [rsp+arg_8], rdi
0x14000677e  mov     rdi, rdx
0x140006781  mov     r9, rcx
0x140006784  test    rcx, rcx
0x140006787  jz      loc_14000682F
0x14000678d  mov     r8d, 104h
0x140006793  mov     rax, rcx
0x140006796  cmp     byte ptr [rax], 0
0x140006799  jz      short loc_1400067A4
0x14000679b  inc     rax
0x14000679e  sub     r8, 1
0x1400067a2  jnz     short loc_140006796
0x1400067a4  mov     ecx, 104h
0x1400067a9  mov     rax, r8
0x1400067ac  sub     rcx, r8
0x1400067af  neg     rax
0x1400067b2  sbb     r10, r10
0x1400067b5  and     r10, rcx
0x1400067b8  test    r8, r8
0x1400067bb  jz      short loc_14000682F
0x1400067bd  xor     r8d, r8d
0x1400067c0  xor     edx, edx
0x1400067c2  xor     ebx, ebx
0x1400067c4  test    r10, r10
0x1400067c7  jz      short loc_1400067F7
0x1400067c9  cmp     edx, 104h
0x1400067cf  jg      short loc_14000682F
0x1400067d1  mov     r11b, [r9]
0x1400067d4  cmp     r11b, 20h ; ' '
0x1400067d8  jnz     short loc_1400067FC
0x1400067da  test    edx, edx
0x1400067dc  jle     short loc_14000680C
0x1400067de  movsxd  rax, r8d
0x1400067e1  inc     r8d
0x1400067e4  mov     rcx, [rdi+rax*8]
0x1400067e8  movsxd  rax, edx
0x1400067eb  xor     edx, edx
0x1400067ed  mov     byte ptr [rax+rcx], 0
0x1400067f1  cmp     r8d, 1
0x1400067f5  jnz     short loc_14000680C
0x1400067f7  mov     eax, r8d
0x1400067fa  jmp     short loc_140006831
0x1400067fc  movsxd  rcx, edx
0x1400067ff  inc     edx
0x140006801  movsxd  rax, r8d
0x140006804  mov     rax, [rdi+rax*8]
0x140006808  mov     [rcx+rax], r11b
0x14000680c  inc     ebx
0x14000680e  inc     r9
0x140006811  mov     eax, ebx
0x140006813  cmp     rax, r10
0x140006816  jb      short loc_1400067C9
0x140006818  test    edx, edx
0x14000681a  jz      short loc_1400067F7
0x14000681c  movsxd  rcx, r8d
0x14000681f  inc     r8d
0x140006822  movsxd  rdx, edx
0x140006825  mov     rcx, [rdi+rcx*8]
0x140006829  mov     byte ptr [rdx+rcx], 0
0x14000682d  jmp     short loc_1400067F7
0x14000682f  xor     eax, eax
0x140006831  mov     rbx, [rsp+arg_0]
0x140006836  mov     rdi, [rsp+arg_8]
0x14000683b  retn
```
