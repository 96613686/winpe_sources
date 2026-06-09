# SIdxStringPool::AddStr(char *,ushort,int *)

- ea: `0x180023828`
- end: `0x180023a67`
- name: `?AddStr@SIdxStringPool@@QEAAKPEADGPEAH@Z`
- size: `575`
- prototype: `__int64 __fastcall(SIdxStringPool *this, char *, unsigned __int16, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800109d0`

## callees

- `0x1800012b8`
- `0x180023828`
- `0x18002b7c2`
- `0x180038c30`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800238fb`
- `wbemcomn!GetMemLogObject` at `0x18002399d`
- `wbemcomn!GetMemLogObject` at `0x180023a08`
- `wbemcomn!GetMemLogObject` at `0x1800238fb`
- `wbemcomn!GetMemLogObject` at `0x18002399d`
- `wbemcomn!GetMemLogObject` at `0x180023a08`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002390b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800239ad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180023a18`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002390b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800239ad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180023a18`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SIdxStringPool::AddStr(SIdxStringPool *this, char *a2, unsigned __int16 a3, int *a4)
{
  __int64 v4; // r14
  char *v6; // rsi
  __int64 v8; // rcx
  int v9; // edx
  int v10; // r15d
  int v11; // edx
  unsigned int v12; // ebp
  __int64 v13; // r8
  _BYTE *v14; // rdx
  __int64 v15; // rax
  _BYTE *v16; // rax
  CMemoryLog *MemLogObject; // rax
  unsigned int v19; // ebx
  CVarObjHeap *v20; // rcx
  __int64 v21; // rdx
  void *v22; // rcx
  CMemoryLog *v23; // rax
  int v24; // eax
  void *v25; // rcx
  CMemoryLog *v26; // rax
  int v27; // eax

  v4 = a3;
  v6 = a2;
  if ( a4 )
    *a4 = 0;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  v9 = *((_DWORD *)this + 9);
  if ( (unsigned int)(v9 + v8) > 0xFFFF )
  {
    MemLogObject = GetMemLogObject();
    v19 = 122;
    CMemoryLog::Write(MemLogObject, 122);
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v19;
    }
    v21 = 74;
    goto LABEL_26;
  }
  v10 = v8 + 1;
  if ( (int)v8 + 1 > (unsigned int)(*((_DWORD *)this + 8) - v9) )
  {
    v22 = _BtrMemReAlloc(*((void **)this + 3), 2 * *((_DWORD *)this + 8));
    if ( !v22 )
    {
      v23 = GetMemLogObject();
      v19 = 8;
      CMemoryLog::Write(v23, 8);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v19;
      }
      v21 = 75;
      goto LABEL_26;
    }
    v24 = *((_DWORD *)this + 8);
    *((_QWORD *)this + 3) = v22;
    *((_DWORD *)this + 8) = 2 * v24;
  }
  v11 = *((_DWORD *)this + 4);
  if ( *(_DWORD *)this == v11 )
  {
    v25 = _BtrMemReAlloc(*((void **)this + 1), 4 * v11);
    if ( v25 )
    {
      v27 = *((_DWORD *)this + 4);
      *((_QWORD *)this + 1) = v25;
      *((_DWORD *)this + 4) = 2 * v27;
      goto LABEL_8;
    }
    v26 = GetMemLogObject();
    v19 = 8;
    CMemoryLog::Write(v26, 8);
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v19;
    }
    v21 = 76;
LABEL_26:
    WPP_SF_d(*((_QWORD *)v20 + 2), v21, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, v19);
    return v19;
  }
LABEL_8:
  v12 = *((_DWORD *)this + 9);
  v13 = *((_DWORD *)this + 8) - v12;
  if ( (_DWORD)v13 )
  {
    v14 = (_BYTE *)(*((_QWORD *)this + 3) + v12);
    if ( (unsigned int)v13 > 0x7FFFFFFFuLL )
    {
      *v14 = 0;
    }
    else
    {
      v15 = 2147483646;
      do
      {
        if ( !v15 )
          break;
        if ( !*v6 )
          break;
        *v14++ = *v6++;
        --v15;
        --v13;
      }
      while ( v13 );
      v16 = v14 - 1;
      if ( v13 )
        v16 = v14;
      *v16 = 0;
    }
  }
  *((_DWORD *)this + 9) += v10;
  if ( *(_DWORD *)this != (_DWORD)v4 )
  {
    memmove_0(
      (void *)(*((_QWORD *)this + 1) + 2LL * (unsigned int)(v4 + 1)),
      (const void *)(*((_QWORD *)this + 1) + 2 * v4),
      2LL * (unsigned int)(*(_DWORD *)this - v4));
    if ( a4 )
      *a4 = 1;
  }
  *(_WORD *)(*((_QWORD *)this + 1) + 2 * v4) = v12;
  ++*(_DWORD *)this;
  return 0;
}

```

