# CADMCOMW::GetHandleInfo(ulong,_METADATA_HANDLE_INFO *)

- ea: `0x180005f70`
- end: `0x180005ffd`
- name: `?GetHandleInfo@CADMCOMW@@UEAAJKPEAU_METADATA_HANDLE_INFO@@@Z`
- size: `141`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned int, struct _METADATA_HANDLE_INFO *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005f70`
- `0x180007068`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::GetHandleInfo(CADMCOMW *this, unsigned int a2, struct _METADATA_HANDLE_INFO *a3)
{
  __int64 result; // rax
  __int64 v6; // rcx
  unsigned int v7; // [rsp+50h] [rbp+18h] BYREF
  unsigned int v8; // [rsp+58h] [rbp+20h] BYREF

  v8 = 0;
  v7 = 0;
  if ( !a3 )
    return 2147942487LL;
  result = CADMCOMW::Lookup(this, a2, &v8, &v7, 0);
  if ( (int)result >= 0 )
  {
    v6 = *((_QWORD *)this + 101);
    if ( v6 && v7 )
      return (*(__int64 (__fastcall **)(__int64, _QWORD, struct _METADATA_HANDLE_INFO *))(*(_QWORD *)v6 + 128LL))(
               v6,
               v7,
               a3);
    else
      return (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct _METADATA_HANDLE_INFO *))(**((_QWORD **)this + 4) + 312LL))(
               *((_QWORD *)this + 4),
               v8,
               a3);
  }
  return result;
}

```

## disassembly

```asm
0x180005f70  mov     [rsp+arg_0], rbx
0x180005f75  push    rdi
0x180005f76  sub     rsp, 30h
0x180005f7a  mov     [rsp+38h+arg_18], 0
0x180005f82  mov     rdi, r8
0x180005f85  mov     [rsp+38h+arg_10], 0
0x180005f8d  mov     rbx, rcx
0x180005f90  test    r8, r8
0x180005f93  jnz     short loc_180005F9C
0x180005f95  mov     eax, 80070057h
0x180005f9a  jmp     short loc_180005FF2
0x180005f9c  lea     r9, [rsp+38h+arg_10]; unsigned int *
0x180005fa1  mov     [rsp+38h+var_18], 0; struct COpenHandle **
0x180005faa  lea     r8, [rsp+38h+arg_18]; unsigned int *
0x180005faf  call    ?Lookup@CADMCOMW@@QEAAJKPEAK0PEAPEAVCOpenHandle@@@Z; CADMCOMW::Lookup(ulong,ulong *,ulong *,COpenHandle * *)
0x180005fb4  test    eax, eax
0x180005fb6  js      short loc_180005FF2
0x180005fb8  mov     rcx, [rbx+328h]
0x180005fbf  test    rcx, rcx
0x180005fc2  jz      short loc_180005FD8
0x180005fc4  mov     edx, [rsp+38h+arg_10]
0x180005fc8  test    edx, edx
0x180005fca  jz      short loc_180005FD8
0x180005fcc  mov     rax, [rcx]
0x180005fcf  mov     rax, [rax+80h]
0x180005fd6  jmp     short loc_180005FEA
0x180005fd8  mov     rcx, [rbx+20h]
0x180005fdc  mov     edx, [rsp+38h+arg_18]
0x180005fe0  mov     rax, [rcx]
0x180005fe3  mov     rax, [rax+138h]
0x180005fea  mov     r8, rdi
0x180005fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ff2  mov     rbx, [rsp+38h+arg_0]
0x180005ff7  add     rsp, 30h
0x180005ffb  pop     rdi
0x180005ffc  retn
```
