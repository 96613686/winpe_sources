# NfsGetDiskResourceDb

- ea: `0x18002aca8`
- end: `0x18002ad96`
- name: `NfsGetDiskResourceDb`
- size: `238`
- prototype: `__int64 __fastcall(HCLUSTER hCluster, LPVOID lpInBuffer)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001f2d8`

## callees

- `0x18002aca8`

## import_xrefs

- `msvcrt!wcstok` at `0x18002ad5b`
- `msvcrt!wcstok` at `0x18002ad5b`
- `KERNEL32!GetLastError` at `0x18002ad75`
- `KERNEL32!GetLastError` at `0x18002ad75`
- `KERNEL32!LocalFree` at `0x18002acf3`
- `KERNEL32!LocalFree` at `0x18002acf3`
- `KERNEL32!LocalAlloc` at `0x18002ad05`
- `KERNEL32!LocalAlloc` at `0x18002ad05`
- `CLUSAPI!OpenClusterResource` at `0x18002ad67`
- `CLUSAPI!OpenClusterResource` at `0x18002ad67`
- `CLUSAPI!ClusterControl` at `0x18002ad3e`
- `CLUSAPI!ClusterControl` at `0x18002ad3e`

## pseudocode

```c
__int64 __fastcall NfsGetDiskResourceDb(HCLUSTER hCluster, _WORD *lpInBuffer, HRESOURCE *a3)
{
  HLOCAL lpOutBuffer; // rdi
  __int64 v4; // rax
  DWORD nInBufferSize; // r14d
  DWORD v9; // eax
  wchar_t **v10; // r8
  DWORD v11; // ebx
  wchar_t *v12; // rax
  HRESOURCE v13; // rax
  DWORD BytesReturned; // [rsp+88h] [rbp+20h] BYREF

  BytesReturned = 2;
  lpOutBuffer = 0;
  v4 = -1;
  do
    ++v4;
  while ( lpInBuffer[v4] );
  nInBufferSize = 2 * v4 + 2;
  do
  {
    if ( lpOutBuffer )
      LocalFree(lpOutBuffer);
    lpOutBuffer = LocalAlloc(0, 2LL * BytesReturned);
    v9 = ClusterControl(hCluster, 0, 0x7000291u, lpInBuffer, nInBufferSize, lpOutBuffer, BytesReturned, &BytesReturned);
    v11 = v9;
  }
  while ( v9 == 234 );
  if ( !v9 )
  {
    v12 = wcstok((wchar_t *)lpOutBuffer, L":", v10);
    v13 = OpenClusterResource(hCluster, v12);
    *a3 = v13;
    if ( !v13 )
      return GetLastError();
  }
  return v11;
}

```

## disassembly

```asm
0x18002aca8  mov     rax, rsp
0x18002acab  mov     [rax+8], rbx
0x18002acaf  mov     [rax+10h], rbp
0x18002acb3  push    rsi
0x18002acb4  push    rdi
0x18002acb5  push    r12
0x18002acb7  push    r14
0x18002acb9  push    r15
0x18002acbb  sub     rsp, 40h
0x18002acbf  xor     r12d, r12d
0x18002acc2  mov     dword ptr [rax+20h], 2
0x18002acc9  mov     edi, r12d
0x18002accc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002acd0  mov     r15, r8
0x18002acd3  mov     rsi, rdx
0x18002acd6  mov     rbp, rcx
0x18002acd9  inc     rax
0x18002acdc  cmp     [rdx+rax*2], r12w
0x18002ace1  jnz     short loc_18002ACD9
0x18002ace3  lea     r14d, ds:2[rax*2]
0x18002aceb  test    rdi, rdi
0x18002acee  jz      short loc_18002ACF9
0x18002acf0  mov     rcx, rdi; hMem
0x18002acf3  call    cs:__imp_LocalFree
0x18002acf9  mov     edx, [rsp+68h+BytesReturned]
0x18002ad00  xor     ecx, ecx; uFlags
0x18002ad02  add     rdx, rdx; uBytes
0x18002ad05  call    cs:__imp_LocalAlloc
0x18002ad0b  mov     r9, rsi; lpInBuffer
0x18002ad0e  xor     edx, edx; hHostNode
0x18002ad10  mov     rdi, rax
0x18002ad13  mov     r8d, 7000291h; dwControlCode
0x18002ad19  lea     rax, [rsp+68h+BytesReturned]
0x18002ad21  mov     rcx, rbp; hCluster
0x18002ad24  mov     [rsp+68h+lpBytesReturned], rax; lpBytesReturned
0x18002ad29  mov     eax, [rsp+68h+BytesReturned]
0x18002ad30  mov     [rsp+68h+nOutBufferSize], eax; nOutBufferSize
0x18002ad34  mov     [rsp+68h+lpOutBuffer], rdi; lpOutBuffer
0x18002ad39  mov     [rsp+68h+nInBufferSize], r14d; nInBufferSize
0x18002ad3e  call    cs:__imp_ClusterControl
0x18002ad44  mov     ebx, eax
0x18002ad46  cmp     eax, 0EAh
0x18002ad4b  jz      short loc_18002ACEB
0x18002ad4d  test    eax, eax
0x18002ad4f  jnz     short loc_18002AD7D
0x18002ad51  lea     rdx, Delimiter; ":"
0x18002ad58  mov     rcx, rdi; String
0x18002ad5b  call    cs:__imp_wcstok
0x18002ad61  mov     rdx, rax; lpszResourceName
0x18002ad64  mov     rcx, rbp; hCluster
0x18002ad67  call    cs:__imp_OpenClusterResource
0x18002ad6d  mov     [r15], rax
0x18002ad70  test    rax, rax
0x18002ad73  jnz     short loc_18002AD7D
0x18002ad75  call    cs:__imp_GetLastError
0x18002ad7b  mov     ebx, eax
0x18002ad7d  mov     rbp, [rsp+68h+arg_8]
0x18002ad82  mov     eax, ebx
0x18002ad84  mov     rbx, [rsp+68h+arg_0]
0x18002ad89  add     rsp, 40h
0x18002ad8d  pop     r15
0x18002ad8f  pop     r14
0x18002ad91  pop     r12
0x18002ad93  pop     rdi
0x18002ad94  pop     rsi
0x18002ad95  retn
```
