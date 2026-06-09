# Copy<TaskAllocator>(_EAP_ATTRIBUTES &,_EAP_ATTRIBUTES const &)

- ea: `0x180003a4c`
- end: `0x180003c38`
- name: `??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_ATTRIBUTES@@AEBU0@@Z`
- size: `492`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180003dbc`
- `0x1800067f0`

## callees

- `0x18000343c`
- `0x180003a4c`
- `0x18000940c`
- `0x180033d78`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003b40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003bac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003b40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003bac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003aae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003aae`

## pseudocode

```c
char __fastcall Copy<TaskAllocator>(__int64 a1, _DWORD *a2)
{
  __int64 *v2; // r14
  int v3; // r8d
  int v4; // ebp
  void *v7; // rcx
  char result; // al
  __int64 v9; // rdx
  unsigned int v10; // eax
  int v11; // r9d
  __int64 v12; // r10
  unsigned int v13; // ebx
  void *v14; // rax
  int v15; // r15d
  __int64 v16; // rax
  int v17; // ecx
  __int64 v18; // rbx
  void *v19; // rcx
  __int64 v20; // rdx
  SIZE_T cb; // [rsp+58h] [rbp+10h] BYREF

  v2 = (__int64 *)(a2 + 2);
  *(_OWORD *)a1 = 0;
  v3 = *a2;
  v4 = 0;
  if ( !*a2 )
  {
    if ( *v2 )
      goto LABEL_3;
    goto LABEL_11;
  }
  if ( *v2 )
  {
LABEL_11:
    v9 = *v2;
    if ( !*v2 )
      return 1;
    v10 = 0;
    LODWORD(cb) = 0;
    if ( v3 <= 0 )
      return 1;
    v11 = 0;
    v12 = 0;
    while ( !*(_DWORD *)(v9 + 16 * v12 + 4) )
    {
      if ( !*(_QWORD *)(v9 + 16 * v12 + 8) )
        goto LABEL_18;
LABEL_19:
      ++v11;
      ++v12;
      if ( v11 >= v3 )
      {
        LODWORD(cb) = v10;
        if ( v10 )
        {
          *(_DWORD *)a1 = v10;
          if ( (int)ULongLongToULong(16LL * v10, (unsigned int *)&cb) < 0 )
            goto LABEL_3;
          v13 = cb;
          v14 = CoTaskMemAlloc((unsigned int)cb);
          *(_QWORD *)(a1 + 8) = v14;
          if ( !v14 )
            goto LABEL_3;
          memset_0(v14, 0, v13);
          v15 = 0;
          while ( 2 )
          {
            if ( v15 >= *a2 )
              return 1;
            v16 = *v2;
            v17 = *(_DWORD *)(*v2 + 16LL * v15 + 4);
            if ( v17 )
            {
              if ( *(_QWORD *)(v16 + 16LL * v15 + 8) )
              {
                v18 = 2LL * v4;
                *(_DWORD *)(*(_QWORD *)(a1 + 8) + 8 * v18 + 4) = v17;
                *(_DWORD *)(*(_QWORD *)(a1 + 8) + 8 * v18) = *(_DWORD *)(*v2 + 16LL * v15);
                *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL * v4 + 8) = CoTaskMemAlloc(*(unsigned int *)(*v2 + 16LL * v15 + 4));
                v19 = *(void **)(*(_QWORD *)(a1 + 8) + 16LL * v4 + 8);
                if ( !v19 )
                  goto LABEL_3;
                memcpy_0(v19, *(const void **)(*v2 + 16LL * v15 + 8), *(unsigned int *)(*v2 + 16LL * v15 + 4));
LABEL_31:
                ++v4;
              }
            }
            else if ( !*(_QWORD *)(v16 + 16LL * v15 + 8) )
            {
              v20 = 2LL * v4;
              *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v20 + 8) = 0;
              *(_DWORD *)(*(_QWORD *)(a1 + 8) + 8 * v20 + 4) = 0;
              *(_DWORD *)(*(_QWORD *)(a1 + 8) + 8 * v20) = *(_DWORD *)(*v2 + 16LL * v15);
              goto LABEL_31;
            }
            ++v15;
            continue;
          }
        }
        return 1;
      }
    }
    if ( !*(_QWORD *)(v9 + 16 * v12 + 8) )
      goto LABEL_19;
LABEL_18:
    ++v10;
    goto LABEL_19;
  }
LABEL_3:
  if ( *(_QWORD *)(a1 + 8) )
  {
    for ( ; v4 >= 0; --v4 )
    {
      v7 = *(void **)(*(_QWORD *)(a1 + 8) + 16LL * (unsigned int)v4 + 8);
      if ( v7 )
        CoTaskMemFree(v7);
    }
    CoTaskMemFree(*(LPVOID *)(a1 + 8));
  }
  result = 0;
  *(_OWORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180003a4c  mov     [rsp+arg_0], rbx
0x180003a51  mov     [rsp+arg_10], rbp
0x180003a56  push    rsi
0x180003a57  push    rdi
0x180003a58  push    r12
0x180003a5a  push    r14
0x180003a5c  push    r15
0x180003a5e  sub     rsp, 20h
0x180003a62  xorps   xmm0, xmm0
0x180003a65  lea     r14, [rdx+8]
0x180003a69  movups  xmmword ptr [rcx], xmm0
0x180003a6c  mov     r8d, [rdx]
0x180003a6f  xor     ebp, ebp
0x180003a71  mov     r12, rdx
0x180003a74  mov     rdi, rcx
0x180003a77  test    r8d, r8d
0x180003a7a  jz      short loc_180003AC1
0x180003a7c  cmp     [r14], rbp
0x180003a7f  jnz     short loc_180003AC6
0x180003a81  cmp     qword ptr [rdi+8], 0
0x180003a86  jz      short loc_180003AB4
0x180003a88  test    ebp, ebp
0x180003a8a  js      short loc_180003AAA
0x180003a8c  mov     rax, [rdi+8]
0x180003a90  mov     ecx, ebp
0x180003a92  add     rcx, rcx
0x180003a95  mov     rcx, [rax+rcx*8+8]; pv
0x180003a9a  test    rcx, rcx
0x180003a9d  jz      short loc_180003AA5
0x180003a9f  call    cs:__imp_CoTaskMemFree
0x180003aa5  sub     ebp, 1
0x180003aa8  jns     short loc_180003A8C
0x180003aaa  mov     rcx, [rdi+8]; pv
0x180003aae  call    cs:__imp_CoTaskMemFree
0x180003ab4  xorps   xmm0, xmm0
0x180003ab7  xor     al, al
0x180003ab9  movups  xmmword ptr [rdi], xmm0
0x180003abc  jmp     loc_180003C21
0x180003ac1  cmp     [r14], rbp
0x180003ac4  jnz     short loc_180003A81
0x180003ac6  mov     rdx, [r14]
0x180003ac9  test    rdx, rdx
0x180003acc  jz      loc_180003C1F
0x180003ad2  xor     eax, eax
0x180003ad4  mov     dword ptr [rsp+48h+cb], eax
0x180003ad8  test    r8d, r8d
0x180003adb  jle     loc_180003C1F
0x180003ae1  xor     r9d, r9d
0x180003ae4  xor     r10d, r10d
0x180003ae7  mov     rcx, r10
0x180003aea  add     rcx, rcx
0x180003aed  mov     r11d, [rdx+rcx*8+4]
0x180003af2  test    r11d, r11d
0x180003af5  jz      short loc_180003B00
0x180003af7  cmp     [rdx+rcx*8+8], rbp
0x180003afc  jnz     short loc_180003B07
0x180003afe  jmp     short loc_180003B09
0x180003b00  cmp     [rdx+rcx*8+8], rbp
0x180003b05  jnz     short loc_180003B09
0x180003b07  inc     eax
0x180003b09  inc     r9d
0x180003b0c  inc     r10
0x180003b0f  cmp     r9d, r8d
0x180003b12  jl      short loc_180003AE7
0x180003b14  mov     dword ptr [rsp+48h+cb], eax
0x180003b18  test    eax, eax
0x180003b1a  jz      loc_180003C1F
0x180003b20  mov     ecx, eax
0x180003b22  lea     rdx, [rsp+48h+cb]; unsigned int *
0x180003b27  shl     rcx, 4; unsigned __int64
0x180003b2b  mov     [rdi], eax
0x180003b2d  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180003b32  test    eax, eax
0x180003b34  js      loc_180003A81
0x180003b3a  mov     ebx, dword ptr [rsp+48h+cb]
0x180003b3e  mov     ecx, ebx; cb
0x180003b40  call    cs:__imp_CoTaskMemAlloc
0x180003b46  mov     [rdi+8], rax
0x180003b4a  test    rax, rax
0x180003b4d  jz      loc_180003A81
0x180003b53  mov     r8d, ebx; Size
0x180003b56  xor     edx, edx; Val
0x180003b58  mov     rcx, rax; void *
0x180003b5b  call    memset_0
0x180003b60  xor     r15d, r15d
0x180003b63  cmp     r15d, [r12]
0x180003b67  jge     loc_180003C1F
0x180003b6d  mov     rax, [r14]
0x180003b70  movsxd  rsi, r15d
0x180003b73  add     rsi, rsi
0x180003b76  mov     ecx, [rax+rsi*8+4]
0x180003b7a  test    ecx, ecx
0x180003b7c  jz      short loc_180003BE1
0x180003b7e  cmp     qword ptr [rax+rsi*8+8], 0
0x180003b84  jz      loc_180003C17
0x180003b8a  mov     rax, [rdi+8]
0x180003b8e  movsxd  rbx, ebp
0x180003b91  add     rbx, rbx
0x180003b94  mov     [rax+rbx*8+4], ecx
0x180003b98  mov     rax, [r14]
0x180003b9b  mov     rcx, [rdi+8]
0x180003b9f  mov     eax, [rax+rsi*8]
0x180003ba2  mov     [rcx+rbx*8], eax
0x180003ba5  mov     rax, [r14]
0x180003ba8  mov     ecx, [rax+rsi*8+4]; cb
0x180003bac  call    cs:__imp_CoTaskMemAlloc
0x180003bb2  mov     rcx, [rdi+8]
0x180003bb6  mov     [rcx+rbx*8+8], rax
0x180003bbb  mov     rax, [rdi+8]
0x180003bbf  mov     rcx, [rax+rbx*8+8]; void *
0x180003bc4  test    rcx, rcx
0x180003bc7  jz      loc_180003A81
0x180003bcd  mov     rdx, [r14]
0x180003bd0  mov     r8d, [rdx+rsi*8+4]; Size
0x180003bd5  mov     rdx, [rdx+rsi*8+8]; Src
0x180003bda  call    memcpy_0
0x180003bdf  jmp     short loc_180003C15
0x180003be1  cmp     qword ptr [rax+rsi*8+8], 0
0x180003be7  jnz     short loc_180003C17
0x180003be9  mov     rax, [rdi+8]
0x180003bed  movsxd  rdx, ebp
0x180003bf0  add     rdx, rdx
0x180003bf3  mov     qword ptr [rax+rdx*8+8], 0
0x180003bfc  mov     rax, [rdi+8]
0x180003c00  mov     dword ptr [rax+rdx*8+4], 0
0x180003c08  mov     rax, [r14]
0x180003c0b  mov     rcx, [rdi+8]
0x180003c0f  mov     eax, [rax+rsi*8]
0x180003c12  mov     [rcx+rdx*8], eax
0x180003c15  inc     ebp
0x180003c17  inc     r15d
0x180003c1a  jmp     loc_180003B63
0x180003c1f  mov     al, 1
0x180003c21  mov     rbx, [rsp+48h+arg_0]
0x180003c26  mov     rbp, [rsp+48h+arg_10]
0x180003c2b  add     rsp, 20h
0x180003c2f  pop     r15
0x180003c31  pop     r14
0x180003c33  pop     r12
0x180003c35  pop     rdi
0x180003c36  pop     rsi
0x180003c37  retn
```
