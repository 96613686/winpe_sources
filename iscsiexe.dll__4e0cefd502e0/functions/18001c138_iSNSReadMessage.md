# iSNSReadMessage

- ea: `0x18001c138`
- end: `0x18001c497`
- name: `iSNSReadMessage`
- size: `863`
- prototype: `__int64 __fastcall(SOCKET s, __int64, __int64, _DWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d090`
- `0x18001c4a0`

## callees

- `0x180001410`
- `0x18001be94`
- `0x18001c138`
- `0x18001d38c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c285`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c302`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c438`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c45a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c463`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c285`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c302`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c438`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c45a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c463`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001c1f4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001c2a7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001c39a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001c1f4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001c2a7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001c39a`

## pseudocode

```c
__int64 __fastcall iSNSReadMessage(SOCKET s, __int64 a2, __int64 a3, _DWORD *a4)
{
  SOCKET v4; // rax
  void **v5; // rsi
  void **v6; // rbx
  void *Block[2]; // [rsp+28h] [rbp-38h] BYREF
  SOCKET sa; // [rsp+38h] [rbp-28h]
  _DWORD *v10; // [rsp+40h] [rbp-20h]
  char buf[8]; // [rsp+48h] [rbp-18h] BYREF
  int v12; // [rsp+50h] [rbp-10h]

  sa = s;
  v4 = s;
  v10 = a4;
  *a4 = 0;
  Block[1] = Block;
  Block[0] = Block;
  *(_QWORD *)buf = 0;
  v12 = 0;
  while ( !(unsigned int)ReadFromSocket(v4, buf, 12) )
    v4 = sa;
  v5 = (void **)Block[0];
  if ( Block[0] )
  {
    do
    {
      if ( v5 == Block )
        break;
      v6 = (void **)*v5;
      free(v5[2]);
      free(v5);
      v5 = v6;
    }
    while ( v6 );
  }
  return 1;
}

```

## disassembly

