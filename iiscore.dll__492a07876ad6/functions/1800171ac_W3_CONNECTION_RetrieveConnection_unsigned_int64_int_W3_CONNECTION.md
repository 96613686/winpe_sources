# W3_CONNECTION::RetrieveConnection(unsigned __int64,int,W3_CONNECTION * *)

- ea: `0x1800171ac`
- end: `0x18001733d`
- name: `?RetrieveConnection@W3_CONNECTION@@SAJ_KHPEAPEAV1@@Z`
- size: `401`
- prototype: `__int64 __fastcall(unsigned __int64, int, struct W3_CONNECTION **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022080`

## callees

- `0x1800171ac`
- `0x180017384`
- `0x180025f88`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180017311`
- `iisutil!PuDbgPrint` at `0x180017311`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180017204`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180017204`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18001727e`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18001727e`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800171e1`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800171e1`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x18001732c`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x18001732c`
- `w3dt!UlAtqWaitForDisconnect` at `0x18001729f`
- `w3dt!UlAtqWaitForDisconnect` at `0x18001729f`

## string_xrefs

- `0x1800172f3`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3connection.cxx`

## pseudocode

```c
__int64 __fastcall W3_CONNECTION::RetrieveConnection(unsigned __int64 a1, int a2, struct W3_CONNECTION **a3)
{
  void *v3; // rcx
  int Key; // eax
  volatile __int32 *v7; // rbx
  void *v9; // rcx
  int inserted; // edi
  int v11; // eax
  unsigned __int64 v12; // [rsp+60h] [rbp+8h] BYREF
  struct W3_CONNECTION *v13; // [rsp+70h] [rbp+18h] BYREF

  v12 = a1;
  v3 = W3_CONNECTION::sm_pConnectionTable;
  *a3 = 0;
  v13 = 0;
  Key = CLKRHashTable::FindKey(v3, &v12, &v13);
  *a3 = v13;
  if ( !Key )
    return 0;
  v7 = (volatile __int32 *)ALLOC_CACHE_HANDLER::Alloc(W3_CONNECTION::sm_pachW3Connections);
  if ( !v7 )
    return 2147942408LL;
  *((_QWORD *)v7 + 2) = v12;
  *(_QWORD *)v7 = &W3_CONNECTION::`vftable';
  *((_DWORD *)v7 + 2) = 1313026903;
  *((_DWORD *)v7 + 6) = 1;
  *((_DWORD *)v7 + 7) = 1;
  *((_QWORD *)v7 + 4) = 0;
  CONTEXT_CONTAINER::CONTEXT_CONTAINER((CONTEXT_CONTAINER *)(v7 + 10), 1, 0);
  v9 = W3_CONNECTION::sm_pConnectionTable;
  *((_QWORD *)v7 + 15) = 0;
  inserted = CLKRHashTable::InsertRecord(v9, v7, 0);
  if ( !inserted )
  {
    if ( a2 )
    {
      v11 = UlAtqWaitForDisconnect(v12, 1, (void *)v7);
      if ( v11 != -2147023899 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\core\\w3connection.cxx",
            206,
            "W3_CONNECTION::RetrieveConnection",
            "Connection '%p' disconnected.  hr = %x\n",
            (const void *)v7,
            v11);
        _InterlockedExchange(v7 + 7, 0);
        CLKRHashTable::DeleteRecord(W3_CONNECTION::sm_pConnectionTable, v7);
      }
    }
    *a3 = (struct W3_CONNECTION *)v7;
    return 0;
  }
  W3_CONNECTION::DereferenceConnection((W3_CONNECTION *)v7);
  if ( inserted > 0 )
    return (unsigned __int16)inserted | 0x80070000;
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1800171ac  mov     rax, rsp
0x1800171af  mov     [rax+10h], rbx
0x1800171b3  mov     [rax+8], rcx
0x1800171b7  push    rbp
0x1800171b8  push    rsi
0x1800171b9  push    rdi
0x1800171ba  sub     rsp, 40h
0x1800171be  mov     rcx, cs:?sm_pConnectionTable@W3_CONNECTION@@0PEAVW3_CONNECTION_HASH@@EA; W3_CONNECTION_HASH * W3_CONNECTION::sm_pConnectionTable
0x1800171c5  mov     rsi, r8
0x1800171c8  mov     ebp, edx
0x1800171ca  mov     qword ptr [r8], 0
0x1800171d1  lea     r8, [rax+18h]
0x1800171d5  mov     qword ptr [rax+18h], 0
0x1800171dd  lea     rdx, [rax+8]
0x1800171e1  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x1800171e8  nop     dword ptr [rax+rax+00h]
0x1800171ed  mov     rcx, [rsp+58h+arg_10]
0x1800171f2  mov     [rsi], rcx
0x1800171f5  test    eax, eax
0x1800171f7  jz      loc_1800172B5
0x1800171fd  mov     rcx, cs:?sm_pachW3Connections@W3_CONNECTION@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * W3_CONNECTION::sm_pachW3Connections
0x180017204  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18001720b  nop     dword ptr [rax+rax+00h]
0x180017210  mov     rbx, rax
0x180017213  test    rax, rax
0x180017216  jnz     short loc_18001722B
0x180017218  mov     eax, 80070008h
0x18001721d  mov     rbx, [rsp+58h+arg_8]
0x180017222  add     rsp, 40h
0x180017226  pop     rdi
0x180017227  pop     rsi
0x180017228  pop     rbp
0x180017229  retn
0x18001722b  mov     rcx, [rsp+58h+arg_0]
0x180017230  lea     rax, ??_7W3_CONNECTION@@6B@; const W3_CONNECTION::`vftable'
0x180017237  mov     [rbx+10h], rcx
0x18001723b  xor     r8d, r8d; bool
0x18001723e  lea     rcx, [rbx+28h]; this
0x180017242  mov     [rbx], rax
0x180017245  mov     dl, 1; bool
0x180017247  mov     dword ptr [rbx+8], 4E433357h
0x18001724e  mov     dword ptr [rbx+18h], 1
0x180017255  mov     dword ptr [rbx+1Ch], 1
0x18001725c  mov     qword ptr [rbx+20h], 0
0x180017264  call    ??0CONTEXT_CONTAINER@@QEAA@_N0@Z; CONTEXT_CONTAINER::CONTEXT_CONTAINER(bool,bool)
0x180017269  mov     rcx, cs:?sm_pConnectionTable@W3_CONNECTION@@0PEAVW3_CONNECTION_HASH@@EA; W3_CONNECTION_HASH * W3_CONNECTION::sm_pConnectionTable
0x180017270  xor     r8d, r8d
0x180017273  mov     rdx, rbx
0x180017276  mov     qword ptr [rbx+78h], 0
0x18001727e  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180017285  nop     dword ptr [rax+rax+00h]
0x18001728a  mov     edi, eax
0x18001728c  test    eax, eax
0x18001728e  jnz     short loc_1800172BC
0x180017290  test    ebp, ebp
0x180017292  jz      short loc_1800172B2
0x180017294  mov     rcx, [rsp+58h+arg_0]
0x180017299  lea     edx, [rax+1]
0x18001729c  mov     r8, rbx
0x18001729f  call    cs:__imp_?UlAtqWaitForDisconnect@@YAJ_KHPEAX@Z; UlAtqWaitForDisconnect(unsigned __int64,int,void *)
0x1800172a6  nop     dword ptr [rax+rax+00h]
0x1800172ab  cmp     eax, 800703E5h
0x1800172b0  jnz     short loc_1800172D8
0x1800172b2  mov     [rsi], rbx
0x1800172b5  xor     eax, eax
0x1800172b7  jmp     loc_18001721D
0x1800172bc  mov     rcx, rbx; this
0x1800172bf  call    ?DereferenceConnection@W3_CONNECTION@@QEAAXXZ; W3_CONNECTION::DereferenceConnection(void)
0x1800172c4  test    edi, edi
0x1800172c6  jle     short loc_1800172D1
0x1800172c8  movzx   edi, di
0x1800172cb  or      edi, 80070000h
0x1800172d1  mov     eax, edi
0x1800172d3  jmp     loc_18001721D
0x1800172d8  test    byte ptr cs:g_dwDebugFlags, 3
0x1800172df  jz      short loc_18001731D
0x1800172e1  mov     rcx, cs:g_pDebug
0x1800172e8  lea     r9, aW3ConnectionRe; "W3_CONNECTION::RetrieveConnection"
0x1800172ef  mov     [rsp+58h+var_28], eax
0x1800172f3  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800172fa  lea     rax, aConnectionPDis; "Connection '%p' disconnected.  hr = %x"...
0x180017301  mov     [rsp+58h+var_30], rbx
0x180017306  mov     r8d, 0CEh
0x18001730c  mov     [rsp+58h+var_38], rax
0x180017311  call    cs:__imp_PuDbgPrint
0x180017318  nop     dword ptr [rax+rax+00h]
0x18001731d  xor     eax, eax
0x18001731f  mov     rdx, rbx
0x180017322  xchg    eax, [rbx+1Ch]
0x180017325  mov     rcx, cs:?sm_pConnectionTable@W3_CONNECTION@@0PEAVW3_CONNECTION_HASH@@EA; W3_CONNECTION_HASH * W3_CONNECTION::sm_pConnectionTable
0x18001732c  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x180017333  nop     dword ptr [rax+rax+00h]
0x180017338  jmp     loc_1800172B2
```
