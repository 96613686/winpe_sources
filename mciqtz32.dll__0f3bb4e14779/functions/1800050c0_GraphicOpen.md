# GraphicOpen

- ea: `0x1800050c0`
- end: `0x180005260`
- name: `GraphicOpen`
- size: `416`
- prototype: `__int64 __fastcall(HLOCAL *, int, __int64, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000485c`
- `0x1800062f8`

## callees

- `0x180002448`
- `0x180004de0`
- `0x1800050c0`
- `0x18000655d`
- `0x180007010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180005103`
- `KERNEL32!LocalAlloc` at `0x18000516b`
- `KERNEL32!LocalAlloc` at `0x180005103`
- `KERNEL32!LocalAlloc` at `0x18000516b`
- `USER32!IsWindow` at `0x18000519d`
- `USER32!IsWindow` at `0x18000519d`

## pseudocode

```c
__int64 __fastcall GraphicOpen(HLOCAL *a1, int a2, __int64 a3, int a4)
{
  _DWORD *v8; // rbx
  __int64 result; // rax
  const void *v10; // rbp
  _WORD *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r15
  HLOCAL v14; // rax
  unsigned int v15; // edi
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rcx

  if ( (a2 & 0x200) == 0 || !*(_QWORD *)(a3 + 20) )
    return 274;
  v8 = *a1;
  if ( !*a1 )
  {
    v8 = LocalAlloc(0x40u, 0x268u);
    if ( !v8 )
      return 264;
  }
  v8[4] = 2051;
  v10 = *(const void **)(a3 + 20);
  if ( !v10 )
    goto LABEL_27;
  v11 = *(_WORD **)(a3 + 20);
  v12 = 256;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v12;
  }
  while ( v12 );
  if ( !v12 )
  {
LABEL_27:
    v15 = 268;
    goto LABEL_28;
  }
  v13 = -(__int64)(v12 != 0) & (2 * (256 - v12));
  v14 = LocalAlloc(0x40u, v13 + 2);
  *((_QWORD *)v8 + 8) = v14;
  if ( !v14 )
  {
    v15 = 264;
LABEL_28:
    GraphicClose((struct _MCIGRAPHIC *)v8);
    return v15;
  }
  memcpy_0(v14, v10, v13 + 2);
  if ( (a2 & 0x20000) != 0 )
  {
    if ( !IsWindow(*(HWND *)(a3 + 40)) )
    {
      v15 = 347;
      goto LABEL_28;
    }
    v16 = *(_QWORD *)(a3 + 40);
  }
  else
  {
    v16 = 0;
  }
  *((_QWORD *)v8 + 4) = v16;
  if ( (a2 & 0x10000) != 0 )
    v17 = *(_DWORD *)(a3 + 36);
  else
    v17 = 114163712;
  v8[10] = v17;
  *(_QWORD *)v8 = 0;
  v8[2] = a4;
  *((_QWORD *)v8 + 6) = 0;
  v8[15] = 0;
  v15 = DeviceOpen((LPVOID *)v8, a2);
  if ( v15 )
    goto LABEL_28;
  if ( *((double *)v8 + 73) != 0.0 )
  {
    v18 = *((_QWORD *)v8 + 18);
    if ( v18 )
    {
      if ( (*(int (__fastcall **)(__int64, const GUID *))(*(_QWORD *)v18 + 72LL))(v18, &TIME_FORMAT_FRAME) >= 0 )
        v8[15] = 3;
    }
  }
  *a1 = v8;
  result = 0;
  v8[4] = 0;
  return result;
}

```

## disassembly

