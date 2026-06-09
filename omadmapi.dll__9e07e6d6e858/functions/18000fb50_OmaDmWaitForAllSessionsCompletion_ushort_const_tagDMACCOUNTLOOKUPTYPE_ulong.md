# OmaDmWaitForAllSessionsCompletion(ushort const *,tagDMACCOUNTLOOKUPTYPE,ulong)

- ea: `0x18000fb50`
- end: `0x18000fc2c`
- name: `?OmaDmWaitForAllSessionsCompletion@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@K@Z`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016160`

## callees

- `0x18000fb50`
- `0x18000fc34`
- `0x180016c50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fbeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fc02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fbeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fc02`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fb7b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fbb1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fb7b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fbb1`

## pseudocode

```c
__int64 __fastcall OmaDmWaitForAllSessionsCompletion(unsigned __int16 *a1, int a2, DWORD a3)
{
  DWORD TickCount; // r15d
  int v7; // eax
  LPCWSTR *v8; // r14
  unsigned int v9; // ebx
  __int64 v10; // rbx
  DWORD v11; // eax
  __int64 i; // rdi
  HLOCAL hMem; // [rsp+20h] [rbp-28h] BYREF
  DWORD v15; // [rsp+68h] [rbp+20h] BYREF

  hMem = 0;
  v15 = 0;
  TickCount = GetTickCount();
  v7 = OmaDmEnumerateInitiationInfo(a1, a2, (HLOCAL **)&hMem, &v15);
  v8 = (LPCWSTR *)hMem;
  v9 = v7;
  if ( v7 >= 0 )
  {
    v10 = 0;
    if ( v15 )
    {
      while ( 1 )
      {
        v11 = GetTickCount() - TickCount;
        if ( v11 >= a3 || !OmaDmWaitForSingleSessionCompletion(v8[v10], a3 - v11) )
          break;
        v10 = (unsigned int)(v10 + 1);
        if ( (unsigned int)v10 >= v15 )
          goto LABEL_6;
      }
      v9 = -2147483638;
    }
    else
    {
LABEL_6:
      v9 = 0;
    }
  }
  for ( i = 0; (unsigned int)i < v15; i = (unsigned int)(i + 1) )
    LocalFree((HLOCAL)v8[i]);
  LocalFree(v8);
  return v9;
}

```

## disassembly

```asm
0x18000fb50  mov     rax, rsp
0x18000fb53  mov     [rax+8], rbx
0x18000fb57  mov     [rax+10h], rbp
0x18000fb5b  push    rdi
0x18000fb5c  push    r14
0x18000fb5e  push    r15
0x18000fb60  sub     rsp, 30h
0x18000fb64  mov     ebp, r8d
0x18000fb67  mov     qword ptr [rax-28h], 0
0x18000fb6f  mov     ebx, edx
0x18000fb71  mov     dword ptr [rax+20h], 0
0x18000fb78  mov     rdi, rcx
0x18000fb7b  call    cs:__imp_GetTickCount
0x18000fb82  nop     dword ptr [rax+rax+00h]
0x18000fb87  lea     r9, [rsp+48h+arg_18]
0x18000fb8c  mov     edx, ebx
0x18000fb8e  lea     r8, [rsp+48h+hMem]
0x18000fb93  mov     rcx, rdi
0x18000fb96  mov     r15d, eax
0x18000fb99  call    OmaDmEnumerateInitiationInfo
0x18000fb9e  mov     r14, [rsp+48h+hMem]
0x18000fba3  mov     ebx, eax
0x18000fba5  test    eax, eax
0x18000fba7  js      short loc_18000FBDF
0x18000fba9  xor     ebx, ebx
0x18000fbab  cmp     [rsp+48h+arg_18], ebx
0x18000fbaf  jbe     short loc_18000FBDD
0x18000fbb1  call    cs:__imp_GetTickCount
0x18000fbb8  nop     dword ptr [rax+rax+00h]
0x18000fbbd  sub     eax, r15d
0x18000fbc0  cmp     eax, ebp
0x18000fbc2  jnb     short loc_18000FC25
0x18000fbc4  mov     rcx, [r14+rbx*8]; lpSubKey
0x18000fbc8  mov     edx, ebp
0x18000fbca  sub     edx, eax; unsigned int
0x18000fbcc  call    ?OmaDmWaitForSingleSessionCompletion@@YAHPEBGK@Z; OmaDmWaitForSingleSessionCompletion(ushort const *,ulong)
0x18000fbd1  test    eax, eax
0x18000fbd3  jz      short loc_18000FC25
0x18000fbd5  inc     ebx
0x18000fbd7  cmp     ebx, [rsp+48h+arg_18]
0x18000fbdb  jb      short loc_18000FBB1
0x18000fbdd  xor     ebx, ebx
0x18000fbdf  xor     edi, edi
0x18000fbe1  cmp     [rsp+48h+arg_18], edi
0x18000fbe5  jbe     short loc_18000FBFF
0x18000fbe7  mov     rcx, [r14+rdi*8]; hMem
0x18000fbeb  call    cs:__imp_LocalFree
0x18000fbf2  nop     dword ptr [rax+rax+00h]
0x18000fbf7  inc     edi
0x18000fbf9  cmp     edi, [rsp+48h+arg_18]
0x18000fbfd  jb      short loc_18000FBE7
0x18000fbff  mov     rcx, r14; hMem
0x18000fc02  call    cs:__imp_LocalFree
0x18000fc09  nop     dword ptr [rax+rax+00h]
0x18000fc0e  mov     rbp, [rsp+48h+arg_8]
0x18000fc13  mov     eax, ebx
0x18000fc15  mov     rbx, [rsp+48h+arg_0]
0x18000fc1a  add     rsp, 30h
0x18000fc1e  pop     r15
0x18000fc20  pop     r14
0x18000fc22  pop     rdi
0x18000fc23  retn
0x18000fc25  mov     ebx, 8000000Ah
0x18000fc2a  jmp     short loc_18000FBDF
```
