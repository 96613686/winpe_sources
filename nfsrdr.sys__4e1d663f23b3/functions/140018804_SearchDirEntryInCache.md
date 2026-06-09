# SearchDirEntryInCache

- ea: `0x140018804`
- end: `0x140018a17`
- name: `SearchDirEntryInCache`
- size: `531`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140012c40`

## callees

- `0x1400029d0`
- `0x140008140`
- `0x140013c20`
- `0x1400159cc`
- `0x14001837c`
- `0x140018804`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400189ce`
- `ntoskrnl!KeReleaseMutex` at `0x1400189ce`

## pseudocode

```c
__int64 __fastcall SearchDirEntryInCache(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r15
  unsigned int v9; // ebp
  __int64 v10; // rbx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  __int64 *v15; // rcx

  v4 = *(_QWORD *)(a2 + 80);
  v9 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids);
  if ( a4 && a3 && a1 && *(_QWORD *)(a1 + 40) )
  {
    HacAcquireLock(a3);
    v10 = *(_QWORD *)(a3 + 32);
    if ( !v10 )
      goto LABEL_38;
    if ( (unsigned int)*(unsigned __int16 *)(v10 + 4) >= *(_DWORD *)a4 )
    {
      *(_QWORD *)(a4 + 56) = *(_QWORD *)(v10 + 24);
      if ( (int)NfsGetAttributes(a1, a2, a3) < 0 )
        goto LABEL_38;
      if ( *(_DWORD *)(a3 + 136) == *(_DWORD *)(v10 + 32)
        && *(_DWORD *)(a3 + 200) == *(_DWORD *)(v10 + 36)
        && *(_DWORD *)(a3 + 204) == *(_DWORD *)(v10 + 40) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids);
        }
        v11 = *(_DWORD *)(a4 + 20);
        if ( v11 == -1 )
        {
          v11 = *(_DWORD *)v10;
          *(_DWORD *)(a4 + 20) = *(_DWORD *)v10;
        }
        if ( !*(_QWORD *)(a4 + 80) )
        {
          v15 = **(__int64 ***)(v10 + 8);
          do
          {
            if ( !v15 )
              break;
            if ( (v15[1] & 2) != 0 )
              goto LABEL_25;
            v15 = (__int64 *)*v15;
          }
          while ( v15 != **(__int64 ***)(v10 + 8) );
          goto LABEL_38;
        }
        if ( v11 != *(_DWORD *)v10 || (v12 = *(unsigned __int16 *)(a4 + 16), (_WORD)v12 == 0xFFFF) )
        {
          v14 = SearchCacheBasedOnCookie(v10, a4);
          if ( v14 && v14 != -2147483642 )
            goto LABEL_38;
        }
        else
        {
          v13 = *(_QWORD *)(a4 + 24);
          if ( v12 >= *(_DWORD *)(v13 + 24) && v13 == *(_QWORD *)(v10 + 8) && (*(_DWORD *)(v13 + 8) & 1) == 0 )
            goto LABEL_38;
        }
LABEL_25:
        v9 = 1;
LABEL_38:
        KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
        goto LABEL_39;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids);
      }
    }
    DeleteDirCache(v4, a3);
    goto LABEL_38;
  }
LABEL_39:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids);
  return v9;
}

```

## disassembly

