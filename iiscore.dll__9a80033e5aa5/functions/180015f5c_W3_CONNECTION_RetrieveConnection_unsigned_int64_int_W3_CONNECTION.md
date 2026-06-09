# W3_CONNECTION::RetrieveConnection(unsigned __int64,int,W3_CONNECTION * *)

- ea: `0x180015f5c`
- end: `0x1800160c5`
- name: `?RetrieveConnection@W3_CONNECTION@@SAJ_KHPEAPEAV1@@Z`
- size: `361`
- prototype: `__int64 __fastcall(unsigned __int64, int, struct W3_CONNECTION **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020450`

## callees

- `0x180015f5c`
- `0x180016100`
- `0x1800240e8`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800160a8`
- `iisutil!PuDbgPrint` at `0x1800160a8`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180015fae`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180015fae`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180016021`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180016021`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180015f91`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180015f91`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x1800160bd`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x1800160bd`
- `w3dt!UlAtqWaitForDisconnect` at `0x18001603c`
- `w3dt!UlAtqWaitForDisconnect` at `0x18001603c`

## string_xrefs

- `0x18001608a`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3connection.cxx`

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
0x180015f5c  mov     rax, rsp
0x180015f5f  mov     [rax+10h], rbx
0x180015f63  mov     [rax+8], rcx
0x180015f67  push    rbp
0x180015f68  push    rsi
0x180015f69  push    rdi
0x180015f6a  sub     rsp, 40h
0x180015f6e  mov     rcx, cs:?sm_pConnectionTable@W3_CONNECTION@@0PEAVW3_CONNECTION_HASH@@EA; W3_CONNECTION_HASH * W3_CONNECTION::sm_pConnectionTable
0x180015f75  mov     rsi, r8
0x180015f78  mov     ebp, edx
0x180015f7a  mov     qword ptr [r8], 0
0x180015f81  lea     r8, [rax+18h]
0x180015f85  mov     qword ptr [rax+18h], 0
0x180015f8d  lea     rdx, [rax+8]
0x180015f91  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180015f97  mov     rcx, [rsp+58h+arg_10]
0x180015f9c  mov     [rsi], rcx
0x180015f9f  test    eax, eax
0x180015fa1  jz      loc_18001604C
0x180015fa7  mov     rcx, cs:?sm_pachW3Connections@W3_CONNECTION@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * W3_CONNECTION::sm_pachW3Connections
0x180015fae  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180015fb4  mov     rbx, rax
0x180015fb7  test    rax, rax
0x180015fba  jnz     short loc_180015FCE
0x180015fbc  mov     eax, 80070008h
0x180015fc1  mov     rbx, [rsp+58h+arg_8]
0x180015fc6  add     rsp, 40h
0x180015fca  pop     rdi
0x180015fcb  pop     rsi
0x180015fcc  pop     rbp
0x180015fcd  retn
0x180015fce  mov     rcx, [rsp+58h+arg_0]
0x180015fd3  lea     rax, ??_7W3_CONNECTION@@6B@; const W3_CONNECTION::`vftable'
0x180015fda  mov     [rbx+10h], rcx
0x180015fde  xor     r8d, r8d; bool
0x180015fe1  lea     rcx, [rbx+28h]; this
0x180015fe5  mov     [rbx], rax
0x180015fe8  mov     dl, 1; bool
0x180015fea  mov     dword ptr [rbx+8], 4E433357h
0x180015ff1  mov     dword ptr [rbx+18h], 1
0x180015ff8  mov     dword ptr [rbx+1Ch], 1
0x180015fff  mov     qword ptr [rbx+20h], 0
0x180016007  call    ??0CONTEXT_CONTAINER@@QEAA@_N0@Z; CONTEXT_CONTAINER::CONTEXT_CONTAINER(bool,bool)
0x18001600c  mov     rcx, cs:?sm_pConnectionTable@W3_CONNECTION@@0PEAVW3_CONNECTION_HASH@@EA; W3_CONNECTION_HASH * W3_CONNECTION::sm_pConnectionTable
0x180016013  xor     r8d, r8d
0x180016016  mov     rdx, rbx
0x180016019  mov     qword ptr [rbx+78h], 0
0x180016021  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180016027  mov     edi, eax
0x180016029  test    eax, eax
0x18001602b  jnz     short loc_180016053
0x18001602d  test    ebp, ebp
0x18001602f  jz      short loc_180016049
0x180016031  mov     rcx, [rsp+58h+arg_0]
0x180016036  lea     edx, [rax+1]
0x180016039  mov     r8, rbx
0x18001603c  call    cs:__imp_?UlAtqWaitForDisconnect@@YAJ_KHPEAX@Z; UlAtqWaitForDisconnect(unsigned __int64,int,void *)
0x180016042  cmp     eax, 800703E5h
0x180016047  jnz     short loc_18001606F
0x180016049  mov     [rsi], rbx
0x18001604c  xor     eax, eax
0x18001604e  jmp     loc_180015FC1
0x180016053  mov     rcx, rbx; this
0x180016056  call    ?DereferenceConnection@W3_CONNECTION@@QEAAXXZ; W3_CONNECTION::DereferenceConnection(void)
0x18001605b  test    edi, edi
0x18001605d  jle     short loc_180016068
0x18001605f  movzx   edi, di
0x180016062  or      edi, 80070000h
0x180016068  mov     eax, edi
0x18001606a  jmp     loc_180015FC1
0x18001606f  test    byte ptr cs:g_dwDebugFlags, 3
0x180016076  jz      short loc_1800160AE
0x180016078  mov     rcx, cs:g_pDebug
0x18001607f  lea     r9, aW3ConnectionRe; "W3_CONNECTION::RetrieveConnection"
0x180016086  mov     [rsp+58h+var_28], eax
0x18001608a  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180016091  lea     rax, aConnectionPDis; "Connection '%p' disconnected.  hr = %x"...
0x180016098  mov     [rsp+58h+var_30], rbx
0x18001609d  mov     r8d, 0CEh
0x1800160a3  mov     [rsp+58h+var_38], rax
0x1800160a8  call    cs:__imp_PuDbgPrint
0x1800160ae  xor     eax, eax
0x1800160b0  mov     rdx, rbx
0x1800160b3  xchg    eax, [rbx+1Ch]
0x1800160b6  mov     rcx, cs:?sm_pConnectionTable@W3_CONNECTION@@0PEAVW3_CONNECTION_HASH@@EA; W3_CONNECTION_HASH * W3_CONNECTION::sm_pConnectionTable
0x1800160bd  call    cs:__imp_?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z; CLKRHashTable::DeleteRecord(void const *)
0x1800160c3  jmp     short loc_180016049
```
