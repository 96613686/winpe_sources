# GetCommandLineArgumentsForTraceFileName(char *,char * * const,int,int)

- ea: `0x180012084`
- end: `0x18001214c`
- name: `?GetCommandLineArgumentsForTraceFileName@@YAHPEADQEAPEADHH@Z`
- size: `200`
- prototype: `__int64 __fastcall(char *, char **const)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180012154`

## callees

- `0x180012084`

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
0x180012084  mov     [rsp+arg_0], rbx
0x180012089  mov     [rsp+arg_8], rdi
0x18001208e  mov     rdi, rdx
0x180012091  mov     r9, rcx
0x180012094  test    rcx, rcx
0x180012097  jz      loc_18001213F
0x18001209d  mov     r8d, 104h
0x1800120a3  mov     rax, rcx
0x1800120a6  cmp     byte ptr [rax], 0
0x1800120a9  jz      short loc_1800120B4
0x1800120ab  inc     rax
0x1800120ae  sub     r8, 1
0x1800120b2  jnz     short loc_1800120A6
0x1800120b4  mov     ecx, 104h
0x1800120b9  mov     rax, r8
0x1800120bc  sub     rcx, r8
0x1800120bf  neg     rax
0x1800120c2  sbb     r10, r10
0x1800120c5  and     r10, rcx
0x1800120c8  test    r8, r8
0x1800120cb  jz      short loc_18001213F
0x1800120cd  xor     r8d, r8d
0x1800120d0  xor     edx, edx
0x1800120d2  xor     ebx, ebx
0x1800120d4  test    r10, r10
0x1800120d7  jz      short loc_180012107
0x1800120d9  cmp     edx, 104h
0x1800120df  jg      short loc_18001213F
0x1800120e1  mov     r11b, [r9]
0x1800120e4  cmp     r11b, 20h ; ' '
0x1800120e8  jnz     short loc_18001210C
0x1800120ea  test    edx, edx
0x1800120ec  jle     short loc_18001211C
0x1800120ee  movsxd  rax, r8d
0x1800120f1  inc     r8d
0x1800120f4  mov     rcx, [rdi+rax*8]
0x1800120f8  movsxd  rax, edx
0x1800120fb  xor     edx, edx
0x1800120fd  mov     byte ptr [rax+rcx], 0
0x180012101  cmp     r8d, 1
0x180012105  jnz     short loc_18001211C
0x180012107  mov     eax, r8d
0x18001210a  jmp     short loc_180012141
0x18001210c  movsxd  rcx, edx
0x18001210f  inc     edx
0x180012111  movsxd  rax, r8d
0x180012114  mov     rax, [rdi+rax*8]
0x180012118  mov     [rcx+rax], r11b
0x18001211c  inc     ebx
0x18001211e  inc     r9
0x180012121  mov     eax, ebx
0x180012123  cmp     rax, r10
0x180012126  jb      short loc_1800120D9
0x180012128  test    edx, edx
0x18001212a  jz      short loc_180012107
0x18001212c  movsxd  rcx, r8d
0x18001212f  inc     r8d
0x180012132  movsxd  rdx, edx
0x180012135  mov     rcx, [rdi+rcx*8]
0x180012139  mov     byte ptr [rdx+rcx], 0
0x18001213d  jmp     short loc_180012107
0x18001213f  xor     eax, eax
0x180012141  mov     rbx, [rsp+arg_0]
0x180012146  mov     rdi, [rsp+arg_8]
0x18001214b  retn
```
