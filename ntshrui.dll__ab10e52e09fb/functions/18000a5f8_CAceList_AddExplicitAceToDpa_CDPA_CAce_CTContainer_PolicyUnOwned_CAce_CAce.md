# CAceList::_AddExplicitAceToDpa(CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &,CAce *)

- ea: `0x18000a5f8`
- end: `0x18000a7f3`
- name: `?_AddExplicitAceToDpa@CAceList@@AEAAJAEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@PEAVCAce@@@Z`
- size: `507`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000a800`
- `0x18000ac90`
- `0x18000b240`
- `0x18000b6f0`
- `0x18000c6f0`
- `0x18000dd60`

## callees

- `0x18000a5f8`
- `0x18000f7a0`
- `0x18000f7f0`
- `0x180026370`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a733`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a733`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000a676`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000a706`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000a676`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000a706`

## pseudocode

```c
__int64 __fastcall CAceList::_AddExplicitAceToDpa(__int64 a1, int **a2, __int64 a3)
{
  int v5; // r15d
  int v6; // ebp
  unsigned int v7; // esi
  int *v8; // rbx
  __int64 v9; // rbx
  bool v10; // cl
  BOOL v11; // eax
  __int64 (__fastcall *v12)(int *, __int64, __int64); // rax
  int *v13; // rbx
  int v14; // eax

  if ( *a2 )
    v5 = **a2;
  else
    v5 = 0;
  v6 = 0;
  v7 = 1;
  while ( 1 )
  {
    if ( v6 >= v5 )
      goto LABEL_19;
    v8 = *a2;
    if ( qword_180095A20 == (__int64 (__fastcall *)(_QWORD, _QWORD))-1LL )
    {
      if ( g_hinstCC || (DelayLoadCC(), g_hinstCC) )
        qword_180095A20 = (__int64 (__fastcall *)(_QWORD, _QWORD))GetProcAddress(g_hinstCC, (LPCSTR)0x14C);
      else
        qword_180095A20 = 0;
    }
    v9 = qword_180095A20 ? qword_180095A20(v8, v6) : 0LL;
    if ( a3 )
      break;
    if ( !*(_DWORD *)(v9 + 24) )
    {
      v11 = EqualSid(*(PSID *)(v9 + 8), 0);
      goto LABEL_16;
    }
LABEL_17:
    ++v6;
  }
  v10 = 0;
  if ( *(int *)(a3 + 28) < 0 && *(int *)(v9 + 28) < 0 )
  {
    v10 = EqualSid(*(PSID *)(a3 + 8), *(PSID *)(v9 + 8))
       && *(_DWORD *)(a3 + 28) == *(_DWORD *)(v9 + 28)
       && *(_DWORD *)(a3 + 4) == *(_DWORD *)(v9 + 4)
       && *(_BYTE *)(a3 + 1) == *(_BYTE *)(v9 + 1)
       && *(_BYTE *)a3 == *(_BYTE *)v9
       && *(_DWORD *)(a3 + 24) == *(_DWORD *)(v9 + 24);
    if ( *(_QWORD *)(v9 + 16) != 0 && v10 )
      v10 = memcmp_0(*(const void **)(v9 + 16), *(const void **)(a3 + 16), *(unsigned int *)(v9 + 24)) == 0;
  }
  v11 = v10;
LABEL_16:
  if ( !v11 )
    goto LABEL_17;
  if ( !v9 )
  {
LABEL_19:
    v12 = (__int64 (__fastcall *)(int *, __int64, __int64))qword_1800959F8;
    v13 = *a2;
    if ( qword_1800959F8 == -1 )
    {
      GetProcFromComCtl32(&qword_1800959F8, 334);
      v12 = (__int64 (__fastcall *)(int *, __int64, __int64))qword_1800959F8;
    }
    if ( v12 )
      v14 = v12(v13, 0x7FFFFFFF, a3);
    else
      v14 = -1;
    v7 = 0;
    if ( v14 == -1 )
      return (unsigned int)-2147024882;
    return v7;
  }
  if ( a3 )
    *(_DWORD *)(v9 + 4) |= *(_DWORD *)(a3 + 4);
  return v7;
}

