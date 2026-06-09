# AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::Initialize(void)

- ea: `0x180020c84`
- end: `0x180020f44`
- name: `?Initialize@AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP@@QEAAJXZ`
- size: `704`
- prototype: `__int64 __fastcall(AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180020f4c`

## callees

- `0x180001210`
- `0x180001250`
- `0x180020c84`
- `0x18002118c`
- `0x18004700f`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180020cc0`
- `KERNEL32!GetLastError` at `0x180020d1b`
- `KERNEL32!GetLastError` at `0x180020cc0`
- `KERNEL32!GetLastError` at `0x180020d1b`
- `KERNEL32!HeapFree` at `0x180020d47`
- `KERNEL32!HeapFree` at `0x180020e6f`
- `KERNEL32!HeapFree` at `0x180020ea5`
- `KERNEL32!HeapFree` at `0x180020ef0`
- `KERNEL32!HeapFree` at `0x180020d47`
- `KERNEL32!HeapFree` at `0x180020e6f`
- `KERNEL32!HeapFree` at `0x180020ea5`
- `KERNEL32!HeapFree` at `0x180020ef0`
- `KERNEL32!GetLogicalProcessorInformationEx` at `0x180020cb6`
- `KERNEL32!GetLogicalProcessorInformationEx` at `0x180020d11`
- `KERNEL32!GetLogicalProcessorInformationEx` at `0x180020cb6`
- `KERNEL32!GetLogicalProcessorInformationEx` at `0x180020d11`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x180020e58`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x180020ed9`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x180020e58`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x180020ed9`
- `KERNEL32!HeapAlloc` at `0x180020ce5`
- `KERNEL32!HeapAlloc` at `0x180020ce5`
- `KERNEL32!GetProcessHeap` at `0x180020cd7`
- `KERNEL32!GetProcessHeap` at `0x180020d39`
- `KERNEL32!GetProcessHeap` at `0x180020e61`
- `KERNEL32!GetProcessHeap` at `0x180020e97`
- `KERNEL32!GetProcessHeap` at `0x180020ee2`
- `KERNEL32!GetProcessHeap` at `0x180020cd7`
- `KERNEL32!GetProcessHeap` at `0x180020d39`
- `KERNEL32!GetProcessHeap` at `0x180020e61`
- `KERNEL32!GetProcessHeap` at `0x180020e97`
- `KERNEL32!GetProcessHeap` at `0x180020ee2`

## pseudocode

```c
__int64 __fastcall AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::Initialize(AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP *this)
{
  unsigned __int16 v2; // r12
  struct _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX *v3; // rbp
  struct _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX *v4; // rbx
  signed int v5; // edi
  unsigned int v6; // ebx
  HANDLE v7; // rax
  bool v8; // sf
  signed int LastError; // eax
  HANDLE v10; // rax
  unsigned __int64 LineSize; // rcx
  void *v12; // rax
  char *v13; // rax
  char *v14; // rcx
  __int64 v15; // rcx
  AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP *v16; // rcx
  LPPROC_THREAD_ATTRIBUTE_LIST *v17; // r14
  LPPROC_THREAD_ATTRIBUTE_LIST v18; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v20; // rax
  unsigned __int16 i; // bp
  LPPROC_THREAD_ATTRIBUTE_LIST *v22; // r14
  LPPROC_THREAD_ATTRIBUTE_LIST v23; // rbx
  HANDLE v24; // rax
  SIZE_T dwBytes; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  v3 = 0;
  LODWORD(dwBytes) = 0;
  v4 = 0;
  if ( GetLogicalProcessorInformationEx(RelationGroup, 0, (PDWORD)&dwBytes) )
  {
LABEL_8:
    if ( GetLogicalProcessorInformationEx(RelationGroup, v4, (PDWORD)&dwBytes) )
    {
      v3 = v4;
      v5 = 0;
LABEL_19:
      if ( v3->Relationship != RelationGroup )
      {
        v5 = -2147024883;
        goto LABEL_36;
      }
      LineSize = v3->Cache.LineSize;
      *((_WORD *)this + 4) = LineSize;
      v12 = operator new(saturated_mul(LineSize, 8u));
      *((_QWORD *)this + 2) = v12;
      if ( v12 )
      {
        memset_0(v12, 0, 8LL * *((unsigned __int16 *)this + 4));
        if ( !*((_WORD *)this + 4) )
          goto LABEL_36;
        while ( 1 )
        {
          v13 = (char *)operator new(0x18u);
          v14 = v13;
          if ( v13 )
          {
            *(_QWORD *)v13 = 0;
            *(_OWORD *)(v13 + 8) = 0;
          }
          else
          {
            v14 = 0;
          }
          *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * v2) = v14;
          v15 = *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * v2);
          if ( !v15 )
            break;
          *(_WORD *)(v15 + 16) = v2;
          v16 = *(AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP **)(*((_QWORD *)this + 2) + 8LL * v2);
          *((_QWORD *)v16 + 1) = v4->Group.GroupInfo[v2].ActiveProcessorMask;
          v5 = AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::InitializeContext(
                 v16,
                 *(struct AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT **)(*((_QWORD *)this + 2)
                                                                                          + 8LL * v2));
          if ( v5 < 0 )
          {
            v17 = *(LPPROC_THREAD_ATTRIBUTE_LIST **)(*((_QWORD *)this + 2) + 8LL * v2);
            if ( v17 )
            {
              if ( *v17 )
              {
                DeleteProcThreadAttributeList(*v17);
                v18 = *v17;
                ProcessHeap = GetProcessHeap();
                HeapFree(ProcessHeap, 0, v18);
                *v17 = 0;
              }
              operator delete(v17);
            }
            *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * v2) = 0;
            goto LABEL_36;
          }
          if ( ++v2 >= *((_WORD *)this + 4) )
            goto LABEL_36;
        }
      }
      v5 = -2147024888;
