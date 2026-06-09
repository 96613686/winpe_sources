# _CatDBCatnameAlreadyInHashesListOfCats(_JET_DB_STRUCT *,JET_DB_HASH_TABLE_IDS *,ushort const *)

- ea: `0x1800015cc`
- end: `0x180001675`
- name: `?_CatDBCatnameAlreadyInHashesListOfCats@@YAHPEAU_JET_DB_STRUCT@@PEAUJET_DB_HASH_TABLE_IDS@@PEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(struct _JET_DB_STRUCT *, struct JET_DB_HASH_TABLE_IDS *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180003c50`

## callees

- `0x1800015b0`
- `0x1800015cc`
- `0x180001680`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180001637`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180001637`

## pseudocode

```c
__int64 __fastcall _CatDBCatnameAlreadyInHashesListOfCats(
        struct _JET_DB_STRUCT *a1,
        struct JET_DB_HASH_TABLE_IDS *a2,
        const unsigned __int16 *a3,
        __int64 a4)
{
  JET_SESID v4; // rcx
  JET_COLUMNID v6; // r8d
  JET_TABLEID v7; // rdx
  unsigned int v8; // esi
  int v9; // eax
  _QWORD *v10; // rdi
  __int64 v11; // rbx
  unsigned int v13; // [rsp+60h] [rbp+8h] BYREF
  void *v14; // [rsp+68h] [rbp+10h] BYREF
  void *v15; // [rsp+78h] [rbp+20h] BYREF

  v4 = *((_QWORD *)a1 + 1);
  v6 = *((_DWORD *)a2 + 3);
  v7 = *(_QWORD *)a2;
  v8 = 0;
  v15 = 0;
  v14 = 0;
  v13 = 0;
  v9 = CatHelperRetrieveLongColumnAsStringVector(v4, v7, v6, a4, &v15, (unsigned __int16 ***)&v14, &v13);
  v10 = v14;
  v11 = 0;
  if ( !v9 )
  {
    while ( (unsigned int)v11 < v13 )
    {
      if ( !(unsigned int)_o__wcsicmp(v10[v11], a3) )
      {
        v8 = 1;
        break;
      }
      v11 = (unsigned int)(v11 + 1);
    }
  }
  if ( v15 )
    _CatDBFree(v15);
  if ( v10 )
    _CatDBFree(v10);
  return v8;
}

```

## disassembly

```asm
0x1800015cc  mov     r11, rsp
0x1800015cf  mov     [r11+18h], rbx
0x1800015d3  push    rbp
0x1800015d4  push    rsi
0x1800015d5  push    rdi
0x1800015d6  sub     rsp, 40h
0x1800015da  mov     rcx, [rcx+8]; sesid
0x1800015de  lea     rax, [r11+8]
0x1800015e2  mov     [r11-28h], rax
0x1800015e6  mov     rbp, r8
0x1800015e9  mov     r8d, [rdx+0Ch]; columnid
0x1800015ed  lea     rax, [r11+10h]
0x1800015f1  mov     rdx, [rdx]; tableid
0x1800015f4  xor     esi, esi
0x1800015f6  mov     [r11-30h], rax
0x1800015fa  lea     rax, [r11+20h]
0x1800015fe  mov     [r11-38h], rax
0x180001602  mov     qword ptr [r11+20h], 0
0x18000160a  mov     qword ptr [r11+10h], 0
0x180001612  mov     [rsp+58h+arg_0], 0
0x18000161a  call    ?CatHelperRetrieveLongColumnAsStringVector@@YAJ_K0KKAEAPEAGAEAPEAPEAGAEAK@Z; CatHelperRetrieveLongColumnAsStringVector(unsigned __int64,unsigned __int64,ulong,ulong,ushort * &,ushort * * &,ulong &)
0x18000161f  mov     rdi, [rsp+58h+arg_8]
0x180001624  xor     ebx, ebx
0x180001626  test    eax, eax
0x180001628  jnz     short loc_18000164A
0x18000162a  cmp     ebx, [rsp+58h+arg_0]
0x18000162e  jnb     short loc_18000164A
0x180001630  mov     rcx, [rdi+rbx*8]
0x180001634  mov     rdx, rbp
0x180001637  call    cs:__imp__o__wcsicmp
0x18000163d  test    eax, eax
0x18000163f  jz      short loc_180001645
0x180001641  inc     ebx
0x180001643  jmp     short loc_18000162A
0x180001645  mov     esi, 1
0x18000164a  mov     rcx, [rsp+58h+arg_18]; void *
0x18000164f  test    rcx, rcx
0x180001652  jz      short loc_180001659
0x180001654  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x180001659  test    rdi, rdi
0x18000165c  jz      short loc_180001666
0x18000165e  mov     rcx, rdi; void *
0x180001661  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x180001666  mov     rbx, [rsp+58h+arg_10]
0x18000166b  mov     eax, esi
0x18000166d  add     rsp, 40h
0x180001671  pop     rdi
0x180001672  pop     rsi
0x180001673  pop     rbp
0x180001674  retn
```
