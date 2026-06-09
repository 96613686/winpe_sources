# DfsCreateThreadpool(ulong,ulong,_TP_POOL * *)

- ea: `0x14003b698`
- end: `0x14003b73c`
- name: `?DfsCreateThreadpool@@YAKKKPEAPEAU_TP_POOL@@@Z`
- size: `164`
- prototype: `unsigned int(unsigned int, unsigned int, struct _TP_POOL **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140018e88`

## callees

- `0x14003b698`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b6e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b6e3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x14003b6d3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x14003b6d3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x14003b6b9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x14003b6b9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x14003b6fd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x14003b6fd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x14003b714`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x14003b714`

## pseudocode

```c
__int64 __fastcall DfsCreateThreadpool(__int64 a1, DWORD a2, struct _TP_POOL **a3)
{
  DWORD LastError; // edi
  struct _TP_POOL *Threadpool; // rax
  struct _TP_POOL *v7; // rbx

  LastError = 0;
  *a3 = 0;
  Threadpool = CreateThreadpool(0);
  v7 = Threadpool;
  if ( Threadpool && SetThreadpoolThreadMinimum(Threadpool, 2u) )
  {
    if ( a2 )
      SetThreadpoolThreadMaximum(v7, a2);
    *a3 = v7;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError && v7 )
      CloseThreadpool(v7);
  }
  return LastError;
}

```

## disassembly

```asm
0x14003b698  mov     [rsp+arg_0], rbx
0x14003b69d  mov     [rsp+arg_8], rsi
0x14003b6a2  mov     [rsp+arg_10], rdi
0x14003b6a7  push    r14
0x14003b6a9  sub     rsp, 20h
0x14003b6ad  xor     edi, edi
0x14003b6af  xor     ecx, ecx; reserved
0x14003b6b1  and     [r8], rdi
0x14003b6b4  mov     r14, r8
0x14003b6b7  mov     esi, edx
0x14003b6b9  call    cs:__imp_CreateThreadpool
0x14003b6c0  nop     dword ptr [rax+rax+00h]
0x14003b6c5  mov     rbx, rax
0x14003b6c8  test    rax, rax
0x14003b6cb  jz      short loc_14003B6E3
0x14003b6cd  lea     edx, [rdi+2]; cthrdMic
0x14003b6d0  mov     rcx, rax; ptpp
0x14003b6d3  call    cs:__imp_SetThreadpoolThreadMinimum
0x14003b6da  nop     dword ptr [rax+rax+00h]
0x14003b6df  test    eax, eax
0x14003b6e1  jnz     short loc_14003B70B
0x14003b6e3  call    cs:__imp_GetLastError
0x14003b6ea  nop     dword ptr [rax+rax+00h]
0x14003b6ef  mov     edi, eax
0x14003b6f1  test    eax, eax
0x14003b6f3  jz      short loc_14003B723
0x14003b6f5  test    rbx, rbx
0x14003b6f8  jz      short loc_14003B723
0x14003b6fa  mov     rcx, rbx; ptpp
0x14003b6fd  call    cs:__imp_CloseThreadpool
0x14003b704  nop     dword ptr [rax+rax+00h]
0x14003b709  jmp     short loc_14003B723
0x14003b70b  test    esi, esi
0x14003b70d  jz      short loc_14003B720
0x14003b70f  mov     edx, esi; cthrdMost
0x14003b711  mov     rcx, rbx; ptpp
0x14003b714  call    cs:__imp_SetThreadpoolThreadMaximum
0x14003b71b  nop     dword ptr [rax+rax+00h]
0x14003b720  mov     [r14], rbx
0x14003b723  mov     rbx, [rsp+28h+arg_0]
0x14003b728  mov     eax, edi
0x14003b72a  mov     rdi, [rsp+28h+arg_10]
0x14003b72f  mov     rsi, [rsp+28h+arg_8]
0x14003b734  add     rsp, 20h
0x14003b738  pop     r14
0x14003b73a  retn
```
