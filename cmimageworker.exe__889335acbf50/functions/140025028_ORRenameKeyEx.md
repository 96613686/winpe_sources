# ORRenameKeyEx

- ea: `0x140025028`
- end: `0x140025253`
- name: `ORRenameKeyEx`
- size: `555`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140024ff0`

## callees

- `0x1400029d2`
- `0x140002d72`
- `0x140024888`
- `0x140024f20`
- `0x140025028`
- `0x140026bbc`
- `0x140026fa8`
- `0x140026ff0`
- `0x14002a1ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400250f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400250f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140025242`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140025242`

## pseudocode

```c
__int64 __fastcall ORRenameKeyEx(__int64 a1, unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // r14
  unsigned int v6; // eax
  unsigned __int16 v7; // cx
  unsigned int v9; // ecx
  __int64 v10; // rbp
  __int64 v11; // r13
  _OWORD *v12; // r15
  _OWORD *v13; // rax
  __int16 v14; // cx
  __int16 v15; // ax
  __int16 v16; // cx
  __int64 v17; // rdx
  unsigned int v18; // r8d
  __int64 v19; // [rsp+70h] [rbp+8h] BYREF

  v19 = 0;
  if ( *(_WORD *)(a1 + 28) == 29806 && (v5 = *(_QWORD *)(a1 + 16), *(_DWORD *)v5 == -1092567328) )
  {
    v6 = *a2;
    if ( (v6 & 1) != 0 )
      return RtlNtStatusToDosError_0(-1073741811);
    v7 = a2[1];
    if ( (v7 & 1) != 0 || (unsigned __int16)v6 > v7 || v7 == 0xFFFF )
      return RtlNtStatusToDosError_0(-1073741811);
    if ( !*((_QWORD *)a2 + 1) )
    {
      if ( (_WORD)v6 || v7 )
        return RtlNtStatusToDosError_0(-1073741811);
      return 87;
    }
    if ( !(_WORD)v6 || (unsigned __int16)v6 > 0x200u )
      return 87;
    if ( v6 >> 1 )
    {
      v9 = 0;
      while ( *(_WORD *)(*((_QWORD *)a2 + 1) + 2LL * v9) != 92 )
      {
        if ( ++v9 >= v6 >> 1 )
          goto LABEL_20;
      }
      return 87;
    }
LABEL_20:
    EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 136));
    if ( *(_WORD *)(a1 + 30) )
    {
      v4 = 1018;
    }
    else if ( *(_QWORD *)(v5 + 56) == a1 )
    {
      v4 = 87;
    }
    else
    {
      v10 = *(_QWORD *)(a1 + 72);
      if ( (unsigned int)ORParseSubKey(a2, v10, 0, &v19) == 2 )
      {
        v11 = (unsigned __int16)ORGetCompressedLength(*(_QWORD *)(v5 + 16), a2);
        v12 = o__aligned_malloc_0(v11 + 76, 0x10u);
        if ( v12 )
        {
          v13 = *(_OWORD **)(a1 + 40);
          *v12 = *v13;
          v12[1] = v13[1];
          v12[2] = v13[2];
          v12[3] = v13[3];
          *(_OWORD *)((char *)v12 + 60) = *(_OWORD *)((char *)v13 + 60);
          v14 = *((_WORD *)v12 + 1);
          *((_WORD *)v12 + 36) = v11;
          v15 = v14 & 0xFFDF;
          v16 = v14 | 0x20;
          if ( (_WORD)v11 == *a2 )
            v16 = v15;
          *((_WORD *)v12 + 1) = v16;
          ORCompressCopyName((char *)v12 + 76, v11, *(_QWORD *)(v5 + 16), a2);
          ORRemoveSubKey(v10, a1);
          ORFreeOrNop(v5, a1 + 40);
          *(_QWORD *)(a1 + 40) = v12;
          if ( v10 && *(_WORD *)(v10 + 28) == 29806 && *(_WORD *)(a1 + 28) == 29806 )
            ORInsertTreeNodeIntoSubkeyList(v10, a1);
          v17 = *(_QWORD *)(v10 + 40);
          v18 = *a2;
          if ( *(unsigned __int16 *)(v17 + 52) < v18 )
            *(_WORD *)(v17 + 52) = v18;
          ++*(_QWORD *)(v10 + 168);
          v4 = 0;
          *(_DWORD *)(v5 + 180) = 1;
        }
        else
        {
          v4 = 8;
        }
      }
      else
      {
        v4 = 183;
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 136));
  }
  else
  {
    return 6;
  }
  return v4;
}

```

