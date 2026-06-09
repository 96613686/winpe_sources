# GenFilterAMD64Context(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,void *,ulong,uchar)

- ea: `0x1800198b4`
- end: `0x180019c1d`
- name: `?GenFilterAMD64Context@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@PEAXKE@Z`
- size: `873`
- prototype: `__int64 __usercall@<rax>(struct _MINIDUMP_STATE *@<rcx>, struct _INTERNAL_PROCESS *@<rdx>, struct _INTERNAL_THREAD *@<r8>, void *@<r9>, unsigned int, unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180019e3c`

## callees

- `0x1800021f4`
- `0x180016930`
- `0x1800198b4`

## pseudocode

```c
__int64 __fastcall GenFilterAMD64Context(
        struct _MINIDUMP_STATE *a1,
        struct _INTERNAL_PROCESS *a2,
        struct _INTERNAL_THREAD *a3,
        unsigned __int64 *a4,
        unsigned int a5,
        unsigned __int8 a6)
{
  unsigned int v10; // r14d
  unsigned __int64 v11; // r9
  unsigned __int64 v12; // r9
  unsigned __int64 v13; // r9
  unsigned __int64 v14; // r9
  unsigned __int64 v15; // r9
  unsigned __int64 v16; // r9
  unsigned __int64 v17; // r9
  unsigned __int64 v18; // r9
  unsigned __int64 v19; // r9
  unsigned __int64 v20; // r9
  unsigned __int64 v21; // r9
  unsigned __int64 v22; // r9
  unsigned __int64 v23; // r9
  unsigned __int64 v24; // r9
  unsigned __int64 v25; // r9
  unsigned __int64 v26; // r9
  unsigned __int64 v27; // r9
  unsigned __int64 v28; // r9
  unsigned __int64 v29; // r9
  unsigned __int64 v30; // r9
  int v32; // [rsp+20h] [rbp-48h]

  if ( a5 >= 0x4D0 )
  {
    v10 = 0;
    memset_0(a4 + 32, 170, 0x200u);
    memset_0(a4 + 96, 170, 0x1A0u);
    if ( !a6 )
    {
      v11 = a4[20];
      if ( v11 && !AddressReferenced(a1, a2, a3, v11, v32) )
        a4[20] = 0xAAAAAAAAAAAAAAAAuLL;
      if ( *a4 && !AddressReferenced(a1, a2, a3, *a4, v32) )
        *a4 = 0xAAAAAAAAAAAAAAAAuLL;
      v12 = a4[1];
      if ( v12 && !AddressReferenced(a1, a2, a3, v12, v32) )
        a4[1] = 0xAAAAAAAAAAAAAAAAuLL;
      v13 = a4[2];
      if ( v13 && !AddressReferenced(a1, a2, a3, v13, v32) )
        a4[2] = 0xAAAAAAAAAAAAAAAAuLL;
      v14 = a4[3];
      if ( v14 && !AddressReferenced(a1, a2, a3, v14, v32) )
        a4[3] = 0xAAAAAAAAAAAAAAAAuLL;
      v15 = a4[4];
      if ( v15 && !AddressReferenced(a1, a2, a3, v15, v32) )
        a4[4] = 0xAAAAAAAAAAAAAAAAuLL;
      v16 = a4[5];
      if ( v16 && !AddressReferenced(a1, a2, a3, v16, v32) )
        a4[5] = 0xAAAAAAAAAAAAAAAAuLL;
      v17 = a4[15];
      if ( v17 && !AddressReferenced(a1, a2, a3, v17, v32) )
        a4[15] = 0xAAAAAAAAAAAAAAAAuLL;
      v18 = a4[18];
      if ( v18 && !AddressReferenced(a1, a2, a3, v18, v32) )
        a4[18] = 0xAAAAAAAAAAAAAAAAuLL;
      v19 = a4[16];
      if ( v19 && !AddressReferenced(a1, a2, a3, v19, v32) )
        a4[16] = 0xAAAAAAAAAAAAAAAAuLL;
      v20 = a4[17];
      if ( v20 && !AddressReferenced(a1, a2, a3, v20, v32) )
        a4[17] = 0xAAAAAAAAAAAAAAAAuLL;
      v21 = a4[21];
      if ( v21 && !AddressReferenced(a1, a2, a3, v21, v32) )
        a4[21] = 0xAAAAAAAAAAAAAAAAuLL;
      v22 = a4[22];
      if ( v22 && !AddressReferenced(a1, a2, a3, v22, v32) )
        a4[22] = 0xAAAAAAAAAAAAAAAAuLL;
      v23 = a4[23];
      if ( v23 && !AddressReferenced(a1, a2, a3, v23, v32) )
        a4[23] = 0xAAAAAAAAAAAAAAAAuLL;
      v24 = a4[24];
      if ( v24 && !AddressReferenced(a1, a2, a3, v24, v32) )
        a4[24] = 0xAAAAAAAAAAAAAAAAuLL;
      v25 = a4[25];
      if ( v25 && !AddressReferenced(a1, a2, a3, v25, v32) )
        a4[25] = 0xAAAAAAAAAAAAAAAAuLL;
      v26 = a4[26];
      if ( v26 && !AddressReferenced(a1, a2, a3, v26, v32) )
        a4[26] = 0xAAAAAAAAAAAAAAAAuLL;
      v27 = a4[27];
      if ( v27 && !AddressReferenced(a1, a2, a3, v27, v32) )
        a4[27] = 0xAAAAAAAAAAAAAAAAuLL;
      v28 = a4[28];
      if ( v28 && !AddressReferenced(a1, a2, a3, v28, v32) )
        a4[28] = 0xAAAAAAAAAAAAAAAAuLL;
      v29 = a4[29];
      if ( v29 && !AddressReferenced(a1, a2, a3, v29, v32) )
        a4[29] = 0xAAAAAAAAAAAAAAAAuLL;
      v30 = a4[30];
      if ( v30 && !AddressReferenced(a1, a2, a3, v30, v32) )
        a4[30] = 0xAAAAAAAAAAAAAAAAuLL;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v10;
}

```

