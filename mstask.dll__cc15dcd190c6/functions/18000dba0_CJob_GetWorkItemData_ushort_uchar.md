# CJob::GetWorkItemData(ushort *,uchar * *)

- ea: `0x18000dba0`
- end: `0x18000dc1b`
- name: `?GetWorkItemData@CJob@@UEAAJPEAGPEAPEAE@Z`
- size: `123`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16 *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000dba0`
- `0x18001aa82`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dbc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dbc9`

## pseudocode

```c
__int64 __fastcall CJob::GetWorkItemData(const void **this, unsigned __int16 *a2, unsigned __int8 **a3)
{
  unsigned __int8 *v6; // rax

  if ( this[21] )
  {
    v6 = (unsigned __int8 *)CoTaskMemAlloc(*((unsigned __int16 *)this + 88));
    *a3 = v6;
    if ( !v6 )
      return 2147942414LL;
    memcpy_0(v6, this[21], *((unsigned __int16 *)this + 88));
    *a2 = *((_WORD *)this + 88);
  }
  else
  {
    *a2 = 0;
    *a3 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000dba0  mov     [rsp+arg_0], rbx
0x18000dba5  mov     [rsp+arg_8], rsi
0x18000dbaa  push    rdi
0x18000dbab  sub     rsp, 20h
0x18000dbaf  cmp     qword ptr [rcx+0A8h], 0
0x18000dbb7  mov     rdi, r8
0x18000dbba  mov     rsi, rdx
0x18000dbbd  mov     rbx, rcx
0x18000dbc0  jz      short loc_18000DC01
0x18000dbc2  movzx   ecx, word ptr [rcx+0B0h]; cb
0x18000dbc9  call    cs:__imp_CoTaskMemAlloc
0x18000dbcf  mov     [rdi], rax
0x18000dbd2  test    rax, rax
0x18000dbd5  jnz     short loc_18000DBDE
0x18000dbd7  mov     eax, 8007000Eh
0x18000dbdc  jmp     short loc_18000DC0B
0x18000dbde  movzx   r8d, word ptr [rbx+0B0h]; Size
0x18000dbe6  mov     rcx, rax; void *
0x18000dbe9  mov     rdx, [rbx+0A8h]; Src
0x18000dbf0  call    memcpy_0
0x18000dbf5  movzx   eax, word ptr [rbx+0B0h]
0x18000dbfc  mov     [rsi], ax
0x18000dbff  jmp     short loc_18000DC09
0x18000dc01  xor     eax, eax
0x18000dc03  mov     [rdx], ax
0x18000dc06  mov     [r8], rax
0x18000dc09  xor     eax, eax
0x18000dc0b  mov     rbx, [rsp+28h+arg_0]
0x18000dc10  mov     rsi, [rsp+28h+arg_8]
0x18000dc15  add     rsp, 20h
0x18000dc19  pop     rdi
0x18000dc1a  retn
```
