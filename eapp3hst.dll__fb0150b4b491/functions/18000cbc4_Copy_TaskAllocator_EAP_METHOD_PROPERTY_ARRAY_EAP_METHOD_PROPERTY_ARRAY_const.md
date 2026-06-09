# Copy<TaskAllocator>(_EAP_METHOD_PROPERTY_ARRAY &,_EAP_METHOD_PROPERTY_ARRAY const &)

- ea: `0x18000cbc4`
- end: `0x18000cced`
- name: `??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_METHOD_PROPERTY_ARRAY@@AEBU0@@Z`
- size: `297`
- prototype: `char __fastcall(__int64, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000db80`

## callees

- `0x18000cbc4`
- `0x18000cf78`
- `0x18002f4c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cc01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cc82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cc01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cc82`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Copy<TaskAllocator>(__int64 a1, unsigned int *a2)
{
  __int64 v4; // rax
  LPVOID v6; // rax
  __int64 v7; // rbp
  __int64 v8; // rbx
  __int64 v9; // rdx
  int v10; // ecx
  int v11; // ecx
  unsigned int v12; // eax
  __int64 v13; // rdx

  *(_OWORD *)a1 = 0;
  v4 = *a2;
  if ( *((_QWORD *)a2 + 1) )
  {
    if ( (_DWORD)v4 )
    {
      v6 = CoTaskMemAlloc(24 * v4);
      *(_QWORD *)(a1 + 8) = v6;
      if ( v6 )
      {
        v7 = 0;
        *(_DWORD *)a1 = *a2;
        while ( (unsigned int)v7 < *a2 )
        {
          v8 = 3 * v7;
          *(_DWORD *)(*(_QWORD *)(a1 + 8) + 8 * v8) = *(_DWORD *)(*((_QWORD *)a2 + 1) + 24 * v7);
          *(_DWORD *)(*(_QWORD *)(a1 + 8) + 8 * v8 + 4) = *(_DWORD *)(*((_QWORD *)a2 + 1) + 24 * v7 + 4);
          v9 = *((_QWORD *)a2 + 1);
          v10 = *(_DWORD *)(v9 + 24 * v7 + 4);
          if ( v10 && (v11 = v10 - 1) != 0 )
          {
            if ( v11 != 1 )
              goto LABEL_14;
            v12 = *(_DWORD *)(v9 + 24 * v7 + 8);
            if ( *(_QWORD *)(v9 + 24 * v7 + 16) )
            {
              if ( !v12 )
                goto LABEL_14;
            }
            else if ( v12 )
            {
              goto LABEL_14;
            }
            *(_QWORD *)(*(_QWORD *)(a1 + 8) + 24 * v7 + 16) = CoTaskMemAlloc(v12);
            v13 = *(_QWORD *)(a1 + 8);
            if ( !*(_QWORD *)(v13 + 24 * v7 + 16) )
              goto LABEL_14;
            *(_DWORD *)(v13 + 24 * v7 + 8) = *(_DWORD *)(*((_QWORD *)a2 + 1) + 24 * v7 + 8);
            memcpy_0(
              *(void **)(*(_QWORD *)(a1 + 8) + 24 * v7 + 16),
              *(const void **)(*((_QWORD *)a2 + 1) + 24 * v7 + 16),
              *(unsigned int *)(*((_QWORD *)a2 + 1) + 24 * v7 + 8));
          }
          else
          {
            *(_DWORD *)(*(_QWORD *)(a1 + 8) + 24 * v7 + 8) = *(_DWORD *)(v9 + 24 * v7 + 8);
            *(_DWORD *)(*(_QWORD *)(a1 + 8) + 24 * v7 + 12) = *(_DWORD *)(*((_QWORD *)a2 + 1) + 24 * v7 + 12);
          }
          v7 = (unsigned int)(v7 + 1);
        }
        return 1;
      }
LABEL_14:
      Free<TaskAllocator>(a1);
      *(_OWORD *)a1 = 0;
    }
  }
  else if ( !(_DWORD)v4 )
  {
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18000cbc4  push    rbx
0x18000cbc6  push    rbp
0x18000cbc7  push    rsi
0x18000cbc8  push    rdi
0x18000cbc9  sub     rsp, 28h
0x18000cbcd  xorps   xmm0, xmm0
0x18000cbd0  mov     rsi, rdx
0x18000cbd3  movups  xmmword ptr [rcx], xmm0
0x18000cbd6  cmp     qword ptr [rdx+8], 0
0x18000cbdb  mov     rdi, rcx
0x18000cbde  mov     eax, [rdx]
0x18000cbe0  jnz     short loc_18000CBF1
0x18000cbe2  test    eax, eax
0x18000cbe4  jnz     short loc_18000CBF5
0x18000cbe6  mov     al, 1
0x18000cbe8  add     rsp, 28h
0x18000cbec  pop     rdi
0x18000cbed  pop     rsi
0x18000cbee  pop     rbp
0x18000cbef  pop     rbx
0x18000cbf0  retn
0x18000cbf1  test    eax, eax
0x18000cbf3  jnz     short loc_18000CBF9
0x18000cbf5  xor     al, al
0x18000cbf7  jmp     short loc_18000CBE8
0x18000cbf9  lea     rcx, [rax+rax*2]
0x18000cbfd  shl     rcx, 3; cb
0x18000cc01  call    cs:__imp_CoTaskMemAlloc
0x18000cc07  mov     [rdi+8], rax
0x18000cc0b  test    rax, rax
0x18000cc0e  jz      short loc_18000CC69
0x18000cc10  mov     eax, [rsi]
0x18000cc12  xor     ebp, ebp
0x18000cc14  mov     [rdi], eax
0x18000cc16  cmp     ebp, [rsi]
0x18000cc18  jnb     short loc_18000CBE6
0x18000cc1a  mov     rax, [rsi+8]
0x18000cc1e  lea     rbx, ds:0[rbp*2]
0x18000cc26  mov     rcx, [rdi+8]
0x18000cc2a  add     rbx, rbp
0x18000cc2d  mov     eax, [rax+rbx*8]
0x18000cc30  mov     [rcx+rbx*8], eax
0x18000cc33  mov     rax, [rsi+8]
0x18000cc37  mov     rcx, [rdi+8]
0x18000cc3b  mov     eax, [rax+rbx*8+4]
0x18000cc3f  mov     [rcx+rbx*8+4], eax
0x18000cc43  mov     rdx, [rsi+8]
0x18000cc47  mov     ecx, [rdx+rbx*8+4]
0x18000cc4b  test    ecx, ecx
0x18000cc4d  jz      short loc_18000CCCA
0x18000cc4f  sub     ecx, 1
0x18000cc52  jz      short loc_18000CCCA
0x18000cc54  cmp     ecx, 1
0x18000cc57  jnz     short loc_18000CC69
0x18000cc59  cmp     qword ptr [rdx+rbx*8+10h], 0
0x18000cc5f  mov     eax, [rdx+rbx*8+8]
0x18000cc63  jz      short loc_18000CC7C
0x18000cc65  test    eax, eax
0x18000cc67  jnz     short loc_18000CC80
0x18000cc69  mov     rcx, rdi
0x18000cc6c  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_METHOD_PROPERTY_ARRAY@@@Z; Free<TaskAllocator>(_EAP_METHOD_PROPERTY_ARRAY &)
0x18000cc71  xorps   xmm0, xmm0
0x18000cc74  movups  xmmword ptr [rdi], xmm0
0x18000cc77  jmp     loc_18000CBF5
0x18000cc7c  test    eax, eax
0x18000cc7e  jnz     short loc_18000CC69
0x18000cc80  mov     ecx, eax; cb
0x18000cc82  call    cs:__imp_CoTaskMemAlloc
0x18000cc88  mov     rcx, rax
0x18000cc8b  mov     rax, [rdi+8]
0x18000cc8f  mov     [rax+rbx*8+10h], rcx
0x18000cc94  mov     rdx, [rdi+8]
0x18000cc98  cmp     qword ptr [rdx+rbx*8+10h], 0
0x18000cc9e  jz      short loc_18000CC69
0x18000cca0  mov     rax, [rsi+8]
0x18000cca4  mov     ecx, [rax+rbx*8+8]
0x18000cca8  mov     [rdx+rbx*8+8], ecx
0x18000ccac  mov     rdx, [rsi+8]
0x18000ccb0  mov     rcx, [rdi+8]
0x18000ccb4  mov     r8d, [rdx+rbx*8+8]; Size
0x18000ccb9  mov     rdx, [rdx+rbx*8+10h]; Src
0x18000ccbe  mov     rcx, [rcx+rbx*8+10h]; void *
0x18000ccc3  call    memcpy_0
0x18000ccc8  jmp     short loc_18000CCE6
0x18000ccca  mov     rcx, [rdi+8]
0x18000ccce  mov     eax, [rdx+rbx*8+8]
0x18000ccd2  mov     [rcx+rbx*8+8], eax
0x18000ccd6  mov     rax, [rsi+8]
0x18000ccda  mov     rcx, [rdi+8]
0x18000ccde  mov     eax, [rax+rbx*8+0Ch]
0x18000cce2  mov     [rcx+rbx*8+0Ch], eax
0x18000cce6  inc     ebp
0x18000cce8  jmp     loc_18000CC16
```
