# CatHelperAddToLongColumn(unsigned __int64,unsigned __int64,ulong,ushort const *)

- ea: `0x180003ff8`
- end: `0x18000408e`
- name: `?CatHelperAddToLongColumn@@YAJ_K0KPEBG@Z`
- size: `150`
- prototype: `__int64 __fastcall(JET_SESID sesid, JET_TABLEID tableid, JET_COLUMNID columnid, LPCWCH lpWideCharStr)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180003c50`

## callees

- `0x180001480`
- `0x1800015b0`
- `0x180003ff8`

## import_xrefs

- `ESENT!JetSetColumn` at `0x18000405e`
- `ESENT!JetSetColumn` at `0x18000405e`

## pseudocode

```c
__int64 __fastcall CatHelperAddToLongColumn(
        JET_SESID sesid,
        const unsigned __int16 *tableid,
        JET_COLUMNID columnid,
        LPCWCH lpWideCharStr)
{
  char *v7; // rdi
  unsigned int v8; // ebx
  unsigned int cbData; // [rsp+78h] [rbp+20h] BYREF

  cbData = 0;
  if ( !lpWideCharStr || !*lpWideCharStr )
    return 0;
  v7 = _CatDBConvertWszToCodePageCat(lpWideCharStr, tableid, columnid, &cbData);
  if ( !v7 )
    return 4294966285LL;
  v8 = JetSetColumn(sesid, (JET_TABLEID)tableid, columnid, v7, cbData, 1u, 0);
  _CatDBFree(v7);
  return v8;
}

```

## disassembly

```asm
0x180003ff8  mov     r11, rsp
0x180003ffb  mov     [r11+8], rbx
0x180003fff  mov     [r11+10h], rbp
0x180004003  push    rsi
0x180004004  push    rdi
0x180004005  push    r14
0x180004007  sub     rsp, 40h
0x18000400b  xor     r14d, r14d
0x18000400e  mov     rax, r9
0x180004011  mov     [r11+20h], r14d
0x180004015  mov     ebx, r8d
0x180004018  mov     rsi, rdx
0x18000401b  mov     rbp, rcx
0x18000401e  test    r9, r9
0x180004021  jz      short loc_180004072
0x180004023  cmp     [r9], r14w
0x180004027  jz      short loc_180004072
0x180004029  lea     r9, [r11+20h]; unsigned int *
0x18000402d  mov     rcx, rax; lpWideCharStr
0x180004030  call    ?_CatDBConvertWszToCodePageCat@@YAPEADPEBG0IPEAK@Z; _CatDBConvertWszToCodePageCat(ushort const *,ushort const *,uint,ulong *)
0x180004035  mov     rdi, rax
0x180004038  test    rax, rax
0x18000403b  jz      short loc_180004087
0x18000403d  mov     eax, [rsp+58h+arg_18]
0x180004041  mov     r9, rdi; pvData
0x180004044  mov     [rsp+58h+psetinfo], r14; psetinfo
0x180004049  mov     r8d, ebx; columnid
0x18000404c  mov     [rsp+58h+grbit], 1; grbit
0x180004054  mov     rdx, rsi; tableid
0x180004057  mov     rcx, rbp; sesid
0x18000405a  mov     [rsp+58h+cbData], eax; cbData
0x18000405e  call    cs:__imp_JetSetColumn
0x180004064  mov     rcx, rdi; void *
0x180004067  mov     ebx, eax
0x180004069  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18000406e  mov     eax, ebx
0x180004070  jmp     short loc_180004074
0x180004072  xor     eax, eax
0x180004074  mov     rbx, [rsp+58h+arg_0]
0x180004079  mov     rbp, [rsp+58h+arg_8]
0x18000407e  add     rsp, 40h
0x180004082  pop     r14
0x180004084  pop     rdi
0x180004085  pop     rsi
0x180004086  retn
0x180004087  mov     eax, 0FFFFFC0Dh
0x18000408c  jmp     short loc_180004074
```
