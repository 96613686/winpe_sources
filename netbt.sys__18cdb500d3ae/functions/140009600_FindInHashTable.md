# FindInHashTable

- ea: `0x140009600`
- end: `0x14000983e`
- name: `FindInHashTable`
- size: `574`
- prototype: ``
- caller_count: `19`
- callee_count: `6`
- tags: ``

## callers

- `0x140001ee4`
- `0x1400031bc`
- `0x14000508c`
- `0x140006e2c`
- `0x140007354`
- `0x140008160`
- `0x140008840`
- `0x140008a74`
- `0x140009150`
- `0x140015818`
- `0x14001854c`
- `0x14001d0b4`
- `0x14001fc60`
- `0x140021ff8`
- `0x1400232bc`
- `0x140028fb0`
- `0x14002919c`
- `0x14002e5a8`
- `0x14005231c`

## callees

- `0x140007ff8`
- `0x1400089c8`
- `0x140009600`
- `0x140030e76`
- `0x140031020`
- `0x1400439bc`

## pseudocode

```c
__int64 __fastcall FindInHashTable(_DWORD *a1, _BYTE *a2, const char *a3, _QWORD *a4)
{
  __int64 v6; // rdi
  _QWORD *v8; // r14
  _QWORD *v9; // rbx
  unsigned __int64 v10; // r15
  __int64 v11; // rcx
  _QWORD *v12; // rbp
  __int64 v13; // rcx
  _QWORD *v14; // rax
  int v15; // eax
  unsigned int v16; // ecx
  bool v17; // zf
  __int64 v18; // rax

  LODWORD(v6) = 0;
  if ( a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
  }
  v8 = &a1[4 * (((a2[1] & 0xF) + 16 * (*a2 & 0xF)) % *a1) + 2];
  v9 = (_QWORD *)*v8;
  v10 = MEMORY[0xFFFFF78000000008] / 0x2710uLL;
  if ( (_QWORD *)*v8 == v8 )
    return 3221225473LL;
  while ( 1 )
  {
    v11 = v9[19];
    v12 = (_QWORD *)*v9;
    if ( v11 && (__int64)(v11 + *((unsigned int *)v9 + 14) - v10) <= 0 )
    {
      if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
        WPP_SF_qddds(
          *((_DWORD *)v9 + 5),
          81,
          (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
          (_DWORD)v9,
          *((_DWORD *)v9 + 5),
          *((_DWORD *)v9 + 5) - 1,
          7,
          (__int64)"minio\\netbt\\sys\\hashtbl.c");
      if ( *((_DWORD *)v9 + 4) == -87097344 )
        --dword_140039760;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9 + 5, 0xFFFFFFFF) == 1 )
      {
        v13 = *v9;
        if ( *v9 )
        {
          v14 = (_QWORD *)v9[1];
          if ( v14 )
          {
            if ( *(_QWORD **)(v13 + 8) != v9 || (_QWORD *)*v14 != v9 )
              __fastfail(3u);
            *v14 = v13;
            *(_QWORD *)(v13 + 8) = v14;
          }
        }
        if ( *((_DWORD *)v9 + 4) == -87097344 && --dword_140039608 < 0 )
          dword_140039608 = 0;
        NbtFreeNameAddr(v9);
      }
      else
      {
        NbtCheckNameAddrTimer(v9);
      }
      goto LABEL_34;
    }
    v15 = *((_DWORD *)v9 + 18);
    v16 = (v15 & 0x1000) != 0 ? *((_DWORD *)v9 + 28) : 16;
    if ( (v15 & 0x20) == 0 && !memcmp(a2, (char *)v9 + 164, v16) )
    {
      if ( !a3 )
        break;
      if ( a1 == qword_140039460 )
      {
        v17 = strncmp_0(a3, (const char *)Str2, (unsigned __int16)word_1400395DC) == 0;
      }
      else
      {
        v18 = v9[15];
        v17 = v18 ? strncmp_0(a3, (const char *)(v18 + 164), *(unsigned int *)(v18 + 112)) == 0 : (_DWORD)v6 == 0;
      }
      if ( v17 )
        break;
    }
LABEL_34:
    v9 = v12;
    if ( v12 == v8 )
      return 3221225473LL;
  }
  *a4 = v9;
  return 0;
}

```

