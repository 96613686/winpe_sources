# CEfsClient::ConnectToService(ushort *,ushort *,int,void * *)

- ea: `0x18000a870`
- end: `0x18000a8c3`
- name: `?ConnectToService@CEfsClient@@MEAAKPEAG0HPEAPEAX@Z`
- size: `83`
- prototype: `unsigned int __fastcall(CEfsClient *__hidden this, unsigned __int16 *, unsigned __int16 *, int, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18000a870`
- `0x18000a974`
- `0x18000ac60`

## pseudocode

```c
__int64 __fastcall CEfsClient::ConnectToService(CEfsClient *this, char *a2, unsigned __int16 *a3, int a4, void **a5)
{
  __int64 result; // rax

  *a5 = 0;
  result = CEfsClient::StartEfsService((unsigned __int64)a2);
  if ( !(_DWORD)result )
    return CEfsClientBase::ConnectToService(this, a2, a3, a4, a5);
  return result;
}

```

## disassembly

```asm
0x18000a870  push    rbx
0x18000a872  push    rbp
0x18000a873  push    rsi
0x18000a874  push    rdi
0x18000a875  push    r14
0x18000a877  sub     rsp, 30h
0x18000a87b  mov     rdi, [rsp+58h+arg_20]
0x18000a883  mov     r14, rcx
0x18000a886  mov     rcx, rdx; unsigned __int16 *
0x18000a889  mov     esi, r9d
0x18000a88c  mov     rbp, r8
0x18000a88f  mov     rbx, rdx
0x18000a892  mov     qword ptr [rdi], 0
0x18000a899  call    ?StartEfsService@CEfsClient@@KAKPEBG@Z; CEfsClient::StartEfsService(ushort const *)
0x18000a89e  test    eax, eax
0x18000a8a0  jnz     short loc_18000A8B8
0x18000a8a2  mov     r9d, esi; int
0x18000a8a5  mov     [rsp+58h+var_38], rdi; void **
0x18000a8aa  mov     r8, rbp; unsigned __int16 *
0x18000a8ad  mov     rdx, rbx; unsigned __int16 *
0x18000a8b0  mov     rcx, r14; this
0x18000a8b3  call    ?ConnectToService@CEfsClientBase@@MEAAKPEAG0HPEAPEAX@Z; CEfsClientBase::ConnectToService(ushort *,ushort *,int,void * *)
0x18000a8b8  add     rsp, 30h
0x18000a8bc  pop     r14
0x18000a8be  pop     rdi
0x18000a8bf  pop     rsi
0x18000a8c0  pop     rbp
0x18000a8c1  pop     rbx
0x18000a8c2  retn
```
