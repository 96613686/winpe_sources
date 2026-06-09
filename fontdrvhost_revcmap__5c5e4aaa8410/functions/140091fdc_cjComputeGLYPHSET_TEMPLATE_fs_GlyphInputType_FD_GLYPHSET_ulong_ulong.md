# cjComputeGLYPHSET_TEMPLATE(fs_GlyphInputType *,_FD_GLYPHSET * *,ulong,ulong)

- ea: `0x140091fdc`
- end: `0x1400920d2`
- name: `?cjComputeGLYPHSET_TEMPLATE@@YAXPEAUfs_GlyphInputType@@PEAPEAU_FD_GLYPHSET@@KK@Z`
- size: `246`
- prototype: `void __fastcall(struct fs_GlyphInputType *, struct _FD_GLYPHSET **, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000a018`

## callees

- `0x14002ea60`
- `0x14005a7b8`
- `0x14005a930`
- `0x140075de0`
- `0x14007680c`
- `0x140091fdc`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x1400920ca`
- `KERNEL32!GlobalFree` at `0x1400920ca`

## pseudocode

```c
void __fastcall cjComputeGLYPHSET_TEMPLATE(
        struct fs_GlyphInputType *a1,
        struct _FD_GLYPHSET **a2,
        unsigned int a3,
        int a4)
{
  int v6; // r14d
  INT v8; // edx
  INT v9; // r8d
  int v10; // ebx
  int v11; // ebx
  FD_GLYPHSET *v12; // rax
  INT v13; // ecx
  struct _FD_GLYPHSET *v14; // rbx
  int v15; // edi
  __int64 phg; // [rsp+28h] [rbp-140h]
  _BYTE v17[256]; // [rsp+40h] [rbp-128h] BYREF

  v6 = (int)a1;
  memset_0(v17, 0, sizeof(v17));
  *a2 = 0;
  v10 = a4 - 1;
  if ( !v10 )
  {
    v13 = 10000;
    goto LABEL_7;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    v13 = 0;
LABEL_7:
    v12 = EngComputeGlyphSet(v13, v8, v9);
    goto LABEL_8;
  }
  if ( v11 != 2 )
    return;
  v12 = pgsetComputeSymbolCP();
LABEL_8:
  v14 = v12;
  if ( v12 )
  {
    v15 = 0;
    v12->flAccel = 4;
    if ( v12->cRuns )
    {
      while ( 1 )
      {
        phg = (__int64)v14->awcrun[v15].phg;
        if ( (unsigned int)fs_WinNTGetGlyphIDs(v6, (unsigned int)v17, v14->awcrun[v15].cGlyphs, 0, a3, phg, phg) )
          break;
        if ( ++v15 >= v14->cRuns )
          goto LABEL_12;
      }
      GlobalFree(v14);
    }
    else
    {
LABEL_12:
      *a2 = v14;
    }
  }
}

```

## disassembly

```asm
0x140091fdc  mov     [rsp+arg_10], rbx
0x140091fe1  mov     [rsp+arg_18], rbp
0x140091fe6  push    rsi
0x140091fe7  push    rdi
0x140091fe8  push    r14
0x140091fea  sub     rsp, 150h
0x140091ff1  mov     rax, cs:__security_cookie
0x140091ff8  xor     rax, rsp
0x140091ffb  mov     [rsp+168h+var_28], rax
0x140092003  mov     ebp, r8d
0x140092006  mov     rsi, rdx
0x140092009  mov     r14, rcx
0x14009200c  xor     edx, edx; Val
0x14009200e  mov     r8d, 100h; Size
0x140092014  lea     rcx, [rsp+168h+var_128]; void *
0x140092019  mov     ebx, r9d
0x14009201c  call    memset_0
0x140092021  mov     qword ptr [rsi], 0
0x140092028  sub     ebx, 1
0x14009202b  jz      short loc_140092042
0x14009202d  sub     ebx, 1
0x140092030  jz      short loc_14009203E
0x140092032  cmp     ebx, 2
0x140092035  jnz     short loc_14009209F
0x140092037  call    ?pgsetComputeSymbolCP@@YAPEAU_FD_GLYPHSET@@XZ; pgsetComputeSymbolCP(void)
0x14009203c  jmp     short loc_14009204C
0x14009203e  xor     ecx, ecx
0x140092040  jmp     short loc_140092047
0x140092042  mov     ecx, 2710h; nCodePage
0x140092047  call    EngComputeGlyphSet
0x14009204c  mov     rbx, rax
0x14009204f  test    rax, rax
0x140092052  jz      short loc_14009209F
0x140092054  xor     edi, edi
0x140092056  mov     dword ptr [rax+4], 4
0x14009205d  cmp     [rax+0Ch], edi
0x140092060  jbe     short loc_14009209C
0x140092062  mov     r8d, edi
0x140092065  lea     rdx, [rsp+168h+var_128]
0x14009206a  add     r8, r8
0x14009206d  xor     r9d, r9d
0x140092070  mov     rcx, r14
0x140092073  mov     rax, [rbx+r8*8+18h]
0x140092078  movzx   r8d, word ptr [rbx+r8*8+12h]
0x14009207e  mov     [rsp+168h+var_138], rax
0x140092083  mov     [rsp+168h+var_140], rax
0x140092088  mov     [rsp+168h+var_148], ebp
0x14009208c  call    fs_WinNTGetGlyphIDs
0x140092091  test    eax, eax
0x140092093  jnz     short loc_1400920C7
0x140092095  inc     edi
0x140092097  cmp     edi, [rbx+0Ch]
0x14009209a  jb      short loc_140092062
0x14009209c  mov     [rsi], rbx
0x14009209f  mov     rcx, [rsp+168h+var_28]
0x1400920a7  xor     rcx, rsp; StackCookie
0x1400920aa  call    __security_check_cookie
0x1400920af  lea     r11, [rsp+168h+var_18]
0x1400920b7  mov     rbx, [r11+30h]
0x1400920bb  mov     rbp, [r11+38h]
0x1400920bf  mov     rsp, r11
0x1400920c2  pop     r14
0x1400920c4  pop     rdi
0x1400920c5  pop     rsi
0x1400920c6  retn
0x1400920c7  mov     rcx, rbx; hMem
0x1400920ca  call    cs:__imp_GlobalFree
0x1400920d0  jmp     short loc_14009209F
```