```asm
0x1800050c0  push    rbx
0x1800050c2  push    rbp
0x1800050c3  push    rsi
0x1800050c4  push    rdi
0x1800050c5  push    r12
0x1800050c7  push    r13
0x1800050c9  push    r14
0x1800050cb  push    r15
0x1800050cd  sub     rsp, 28h
0x1800050d1  mov     r12d, r9d
0x1800050d4  mov     rdi, r8
0x1800050d7  mov     esi, edx
0x1800050d9  mov     r14, rcx
0x1800050dc  bt      edx, 9
0x1800050e0  jnb     loc_18000524A
0x1800050e6  xor     r13d, r13d
0x1800050e9  cmp     [r8+14h], r13
0x1800050ed  jz      loc_18000524A
0x1800050f3  mov     rbx, [rcx]
0x1800050f6  test    rbx, rbx
0x1800050f9  jnz     short loc_18000511B
0x1800050fb  mov     edx, 268h; uBytes
0x180005100  lea     ecx, [rbx+40h]; uFlags
0x180005103  call    cs:__imp_LocalAlloc
0x180005109  mov     rbx, rax
0x18000510c  test    rax, rax
0x18000510f  jnz     short loc_18000511B
0x180005111  mov     eax, 108h
0x180005116  jmp     loc_18000524F
0x18000511b  mov     dword ptr [rbx+10h], 803h
0x180005122  mov     rbp, [rdi+14h]
0x180005126  test    rbp, rbp
0x180005129  jz      loc_180005239
0x18000512f  mov     edx, 100h
0x180005134  mov     rcx, rbp
0x180005137  mov     eax, edx
0x180005139  cmp     [rcx], r13w
0x18000513d  jz      short loc_180005149
0x18000513f  add     rcx, 2
0x180005143  sub     rax, 1
0x180005147  jnz     short loc_180005139
0x180005149  test    rax, rax
0x18000514c  jz      loc_180005239
0x180005152  sub     rdx, rax
0x180005155  mov     ecx, 40h ; '@'; uFlags
0x18000515a  neg     rax
0x18000515d  sbb     rax, rax
0x180005160  lea     r15, [rdx+rdx]
0x180005164  and     r15, rax
0x180005167  lea     rdx, [r15+2]; uBytes
0x18000516b  call    cs:__imp_LocalAlloc
0x180005171  mov     [rbx+40h], rax
0x180005175  test    rax, rax
0x180005178  jnz     short loc_180005184
0x18000517a  mov     edi, 108h
0x18000517f  jmp     loc_18000523E
0x180005184  lea     r8, [r15+2]; Size
0x180005188  mov     rdx, rbp; Src
0x18000518b  mov     rcx, rax; void *
0x18000518e  call    memcpy_0
0x180005193  bt      esi, 11h
0x180005197  jnb     short loc_1800051B7
0x180005199  mov     rcx, [rdi+28h]; hWnd
0x18000519d  call    cs:__imp_IsWindow
0x1800051a3  test    eax, eax
0x1800051a5  jnz     short loc_1800051B1
0x1800051a7  mov     edi, 15Bh
0x1800051ac  jmp     loc_18000523E
0x1800051b1  mov     rax, [rdi+28h]
0x1800051b5  jmp     short loc_1800051BA
0x1800051b7  mov     rax, r13
0x1800051ba  mov     [rbx+20h], rax
0x1800051be  bt      esi, 10h
0x1800051c2  jnb     short loc_1800051C9
0x1800051c4  mov     eax, [rdi+24h]
0x1800051c7  jmp     short loc_1800051CE
0x1800051c9  mov     eax, 6CE0000h
0x1800051ce  mov     [rbx+28h], eax
0x1800051d1  mov     edx, esi; unsigned int
0x1800051d3  mov     rcx, rbx; struct _MCIGRAPHIC *
0x1800051d6  mov     [rbx], r13
0x1800051d9  mov     [rbx+8], r12d
0x1800051dd  mov     [rbx+30h], r13
0x1800051e1  mov     [rbx+3Ch], r13d
0x1800051e5  call    ?DeviceOpen@@YAKPEAU_MCIGRAPHIC@@K@Z; DeviceOpen(_MCIGRAPHIC *,ulong)
0x1800051ea  mov     edi, eax
0x1800051ec  test    eax, eax
0x1800051ee  jnz     short loc_18000523E
0x1800051f0  movsd   xmm0, qword ptr [rbx+248h]
0x1800051f8  ucomisd xmm0, cs:__real@0000000000000000
0x180005200  jp      short loc_180005204
0x180005202  jz      short loc_18000522E
0x180005204  mov     rcx, [rbx+90h]
0x18000520b  test    rcx, rcx
0x18000520e  jz      short loc_18000522E
0x180005210  mov     rax, [rcx]
0x180005213  lea     rdx, TIME_FORMAT_FRAME
0x18000521a  mov     rax, [rax+48h]
0x18000521e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005223  test    eax, eax
0x180005225  js      short loc_18000522E
0x180005227  mov     dword ptr [rbx+3Ch], 3
0x18000522e  mov     [r14], rbx
0x180005231  xor     eax, eax
0x180005233  mov     [rbx+10h], r13d
0x180005237  jmp     short loc_18000524F
0x180005239  mov     edi, 10Ch
0x18000523e  mov     rcx, rbx; struct _MCIGRAPHIC *
0x180005241  call    GraphicClose
0x180005246  mov     eax, edi
0x180005248  jmp     short loc_18000524F
0x18000524a  mov     eax, 112h
0x18000524f  add     rsp, 28h
0x180005253  pop     r15
0x180005255  pop     r14
0x180005257  pop     r13
0x180005259  pop     r12
0x18000525b  pop     rdi
0x18000525c  pop     rsi
0x18000525d  pop     rbp
0x18000525e  pop     rbx
0x18000525f  retn
```