LABEL_36:
      v20 = GetProcessHeap();
      HeapFree(v20, 0, v3);
      if ( v5 >= 0 )
        return (unsigned int)v5;
      goto LABEL_37;
    }
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError <= 0 )
      goto LABEL_12;
    v5 = (unsigned __int16)LastError;
LABEL_11:
    v5 |= 0x80070000;
LABEL_12:
    v8 = v5 < 0;
    goto LABEL_13;
  }
  v5 = GetLastError();
  if ( v5 == 122 )
  {
    if ( (_DWORD)dwBytes )
    {
      v6 = dwBytes;
      v7 = GetProcessHeap();
      v4 = (struct _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX *)HeapAlloc(v7, 0, v6);
      if ( !v4 )
      {
        v5 = -2147024774;
        goto LABEL_37;
      }
      goto LABEL_8;
    }
LABEL_7:
    v5 = (unsigned __int16)v5;
    goto LABEL_11;
  }
  v8 = v5 < 0;
  if ( v5 > 0 )
    goto LABEL_7;
LABEL_13:
  if ( v8 && v4 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v4);
    goto LABEL_37;
  }
  if ( v5 >= 0 )
  {
    v4 = 0;
    goto LABEL_19;
  }
LABEL_37:
  if ( *((_QWORD *)this + 2) )
  {
    for ( i = 0; i < v2; ++i )
    {
      v22 = *(LPPROC_THREAD_ATTRIBUTE_LIST **)(*((_QWORD *)this + 2) + 8LL * i);
      if ( v22 )
      {
        if ( *v22 )
        {
          DeleteProcThreadAttributeList(*v22);
          v23 = *v22;
          v24 = GetProcessHeap();
          HeapFree(v24, 0, v23);
          *v22 = 0;
        }
        operator delete(v22);
        *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * i) = 0;
      }
    }
    operator delete(*((void **)this + 2));
    *((_QWORD *)this + 2) = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180020c84  mov     rax, rsp