```asm
0x140018804  push    rbx
0x140018806  push    rbp
0x140018807  push    rsi
0x140018808  push    rdi
0x140018809  push    r12
0x14001880b  push    r13
0x14001880d  push    r14
0x14001880f  push    r15
0x140018811  sub     rsp, 28h
0x140018815  mov     r15, [rdx+50h]
0x140018819  mov     rdi, r9
0x14001881c  mov     rsi, r8
0x14001881f  mov     r13, rdx
0x140018822  mov     r14, rcx
0x140018825  xor     ebp, ebp
0x140018827  mov     rcx, cs:WPP_GLOBAL_Control
0x14001882e  lea     r12, WPP_GLOBAL_Control
0x140018835  cmp     rcx, r12
0x140018838  jz      short loc_140018854
0x14001883a  mov     eax, [rcx+2Ch]
0x14001883d  test    al, 40h
0x14001883f  jz      short loc_140018854
0x140018841  mov     rcx, [rcx+18h]
0x140018845  lea     edx, [rbp+0Fh]
0x140018848  lea     r8, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids
0x14001884f  call    WPP_SF_
0x140018854  test    rdi, rdi
0x140018857  jz      loc_1400189DA
0x14001885d  test    rsi, rsi
0x140018860  jz      loc_1400189DA
0x140018866  test    r14, r14
0x140018869  jz      loc_1400189DA
0x14001886f  cmp     [r14+28h], rbp
0x140018873  jz      loc_1400189DA
0x140018879  mov     rcx, rsi
0x14001887c  call    HacAcquireLock
0x140018881  mov     rbx, [rsi+20h]
0x140018885  test    rbx, rbx
0x140018888  jz      loc_1400189C8
0x14001888e  movzx   eax, word ptr [rbx+4]
0x140018892  cmp     eax, [rdi]
0x140018894  jb      loc_1400189BD
0x14001889a  mov     rax, [rbx+18h]
0x14001889e  mov     r8, rsi
0x1400188a1  mov     [rdi+38h], rax
0x1400188a5  mov     rdx, r13
0x1400188a8  mov     rax, ds:0FFFFF78000000014h
0x1400188b2  mov     rcx, r14
0x1400188b5  call    NfsGetAttributes
0x1400188ba  test    eax, eax
0x1400188bc  js      loc_1400189C8
0x1400188c2  mov     eax, [rbx+20h]
0x1400188c5  cmp     [rsi+88h], eax
0x1400188cb  jnz     loc_140018993
0x1400188d1  mov     eax, [rbx+24h]
0x1400188d4  cmp     [rsi+0C8h], eax
0x1400188da  jnz     loc_140018993
0x1400188e0  mov     eax, [rbx+28h]
0x1400188e3  cmp     [rsi+0CCh], eax
0x1400188e9  jnz     loc_140018993
0x1400188ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400188f6  cmp     rcx, r12
0x1400188f9  jz      short loc_140018919
0x1400188fb  test    dword ptr [rcx+2Ch], 100h
0x140018902  jz      short loc_140018919
0x140018904  mov     rcx, [rcx+18h]
0x140018908  lea     r8, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids
0x14001890f  mov     edx, 10h
0x140018914  call    WPP_SF_
0x140018919  mov     eax, [rdi+14h]
0x14001891c  cmp     eax, 0FFFFFFFFh
0x14001891f  jnz     short loc_140018926
0x140018921  mov     eax, [rbx]
0x140018923  mov     [rdi+14h], eax
0x140018926  cmp     [rdi+50h], rbp
0x14001892a  jz      short loc_140018973
0x14001892c  cmp     eax, [rbx]
0x14001892e  jnz     short loc_14001895B
0x140018930  movzx   eax, word ptr [rdi+10h]
0x140018934  mov     ecx, 0FFFFh
0x140018939  cmp     cx, ax
0x14001893c  jz      short loc_14001895B
0x14001893e  mov     rcx, [rdi+18h]
0x140018942  cmp     eax, [rcx+18h]
0x140018945  jl      short loc_140018954
0x140018947  cmp     rcx, [rbx+8]
0x14001894b  jnz     short loc_140018954
0x14001894d  mov     eax, [rcx+8]
0x140018950  test    al, 1
0x140018952  jz      short loc_1400189C8
0x140018954  mov     ebp, 1
0x140018959  jmp     short loc_1400189C8
0x14001895b  mov     rdx, rdi
0x14001895e  mov     rcx, rbx
0x140018961  call    SearchCacheBasedOnCookie
0x140018966  test    eax, eax
0x140018968  jz      short loc_140018954
0x14001896a  cmp     eax, 80000006h
0x14001896f  jnz     short loc_1400189C8
0x140018971  jmp     short loc_140018954
0x140018973  mov     rax, [rbx+8]
0x140018977  mov     rdx, [rax]
0x14001897a  mov     rcx, rdx
0x14001897d  test    rcx, rcx
0x140018980  jz      short loc_1400189C8
0x140018982  mov     eax, [rcx+8]
0x140018985  test    al, 2
0x140018987  jnz     short loc_140018954
0x140018989  mov     rcx, [rcx]
0x14001898c  cmp     rcx, rdx
0x14001898f  jnz     short loc_14001897D
0x140018991  jmp     short loc_1400189C8
0x140018993  mov     rcx, cs:WPP_GLOBAL_Control
0x14001899a  cmp     rcx, r12
0x14001899d  jz      short loc_1400189BD
0x14001899f  test    dword ptr [rcx+2Ch], 100h
0x1400189a6  jz      short loc_1400189BD
0x1400189a8  mov     rcx, [rcx+18h]
0x1400189ac  lea     r8, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids
0x1400189b3  mov     edx, 11h
0x1400189b8  call    WPP_SF_
0x1400189bd  mov     rdx, rsi
0x1400189c0  mov     rcx, r15
0x1400189c3  call    DeleteDirCache
0x1400189c8  mov     rcx, [rsi+28h]; Mutex
0x1400189cc  xor     edx, edx; Wait
0x1400189ce  call    cs:__imp_KeReleaseMutex
0x1400189d5  nop     dword ptr [rax+rax+00h]
0x1400189da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400189e1  cmp     rcx, r12
0x1400189e4  jz      short loc_140018A03
0x1400189e6  mov     edx, [rcx+2Ch]
0x1400189e9  test    dl, 40h
0x1400189ec  jz      short loc_140018A03
0x1400189ee  mov     rcx, [rcx+18h]
0x1400189f2  lea     r8, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids
0x1400189f9  mov     edx, 12h
0x1400189fe  call    WPP_SF_
0x140018a03  mov     eax, ebp
0x140018a05  add     rsp, 28h
0x140018a09  pop     r15
0x140018a0b  pop     r14
0x140018a0d  pop     r13
0x140018a0f  pop     r12
0x140018a11  pop     rdi
0x140018a12  pop     rsi
0x140018a13  pop     rbp
0x140018a14  pop     rbx
0x140018a15  retn
```
