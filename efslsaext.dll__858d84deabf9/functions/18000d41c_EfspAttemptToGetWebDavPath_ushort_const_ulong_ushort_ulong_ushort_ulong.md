# EfspAttemptToGetWebDavPath(ushort const *,ulong,ushort * *,ulong,ushort * *,ulong)

- ea: `0x18000d41c`
- end: `0x18000d6f7`
- name: `?EfspAttemptToGetWebDavPath@@YAKPEBGKPEAPEAGK1K@Z`
- size: `731`
- prototype: `unsigned int __usercall@<eax>(const unsigned __int16 *@<rcx>, unsigned int@<edx>, unsigned __int16 **@<r8>, unsigned int@<r9d>, unsigned __int16 **, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d700`

## callees

- `0x180005c94`
- `0x180005d58`
- `0x18000d41c`
- `0x18001200e`
- `0x180012040`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000d50e`
- `ntdll!RtlFreeHeap` at `0x18000d60d`
- `ntdll!RtlFreeHeap` at `0x18000d6aa`
- `ntdll!RtlFreeHeap` at `0x18000d6c7`
- `ntdll!RtlFreeHeap` at `0x18000d50e`
- `ntdll!RtlFreeHeap` at `0x18000d60d`
- `ntdll!RtlFreeHeap` at `0x18000d6aa`
- `ntdll!RtlFreeHeap` at `0x18000d6c7`
- `ntdll!RtlAllocateHeap` at `0x18000d49f`
- `ntdll!RtlAllocateHeap` at `0x18000d528`
- `ntdll!RtlAllocateHeap` at `0x18000d5a2`
- `ntdll!RtlAllocateHeap` at `0x18000d63d`
- `ntdll!RtlAllocateHeap` at `0x18000d49f`
- `ntdll!RtlAllocateHeap` at `0x18000d528`
- `ntdll!RtlAllocateHeap` at `0x18000d5a2`
- `ntdll!RtlAllocateHeap` at `0x18000d63d`
- `MPR!WNetGetProviderNameW` at `0x18000d576`
- `MPR!WNetGetProviderNameW` at `0x18000d5c5`
- `MPR!WNetGetProviderNameW` at `0x18000d576`
- `MPR!WNetGetProviderNameW` at `0x18000d5c5`
- `MPR!WNetGetResourceInformationW` at `0x18000d4ef`
- `MPR!WNetGetResourceInformationW` at `0x18000d54c`
- `MPR!WNetGetResourceInformationW` at `0x18000d4ef`
- `MPR!WNetGetResourceInformationW` at `0x18000d54c`

## pseudocode

```c
__int64 __fastcall EfspAttemptToGetWebDavPath(
        const unsigned __int16 *a1,
        int a2,
        unsigned __int16 **a3,
        __int64 a4,
        unsigned __int16 **a5,
        unsigned int a6)
{
  _QWORD *Heap; // rax
  _QWORD *v10; // rsi
  unsigned int v11; // ebx
  WCHAR *v12; // rdi
  DWORD ResourceInformationW; // eax
  _QWORD *v14; // rax
  DWORD ProviderNameW; // eax
  WCHAR *v16; // rax
  WCHAR *v17; // rax
  int v18; // r8d
  int v19; // ecx
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // r14
  unsigned __int64 v22; // rax
  unsigned __int16 *v23; // rax
  DWORD cbBuffer; // [rsp+20h] [rbp-E0h] BYREF
  DWORD BufferSize; // [rsp+24h] [rbp-DCh] BYREF
  LPWSTR lpSystem; // [rsp+28h] [rbp-D8h] BYREF
  _NETRESOURCEW NetResource; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR ProviderName[264]; // [rsp+60h] [rbp-A0h] BYREF

  lpSystem = 0;
  cbBuffer = 1024;
  memset(&NetResource, 0, sizeof(NetResource));
  memset_0(ProviderName, 0, sizeof(ProviderName));
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x400u);
  v10 = Heap;
  if ( !Heap )
    return 8;
  v12 = 0;
  NetResource.dwUsage = 0;
  NetResource.lpLocalName = 0;
  NetResource.dwScope = 1;
  *(_QWORD *)&NetResource.dwType = 1;
  NetResource.lpRemoteName = *a3;
  *(_OWORD *)&NetResource.lpComment = 0;
  ResourceInformationW = WNetGetResourceInformationW(&NetResource, Heap, &cbBuffer, &lpSystem);
  if ( ResourceInformationW == 234 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
    v14 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, cbBuffer);
    v10 = v14;
    if ( !v14 )
      goto LABEL_20;
    ResourceInformationW = WNetGetResourceInformationW(&NetResource, v14, &cbBuffer, &lpSystem);
  }
  if ( ResourceInformationW )
    goto LABEL_20;
  BufferSize = 264;
  v12 = ProviderName;
  ProviderNameW = WNetGetProviderNameW(0x2E0000u, ProviderName, &BufferSize);
  if ( !ProviderNameW )
  {
LABEL_12:
    v17 = v12;
    do
    {
      v18 = *(WCHAR *)((char *)v17 + v10[5] - (_QWORD)v12);
      v19 = *v17 - v18;
      if ( v19 )
        break;
      ++v17;
    }
    while ( v18 );
    if ( !v19 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *a3);
      v20 = (unsigned int)(a2 + 3);
      v21 = v20;
      v22 = 2 * v20;
      if ( v22 > 0xFFFFFFFF )
      {
        v11 = 534;
        goto LABEL_21;
      }
      v23 = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)v22);
      *a3 = v23;
      if ( !v23 )
      {
        v11 = 8;
LABEL_21:
        if ( v12 && v12 != ProviderName )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
        goto LABEL_24;
      }
      StringCchCopyW(*a5, a6, L".");
      **a3 = 1;
      (*a3)[1] = 0;
      StringCchCatW(*a3, v21, a1);
    }
