# CallTransitionComplete

- ea: `0x140012138`
- end: `0x1400122cc`
- name: `CallTransitionComplete`
- size: `404`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000f008`
- `0x14000faa0`
- `0x14001083c`
- `0x1400126c8`
- `0x1400128bc`
- `0x140012b20`
- `0x140012dc4`
- `0x140012f5c`
- `0x1400130b8`

## callees

- `0x140001850`
- `0x14000351c`
- `0x140012138`
- `0x14001c860`

## pseudocode

```c
__int64 __fastcall CallTransitionComplete(__int64 a1, __int64 a2, int a3)
{
  _DWORD *v3; // rdi
  __int64 result; // rax
  int v5; // r11d
  _DWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  const char *v13; // r8
  __int64 v14; // rdx
  _QWORD *v15; // rcx
  _QWORD *v16; // rdx

  v3 = (_DWORD *)(a2 + 60);
  *(_DWORD *)(a2 + 88) = a3;
  result = *(unsigned int *)(a2 + 60);
  v5 = a3;
  if ( (result & 0xF000) == 0 )
  {
    if ( (result & 4) == 0 )
      return result;
    SetFlags(v3, 0x4000);
LABEL_10:
    v9 = 4;
    goto LABEL_11;
  }
  if ( (result & 0x2000) == 0 )
  {
    if ( (result & 0x1000) == 0 || !*(_DWORD *)(a2 + 128) )
      goto LABEL_12;
    v8 = (_DWORD *)(a2 + 60);
    goto LABEL_10;
  }
  if ( *(_DWORD *)(a2 + 128) )
  {
    v9 = 6;
    v8 = v3;
LABEL_11:
    ClearFlags(v8, v9);
  }
LABEL_12:
  v10 = MEMORY[0xFFFFF78000000014];
  if ( *(_DWORD *)(a2 + 88) )
  {
    v12 = *(_DWORD *)(a2 + 248);
    *(_DWORD *)(a2 + 416) = v12;
    *(_DWORD *)(a2 + 420) = v12;
    *(_QWORD *)(a2 + 344) = v10;
  }
  else
  {
    v11 = *(_QWORD *)(a2 + 344);
    if ( v11 )
      *(_DWORD *)(a2 + 352) = (MEMORY[0xFFFFF78000000014] - v11) / 0x989680uLL;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v13 = "UP";
    if ( v5 != 6 )
      v13 = "DOWN";
    WPP_SF_qdqds(
      WPP_GLOBAL_Control->AttachedDevice,
      *(unsigned __int16 *)(a2 + 56),
      (_DWORD)v13,
      a2,
      *(_WORD *)(a2 + 56),
      a1,
      *(_WORD *)(a1 + 114),
      (__int64)v13);
  }
  result = a2 + 96;
  v14 = *(_QWORD *)(a2 + 96);
  if ( *(_QWORD *)(v14 + 8) != a2 + 96 )
    goto LABEL_28;
  v15 = *(_QWORD **)(a2 + 104);
  if ( *v15 != result )
    goto LABEL_28;
  *v15 = v14;
  *(_QWORD *)(v14 + 8) = v15;
  *(_QWORD *)(a2 + 104) = a2 + 96;
  *(_QWORD *)result = result;
  if ( (*v3 & 0x1000000) != 0 )
    return result;
  SetFlags(v3, 0x1000000);
  v16 = *(_QWORD **)(a1 + 152);
  if ( *v16 != a1 + 144 )
LABEL_28:
    __fastfail(3u);
  result = a2 + 112;
  *(_QWORD *)(a2 + 112) = a1 + 144;
  *(_QWORD *)(a2 + 120) = v16;
  *v16 = a2 + 112;
  *(_QWORD *)(a1 + 152) = a2 + 112;
  return result;
}

