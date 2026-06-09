# _drr_ResolveConflictions

- ea: `0x180004e90`
- end: `0x1800050cc`
- name: `_drr_ResolveConflictions`
- size: `572`
- prototype: `__int64 __fastcall(__int64 *, __int64 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006230`

## callees

- `0x180004e90`
- `0x18000cfe8`
- `0x18000d886`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004ff1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005019`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005054`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005088`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004f9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004ff1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005019`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005054`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005088`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180004f5d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180004f5d`

## pseudocode

```c
__int64 __fastcall drr_ResolveConflictions(__int64 *a1, __int64 *a2, int a3)
{
  __int64 v3; // rax
  unsigned int v5; // ecx
  __int64 v6; // rdi
  __int64 v7; // rbx
  __int64 v9; // r15
  _QWORD *v10; // rsi
  __int64 v11; // rbp
  __int64 v12; // r15
  int v13; // eax
  int *v14; // rcx
  int v15; // edx
  LONG v16; // eax
  _DWORD *v17; // rcx
  _DWORD *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // esi
  _DWORD *v22; // rcx
  int v23; // eax
  unsigned int v25; // [rsp+70h] [rbp+8h]
  __int64 v26; // [rsp+78h] [rbp+10h]
  __int64 v28; // [rsp+88h] [rbp+20h]

  v3 = *a2;
  v5 = 0;
  v28 = *a2;
  v6 = 0;
  v25 = 0;
  v7 = 0;
  v9 = *a1;
  v26 = *a1;
  if ( *((_DWORD *)a1 + 2) )
  {
    while ( 1 )
    {
      if ( (unsigned int)v6 >= *((_DWORD *)a2 + 2) )
        return v25;
      v10 = *(_QWORD **)(v3 + 8 * v6);
      v11 = v10[1];
      v12 = *(_QWORD *)(*(_QWORD *)(v9 + 8 * v7) + 8LL);
      v13 = memcmp_0((const void *)v12, (const void *)v11, 0x60u);
      if ( v13 >= 0 )
      {
        if ( v13 > 0 )
          goto LABEL_6;
        v14 = *(int **)(v26 + 8 * v7);
        v15 = *v14;
        if ( *v14 != *(_DWORD *)v10 )
        {
          if ( a3 )
          {
            if ( ((v15 - 1) & 0xFFFFFFFD) == 0 || (v21 = 1, v15 == 5) )
            {
              LocalFree(v14);
              DRR_DeleteAnyGrowableArray(a1, (unsigned int)v7);
              v21 = 0;
            }
            v22 = *(_DWORD **)(v28 + 8 * v6);
            if ( ((*v22 - 1) & 0xFFFFFFFD) == 0 || (v23 = 1, *v22 == 5) )
            {
              LocalFree(v22);
              DRR_DeleteAnyGrowableArray(a2, (unsigned int)v6);
              v23 = 0;
            }
            v7 = (unsigned int)(v21 + v7);
            v6 = (unsigned int)(v23 + v6);
            goto LABEL_32;
          }
          if ( v15 == 1 )
          {
            if ( *(_DWORD *)v10 )
              goto LABEL_12;
          }
          else if ( v15 != 3 || *(_DWORD *)v10 != 2 )
          {
LABEL_12:
            v25 = 1;
            v16 = CompareFileTime((const FILETIME *)(v12 + 96), (const FILETIME *)(v11 + 96));
            v9 = v26;
            v17 = *(_DWORD **)(v26 + 8 * v7);
            if ( v16 <= 0 )
            {
              LocalFree(v17);
              DRR_DeleteAnyGrowableArray(a1, (unsigned int)v7);
              v20 = *(_QWORD *)(v28 + 8 * v6);
              v6 = (unsigned int)(v6 + 1);
              *(_DWORD *)(v20 + 4) = 0;
            }
            else
            {
              if ( *v17 == 1 )
              {
                v18 = *(_DWORD **)(v28 + 8 * v6);
                if ( (*v18 & 0xFFFFFFF9) == 0 && *v18 != 6 )
                  *v17 = 3;
              }
              LocalFree(*(HLOCAL *)(v28 + 8 * v6));
              DRR_DeleteAnyGrowableArray(a2, (unsigned int)v6);
              v19 = *(_QWORD *)(v26 + 8 * v7);
              v7 = (unsigned int)(v7 + 1);
              *(_DWORD *)(v19 + 4) = 0;
            }
            goto LABEL_33;
          }
          if ( *(_QWORD *)(v12 + 108) != *(_QWORD *)(v11 + 108)
            || *(_QWORD *)(v12 + 116) != *(_QWORD *)(v11 + 116)
            || *(_DWORD *)(v12 + 124) != *(_DWORD *)(v11 + 124) )
          {
            goto LABEL_12;
          }
          LocalFree(v14);
          DRR_DeleteAnyGrowableArray(a1, (unsigned int)v7);
          *(_DWORD *)(*(_QWORD *)(v28 + 8 * v6) + 4LL) = 1;
LABEL_6:
          v6 = (unsigned int)(v6 + 1);
          goto LABEL_32;
        }
        LocalFree(v10);
        DRR_DeleteAnyGrowableArray(a2, (unsigned int)v6);
      }
      v7 = (unsigned int)(v7 + 1);
LABEL_32:
      v9 = v26;
LABEL_33:
      v3 = v28;
      if ( (unsigned int)v7 >= *((_DWORD *)a1 + 2) )
        return v25;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180004e90  mov     [rsp+arg_10], r8d
0x180004e95  push    rbx
0x180004e96  push    rbp
0x180004e97  push    rsi
0x180004e98  push    rdi
0x180004e99  push    r12
0x180004e9b  push    r13
0x180004e9d  push    r14
0x180004e9f  push    r15
0x180004ea1  sub     rsp, 28h
0x180004ea5  mov     rax, [rdx]
0x180004ea8  mov     r14, rcx
0x180004eab  xor     ecx, ecx
0x180004ead  mov     [rsp+68h+arg_18], rax
0x180004eb5  xor     edi, edi
0x180004eb7  mov     [rsp+68h+arg_0], ecx
0x180004ebb  xor     ebx, ebx
0x180004ebd  mov     r13, rdx
0x180004ec0  mov     r15, [r14]
0x180004ec3  mov     [rsp+68h+arg_8], r15
0x180004ec8  cmp     [r14+8], ecx
0x180004ecc  jbe     loc_1800050B9
0x180004ed2  cmp     edi, [r13+8]
0x180004ed6  jnb     loc_1800050B5
0x180004edc  mov     rsi, [rax+rdi*8]
0x180004ee0  mov     r8d, 60h ; '`'; Size
0x180004ee6  mov     rax, [r15+rbx*8]
0x180004eea  mov     rbp, [rsi+8]
0x180004eee  mov     r15, [rax+8]
0x180004ef2  mov     rdx, rbp; Buf2
0x180004ef5  mov     rcx, r15; Buf1
0x180004ef8  call    memcmp_0
0x180004efd  test    eax, eax
0x180004eff  jns     short loc_180004F08
0x180004f01  inc     ebx
0x180004f03  jmp     loc_18000509E
0x180004f08  jle     short loc_180004F11
0x180004f0a  inc     edi
0x180004f0c  jmp     loc_18000509E
0x180004f11  mov     rax, [rsp+68h+arg_8]
0x180004f16  mov     rcx, [rax+rbx*8]; hMem
0x180004f1a  mov     edx, [rcx]
0x180004f1c  cmp     edx, [rsi]
0x180004f1e  jnz     short loc_180004F35
0x180004f20  mov     rcx, rsi; hMem
0x180004f23  call    cs:__imp_LocalFree
0x180004f29  mov     edx, edi
0x180004f2b  mov     rcx, r13
0x180004f2e  call    DRR_DeleteAnyGrowableArray
0x180004f33  jmp     short loc_180004F01
0x180004f35  cmp     [rsp+68h+arg_10], 0
0x180004f3d  jnz     loc_180005040
0x180004f43  cmp     edx, 1
0x180004f46  jnz     short loc_180004FBE
0x180004f48  cmp     dword ptr [rsi], 0
0x180004f4b  jz      short loc_180004FC8
0x180004f4d  lea     rdx, [rbp+60h]; lpFileTime2
0x180004f51  mov     [rsp+68h+arg_0], 1
0x180004f59  lea     rcx, [r15+60h]; lpFileTime1
0x180004f5d  call    cs:__imp_CompareFileTime
0x180004f63  mov     r15, [rsp+68h+arg_8]
0x180004f68  mov     rcx, [r15+rbx*8]; hMem
0x180004f6c  test    eax, eax
0x180004f6e  jle     loc_180005019
0x180004f74  cmp     dword ptr [rcx], 1
0x180004f77  mov     rdx, [rsp+68h+arg_18]
0x180004f7f  jnz     short loc_180004F98
0x180004f81  mov     rax, [rdx+rdi*8]
0x180004f85  test    dword ptr [rax], 0FFFFFFF9h
0x180004f8b  jnz     short loc_180004F98
0x180004f8d  cmp     dword ptr [rax], 6
0x180004f90  jz      short loc_180004F98
0x180004f92  mov     dword ptr [rcx], 3
0x180004f98  mov     rcx, [rdx+rdi*8]; hMem
0x180004f9c  call    cs:__imp_LocalFree
0x180004fa2  mov     edx, edi
0x180004fa4  mov     rcx, r13
0x180004fa7  call    DRR_DeleteAnyGrowableArray
0x180004fac  mov     rax, [r15+rbx*8]
0x180004fb0  inc     ebx
0x180004fb2  mov     dword ptr [rax+4], 0
0x180004fb9  jmp     loc_1800050A3
0x180004fbe  cmp     edx, 3
0x180004fc1  jnz     short loc_180004F4D
0x180004fc3  cmp     dword ptr [rsi], 2
0x180004fc6  jnz     short loc_180004F4D
0x180004fc8  mov     rax, [r15+6Ch]
0x180004fcc  cmp     rax, [rbp+6Ch]
0x180004fd0  jnz     loc_180004F4D
0x180004fd6  mov     rax, [r15+74h]
0x180004fda  cmp     rax, [rbp+74h]
0x180004fde  jnz     loc_180004F4D
0x180004fe4  mov     eax, [r15+7Ch]
0x180004fe8  cmp     eax, [rbp+7Ch]
0x180004feb  jnz     loc_180004F4D
0x180004ff1  call    cs:__imp_LocalFree
0x180004ff7  mov     edx, ebx
0x180004ff9  mov     rcx, r14
0x180004ffc  call    DRR_DeleteAnyGrowableArray
0x180005001  mov     rdx, [rsp+68h+arg_18]
0x180005009  mov     rax, [rdx+rdi*8]
0x18000500d  mov     dword ptr [rax+4], 1
0x180005014  jmp     loc_180004F0A
0x180005019  call    cs:__imp_LocalFree
0x18000501f  mov     edx, ebx
0x180005021  mov     rcx, r14
0x180005024  call    DRR_DeleteAnyGrowableArray
0x180005029  mov     rdx, [rsp+68h+arg_18]
0x180005031  mov     rax, [rdx+rdi*8]
0x180005035  inc     edi
0x180005037  mov     dword ptr [rax+4], 0
0x18000503e  jmp     short loc_1800050A3
0x180005040  lea     eax, [rdx-1]
0x180005043  test    eax, 0FFFFFFFDh
0x180005048  jz      short loc_180005054
0x18000504a  mov     esi, 1
0x18000504f  cmp     edx, 5
0x180005052  jnz     short loc_180005066
0x180005054  call    cs:__imp_LocalFree
0x18000505a  mov     edx, ebx
0x18000505c  mov     rcx, r14
0x18000505f  call    DRR_DeleteAnyGrowableArray
0x180005064  xor     esi, esi
0x180005066  mov     rdx, [rsp+68h+arg_18]
0x18000506e  mov     rcx, [rdx+rdi*8]; hMem
0x180005072  mov     edx, [rcx]
0x180005074  lea     eax, [rdx-1]
0x180005077  test    eax, 0FFFFFFFDh
0x18000507c  jz      short loc_180005088
0x18000507e  mov     eax, 1
0x180005083  cmp     edx, 5
0x180005086  jnz     short loc_18000509A
0x180005088  call    cs:__imp_LocalFree
0x18000508e  mov     edx, edi
0x180005090  mov     rcx, r13
0x180005093  call    DRR_DeleteAnyGrowableArray
0x180005098  xor     eax, eax
0x18000509a  add     ebx, esi
0x18000509c  add     edi, eax
0x18000509e  mov     r15, [rsp+68h+arg_8]
0x1800050a3  mov     rax, [rsp+68h+arg_18]
0x1800050ab  cmp     ebx, [r14+8]
0x1800050af  jb      loc_180004ED2
0x1800050b5  mov     ecx, [rsp+68h+arg_0]
0x1800050b9  mov     eax, ecx
0x1800050bb  add     rsp, 28h
0x1800050bf  pop     r15
0x1800050c1  pop     r14
0x1800050c3  pop     r13
0x1800050c5  pop     r12
0x1800050c7  pop     rdi
0x1800050c8  pop     rsi
0x1800050c9  pop     rbp
0x1800050ca  pop     rbx
0x1800050cb  retn
```