LABEL_20:
    v11 = 0;
    goto LABEL_21;
  }
  if ( ProviderNameW != 234 )
    goto LABEL_20;
  v16 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2LL * BufferSize);
  v12 = v16;
  if ( v16 )
  {
    if ( WNetGetProviderNameW(0x2E0000u, v16, &BufferSize) )
      goto LABEL_20;
    goto LABEL_12;
  }
  v11 = 8;
LABEL_24:
  if ( v10 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  return v11;
}

```

## disassembly

```asm
0x18000d41c  push    rbp
0x18000d41e  push    rbx
0x18000d41f  push    rsi
0x18000d420  push    rdi
0x18000d421  push    r12
0x18000d423  push    r14
0x18000d425  push    r15
0x18000d427  lea     rbp, [rsp-180h]
0x18000d42f  sub     rsp, 280h
0x18000d436  mov     rax, cs:__security_cookie
0x18000d43d  xor     rax, rsp
0x18000d440  mov     [rbp+1B0h+var_40], rax
0x18000d447  mov     r12, [rbp+1B0h+arg_20]
0x18000d44e  xorps   xmm0, xmm0
0x18000d451  mov     rbx, r8
0x18000d454  mov     [rsp+2B0h+lpSystem], 0
0x18000d45d  mov     r14d, edx
0x18000d460  mov     r15, rcx
0x18000d463  mov     edi, 400h
0x18000d468  lea     rcx, [rsp+2B0h+ProviderName]; void *
0x18000d46d  xor     edx, edx; Val
0x18000d46f  mov     [rsp+2B0h+cbBuffer], edi
0x18000d473  mov     r8d, 210h; Size
0x18000d479  movups  xmmword ptr [rsp+2B0h+NetResource.dwScope], xmm0
0x18000d47e  movups  xmmword ptr [rsp+2B0h+NetResource.lpLocalName], xmm0
0x18000d483  movups  xmmword ptr [rsp+2B0h+NetResource.lpComment], xmm0
0x18000d488  call    memset_0
0x18000d48d  mov     rcx, gs:60h
0x18000d496  mov     r8d, edi; Size
0x18000d499  xor     edx, edx; Flags
0x18000d49b  mov     rcx, [rcx+30h]; HeapHandle
0x18000d49f  call    cs:__imp_RtlAllocateHeap
0x18000d4a5  mov     rsi, rax
0x18000d4a8  test    rax, rax
0x18000d4ab  jnz     short loc_18000D4B5
0x18000d4ad  lea     ebx, [rax+8]
0x18000d4b0  jmp     loc_18000D6CD
0x18000d4b5  xor     edi, edi
0x18000d4b7  lea     r9, [rsp+2B0h+lpSystem]; lplpSystem
0x18000d4bc  xorps   xmm0, xmm0
0x18000d4bf  mov     [rsp+2B0h+NetResource.dwUsage], edi
0x18000d4c3  lea     r8, [rsp+2B0h+cbBuffer]; lpcbBuffer
0x18000d4c8  mov     [rsp+2B0h+NetResource.lpLocalName], rdi
0x18000d4cd  mov     rdx, rsi; lpBuffer
0x18000d4d0  lea     rcx, [rsp+2B0h+NetResource]; lpNetResource
0x18000d4d5  lea     eax, [rdi+1]
0x18000d4d8  mov     [rsp+2B0h+NetResource.dwScope], eax
0x18000d4dc  mov     qword ptr [rsp+2B0h+NetResource.dwType], rax
0x18000d4e1  mov     rax, [rbx]
0x18000d4e4  mov     [rsp+2B0h+NetResource.lpRemoteName], rax
0x18000d4e9  movdqu  xmmword ptr [rsp+2B0h+NetResource.lpComment], xmm0
0x18000d4ef  call    cs:__imp_WNetGetResourceInformationW
0x18000d4f5  cmp     eax, 0EAh
0x18000d4fa  jnz     short loc_18000D552
0x18000d4fc  mov     rcx, gs:60h
0x18000d505  mov     r8, rsi; P
0x18000d508  xor     edx, edx; Flags
0x18000d50a  mov     rcx, [rcx+30h]; HeapHandle
0x18000d50e  call    cs:__imp_RtlFreeHeap
0x18000d514  mov     rcx, gs:60h
0x18000d51d  xor     edx, edx; Flags
0x18000d51f  mov     r8d, [rsp+2B0h+cbBuffer]; Size
0x18000d524  mov     rcx, [rcx+30h]; HeapHandle
0x18000d528  call    cs:__imp_RtlAllocateHeap
0x18000d52e  mov     rsi, rax
0x18000d531  test    rax, rax
0x18000d534  jz      loc_18000D687
0x18000d53a  lea     r9, [rsp+2B0h+lpSystem]; lplpSystem
0x18000d53f  mov     rdx, rax; lpBuffer
0x18000d542  lea     r8, [rsp+2B0h+cbBuffer]; lpcbBuffer
0x18000d547  lea     rcx, [rsp+2B0h+NetResource]; lpNetResource
0x18000d54c  call    cs:__imp_WNetGetResourceInformationW
0x18000d552  test    eax, eax
0x18000d554  jnz     loc_18000D687
0x18000d55a  lea     r8, [rsp+2B0h+BufferSize]; lpBufferSize
0x18000d55f  mov     [rsp+2B0h+BufferSize], 108h
0x18000d567  lea     rdx, [rsp+2B0h+ProviderName]; lpProviderName
0x18000d56c  mov     ecx, 2E0000h; dwNetType
0x18000d571  lea     rdi, [rsp+2B0h+ProviderName]
0x18000d576  call    cs:__imp_WNetGetProviderNameW
0x18000d57c  test    eax, eax
0x18000d57e  jz      short loc_18000D5D3
0x18000d580  cmp     eax, 0EAh
0x18000d585  jnz     loc_18000D687
0x18000d58b  mov     rcx, gs:60h
0x18000d594  xor     edx, edx; Flags
0x18000d596  mov     r8d, [rsp+2B0h+BufferSize]
0x18000d59b  add     r8, r8; Size
0x18000d59e  mov     rcx, [rcx+30h]; HeapHandle
0x18000d5a2  call    cs:__imp_RtlAllocateHeap
0x18000d5a8  mov     rdi, rax
0x18000d5ab  test    rax, rax
0x18000d5ae  jnz     short loc_18000D5B8
0x18000d5b0  lea     ebx, [rax+8]
0x18000d5b3  jmp     loc_18000D6B0
0x18000d5b8  lea     r8, [rsp+2B0h+BufferSize]; lpBufferSize
0x18000d5bd  mov     rdx, rax; lpProviderName
0x18000d5c0  mov     ecx, 2E0000h; dwNetType
0x18000d5c5  call    cs:__imp_WNetGetProviderNameW
0x18000d5cb  test    eax, eax
0x18000d5cd  jnz     loc_18000D687
0x18000d5d3  mov     rdx, [rsi+28h]
0x18000d5d7  mov     rax, rdi
0x18000d5da  sub     rdx, rdi
0x18000d5dd  movzx   ecx, word ptr [rax]
0x18000d5e0  movzx   r8d, word ptr [rax+rdx]
0x18000d5e5  sub     ecx, r8d
0x18000d5e8  jnz     short loc_18000D5F3
0x18000d5ea  add     rax, 2
0x18000d5ee  test    r8d, r8d
0x18000d5f1  jnz     short loc_18000D5DD
0x18000d5f3  test    ecx, ecx
0x18000d5f5  jnz     loc_18000D687
0x18000d5fb  mov     rcx, gs:60h
0x18000d604  xor     edx, edx; Flags
0x18000d606  mov     r8, [rbx]; P
0x18000d609  mov     rcx, [rcx+30h]; HeapHandle
0x18000d60d  call    cs:__imp_RtlFreeHeap
0x18000d613  lea     eax, [r14+3]
0x18000d617  mov     ecx, 0FFFFFFFFh
0x18000d61c  mov     r14d, eax
0x18000d61f  add     rax, rax
0x18000d622  cmp     rax, rcx
0x18000d625  ja      loc_18000D6F0
0x18000d62b  mov     rcx, gs:60h
0x18000d634  xor     edx, edx; Flags
0x18000d636  mov     r8d, eax; Size
0x18000d639  mov     rcx, [rcx+30h]; HeapHandle
0x18000d63d  call    cs:__imp_RtlAllocateHeap
0x18000d643  mov     [rbx], rax
0x18000d646  test    rax, rax
0x18000d649  jnz     short loc_18000D650
0x18000d64b  lea     ebx, [rax+8]
0x18000d64e  jmp     short loc_18000D689
0x18000d650  mov     edx, [rbp+1B0h+arg_28]; unsigned __int64
0x18000d656  lea     r8, asc_180018748; "."
0x18000d65d  mov     rcx, [r12]; unsigned __int16 *
0x18000d661  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d666  mov     r11, [rbx]
0x18000d669  xor     eax, eax
0x18000d66b  mov     r8, r15; unsigned __int16 *
0x18000d66e  mov     rdx, r14; unsigned __int64
0x18000d671  mov     word ptr [r11], 1
0x18000d677  mov     r9, [rbx]
0x18000d67a  mov     [r9+2], ax
0x18000d67f  mov     rcx, [rbx]; unsigned __int16 *
0x18000d682  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d687  xor     ebx, ebx
0x18000d689  test    rdi, rdi
0x18000d68c  jz      short loc_18000D6B0
0x18000d68e  lea     rax, [rsp+2B0h+ProviderName]
0x18000d693  cmp     rdi, rax
0x18000d696  jz      short loc_18000D6B0
0x18000d698  mov     rcx, gs:60h
0x18000d6a1  mov     r8, rdi; P
0x18000d6a4  xor     edx, edx; Flags
0x18000d6a6  mov     rcx, [rcx+30h]; HeapHandle
0x18000d6aa  call    cs:__imp_RtlFreeHeap
0x18000d6b0  test    rsi, rsi
0x18000d6b3  jz      short loc_18000D6CD
0x18000d6b5  mov     rcx, gs:60h
0x18000d6be  mov     r8, rsi; P
0x18000d6c1  xor     edx, edx; Flags
0x18000d6c3  mov     rcx, [rcx+30h]; HeapHandle
0x18000d6c7  call    cs:__imp_RtlFreeHeap
0x18000d6cd  mov     eax, ebx
0x18000d6cf  mov     rcx, [rbp+1B0h+var_40]
0x18000d6d6  xor     rcx, rsp; StackCookie
0x18000d6d9  call    __security_check_cookie
0x18000d6de  add     rsp, 280h
0x18000d6e5  pop     r15
0x18000d6e7  pop     r14
0x18000d6e9  pop     r12
0x18000d6eb  pop     rdi
0x18000d6ec  pop     rsi
0x18000d6ed  pop     rbx
0x18000d6ee  pop     rbp
0x18000d6ef  retn
0x18000d6f0  mov     ebx, 216h
0x18000d6f5  jmp     short loc_18000D689
```
