# NMP_CreatePipeInstance(NMP_ADDRESS *,int)

- ea: `0x18005fe3c`
- end: `0x180060043`
- name: `?NMP_CreatePipeInstance@@YAJPEAUNMP_ADDRESS@@H@Z`
- size: `519`
- prototype: `__int64 __fastcall(struct NMP_ADDRESS *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18005fd90`
- `0x1800847b0`

## callees

- `0x180021e70`
- `0x180022870`
- `0x18004cc10`
- `0x18005da9c`
- `0x18005fe3c`
- `0x180060e18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ffc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ffc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ffda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ffda`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x18005ff6c`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x18005ff6c`

## pseudocode

```c
__int64 __fastcall NMP_CreatePipeInstance(struct NMP_ADDRESS *a1)
{
  __int64 i; // rdx
  __int64 v3; // r8
  __int64 result; // rax
  _QWORD *v5; // rax
  __int64 v6; // rax
  void *v7; // rcx
  DWORD LastError; // ebx
  void *v9; // rcx
  DWORD v10; // ebx
  DWORD v11; // ebx
  DWORD v12; // ebx
  DWORD v13; // ebx
  DWORD v14; // ebx
  DWORD v15; // ebx
  DWORD v16; // ebx
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-28h] BYREF

  SecurityAttributes.lpSecurityDescriptor = (LPVOID)*((_QWORD *)a1 + 34);
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  CSpinLock::Lock((struct NMP_ADDRESS *)((char *)a1 + 208));
  for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 56); i = (unsigned int)(i + 1) )
  {
    v3 = *(_QWORD *)(*((_QWORD *)a1 + 27) + 8 * i);
    if ( v3 )
      goto LABEL_6;
  }
  LODWORD(i) = 0;
  v3 = 0;
LABEL_6:
  *((_QWORD *)a1 + 25) = v3;
  if ( v3 )
  {
    SIMPLE_DICT::Delete((struct NMP_ADDRESS *)((char *)a1 + 216), i);
    result = 3221360672LL;
    _InterlockedExchange(
      (volatile __int32 *)a1 + 52,
      ((*((_DWORD *)a1 + 52) - 0x10000000) & 0xF0000000) != 0 ? *((_DWORD *)a1 + 52) - 0x10000000 : 0);
    return result;
  }
  _InterlockedExchange(
    (volatile __int32 *)a1 + 52,
    ((*((_DWORD *)a1 + 52) - 0x10000000) & 0xF0000000) != 0 ? *((_DWORD *)a1 + 52) - 0x10000000 : 0);
  v5 = AllocWrapper(0x40u);
  *((_QWORD *)a1 + 25) = v5;
  if ( !v5 )
    return 14;
  *v5 = a1;
  *(_QWORD *)(*((_QWORD *)a1 + 25) + 48LL) = 0;
  *(_QWORD *)(*((_QWORD *)a1 + 25) + 56LL) = CreateNamedPipeW(
                                               *((LPCWSTR *)a1 + 35),
                                               0x40000003u,
                                               *((_DWORD *)a1 + 72) != 0 ? 14 : 6,
                                               0xFFu,
                                               0x800u,
                                               0x800u,
                                               0,
                                               &SecurityAttributes);
  v6 = *((_QWORD *)a1 + 25);
  v7 = *(void **)(v6 + 56);
  if ( v7 == (void *)-1LL )
  {
    LastError = GetLastError();
LABEL_14:
    v9 = *(void **)(*((_QWORD *)a1 + 25) + 56LL);
    if ( v9 != (void *)-1LL )
      CloseHandle(v9);
    FreeWrapper(*((void **)a1 + 25));
    *((_QWORD *)a1 + 25) = 0;
    v10 = LastError - 2;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        v12 = v11 - 2;
        if ( !v12 )
          return 1740;
        v13 = v12 - 3;
        if ( !v13 )
          return 14;
        v14 = v13 - 6;
        if ( !v14 )
          return 14;
        v15 = v14 - 109;
        if ( v15 )
        {
          v16 = v15 - 1327;
          if ( v16 && v16 != 366 )
            return 1766;
          return 14;
        }
      }
    }
    return 1706;
  }
  result = RPC_THREAD_POOL::CreateIoEx(
             v7,
             (PTP_WIN32_IO_CALLBACK)CO_NmpThreadPoolCallback,
             0,
             1,
             (struct RPC_THREAD_POOL_IO **)(v6 + 48));
  LastError = result;
  if ( (_DWORD)result )
    goto LABEL_14;
  return result;
}

```

