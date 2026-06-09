# MVarTable::CacheTagDelta(tagNORMALIZEDVECTOR *)

- ea: `0x140001c9c`
- end: `0x140002027`
- name: `?CacheTagDelta@MVarTable@@QEAAXPEAUtagNORMALIZEDVECTOR@@@Z`
- size: `907`
- prototype: `void(MVarTable *__hidden this, struct tagNORMALIZEDVECTOR *)`
- caller_count: `4`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x140001384`
- `0x140001890`
- `0x140002a68`
- `0x140035de4`

## callees

- `0x140001c9c`
- `0x1400022c4`

## pseudocode

```c
void __fastcall MVarTable::CacheTagDelta(MVarTable *this, struct tagNORMALIZEDVECTOR *a2)
{
  __int64 v2; // rsi
  unsigned int v3; // r15d
  int v6; // r12d
  unsigned int v7; // r14d
  unsigned int v8; // ebp
  __int64 v9; // rcx
  __int64 v10; // rbx
  unsigned __int16 ItemDelta; // ax
  unsigned int v12; // edx
  unsigned int v13; // edx
  unsigned int v14; // edx
  unsigned int v15; // edx
  unsigned int v16; // edx
  unsigned int v17; // edx
  unsigned int v18; // edx
  unsigned int v19; // edx
  unsigned int v20; // edx
  unsigned int v21; // edx
  unsigned int v22; // edx
  unsigned int v23; // edx
  unsigned int v24; // edx
  unsigned int v25; // edx
  unsigned int v26; // edx
  unsigned int v27; // edx
  unsigned int v28; // edx
  unsigned int v29; // edx
  unsigned int v30; // edx
  unsigned int v31; // edx
  unsigned int v32; // edx
  unsigned int v33; // edx
  unsigned int v34; // edx
  unsigned int v35; // edx
  unsigned int v36; // edx
  unsigned int v37; // edx
  unsigned int v38; // edx
  unsigned int v39; // edx
  unsigned int v40; // edx
  unsigned int v41; // edx
  unsigned int v42; // edx
  unsigned int v43; // edx

  v2 = *(_QWORD *)this;
  v3 = 0;
  v6 = (*(unsigned __int8 *)(*(_QWORD *)this + 6LL) << 8) | *(unsigned __int8 *)(*(_QWORD *)this + 7LL);
  v7 = (*(unsigned __int8 *)(*(_QWORD *)this + 8LL) << 8) | *(unsigned __int8 *)(*(_QWORD *)this + 9LL);
  v8 = *(unsigned __int8 *)(*(_QWORD *)this + 11LL) | (*(unsigned __int8 *)(*(_QWORD *)this + 10LL) << 8);
  if ( v7 )
  {
    v9 = v8;
    do
    {
      v10 = v6 * v3;
      ItemDelta = VariationStoreGetItemDelta(
                    (unsigned __int8 *)(*(_QWORD *)this + v9),
                    *((_DWORD *)this + 2) - v8,
                    a2,
                    *(unsigned __int8 *)(v10 + v2 + 17) | (*(unsigned __int8 *)(v10 + v2 + 16) << 8),
                    *(unsigned __int8 *)(v10 + v2 + 19) | (*(unsigned __int8 *)(v10 + v2 + 18) << 8));
      v12 = *(unsigned __int8 *)(v10 + v2 + 15)
          | ((*(unsigned __int8 *)(v10 + v2 + 14)
            | ((*(unsigned __int8 *)(v10 + v2 + 13) | (*(unsigned __int8 *)(v10 + v2 + 12) << 8)) << 8)) << 8);
      if ( v12 <= 0x7362786F )
      {
        if ( v12 == 1935833199 )
        {
          *((_WORD *)this + 25) = ItemDelta;
        }
        else if ( v12 > 0x67737038 )
        {
          v36 = v12 - 1735618617;
          if ( v36 )
          {
            v37 = v36 - 15598378;
            if ( v37 )
            {
              v38 = v37 - 129278;
              if ( v38 )
              {
                v39 = v38 - 3;
                if ( v39 )
                {
                  v40 = v39 - 770;
                  if ( v40 )
                  {
                    v41 = v40 - 776;
                    if ( v41 )
                    {
                      v42 = v41 - 5;
                      if ( v42 )
                      {
                        v43 = v42 - 65776;
                        if ( v43 )
                        {
                          if ( v43 == 521229 )
                            *((_WORD *)this + 9) = ItemDelta;
                        }
                        else
                        {
                          *((_WORD *)this + 8) = ItemDelta;
                        }
                      }
                      else
                      {
                        *((_WORD *)this + 15) = ItemDelta;
                      }
                    }
                    else
                    {
                      *((_WORD *)this + 16) = ItemDelta;
                    }
                  }
                  else
                  {
                    *((_WORD *)this + 17) = ItemDelta;
                  }
                }
                else
                {
                  *((_WORD *)this + 11) = ItemDelta;
                }
              }
              else
              {
                *((_WORD *)this + 10) = ItemDelta;
              }
            }
            else
            {
              *((_WORD *)this + 7) = ItemDelta;
            }
          }
          else
          {
            *((_WORD *)this + 44) = ItemDelta;
          }
        }
        else if ( v12 == 1735618616 )
        {
          *((_WORD *)this + 43) = ItemDelta;
        }
        else
        {
          v20 = v12 - 1668311156;
          if ( v20 )
          {
            v29 = v20 - 67307452;
            if ( v29 )
            {
              v30 = v29 - 1;
              if ( v30 )
              {
                v31 = v30 - 1;
                if ( v31 )
                {
                  v32 = v31 - 1;
                  if ( v32 )
                  {
                    v33 = v32 - 1;
                    if ( v33 )
                    {
                      v34 = v33 - 1;
                      if ( v34 )
                      {
                        v35 = v34 - 1;
                        if ( v35 )
                        {
                          if ( v35 == 1 )
                            *((_WORD *)this + 42) = ItemDelta;
                        }
                        else
                        {
                          *((_WORD *)this + 41) = ItemDelta;
                        }
                      }
                      else
                      {
                        *((_WORD *)this + 40) = ItemDelta;
                      }
                    }
                    else
                    {
                      *((_WORD *)this + 39) = ItemDelta;
                    }
                  }
                  else
                  {
                    *((_WORD *)this + 38) = ItemDelta;
                  }
                }
                else
                {
                  *((_WORD *)this + 37) = ItemDelta;
                }
              }
              else
              {
                *((_WORD *)this + 36) = ItemDelta;
              }
            }
            else
            {
              *((_WORD *)this + 35) = ItemDelta;
            }
          }
          else
          {
            *((_WORD *)this + 22) = ItemDelta;
          }
        }
      }
      else if ( v12 <= 0x756E646F )
      {
        if ( v12 == 1970168943 )
        {
          *((_WORD *)this + 34) = ItemDelta;
        }
        else
        {
          v21 = v12 - 1935833203;
          if ( v21 )
          {
            v22 = v21 - 252;
            if ( v22 )
            {
              v23 = v22 - 4;
              if ( v23 )
              {
                v24 = v23 - 917244;
                if ( v24 )
                {
                  v25 = v24 - 4;
                  if ( v25 )
                  {
                    v26 = v25 - 252;
                    if ( v26 )
                    {
                      v27 = v26 - 4;
                      if ( v27 )
                      {
                        v28 = v27 - 260348;
                        if ( v28 )
                        {
                          if ( v28 == 4 )
                            *((_WORD *)this + 31) = ItemDelta;
                        }
                        else
                        {
                          *((_WORD *)this + 32) = ItemDelta;
                        }
                      }
                      else
                      {
                        *((_WORD *)this + 28) = ItemDelta;
                      }
                    }
                    else
                    {
                      *((_WORD *)this + 30) = ItemDelta;
                    }
                  }
                  else
                  {
                    *((_WORD *)this + 27) = ItemDelta;
                  }
                }
                else
                {
                  *((_WORD *)this + 29) = ItemDelta;
                }
              }
              else
              {
                *((_WORD *)this + 24) = ItemDelta;
              }
            }
            else
            {
              *((_WORD *)this + 26) = ItemDelta;
            }
          }
          else
          {
            *((_WORD *)this + 23) = ItemDelta;
          }
        }
      }
      else
      {
        v13 = v12 - 1970168947;
        if ( v13 )
        {
          v14 = v13 - 15929072;
          if ( v14 )
          {
            v15 = v14 - 130051;
            if ( v15 )
            {
              v16 = v15 - 776;
              if ( v16 )
              {
                v17 = v16 - 5;
                if ( v17 )
                {
                  v18 = v17 - 65776;
                  if ( v18 )
                  {
                    v19 = v18 - 521229;
                    if ( v19 )
                    {
                      if ( v19 == 33292292 )
                        *((_WORD *)this + 21) = ItemDelta;
                    }
                    else
                    {
                      *((_WORD *)this + 14) = ItemDelta;
                    }
                  }
                  else
                  {
                    *((_WORD *)this + 13) = ItemDelta;
                  }
                }
                else
                {
                  *((_WORD *)this + 18) = ItemDelta;
                }
              }
              else
              {
                *((_WORD *)this + 19) = ItemDelta;
              }
            }
            else
            {
              *((_WORD *)this + 20) = ItemDelta;
            }
          }
          else
          {
            *((_WORD *)this + 12) = ItemDelta;
          }
        }
        else
        {
          *((_WORD *)this + 33) = ItemDelta;
        }
      }
      ++v3;
      v9 = v8;
    }
    while ( v3 < v7 );
  }
}