## disassembly

```asm
0x180023828  push    rbx
0x18002382a  push    rbp
0x18002382b  push    rsi
0x18002382c  push    rdi
0x18002382d  push    r14
0x18002382f  push    r15
0x180023831  sub     rsp, 28h
0x180023835  movzx   r14d, r8w
0x180023839  mov     rdi, r9
0x18002383c  mov     rsi, rdx
0x18002383f  mov     rbx, rcx
0x180023842  test    r9, r9
0x180023845  jnz     loc_180023950
0x18002384b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002384f  inc     rcx
0x180023852  cmp     byte ptr [rdx+rcx], 0
0x180023856  jnz     short loc_18002384F
0x180023858  mov     edx, [rbx+24h]
0x18002385b  lea     eax, [rdx+rcx]
0x18002385e  cmp     eax, 0FFFFh
0x180023863  ja      loc_1800238FB
0x180023869  lea     r15d, [rcx+1]
0x18002386d  mov     ecx, [rbx+20h]
0x180023870  mov     eax, ecx
0x180023872  sub     eax, edx
0x180023874  cmp     r15d, eax
0x180023877  ja      loc_180023989
0x18002387d  mov     edx, [rbx+10h]
0x180023880  cmp     [rbx], edx
0x180023882  jz      loc_1800239F4
0x180023888  mov     ebp, [rbx+24h]
0x18002388b  mov     r8d, [rbx+20h]
0x18002388f  sub     r8d, ebp
0x180023892  jz      short loc_1800238D6
0x180023894  mov     edx, ebp
0x180023896  add     rdx, [rbx+18h]
0x18002389a  cmp     r8, 7FFFFFFFh
0x1800238a1  ja      loc_180023A5F
0x1800238a7  mov     eax, 7FFFFFFEh
0x1800238ac  test    rax, rax
0x1800238af  jz      short loc_1800238C8
0x1800238b1  mov     cl, [rsi]
0x1800238b3  test    cl, cl
0x1800238b5  jz      short loc_1800238C8
0x1800238b7  mov     [rdx], cl
0x1800238b9  inc     rsi
0x1800238bc  inc     rdx
0x1800238bf  dec     rax
0x1800238c2  sub     r8, 1
0x1800238c6  jnz     short loc_1800238AC
0x1800238c8  test    r8, r8
0x1800238cb  lea     rax, [rdx-1]
0x1800238cf  cmovnz  rax, rdx
0x1800238d3  mov     byte ptr [rax], 0
0x1800238d6  add     [rbx+24h], r15d
0x1800238da  mov     eax, [rbx]
0x1800238dc  sub     eax, r14d
0x1800238df  jnz     short loc_180023928
0x1800238e1  mov     rax, [rbx+8]
0x1800238e5  mov     [rax+r14*2], bp
0x1800238ea  inc     dword ptr [rbx]
0x1800238ec  xor     eax, eax
0x1800238ee  add     rsp, 28h
0x1800238f2  pop     r15
0x1800238f4  pop     r14
0x1800238f6  pop     rdi
0x1800238f7  pop     rsi
0x1800238f8  pop     rbp
0x1800238f9  pop     rbx
0x1800238fa  retn
0x1800238fb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180023901  mov     ebx, 7Ah ; 'z'
0x180023906  mov     rcx, rax
0x180023909  mov     edx, ebx
0x18002390b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180023911  mov     rcx, cs:WPP_GLOBAL_Control
0x180023918  lea     rax, WPP_GLOBAL_Control
0x18002391f  cmp     rcx, rax
0x180023922  jnz     short loc_18002395C
0x180023924  mov     eax, ebx
0x180023926  jmp     short loc_1800238EE
0x180023928  mov     r9, [rbx+8]
0x18002392c  mov     r8d, eax
0x18002392f  lea     eax, [r14+1]
0x180023933  add     r8, r8; Size
0x180023936  lea     rdx, [r9+r14*2]; Src
0x18002393a  lea     rcx, [r9+rax*2]; void *
0x18002393e  call    memmove_0
0x180023943  test    rdi, rdi
0x180023946  jz      short loc_1800238E1
0x180023948  mov     dword ptr [rdi], 1
0x18002394e  jmp     short loc_1800238E1
0x180023950  mov     dword ptr [r9], 0
0x180023957  jmp     loc_18002384B
0x18002395c  test    byte ptr [rcx+1Ch], 1
0x180023960  jz      short loc_180023924
0x180023962  cmp     byte ptr [rcx+19h], 2
0x180023966  jb      short loc_180023924
0x180023968  mov     edx, 4Ah ; 'J'
0x18002396d  jmp     short loc_180023974
0x18002396f  mov     edx, 4Ch ; 'L'
0x180023974  mov     rcx, [rcx+10h]
0x180023978  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18002397f  mov     r9d, ebx
0x180023982  call    WPP_SF_d
0x180023987  jmp     short loc_180023924
0x180023989  lea     edx, [rcx+rcx]; unsigned int
0x18002398c  mov     rcx, [rbx+18h]; void *
0x180023990  call    ?_BtrMemReAlloc@@YAPEAXPEAXK@Z; _BtrMemReAlloc(void *,ulong)
0x180023995  mov     rcx, rax
0x180023998  test    rax, rax
0x18002399b  jnz     short loc_1800239E3
0x18002399d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800239a3  mov     ebx, 8
0x1800239a8  mov     rcx, rax
0x1800239ab  mov     edx, ebx
0x1800239ad  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800239b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800239ba  lea     rax, WPP_GLOBAL_Control
0x1800239c1  cmp     rcx, rax
0x1800239c4  jz      loc_180023924
0x1800239ca  test    byte ptr [rcx+1Ch], 1
0x1800239ce  jz      loc_180023924
0x1800239d4  cmp     byte ptr [rcx+19h], 2
0x1800239d8  jb      loc_180023924
0x1800239de  lea     edx, [rbx+43h]
0x1800239e1  jmp     short loc_180023974
0x1800239e3  mov     eax, [rbx+20h]
0x1800239e6  add     eax, eax
0x1800239e8  mov     [rbx+18h], rcx
0x1800239ec  mov     [rbx+20h], eax
0x1800239ef  jmp     loc_18002387D
0x1800239f4  mov     rcx, [rbx+8]; void *
0x1800239f8  shl     edx, 2; unsigned int
0x1800239fb  call    ?_BtrMemReAlloc@@YAPEAXPEAXK@Z; _BtrMemReAlloc(void *,ulong)
0x180023a00  mov     rcx, rax
0x180023a03  test    rax, rax
0x180023a06  jnz     short loc_180023A4E
0x180023a08  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180023a0e  mov     ebx, 8
0x180023a13  mov     rcx, rax
0x180023a16  mov     edx, ebx
0x180023a18  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180023a1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a25  lea     rax, WPP_GLOBAL_Control
0x180023a2c  cmp     rcx, rax
0x180023a2f  jz      loc_180023924
0x180023a35  test    byte ptr [rcx+1Ch], 1
0x180023a39  jz      loc_180023924
0x180023a3f  cmp     byte ptr [rcx+19h], 2
0x180023a43  jb      loc_180023924
0x180023a49  jmp     loc_18002396F
0x180023a4e  mov     eax, [rbx+10h]
0x180023a51  add     eax, eax
0x180023a53  mov     [rbx+8], rcx
0x180023a57  mov     [rbx+10h], eax
0x180023a5a  jmp     loc_180023888
0x180023a5f  mov     byte ptr [rdx], 0
0x180023a62  jmp     loc_1800238D6
```