## disassembly

```asm
0x18005fe3c  mov     r11, rsp
0x18005fe3f  mov     [r11+8], rbx
0x18005fe43  push    rdi
0x18005fe44  sub     rsp, 60h
0x18005fe48  mov     rax, [rcx+110h]
0x18005fe4f  mov     rdi, rcx
0x18005fe52  add     rcx, 0D0h; this
0x18005fe59  mov     [r11-20h], rax
0x18005fe5d  mov     qword ptr [r11-28h], 18h
0x18005fe65  mov     qword ptr [r11-18h], 0
0x18005fe6d  call    ?Lock@CSpinLock@@QEAAXXZ; CSpinLock::Lock(void)
0x18005fe72  xor     edx, edx
0x18005fe74  lea     r9, [rdi+0D8h]
0x18005fe7b  cmp     edx, [r9+8]
0x18005fe7f  jnb     short loc_18005FE91
0x18005fe81  mov     rax, [r9]
0x18005fe84  mov     r8, [rax+rdx*8]
0x18005fe88  test    r8, r8
0x18005fe8b  jnz     short loc_18005FE96
0x18005fe8d  inc     edx
0x18005fe8f  jmp     short loc_18005FE7B
0x18005fe91  xor     edx, edx; unsigned int
0x18005fe93  xor     r8d, r8d
0x18005fe96  mov     [rdi+0C8h], r8
0x18005fe9d  test    r8, r8
0x18005fea0  jz      short loc_18005FEDD
0x18005fea2  mov     rcx, r9; this
0x18005fea5  call    ?Delete@SIMPLE_DICT@@QEAAPEAXI@Z; SIMPLE_DICT::Delete(uint)
0x18005feaa  mov     r9d, [rdi+0D0h]
0x18005feb1  add     r9d, 0F0000000h
0x18005feb8  mov     eax, r9d
0x18005febb  and     eax, 0F0000000h
0x18005fec0  neg     eax
0x18005fec2  mov     eax, 0C0021020h
0x18005fec7  sbb     ecx, ecx
0x18005fec9  and     ecx, r9d
0x18005fecc  xchg    ecx, [rdi+0D0h]
0x18005fed2  mov     rbx, [rsp+68h+arg_0]
0x18005fed7  add     rsp, 60h
0x18005fedb  pop     rdi
0x18005fedc  retn
0x18005fedd  mov     edx, [rdi+0D0h]
0x18005fee3  add     edx, 0F0000000h
0x18005fee9  mov     eax, edx
0x18005feeb  and     eax, 0F0000000h
0x18005fef0  neg     eax
0x18005fef2  sbb     ecx, ecx
0x18005fef4  and     ecx, edx
0x18005fef6  xchg    ecx, [rdi+0D0h]
0x18005fefc  mov     ecx, 40h ; '@'; dwBytes
0x18005ff01  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18005ff06  mov     [rdi+0C8h], rax
0x18005ff0d  test    rax, rax
0x18005ff10  jz      loc_18005FFB7
0x18005ff16  mov     [rax], rdi
0x18005ff19  mov     edx, 40000003h; dwOpenMode
0x18005ff1e  mov     rax, [rdi+0C8h]
0x18005ff25  mov     r9d, 0FFh; nMaxInstances
0x18005ff2b  mov     qword ptr [rax+30h], 0
0x18005ff33  mov     eax, [rdi+120h]
0x18005ff39  mov     rcx, [rdi+118h]; lpName
0x18005ff40  neg     eax
0x18005ff42  lea     rax, [rsp+68h+SecurityAttributes]
0x18005ff47  mov     [rsp+68h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18005ff4c  sbb     r8d, r8d
0x18005ff4f  mov     eax, 800h
0x18005ff54  mov     [rsp+68h+nDefaultTimeOut], 0; nDefaultTimeOut
0x18005ff5c  and     r8d, 8
0x18005ff60  mov     [rsp+68h+nInBufferSize], eax; nInBufferSize
0x18005ff64  add     r8d, 6; dwPipeMode
0x18005ff68  mov     [rsp+68h+nOutBufferSize], eax; nOutBufferSize
0x18005ff6c  call    cs:__imp_CreateNamedPipeW
0x18005ff72  mov     rcx, [rdi+0C8h]
0x18005ff79  mov     [rcx+38h], rax
0x18005ff7d  mov     rax, [rdi+0C8h]
0x18005ff84  mov     rcx, [rax+38h]; fl
0x18005ff88  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005ff8c  jz      short loc_18005FFC1
0x18005ff8e  add     rax, 30h ; '0'
0x18005ff92  lea     rdx, ?CO_NmpThreadPoolCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x18005ff99  mov     r9d, 1; int
0x18005ff9f  mov     qword ptr [rsp+68h+nOutBufferSize], rax; struct RPC_THREAD_POOL_IO **
0x18005ffa4  xor     r8d, r8d; pv
0x18005ffa7  call    ?CreateIoEx@RPC_THREAD_POOL@@SAJPEAXP6AXPEAU_TP_CALLBACK_INSTANCE@@00K_KPEAU_TP_IO@@@Z0HPEAPEAVRPC_THREAD_POOL_IO@@@Z; RPC_THREAD_POOL::CreateIoEx(void *,void (*)(_TP_CALLBACK_INSTANCE *,void *,void *,ulong,unsigned __int64,_TP_IO *),void *,int,RPC_THREAD_POOL_IO * *)
0x18005ffac  mov     ebx, eax
0x18005ffae  test    eax, eax
0x18005ffb0  jnz     short loc_18005FFC9
0x18005ffb2  jmp     loc_18005FED2
0x18005ffb7  mov     eax, 0Eh
0x18005ffbc  jmp     loc_18005FED2
0x18005ffc1  call    cs:__imp_GetLastError
0x18005ffc7  mov     ebx, eax
0x18005ffc9  mov     rax, [rdi+0C8h]
0x18005ffd0  mov     rcx, [rax+38h]; hObject
0x18005ffd4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005ffd8  jz      short loc_18005FFE0
0x18005ffda  call    cs:__imp_CloseHandle
0x18005ffe0  mov     rcx, [rdi+0C8h]; lpMem
0x18005ffe7  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18005ffec  mov     qword ptr [rdi+0C8h], 0
0x18005fff7  sub     ebx, 2
0x18005fffa  jz      short loc_180060039
0x18005fffc  sub     ebx, 1
0x18005ffff  jz      short loc_180060039
0x180060001  sub     ebx, 2
0x180060004  jz      short loc_18006002F
0x180060006  sub     ebx, 3
0x180060009  jz      short loc_18005FFB7
0x18006000b  sub     ebx, 6
0x18006000e  jz      short loc_18005FFB7
0x180060010  sub     ebx, 6Dh ; 'm'
0x180060013  jz      short loc_180060039
0x180060015  sub     ebx, 52Fh
0x18006001b  jz      short loc_18005FFB7
0x18006001d  cmp     ebx, 16Eh
0x180060023  jz      short loc_18005FFB7
0x180060025  mov     eax, 6E6h
0x18006002a  jmp     loc_18005FED2
0x18006002f  mov     eax, 6CCh
0x180060034  jmp     loc_18005FED2
0x180060039  mov     eax, 6AAh
0x18006003e  jmp     loc_18005FED2
```
