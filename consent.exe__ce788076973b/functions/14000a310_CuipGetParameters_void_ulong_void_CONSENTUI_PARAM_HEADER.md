# CuipGetParameters(void *,ulong,void *,_CONSENTUI_PARAM_HEADER * *)

- ea: `0x14000a310`
- end: `0x14000a6a4`
- name: `?CuipGetParameters@@YAJPEAXK0PEAPEAU_CONSENTUI_PARAM_HEADER@@@Z`
- size: `916`
- prototype: `__int64 __fastcall(HANDLE SourceProcessHandle, SIZE_T NumberOfBytesToRead, PVOID BaseAddress, struct _CONSENTUI_PARAM_HEADER **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001a080`

## callees

- `0x14000a310`
- `0x14001e050`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x14000a44b`
- `ntdll!EtwEventWrite` at `0x14000a44b`
- `ntdll!RtlFreeHeap` at `0x14000a65b`
- `ntdll!RtlFreeHeap` at `0x14000a65b`
- `ntdll!NtReadVirtualMemory` at `0x14000a38b`
- `ntdll!NtReadVirtualMemory` at `0x14000a38b`
- `ntdll!RtlAllocateHeap` at `0x14000a355`
- `ntdll!RtlAllocateHeap` at `0x14000a355`
- `ntdll!NtDuplicateObject` at `0x14000a3c7`
- `ntdll!NtDuplicateObject` at `0x14000a406`
- `ntdll!NtDuplicateObject` at `0x14000a5a9`
- `ntdll!NtDuplicateObject` at `0x14000a3c7`
- `ntdll!NtDuplicateObject` at `0x14000a406`
- `ntdll!NtDuplicateObject` at `0x14000a5a9`
- `ntdll!NtClose` at `0x14000a62c`
- `ntdll!NtClose` at `0x14000a63f`
- `ntdll!NtClose` at `0x14000a62c`
- `ntdll!NtClose` at `0x14000a63f`

## pseudocode

```c
__int64 __fastcall CuipGetParameters(
        HANDLE SourceProcessHandle,
        SIZE_T NumberOfBytesToRead,
        PVOID BaseAddress,
        struct _CONSENTUI_PARAM_HEADER **a4)
{
  SIZE_T v5; // r14
  char *Heap; // rax
  char *v9; // rbx
  NTSTATUS VirtualMemory; // edi
  void *v12; // rdx
  char v13; // r12
  void *v14; // rdx
  char v15; // bp
  unsigned int v16; // r8d
  __int64 v17; // rax
  __int64 v18; // rdx
  __int128 v19; // [rsp+40h] [rbp-68h] BYREF

