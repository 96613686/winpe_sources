# DrvUnlockDisplayArea

- ea: `0x1400342e0`
- end: `0x140034436`
- name: `DrvUnlockDisplayArea`
- size: `342`
- prototype: `FN_DrvUnlockDisplayArea`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140008fa4`
- `0x14001931c`
- `0x14001a464`
- `0x14001cc38`
- `0x1400224a0`
- `0x1400342e0`

## import_xrefs

- `WIN32K!EngIsSemaphoreOwnedByCurrentThread` at `0x1400343aa`
- `WIN32K!EngIsSemaphoreOwnedByCurrentThread` at `0x1400343da`
- `WIN32K!EngIsSemaphoreOwnedByCurrentThread` at `0x1400343aa`
- `WIN32K!EngIsSemaphoreOwnedByCurrentThread` at `0x1400343da`
- `WIN32K!EngReleaseSemaphore` at `0x1400343c6`
- `WIN32K!EngReleaseSemaphore` at `0x1400343c6`

## string_xrefs

- `0x1400343ea`: `DrvUnlockDisplayArea tile lock is still locked by current thread!\n`

## pseudocode

```c
void __stdcall DrvUnlockDisplayArea(DHPDEV dhpdev, RECTL *prcl)
{
  __int64 v3; // rdx
  unsigned int v4; // ecx
  unsigned int v5; // r12d
  int v6; // eax
  unsigned int v7; // ecx
  int v8; // r13d
  int v9; // r8d
  int i; // esi
  signed int v11; // r15d
  __int64 v12; // r14
  __int64 v13; // r12
  RECTL v14; // [rsp+20h] [rbp-20h] BYREF
  __int64 v15; // [rsp+30h] [rbp-10h] BYREF
  int v16; // [rsp+38h] [rbp-8h]
  int v17; // [rsp+3Ch] [rbp-4h]
  unsigned int v18; // [rsp+80h] [rbp+40h]
  int v19; // [rsp+88h] [rbp+48h]

  v14 = *prcl;
  ERECTL::vOrder((ERECTL *)&v14);
  v3 = *((_QWORD *)dhpdev + 349);
  v15 = 0;
  v16 = *(_DWORD *)(v3 + 32);
  v17 = *(_DWORD *)(v3 + 36);
  ERECTL::operator*=(&v14, &v15);
  if ( !(unsigned int)ERECTL::bEmpty((ERECTL *)&v14) )
  {
    v4 = *((_DWORD *)dhpdev + 894);
    v5 = v14.left / v4;
    v18 = v14.left / v4;
    v6 = v14.right / v4;
    v7 = *((_DWORD *)dhpdev + 895);
    v8 = v6 + 1;
    v9 = v14.bottom / v7 + 1;
    v19 = v9;
    for ( i = v14.top / v7; i < v9; ++i )
    {
      v11 = v5;
      if ( (int)v5 < v8 )
      {
        v12 = v5;
        v13 = 9LL * i;
        do
        {
          if ( EngIsSemaphoreOwnedByCurrentThread(*((HSEMAPHORE *)dhpdev + v13 + v12 + 366)) )
          {
            EngReleaseSemaphore(*((HSEMAPHORE *)dhpdev + v13 + v12 + 366));
            if ( EngIsSemaphoreOwnedByCurrentThread(*((HSEMAPHORE *)dhpdev + v13 + v12 + 366)) )
            {
              DbgLog("DrvUnlockDisplayArea tile lock is still locked by current thread!\n");
              __debugbreak();
            }
          }
          ++v11;
          ++v12;
        }
        while ( v11 < v8 );
        v5 = v18;
        v9 = v19;
      }
    }
    ShadowUnLock((struct CDDPDEV *)dhpdev);
  }
}

