# AddNewPortsPerLine

- ea: `0x18000212c`
- end: `0x180002298`
- name: `AddNewPortsPerLine`
- size: `364`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180002e20`
- `0x18000cb80`
- `0x180014bc0`

## callees

- `0x18000212c`
- `0x18000c974`
- `0x18000d92c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000215b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000215b`

## string_xrefs

- `0x18000226d`: `AddNewPorts: New Device Created - %s`

## pseudocode

```c
void __fastcall AddNewPortsPerLine(__int64 a1, unsigned int a2)
{
  __int64 v4; // rsi
  __int64 v5; // rdi
  char *v6; // rbx
  _BYTE *v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rax
  _BYTE *v10; // rcx
  bool v11; // zf
  _BYTE *v12; // rax
  _BYTE *v13; // r8
  __int64 v14; // rdx
  _BYTE *v15; // rcx
  __int64 v16; // rax
  _BYTE *v17; // rax
  __int64 v18; // rdx
  _BYTE *v19; // r8
  _BYTE *v20; // rcx
  __int64 v21; // rax
  _BYTE *v22; // rax

  if ( a2 )
  {
    v4 = 0;
    do
    {
      v5 = *(_QWORD *)(a1 + 8 * v4);
      v6 = (char *)LocalAlloc(0x40u, 0xD8u);
      if ( !v6 )
        break;
      v7 = (_BYTE *)(v5 + 24);
      v8 = 16;
      v9 = 2147483646;
      v10 = v6;
      do
      {
        if ( !v9 )
          break;
        if ( !*v7 )
          break;
        *v10++ = *v7++;
        --v9;
        --v8;
      }
      while ( v8 );
      v11 = v8 == 0;
      v12 = v10 - 1;
      v13 = (_BYTE *)(v5 + 64);
      v14 = 16;
      if ( !v11 )
        v12 = v10;
      v15 = v6 + 52;
      *v12 = 0;
      *((_DWORD *)v6 + 12) = *(_DWORD *)(v5 + 208);
      v16 = 2147483646;
      do
      {
        if ( !v16 )
          break;
        if ( !*v13 )
          break;
        *v15++ = *v13++;
        --v16;
        --v14;
      }
      while ( v14 );
      v11 = v14 == 0;
      v17 = v15 - 1;
      v18 = 128;
      if ( !v11 )
        v17 = v15;
      v19 = (_BYTE *)(v5 + 80);
      v20 = v6 + 68;
      *v17 = 0;
      v21 = 2147483646;
      do
      {
        if ( !v21 )
          break;
        if ( !*v19 )
          break;
        *v20++ = *v19++;
        --v21;
        --v18;
      }
      while ( v18 );
      v22 = v20 - 1;
      if ( v18 )
        v22 = v20;
      *v22 = 0;
      *((_DWORD *)v6 + 49) = *(_DWORD *)(*(_QWORD *)(v5 + 216) + 8LL);
      *((_DWORD *)v6 + 50) = *(_DWORD *)(v5 + 224);
      *((_QWORD *)v6 + 26) = *(_QWORD *)(*(_QWORD *)(v5 + 216) + 40LL);
      RasTapiTrace("AddNewPorts: New Device Created - %s");
      PostNotificationNewPort(v6);
      v4 = (unsigned int)(v4 + 1);
    }
    while ( (unsigned int)v4 < a2 );
  }
}