```

## disassembly

```asm
0x140001c9c  push    rbx
0x140001c9e  push    rbp
0x140001c9f  push    rsi
0x140001ca0  push    rdi
0x140001ca1  push    r12
0x140001ca3  push    r13
0x140001ca5  push    r14
0x140001ca7  push    r15
0x140001ca9  sub     rsp, 38h
0x140001cad  mov     rsi, [rcx]
0x140001cb0  xor     r15d, r15d
0x140001cb3  mov     r13, rdx
0x140001cb6  mov     rdi, rcx
0x140001cb9  movzx   eax, byte ptr [rsi+6]
0x140001cbd  movzx   r12d, byte ptr [rsi+7]
0x140001cc2  movzx   r14d, byte ptr [rsi+9]
0x140001cc7  movzx   ebp, byte ptr [rsi+0Ah]
0x140001ccb  shl     eax, 8
0x140001cce  or      r12d, eax
0x140001cd1  shl     ebp, 8
0x140001cd4  movzx   eax, byte ptr [rsi+8]
0x140001cd8  shl     eax, 8
0x140001cdb  or      r14d, eax
0x140001cde  movzx   eax, byte ptr [rsi+0Bh]
0x140001ce2  or      ebp, eax
0x140001ce4  test    r14d, r14d
0x140001ce7  jz      loc_140001DD9
0x140001ced  mov     ecx, ebp
0x140001cef  mov     edx, [rdi+8]
0x140001cf2  mov     eax, r15d
0x140001cf5  add     rcx, [rdi]; unsigned __int8 *
0x140001cf8  sub     edx, ebp; unsigned int
0x140001cfa  imul    eax, r12d
0x140001cfe  mov     ebx, eax
0x140001d00  movzx   r8d, byte ptr [rax+rsi+12h]
0x140001d06  movzx   eax, byte ptr [rax+rsi+13h]
0x140001d0b  movzx   r9d, byte ptr [rbx+rsi+10h]
0x140001d11  shl     r8d, 8
0x140001d15  or      r8d, eax
0x140001d18  shl     r9d, 8
0x140001d1c  movzx   eax, byte ptr [rbx+rsi+11h]
0x140001d21  mov     [rsp+78h+var_58], r8d; unsigned int
0x140001d26  or      r9d, eax; unsigned int
0x140001d29  mov     r8, r13; struct tagNORMALIZEDVECTOR *
0x140001d2c  call    ?VariationStoreGetItemDelta@@YAGPEAEIPEAUtagNORMALIZEDVECTOR@@II@Z; VariationStoreGetItemDelta(uchar *,uint,tagNORMALIZEDVECTOR *,uint,uint)
0x140001d31  movzx   ecx, byte ptr [rbx+rsi+0Dh]
0x140001d36  movzx   edx, byte ptr [rbx+rsi+0Ch]
0x140001d3b  shl     edx, 8
0x140001d3e  or      edx, ecx
0x140001d40  movzx   ecx, byte ptr [rbx+rsi+0Eh]
0x140001d45  shl     edx, 8
0x140001d48  or      edx, ecx
0x140001d4a  movzx   ecx, byte ptr [rbx+rsi+0Fh]
0x140001d4f  shl     edx, 8
0x140001d52  or      edx, ecx
0x140001d54  mov     ecx, 7362786Fh
0x140001d59  cmp     edx, ecx
0x140001d5b  jbe     loc_140001DEA
0x140001d61  mov     ecx, 756E646Fh
0x140001d66  cmp     edx, ecx
0x140001d68  jbe     loc_140001E11
0x140001d6e  sub     edx, 756E6473h
0x140001d74  jz      loc_140001E19
0x140001d7a  sub     edx, 0F30EF0h
0x140001d80  jz      loc_14000201E
0x140001d86  sub     edx, 1FC03h
0x140001d8c  jz      loc_140002015
0x140001d92  sub     edx, 308h
0x140001d98  jz      loc_14000200C
0x140001d9e  sub     edx, 5
0x140001da1  jz      loc_140002003
0x140001da7  sub     edx, 100F0h
0x140001dad  jz      loc_140001FFA
0x140001db3  sub     edx, 7F40Dh
0x140001db9  jz      loc_140001FF1
0x140001dbf  cmp     edx, 1FC0004h
0x140001dc5  jnz     short loc_140001DCB
0x140001dc7  mov     [rdi+2Ah], ax
0x140001dcb  inc     r15d
0x140001dce  mov     ecx, ebp
0x140001dd0  cmp     r15d, r14d
0x140001dd3  jb      loc_140001CEF
0x140001dd9  add     rsp, 38h
0x140001ddd  pop     r15
0x140001ddf  pop     r14
0x140001de1  pop     r13
0x140001de3  pop     r12
0x140001de5  pop     rdi
0x140001de6  pop     rsi
0x140001de7  pop     rbp
0x140001de8  pop     rbx
0x140001de9  retn
0x140001dea  jz      loc_140001FA0
0x140001df0  mov     ecx, 67737038h
0x140001df5  cmp     edx, ecx
0x140001df7  ja      loc_140001F05
0x140001dfd  jz      loc_140001EFC
0x140001e03  sub     edx, 63706874h
0x140001e09  jnz     short loc_140001E85
0x140001e0b  mov     [rdi+2Ch], ax
0x140001e0f  jmp     short loc_140001DCB
0x140001e11  jnz     short loc_140001E1F
0x140001e13  mov     [rdi+44h], ax
0x140001e17  jmp     short loc_140001DCB
0x140001e19  mov     [rdi+42h], ax
0x140001e1d  jmp     short loc_140001DCB
0x140001e1f  sub     edx, 73627873h
0x140001e25  jz      loc_140001FE8
0x140001e2b  mov     ecx, 0FCh
0x140001e30  sub     edx, ecx
0x140001e32  jz      loc_140001FDF
0x140001e38  sub     edx, 4
0x140001e3b  jz      loc_140001FD6
0x140001e41  sub     edx, 0DFEFCh
0x140001e47  jz      loc_140001FCD
0x140001e4d  sub     edx, 4
0x140001e50  jz      loc_140001FC4
0x140001e56  sub     edx, ecx
0x140001e58  jz      loc_140001FBB
0x140001e5e  sub     edx, 4
0x140001e61  jz      loc_140001FB2
0x140001e67  sub     edx, 3F8FCh
0x140001e6d  jz      loc_140001FA9
0x140001e73  cmp     edx, 4
0x140001e76  jnz     loc_140001DCB
0x140001e7c  mov     [rdi+3Eh], ax
0x140001e80  jmp     loc_140001DCB
0x140001e85  sub     edx, 40307BCh
0x140001e8b  jz      short loc_140001EF3
0x140001e8d  sub     edx, 1
0x140001e90  jz      short loc_140001EEA
0x140001e92  sub     edx, 1
0x140001e95  jz      short loc_140001EE1
0x140001e97  sub     edx, 1
0x140001e9a  jz      short loc_140001ED8
0x140001e9c  sub     edx, 1
0x140001e9f  jz      short loc_140001ECF
0x140001ea1  sub     edx, 1
0x140001ea4  jz      short loc_140001EC6
0x140001ea6  sub     edx, 1
0x140001ea9  jz      short loc_140001EBD
0x140001eab  cmp     edx, 1
0x140001eae  jnz     loc_140001DCB
0x140001eb4  mov     [rdi+54h], ax
0x140001eb8  jmp     loc_140001DCB
0x140001ebd  mov     [rdi+52h], ax
0x140001ec1  jmp     loc_140001DCB
0x140001ec6  mov     [rdi+50h], ax
0x140001eca  jmp     loc_140001DCB
0x140001ecf  mov     [rdi+4Eh], ax
0x140001ed3  jmp     loc_140001DCB
0x140001ed8  mov     [rdi+4Ch], ax
0x140001edc  jmp     loc_140001DCB
0x140001ee1  mov     [rdi+4Ah], ax
0x140001ee5  jmp     loc_140001DCB
0x140001eea  mov     [rdi+48h], ax
0x140001eee  jmp     loc_140001DCB
0x140001ef3  mov     [rdi+46h], ax
0x140001ef7  jmp     loc_140001DCB
0x140001efc  mov     [rdi+56h], ax
0x140001f00  jmp     loc_140001DCB
0x140001f05  sub     edx, 67737039h
0x140001f0b  jz      loc_140001F97
0x140001f11  sub     edx, 0EE032Ah
0x140001f17  jz      short loc_140001F8E
0x140001f19  sub     edx, 1F8FEh
0x140001f1f  jz      short loc_140001F85
0x140001f21  sub     edx, 3
0x140001f24  jz      short loc_140001F7C
0x140001f26  sub     edx, 302h
0x140001f2c  jz      short loc_140001F73
0x140001f2e  sub     edx, 308h
0x140001f34  jz      short loc_140001F6A
0x140001f36  sub     edx, 5
0x140001f39  jz      short loc_140001F61
0x140001f3b  sub     edx, 100F0h
0x140001f41  jz      short loc_140001F58
0x140001f43  cmp     edx, 7F40Dh
0x140001f49  jnz     loc_140001DCB
0x140001f4f  mov     [rdi+12h], ax
0x140001f53  jmp     loc_140001DCB
0x140001f58  mov     [rdi+10h], ax
0x140001f5c  jmp     loc_140001DCB
0x140001f61  mov     [rdi+1Eh], ax
0x140001f65  jmp     loc_140001DCB
0x140001f6a  mov     [rdi+20h], ax
0x140001f6e  jmp     loc_140001DCB
0x140001f73  mov     [rdi+22h], ax
0x140001f77  jmp     loc_140001DCB
0x140001f7c  mov     [rdi+16h], ax
0x140001f80  jmp     loc_140001DCB
0x140001f85  mov     [rdi+14h], ax
0x140001f89  jmp     loc_140001DCB
0x140001f8e  mov     [rdi+0Eh], ax
0x140001f92  jmp     loc_140001DCB
0x140001f97  mov     [rdi+58h], ax
0x140001f9b  jmp     loc_140001DCB
0x140001fa0  mov     [rdi+32h], ax
0x140001fa4  jmp     loc_140001DCB
0x140001fa9  mov     [rdi+40h], ax
0x140001fad  jmp     loc_140001DCB
0x140001fb2  mov     [rdi+38h], ax
0x140001fb6  jmp     loc_140001DCB
0x140001fbb  mov     [rdi+3Ch], ax
0x140001fbf  jmp     loc_140001DCB
0x140001fc4  mov     [rdi+36h], ax
0x140001fc8  jmp     loc_140001DCB
0x140001fcd  mov     [rdi+3Ah], ax
0x140001fd1  jmp     loc_140001DCB
0x140001fd6  mov     [rdi+30h], ax
0x140001fda  jmp     loc_140001DCB
0x140001fdf  mov     [rdi+34h], ax
0x140001fe3  jmp     loc_140001DCB
0x140001fe8  mov     [rdi+2Eh], ax
0x140001fec  jmp     loc_140001DCB
0x140001ff1  mov     [rdi+1Ch], ax
0x140001ff5  jmp     loc_140001DCB
0x140001ffa  mov     [rdi+1Ah], ax
0x140001ffe  jmp     loc_140001DCB
0x140002003  mov     [rdi+24h], ax
0x140002007  jmp     loc_140001DCB
0x14000200c  mov     [rdi+26h], ax
0x140002010  jmp     loc_140001DCB
0x140002015  mov     [rdi+28h], ax
0x140002019  jmp     loc_140001DCB
0x14000201e  mov     [rdi+18h], ax
0x140002022  jmp     loc_140001DCB
```
