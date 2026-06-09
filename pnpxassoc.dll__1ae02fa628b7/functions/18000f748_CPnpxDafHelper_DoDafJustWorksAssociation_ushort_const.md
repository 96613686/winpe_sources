# CPnpxDafHelper::DoDafJustWorksAssociation(ushort const *)

- ea: `0x18000f748`
- end: `0x18000f84f`
- name: `?DoDafJustWorksAssociation@CPnpxDafHelper@@QEAAJPEBG@Z`
- size: `263`
- prototype: `__int64 __fastcall(CPnpxDafHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180009c10`

## callees

- `0x1800019b0`
- `0x18000f6cc`
- `0x18000f748`
- `0x18000ff38`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18000f7f5`
- `KERNEL32!WaitForSingleObject` at `0x18000f7f5`
- `KERNEL32!CloseHandle` at `0x18000f821`
- `KERNEL32!CloseHandle` at `0x18000f821`
- `deviceassociation!DafCloseAssociationContext` at `0x18000f83f`
- `deviceassociation!DafCloseAssociationContext` at `0x18000f83f`
- `deviceassociation!DafStartFinalize` at `0x18000f7e3`
- `deviceassociation!DafStartFinalize` at `0x18000f7e3`
- `deviceassociation!DafSelectCeremony` at `0x18000f7c5`
- `deviceassociation!DafSelectCeremony` at `0x18000f7c5`
- `deviceassociation!DafCreateAssociationContext` at `0x18000f7ae`
- `deviceassociation!DafCreateAssociationContext` at `0x18000f7ae`

## pseudocode

```c
__int64 __fastcall CPnpxDafHelper::DoDafJustWorksAssociation(
        CPnpxDafHelper *this,
        const unsigned __int16 *a2,
        __int64 a3)
{
  __int64 v3; // rcx
  struct _PNPX_DAF_CONTEXT *v4; // rbx
  unsigned int started; // edi
  void *Block; // [rsp+50h] [rbp+20h] BYREF
  __int64 v8; // [rsp+60h] [rbp+30h] BYREF
  struct _PNPX_DAF_CONTEXT *v9; // [rsp+68h] [rbp+38h] BYREF

  v3 = *(_QWORD *)this;
  v4 = 0;
  Block = 0;
  v8 = 0;
  v9 = 0;
  if ( v3 )
  {
    started = DafConcatenateWithDelimiter(v3, a2, a3, &Block);
    if ( !started )
    {
      started = CreatePnpxDafContext(&v9);
      if ( started
        || (started = DafCreateAssociationContext(Block, 0, 0, 0, &v8)) != 0
        || (started = DafSelectCeremony(v8, DAF_Ceremony_JustWorks)) != 0 )
      {
        v4 = v9;
      }
      else
      {
        v4 = v9;
        started = DafStartFinalize(v8, &FinalizeCallback, v9);
        if ( !started )
        {
          WaitForSingleObject(*(HANDLE *)v4, 0xFFFFFFFF);
          started = *((_DWORD *)v4 + 2);
        }
      }
    }
    if ( Block )
      operator delete(Block);
    if ( v4 )
    {
      if ( *(_QWORD *)v4 )
      {
        CloseHandle(*(HANDLE *)v4);
        *(_QWORD *)v4 = 0;
      }
      operator delete(v4);
    }
    if ( v8 )
      DafCloseAssociationContext();
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return started;
}

```

## disassembly

```asm
0x18000f748  push    rbp
0x18000f74a  push    rbx
0x18000f74b  push    rdi
0x18000f74c  mov     rbp, rsp
0x18000f74f  sub     rsp, 30h
0x18000f753  mov     rcx, [rcx]
0x18000f756  xor     ebx, ebx
0x18000f758  mov     [rbp+Block], 0
0x18000f760  mov     [rbp+arg_10], 0
0x18000f768  mov     [rbp+arg_18], rbx
0x18000f76c  test    rcx, rcx
0x18000f76f  jnz     short loc_18000F77B
0x18000f771  mov     edi, 80004005h
0x18000f776  jmp     loc_18000F845
0x18000f77b  lea     r9, [rbp+Block]
0x18000f77f  call    DafConcatenateWithDelimiter
0x18000f784  mov     edi, eax
0x18000f786  test    eax, eax
0x18000f788  jnz     short loc_18000F804
0x18000f78a  lea     rcx, [rbp+arg_18]; struct _PNPX_DAF_CONTEXT **
0x18000f78e  call    ?CreatePnpxDafContext@@YAJPEAPEAU_PNPX_DAF_CONTEXT@@@Z; CreatePnpxDafContext(_PNPX_DAF_CONTEXT * *)
0x18000f793  mov     edi, eax
0x18000f795  test    eax, eax
0x18000f797  jnz     short loc_18000F800
0x18000f799  mov     rcx, [rbp+Block]
0x18000f79d  lea     rax, [rbp+arg_10]
0x18000f7a1  xor     r9d, r9d
0x18000f7a4  mov     [rsp+30h+var_10], rax
0x18000f7a9  xor     r8d, r8d
0x18000f7ac  xor     edx, edx
0x18000f7ae  call    cs:__imp_DafCreateAssociationContext
0x18000f7b4  mov     edi, eax
0x18000f7b6  test    eax, eax
0x18000f7b8  jnz     short loc_18000F800
0x18000f7ba  mov     rcx, [rbp+arg_10]
0x18000f7be  lea     rdx, DAF_Ceremony_JustWorks
0x18000f7c5  call    cs:__imp_DafSelectCeremony
0x18000f7cb  mov     edi, eax
0x18000f7cd  test    eax, eax
0x18000f7cf  jnz     short loc_18000F800
0x18000f7d1  mov     rbx, [rbp+arg_18]
0x18000f7d5  lea     rdx, ?FinalizeCallback@@YAXW4_DAF_ASSOCIATION_STATUS@@PEAXJ@Z; FinalizeCallback(_DAF_ASSOCIATION_STATUS,void *,long)
0x18000f7dc  mov     rcx, [rbp+arg_10]
0x18000f7e0  mov     r8, rbx
0x18000f7e3  call    cs:__imp_DafStartFinalize
0x18000f7e9  mov     edi, eax
0x18000f7eb  test    eax, eax
0x18000f7ed  jnz     short loc_18000F804
0x18000f7ef  mov     rcx, [rbx]; hHandle
0x18000f7f2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000f7f5  call    cs:__imp_WaitForSingleObject
0x18000f7fb  mov     edi, [rbx+8]
0x18000f7fe  jmp     short loc_18000F804
0x18000f800  mov     rbx, [rbp+arg_18]
0x18000f804  cmp     [rbp+Block], 0
0x18000f809  jz      short loc_18000F814
0x18000f80b  mov     rcx, [rbp+Block]; Block
0x18000f80f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f814  test    rbx, rbx
0x18000f817  jz      short loc_18000F836
0x18000f819  mov     rcx, [rbx]; hObject
0x18000f81c  test    rcx, rcx
0x18000f81f  jz      short loc_18000F82E
0x18000f821  call    cs:__imp_CloseHandle
0x18000f827  mov     qword ptr [rbx], 0
0x18000f82e  mov     rcx, rbx; Block
0x18000f831  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f836  mov     rcx, [rbp+arg_10]
0x18000f83a  test    rcx, rcx
0x18000f83d  jz      short loc_18000F845
0x18000f83f  call    cs:__imp_DafCloseAssociationContext
0x18000f845  mov     eax, edi
0x18000f847  add     rsp, 30h
0x18000f84b  pop     rdi
0x18000f84c  pop     rbx
0x18000f84d  pop     rbp
0x18000f84e  retn
```
