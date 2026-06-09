# SpDeleteContext(unsigned __int64)

- ea: `0x18000c7d0`
- end: `0x18000ca00`
- name: `?SpDeleteContext@@YAJ_K@Z`
- size: `560`
- prototype: `__int64 __fastcall(struct _WST_CONTEXT *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180008544`
- `0x180008c58`
- `0x18000c528`
- `0x18000c7d0`
- `0x18000ca08`
- `0x18000cc6c`
- `0x18000ffa4`
- `0x180015aa8`
- `0x18001a390`
- `0x18001cff0`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall SpDeleteContext(struct _WST_CONTEXT *a1)
{
  struct _WST_SSP_PACKAGE *v3; // r14
  PVOID *v4; // r10
  _DWORD *v5; // rbx
  unsigned int i; // ebx
  struct _WST_ACTIVE_ENGINE_CONTEXT *v7; // r13
  void (__fastcall *v8)(_QWORD, __int64, _QWORD); // rax

  v3 = 0;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_6fa7dbc14d303f0b349d28a6dba66ee3_Traceguids, a1);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    {
      WPP_SF_qDDZ(
        (TRACEHANDLE)v4[2],
        *(_DWORD *)(*((_QWORD *)a1 + 3) + 44LL),
        *(_DWORD *)(*((_QWORD *)a1 + 3) + 40LL),
        (__int64)a1 + 168);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( *((_DWORD *)a1 + 66) )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
      WPP_SF_qDDZ(
        (TRACEHANDLE)v4[2],
        *(_DWORD *)(*((_QWORD *)a1 + 3) + 44LL),
        *(_DWORD *)(*((_QWORD *)a1 + 3) + 40LL),
        (__int64)a1 + 168);
    WSTContextByTargetTableInsert(a1);
    *((_DWORD *)a1 + 66) = 0;
    v5 = (_DWORD *)((char *)a1 + 156);
    goto LABEL_18;
  }
  v5 = (_DWORD *)((char *)a1 + 156);
  if ( !*((_DWORD *)a1 + 39) )
  {
    if ( *((_DWORD *)a1 + 12) != 7 && *((_DWORD *)a1 + 12) && *((_DWORD *)a1 + 12) != 5 && *((_WORD *)a1 + 76) )
      WSTContextTableInsert(a1);
LABEL_18:
    if ( !*v5 )
      goto LABEL_26;
  }
  for ( i = 0; i < *((unsigned __int16 *)a1 + 76); ++i )
  {
    v7 = WSTGetActiveContextByAuthScheme(a1, (struct _GUID *)(*((_QWORD *)a1 + 18) + 16LL * i));
    if ( v3 )
      WSTDereferencePackage(v3);
    v3 = WSTLocatePackageByAuthScheme((struct _GUID *)((char *)v7 + 24));
    v8 = (void (__fastcall *)(_QWORD, __int64, _QWORD))*((_QWORD *)v3 + 31);
    if ( v8 )
      v8(*((_QWORD *)v7 + 5), 33, 0);
  }
LABEL_26:
  WSTDereferenceContext(a1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_6fa7dbc14d303f0b349d28a6dba66ee3_Traceguids, a1);
  if ( v3 )
    WSTDereferencePackage(v3);
  return 0;
}

