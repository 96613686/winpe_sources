# CSchedule::AddWorkItem(ushort const *,IScheduledWorkItem *)

- ea: `0x18000f610`
- end: `0x18000f6f1`
- name: `?AddWorkItem@CSchedule@@UEAAJPEBGPEAUIScheduledWorkItem@@@Z`
- size: `225`
- prototype: `__int64 __fastcall(CSchedule *__hidden this, const unsigned __int16 *, struct IScheduledWorkItem *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task`

## callees

- `0x180002ab0`
- `0x180006120`
- `0x180009f38`
- `0x18000f610`
- `0x18001b010`

## pseudocode

```c
signed int __fastcall CSchedule::AddWorkItem(LPCWSTR *this, const unsigned __int16 *a2, struct IScheduledWorkItem *a3)
{
  signed int result; // eax
  struct IScheduledWorkItemVtbl *lpVtbl; // rax
  int v8; // ebx
  void *Block; // [rsp+30h] [rbp+8h] BYREF
  __int64 v10; // [rsp+48h] [rbp+20h] BYREF

  if ( this[7] || (result = FolderAccessCheckOnThreadToken(this[8], 2u), result >= 0) )
  {
    if ( a2 && a3 )
    {
      Block = 0;
      result = CSchedule::CheckJobName((CSchedule *)this, a2, (unsigned __int16 **)&Block);
      if ( result >= 0 )
      {
        lpVtbl = a3->lpVtbl;
        v10 = 0;
        v8 = ((__int64 (__fastcall *)(struct IScheduledWorkItem *, GUID *, __int64 *))lpVtbl->QueryInterface)(
               a3,
               &IID_IPersistFile,
               &v10);
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(__int64, void *, __int64))(*(_QWORD *)v10 + 48LL))(v10, Block, 1);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        }
        operator delete(Block);
        return v8;
      }
    }
    else
    {
      return -2147024809;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f610  mov     [rsp+arg_8], rbx
0x18000f615  mov     [rsp+arg_10], rsi
0x18000f61a  push    rdi
0x18000f61b  sub     rsp, 20h
0x18000f61f  cmp     qword ptr [rcx+38h], 0
0x18000f624  mov     rdi, r8
0x18000f627  mov     rsi, rdx
0x18000f62a  mov     rbx, rcx
0x18000f62d  jnz     short loc_18000F645
0x18000f62f  mov     rcx, [rcx+40h]; lpFileName
0x18000f633  mov     edx, 2; DesiredAccess
0x18000f638  call    ?FolderAccessCheckOnThreadToken@@YAJPEBGK@Z; FolderAccessCheckOnThreadToken(ushort const *,ulong)
0x18000f63d  test    eax, eax
0x18000f63f  js      loc_18000F6E1
0x18000f645  test    rsi, rsi
0x18000f648  jz      loc_18000F6DC
0x18000f64e  test    rdi, rdi
0x18000f651  jz      loc_18000F6DC
0x18000f657  lea     r8, [rsp+28h+Block]; unsigned __int16 **
0x18000f65c  mov     [rsp+28h+Block], 0
0x18000f665  mov     rdx, rsi; unsigned __int16 *
0x18000f668  mov     rcx, rbx; this
0x18000f66b  call    ?CheckJobName@CSchedule@@AEAAJPEBGPEAPEAG@Z; CSchedule::CheckJobName(ushort const *,ushort * *)
0x18000f670  test    eax, eax
0x18000f672  js      short loc_18000F6E1
0x18000f674  mov     rax, [rdi]
0x18000f677  lea     r8, [rsp+28h+arg_18]
0x18000f67c  lea     rdx, IID_IPersistFile
0x18000f683  mov     [rsp+28h+arg_18], 0
0x18000f68c  mov     rcx, rdi
0x18000f68f  mov     rax, [rax]
0x18000f692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f697  mov     ebx, eax
0x18000f699  test    eax, eax
0x18000f69b  jns     short loc_18000F6AB
0x18000f69d  mov     rcx, [rsp+28h+Block]; Block
0x18000f6a2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f6a7  mov     eax, ebx
0x18000f6a9  jmp     short loc_18000F6E1
0x18000f6ab  mov     rcx, [rsp+28h+arg_18]
0x18000f6b0  mov     r8d, 1
0x18000f6b6  mov     rdx, [rsp+28h+Block]
0x18000f6bb  mov     rax, [rcx]
0x18000f6be  mov     rax, [rax+30h]
0x18000f6c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6c7  mov     rcx, [rsp+28h+arg_18]
0x18000f6cc  mov     ebx, eax
0x18000f6ce  mov     rdx, [rcx]
0x18000f6d1  mov     rax, [rdx+10h]
0x18000f6d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6da  jmp     short loc_18000F69D
0x18000f6dc  mov     eax, 80070057h
0x18000f6e1  mov     rbx, [rsp+28h+arg_8]
0x18000f6e6  mov     rsi, [rsp+28h+arg_10]
0x18000f6eb  add     rsp, 20h
0x18000f6ef  pop     rdi
0x18000f6f0  retn
```