```

## disassembly

```asm
0x18000212c  test    edx, edx
0x18000212e  jz      locret_180002297
0x180002134  push    rbx
0x180002135  push    rbp
0x180002136  push    rsi
0x180002137  push    rdi
0x180002138  push    r13
0x18000213a  push    r14
0x18000213c  sub     rsp, 28h
0x180002140  mov     ebp, edx
0x180002142  mov     r14, rcx
0x180002145  xor     esi, esi
0x180002147  mov     r13d, 7FFFFFFEh
0x18000214d  mov     rdi, [r14+rsi*8]
0x180002151  mov     edx, 0D8h; uBytes
0x180002156  mov     ecx, 40h ; '@'; uFlags
0x18000215b  call    cs:__imp_LocalAlloc
0x180002161  mov     rbx, rax
0x180002164  test    rax, rax
0x180002167  jz      loc_18000228B
0x18000216d  mov     r10d, 10h
0x180002173  lea     r8, [rdi+18h]
0x180002177  mov     edx, r10d
0x18000217a  mov     rax, r13
0x18000217d  mov     rcx, rbx
0x180002180  test    rax, rax
0x180002183  jz      short loc_18000219F
0x180002185  mov     r9b, [r8]
0x180002188  test    r9b, r9b
0x18000218b  jz      short loc_18000219F
0x18000218d  mov     [rcx], r9b
0x180002190  inc     r8
0x180002193  inc     rcx
0x180002196  dec     rax
0x180002199  sub     rdx, 1
0x18000219d  jnz     short loc_180002180
0x18000219f  test    rdx, rdx
0x1800021a2  lea     rax, [rcx-1]
0x1800021a6  lea     r8, [rdi+40h]
0x1800021aa  mov     rdx, r10
0x1800021ad  cmovnz  rax, rcx
0x1800021b1  lea     rcx, [rbx+34h]
0x1800021b5  mov     byte ptr [rax], 0
0x1800021b8  mov     eax, [rdi+0D0h]
0x1800021be  mov     [rbx+30h], eax
0x1800021c1  mov     rax, r13
0x1800021c4  test    rax, rax
0x1800021c7  jz      short loc_1800021E3
0x1800021c9  mov     r9b, [r8]
0x1800021cc  test    r9b, r9b
0x1800021cf  jz      short loc_1800021E3
0x1800021d1  mov     [rcx], r9b
0x1800021d4  inc     r8
0x1800021d7  inc     rcx
0x1800021da  dec     rax
0x1800021dd  sub     rdx, 1
0x1800021e1  jnz     short loc_1800021C4
0x1800021e3  test    rdx, rdx
0x1800021e6  lea     rax, [rcx-1]
0x1800021ea  lea     r10, [rdi+50h]
0x1800021ee  mov     edx, 80h
0x1800021f3  cmovnz  rax, rcx
0x1800021f7  mov     r8, r10
0x1800021fa  lea     rcx, [rbx+44h]
0x1800021fe  mov     byte ptr [rax], 0
0x180002201  mov     rax, r13
0x180002204  test    rax, rax
0x180002207  jz      short loc_180002223
0x180002209  mov     r9b, [r8]
0x18000220c  test    r9b, r9b
0x18000220f  jz      short loc_180002223
0x180002211  mov     [rcx], r9b
0x180002214  inc     r8
0x180002217  inc     rcx
0x18000221a  dec     rax
0x18000221d  sub     rdx, 1
0x180002221  jnz     short loc_180002204
0x180002223  test    rdx, rdx
0x180002226  lea     rax, [rcx-1]
0x18000222a  lea     rdx, aNull; "NULL!"
0x180002231  cmovnz  rax, rcx
0x180002235  test    r10, r10
0x180002238  cmovnz  rdx, r10
0x18000223c  mov     byte ptr [rax], 0
0x18000223f  mov     rax, [rdi+0D8h]
0x180002246  mov     ecx, [rax+8]
0x180002249  mov     [rbx+0C4h], ecx
0x18000224f  mov     eax, [rdi+0E0h]
0x180002255  mov     [rbx+0C8h], eax
0x18000225b  mov     rax, [rdi+0D8h]
0x180002262  mov     rcx, [rax+28h]
0x180002266  mov     [rbx+0D0h], rcx
0x18000226d  lea     rcx, aAddnewportsNew; "AddNewPorts: New Device Created - %s"
0x180002274  call    RasTapiTrace
0x180002279  mov     rcx, rbx; hMem
0x18000227c  call    PostNotificationNewPort
0x180002281  inc     esi
0x180002283  cmp     esi, ebp
0x180002285  jb      loc_18000214D
0x18000228b  add     rsp, 28h
0x18000228f  pop     r14
0x180002291  pop     r13
0x180002293  pop     rdi
0x180002294  pop     rsi
0x180002295  pop     rbp
0x180002296  pop     rbx
0x180002297  retn
```