0x180020c87  mov     [rax+8], rbx
0x180020c8b  mov     [rax+18h], rbp
0x180020c8f  push    rsi
0x180020c90  push    rdi
0x180020c91  push    r12
0x180020c93  push    r14
0x180020c95  push    r15
0x180020c97  sub     rsp, 20h
0x180020c9b  mov     rsi, rcx
0x180020c9e  lea     r8, [rax+10h]; ReturnedLength
0x180020ca2  xor     r12d, r12d
0x180020ca5  xor     ebp, ebp
0x180020ca7  xor     edx, edx; Buffer
0x180020ca9  mov     [rax+10h], ebp
0x180020cac  xor     ebx, ebx
0x180020cae  lea     r14d, [r12+4]
0x180020cb3  mov     ecx, r14d; RelationshipType
0x180020cb6  call    cs:__imp_GetLogicalProcessorInformationEx
0x180020cbc  test    eax, eax
0x180020cbe  jnz     short loc_180020D06
0x180020cc0  call    cs:__imp_GetLastError
0x180020cc6  mov     edi, eax
0x180020cc8  cmp     eax, 7Ah ; 'z'
0x180020ccb  jnz     short loc_180020CFD
0x180020ccd  mov     eax, dword ptr [rsp+48h+dwBytes]
0x180020cd1  test    eax, eax
0x180020cd3  jz      short loc_180020D01
0x180020cd5  mov     ebx, eax
0x180020cd7  call    cs:__imp_GetProcessHeap
0x180020cdd  mov     r8d, ebx; dwBytes
0x180020ce0  xor     edx, edx; dwFlags
0x180020ce2  mov     rcx, rax; hHeap
0x180020ce5  call    cs:__imp_HeapAlloc
0x180020ceb  mov     rbx, rax
0x180020cee  test    rax, rax
0x180020cf1  jnz     short loc_180020D06
0x180020cf3  mov     edi, 8007007Ah
0x180020cf8  jmp     loc_180020EAF
0x180020cfd  test    edi, edi
0x180020cff  jle     short loc_180020D32
0x180020d01  movzx   edi, di
0x180020d04  jmp     short loc_180020D2A
0x180020d06  lea     r8, [rsp+48h+dwBytes]; ReturnedLength
0x180020d0b  mov     rdx, rbx; Buffer
0x180020d0e  mov     ecx, r14d; RelationshipType
0x180020d11  call    cs:__imp_GetLogicalProcessorInformationEx
0x180020d17  test    eax, eax
0x180020d19  jnz     short loc_180020D5F
0x180020d1b  call    cs:__imp_GetLastError
0x180020d21  mov     edi, eax
0x180020d23  test    eax, eax
0x180020d25  jle     short loc_180020D30
0x180020d27  movzx   edi, ax
0x180020d2a  or      edi, 80070000h
0x180020d30  test    edi, edi
0x180020d32  jns     short loc_180020D52
0x180020d34  test    rbx, rbx
0x180020d37  jz      short loc_180020D52
0x180020d39  call    cs:__imp_GetProcessHeap
0x180020d3f  mov     r8, rbx; lpMem
0x180020d42  xor     edx, edx; dwFlags
0x180020d44  mov     rcx, rax; hHeap
0x180020d47  call    cs:__imp_HeapFree
0x180020d4d  jmp     loc_180020EAF
0x180020d52  test    edi, edi
0x180020d54  js      loc_180020EAF
0x180020d5a  mov     rbx, rbp
0x180020d5d  jmp     short loc_180020D64
0x180020d5f  mov     rbp, rbx
0x180020d62  xor     edi, edi
0x180020d64  cmp     [rbp+0], r14d
0x180020d68  jz      short loc_180020D74
0x180020d6a  mov     edi, 8007000Dh
0x180020d6f  jmp     loc_180020E97
0x180020d74  movzx   eax, word ptr [rbp+0Ah]
0x180020d78  mov     ecx, eax
0x180020d7a  mov     [rsi+8], ax
0x180020d7e  mov     eax, 8
0x180020d83  mul     rcx
0x180020d86  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180020d8d  cmovb   rax, rcx
0x180020d91  mov     rcx, rax; Size
0x180020d94  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020d99  mov     [rsi+10h], rax
0x180020d9d  test    rax, rax
0x180020da0  jz      loc_180020E92
0x180020da6  movzx   r8d, word ptr [rsi+8]
0x180020dab  xor     edx, edx; Val
0x180020dad  shl     r8, 3; Size
0x180020db1  mov     rcx, rax; void *
0x180020db4  call    memset_0
0x180020db9  xor     eax, eax
0x180020dbb  cmp     ax, [rsi+8]
0x180020dbf  jnb     loc_180020E97
0x180020dc5  mov     ecx, 18h; Size
0x180020dca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020dcf  mov     rcx, rax
0x180020dd2  test    rax, rax
0x180020dd5  jz      short loc_180020DE7
0x180020dd7  xorps   xmm0, xmm0
0x180020dda  mov     qword ptr [rax], 0
0x180020de1  movups  xmmword ptr [rax+8], xmm0
0x180020de5  jmp     short loc_180020DE9
0x180020de7  xor     ecx, ecx
0x180020de9  mov     rax, [rsi+10h]
0x180020ded  movzx   r15d, r12w
0x180020df1  mov     [rax+r15*8], rcx
0x180020df5  mov     rax, [rsi+10h]
0x180020df9  mov     rcx, [rax+r15*8]
0x180020dfd  test    rcx, rcx
0x180020e00  jz      loc_180020E92
0x180020e06  mov     [rcx+10h], r12w
0x180020e0b  lea     rdx, [r15+r15*2]
0x180020e0f  mov     rax, [rsi+10h]
0x180020e13  add     rdx, rdx
0x180020e16  mov     rcx, [rax+r15*8]; this
0x180020e1a  mov     rax, [rbx+rdx*8+48h]
0x180020e1f  mov     [rcx+8], rax
0x180020e23  mov     rdx, [rsi+10h]
0x180020e27  mov     rdx, [rdx+r15*8]; struct AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT *
0x180020e2b  call    ?InitializeContext@AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP@@AEAAJPEAUTHREAD_AFFINITY_CONTEXT@1@@Z; AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::InitializeContext(AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT *)
0x180020e30  mov     edi, eax
0x180020e32  test    eax, eax
0x180020e34  js      short loc_180020E43
0x180020e36  inc     r12w
0x180020e3a  cmp     r12w, [rsi+8]
0x180020e3f  jb      short loc_180020DC5
0x180020e41  jmp     short loc_180020E97
0x180020e43  mov     rax, [rsi+10h]
0x180020e47  mov     r14, [rax+r15*8]
0x180020e4b  test    r14, r14
0x180020e4e  jz      short loc_180020E84
0x180020e50  mov     rcx, [r14]; lpAttributeList
0x180020e53  test    rcx, rcx
0x180020e56  jz      short loc_180020E7C
0x180020e58  call    cs:__imp_DeleteProcThreadAttributeList
0x180020e5e  mov     rbx, [r14]
0x180020e61  call    cs:__imp_GetProcessHeap
0x180020e67  mov     r8, rbx; lpMem
0x180020e6a  xor     edx, edx; dwFlags
0x180020e6c  mov     rcx, rax; hHeap
0x180020e6f  call    cs:__imp_HeapFree
0x180020e75  mov     qword ptr [r14], 0
0x180020e7c  mov     rcx, r14; Block
0x180020e7f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020e84  mov     rax, [rsi+10h]
0x180020e88  mov     qword ptr [rax+r15*8], 0
0x180020e90  jmp     short loc_180020E97
0x180020e92  mov     edi, 80070008h
0x180020e97  call    cs:__imp_GetProcessHeap
0x180020e9d  mov     r8, rbp; lpMem
0x180020ea0  xor     edx, edx; dwFlags
0x180020ea2  mov     rcx, rax; hHeap
0x180020ea5  call    cs:__imp_HeapFree
0x180020eab  test    edi, edi
0x180020ead  jns     short loc_180020F2B
0x180020eaf  cmp     qword ptr [rsi+10h], 0
0x180020eb4  jz      short loc_180020F2B
0x180020eb6  xor     ebp, ebp
0x180020eb8  xor     eax, eax
0x180020eba  cmp     ax, r12w
0x180020ebe  jnb     short loc_180020F1A
0x180020ec0  mov     rax, [rsi+10h]
0x180020ec4  movzx   r15d, bp
0x180020ec8  mov     r14, [rax+r15*8]
0x180020ecc  test    r14, r14
0x180020ecf  jz      short loc_180020F11
0x180020ed1  mov     rcx, [r14]; lpAttributeList
0x180020ed4  test    rcx, rcx
0x180020ed7  jz      short loc_180020EFD
0x180020ed9  call    cs:__imp_DeleteProcThreadAttributeList
0x180020edf  mov     rbx, [r14]
0x180020ee2  call    cs:__imp_GetProcessHeap
0x180020ee8  mov     r8, rbx; lpMem
0x180020eeb  xor     edx, edx; dwFlags
0x180020eed  mov     rcx, rax; hHeap
0x180020ef0  call    cs:__imp_HeapFree
0x180020ef6  mov     qword ptr [r14], 0
0x180020efd  mov     rcx, r14; Block
0x180020f00  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020f05  mov     rax, [rsi+10h]
0x180020f09  mov     qword ptr [rax+r15*8], 0
0x180020f11  inc     bp
0x180020f14  cmp     bp, r12w
0x180020f18  jb      short loc_180020EC0
0x180020f1a  mov     rcx, [rsi+10h]; Block
0x180020f1e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020f23  mov     qword ptr [rsi+10h], 0
0x180020f2b  mov     rbx, [rsp+48h+arg_0]
0x180020f30  mov     eax, edi
0x180020f32  mov     rbp, [rsp+48h+arg_10]
0x180020f37  add     rsp, 20h
0x180020f3b  pop     r15
0x180020f3d  pop     r14
0x180020f3f  pop     r12
0x180020f41  pop     rdi
0x180020f42  pop     rsi
0x180020f43  retn
```
