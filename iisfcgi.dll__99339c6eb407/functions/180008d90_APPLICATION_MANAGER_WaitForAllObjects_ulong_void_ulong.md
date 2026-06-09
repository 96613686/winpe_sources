# APPLICATION_MANAGER::WaitForAllObjects(ulong,void * *,ulong)

- ea: `0x180008d90`
- end: `0x180008f20`
- name: `?WaitForAllObjects@APPLICATION_MANAGER@@AEAAXKPEAPEAXK@Z`
- size: `400`
- prototype: `void(APPLICATION_MANAGER *__hidden this, unsigned int, void **, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180008164`

## callees

- `0x180001008`
- `0x180001048`
- `0x180008d90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008ecc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008ecc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ee6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ee6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180008e8d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180008e8d`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180008dbf`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180008eba`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180008dbf`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180008eba`

## pseudocode

```c
void __fastcall APPLICATION_MANAGER::WaitForAllObjects(APPLICATION_MANAGER *this, DWORD a2, void **a3, DWORD a4)
{
  DWORD v7; // eax
  int v8; // edx
  unsigned int v9; // ecx
  DWORD v10; // edi
  int v11; // eax
  HANDLE *v12; // rsi
  char *v13; // rax
  char *v14; // r15
  __int64 v15; // r13
  __int64 v16; // rbx
  DWORD v17; // edx
  int *v18; // r9
  int v19; // ebp
  HANDLE Thread; // rax
  __int64 i; // rbx
  HANDLE v22; // rcx
  int v23; // [rsp+88h] [rbp+10h]

  if ( a2 <= 0x40 )
  {
    WaitForMultipleObjects(a2, a3, 1, a4);
    return;
  }
  v7 = a2 >> 6;
  v8 = a2 & 0x3F;
  v9 = (a2 >> 6) + 1;
  if ( !v8 )
    v9 = v7;
  v10 = v9;
  if ( v9 > 0x40 )
    v10 = 64;
  v11 = 0;
  if ( v9 <= 0x40 )
    v11 = v8;
  v23 = v11;
  v12 = (HANDLE *)operator new(saturated_mul(v10, 8u));
  v13 = (char *)operator new(saturated_mul(v10, 0x18u));
  v14 = v13;
  if ( v12 && v13 )
  {
    v15 = 0;
    v16 = 0;
    if ( v10 )
    {
      v17 = v10 - 1;
      while ( 1 )
      {
        v18 = (int *)&v14[24 * v16];
        v18[4] = a4;
        *((_QWORD *)v18 + 1) = &a3[v15];
        if ( (_DWORD)v16 != v17 || (v19 = v23) == 0 )
          v19 = 64;
        *v18 = v19;
        Thread = CreateThread(0, 0, APPLICATION_MANAGER::WaitForMultipleObjectsThread, v18, 0, 0);
        v12[v16] = Thread;
        if ( !Thread )
          break;
        v16 = (unsigned int)(v16 + 1);
        v17 = v10 - 1;
        v15 = (unsigned int)(v19 + v15);
        if ( (unsigned int)v16 >= v10 )
          goto LABEL_20;
      }
      v10 = v16;
    }
LABEL_20:
    WaitForMultipleObjects(v10, v12, 1, a4);
    goto LABEL_22;
  }
  WaitForSingleObject(a3[a2 - 1], a4);
  if ( v12 )
  {
LABEL_22:
    for ( i = 0; (unsigned int)i < v10; i = (unsigned int)(i + 1) )
    {
      v22 = v12[i];
      if ( v22 )
      {
        CloseHandle(v22);
        v12[i] = 0;
      }
    }
    operator delete(v12);
  }
  if ( v14 )
    operator delete(v14);
}

```

## disassembly

