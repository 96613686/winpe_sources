# SetupReadWriteExtraInfo

- ea: `0x140004080`
- end: `0x1400042f4`
- name: `SetupReadWriteExtraInfo`
- size: `628`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x140003910`

## callees

- `0x140004080`

## import_xrefs

- `ntoskrnl!IoGetAdapterCryptoEngineExtension` at `0x14000420e`
- `ntoskrnl!IoGetAdapterCryptoEngineExtension` at `0x14000420e`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140004231`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140004231`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14000415c`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x1400041f6`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14000415c`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x1400041f6`

## pseudocode

```c
char __fastcall SetupReadWriteExtraInfo(__int64 a1, __int64 a2)
{
  __int64 v3; // r8
  __int64 v4; // rax
  __int64 v5; // rcx
  unsigned int v6; // r9d
  unsigned int i; // r8d
  __int64 v8; // rdx
  __int64 v9; // rbx
  int v10; // eax
  int v11; // ecx
  __int64 v12; // rdx
  int v13; // ecx
  __int64 v14; // rsi
  char v15; // al
  char v16; // al
  int v18; // [rsp+40h] [rbp+8h] BYREF
  __int64 v19; // [rsp+48h] [rbp+10h] BYREF

  v3 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 64LL);
  v19 = 0;
  v4 = *(_QWORD *)(v3 + 528);
  if ( *(_BYTE *)(v4 + 30) == 1 )
  {
    v4 = *(_QWORD *)(v3 + 1160);
    if ( v4 )
    {
      if ( *(_DWORD *)(v4 + 4) >= 0x11u )
      {
        if ( *(_BYTE *)(v4 + 16) )
        {
          v5 = *(_QWORD *)(a1 + 288);
          if ( *(_BYTE *)(v5 + 2) == 40 )
          {
            v6 = *(_DWORD *)(v5 + 56);
            if ( v6 )
            {
              for ( i = 0; ; ++i )
              {
                if ( i >= v6 )
                  return v4;
                LOBYTE(v4) = i;
                v8 = *(unsigned int *)(v5 + 4LL * i + 120);
                if ( (unsigned int)v8 >= 0x80 && (unsigned int)v8 < *(_DWORD *)(v5 + 16) )
                {
                  v9 = v5 + v8;
                  if ( *(_DWORD *)(v5 + v8) == 128 )
                    break;
                }
              }
              if ( !v9 )
                return v4;
              v12 = *(_QWORD *)(a2 + 192);
              v13 = 0;
              v14 = *(_QWORD *)(a2 + 184);
              *(_DWORD *)(v9 + 8) = 0;
              if ( (*(_DWORD *)(a2 + 16) & 1) != 0 )
              {
                v13 = 1;
                *(_DWORD *)(v9 + 8) = 1;
              }
              if ( (*(_DWORD *)(a2 + 16) & 0x42) != 0 )
              {
                v13 |= 2u;
                *(_DWORD *)(v9 + 8) = v13;
              }
              if ( v12 )
              {
                if ( (*(_DWORD *)(v12 + 80) & 0x20) != 0 )
                  *(_DWORD *)(v9 + 8) |= 4u;
                if ( (*(_DWORD *)(v12 + 80) & 0x18000) != 0 )
                  *(_DWORD *)(v9 + 8) |= 8u;
                if ( (*(_DWORD *)(v12 + 80) & 0x10) != 0 )
                  *(_DWORD *)(v9 + 8) |= 0x10u;
              }
              else
              {
                *(_DWORD *)(v9 + 8) = v13 | 0x40;
              }
              v18 = 0;
              if ( (int)IoGetGenericIrpExtension(a2, &v18, 4) >= 0 && (v18 & 0x20) != 0 )
                *(_DWORD *)(v9 + 8) |= 0x20u;
              if ( (int)IoGetAdapterCryptoEngineExtension(a2, &v19) >= 0 )
                *(_DWORD *)(v9 + 8) |= 0x200u;
              v15 = (*(_DWORD *)(a2 + 16) >> 17) & 7;
              if ( v15 )
                v16 = v15 - 1;
              else
                v16 = 2;
              *(_BYTE *)(v9 + 22) = v16;
              if ( IoGetTopLevelIrp() == (PIRP)3 )
                *(_BYTE *)(v9 + 22) = 3;
              if ( !v14 )
              {
                *(_QWORD *)(v9 + 12) = 0;
                *(_BYTE *)(v9 + 20) = 0;
LABEL_18:
                v18 = 0;
                LODWORD(v4) = IoGetGenericIrpExtension(a2, &v18, 4);
                if ( (int)v4 >= 0 )
                {
                  LOBYTE(v4) = v18;
                  if ( (v18 & 0x10) != 0 )
                  {
                    *(_DWORD *)(v9 + 8) |= 0x80000000;
                    LOBYTE(v4) = v4 & 0xF;
                    *(_BYTE *)(v9 + 21) = v4;
                  }
                }
                return v4;
              }
              if ( *(_BYTE *)v14 == 3 )
              {
                v10 = *(_DWORD *)(v14 + 16);
                *(_DWORD *)(v9 + 12) = v10;
                v11 = *(_DWORD *)(v14 + 8);
              }
              else
              {
                if ( *(_BYTE *)v14 == 4 )
                {
                  v10 = *(_DWORD *)(v14 + 16);
                  *(_DWORD *)(v9 + 12) = v10;
                  v11 = *(_DWORD *)(v14 + 8);
                  *(_BYTE *)(v9 + 20) = 1;
LABEL_16:
                  *(_DWORD *)(v9 + 16) = v11;
                  if ( (v10 & 0xFFFF0000) == 0x56530000 )
                    *(_DWORD *)(v9 + 8) |= 0x80u;
                  goto LABEL_18;
                }
                *(_DWORD *)(v9 + 12) = 0;
                v11 = 0;
                v10 = 0;
              }
              *(_BYTE *)(v9 + 20) = 0;
              goto LABEL_16;
            }
          }
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x140004080  push    rbp
0x140004082  push    rdi
0x140004083  sub     rsp, 28h
0x140004087  mov     rax, [rcx+28h]
0x14000408b  xor     ebp, ebp
0x14000408d  mov     rdi, rdx
0x140004090  mov     r8, [rax+40h]
0x140004094  mov     [rsp+38h+arg_8], rbp
0x140004099  mov     rax, [r8+210h]
0x1400040a0  cmp     byte ptr [rax+1Eh], 1
0x1400040a4  jnz     loc_14000417A
0x1400040aa  mov     rax, [r8+488h]
0x1400040b1  test    rax, rax
0x1400040b4  jz      loc_14000417A
0x1400040ba  cmp     dword ptr [rax+4], 11h
0x1400040be  jb      loc_14000417A
0x1400040c4  cmp     [rax+10h], bpl
0x1400040c8  jz      loc_14000417A
0x1400040ce  mov     rcx, [rcx+120h]
0x1400040d5  cmp     byte ptr [rcx+2], 28h ; '('
0x1400040d9  jnz     loc_14000417A
0x1400040df  mov     r9d, [rcx+38h]
0x1400040e3  test    r9d, r9d
0x1400040e6  jz      loc_14000417A
0x1400040ec  mov     r8d, ebp
0x1400040ef  mov     [rsp+38h+arg_10], rbx
0x1400040f4  cmp     r8d, r9d
0x1400040f7  jnb     short loc_140004175
0x1400040f9  mov     eax, r8d
0x1400040fc  mov     edx, [rcx+rax*4+78h]
0x140004100  cmp     edx, 80h
0x140004106  jb      short loc_14000411A
0x140004108  cmp     edx, [rcx+10h]
0x14000410b  jnb     short loc_14000411A
0x14000410d  cmp     dword ptr [rcx+rdx], 80h
0x140004114  lea     rbx, [rcx+rdx]
0x140004118  jz      short loc_140004182
0x14000411a  inc     r8d
0x14000411d  jmp     short loc_1400040F4
0x14000411f  movzx   eax, byte ptr [rsi]
0x140004122  cmp     al, 3
0x140004124  jnz     loc_140004294
0x14000412a  mov     eax, [rsi+10h]
0x14000412d  mov     [rbx+0Ch], eax
0x140004130  mov     ecx, [rsi+8]
0x140004133  mov     [rbx+14h], bpl
0x140004137  and     eax, 0FFFF0000h
0x14000413c  mov     [rbx+10h], ecx
0x14000413f  cmp     eax, 56530000h
0x140004144  jz      loc_1400042B3
0x14000414a  mov     r8d, 4
0x140004150  mov     [rsp+38h+arg_0], ebp
0x140004154  lea     rdx, [rsp+38h+arg_0]
0x140004159  mov     rcx, rdi
0x14000415c  call    cs:__imp_IoGetGenericIrpExtension
0x140004163  nop     dword ptr [rax+rax+00h]
0x140004168  mov     rsi, [rsp+38h+var_18]
0x14000416d  test    eax, eax
0x14000416f  jns     loc_140004277
0x140004175  mov     rbx, [rsp+38h+arg_10]
0x14000417a  add     rsp, 28h
0x14000417e  pop     rdi
0x14000417f  pop     rbp
0x140004180  retn
0x140004182  test    rbx, rbx
0x140004185  jz      short loc_140004175
0x140004187  mov     rdx, [rdi+0C0h]
0x14000418e  mov     ecx, ebp
0x140004190  mov     [rsp+38h+var_18], rsi
0x140004195  mov     rsi, [rdi+0B8h]
0x14000419c  mov     [rbx+8], ebp
0x14000419f  mov     eax, [rdi+10h]
0x1400041a2  test    al, 1
0x1400041a4  jz      short loc_1400041AE
0x1400041a6  mov     ecx, 1
0x1400041ab  mov     [rbx+8], ecx
0x1400041ae  mov     eax, [rdi+10h]
0x1400041b1  test    al, 42h
0x1400041b3  jz      short loc_1400041BB
0x1400041b5  or      ecx, 2
0x1400041b8  mov     [rbx+8], ecx
0x1400041bb  test    rdx, rdx
0x1400041be  jz      loc_1400042C8
0x1400041c4  mov     eax, [rdx+50h]
0x1400041c7  test    al, 20h
0x1400041c9  jnz     loc_1400042BF
0x1400041cf  mov     eax, [rdx+50h]
0x1400041d2  test    eax, 18000h
0x1400041d7  jnz     loc_1400042AA
0x1400041dd  mov     eax, [rdx+50h]
0x1400041e0  test    al, 10h
0x1400041e2  jnz     short loc_140004261
0x1400041e4  mov     r8d, 4
0x1400041ea  mov     [rsp+38h+arg_0], ebp
0x1400041ee  lea     rdx, [rsp+38h+arg_0]
0x1400041f3  mov     rcx, rdi
0x1400041f6  call    cs:__imp_IoGetGenericIrpExtension
0x1400041fd  nop     dword ptr [rax+rax+00h]
0x140004202  test    eax, eax
0x140004204  jns     short loc_14000426A
0x140004206  lea     rdx, [rsp+38h+arg_8]
0x14000420b  mov     rcx, rdi
0x14000420e  call    cs:__imp_IoGetAdapterCryptoEngineExtension
0x140004215  nop     dword ptr [rax+rax+00h]
0x14000421a  test    eax, eax
0x14000421c  jns     loc_1400042DF
0x140004222  mov     eax, [rdi+10h]
0x140004225  shr     eax, 11h
0x140004228  and     al, 7
0x14000422a  jz      short loc_14000425D
0x14000422c  dec     al
0x14000422e  mov     [rbx+16h], al
0x140004231  call    cs:__imp_IoGetTopLevelIrp
0x140004238  nop     dword ptr [rax+rax+00h]
0x14000423d  cmp     rax, 3
0x140004241  jz      loc_1400042EB
0x140004247  test    rsi, rsi
0x14000424a  jnz     loc_14000411F
0x140004250  mov     [rbx+0Ch], rbp
0x140004254  mov     [rbx+14h], bpl
0x140004258  jmp     loc_14000414A
0x14000425d  mov     al, 2
0x14000425f  jmp     short loc_14000422E
0x140004261  or      dword ptr [rbx+8], 10h
0x140004265  jmp     loc_1400041E4
0x14000426a  test    byte ptr [rsp+38h+arg_0], 20h
0x14000426f  jz      short loc_140004206
0x140004271  or      dword ptr [rbx+8], 20h
0x140004275  jmp     short loc_140004206
0x140004277  mov     eax, [rsp+38h+arg_0]
0x14000427b  test    al, 10h
0x14000427d  jz      loc_140004175
0x140004283  or      dword ptr [rbx+8], 80000000h
0x14000428a  and     al, 0Fh
0x14000428c  mov     [rbx+15h], al
0x14000428f  jmp     loc_140004175
0x140004294  cmp     al, 4
0x140004296  jnz     short loc_1400042D3
0x140004298  mov     eax, [rsi+10h]
0x14000429b  mov     [rbx+0Ch], eax
0x14000429e  mov     ecx, [rsi+8]
0x1400042a1  mov     byte ptr [rbx+14h], 1
0x1400042a5  jmp     loc_140004137
0x1400042aa  or      dword ptr [rbx+8], 8
0x1400042ae  jmp     loc_1400041DD
0x1400042b3  or      dword ptr [rbx+8], 80h
0x1400042ba  jmp     loc_14000414A
0x1400042bf  or      dword ptr [rbx+8], 4
0x1400042c3  jmp     loc_1400041CF
0x1400042c8  or      ecx, 40h
0x1400042cb  mov     [rbx+8], ecx
0x1400042ce  jmp     loc_1400041E4
0x1400042d3  mov     [rbx+0Ch], ebp
0x1400042d6  mov     ecx, ebp
0x1400042d8  mov     eax, ebp
0x1400042da  jmp     loc_140004133
0x1400042df  or      dword ptr [rbx+8], 200h
0x1400042e6  jmp     loc_140004222
0x1400042eb  mov     byte ptr [rbx+16h], 3
0x1400042ef  jmp     loc_140004247
```
