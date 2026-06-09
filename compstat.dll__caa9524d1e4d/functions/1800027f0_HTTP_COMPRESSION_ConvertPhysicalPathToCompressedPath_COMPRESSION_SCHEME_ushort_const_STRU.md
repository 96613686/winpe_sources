# HTTP_COMPRESSION::ConvertPhysicalPathToCompressedPath(COMPRESSION_SCHEME *,ushort const *,STRU *)

- ea: `0x1800027f0`
- end: `0x18000288e`
- name: `?ConvertPhysicalPathToCompressedPath@HTTP_COMPRESSION@@CAJPEAVCOMPRESSION_SCHEME@@PEBGPEAVSTRU@@@Z`
- size: `158`
- prototype: `int __fastcall(struct COMPRESSION_SCHEME *, const unsigned __int16 *, struct STRU *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001310`
- `0x180002090`

## callees

- `0x1800027f0`

## import_xrefs

- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002827`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002827`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000283d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000285d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000286d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006cd7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000283d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000285d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000286d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180006cd7`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180002819`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180002819`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180002807`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180002807`

## pseudocode

```c
int __fastcall HTTP_COMPRESSION::ConvertPhysicalPathToCompressedPath(
        struct COMPRESSION_SCHEME *a1,
        const unsigned __int16 *a2,
        struct STRU *a3)
{
  int result; // eax
  __int64 CCH; // rdi
  __int64 v7; // rdi

  result = STRU::Copy(a3, (struct COMPRESSION_SCHEME *)((char *)a1 + 112));
  if ( result >= 0 )
  {
    CCH = STRU::QueryCCH(a3);
    result = STRU::Append(a3, a2);
    if ( result >= 0 )
    {
      if ( STRU::QueryStr(a3)[CCH] == 92 )
        STRU::QueryStr(a3)[CCH] = 94;
      v7 = (unsigned int)(CCH + 1);
      if ( STRU::QueryStr(a3)[v7] == 58 )
        STRU::QueryStr(a3)[v7] = 94;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800027f0  mov     [rsp+arg_10], rbx
0x1800027f5  push    rsi
0x1800027f6  sub     rsp, 20h
0x1800027fa  mov     rsi, rdx
0x1800027fd  mov     rbx, r8
0x180002800  lea     rdx, [rcx+70h]
0x180002804  mov     rcx, r8
0x180002807  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18000280d  test    eax, eax
0x18000280f  js      short loc_180002883
0x180002811  mov     rcx, rbx
0x180002814  mov     [rsp+28h+arg_8], rdi
0x180002819  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18000281f  mov     rdx, rsi
0x180002822  mov     rcx, rbx
0x180002825  mov     edi, eax
0x180002827  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000282d  test    eax, eax
0x18000282f  js      short loc_18000287E
0x180002831  mov     rcx, rbx
0x180002834  mov     [rsp+28h+arg_0], rbp
0x180002839  lea     rsi, [rdi+rdi]
0x18000283d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180002843  mov     ebp, 5Eh ; '^'
0x180002848  cmp     word ptr [rax+rsi], 5Ch ; '\'
0x18000284d  jz      loc_180006CD4
0x180002853  lea     eax, [rdi+1]
0x180002856  mov     rcx, rbx
0x180002859  lea     rdi, [rax+rax]
0x18000285d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180002863  cmp     word ptr [rax+rdi], 3Ah ; ':'
0x180002868  jnz     short loc_180002877
0x18000286a  mov     rcx, rbx
0x18000286d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180002873  mov     [rax+rdi], bp
0x180002877  mov     rbp, [rsp+28h+arg_0]
0x18000287c  xor     eax, eax
0x18000287e  mov     rdi, [rsp+28h+arg_8]
0x180002883  mov     rbx, [rsp+28h+arg_10]
0x180002888  add     rsp, 20h
0x18000288c  pop     rsi
0x18000288d  retn
0x180006cd4  mov     rcx, rbx
0x180006cd7  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180006cdd  mov     [rax+rsi], bp
0x180006ce1  jmp     loc_180002853
```