```asm
0x180008d90  push    rbx
0x180008d92  push    rbp
0x180008d93  push    rsi
0x180008d94  push    rdi
0x180008d95  push    r12
0x180008d97  push    r13
0x180008d99  push    r14
0x180008d9b  push    r15
0x180008d9d  sub     rsp, 38h
0x180008da1  mov     r12, r8
0x180008da4  mov     r14d, r9d
0x180008da7  mov     r8d, 40h ; '@'
0x180008dad  mov     ebp, edx
0x180008daf  cmp     edx, r8d
0x180008db2  ja      short loc_180008DCA
0x180008db4  mov     r8d, 1; bWaitAll
0x180008dba  mov     rdx, r12; lpHandles
0x180008dbd  mov     ecx, ebp; nCount
0x180008dbf  call    cs:__imp_WaitForMultipleObjects
0x180008dc5  jmp     loc_180008F0F
0x180008dca  mov     eax, ebp
0x180008dcc  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180008dd3  shr     eax, 6
0x180008dd6  and     edx, 3Fh
0x180008dd9  lea     ecx, [rax+1]
0x180008ddc  cmovbe  ecx, eax
0x180008ddf  cmp     ecx, r8d
0x180008de2  mov     edi, ecx
0x180008de4  cmova   edi, r8d
0x180008de8  xor     eax, eax
0x180008dea  cmp     ecx, r8d
0x180008ded  mov     ebx, edi
0x180008def  cmovbe  eax, edx
0x180008df2  mov     [rsp+78h+arg_8], eax
0x180008df9  mov     eax, 8
0x180008dfe  mul     rbx
0x180008e01  cmovb   rax, r15
0x180008e05  mov     rcx, rax; Size
0x180008e08  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008e0d  mov     rsi, rax
0x180008e10  lea     eax, [r15+19h]
0x180008e14  mul     rbx
0x180008e17  cmovb   rax, r15
0x180008e1b  mov     rcx, rax; Size
0x180008e1e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008e23  mov     r15, rax
0x180008e26  test    rsi, rsi
0x180008e29  jz      loc_180008EC2
0x180008e2f  test    rax, rax
0x180008e32  jz      loc_180008EC2
0x180008e38  xor     r13d, r13d
0x180008e3b  xor     ebx, ebx
0x180008e3d  test    edi, edi
0x180008e3f  jz      short loc_180008EAC
0x180008e41  lea     edx, [rdi-1]
0x180008e44  lea     rax, [rbx+rbx*2]
0x180008e48  lea     r9, [r15+rax*8]; lpParameter
0x180008e4c  mov     [r9+10h], r14d
0x180008e50  lea     rcx, [r12+r13*8]
0x180008e54  mov     [r9+8], rcx
0x180008e58  cmp     ebx, edx
0x180008e5a  jnz     short loc_180008E69
0x180008e5c  mov     eax, [rsp+78h+arg_8]
0x180008e63  mov     ebp, eax
0x180008e65  test    eax, eax
0x180008e67  jnz     short loc_180008E6E
0x180008e69  mov     ebp, 40h ; '@'
0x180008e6e  mov     [rsp+78h+lpThreadId], 0; lpThreadId
0x180008e77  lea     r8, ?WaitForMultipleObjectsThread@APPLICATION_MANAGER@@CAKPEAX@Z; lpStartAddress
0x180008e7e  xor     edx, edx; dwStackSize
0x180008e80  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x180008e88  xor     ecx, ecx; lpThreadAttributes
0x180008e8a  mov     [r9], ebp
0x180008e8d  call    cs:__imp_CreateThread
0x180008e93  mov     [rsi+rbx*8], rax
0x180008e97  test    rax, rax
0x180008e9a  jz      short loc_180008EAA
0x180008e9c  inc     ebx
0x180008e9e  lea     edx, [rdi-1]
0x180008ea1  add     r13d, ebp
0x180008ea4  cmp     ebx, edi
0x180008ea6  jb      short loc_180008E44
0x180008ea8  jmp     short loc_180008EAC
0x180008eaa  mov     edi, ebx
0x180008eac  mov     r9d, r14d; dwMilliseconds
0x180008eaf  mov     r8d, 1; bWaitAll
0x180008eb5  mov     rdx, rsi; lpHandles
0x180008eb8  mov     ecx, edi; nCount
0x180008eba  call    cs:__imp_WaitForMultipleObjects
0x180008ec0  jmp     short loc_180008ED7
0x180008ec2  lea     eax, [rbp-1]
0x180008ec5  mov     edx, r14d; dwMilliseconds
0x180008ec8  mov     rcx, [r12+rax*8]; hHandle
0x180008ecc  call    cs:__imp_WaitForSingleObject
0x180008ed2  test    rsi, rsi
0x180008ed5  jz      short loc_180008F02
0x180008ed7  xor     ebx, ebx
0x180008ed9  test    edi, edi
0x180008edb  jz      short loc_180008EFA
0x180008edd  mov     rcx, [rsi+rbx*8]; hObject
0x180008ee1  test    rcx, rcx
0x180008ee4  jz      short loc_180008EF4
0x180008ee6  call    cs:__imp_CloseHandle
0x180008eec  mov     qword ptr [rsi+rbx*8], 0
0x180008ef4  inc     ebx
0x180008ef6  cmp     ebx, edi
0x180008ef8  jb      short loc_180008EDD
0x180008efa  mov     rcx, rsi; Block
0x180008efd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008f02  test    r15, r15
0x180008f05  jz      short loc_180008F0F
0x180008f07  mov     rcx, r15; Block
0x180008f0a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008f0f  add     rsp, 38h
0x180008f13  pop     r15
0x180008f15  pop     r14
0x180008f17  pop     r13
0x180008f19  pop     r12
0x180008f1b  pop     rdi
0x180008f1c  pop     rsi
0x180008f1d  pop     rbp
0x180008f1e  pop     rbx
0x180008f1f  retn
```