```

## disassembly

```asm
0x18000c7d0  mov     [rsp+arg_0], rcx
0x18000c7d5  push    rbx
0x18000c7d6  push    rsi
0x18000c7d7  push    rdi
0x18000c7d8  push    r12
0x18000c7da  push    r13
0x18000c7dc  push    r14
0x18000c7de  push    r15
0x18000c7e0  sub     rsp, 50h
0x18000c7e4  mov     rdi, rcx
0x18000c7e7  mov     r15, rcx
0x18000c7ea  mov     [rsp+88h+arg_10], rcx
0x18000c7f2  xor     esi, esi
0x18000c7f4  mov     r14d, esi
0x18000c7f7  lea     r12, WPP_GLOBAL_Control
0x18000c7fe  mov     r10, cs:WPP_GLOBAL_Control
0x18000c805  cmp     r10, r12
0x18000c808  jz      short loc_18000C877
0x18000c80a  test    byte ptr [r10+1Ch], 8
0x18000c80f  jz      short loc_18000C82E
0x18000c811  lea     edx, [rsi+27h]
0x18000c814  mov     r9, rcx
0x18000c817  lea     r8, WPP_6fa7dbc14d303f0b349d28a6dba66ee3_Traceguids
0x18000c81e  mov     rcx, [r10+10h]
0x18000c822  call    WPP_SF_q
0x18000c827  mov     r10, cs:WPP_GLOBAL_Control
0x18000c82e  cmp     r10, r12
0x18000c831  jz      short loc_18000C877
0x18000c833  test    byte ptr [r10+1Ch], 20h
0x18000c838  jz      short loc_18000C877
0x18000c83a  mov     rcx, [rdi+18h]
0x18000c83e  lea     rax, [rdi+0A8h]
0x18000c845  mov     edx, 28h ; '('
0x18000c84a  mov     [rsp+88h+var_58], rax; __int64
0x18000c84f  mov     eax, [rcx+28h]
0x18000c852  mov     dword ptr [rsp+88h+var_60], eax; char
0x18000c856  mov     eax, [rcx+2Ch]
0x18000c859  mov     dword ptr [rsp+88h+var_68], eax; char
0x18000c85d  mov     r9, rdi
0x18000c860  lea     r8, WPP_6fa7dbc14d303f0b349d28a6dba66ee3_Traceguids
0x18000c867  mov     rcx, [r10+10h]; LoggerHandle
0x18000c86b  call    WPP_SF_qDDZ
0x18000c870  mov     r10, cs:WPP_GLOBAL_Control
0x18000c877  cmp     [rdi+108h], esi
0x18000c87d  jz      short loc_18000C8D8
0x18000c87f  cmp     r10, r12
0x18000c882  jz      short loc_18000C8C1
0x18000c884  test    byte ptr [r10+1Ch], 2
0x18000c889  jz      short loc_18000C8C1
0x18000c88b  mov     rcx, [rdi+18h]
0x18000c88f  lea     rax, [rdi+0A8h]
0x18000c896  mov     edx, 29h ; ')'
0x18000c89b  mov     [rsp+88h+var_58], rax; __int64
0x18000c8a0  mov     eax, [rcx+28h]
0x18000c8a3  mov     dword ptr [rsp+88h+var_60], eax; char
0x18000c8a7  mov     eax, [rcx+2Ch]
0x18000c8aa  mov     dword ptr [rsp+88h+var_68], eax; char
0x18000c8ae  mov     r9, rdi
0x18000c8b1  lea     r8, WPP_6fa7dbc14d303f0b349d28a6dba66ee3_Traceguids
0x18000c8b8  mov     rcx, [r10+10h]; LoggerHandle
0x18000c8bc  call    WPP_SF_qDDZ
0x18000c8c1  mov     rcx, rdi; struct _WST_CONTEXT *
0x18000c8c4  call    ?WSTContextByTargetTableInsert@@YAJPEAU_WST_CONTEXT@@@Z; WSTContextByTargetTableInsert(_WST_CONTEXT *)
0x18000c8c9  mov     [rdi+108h], esi
0x18000c8cf  lea     rbx, [rdi+9Ch]
0x18000c8d6  jmp     short loc_18000C905
0x18000c8d8  lea     rbx, [rdi+9Ch]
0x18000c8df  cmp     [rbx], esi
0x18000c8e1  jnz     short loc_18000C90D
0x18000c8e3  cmp     dword ptr [rdi+30h], 7
0x18000c8e7  jz      short loc_18000C905
0x18000c8e9  cmp     [rdi+30h], esi
0x18000c8ec  jz      short loc_18000C905
0x18000c8ee  cmp     dword ptr [rdi+30h], 5
0x18000c8f2  jz      short loc_18000C905
0x18000c8f4  cmp     [rdi+98h], si
0x18000c8fb  jz      short loc_18000C905
0x18000c8fd  mov     rcx, rdi; struct _WST_CONTEXT *
0x18000c900  call    ?WSTContextTableInsert@@YAJPEAU_WST_CONTEXT@@@Z; WSTContextTableInsert(_WST_CONTEXT *)
0x18000c905  cmp     [rbx], esi
0x18000c907  jz      loc_18000C9AF
0x18000c90d  mov     ebx, esi
0x18000c90f  mov     [rsp+88h+arg_8], ebx
0x18000c916  movzx   eax, word ptr [r15+98h]
0x18000c91e  cmp     ebx, eax
0x18000c920  jnb     loc_18000C9AF
0x18000c926  mov     edx, ebx
0x18000c928  shl     rdx, 4
0x18000c92c  add     rdx, [r15+90h]; struct _GUID *
0x18000c933  mov     rcx, r15; struct _WST_CONTEXT *
0x18000c936  call    ?WSTGetActiveContextByAuthScheme@@YAPEAU_WST_ACTIVE_ENGINE_CONTEXT@@PEAU_WST_CONTEXT@@PEAU_GUID@@@Z; WSTGetActiveContextByAuthScheme(_WST_CONTEXT *,_GUID *)
0x18000c93b  mov     r13, rax
0x18000c93e  test    r14, r14
0x18000c941  jz      short loc_18000C94B
0x18000c943  mov     rcx, r14; struct _WST_SSP_PACKAGE *
0x18000c946  call    ?WSTDereferencePackage@@YAXPEAU_WST_SSP_PACKAGE@@@Z; WSTDereferencePackage(_WST_SSP_PACKAGE *)
0x18000c94b  lea     rcx, [r13+18h]; struct _GUID *
0x18000c94f  call    ?WSTLocatePackageByAuthScheme@@YAPEAU_WST_SSP_PACKAGE@@PEAU_GUID@@@Z; WSTLocatePackageByAuthScheme(_GUID *)
0x18000c954  mov     r14, rax
0x18000c957  mov     [rsp+88h+arg_18], rax
0x18000c95f  mov     rax, [rax+0F8h]
0x18000c966  test    rax, rax
0x18000c969  jz      short loc_18000C9A8
0x18000c96b  xor     r9d, r9d
0x18000c96e  xor     r8d, r8d
0x18000c971  lea     edx, [r9+21h]
0x18000c975  mov     rcx, [r13+28h]
0x18000c979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c97e  jmp     short loc_18000C9A8
0x18000c980  xor     esi, esi
0x18000c982  lea     r12, WPP_GLOBAL_Control
0x18000c989  mov     rdi, [rsp+88h+arg_0]
0x18000c991  mov     r15, [rsp+88h+arg_10]
0x18000c999  mov     r14, [rsp+88h+arg_18]
0x18000c9a1  mov     ebx, [rsp+88h+arg_8]
0x18000c9a8  inc     ebx
0x18000c9aa  jmp     loc_18000C90F
0x18000c9af  mov     rcx, rdi; struct _WST_CONTEXT *
0x18000c9b2  call    ?WSTDereferenceContext@@YAXPEAU_WST_CONTEXT@@@Z; WSTDereferenceContext(_WST_CONTEXT *)
0x18000c9b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9be  cmp     rcx, r12
0x18000c9c1  jz      short loc_18000C9E1
0x18000c9c3  test    byte ptr [rcx+1Ch], 8
0x18000c9c7  jz      short loc_18000C9E1
0x18000c9c9  mov     edx, 2Ah ; '*'
0x18000c9ce  mov     r9, r15
0x18000c9d1  lea     r8, WPP_6fa7dbc14d303f0b349d28a6dba66ee3_Traceguids
0x18000c9d8  mov     rcx, [rcx+10h]
0x18000c9dc  call    WPP_SF_q
0x18000c9e1  test    r14, r14
0x18000c9e4  jz      short loc_18000C9EE
0x18000c9e6  mov     rcx, r14; struct _WST_SSP_PACKAGE *
0x18000c9e9  call    ?WSTDereferencePackage@@YAXPEAU_WST_SSP_PACKAGE@@@Z; WSTDereferencePackage(_WST_SSP_PACKAGE *)
0x18000c9ee  xor     eax, eax
0x18000c9f0  add     rsp, 50h
0x18000c9f4  pop     r15
0x18000c9f6  pop     r14
0x18000c9f8  pop     r13
0x18000c9fa  pop     r12
0x18000c9fc  pop     rdi
0x18000c9fd  pop     rsi
0x18000c9fe  pop     rbx
0x18000c9ff  retn
0x18001ef88  push    rbp
0x18001ef8a  sub     rsp, 40h
0x18001ef8e  mov     rbp, rdx
0x18001ef91  call    ?WSTExceptionFilter@@YAKXZ; WSTExceptionFilter(void)
0x18001ef96  nop
0x18001ef97  add     rsp, 40h
0x18001ef9b  pop     rbp
0x18001ef9c  retn
```