## disassembly

```asm
0x1800198b4  push    rbx
0x1800198b6  push    rbp
0x1800198b7  push    rsi
0x1800198b8  push    rdi
0x1800198b9  push    r14
0x1800198bb  push    r15
0x1800198bd  sub     rsp, 38h
0x1800198c1  cmp     [rsp+68h+arg_20], 4D0h
0x1800198cc  mov     rbx, r9
0x1800198cf  mov     rdi, r8
0x1800198d2  mov     rsi, rdx
0x1800198d5  mov     rbp, rcx
0x1800198d8  jnb     short loc_1800198E5
0x1800198da  mov     r14d, 80070057h
0x1800198e0  jmp     loc_180019C0D
0x1800198e5  mov     r15d, 0AAh
0x1800198eb  lea     rcx, [r9+100h]; void *
0x1800198f2  mov     edx, r15d; Val
0x1800198f5  mov     r8d, 200h; Size
0x1800198fb  xor     r14d, r14d
0x1800198fe  call    memset_0
0x180019903  lea     rcx, [rbx+300h]; void *
0x18001990a  mov     r8d, 1A0h; Size
0x180019910  mov     edx, r15d; Val
0x180019913  call    memset_0
0x180019918  cmp     [rsp+68h+arg_28], r14b
0x180019920  jnz     loc_180019C0D
0x180019926  mov     r9, [rbx+0A0h]; unsigned __int64
0x18001992d  mov     r15, 0AAAAAAAAAAAAAAAAh
0x180019937  test    r9, r9
0x18001993a  jz      short loc_180019955
0x18001993c  mov     r8, rdi; struct _INTERNAL_THREAD *
0x18001993f  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019942  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019945  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x18001994a  test    al, al
0x18001994c  jnz     short loc_180019955
0x18001994e  mov     [rbx+0A0h], r15
0x180019955  mov     r9, [rbx]; unsigned __int64
0x180019958  test    r9, r9
0x18001995b  jz      short loc_180019972
0x18001995d  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019960  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019963  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019966  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x18001996b  test    al, al
0x18001996d  jnz     short loc_180019972
0x18001996f  mov     [rbx], r15
0x180019972  mov     r9, [rbx+8]; unsigned __int64
0x180019976  test    r9, r9
0x180019979  jz      short loc_180019991
0x18001997b  mov     r8, rdi; struct _INTERNAL_THREAD *
0x18001997e  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019981  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019984  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019989  test    al, al
0x18001998b  jnz     short loc_180019991
0x18001998d  mov     [rbx+8], r15
0x180019991  mov     r9, [rbx+10h]; unsigned __int64
0x180019995  test    r9, r9
0x180019998  jz      short loc_1800199B0
0x18001999a  mov     r8, rdi; struct _INTERNAL_THREAD *
0x18001999d  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x1800199a0  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x1800199a3  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x1800199a8  test    al, al
0x1800199aa  jnz     short loc_1800199B0
0x1800199ac  mov     [rbx+10h], r15
0x1800199b0  mov     r9, [rbx+18h]; unsigned __int64
0x1800199b4  test    r9, r9
0x1800199b7  jz      short loc_1800199CF
0x1800199b9  mov     r8, rdi; struct _INTERNAL_THREAD *
0x1800199bc  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x1800199bf  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x1800199c2  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x1800199c7  test    al, al
0x1800199c9  jnz     short loc_1800199CF
0x1800199cb  mov     [rbx+18h], r15
0x1800199cf  mov     r9, [rbx+20h]; unsigned __int64
0x1800199d3  test    r9, r9
0x1800199d6  jz      short loc_1800199EE
0x1800199d8  mov     r8, rdi; struct _INTERNAL_THREAD *
0x1800199db  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x1800199de  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x1800199e1  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x1800199e6  test    al, al
0x1800199e8  jnz     short loc_1800199EE
0x1800199ea  mov     [rbx+20h], r15
0x1800199ee  mov     r9, [rbx+28h]; unsigned __int64
0x1800199f2  test    r9, r9
0x1800199f5  jz      short loc_180019A0D
0x1800199f7  mov     r8, rdi; struct _INTERNAL_THREAD *
0x1800199fa  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x1800199fd  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019a00  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019a05  test    al, al
0x180019a07  jnz     short loc_180019A0D
0x180019a09  mov     [rbx+28h], r15
0x180019a0d  mov     r9, [rbx+78h]; unsigned __int64
0x180019a11  test    r9, r9
0x180019a14  jz      short loc_180019A2C
0x180019a16  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019a19  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019a1c  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019a1f  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019a24  test    al, al
0x180019a26  jnz     short loc_180019A2C
0x180019a28  mov     [rbx+78h], r15
0x180019a2c  mov     r9, [rbx+90h]; unsigned __int64
0x180019a33  test    r9, r9
0x180019a36  jz      short loc_180019A51
0x180019a38  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019a3b  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019a3e  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019a41  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019a46  test    al, al
0x180019a48  jnz     short loc_180019A51
0x180019a4a  mov     [rbx+90h], r15
0x180019a51  mov     r9, [rbx+80h]; unsigned __int64
0x180019a58  test    r9, r9
0x180019a5b  jz      short loc_180019A76
0x180019a5d  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019a60  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019a63  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019a66  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019a6b  test    al, al
0x180019a6d  jnz     short loc_180019A76
0x180019a6f  mov     [rbx+80h], r15
0x180019a76  mov     r9, [rbx+88h]; unsigned __int64
0x180019a7d  test    r9, r9
0x180019a80  jz      short loc_180019A9B
0x180019a82  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019a85  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019a88  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019a8b  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019a90  test    al, al
0x180019a92  jnz     short loc_180019A9B
0x180019a94  mov     [rbx+88h], r15
0x180019a9b  mov     r9, [rbx+0A8h]; unsigned __int64
0x180019aa2  test    r9, r9
0x180019aa5  jz      short loc_180019AC0
0x180019aa7  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019aaa  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019aad  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019ab0  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019ab5  test    al, al
0x180019ab7  jnz     short loc_180019AC0
0x180019ab9  mov     [rbx+0A8h], r15
0x180019ac0  mov     r9, [rbx+0B0h]; unsigned __int64
0x180019ac7  test    r9, r9
0x180019aca  jz      short loc_180019AE5
0x180019acc  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019acf  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019ad2  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019ad5  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019ada  test    al, al
0x180019adc  jnz     short loc_180019AE5
0x180019ade  mov     [rbx+0B0h], r15
0x180019ae5  mov     r9, [rbx+0B8h]; unsigned __int64
0x180019aec  test    r9, r9
0x180019aef  jz      short loc_180019B0A
0x180019af1  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019af4  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019af7  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019afa  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019aff  test    al, al
0x180019b01  jnz     short loc_180019B0A
0x180019b03  mov     [rbx+0B8h], r15
0x180019b0a  mov     r9, [rbx+0C0h]; unsigned __int64
0x180019b11  test    r9, r9
0x180019b14  jz      short loc_180019B2F
0x180019b16  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019b19  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019b1c  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019b1f  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019b24  test    al, al
0x180019b26  jnz     short loc_180019B2F
0x180019b28  mov     [rbx+0C0h], r15
0x180019b2f  mov     r9, [rbx+0C8h]; unsigned __int64
0x180019b36  test    r9, r9
0x180019b39  jz      short loc_180019B54
0x180019b3b  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019b3e  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019b41  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019b44  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019b49  test    al, al
0x180019b4b  jnz     short loc_180019B54
0x180019b4d  mov     [rbx+0C8h], r15
0x180019b54  mov     r9, [rbx+0D0h]; unsigned __int64
0x180019b5b  test    r9, r9
0x180019b5e  jz      short loc_180019B79
0x180019b60  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019b63  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019b66  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019b69  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019b6e  test    al, al
0x180019b70  jnz     short loc_180019B79
0x180019b72  mov     [rbx+0D0h], r15
0x180019b79  mov     r9, [rbx+0D8h]; unsigned __int64
0x180019b80  test    r9, r9
0x180019b83  jz      short loc_180019B9E
0x180019b85  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019b88  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019b8b  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019b8e  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019b93  test    al, al
0x180019b95  jnz     short loc_180019B9E
0x180019b97  mov     [rbx+0D8h], r15
0x180019b9e  mov     r9, [rbx+0E0h]; unsigned __int64
0x180019ba5  test    r9, r9
0x180019ba8  jz      short loc_180019BC3
0x180019baa  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019bad  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019bb0  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019bb3  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019bb8  test    al, al
0x180019bba  jnz     short loc_180019BC3
0x180019bbc  mov     [rbx+0E0h], r15
0x180019bc3  mov     r9, [rbx+0E8h]; unsigned __int64
0x180019bca  test    r9, r9
0x180019bcd  jz      short loc_180019BE8
0x180019bcf  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019bd2  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019bd5  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019bd8  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019bdd  test    al, al
0x180019bdf  jnz     short loc_180019BE8
0x180019be1  mov     [rbx+0E8h], r15
0x180019be8  mov     r9, [rbx+0F0h]; unsigned __int64
0x180019bef  test    r9, r9
0x180019bf2  jz      short loc_180019C0D
0x180019bf4  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019bf7  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019bfa  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019bfd  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019c02  test    al, al
0x180019c04  jnz     short loc_180019C0D
0x180019c06  mov     [rbx+0F0h], r15
0x180019c0d  mov     eax, r14d
0x180019c10  add     rsp, 38h
0x180019c14  pop     r15
0x180019c16  pop     r14
0x180019c18  pop     rdi
0x180019c19  pop     rsi
0x180019c1a  pop     rbp
0x180019c1b  pop     rbx
0x180019c1c  retn
```
