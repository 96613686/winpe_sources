# RECEIVE_QUEUE::PostData(_WEB_SOCKET_BUFFER_TYPE,_WEB_SOCKET_BUFFER *,int *)

- ea: `0x1800041dc`
- end: `0x1800042d9`
- name: `?PostData@RECEIVE_QUEUE@@QEAAJW4_WEB_SOCKET_BUFFER_TYPE@@PEAT_WEB_SOCKET_BUFFER@@PEAH@Z`
- size: `253`
- prototype: `__int64 __fastcall(_DWORD *, int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006284`

## callees

- `0x180001008`
- `0x1800040c0`
- `0x1800041dc`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180004271`
- `iisutil!PuDbgPrint` at `0x1800042c0`
- `iisutil!PuDbgPrint` at `0x180004271`
- `iisutil!PuDbgPrint` at `0x1800042c0`

## string_xrefs

- `0x18000426a`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\receivequeue.cxx`
- `0x1800042b9`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\receivequeue.cxx`

## pseudocode

```c
__int64 __fastcall RECEIVE_QUEUE::PostData(_DWORD *a1, int a2, __int64 a3, _DWORD *a4)
{
  _DWORD *v8; // rax
  unsigned int v9; // ebx

  if ( a2 > -2147483644 )
    return 2147942487LL;
  v8 = operator new(0x30u);
  if ( v8 )
  {
    v8[6] = 0;
    *(_QWORD *)v8 = &RECEIVE_QUEUE_RECORD::`vftable';
    v8[8] = a2;
    v9 = 0;
    v8[9] = 0;
    *((_QWORD *)v8 + 5) = 0;
    *((_QWORD *)v8 + 5) = *(_QWORD *)a3;
    v8[6] = *(_DWORD *)(a3 + 8);
    QUEUE::Enqueue((QUEUE *)(a1 + 4), (struct QUEUE_RECORD *)v8);
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\receivequeue.cxx",
        114,
        "RECEIVE_QUEUE::PostData",
        "Copied data to receive queue\n");
    if ( a1[19] >= a1[2] )
      *a4 = 1;
  }
  else
  {
    v9 = -2147024882;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\receivequeue.cxx",
        135,
        "RECEIVE_QUEUE::PostData",
        "ERROR = %08x\n",
        -2147024882);
  }
  return v9;
}

```

## disassembly

```asm
0x1800041dc  push    rbx
0x1800041de  push    rsi
0x1800041df  push    rdi
0x1800041e0  push    r14
0x1800041e2  sub     rsp, 38h
0x1800041e6  mov     rsi, r9
0x1800041e9  mov     r14, r8
0x1800041ec  mov     ebx, edx
0x1800041ee  mov     rdi, rcx
0x1800041f1  cmp     edx, 80000004h
0x1800041f7  jg      loc_1800042CA
0x1800041fd  mov     ecx, 30h ; '0'; Size
0x180004202  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004207  xor     edx, edx
0x180004209  test    rax, rax
0x18000420c  jz      short loc_180004287
0x18000420e  mov     [rax+18h], edx
0x180004211  lea     rcx, ??_7RECEIVE_QUEUE_RECORD@@6B@; const RECEIVE_QUEUE_RECORD::`vftable'
0x180004218  mov     [rax], rcx
0x18000421b  mov     [rax+20h], ebx
0x18000421e  mov     ebx, edx
0x180004220  mov     [rax+24h], edx
0x180004223  mov     [rax+28h], rdx
0x180004227  mov     rdx, rax; struct QUEUE_RECORD *
0x18000422a  mov     rcx, [r14]
0x18000422d  mov     [rax+28h], rcx
0x180004231  mov     ecx, [r14+8]
0x180004235  mov     [rax+18h], ecx
0x180004238  lea     rcx, [rdi+10h]; this
0x18000423c  call    ?Enqueue@QUEUE@@QEAAXPEAVQUEUE_RECORD@@@Z; QUEUE::Enqueue(QUEUE_RECORD *)
0x180004241  test    byte ptr cs:g_dwDebugFlags, 3
0x180004248  jz      short loc_180004277
0x18000424a  mov     rcx, cs:g_pDebug
0x180004251  lea     rax, aCopiedDataToRe; "Copied data to receive queue\n"
0x180004258  lea     r9, aReceiveQueuePo; "RECEIVE_QUEUE::PostData"
0x18000425f  mov     [rsp+58h+var_38], rax
0x180004264  mov     r8d, 72h ; 'r'
0x18000426a  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004271  call    cs:__imp_PuDbgPrint
0x180004277  mov     eax, [rdi+8]
0x18000427a  cmp     [rdi+4Ch], eax
0x18000427d  jb      short loc_1800042C6
0x18000427f  mov     dword ptr [rsi], 1
0x180004285  jmp     short loc_1800042C6
0x180004287  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000428e  mov     ebx, 8007000Eh
0x180004293  jz      short loc_1800042C6
0x180004295  mov     rcx, cs:g_pDebug
0x18000429c  lea     rax, aError08x; "ERROR = %08x\n"
0x1800042a3  mov     [rsp+58h+var_30], ebx
0x1800042a7  lea     r9, aReceiveQueuePo; "RECEIVE_QUEUE::PostData"
0x1800042ae  mov     r8d, 87h
0x1800042b4  mov     [rsp+58h+var_38], rax
0x1800042b9  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800042c0  call    cs:__imp_PuDbgPrint
0x1800042c6  mov     eax, ebx
0x1800042c8  jmp     short loc_1800042CF
0x1800042ca  mov     eax, 80070057h
0x1800042cf  add     rsp, 38h
0x1800042d3  pop     r14
0x1800042d5  pop     rdi
0x1800042d6  pop     rsi
0x1800042d7  pop     rbx
0x1800042d8  retn
```