```

## disassembly

```asm
0x140012138  mov     [rsp+arg_0], rbx
0x14001213d  mov     [rsp+arg_8], rsi
0x140012142  push    rdi
0x140012143  sub     rsp, 40h
0x140012147  lea     rdi, [rdx+3Ch]
0x14001214b  mov     [rdx+58h], r8d
0x14001214f  mov     eax, [rdi]
0x140012151  mov     r11d, r8d
0x140012154  mov     rbx, rdx
0x140012157  mov     rsi, rcx
0x14001215a  test    eax, 0F000h
0x14001215f  jnz     short loc_140012178
0x140012161  test    al, 4
0x140012163  jz      loc_1400122B4
0x140012169  mov     edx, 4000h
0x14001216e  mov     rcx, rdi
0x140012171  call    SetFlags
0x140012176  jmp     short loc_1400121A3
0x140012178  bt      eax, 0Dh
0x14001217c  jnb     short loc_140012191
0x14001217e  cmp     dword ptr [rdx+80h], 0
0x140012185  jz      short loc_1400121AD
0x140012187  mov     edx, 6
0x14001218c  mov     rcx, rdi
0x14001218f  jmp     short loc_1400121A8
0x140012191  bt      eax, 0Ch
0x140012195  jnb     short loc_1400121AD
0x140012197  cmp     dword ptr [rdx+80h], 0
0x14001219e  jz      short loc_1400121AD
0x1400121a0  mov     rcx, rdi
0x1400121a3  mov     edx, 4
0x1400121a8  call    ClearFlags
0x1400121ad  mov     rcx, 0FFFFF78000000014h
0x1400121b7  mov     rcx, [rcx]
0x1400121ba  cmp     dword ptr [rbx+58h], 0
0x1400121be  jnz     short loc_1400121E8
0x1400121c0  mov     rax, [rbx+158h]
0x1400121c7  test    rax, rax
0x1400121ca  jz      short loc_140012201
0x1400121cc  sub     rcx, rax
0x1400121cf  mov     rax, 0D6BF94D5E57A42BDh
0x1400121d9  mul     rcx
0x1400121dc  shr     rdx, 17h
0x1400121e0  mov     [rbx+160h], edx
0x1400121e6  jmp     short loc_140012201
0x1400121e8  mov     eax, [rbx+0F8h]
0x1400121ee  mov     [rbx+1A0h], eax
0x1400121f4  mov     [rbx+1A4h], eax
0x1400121fa  mov     [rbx+158h], rcx
0x140012201  mov     rcx, cs:WPP_GLOBAL_Control
0x140012208  lea     rax, WPP_GLOBAL_Control
0x14001220f  cmp     rcx, rax
0x140012212  jz      short loc_14001225D
0x140012214  mov     eax, [rcx+2Ch]
0x140012217  test    al, 8
0x140012219  jz      short loc_14001225D
0x14001221b  cmp     byte ptr [rcx+29h], 2
0x14001221f  jb      short loc_14001225D
0x140012221  movzx   edx, word ptr [rbx+38h]
0x140012225  lea     rax, aDown; "DOWN"
0x14001222c  mov     rcx, [rcx+18h]
0x140012230  lea     r8, aUp; "UP"
0x140012237  cmp     r11d, 6
0x14001223b  mov     r9, rbx
0x14001223e  cmovnz  r8, rax
0x140012242  movzx   eax, word ptr [rsi+72h]
0x140012246  mov     [rsp+48h+var_10], r8
0x14001224b  mov     [rsp+48h+var_18], eax
0x14001224f  mov     [rsp+48h+var_20], rsi
0x140012254  mov     [rsp+48h+var_28], edx
0x140012258  call    WPP_SF_qdqds
0x14001225d  lea     rax, [rbx+60h]
0x140012261  mov     rdx, [rax]
0x140012264  cmp     [rdx+8], rax
0x140012268  jnz     short loc_1400122C5
0x14001226a  mov     rcx, [rax+8]
0x14001226e  cmp     [rcx], rax
0x140012271  jnz     short loc_1400122C5
0x140012273  mov     [rcx], rdx
0x140012276  mov     [rdx+8], rcx
0x14001227a  mov     edx, 1000000h
0x14001227f  mov     [rax+8], rax
0x140012283  mov     [rax], rax
0x140012286  test    [rdi], edx
0x140012288  jnz     short loc_1400122B4
0x14001228a  mov     rcx, rdi
0x14001228d  call    SetFlags
0x140012292  lea     rcx, [rsi+90h]
0x140012299  mov     rdx, [rcx+8]
0x14001229d  cmp     [rdx], rcx
0x1400122a0  jnz     short loc_1400122C5
0x1400122a2  lea     rax, [rbx+70h]
0x1400122a6  mov     [rax], rcx
0x1400122a9  mov     [rax+8], rdx
0x1400122ad  mov     [rdx], rax
0x1400122b0  mov     [rcx+8], rax
0x1400122b4  mov     rbx, [rsp+48h+arg_0]
0x1400122b9  mov     rsi, [rsp+48h+arg_8]
0x1400122be  add     rsp, 40h
0x1400122c2  pop     rdi
0x1400122c3  retn
0x1400122c5  mov     ecx, 3
0x1400122ca  int     29h; Win8: RtlFailFast(ecx)
```