```

## disassembly

```asm
0x18000a5f8  push    rbx
0x18000a5fa  push    rbp
0x18000a5fb  push    rsi
0x18000a5fc  push    rdi
0x18000a5fd  push    r14
0x18000a5ff  push    r15
0x18000a601  sub     rsp, 28h
0x18000a605  mov     rax, [rdx]
0x18000a608  mov     rdi, r8
0x18000a60b  mov     r14, rdx
0x18000a60e  test    rax, rax
0x18000a611  jz      loc_18000A769
0x18000a617  mov     r15d, [rax]
0x18000a61a  xor     ebp, ebp
0x18000a61c  lea     esi, [rbp+1]
0x18000a61f  cmp     ebp, r15d
0x18000a622  jge     loc_18000A6B1
0x18000a628  cmp     cs:qword_180095A20, 0FFFFFFFFFFFFFFFFh
0x18000a630  mov     rbx, [r14]
0x18000a633  jz      loc_18000A70E
0x18000a639  mov     rax, cs:qword_180095A20
0x18000a640  test    rax, rax
0x18000a643  jz      loc_18000A745
0x18000a649  movsxd  rdx, ebp
0x18000a64c  mov     rcx, rbx
0x18000a64f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a654  mov     rbx, rax
0x18000a657  test    rdi, rdi
0x18000a65a  jz      loc_18000A6FA
0x18000a660  xor     cl, cl
0x18000a662  cmp     dword ptr [rdi+1Ch], 0
0x18000a666  jge     short loc_18000A69A
0x18000a668  cmp     dword ptr [rbx+1Ch], 0
0x18000a66c  jge     short loc_18000A69A
0x18000a66e  mov     rdx, [rbx+8]; pSid2
0x18000a672  mov     rcx, [rdi+8]; pSid1
0x18000a676  call    cs:__imp_EqualSid
0x18000a67c  test    eax, eax
0x18000a67e  jnz     loc_18000A771
0x18000a684  xor     cl, cl
0x18000a686  mov     rax, [rbx+10h]
0x18000a68a  neg     rax
0x18000a68d  movzx   edx, cl
0x18000a690  sbb     eax, eax
0x18000a692  test    edx, eax
0x18000a694  jnz     loc_18000A7B3
0x18000a69a  movzx   eax, cl
0x18000a69d  test    eax, eax
0x18000a69f  jnz     short loc_18000A6A8
0x18000a6a1  add     ebp, esi
0x18000a6a3  jmp     loc_18000A61F
0x18000a6a8  test    rbx, rbx
0x18000a6ab  jnz     loc_18000A75C
0x18000a6b1  mov     rax, cs:qword_1800959F8
0x18000a6b8  mov     rbx, [r14]
0x18000a6bb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a6bf  jz      loc_18000A7CE
0x18000a6c5  test    rax, rax
0x18000a6c8  jz      loc_18000A7EB
0x18000a6ce  mov     r8, rdi
0x18000a6d1  mov     edx, 7FFFFFFFh
0x18000a6d6  mov     rcx, rbx
0x18000a6d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6de  xor     esi, esi
0x18000a6e0  mov     ecx, 8007000Eh
0x18000a6e5  cmp     eax, 0FFFFFFFFh
0x18000a6e8  cmovz   esi, ecx
0x18000a6eb  mov     eax, esi
0x18000a6ed  add     rsp, 28h
0x18000a6f1  pop     r15
0x18000a6f3  pop     r14
0x18000a6f5  pop     rdi
0x18000a6f6  pop     rsi
0x18000a6f7  pop     rbp
0x18000a6f8  pop     rbx
0x18000a6f9  retn
0x18000a6fa  cmp     dword ptr [rbx+18h], 0
0x18000a6fe  jnz     short loc_18000A6A1
0x18000a700  mov     rcx, [rbx+8]; pSid1
0x18000a704  xor     edx, edx; pSid2
0x18000a706  call    cs:__imp_EqualSid
0x18000a70c  jmp     short loc_18000A69D
0x18000a70e  cmp     cs:g_hinstCC, 0
0x18000a716  jnz     short loc_18000A727
0x18000a718  call    DelayLoadCC
0x18000a71d  cmp     cs:g_hinstCC, 0
0x18000a725  jz      short loc_18000A74C
0x18000a727  mov     rcx, cs:g_hinstCC; hModule
0x18000a72e  mov     edx, 14Ch; lpProcName
0x18000a733  call    cs:__imp_GetProcAddress
0x18000a739  mov     cs:qword_180095A20, rax
0x18000a740  jmp     loc_18000A639
0x18000a745  xor     ebx, ebx
0x18000a747  jmp     loc_18000A657
0x18000a74c  mov     cs:qword_180095A20, 0
0x18000a757  jmp     loc_18000A639
0x18000a75c  test    rdi, rdi
0x18000a75f  jz      short loc_18000A6EB
0x18000a761  mov     eax, [rdi+4]
0x18000a764  or      [rbx+4], eax
0x18000a767  jmp     short loc_18000A6EB
0x18000a769  xor     r15d, r15d
0x18000a76c  jmp     loc_18000A61A
0x18000a771  mov     eax, [rbx+1Ch]
0x18000a774  cmp     [rdi+1Ch], eax
0x18000a777  jnz     loc_18000A684
0x18000a77d  mov     eax, [rbx+4]
0x18000a780  cmp     [rdi+4], eax
0x18000a783  jnz     loc_18000A684
0x18000a789  mov     al, [rbx+1]
0x18000a78c  cmp     [rdi+1], al
0x18000a78f  jnz     loc_18000A684
0x18000a795  mov     al, [rbx]
0x18000a797  cmp     [rdi], al
0x18000a799  jnz     loc_18000A684
0x18000a79f  mov     eax, [rbx+18h]
0x18000a7a2  cmp     [rdi+18h], eax
0x18000a7a5  jnz     loc_18000A684
0x18000a7ab  mov     cl, sil
0x18000a7ae  jmp     loc_18000A686
0x18000a7b3  mov     r8d, [rbx+18h]; Size
0x18000a7b7  mov     rdx, [rdi+10h]; Buf2
0x18000a7bb  mov     rcx, [rbx+10h]; Buf1
0x18000a7bf  call    memcmp_0
0x18000a7c4  test    eax, eax
0x18000a7c6  setz    cl
0x18000a7c9  jmp     loc_18000A69A
0x18000a7ce  mov     edx, 14Eh
0x18000a7d3  lea     rcx, qword_1800959F8
0x18000a7da  call    _GetProcFromComCtl32
0x18000a7df  mov     rax, cs:qword_1800959F8
0x18000a7e6  jmp     loc_18000A6C5
0x18000a7eb  or      eax, 0FFFFFFFFh
0x18000a7ee  jmp     loc_18000A6DE
```
