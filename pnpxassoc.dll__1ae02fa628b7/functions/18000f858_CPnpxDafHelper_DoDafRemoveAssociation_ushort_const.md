# CPnpxDafHelper::DoDafRemoveAssociation(ushort const *)

- ea: `0x18000f858`
- end: `0x18000f956`
- name: `?DoDafRemoveAssociation@CPnpxDafHelper@@QEAAJPEBG@Z`
- size: `254`
- prototype: `__int64 __fastcall(CPnpxDafHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000a480`
- `0x18000b5c0`

## callees

- `0x1800019b0`
- `0x18000f6cc`
- `0x18000f858`
- `0x18000ff38`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18000f8f5`
- `KERNEL32!WaitForSingleObject` at `0x18000f8f5`
- `KERNEL32!CloseHandle` at `0x18000f924`
- `KERNEL32!CloseHandle` at `0x18000f924`
- `deviceassociation!DafStartRemoveAssociation` at `0x18000f8e3`
- `deviceassociation!DafStartRemoveAssociation` at `0x18000f8e3`
- `deviceassociation!DafCloseAssociationContext` at `0x18000f943`
- `deviceassociation!DafCloseAssociationContext` at `0x18000f943`
- `deviceassociation!DafCreateAssociationContext` at `0x18000f8c3`
- `deviceassociation!DafCreateAssociationContext` at `0x18000f8c3`

## pseudocode

```c
__int64 __fastcall CPnpxDafHelper::DoDafRemoveAssociation(CPnpxDafHelper *this, const unsigned __int16 *a2, __int64 a3)
{
  __int64 v3; // rcx
  struct _PNPX_DAF_CONTEXT *v4; // rbx
  unsigned int v5; // edi
  void *Block; // [rsp+40h] [rbp+8h] BYREF
  struct _PNPX_DAF_CONTEXT *v8; // [rsp+50h] [rbp+18h] BYREF
  __int64 v9; // [rsp+58h] [rbp+20h] BYREF

  v3 = *(_QWORD *)this;
  v4 = 0;
  Block = 0;
  v9 = 0;
  v8 = 0;
  if ( v3 )
  {
    v5 = DafConcatenateWithDelimiter(v3, a2, a3, &Block);
    if ( !v5 )
    {
      v5 = CreatePnpxDafContext(&v8);
      if ( v5 || (v5 = DafCreateAssociationContext(Block, 0, 0, 0, &v9)) != 0 )
      {
        v4 = v8;
      }
      else
      {
        v4 = v8;
        v5 = DafStartRemoveAssociation(v9, RemoveCallback, v8);
        if ( !v5 )
        {
          WaitForSingleObject(*(HANDLE *)v4, 0xFFFFFFFF);
          v5 = *((_DWORD *)v4 + 2);
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
    if ( v9 )
      DafCloseAssociationContext();
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return v5;
}

```

## disassembly

```asm
0x18000f858  mov     rax, rsp
0x18000f85b  mov     [rax+10h], rbx
0x18000f85f  push    rdi
0x18000f860  sub     rsp, 30h
0x18000f864  mov     rcx, [rcx]
0x18000f867  xor     ebx, ebx
0x18000f869  mov     qword ptr [rax+8], 0
0x18000f871  mov     qword ptr [rax+20h], 0
0x18000f879  mov     [rax+18h], rbx
0x18000f87d  test    rcx, rcx
0x18000f880  jnz     short loc_18000F88C
0x18000f882  mov     edi, 80004005h
0x18000f887  jmp     loc_18000F949
0x18000f88c  lea     r9, [rsp+38h+Block]
0x18000f891  call    DafConcatenateWithDelimiter
0x18000f896  mov     edi, eax
0x18000f898  test    eax, eax
0x18000f89a  jnz     short loc_18000F905
0x18000f89c  lea     rcx, [rsp+38h+arg_10]; struct _PNPX_DAF_CONTEXT **
0x18000f8a1  call    ?CreatePnpxDafContext@@YAJPEAPEAU_PNPX_DAF_CONTEXT@@@Z; CreatePnpxDafContext(_PNPX_DAF_CONTEXT * *)
0x18000f8a6  mov     edi, eax
0x18000f8a8  test    eax, eax
0x18000f8aa  jnz     short loc_18000F900
0x18000f8ac  mov     rcx, [rsp+38h+Block]
0x18000f8b1  lea     rax, [rsp+38h+arg_18]
0x18000f8b6  xor     r9d, r9d
0x18000f8b9  mov     [rsp+38h+var_18], rax
0x18000f8be  xor     r8d, r8d
0x18000f8c1  xor     edx, edx
0x18000f8c3  call    cs:__imp_DafCreateAssociationContext
0x18000f8c9  mov     edi, eax
0x18000f8cb  test    eax, eax
0x18000f8cd  jnz     short loc_18000F900
0x18000f8cf  mov     rbx, [rsp+38h+arg_10]
0x18000f8d4  lea     rdx, ?RemoveCallback@@YAXPEAXJ@Z; RemoveCallback(void *,long)
0x18000f8db  mov     rcx, [rsp+38h+arg_18]
0x18000f8e0  mov     r8, rbx
0x18000f8e3  call    cs:__imp_DafStartRemoveAssociation
0x18000f8e9  mov     edi, eax
0x18000f8eb  test    eax, eax
0x18000f8ed  jnz     short loc_18000F905
0x18000f8ef  mov     rcx, [rbx]; hHandle
0x18000f8f2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000f8f5  call    cs:__imp_WaitForSingleObject
0x18000f8fb  mov     edi, [rbx+8]
0x18000f8fe  jmp     short loc_18000F905
0x18000f900  mov     rbx, [rsp+38h+arg_10]
0x18000f905  cmp     [rsp+38h+Block], 0
0x18000f90b  jz      short loc_18000F917
0x18000f90d  mov     rcx, [rsp+38h+Block]; Block
0x18000f912  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f917  test    rbx, rbx
0x18000f91a  jz      short loc_18000F939
0x18000f91c  mov     rcx, [rbx]; hObject
0x18000f91f  test    rcx, rcx
0x18000f922  jz      short loc_18000F931
0x18000f924  call    cs:__imp_CloseHandle
0x18000f92a  mov     qword ptr [rbx], 0
0x18000f931  mov     rcx, rbx; Block
0x18000f934  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f939  mov     rcx, [rsp+38h+arg_18]
0x18000f93e  test    rcx, rcx
0x18000f941  jz      short loc_18000F949
0x18000f943  call    cs:__imp_DafCloseAssociationContext
0x18000f949  mov     rbx, [rsp+38h+arg_8]
0x18000f94e  mov     eax, edi
0x18000f950  add     rsp, 30h
0x18000f954  pop     rdi
0x18000f955  retn
```