```asm
0x18001c138  mov     [rsp-38h+arg_8], rbx
0x18001c13d  push    rbp
0x18001c13e  push    rsi
0x18001c13f  push    rdi
0x18001c140  push    r12
0x18001c142  push    r13
0x18001c144  push    r14
0x18001c146  push    r15
0x18001c148  mov     rbp, rsp
0x18001c14b  sub     rsp, 60h
0x18001c14f  mov     rax, cs:__security_cookie
0x18001c156  xor     rax, rsp
0x18001c159  mov     [rbp+var_8], rax
0x18001c15d  xor     r11d, r11d
0x18001c160  mov     [rbp+s], rcx
0x18001c164  mov     rax, rcx
0x18001c167  mov     [rbp+var_20], r9
0x18001c16b  lea     rcx, [rbp+Block]
0x18001c16f  mov     [r9], r11d
0x18001c172  mov     [rbp+var_30], rcx
0x18001c176  mov     r13, r9
0x18001c179  lea     rcx, [rbp+Block]
0x18001c17d  mov     r12, r8
0x18001c180  mov     [rbp+Block], rcx
0x18001c184  lea     edi, [r11+1]
0x18001c188  mov     r14d, r11d
0x18001c18b  xor     ecx, ecx
0x18001c18d  mov     [rbp+var_40], r11d
0x18001c191  mov     r15d, 0Ch
0x18001c197  mov     qword ptr [rbp+buf], rcx
0x18001c19b  mov     [rbp+var_10], ecx
0x18001c19e  lea     rbx, [rbp+buf]
0x18001c1a2  mov     esi, r15d
0x18001c1a5  lea     r9, [rbp+var_40]
0x18001c1a9  mov     r8d, esi; len
0x18001c1ac  mov     rdx, rbx; buf
0x18001c1af  mov     rcx, rax; s
0x18001c1b2  call    ReadFromSocket
0x18001c1b7  test    eax, eax
0x18001c1b9  jnz     loc_18001C441
0x18001c1bf  mov     eax, [rbp+var_40]
0x18001c1c2  add     rbx, rax
0x18001c1c5  mov     rax, [rbp+s]
0x18001c1c9  sub     esi, [rbp+var_40]
0x18001c1cc  jnz     short loc_18001C1A5
0x18001c1ce  mov     eax, 100h
0x18001c1d3  cmp     word ptr [rbp+buf], ax
0x18001c1d7  jnz     loc_18001C441
0x18001c1dd  movzx   eax, word ptr [rbp+buf+4]
0x18001c1e1  mov     esi, eax
0x18001c1e3  shl     ax, 8
0x18001c1e7  movzx   eax, ax
0x18001c1ea  shr     esi, 8
0x18001c1ed  or      esi, eax
0x18001c1ef  mov     ecx, esi
0x18001c1f1  add     rcx, r15; Size
0x18001c1f4  call    cs:__imp_malloc
0x18001c1fa  xor     r11d, r11d
0x18001c1fd  mov     rbx, rax
0x18001c200  test    rax, rax
0x18001c203  jz      loc_18001C441
0x18001c209  movsd   xmm0, qword ptr [rbp+buf]
0x18001c20e  lea     r15, [rax+0Ch]
0x18001c212  movsd   qword ptr [rax], xmm0
0x18001c216  mov     ecx, [rbp+var_10]
0x18001c219  mov     [rax+8], ecx
0x18001c21c  test    esi, esi
0x18001c21e  jz      short loc_18001C249
0x18001c220  mov     rcx, [rbp+s]; s
0x18001c224  lea     r9, [rbp+var_40]
0x18001c228  mov     r8d, esi; len
0x18001c22b  mov     rdx, r15; buf
0x18001c22e  call    ReadFromSocket
0x18001c233  xor     r11d, r11d
0x18001c236  test    eax, eax
0x18001c238  jnz     loc_18001C2FF
0x18001c23e  mov     eax, [rbp+var_40]
0x18001c241  add     r15, rax
0x18001c244  sub     esi, [rbp+var_40]
0x18001c247  jnz     short loc_18001C220
0x18001c249  movzx   ecx, word ptr [rbx+0Ah]
0x18001c24d  mov     r15d, r11d
0x18001c250  movzx   eax, byte ptr [rbx+0Bh]
0x18001c254  shl     cx, 8
0x18001c258  or      cx, ax
0x18001c25b  cmp     cx, r14w
0x18001c25f  jnz     loc_18001C435
0x18001c265  movzx   esi, word ptr [rbx+6]
0x18001c269  mov     edx, 400h
0x18001c26e  shl     si, 8
0x18001c272  movzx   eax, si
0x18001c275  and     ax, dx
0x18001c278  test    cx, cx
0x18001c27b  jnz     short loc_18001C296
0x18001c27d  test    ax, ax
0x18001c280  jnz     short loc_18001C29B
0x18001c282  mov     rcx, rbx; Block
0x18001c285  call    cs:__imp_free
0x18001c28b  xor     r11d, r11d
0x18001c28e  mov     edi, r11d
0x18001c291  jmp     loc_18001C441
0x18001c296  test    ax, ax
0x18001c299  jz      short loc_18001C2A2
0x18001c29b  bt      si, 0Bh
0x18001c2a0  jb      short loc_18001C30D
0x18001c2a2  mov     ecx, 18h; Size
0x18001c2a7  call    cs:__imp_malloc
0x18001c2ad  xor     r11d, r11d
0x18001c2b0  test    rax, rax
0x18001c2b3  jz      loc_18001C435
0x18001c2b9  mov     [rax+10h], rbx
0x18001c2bd  lea     rdx, [rbp+Block]
0x18001c2c1  mov     rcx, [rbp+var_30]
0x18001c2c5  cmp     [rcx], rdx
0x18001c2c8  jnz     loc_18001C42E
0x18001c2ce  bt      si, 0Bh
0x18001c2d3  mov     [rax+8], rcx
0x18001c2d7  lea     rdx, [rbp+Block]
0x18001c2db  mov     [rax], rdx
0x18001c2de  mov     [rcx], rax
0x18001c2e1  mov     [rbp+var_30], rax
0x18001c2e5  jb      short loc_18001C330
0x18001c2e7  mov     eax, 0FFFFh
0x18001c2ec  cmp     ax, r14w
0x18001c2f0  jz      short loc_18001C28E
0x18001c2f2  mov     rax, [rbp+s]
0x18001c2f6  add     r14w, di
0x18001c2fa  jmp     loc_18001C18B
0x18001c2ff  mov     rcx, rbx; Block
0x18001c302  call    cs:__imp_free
0x18001c308  jmp     loc_18001C441
0x18001c30d  mov     [r12], rbx
0x18001c311  movzx   eax, word ptr [rbx+4]
0x18001c315  shl     ax, 8
0x18001c319  movzx   ecx, ax
0x18001c31c  movzx   eax, byte ptr [rbx+5]
0x18001c320  or      ecx, eax
0x18001c322  add     ecx, 0Ch
0x18001c325  mov     [r13+0], ecx
0x18001c329  xor     eax, eax
0x18001c32b  jmp     loc_18001C473
0x18001c330  mov     r8, [rbp+Block]
0x18001c334  mov     esi, r11d
0x18001c337  jmp     short loc_18001C385
0x18001c339  lea     rax, [rbp+Block]
0x18001c33d  cmp     r8, rax
0x18001c340  jz      short loc_18001C38A
0x18001c342  mov     rax, [r8+10h]
0x18001c346  movzx   ecx, word ptr [rax+4]
0x18001c34a  movzx   r10d, byte ptr [rax+5]
0x18001c34f  shl     cx, 8
0x18001c353  movzx   r9d, cx
0x18001c357  mov     ecx, 0FFFFFFF3h
0x18001c35c  mov     edx, r9d
0x18001c35f  mov     eax, esi
0x18001c361  or      rdx, r10
0x18001c364  sub     rcx, rax
0x18001c367  cmp     rcx, rdx
0x18001c36a  jb      loc_18001C441
0x18001c370  mov     eax, r10d
0x18001c373  or      eax, r9d
0x18001c376  add     eax, esi
0x18001c378  cmp     eax, esi
0x18001c37a  jb      loc_18001C441
0x18001c380  mov     r8, [r8]
0x18001c383  mov     esi, eax
0x18001c385  test    r8, r8
0x18001c388  jnz     short loc_18001C339
0x18001c38a  lea     r14d, [rsi+0Ch]
0x18001c38e  cmp     r14d, esi
0x18001c391  jb      loc_18001C441
0x18001c397  mov     ecx, r14d; Size
0x18001c39a  call    cs:__imp_malloc
0x18001c3a0  xor     r11d, r11d
0x18001c3a3  mov     [r12], rax
0x18001c3a7  mov     rdi, rax
0x18001c3aa  test    rax, rax
0x18001c3ad  jz      loc_18001C28E
0x18001c3b3  mov     r15, [rbp+Block]
0x18001c3b7  test    r15, r15
0x18001c3ba  jz      short loc_18001C410
0x18001c3bc  lea     r13d, [r11+0Ch]
0x18001c3c0  lea     rax, [rbp+Block]
0x18001c3c4  cmp     r15, rax
0x18001c3c7  jz      short loc_18001C40C
0x18001c3c9  mov     rdx, [r15+10h]
0x18001c3cd  movzx   ecx, word ptr [rdx+4]
0x18001c3d1  movzx   eax, byte ptr [rdx+5]
0x18001c3d5  shl     cx, 8
0x18001c3d9  or      cx, ax
0x18001c3dc  cmp     rdi, [r12]
0x18001c3e0  lea     eax, [rcx+r13]
0x18001c3e4  cmovnz  ax, cx
0x18001c3e8  mov     rcx, rdi; void *
0x18001c3eb  movzx   ebx, ax
0x18001c3ee  lea     rax, [rdx+0Ch]
0x18001c3f2  cmovnz  rdx, rax; Src
0x18001c3f6  mov     r8d, ebx; Size
0x18001c3f9  call    memcpy_0
0x18001c3fe  mov     r15, [r15]
0x18001c401  xor     r11d, r11d
0x18001c404  add     rdi, rbx
0x18001c407  test    r15, r15
0x18001c40a  jnz     short loc_18001C3C0
0x18001c40c  mov     r13, [rbp+var_20]
0x18001c410  mov     rax, [r12]
0x18001c414  ror     si, 8
0x18001c418  mov     [rax+4], si
0x18001c41c  mov     rax, [r12]
0x18001c420  or      word ptr [rax+6], 8
0x18001c425  mov     [r13+0], r14d
0x18001c429  jmp     loc_18001C28E
0x18001c42e  mov     ecx, 3
0x18001c433  int     29h; Win8: RtlFailFast(ecx)
0x18001c435  mov     rcx, rbx; Block
0x18001c438  call    cs:__imp_free
0x18001c43e  mov     edi, r15d
0x18001c441  mov     rsi, [rbp+Block]
0x18001c445  test    rsi, rsi
0x18001c448  jz      short loc_18001C471
0x18001c44a  lea     rax, [rbp+Block]
0x18001c44e  cmp     rsi, rax
0x18001c451  jz      short loc_18001C471
0x18001c453  mov     rcx, [rsi+10h]; Block
0x18001c457  mov     rbx, [rsi]
0x18001c45a  call    cs:__imp_free
0x18001c460  mov     rcx, rsi; Block
0x18001c463  call    cs:__imp_free
0x18001c469  mov     rsi, rbx
0x18001c46c  test    rbx, rbx
0x18001c46f  jnz     short loc_18001C44A
0x18001c471  mov     eax, edi
0x18001c473  mov     rcx, [rbp+var_8]
0x18001c477  xor     rcx, rsp; StackCookie
0x18001c47a  call    __security_check_cookie
0x18001c47f  mov     rbx, [rsp+60h+arg_8]
0x18001c487  add     rsp, 60h
0x18001c48b  pop     r15
0x18001c48d  pop     r14
0x18001c48f  pop     r13
0x18001c491  pop     r12
0x18001c493  pop     rdi
0x18001c494  pop     rsi
0x18001c495  pop     rbp
0x18001c496  retn
```