  v5 = (unsigned int)NumberOfBytesToRead;
  v19 = 0;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)NumberOfBytesToRead);
  v9 = Heap;
  if ( !Heap )
    return 3221225495LL;
  VirtualMemory = NtReadVirtualMemory(SourceProcessHandle, BaseAddress, Heap, v5, 0);
  if ( VirtualMemory < 0 )
    goto LABEL_25;
  v12 = (void *)*((_QWORD *)v9 + 3);
  v13 = 0;
  if ( !v12 )
  {
LABEL_7:
    v14 = (void *)*((_QWORD *)v9 + 5);
    v15 = 0;
    if ( v14 )
    {
      VirtualMemory = NtDuplicateObject(
                        SourceProcessHandle,
                        v14,
                        (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                        (PHANDLE)v9 + 5,
                        0,
                        0,
                        2u);
      if ( VirtualMemory < 0 )
      {
LABEL_21:
        if ( v13 )
        {
          NtClose(*((HANDLE *)v9 + 3));
          *((_QWORD *)v9 + 3) = 0;
        }
        if ( v15 )
        {
          NtClose(*((HANDLE *)v9 + 5));
          *((_QWORD *)v9 + 5) = 0;
        }
        goto LABEL_25;
      }
      v15 = 1;
    }
    if ( *((int *)v9 + 2) < 4 )
    {
      *(_QWORD *)&v19 = v9;
      *((_QWORD *)&v19 + 1) = (unsigned int)v5;
      EtwEventWrite(g_ConsentPerfRegHandle, ConsentUI_ExecutableCommandLine_Info, 1, &v19);
      switch ( *((_DWORD *)v9 + 1) )
      {
        case 0:
          *((_QWORD *)v9 + 26) = &v9[*((unsigned int *)v9 + 52)];
          *((_QWORD *)v9 + 27) = &v9[*((unsigned int *)v9 + 54)];
          *((_QWORD *)v9 + 28) = &v9[*((unsigned int *)v9 + 56)];
          *((_QWORD *)v9 + 29) = &v9[*((unsigned int *)v9 + 58)];
          VirtualMemory = NtDuplicateObject(
                            SourceProcessHandle,
                            *((HANDLE *)v9 + 25),
                            (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                            (PHANDLE)v9 + 25,
                            0,
                            0,
                            2u);
          if ( VirtualMemory < 0 )
            goto LABEL_21;
          break;
        case 1:
        case 5:
          *((_QWORD *)v9 + 25) = &v9[*((unsigned int *)v9 + 50)];
          *((_QWORD *)v9 + 26) = &v9[*((unsigned int *)v9 + 52)];
          *((_QWORD *)v9 + 27) = &v9[*((unsigned int *)v9 + 54)];
          *((_QWORD *)v9 + 28) = &v9[*((unsigned int *)v9 + 56)];
          break;
        case 2:
          v16 = 0;
          *((_QWORD *)v9 + 26) = &v9[*((unsigned int *)v9 + 52)];
          *((_QWORD *)v9 + 27) = &v9[*((unsigned int *)v9 + 54)];
          *((_QWORD *)v9 + 28) = &v9[*((unsigned int *)v9 + 56)];
          *((_QWORD *)v9 + 29) = &v9[*((unsigned int *)v9 + 58)];
          *((_QWORD *)v9 + 30) = &v9[*((unsigned int *)v9 + 60)];
          *((_QWORD *)v9 + 31) = &v9[*((unsigned int *)v9 + 62)];
          *((_QWORD *)v9 + 33) = &v9[*((unsigned int *)v9 + 66)];
          for ( *((_QWORD *)v9 + 34) = &v9[*((unsigned int *)v9 + 68)];
                v16 < *((_DWORD *)v9 + 64);
                *(_QWORD *)(*((_QWORD *)v9 + 34) + v18) = &v9[*(unsigned int *)(*((_QWORD *)v9 + 34) + 8 * v17)] )
          {
            v17 = v16++;
            v18 = 8 * v17;
            *(_QWORD *)(*((_QWORD *)v9 + 33) + v18) = &v9[*(unsigned int *)(*((_QWORD *)v9 + 33) + 8 * v17)];
          }
          break;
        case 3:
          *((_QWORD *)v9 + 25) = &v9[*((unsigned int *)v9 + 50)];
          *((_QWORD *)v9 + 26) = &v9[*((unsigned int *)v9 + 52)];
          break;
        case 4:
        case 6:
          break;
        default:
          goto LABEL_20;
      }
      *a4 = (struct _CONSENTUI_PARAM_HEADER *)v9;
      return (unsigned int)VirtualMemory;
    }
LABEL_20:
    VirtualMemory = -1073741811;
    goto LABEL_21;
  }
  VirtualMemory = NtDuplicateObject(SourceProcessHandle, v12, (HANDLE)0xFFFFFFFFFFFFFFFFLL, (PHANDLE)v9 + 3, 0, 0, 2u);
  if ( VirtualMemory >= 0 )
  {
    v13 = 1;
    goto LABEL_7;
  }
LABEL_25:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  return (unsigned int)VirtualMemory;
}

```

## disassembly

```asm
0x14000a310  push    rbx
0x14000a312  push    rbp
0x14000a313  push    rsi
0x14000a314  push    rdi
0x14000a315  push    r14
0x14000a317  push    r15
0x14000a319  sub     rsp, 78h
0x14000a31d  mov     rax, cs:__security_cookie
0x14000a324  xor     rax, rsp
0x14000a327  mov     [rsp+0A8h+var_58], rax
0x14000a32c  mov     rsi, rcx
0x14000a32f  mov     r14d, edx
0x14000a332  xorps   xmm0, xmm0
0x14000a335  mov     rbp, r8
0x14000a338  movups  [rsp+0A8h+var_68], xmm0
0x14000a33d  mov     rcx, gs:60h
0x14000a346  mov     r15, r9
0x14000a349  mov     r8d, edx; Size
0x14000a34c  mov     edx, 8; Flags
0x14000a351  mov     rcx, [rcx+30h]; HeapHandle
0x14000a355  call    cs:__imp_RtlAllocateHeap
0x14000a35b  mov     rbx, rax
0x14000a35e  test    rax, rax
0x14000a361  jnz     short loc_14000A36D
0x14000a363  mov     eax, 0C0000017h
0x14000a368  jmp     loc_14000A66D
0x14000a36d  mov     [rsp+0A8h+var_38], r12
0x14000a372  mov     r9, r14; NumberOfBytesToRead
0x14000a375  mov     [rsp+0A8h+var_40], r13
0x14000a37a  mov     r8, rbx; Buffer
0x14000a37d  xor     r13d, r13d
0x14000a380  mov     rdx, rbp; BaseAddress
0x14000a383  mov     rcx, rsi; ProcessHandle
0x14000a386  mov     [rsp+0A8h+NumberOfBytesRead], r13; NumberOfBytesRead
0x14000a38b  call    cs:__imp_NtReadVirtualMemory
0x14000a391  mov     edi, eax
0x14000a393  test    eax, eax
0x14000a395  js      loc_14000A649
0x14000a39b  mov     rdx, [rbx+18h]; SourceHandle
0x14000a39f  lea     r9, [rbx+18h]; TargetHandle
0x14000a3a3  xor     r12b, r12b
0x14000a3a6  test    rdx, rdx
0x14000a3a9  jz      short loc_14000A3DA
0x14000a3ab  mov     [rsp+0A8h+Options], 2; Options
0x14000a3b3  mov     r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x14000a3ba  mov     [rsp+0A8h+HandleAttributes], r13d; HandleAttributes
0x14000a3bf  mov     rcx, rsi; SourceProcessHandle
0x14000a3c2  mov     dword ptr [rsp+0A8h+NumberOfBytesRead], r13d; DesiredAccess
0x14000a3c7  call    cs:__imp_NtDuplicateObject
0x14000a3cd  mov     edi, eax
0x14000a3cf  test    eax, eax
0x14000a3d1  js      loc_14000A649
0x14000a3d7  mov     r12b, 1
0x14000a3da  mov     rdx, [rbx+28h]; SourceHandle
0x14000a3de  lea     r9, [rbx+28h]; TargetHandle
0x14000a3e2  xor     bpl, bpl
0x14000a3e5  test    rdx, rdx
0x14000a3e8  jz      short loc_14000A419
0x14000a3ea  mov     [rsp+0A8h+Options], 2; Options
0x14000a3f2  mov     r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x14000a3f9  mov     [rsp+0A8h+HandleAttributes], r13d; HandleAttributes
0x14000a3fe  mov     rcx, rsi; SourceProcessHandle
0x14000a401  mov     dword ptr [rsp+0A8h+NumberOfBytesRead], r13d; DesiredAccess
0x14000a406  call    cs:__imp_NtDuplicateObject
0x14000a40c  mov     edi, eax
0x14000a40e  test    eax, eax
0x14000a410  js      loc_14000A623
0x14000a416  mov     bpl, 1
0x14000a419  cmp     dword ptr [rbx+8], 4
0x14000a41d  jge     def_14000A46F; jumptable 000000014000A46F default case
0x14000a423  mov     rcx, cs:?g_ConsentPerfRegHandle@@3_KA; unsigned __int64 g_ConsentPerfRegHandle
0x14000a42a  lea     r9, [rsp+0A8h+var_68]
0x14000a42f  mov     r8d, 1
0x14000a435  mov     qword ptr [rsp+0A8h+var_68], rbx
0x14000a43a  lea     rdx, ConsentUI_ExecutableCommandLine_Info
0x14000a441  mov     dword ptr [rsp+0A8h+var_68+8], r14d
0x14000a446  mov     dword ptr [rsp+0A8h+var_68+0Ch], r13d
0x14000a44b  call    cs:__imp_EtwEventWrite
0x14000a451  movsxd  rax, dword ptr [rbx+4]
0x14000a455  cmp     eax, 6; switch 7 cases
0x14000a458  ja      def_14000A46F; jumptable 000000014000A46F default case
0x14000a45e  lea     rdx, __ImageBase
0x14000a465  mov     ecx, ds:(jpt_14000A46F - 140000000h)[rdx+rax*4]
0x14000a46c  add     rcx, rdx
0x14000a46f  jmp     rcx; switch jump
0x14000a471  mov     eax, [rbx+0D0h]; jumptable 000000014000A46F case 2
0x14000a477  mov     r8d, r13d
0x14000a47a  add     rax, rbx
0x14000a47d  mov     [rbx+0D0h], rax
0x14000a484  mov     eax, [rbx+0D8h]
0x14000a48a  add     rax, rbx
0x14000a48d  mov     [rbx+0D8h], rax
0x14000a494  mov     eax, [rbx+0E0h]
0x14000a49a  add     rax, rbx
0x14000a49d  mov     [rbx+0E0h], rax
0x14000a4a4  mov     eax, [rbx+0E8h]
0x14000a4aa  add     rax, rbx
0x14000a4ad  mov     [rbx+0E8h], rax
0x14000a4b4  mov     eax, [rbx+0F0h]
0x14000a4ba  add     rax, rbx
0x14000a4bd  mov     [rbx+0F0h], rax
0x14000a4c4  mov     eax, [rbx+0F8h]
0x14000a4ca  add     rax, rbx
0x14000a4cd  mov     [rbx+0F8h], rax
0x14000a4d4  mov     eax, [rbx+108h]
0x14000a4da  add     rax, rbx
0x14000a4dd  mov     [rbx+108h], rax
0x14000a4e4  mov     eax, [rbx+110h]
0x14000a4ea  add     rax, rbx
0x14000a4ed  mov     [rbx+110h], rax
0x14000a4f4  cmp     [rbx+100h], r13d
0x14000a4fb  jbe     loc_14000A619; jumptable 000000014000A46F cases 4,6
0x14000a501  mov     rcx, [rbx+108h]
0x14000a508  mov     eax, r8d
0x14000a50b  inc     r8d
0x14000a50e  lea     rdx, ds:0[rax*8]
0x14000a516  mov     eax, [rcx+rax*8]
0x14000a519  add     rax, rbx
0x14000a51c  mov     [rcx+rdx], rax
0x14000a520  mov     rcx, [rbx+110h]
0x14000a527  mov     eax, [rcx+rdx]
0x14000a52a  add     rax, rbx
0x14000a52d  mov     [rcx+rdx], rax
0x14000a531  cmp     r8d, [rbx+100h]
0x14000a538  jb      short loc_14000A501
0x14000a53a  jmp     loc_14000A619; jumptable 000000014000A46F cases 4,6
0x14000a53f  mov     eax, [rbx+0D0h]; jumptable 000000014000A46F case 0
0x14000a545  lea     r9, [rbx+0C8h]; TargetHandle
0x14000a54c  add     rax, rbx
0x14000a54f  mov     [rsp+0A8h+Options], 2; Options
0x14000a557  mov     [rbx+0D0h], rax
0x14000a55e  mov     r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x14000a565  mov     eax, [rbx+0D8h]
0x14000a56b  mov     rcx, rsi; SourceProcessHandle
0x14000a56e  add     rax, rbx
0x14000a571  mov     [rsp+0A8h+HandleAttributes], r13d; HandleAttributes
0x14000a576  mov     [rbx+0D8h], rax
0x14000a57d  mov     eax, [rbx+0E0h]
0x14000a583  add     rax, rbx
0x14000a586  mov     dword ptr [rsp+0A8h+NumberOfBytesRead], r13d; DesiredAccess
0x14000a58b  mov     [rbx+0E0h], rax
0x14000a592  mov     eax, [rbx+0E8h]
0x14000a598  add     rax, rbx
0x14000a59b  mov     [rbx+0E8h], rax
0x14000a5a2  mov     rdx, [rbx+0C8h]; SourceHandle
0x14000a5a9  call    cs:__imp_NtDuplicateObject
0x14000a5af  mov     edi, eax
0x14000a5b1  test    eax, eax
0x14000a5b3  jns     short loc_14000A619; jumptable 000000014000A46F cases 4,6
0x14000a5b5  jmp     short loc_14000A623
0x14000a5b7  mov     eax, [rbx+0C8h]; jumptable 000000014000A46F case 3
0x14000a5bd  add     rax, rbx
0x14000a5c0  mov     [rbx+0C8h], rax
0x14000a5c7  mov     eax, [rbx+0D0h]
0x14000a5cd  add     rax, rbx
0x14000a5d0  mov     [rbx+0D0h], rax
0x14000a5d7  jmp     short loc_14000A619; jumptable 000000014000A46F cases 4,6
0x14000a5d9  mov     eax, [rbx+0C8h]; jumptable 000000014000A46F cases 1,5
0x14000a5df  add     rax, rbx
0x14000a5e2  mov     [rbx+0C8h], rax
0x14000a5e9  mov     eax, [rbx+0D0h]
0x14000a5ef  add     rax, rbx
0x14000a5f2  mov     [rbx+0D0h], rax
0x14000a5f9  mov     eax, [rbx+0D8h]
0x14000a5ff  add     rax, rbx
0x14000a602  mov     [rbx+0D8h], rax
0x14000a609  mov     eax, [rbx+0E0h]
0x14000a60f  add     rax, rbx
0x14000a612  mov     [rbx+0E0h], rax
0x14000a619  mov     [r15], rbx; jumptable 000000014000A46F cases 4,6
0x14000a61c  jmp     short loc_14000A661
0x14000a61e  mov     edi, 0C000000Dh; jumptable 000000014000A46F default case
0x14000a623  test    r12b, r12b
0x14000a626  jz      short loc_14000A636
0x14000a628  mov     rcx, [rbx+18h]; Handle
0x14000a62c  call    cs:__imp_NtClose
0x14000a632  mov     [rbx+18h], r13
0x14000a636  test    bpl, bpl
0x14000a639  jz      short loc_14000A649
0x14000a63b  mov     rcx, [rbx+28h]; Handle
0x14000a63f  call    cs:__imp_NtClose
0x14000a645  mov     [rbx+28h], r13
0x14000a649  mov     rcx, gs:60h
0x14000a652  mov     r8, rbx; P
0x14000a655  xor     edx, edx; Flags
0x14000a657  mov     rcx, [rcx+30h]; HeapHandle
0x14000a65b  call    cs:__imp_RtlFreeHeap
0x14000a661  mov     r12, [rsp+0A8h+var_38]
0x14000a666  mov     eax, edi
0x14000a668  mov     r13, [rsp+0A8h+var_40]
0x14000a66d  mov     rcx, [rsp+0A8h+var_58]
0x14000a672  xor     rcx, rsp; StackCookie
0x14000a675  call    __security_check_cookie
0x14000a67a  add     rsp, 78h
0x14000a67e  pop     r15
0x14000a680  pop     r14
0x14000a682  pop     rdi
0x14000a683  pop     rsi
0x14000a684  pop     rbp
0x14000a685  pop     rbx
0x14000a686  retn
```
