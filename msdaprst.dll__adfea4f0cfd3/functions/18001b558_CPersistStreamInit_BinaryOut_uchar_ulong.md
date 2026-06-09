# CPersistStreamInit::BinaryOut(uchar *,ulong)

- ea: `0x18001b558`
- end: `0x18001b600`
- name: `?BinaryOut@CPersistStreamInit@@AEAAJPEAEK@Z`
- size: `168`
- prototype: `__int64 __fastcall(CPersistStreamInit *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d828`
- `0x18001eb10`
- `0x18001f7c8`
- `0x18001fec8`
- `0x18001fff8`

## callees

- `0x18001b558`
- `0x18001d054`

## string_xrefs

- `0x18001b580`: `0123456789abcdefenduser\databaseaccess\src\mdac\rds\shared\foxprops\uprops.cpp`

## pseudocode

```c
__int64 __fastcall CPersistStreamInit::BinaryOut(CPersistStreamInit *this, unsigned __int8 *a2, unsigned int a3)
{
  __int64 result; // rax
  __int64 v4; // rbx
  char v8; // r9
  __int16 v9; // r8
  __int16 Src; // [rsp+60h] [rbp+18h] BYREF
  __int16 v11; // [rsp+62h] [rbp+1Ah]
  unsigned int i; // [rsp+68h] [rbp+20h] BYREF

  result = 0;
  v4 = 0;
  for ( i = 0; (unsigned int)v4 < a3; v4 = (unsigned int)(v4 + 1) )
  {
    v8 = *((_BYTE *)this + 64);
    v9 = chHex[(unsigned __int64)a2[v4] >> 4];
    if ( v8 )
    {
      HIBYTE(Src) = chHex[a2[v4] & 0xF];
      LOBYTE(Src) = v9;
    }
    else
    {
      v11 = chHex[a2[v4] & 0xF];
      Src = v9;
    }
    result = CPersistStreamInit::Write(this, &Src, v8 != 0 ? 2 : 4, &i, 1);
    if ( (int)result < 0 )
      break;
  }
  return result;
}

```

## disassembly

```asm
0x18001b558  mov     [rsp+arg_0], rbx
0x18001b55d  mov     [rsp+arg_8], rbp
0x18001b562  push    rsi
0x18001b563  push    rdi
0x18001b564  push    r14
0x18001b566  sub     rsp, 30h
0x18001b56a  xor     eax, eax
0x18001b56c  xor     ebx, ebx
0x18001b56e  mov     [rsp+48h+arg_18], eax
0x18001b572  mov     edi, r8d
0x18001b575  mov     rbp, rdx
0x18001b578  mov     rsi, rcx
0x18001b57b  test    r8d, r8d
0x18001b57e  jz      short loc_18001B5EC
0x18001b580  lea     r14, ?chHex@@3PADA; "0123456789abcdefenduser\\databaseaccess"...
0x18001b587  movzx   ecx, byte ptr [rbx+rbp]
0x18001b58b  mov     r9b, [rsi+40h]
0x18001b58f  mov     eax, ecx
0x18001b591  and     eax, 0Fh
0x18001b594  shr     rcx, 4
0x18001b598  movsx   edx, byte ptr [rax+r14]
0x18001b59d  movsx   r8d, byte ptr [rcx+r14]
0x18001b5a2  test    r9b, r9b
0x18001b5a5  jz      short loc_18001B5B2
0x18001b5a7  mov     byte ptr [rsp+48h+Src+1], dl
0x18001b5ab  mov     byte ptr [rsp+48h+Src], r8b
0x18001b5b0  jmp     short loc_18001B5BD
0x18001b5b2  mov     [rsp+48h+arg_12], dx
0x18001b5b7  mov     [rsp+48h+Src], r8w
0x18001b5bd  neg     r9b
0x18001b5c0  mov     [rsp+48h+var_28], 1; bool
0x18001b5c5  lea     r9, [rsp+48h+arg_18]; unsigned int *
0x18001b5ca  mov     rcx, rsi; this
0x18001b5cd  sbb     r8d, r8d
0x18001b5d0  lea     rdx, [rsp+48h+Src]; Src
0x18001b5d5  and     r8d, 0FFFFFFFEh
0x18001b5d9  add     r8d, 4; Size
0x18001b5dd  call    ?Write@CPersistStreamInit@@AEAAJPEAXKPEAK_N@Z; CPersistStreamInit::Write(void *,ulong,ulong *,bool)
0x18001b5e2  test    eax, eax
0x18001b5e4  js      short loc_18001B5EC
0x18001b5e6  inc     ebx
0x18001b5e8  cmp     ebx, edi
0x18001b5ea  jb      short loc_18001B587
0x18001b5ec  mov     rbx, [rsp+48h+arg_0]
0x18001b5f1  mov     rbp, [rsp+48h+arg_8]
0x18001b5f6  add     rsp, 30h
0x18001b5fa  pop     r14
0x18001b5fc  pop     rdi
0x18001b5fd  pop     rsi
0x18001b5fe  retn
```
