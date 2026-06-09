# g_verify_token_header(gss_OID_desc_struct *,int *,uchar * *,int,int)

- ea: `0x1400085dc`
- end: `0x1400086da`
- name: `?g_verify_token_header@@YAHPEAUgss_OID_desc_struct@@PEAHPEAPEAEHH@Z`
- size: `254`
- prototype: `int(struct gss_OID_desc_struct *, int *, unsigned __int8 **, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140025504`

## callees

- `0x140008448`
- `0x1400085dc`
- `0x140010ae0`

## pseudocode

```c
__int64 __fastcall g_verify_token_header(const void **a1, int *a2, unsigned __int8 **a3, __int16 a4, int a5)
{
  char v10; // r10
  int v11; // edx
  int v12; // eax
  unsigned __int8 *v13; // rdi
  bool v14; // zf
  unsigned __int8 *v15; // rcx
  int v16; // esi
  __int64 v17; // rax
  int v18; // esi
  __int64 v19; // rbp
  unsigned __int8 *v20; // r14
  int v21; // esi
  unsigned __int8 *v22; // r8

  if ( --a5 < 0 )
    return 0;
  v10 = *(*a3)++;
  if ( v10 != 96 )
    return 0;
  v11 = der_read_length(a3, &a5);
  if ( v11 < 0 )
    return 0;
  v12 = a5;
  if ( v11 != a5 )
    return 0;
  if ( a5 - 1 < 0 )
    return 0;
  v13 = *a3;
  v14 = **a3 == 6;
  v15 = *a3 + 1;
  *a3 = v15;
  if ( !v14 )
    return 0;
  v16 = v12 - 2;
  if ( v12 - 2 < 0 )
    return 0;
  v17 = *v15;
  v18 = v16 - v17;
  *a3 = v13 + 2;
  if ( v18 < 0 )
    return 0;
  v19 = (unsigned int)v17;
  v20 = &v13[v17 + 2];
  *a3 = v20;
  if ( (_DWORD)v17 != *(_DWORD *)a1 )
    return 0;
  if ( memcmp(v13 + 2, a1[1], (unsigned int)v17) )
    return 0;
  v21 = v18 - 2;
  if ( v21 < 0 )
    return 0;
  v22 = &v13[v19 + 3];
  *a3 = v22;
  if ( *v20 != HIBYTE(a4) )
    return 0;
  *a3 = &v13[v19 + 4];
  if ( *v22 != (_BYTE)a4 )
    return 0;
  *a2 = v21;
  return 1;
}

```

## disassembly

```asm
0x1400085dc  mov     r11, rsp
0x1400085df  push    rbx
0x1400085e0  push    rbp
0x1400085e1  push    rsi
0x1400085e2  push    rdi
0x1400085e3  push    r12
0x1400085e5  push    r13
0x1400085e7  push    r14
0x1400085e9  push    r15
0x1400085eb  sub     rsp, 38h
0x1400085ef  sub     [rsp+78h+arg_20], 1
0x1400085f7  mov     r15d, r9d
0x1400085fa  mov     rbx, r8
0x1400085fd  mov     r12, rdx
0x140008600  mov     r13, rcx
0x140008603  js      loc_1400086C6
0x140008609  mov     rax, [r8]
0x14000860c  mov     r10b, [rax]
0x14000860f  inc     rax
0x140008612  mov     [r8], rax
0x140008615  cmp     r10b, 60h ; '`'
0x140008619  jnz     loc_1400086C6
0x14000861f  lea     rdx, [r11+28h]; int *
0x140008623  mov     rcx, rbx; unsigned __int8 **
0x140008626  call    ?der_read_length@@YAHPEAPEAEPEAH@Z; der_read_length(uchar * *,int *)
0x14000862b  mov     edx, eax
0x14000862d  test    eax, eax
0x14000862f  js      loc_1400086C6
0x140008635  mov     eax, [rsp+78h+arg_20]
0x14000863c  cmp     edx, eax
0x14000863e  jnz     loc_1400086C6
0x140008644  lea     esi, [rax-1]
0x140008647  test    esi, esi
0x140008649  js      short loc_1400086C6
0x14000864b  mov     rdi, [rbx]
0x14000864e  cmp     byte ptr [rdi], 6
0x140008651  lea     rcx, [rdi+1]
0x140008655  mov     [rbx], rcx
0x140008658  jnz     short loc_1400086C6
0x14000865a  sub     esi, 1
0x14000865d  js      short loc_1400086C6
0x14000865f  movzx   eax, byte ptr [rcx]
0x140008662  lea     r9, [rdi+2]
0x140008666  sub     esi, eax
0x140008668  mov     [rbx], r9
0x14000866b  js      short loc_1400086C6
0x14000866d  lea     r14, [rdi+2]
0x140008671  mov     ebp, eax
0x140008673  add     r14, rax
0x140008676  mov     [rbx], r14
0x140008679  cmp     eax, [r13+0]
0x14000867d  jnz     short loc_1400086C6
0x14000867f  mov     rdx, [r13+8]; Buf2
0x140008683  mov     r8d, eax; Size
0x140008686  mov     rcx, r9; Buf1
0x140008689  call    memcmp
0x14000868e  test    eax, eax
0x140008690  jnz     short loc_1400086C6
0x140008692  add     esi, 0FFFFFFFEh
0x140008695  js      short loc_1400086C6
0x140008697  mov     edx, r15d
0x14000869a  lea     r8, [rdi+3]
0x14000869e  add     r8, rbp
0x1400086a1  sar     edx, 8
0x1400086a4  mov     [rbx], r8
0x1400086a7  cmp     [r14], dl
0x1400086aa  jnz     short loc_1400086C6
0x1400086ac  lea     rcx, [rdi+4]
0x1400086b0  add     rcx, rbp
0x1400086b3  mov     [rbx], rcx
0x1400086b6  cmp     [r8], r15b
0x1400086b9  jnz     short loc_1400086C6
0x1400086bb  mov     [r12], esi
0x1400086bf  mov     eax, 1
0x1400086c4  jmp     short loc_1400086C8
0x1400086c6  xor     eax, eax
0x1400086c8  add     rsp, 38h
0x1400086cc  pop     r15
0x1400086ce  pop     r14
0x1400086d0  pop     r13
0x1400086d2  pop     r12
0x1400086d4  pop     rdi
0x1400086d5  pop     rsi
0x1400086d6  pop     rbp
0x1400086d7  pop     rbx
0x1400086d8  retn
```