## disassembly

```asm
0x140025028  push    rbx
0x14002502a  push    rbp
0x14002502b  push    rsi
0x14002502c  push    rdi
0x14002502d  push    r12
0x14002502f  push    r13
0x140025031  push    r14
0x140025033  push    r15
0x140025035  sub     rsp, 28h
0x140025039  xor     ebx, ebx
0x14002503b  mov     eax, 746Eh
0x140025040  mov     rsi, rdx
0x140025043  mov     rdi, rcx
0x140025046  mov     [rsp+68h+arg_0], rbx
0x14002504b  cmp     [rcx+1Ch], ax
0x14002504f  jz      short loc_140025058
0x140025051  mov     ebx, 6
0x140025056  jmp     short loc_1400250A0
0x140025058  mov     r14, [rcx+10h]
0x14002505c  cmp     dword ptr [r14], 0BEE0BEE0h
0x140025063  jnz     short loc_140025051
0x140025065  movzx   eax, word ptr [rdx]
0x140025068  test    al, 1
0x14002506a  jnz     short loc_140025094
0x14002506c  movzx   ecx, word ptr [rdx+2]
0x140025070  test    cl, 1
0x140025073  jnz     short loc_140025094
0x140025075  cmp     ax, cx
0x140025078  ja      short loc_140025094
0x14002507a  mov     edx, 0FFFEh
0x14002507f  cmp     cx, dx
0x140025082  ja      short loc_140025094
0x140025084  cmp     [rsi+8], rbx
0x140025088  jnz     short loc_1400250B4
0x14002508a  test    ax, ax
0x14002508d  jnz     short loc_140025094
0x14002508f  test    cx, cx
0x140025092  jz      short loc_1400250B9
0x140025094  mov     ecx, 0C000000Dh; Status
0x140025099  call    RtlNtStatusToDosError_0
0x14002509e  mov     ebx, eax
0x1400250a0  mov     eax, ebx
0x1400250a2  add     rsp, 28h
0x1400250a6  pop     r15
0x1400250a8  pop     r14
0x1400250aa  pop     r13
0x1400250ac  pop     r12
0x1400250ae  pop     rdi
0x1400250af  pop     rsi
0x1400250b0  pop     rbp
0x1400250b1  pop     rbx
0x1400250b2  retn
0x1400250b4  test    ax, ax
0x1400250b7  jnz     short loc_1400250C0
0x1400250b9  mov     ebx, 57h ; 'W'
0x1400250be  jmp     short loc_1400250A0
0x1400250c0  mov     ecx, 200h
0x1400250c5  cmp     ax, cx
0x1400250c8  ja      short loc_1400250B9
0x1400250ca  mov     edx, eax
0x1400250cc  shr     edx, 1
0x1400250ce  jz      short loc_1400250E6
0x1400250d0  mov     r8, [rsi+8]
0x1400250d4  mov     ecx, ebx
0x1400250d6  mov     eax, ecx
0x1400250d8  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x1400250de  jz      short loc_1400250B9
0x1400250e0  inc     ecx
0x1400250e2  cmp     ecx, edx
0x1400250e4  jb      short loc_1400250D6
0x1400250e6  lea     r12, [r14+88h]
0x1400250ed  mov     rcx, r12; lpCriticalSection
0x1400250f0  call    cs:__imp_EnterCriticalSection
0x1400250f7  nop     dword ptr [rax+rax+00h]
0x1400250fc  cmp     [rdi+1Eh], bx
0x140025100  jz      short loc_14002510C
0x140025102  mov     ebx, 3FAh
0x140025107  jmp     loc_14002523F
0x14002510c  cmp     [r14+38h], rdi
0x140025110  jnz     short loc_14002511C
0x140025112  mov     ebx, 57h ; 'W'
0x140025117  jmp     loc_14002523F
0x14002511c  mov     rbp, [rdi+48h]
0x140025120  lea     r9, [rsp+68h+arg_0]
0x140025125  mov     rdx, rbp
0x140025128  xor     r8d, r8d
0x14002512b  mov     rcx, rsi
0x14002512e  call    ORParseSubKey
0x140025133  cmp     eax, 2
0x140025136  jz      short loc_140025142
0x140025138  mov     ebx, 0B7h
0x14002513d  jmp     loc_14002523F
0x140025142  mov     rcx, [r14+10h]
0x140025146  mov     rdx, rsi
0x140025149  call    ORGetCompressedLength
0x14002514e  movzx   r13d, ax
0x140025152  mov     edx, 10h; Alignment
0x140025157  lea     rcx, [r13+4Ch]; Size
0x14002515b  call    _o__aligned_malloc_0
0x140025160  mov     r15, rax
0x140025163  test    rax, rax
0x140025166  jnz     short loc_140025170
0x140025168  lea     ebx, [rax+8]
0x14002516b  jmp     loc_14002523F
0x140025170  lea     rbx, [rdi+28h]
0x140025174  mov     edx, 0FFDFh
0x140025179  mov     rax, [rbx]
0x14002517c  mov     r9, rsi
0x14002517f  movups  xmm0, xmmword ptr [rax]
0x140025182  movups  xmmword ptr [r15], xmm0
0x140025186  movups  xmm1, xmmword ptr [rax+10h]
0x14002518a  movups  xmmword ptr [r15+10h], xmm1
0x14002518f  movups  xmm0, xmmword ptr [rax+20h]
0x140025193  movups  xmmword ptr [r15+20h], xmm0
0x140025198  movups  xmm1, xmmword ptr [rax+30h]
0x14002519c  movups  xmmword ptr [r15+30h], xmm1
0x1400251a1  movups  xmm0, xmmword ptr [rax+3Ch]
0x1400251a5  movups  xmmword ptr [r15+3Ch], xmm0
0x1400251aa  movzx   ecx, word ptr [r15+2]
0x1400251af  movzx   eax, cx
0x1400251b2  mov     [r15+48h], r13w
0x1400251b7  and     ax, dx
0x1400251ba  or      cx, 20h
0x1400251be  cmp     r13w, [rsi]
0x1400251c2  mov     rdx, r13
0x1400251c5  cmovz   cx, ax
0x1400251c9  mov     [r15+2], cx
0x1400251ce  lea     rcx, [r15+4Ch]
0x1400251d2  mov     r8, [r14+10h]
0x1400251d6  call    ORCompressCopyName
0x1400251db  mov     rdx, rdi
0x1400251de  mov     rcx, rbp
0x1400251e1  call    ORRemoveSubKey
0x1400251e6  mov     rdx, rbx
0x1400251e9  mov     rcx, r14
0x1400251ec  call    ORFreeOrNop
0x1400251f1  mov     [rbx], r15
0x1400251f4  test    rbp, rbp
0x1400251f7  jz      short loc_140025215
0x1400251f9  mov     eax, 746Eh
0x1400251fe  cmp     [rbp+1Ch], ax
0x140025202  jnz     short loc_140025215
0x140025204  cmp     [rdi+1Ch], ax
0x140025208  jnz     short loc_140025215
0x14002520a  mov     rdx, rdi
0x14002520d  mov     rcx, rbp
0x140025210  call    ORInsertTreeNodeIntoSubkeyList
0x140025215  mov     rdx, [rbp+28h]
0x140025219  movzx   r8d, word ptr [rsi]
0x14002521d  movzx   eax, word ptr [rdx+34h]
0x140025221  cmp     eax, r8d
0x140025224  jnb     short loc_14002522B
0x140025226  mov     [rdx+34h], r8w
0x14002522b  inc     qword ptr [rbp+0A8h]
0x140025232  xor     ebx, ebx
0x140025234  mov     dword ptr [r14+0B4h], 1
0x14002523f  mov     rcx, r12; lpCriticalSection
0x140025242  call    cs:__imp_LeaveCriticalSection
0x140025249  nop     dword ptr [rax+rax+00h]
0x14002524e  jmp     loc_1400250A0
```
