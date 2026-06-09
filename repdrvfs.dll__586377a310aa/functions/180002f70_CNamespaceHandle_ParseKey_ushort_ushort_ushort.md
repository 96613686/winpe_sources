# CNamespaceHandle::ParseKey(ushort *,ushort * *,ushort * *)

- ea: `0x180002f70`
- end: `0x18000328c`
- name: `?ParseKey@CNamespaceHandle@@IEAAJPEAGPEAPEAG1@Z`
- size: `796`
- prototype: `int(CNamespaceHandle *__hidden this, unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004310`

## callees

- `0x1800012b8`
- `0x1800013c8`
- `0x180002f70`

## import_xrefs

- `msvcrt!wcschr` at `0x180002fb8`
- `msvcrt!wcschr` at `0x180002fb8`
- `wbemcomn!GetMemLogObject` at `0x1800030bc`
- `wbemcomn!GetMemLogObject` at `0x180003115`
- `wbemcomn!GetMemLogObject` at `0x1800031b9`
- `wbemcomn!GetMemLogObject` at `0x180003219`
- `wbemcomn!GetMemLogObject` at `0x1800030bc`
- `wbemcomn!GetMemLogObject` at `0x180003115`
- `wbemcomn!GetMemLogObject` at `0x1800031b9`
- `wbemcomn!GetMemLogObject` at `0x180003219`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800030ca`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003123`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800031c7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003227`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800030ca`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003123`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800031c7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003227`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::ParseKey(
        CNamespaceHandle *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  wchar_t *v7; // rax
  __int64 v8; // rax
  unsigned __int16 *v10; // rcx
  unsigned __int16 v12; // cx
  unsigned __int16 *v13; // rbx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rdx
  unsigned __int16 v16; // dx
  unsigned __int16 *v17; // rax
  unsigned __int16 v18; // ax
  unsigned __int16 *v19; // rbx
  unsigned __int16 *v20; // rcx
  unsigned __int16 *v21; // rdx
  CMemoryLog *v22; // rax
  CVarObjHeap *v23; // rcx
  CMemoryLog *MemLogObject; // rax
  __int64 v25; // rdx
  unsigned __int16 v26; // dx
  CMemoryLog *v27; // rax
  CMemoryLog *v28; // rax

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, a2);
  }
  if ( *a2 == 39 )
  {
    v12 = a2[1];
    v13 = a2 + 1;
    v14 = v13;
    if ( !v12 )
      goto LABEL_35;
    while ( 1 )
    {
      v15 = v14;
      if ( v12 == 39 )
        break;
      ++v14;
      *v15 = v12;
      v12 = *v14;
      if ( !*v14 )
        goto LABEL_35;
    }
    if ( !*v14 )
    {
LABEL_35:
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217350);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749946LL;
      }
      v25 = 125;
      goto LABEL_65;
    }
    *v14 = 0;
    if ( a3 )
      *a3 = v13;
    v16 = v14[1];
    v10 = v14 + 1;
    if ( !v16 || v16 == 44 )
    {
      if ( !a4 )
        return 0;
      if ( !v16 )
        goto LABEL_11;
      v17 = v14 + 2;
      goto LABEL_47;
    }
    v27 = GetMemLogObject();
    CMemoryLog::Write(v27, -2147217350);
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v25 = 126;
LABEL_65:
      WPP_SF_d(*((_QWORD *)v23 + 2), v25, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749946LL);
    }
  }
  else
  {
    if ( *a2 != 34 )
    {
      if ( a3 )
        *a3 = a2;
      v7 = wcschr(a2, 0x2Cu);
      if ( !v7 )
      {
        if ( !a4 )
          return 0;
        v8 = -1;
        while ( a2[++v8] != 0 )
          ;
        v10 = &a2[v8];
LABEL_11:
        *a4 = v10;
        return 0;
      }
      *v7 = 0;
      if ( !a4 )
        return 0;
      v17 = v7 + 1;
LABEL_47:
      *a4 = v17;
      return 0;
    }
    v18 = a2[1];
    v19 = a2 + 1;
    v20 = v19;
    if ( !v18 )
      goto LABEL_30;
    v21 = v19;
    while ( v18 != 34 )
    {
      if ( v18 == 92 )
      {
        v18 = v20[1];
        if ( v18 == 120 )
        {
          v18 = 92;
        }
        else if ( v18 == 88 )
        {
          v18 = 92;
        }
        else
        {
          ++v20;
        }
      }
      ++v20;
      *v21++ = v18;
      v18 = *v20;
      if ( !*v20 )
        goto LABEL_30;
    }
    if ( !*v20 )
    {
LABEL_30:
      v22 = GetMemLogObject();
      CMemoryLog::Write(v22, -2147217350);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749946LL;
      }
      v25 = 127;
      goto LABEL_65;
    }
    *v21 = 0;
    if ( a3 )
      *a3 = v19;
    v26 = v20[1];
    v17 = v20 + 1;
    if ( !v26 || v26 == 44 )
    {
      if ( !a4 )
        return 0;
      if ( v26 )
      {
        *a4 = v20 + 2;
        return 0;
      }
      goto LABEL_47;
    }
    v28 = GetMemLogObject();
    CMemoryLog::Write(v28, -2147217350);
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v25 = 128;
      goto LABEL_65;
    }
  }
  return 2147749946LL;
}

