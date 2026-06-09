# CCabFolder::CreateIDList(ushort const *,ulong,uint,uint,uint)

- ea: `0x18000dc64`
- end: `0x18000dd61`
- name: `?CreateIDList@CCabFolder@@SAPEFAU_ITEMIDLIST@@PEBGKIII@Z`
- size: `253`
- prototype: `struct _ITEMIDLIST *__usercall@<rax>(const unsigned __int16 *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d364`

## callees

- `0x180002620`
- `0x180008c48`
- `0x18000dc64`

## import_xrefs

- `SHELL32!__imp_ILClone` at `0x18000dd36`
- `SHELL32!__imp_ILClone` at `0x18000dd36`

## pseudocode

```c
LPITEMIDLIST __fastcall CCabFolder::CreateIDList(size_t *a1, int a2, __int16 a3, __int16 a4, char a5)
{
  unsigned __int64 v5; // rbx
  unsigned __int16 v7; // cx
  unsigned __int64 v8; // rax
  __int64 v9; // rdx
  ITEMIDLIST pidl; // [rsp+20h] [rbp-238h] BYREF
  int v12; // [rsp+24h] [rbp-234h]
  __int16 v13; // [rsp+28h] [rbp-230h]
  __int16 v14; // [rsp+2Ah] [rbp-22Eh]
  __int16 v15; // [rsp+2Ch] [rbp-22Ch]
  __int16 v16; // [rsp+2Eh] [rbp-22Ah]
  unsigned __int16 v17[264]; // [rsp+30h] [rbp-228h] BYREF

  v5 = -1;
  do
    ++v5;
  while ( *((_WORD *)a1 + v5) );
  v12 = a2;
  v13 = a3;
  v14 = a4;
  if ( v5 >= 0x104 )
    v5 = 260;
  pidl.mkid.cb = 2 * (v5 + 10);
  v15 = a5 & 0x27;
  StringCchCopyW(v17, 0x104u, a1);
  v7 = 0;
  v16 = 0;
  if ( *(_WORD *)a1 )
  {
    do
    {
      if ( v7 >= v5 )
        break;
      v8 = *((unsigned __int16 *)a1 + v7);
      LOWORD(v8) = v8 - 47;
      if ( (unsigned __int16)v8 <= 0x2Du )
      {
        v9 = 0x200000000801LL;
        if ( _bittest64(&v9, v8) )
          v16 = v7 + 1;
      }
      ++v7;
    }
    while ( *((_WORD *)a1 + v7) );
  }
  *(USHORT *)((char *)&pidl.mkid.cb + pidl.mkid.cb) = 0;
  return ILClone(&pidl);
}

```

## disassembly

```asm
0x18000dc64  mov     [rsp+arg_8], rbx
0x18000dc69  mov     [rsp+arg_10], rsi
0x18000dc6e  push    rdi
0x18000dc6f  sub     rsp, 250h
0x18000dc76  mov     rax, cs:__security_cookie
0x18000dc7d  xor     rax, rsp
0x18000dc80  mov     [rsp+258h+var_18], rax
0x18000dc88  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000dc8c  mov     rdi, rcx
0x18000dc8f  xor     esi, esi
0x18000dc91  inc     rbx
0x18000dc94  cmp     [rcx+rbx*2], si
0x18000dc98  jnz     short loc_18000DC91
0x18000dc9a  mov     ecx, 104h
0x18000dc9f  mov     [rsp+258h+var_234], edx
0x18000dca3  cmp     rbx, rcx
0x18000dca6  mov     [rsp+258h+var_230], r8w
0x18000dcac  mov     edx, ecx; unsigned __int64
0x18000dcae  mov     [rsp+258h+var_22E], r9w
0x18000dcb4  cmovnb  rbx, rcx
0x18000dcb8  mov     r8, rdi; unsigned __int16 *
0x18000dcbb  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x18000dcc0  lea     eax, [rbx+0Ah]
0x18000dcc3  add     ax, ax
0x18000dcc6  mov     [rsp+258h+pidl.mkid.cb], ax
0x18000dccb  movzx   eax, word ptr [rsp+258h+arg_20]
0x18000dcd3  and     ax, 27h
0x18000dcd7  mov     [rsp+258h+var_22C], ax
0x18000dcdc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000dce1  mov     ecx, esi
0x18000dce3  mov     [rsp+258h+var_22A], si
0x18000dce8  cmp     [rdi], si
0x18000dceb  jz      short loc_18000DD27
0x18000dced  movzx   eax, cx
0x18000dcf0  cmp     rax, rbx
0x18000dcf3  jnb     short loc_18000DD27
0x18000dcf5  movzx   eax, word ptr [rdi+rax*2]
0x18000dcf9  sub     ax, 2Fh ; '/'
0x18000dcfd  cmp     ax, 2Dh ; '-'
0x18000dd01  ja      short loc_18000DD1B
0x18000dd03  mov     rdx, 200000000801h
0x18000dd0d  bt      rdx, rax
0x18000dd11  jnb     short loc_18000DD1B
0x18000dd13  lea     eax, [rcx+1]
0x18000dd16  mov     [rsp+258h+var_22A], ax
0x18000dd1b  inc     cx
0x18000dd1e  movzx   eax, cx
0x18000dd21  cmp     [rdi+rax*2], si
0x18000dd25  jnz     short loc_18000DCED
0x18000dd27  movzx   ecx, [rsp+258h+pidl.mkid.cb]
0x18000dd2c  mov     [rsp+rcx+258h+pidl.mkid.cb], si
0x18000dd31  lea     rcx, [rsp+258h+pidl]; pidl
0x18000dd36  call    cs:__imp_ILClone
0x18000dd3c  mov     rcx, [rsp+258h+var_18]
0x18000dd44  xor     rcx, rsp; StackCookie
0x18000dd47  call    __security_check_cookie
0x18000dd4c  lea     r11, [rsp+258h+var_8]
0x18000dd54  mov     rbx, [r11+18h]
0x18000dd58  mov     rsi, [r11+20h]
0x18000dd5c  mov     rsp, r11
0x18000dd5f  pop     rdi
0x18000dd60  retn
```