## disassembly

```asm
0x140009600  mov     [rsp+arg_18], r9
0x140009605  push    rbx
0x140009606  push    rsi
0x140009607  push    rdi
0x140009608  push    r12
0x14000960a  push    r13
0x14000960c  push    r14
0x14000960e  push    r15
0x140009610  sub     rsp, 40h
0x140009614  movzx   eax, byte ptr [rdx]
0x140009617  mov     r13, rdx
0x14000961a  movzx   r10d, byte ptr [rdx+1]
0x14000961f  and     eax, 0Fh
0x140009622  shl     eax, 4
0x140009625  and     r10d, 0Fh
0x140009629  add     eax, r10d
0x14000962c  mov     rsi, r8
0x14000962f  cdq
0x140009630  xor     edi, edi
0x140009632  idiv    dword ptr [rcx]
0x140009634  mov     r12, rcx
0x140009637  movsxd  r8, edx
0x14000963a  test    rsi, rsi
0x14000963d  jz      short loc_14000964F
0x14000963f  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x140009646  inc     rdi
0x140009649  cmp     byte ptr [rsi+rdi], 0
0x14000964d  jnz     short loc_140009646
0x14000964f  mov     rcx, 0FFFFF78000000008h
0x140009659  mov     [rsp+78h+arg_8], rbp
0x140009661  mov     rax, 346DC5D63886594Bh
0x14000966b  mov     r14, r8
0x14000966e  shl     r14, 4
0x140009672  add     r14, 8
0x140009676  mov     rcx, [rcx]
0x140009679  add     r14, r12
0x14000967c  mul     rcx
0x14000967f  mov     rbx, [r14]
0x140009682  mov     r15, rdx
0x140009685  shr     r15, 0Bh
0x140009689  cmp     rbx, r14
0x14000968c  jz      loc_14000980A
0x140009692  lea     r8, aMinioNetbtSysH_0; "minio\\netbt\\sys\\hashtbl.c"
0x140009699  nop     dword ptr [rax+00000000h]
0x1400096a0  mov     rcx, [rbx+98h]
0x1400096a7  mov     rbp, [rbx]
0x1400096aa  test    rcx, rcx
0x1400096ad  jz      loc_140009779
0x1400096b3  mov     eax, [rbx+38h]
0x1400096b6  sub     rax, r15
0x1400096b9  add     rax, rcx
0x1400096bc  test    rax, rax
0x1400096bf  jg      loc_140009779
0x1400096c5  test    byte ptr cs:xmmword_140038420+9, 40h
0x1400096cc  jz      short loc_1400096FD
0x1400096ce  mov     ecx, [rbx+14h]
0x1400096d1  mov     edx, 51h ; 'Q'
0x1400096d6  mov     [rsp+78h+var_40], r8
0x1400096db  mov     r9, rbx
0x1400096de  mov     [rsp+78h+var_48], 307h
0x1400096e6  lea     r8, WPP_8017b60c53a232e581eda6237e04704c_Traceguids
0x1400096ed  lea     eax, [rcx-1]
0x1400096f0  mov     [rsp+78h+var_50], eax
0x1400096f4  mov     [rsp+78h+var_58], ecx
0x1400096f8  call    WPP_SF_qddds
0x1400096fd  cmp     dword ptr [rbx+10h], 0FACF0000h
0x140009704  jnz     short loc_14000970C
0x140009706  dec     cs:dword_140039760
0x14000970c  mov     eax, 0FFFFFFFFh
0x140009711  lock xadd [rbx+14h], eax
0x140009716  cmp     eax, 1
0x140009719  jz      short loc_140009728
0x14000971b  mov     rcx, rbx
0x14000971e  call    NbtCheckNameAddrTimer
0x140009723  jmp     loc_1400097F7
0x140009728  mov     rcx, [rbx]
0x14000972b  test    rcx, rcx
0x14000972e  jz      short loc_140009753
0x140009730  mov     rax, [rbx+8]
0x140009734  test    rax, rax
0x140009737  jz      short loc_140009753
0x140009739  cmp     [rcx+8], rbx
0x14000973d  jnz     loc_140009828
0x140009743  cmp     [rax], rbx
0x140009746  jnz     loc_140009828
0x14000974c  mov     [rax], rcx
0x14000974f  mov     [rcx+8], rax
0x140009753  cmp     dword ptr [rbx+10h], 0FACF0000h
0x14000975a  jnz     short loc_14000976F
0x14000975c  sub     cs:dword_140039608, 1
0x140009763  jns     short loc_14000976F
0x140009765  mov     cs:dword_140039608, 0
0x14000976f  mov     rcx, rbx; P
0x140009772  call    NbtFreeNameAddr
0x140009777  jmp     short loc_1400097F7
0x140009779  mov     eax, [rbx+48h]
0x14000977c  bt      eax, 0Ch
0x140009780  jnb     short loc_140009787
0x140009782  mov     ecx, [rbx+70h]
0x140009785  jmp     short loc_14000978C
0x140009787  mov     ecx, 10h
0x14000978c  test    al, 20h
0x14000978e  jnz     short loc_1400097FE
0x140009790  mov     r8d, ecx; Size
0x140009793  lea     rdx, [rbx+0A4h]; Buf2
0x14000979a  mov     rcx, r13; Buf1
0x14000979d  call    memcmp
0x1400097a2  test    eax, eax
0x1400097a4  jnz     short loc_1400097F7
0x1400097a6  test    rsi, rsi
0x1400097a9  jz      loc_14000982F
0x1400097af  cmp     r12, cs:qword_140039460
0x1400097b6  jnz     short loc_1400097D3
0x1400097b8  mov     rdx, cs:Str2; Str2
0x1400097bf  mov     rcx, rsi; Str1
0x1400097c2  movzx   r8d, cs:word_1400395DC; MaxCount
0x1400097ca  call    strncmp_0
0x1400097cf  test    eax, eax
0x1400097d1  jmp     short loc_1400097F5
0x1400097d3  mov     rax, [rbx+78h]
0x1400097d7  test    rax, rax
0x1400097da  jz      short loc_1400097F3
0x1400097dc  mov     r8d, [rax+70h]; MaxCount
0x1400097e0  lea     rdx, [rax+0A4h]; Str2
0x1400097e7  mov     rcx, rsi; Str1
0x1400097ea  call    strncmp_0
0x1400097ef  test    eax, eax
0x1400097f1  jmp     short loc_1400097F5
0x1400097f3  test    edi, edi
0x1400097f5  jz      short loc_14000982F
0x1400097f7  lea     r8, aMinioNetbtSysH_0; "minio\\netbt\\sys\\hashtbl.c"
0x1400097fe  mov     rbx, rbp
0x140009801  cmp     rbp, r14
0x140009804  jnz     loc_1400096A0
0x14000980a  mov     eax, 0C0000001h
0x14000980f  mov     rbp, [rsp+78h+arg_8]
0x140009817  add     rsp, 40h
0x14000981b  pop     r15
0x14000981d  pop     r14
0x14000981f  pop     r13
0x140009821  pop     r12
0x140009823  pop     rdi
0x140009824  pop     rsi
0x140009825  pop     rbx
0x140009826  retn
0x140009828  mov     ecx, 3
0x14000982d  int     29h; Win8: RtlFailFast(ecx)
0x14000982f  mov     rax, [rsp+78h+arg_18]
0x140009837  mov     [rax], rbx
0x14000983a  xor     eax, eax
0x14000983c  jmp     short loc_14000980F
```