```

## disassembly

```asm
0x180002f70  push    rbx
0x180002f72  push    rbp
0x180002f73  push    rsi
0x180002f74  push    rdi
0x180002f75  sub     rsp, 28h
0x180002f79  mov     rsi, r9
0x180002f7c  mov     rdi, r8
0x180002f7f  mov     rbx, rdx
0x180002f82  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f89  lea     rbp, WPP_GLOBAL_Control
0x180002f90  cmp     rcx, rbp
0x180002f93  jnz     short loc_180002FF1
0x180002f95  movzx   eax, word ptr [rbx]
0x180002f98  cmp     ax, 27h ; '''
0x180002f9c  jz      short loc_18000301A
0x180002f9e  cmp     ax, 22h ; '"'
0x180002fa2  jz      loc_180003080
0x180002fa8  test    rdi, rdi
0x180002fab  jz      short loc_180002FB0
0x180002fad  mov     [rdi], rbx
0x180002fb0  mov     edx, 2Ch ; ','; Ch
0x180002fb5  mov     rcx, rbx; Str
0x180002fb8  call    cs:__imp_wcschr
0x180002fbe  test    rax, rax
0x180002fc1  jnz     loc_18000314B
0x180002fc7  test    rsi, rsi
0x180002fca  jz      short loc_180002FE6
0x180002fcc  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180002fd3  cmp     word ptr [rbx+rax*2+2], 0
0x180002fd9  lea     rax, [rax+1]
0x180002fdd  jnz     short loc_180002FD3
0x180002fdf  lea     rcx, [rbx+rax*2]
0x180002fe3  mov     [rsi], rcx
0x180002fe6  xor     eax, eax
0x180002fe8  add     rsp, 28h
0x180002fec  pop     rdi
0x180002fed  pop     rsi
0x180002fee  pop     rbp
0x180002fef  pop     rbx
0x180002ff0  retn
0x180002ff1  test    byte ptr [rcx+1Ch], 1
0x180002ff5  jz      short loc_180002F95
0x180002ff7  cmp     byte ptr [rcx+19h], 5
0x180002ffb  jb      short loc_180002F95
0x180002ffd  mov     rcx, [rcx+10h]
0x180003001  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180003008  mov     edx, 7Ch ; '|'
0x18000300d  mov     r9, rbx
0x180003010  call    WPP_SF_S
0x180003015  jmp     loc_180002F95
0x18000301a  movzx   ecx, word ptr [rbx+2]
0x18000301e  add     rbx, 2
0x180003022  mov     rax, rbx
0x180003025  test    cx, cx
0x180003028  jz      loc_180003115
0x18000302e  mov     rdx, rax
0x180003031  cmp     cx, 27h ; '''
0x180003035  jnz     loc_180003102
0x18000303b  cmp     word ptr [rax], 0
0x18000303f  jz      loc_180003115
0x180003045  xor     r8d, r8d
0x180003048  mov     [rax], r8w
0x18000304c  test    rdi, rdi
0x18000304f  jz      short loc_180003054
0x180003051  mov     [rdi], rbx
0x180003054  movzx   edx, word ptr [rax+2]
0x180003058  lea     rcx, [rax+2]
0x18000305c  test    dx, dx
0x18000305f  jnz     loc_1800031AF
0x180003065  test    rsi, rsi
0x180003068  jz      loc_180002FE6
0x18000306e  test    dx, dx
0x180003071  jz      loc_180002FE3
0x180003077  add     rax, 4
0x18000307b  jmp     loc_180003196
0x180003080  movzx   eax, word ptr [rbx+2]
0x180003084  add     rbx, 2
0x180003088  mov     rcx, rbx
0x18000308b  test    ax, ax
0x18000308e  jz      short loc_1800030BC
0x180003090  mov     rdx, rbx
0x180003093  mov     r9d, 5Ch ; '\'
0x180003099  cmp     ax, 22h ; '"'
0x18000309d  jz      loc_180003161
0x1800030a3  cmp     ax, r9w
0x1800030a7  jz      short loc_1800030EE
0x1800030a9  add     rcx, 2
0x1800030ad  mov     [rdx], ax
0x1800030b0  add     rdx, 2
0x1800030b4  movzx   eax, word ptr [rcx]
0x1800030b7  test    ax, ax
0x1800030ba  jnz     short loc_180003099
0x1800030bc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800030c2  mov     rcx, rax
0x1800030c5  mov     edx, 8004103Ah
0x1800030ca  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800030d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030d7  cmp     rcx, rbp
0x1800030da  jnz     loc_180003258
0x1800030e0  mov     eax, 8004103Ah
0x1800030e5  add     rsp, 28h
0x1800030e9  pop     rdi
0x1800030ea  pop     rsi
0x1800030eb  pop     rbp
0x1800030ec  pop     rbx
0x1800030ed  retn
0x1800030ee  movzx   eax, word ptr [rcx+2]
0x1800030f2  cmp     ax, 78h ; 'x'
0x1800030f6  jnz     loc_1800031F8
0x1800030fc  movzx   eax, r9w
0x180003100  jmp     short loc_1800030A9
0x180003102  add     rax, 2
0x180003106  mov     [rdx], cx
0x180003109  movzx   ecx, word ptr [rax]
0x18000310c  test    cx, cx
0x18000310f  jnz     loc_18000302E
0x180003115  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000311b  mov     rcx, rax
0x18000311e  mov     edx, 8004103Ah
0x180003123  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180003129  mov     rcx, cs:WPP_GLOBAL_Control
0x180003130  cmp     rcx, rbp
0x180003133  jz      short loc_1800030E0
0x180003135  test    byte ptr [rcx+1Ch], 1
0x180003139  jz      short loc_1800030E0
0x18000313b  cmp     byte ptr [rcx+19h], 2
0x18000313f  jb      short loc_1800030E0
0x180003141  mov     edx, 7Dh ; '}'
0x180003146  jmp     loc_180003271
0x18000314b  xor     r8d, r8d
0x18000314e  mov     [rax], r8w
0x180003152  test    rsi, rsi
0x180003155  jz      loc_180002FE6
0x18000315b  add     rax, 2
0x18000315f  jmp     short loc_180003196
0x180003161  cmp     word ptr [rcx], 0
0x180003165  jz      loc_1800030BC
0x18000316b  xor     r8d, r8d
0x18000316e  mov     [rdx], r8w
0x180003172  test    rdi, rdi
0x180003175  jnz     short loc_18000319E
0x180003177  movzx   edx, word ptr [rcx+2]
0x18000317b  lea     rax, [rcx+2]
0x18000317f  test    dx, dx
0x180003182  jnz     loc_18000320F
0x180003188  test    rsi, rsi
0x18000318b  jz      loc_180002FE6
0x180003191  test    dx, dx
0x180003194  jnz     short loc_1800031A3
0x180003196  mov     [rsi], rax
0x180003199  jmp     loc_180002FE6
0x18000319e  mov     [rdi], rbx
0x1800031a1  jmp     short loc_180003177
0x1800031a3  lea     rax, [rcx+4]
0x1800031a7  mov     [rsi], rax
0x1800031aa  jmp     loc_180002FE6
0x1800031af  cmp     dx, 2Ch ; ','
0x1800031b3  jz      loc_180003065
0x1800031b9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800031bf  mov     rcx, rax
0x1800031c2  mov     edx, 8004103Ah
0x1800031c7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800031cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031d4  cmp     rcx, rbp
0x1800031d7  jz      loc_1800030E0
0x1800031dd  test    byte ptr [rcx+1Ch], 1
0x1800031e1  jz      loc_1800030E0
0x1800031e7  cmp     byte ptr [rcx+19h], 2
0x1800031eb  jb      loc_1800030E0
0x1800031f1  mov     edx, 7Eh ; '~'
0x1800031f6  jmp     short loc_180003271
0x1800031f8  cmp     ax, 58h ; 'X'
0x1800031fc  jz      short loc_180003207
0x1800031fe  add     rcx, 2
0x180003202  jmp     loc_1800030A9
0x180003207  mov     eax, r9d
0x18000320a  jmp     loc_1800030A9
0x18000320f  cmp     dx, 2Ch ; ','
0x180003213  jz      loc_180003188
0x180003219  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000321f  mov     rcx, rax
0x180003222  mov     edx, 8004103Ah
0x180003227  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000322d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003234  cmp     rcx, rbp
0x180003237  jz      loc_1800030E0
0x18000323d  test    byte ptr [rcx+1Ch], 1
0x180003241  jz      loc_1800030E0
0x180003247  cmp     byte ptr [rcx+19h], 2
0x18000324b  jb      loc_1800030E0
0x180003251  mov     edx, 80h
0x180003256  jmp     short loc_180003271
0x180003258  test    byte ptr [rcx+1Ch], 1
0x18000325c  jz      loc_1800030E0
0x180003262  cmp     byte ptr [rcx+19h], 2
0x180003266  jb      loc_1800030E0
0x18000326c  mov     edx, 7Fh
0x180003271  mov     rcx, [rcx+10h]
0x180003275  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18000327c  mov     r9d, 8004103Ah
0x180003282  call    WPP_SF_d
0x180003287  jmp     loc_1800030E0
```
