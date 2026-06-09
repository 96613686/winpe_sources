# _CatDBRemoveCatNameFromCatNameTable(_JET_DB_STRUCT *,ushort const *)

- ea: `0x18001aeb0`
- end: `0x18001af6d`
- name: `?_CatDBRemoveCatNameFromCatNameTable@@YAHPEAU_JET_DB_STRUCT@@PEBG@Z`
- size: `189`
- prototype: `__int64 __fastcall(struct _JET_DB_STRUCT *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180008888`
- `0x18001966c`
- `0x18001b8f4`

## callees

- `0x180003570`
- `0x1800038f0`
- `0x18000a59c`
- `0x18000acbc`
- `0x18001aeb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001af40`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001af40`
- `ESENT!JetMove` at `0x18001aeeb`
- `ESENT!JetMove` at `0x18001aeeb`

## pseudocode

```c
__int64 __fastcall _CatDBRemoveCatNameFromCatNameTable(struct _JET_DB_STRUCT *a1, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  unsigned int v5; // esi
  int i; // r8d
  JET_ERR v7; // eax
  int v8; // edi
  unsigned int v9; // edx
  unsigned __int16 *v10; // rcx
  unsigned int v11; // r8d
  DWORD v12; // eax
  int v14; // [rsp+28h] [rbp-40h]

  v4 = 1;
  v5 = 0;
  while ( 2 )
  {
    if ( v5 < 2 )
    {
      for ( i = 0x80000000; ; i = 1 )
      {
        v7 = JetMove(*((_QWORD *)a1 + 1), *((_QWORD *)a1 + 2 * v5 + 3), i, 0);
        v8 = v7;
        if ( v7 )
          break;
        if ( !(unsigned int)_CatDBRemoveCatNameFromMultiValuedColumn(
                              a1,
                              *((_QWORD *)a1 + 2 * v5 + 3),
                              *((_DWORD *)a1 + 4 * v5 + 9),
                              a2) )
        {
          v11 = 5423;
          goto LABEL_12;
        }
      }
      if ( v7 == -1603 || !(unsigned int)_CatDBJET_errFailure(v7) )
      {
        ++v5;
        continue;
      }
      v12 = _CatDBMapJetError(v8);
      SetLastError(v12);
      v11 = 5442;
LABEL_12:
      ErrLog_LogError(v10, v9, v11, 0, 0, v14);
      return 0;
    }
    return v4;
  }
}

```

## disassembly

```asm
0x18001aeb0  push    rbx
0x18001aeb2  push    rbp
0x18001aeb3  push    rsi
0x18001aeb4  push    rdi
0x18001aeb5  push    r14
0x18001aeb7  push    r15
0x18001aeb9  sub     rsp, 38h
0x18001aebd  mov     r15, rdx
0x18001aec0  mov     rbp, rcx
0x18001aec3  mov     ebx, 1
0x18001aec8  xor     esi, esi
0x18001aeca  cmp     esi, 2
0x18001aecd  jnb     loc_18001AF5E
0x18001aed3  mov     r14d, esi
0x18001aed6  mov     r8d, 80000000h; cRow
0x18001aedc  add     r14, r14
0x18001aedf  xor     r9d, r9d; grbit
0x18001aee2  mov     rdx, [rbp+r14*8+18h]; tableid
0x18001aee7  mov     rcx, [rbp+8]; sesid
0x18001aeeb  call    cs:__imp_JetMove
0x18001aef1  mov     edi, eax
0x18001aef3  test    eax, eax
0x18001aef5  jnz     short loc_18001AF18
0x18001aef7  mov     r8d, [rbp+r14*8+24h]; unsigned int
0x18001aefc  mov     r9, r15; unsigned __int16 *
0x18001aeff  mov     rdx, [rbp+r14*8+18h]; unsigned __int64
0x18001af04  mov     rcx, rbp; struct _JET_DB_STRUCT *
0x18001af07  call    ?_CatDBRemoveCatNameFromMultiValuedColumn@@YAHPEAU_JET_DB_STRUCT@@_KKPEBG@Z; _CatDBRemoveCatNameFromMultiValuedColumn(_JET_DB_STRUCT *,unsigned __int64,ulong,ushort const *)
0x18001af0c  xor     r9d, r9d
0x18001af0f  test    eax, eax
0x18001af11  jz      short loc_18001AF2F
0x18001af13  mov     r8d, ebx
0x18001af16  jmp     short loc_18001AEE2
0x18001af18  cmp     edi, 0FFFFF9BDh
0x18001af1e  jz      short loc_18001AF2B
0x18001af20  mov     ecx, edi; int
0x18001af22  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001af27  test    eax, eax
0x18001af29  jnz     short loc_18001AF37
0x18001af2b  add     esi, ebx
0x18001af2d  jmp     short loc_18001AECA
0x18001af2f  mov     r8d, 152Fh
0x18001af35  jmp     short loc_18001AF4F
0x18001af37  mov     ecx, edi; int
0x18001af39  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18001af3e  mov     ecx, eax; dwErrCode
0x18001af40  call    cs:__imp_SetLastError
0x18001af46  xor     r9d, r9d; unsigned int
0x18001af49  mov     r8d, 1542h; unsigned int
0x18001af4f  mov     [rsp+68h+var_48], 0; int
0x18001af57  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001af5c  xor     ebx, ebx
0x18001af5e  mov     eax, ebx
0x18001af60  add     rsp, 38h
0x18001af64  pop     r15
0x18001af66  pop     r14
0x18001af68  pop     rdi
0x18001af69  pop     rsi
0x18001af6a  pop     rbp
0x18001af6b  pop     rbx
0x18001af6c  retn
```