```

## disassembly

```asm
0x1400342e0  mov     [rsp-38h+arg_18], rbx
0x1400342e5  push    rbp
0x1400342e6  push    rsi
0x1400342e7  push    rdi
0x1400342e8  push    r12
0x1400342ea  push    r13
0x1400342ec  push    r14
0x1400342ee  push    r15
0x1400342f0  mov     rbp, rsp
0x1400342f3  sub     rsp, 40h
0x1400342f7  movups  xmm0, xmmword ptr [rdx]
0x1400342fa  mov     rdi, rcx
0x1400342fd  lea     rcx, [rbp+var_20]; this
0x140034301  movdqu  [rbp+var_20], xmm0
0x140034306  call    ?vOrder@ERECTL@@QEAAXXZ; ERECTL::vOrder(void)
0x14003430b  mov     rdx, [rdi+0AE8h]
0x140034312  lea     rcx, [rbp+var_20]
0x140034316  mov     [rbp+var_10], 0
0x14003431e  mov     eax, [rdx+20h]
0x140034321  mov     [rbp+var_8], eax
0x140034324  mov     eax, [rdx+24h]
0x140034327  lea     rdx, [rbp+var_10]
0x14003432b  mov     [rbp+var_4], eax
0x14003432e  call    ??XERECTL@@QEAAAEAV0@AEAU_RECTL@@@Z; ERECTL::operator*=(_RECTL &)
0x140034333  lea     rcx, [rbp+var_20]; this
0x140034337  call    ?bEmpty@ERECTL@@QEAAHXZ; ERECTL::bEmpty(void)
0x14003433c  test    eax, eax
0x14003433e  jnz     loc_14003441D
0x140034344  mov     ecx, [rdi+0DF8h]
0x14003434a  xor     edx, edx
0x14003434c  mov     eax, dword ptr [rbp+var_20]
0x14003434f  div     ecx
0x140034351  xor     edx, edx
0x140034353  mov     r12d, eax
0x140034356  mov     [rbp+arg_0], eax
0x140034359  mov     eax, dword ptr [rbp+var_20+8]
0x14003435c  div     ecx
0x14003435e  mov     ecx, [rdi+0DFCh]
0x140034364  xor     edx, edx
0x140034366  lea     r13d, [rax+1]
0x14003436a  mov     eax, dword ptr [rbp+var_20+0Ch]
0x14003436d  div     ecx
0x14003436f  xor     edx, edx
0x140034371  lea     r8d, [rax+1]
0x140034375  mov     eax, dword ptr [rbp+var_20+4]
0x140034378  div     ecx
0x14003437a  mov     [rbp+arg_8], r8d
0x14003437e  mov     esi, eax
0x140034380  cmp     eax, r8d
0x140034383  jge     loc_140034415
0x140034389  mov     r15d, r12d
0x14003438c  cmp     r12d, r13d
0x14003438f  jge     short loc_14003440A
0x140034391  movsxd  rcx, esi
0x140034394  mov     r14d, r12d
0x140034397  lea     rax, [rcx+rcx*8]
0x14003439b  lea     r12, [rax]
0x14003439e  lea     rcx, [r12+r14]
0x1400343a2  mov     rcx, [rdi+rcx*8+0B70h]; hsem
0x1400343aa  call    cs:__imp_EngIsSemaphoreOwnedByCurrentThread
0x1400343b1  nop     dword ptr [rax+rax+00h]
0x1400343b6  test    eax, eax
0x1400343b8  jz      short loc_1400343F7
0x1400343ba  lea     rbx, [r12+r14]
0x1400343be  mov     rcx, [rdi+rbx*8+0B70h]; hsem
0x1400343c6  call    cs:__imp_EngReleaseSemaphore
0x1400343cd  nop     dword ptr [rax+rax+00h]
0x1400343d2  mov     rcx, [rdi+rbx*8+0B70h]; hsem
0x1400343da  call    cs:__imp_EngIsSemaphoreOwnedByCurrentThread
0x1400343e1  nop     dword ptr [rax+rax+00h]
0x1400343e6  test    eax, eax
0x1400343e8  jz      short loc_1400343F7
0x1400343ea  lea     rcx, aDrvunlockdispl; "DrvUnlockDisplayArea tile lock is still"...
0x1400343f1  call    ?DbgLog@@YAXPEBDZZ; DbgLog(char const *,...)
0x1400343f6  int     3; Trap to Debugger
0x1400343f7  inc     r15d
0x1400343fa  inc     r14
0x1400343fd  cmp     r15d, r13d
0x140034400  jl      short loc_14003439E
0x140034402  mov     r12d, [rbp+arg_0]
0x140034406  mov     r8d, [rbp+arg_8]
0x14003440a  inc     esi
0x14003440c  cmp     esi, r8d
0x14003440f  jl      loc_140034389
0x140034415  mov     rcx, rdi; struct CDDPDEV *
0x140034418  call    ?ShadowUnLock@@YAXPEAUCDDPDEV@@@Z; ShadowUnLock(CDDPDEV *)
0x14003441d  mov     rbx, [rsp+40h+arg_18]
0x140034425  add     rsp, 40h
0x140034429  pop     r15
0x14003442b  pop     r14
0x14003442d  pop     r13
0x14003442f  pop     r12
0x140034431  pop     rdi
0x140034432  pop     rsi
0x140034433  pop     rbp
0x140034434  retn
```
