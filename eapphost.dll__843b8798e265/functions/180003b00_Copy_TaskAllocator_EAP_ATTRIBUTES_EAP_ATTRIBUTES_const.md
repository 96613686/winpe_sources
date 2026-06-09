# Copy<TaskAllocator>(_EAP_ATTRIBUTES &,_EAP_ATTRIBUTES const &)

- ea: `0x180003b00`
- end: `0x180003d05`
- name: `??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_ATTRIBUTES@@AEBU0@@Z`
- size: `517`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180003ea0`
- `0x180006a80`

## callees

- `0x1800034cc`
- `0x180003b00`
- `0x1800097e0`
- `0x180035138`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003c00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003c72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003c00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003c72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003b53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003b68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003b53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003b68`

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
0x180003b00  mov     [rsp+arg_0], rbx
0x180003b05  mov     [rsp+arg_10], rbp
0x180003b0a  push    rsi
0x180003b0b  push    rdi
0x180003b0c  push    r12
0x180003b0e  push    r14
0x180003b10  push    r15
0x180003b12  sub     rsp, 20h
0x180003b16  xorps   xmm0, xmm0
0x180003b19  lea     r14, [rdx+8]
0x180003b1d  movups  xmmword ptr [rcx], xmm0
0x180003b20  mov     r8d, [rdx]
0x180003b23  xor     ebp, ebp
0x180003b25  mov     r12, rdx
0x180003b28  mov     rdi, rcx
0x180003b2b  test    r8d, r8d
0x180003b2e  jz      short loc_180003B81
0x180003b30  cmp     [r14], rbp
0x180003b33  jnz     short loc_180003B86
0x180003b35  cmp     qword ptr [rdi+8], 0
0x180003b3a  jz      short loc_180003B74
0x180003b3c  test    ebp, ebp
0x180003b3e  js      short loc_180003B64
0x180003b40  mov     rax, [rdi+8]
0x180003b44  mov     ecx, ebp
0x180003b46  add     rcx, rcx
0x180003b49  mov     rcx, [rax+rcx*8+8]; pv
0x180003b4e  test    rcx, rcx
0x180003b51  jz      short loc_180003B5F
0x180003b53  call    cs:__imp_CoTaskMemFree
0x180003b5a  nop     dword ptr [rax+rax+00h]
0x180003b5f  sub     ebp, 1
0x180003b62  jns     short loc_180003B40
0x180003b64  mov     rcx, [rdi+8]; pv
0x180003b68  call    cs:__imp_CoTaskMemFree
0x180003b6f  nop     dword ptr [rax+rax+00h]
0x180003b74  xorps   xmm0, xmm0
0x180003b77  xor     al, al
0x180003b79  movups  xmmword ptr [rdi], xmm0
0x180003b7c  jmp     loc_180003CED
0x180003b81  cmp     [r14], rbp
0x180003b84  jnz     short loc_180003B35
0x180003b86  mov     rdx, [r14]
0x180003b89  test    rdx, rdx
0x180003b8c  jz      loc_180003CEB
0x180003b92  xor     eax, eax
0x180003b94  mov     dword ptr [rsp+48h+cb], eax
0x180003b98  test    r8d, r8d
0x180003b9b  jle     loc_180003CEB
0x180003ba1  xor     r9d, r9d
0x180003ba4  xor     r10d, r10d
0x180003ba7  mov     rcx, r10
0x180003baa  add     rcx, rcx
0x180003bad  mov     r11d, [rdx+rcx*8+4]
0x180003bb2  test    r11d, r11d
0x180003bb5  jz      short loc_180003BC0
0x180003bb7  cmp     [rdx+rcx*8+8], rbp
0x180003bbc  jnz     short loc_180003BC7
0x180003bbe  jmp     short loc_180003BC9
0x180003bc0  cmp     [rdx+rcx*8+8], rbp
0x180003bc5  jnz     short loc_180003BC9
0x180003bc7  inc     eax
0x180003bc9  inc     r9d
0x180003bcc  inc     r10
0x180003bcf  cmp     r9d, r8d
0x180003bd2  jl      short loc_180003BA7
0x180003bd4  mov     dword ptr [rsp+48h+cb], eax
0x180003bd8  test    eax, eax
0x180003bda  jz      loc_180003CEB
0x180003be0  mov     ecx, eax
0x180003be2  lea     rdx, [rsp+48h+cb]; unsigned int *
0x180003be7  shl     rcx, 4; unsigned __int64
0x180003beb  mov     [rdi], eax
0x180003bed  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180003bf2  test    eax, eax
0x180003bf4  js      loc_180003B35
0x180003bfa  mov     ebx, dword ptr [rsp+48h+cb]
0x180003bfe  mov     ecx, ebx; cb
0x180003c00  call    cs:__imp_CoTaskMemAlloc
0x180003c07  nop     dword ptr [rax+rax+00h]
0x180003c0c  mov     [rdi+8], rax
0x180003c10  test    rax, rax
0x180003c13  jz      loc_180003B35
0x180003c19  mov     r8d, ebx; Size
0x180003c1c  xor     edx, edx; Val
0x180003c1e  mov     rcx, rax; void *
0x180003c21  call    memset_0
0x180003c26  xor     r15d, r15d
0x180003c29  cmp     r15d, [r12]
0x180003c2d  jge     loc_180003CEB
0x180003c33  mov     rax, [r14]
0x180003c36  movsxd  rsi, r15d
0x180003c39  add     rsi, rsi
0x180003c3c  mov     ecx, [rax+rsi*8+4]
0x180003c40  test    ecx, ecx
0x180003c42  jz      short loc_180003CAD
0x180003c44  cmp     qword ptr [rax+rsi*8+8], 0
0x180003c4a  jz      loc_180003CE3
0x180003c50  mov     rax, [rdi+8]
0x180003c54  movsxd  rbx, ebp
0x180003c57  add     rbx, rbx
0x180003c5a  mov     [rax+rbx*8+4], ecx
0x180003c5e  mov     rax, [r14]
0x180003c61  mov     rcx, [rdi+8]
0x180003c65  mov     eax, [rax+rsi*8]
0x180003c68  mov     [rcx+rbx*8], eax
0x180003c6b  mov     rax, [r14]
0x180003c6e  mov     ecx, [rax+rsi*8+4]; cb
0x180003c72  call    cs:__imp_CoTaskMemAlloc
0x180003c79  nop     dword ptr [rax+rax+00h]
0x180003c7e  mov     rcx, [rdi+8]
0x180003c82  mov     [rcx+rbx*8+8], rax
0x180003c87  mov     rax, [rdi+8]
0x180003c8b  mov     rcx, [rax+rbx*8+8]; void *
0x180003c90  test    rcx, rcx
0x180003c93  jz      loc_180003B35
0x180003c99  mov     rdx, [r14]
0x180003c9c  mov     r8d, [rdx+rsi*8+4]; Size
0x180003ca1  mov     rdx, [rdx+rsi*8+8]; Src
0x180003ca6  call    memcpy_0
0x180003cab  jmp     short loc_180003CE1
0x180003cad  cmp     qword ptr [rax+rsi*8+8], 0
0x180003cb3  jnz     short loc_180003CE3
0x180003cb5  mov     rax, [rdi+8]
0x180003cb9  movsxd  rdx, ebp
0x180003cbc  add     rdx, rdx
0x180003cbf  mov     qword ptr [rax+rdx*8+8], 0
0x180003cc8  mov     rax, [rdi+8]
0x180003ccc  mov     dword ptr [rax+rdx*8+4], 0
0x180003cd4  mov     rax, [r14]
0x180003cd7  mov     rcx, [rdi+8]
0x180003cdb  mov     eax, [rax+rsi*8]
0x180003cde  mov     [rcx+rdx*8], eax
0x180003ce1  inc     ebp
0x180003ce3  inc     r15d
0x180003ce6  jmp     loc_180003C29
0x180003ceb  mov     al, 1
0x180003ced  mov     rbx, [rsp+48h+arg_0]
0x180003cf2  mov     rbp, [rsp+48h+arg_10]
0x180003cf7  add     rsp, 20h
0x180003cfb  pop     r15
0x180003cfd  pop     r14
0x180003cff  pop     r12
0x180003d01  pop     rdi
0x180003d02  pop     rsi
0x180003d03  retn
```
