# GetUserSid(void *,void * *)

- ea: `0x1800327b0`
- end: `0x180032867`
- name: `?GetUserSid@@YAKPEAXPEAPEAX@Z`
- size: `183`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180030b00`
- `0x1800329b0`

## callees

- `0x1800327b0`
- `0x180032870`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800327d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032833`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800327d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032833`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032841`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032841`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003285f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003285f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032805`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032805`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180032824`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180032824`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800327f8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800327f8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003281b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003281b`

## pseudocode

```c
__int64 __fastcall GetUserSid(HANDLE TokenHandle, void **a2)
{
  unsigned int v4; // edi
  HANDLE ProcessHeap; // rax
  DWORD LengthSid; // ebp
  HLOCAL v7; // rax
  void *v8; // rbx
  HANDLE v9; // rax

  v4 = 8;
  ProcessHeap = GetProcessHeap();
  if ( (int)GetTokenInformation_HeapFree<_SID_AND_ATTRIBUTES>(ProcessHeap, TokenHandle) >= 0 )
  {
    LengthSid = GetLengthSid(MEMORY[0]);
    v7 = LocalAlloc(0x40u, LengthSid);
    v8 = v7;
    if ( v7 )
    {
      CopySid(LengthSid, v7, MEMORY[0]);
      if ( IsValidSid(v8) )
      {
        *a2 = v8;
        v4 = 0;
      }
      else
      {
        LocalFree(v8);
      }
    }
    v9 = GetProcessHeap();
    HeapFree(v9, 0, 0);
  }
  return v4;
}

```

## disassembly

```asm
0x1800327b0  mov     [rsp+arg_0], rbx
0x1800327b5  mov     [rsp+arg_8], rbp
0x1800327ba  push    rsi
0x1800327bb  push    rdi
0x1800327bc  push    r14
0x1800327be  sub     rsp, 20h
0x1800327c2  mov     r14, rdx
0x1800327c5  mov     [rsp+38h+lpMem], 0
0x1800327ce  mov     rbx, rcx
0x1800327d1  mov     edi, 8
0x1800327d6  call    cs:__imp_GetProcessHeap
0x1800327dc  lea     r9, [rsp+38h+lpMem]
0x1800327e1  mov     rdx, rbx; TokenHandle
0x1800327e4  mov     rcx, rax; hHeap
0x1800327e7  call    ??$GetTokenInformation_HeapFree@U_SID_AND_ATTRIBUTES@@@@YAJPEAX0W4_TOKEN_INFORMATION_CLASS@@PEAPEAU_SID_AND_ATTRIBUTES@@@Z; GetTokenInformation_HeapFree<_SID_AND_ATTRIBUTES>(void *,void *,_TOKEN_INFORMATION_CLASS,_SID_AND_ATTRIBUTES * *)
0x1800327ec  test    eax, eax
0x1800327ee  js      short loc_180032847
0x1800327f0  mov     rsi, [rsp+38h+lpMem]
0x1800327f5  mov     rcx, [rsi]; pSid
0x1800327f8  call    cs:__imp_GetLengthSid
0x1800327fe  mov     edx, eax; uBytes
0x180032800  lea     ecx, [rdi+38h]; uFlags
0x180032803  mov     ebp, eax
0x180032805  call    cs:__imp_LocalAlloc
0x18003280b  mov     rbx, rax
0x18003280e  test    rax, rax
0x180032811  jz      short loc_180032833
0x180032813  mov     r8, [rsi]; pSourceSid
0x180032816  mov     rdx, rax; pDestinationSid
0x180032819  mov     ecx, ebp; nDestinationSidLength
0x18003281b  call    cs:__imp_CopySid
0x180032821  mov     rcx, rbx; pSid
0x180032824  call    cs:__imp_IsValidSid
0x18003282a  test    eax, eax
0x18003282c  jz      short loc_18003285C
0x18003282e  mov     [r14], rbx
0x180032831  xor     edi, edi
0x180032833  call    cs:__imp_GetProcessHeap
0x180032839  mov     r8, rsi; lpMem
0x18003283c  xor     edx, edx; dwFlags
0x18003283e  mov     rcx, rax; hHeap
0x180032841  call    cs:__imp_HeapFree
0x180032847  mov     rbx, [rsp+38h+arg_0]
0x18003284c  mov     eax, edi
0x18003284e  mov     rbp, [rsp+38h+arg_8]
0x180032853  add     rsp, 20h
0x180032857  pop     r14
0x180032859  pop     rdi
0x18003285a  pop     rsi
0x18003285b  retn
0x18003285c  mov     rcx, rbx; hMem
0x18003285f  call    cs:__imp_LocalFree
0x180032865  jmp     short loc_180032833
```
