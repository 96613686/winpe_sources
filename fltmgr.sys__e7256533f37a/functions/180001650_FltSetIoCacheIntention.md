# FltSetIoCacheIntention

- ea: `0x180001650`
- end: `0x1800016e5`
- name: `FltSetIoCacheIntention`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001650`

## import_xrefs

- `ntoskrnl!IoGetGenericIrpExtension` at `0x180001681`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x180001681`
- `ntoskrnl!IoSetGenericIrpExtension` at `0x1800016c1`
- `ntoskrnl!IoSetGenericIrpExtension` at `0x1800016c1`

## pseudocode

```c
__int64 __fastcall FltSetIoCacheIntention(_DWORD *a1, char a2)
{
  __int64 v3; // rdi
  __int64 result; // rax
  __int64 v5; // r9
  int v6; // [rsp+30h] [rbp+8h] BYREF

  if ( (*a1 & 1) == 0 )
    return 3221226021LL;
  v3 = *((_QWORD *)a1 - 23);
  v6 = 0;
  result = IoGetGenericIrpExtension(v3, &v6, 4);
  if ( (int)(result + 0x80000000) < 0 || (_DWORD)result == -1073741275 )
  {
    LOBYTE(v5) = 1;
    BYTE1(v6) = a2 & 1 | BYTE1(v6) & 0xFE;
    return IoSetGenericIrpExtension(v3, &v6, 4, v5);
  }
  return result;
}

```

## disassembly

```asm
0x180001650  push    rbx
0x180001652  sub     rsp, 20h
0x180001656  mov     eax, [rcx]
0x180001658  movzx   ebx, dl
0x18000165b  test    al, 1
0x18000165d  jz      short loc_1800016D9
0x18000165f  mov     [rsp+28h+arg_8], rdi
0x180001664  lea     rdx, [rsp+28h+arg_0]
0x180001669  mov     rdi, [rcx-0B8h]
0x180001670  mov     r8d, 4
0x180001676  mov     rcx, rdi
0x180001679  mov     [rsp+28h+arg_0], 0
0x180001681  call    cs:__imp_IoGetGenericIrpExtension
0x180001688  nop     dword ptr [rax+rax+00h]
0x18000168d  mov     edx, 80000000h
0x180001692  lea     ecx, [rax+rdx]
0x180001695  test    edx, ecx
0x180001697  jnz     short loc_1800016A0
0x180001699  cmp     eax, 0C0000225h
0x18000169e  jnz     short loc_1800016CD
0x1800016a0  movzx   eax, byte ptr [rsp+28h+arg_0+1]
0x1800016a5  lea     rdx, [rsp+28h+arg_0]
0x1800016aa  and     al, 0FEh
0x1800016ac  and     bl, 1
0x1800016af  or      al, bl
0x1800016b1  mov     r8d, 4
0x1800016b7  mov     r9b, 1
0x1800016ba  mov     byte ptr [rsp+28h+arg_0+1], al
0x1800016be  mov     rcx, rdi
0x1800016c1  call    cs:__imp_IoSetGenericIrpExtension
0x1800016c8  nop     dword ptr [rax+rax+00h]
0x1800016cd  mov     rdi, [rsp+28h+arg_8]
0x1800016d2  add     rsp, 20h
0x1800016d6  pop     rbx
0x1800016d7  retn
0x1800016d9  mov     eax, 0C0000225h
0x1800016de  add     rsp, 20h
0x1800016e2  pop     rbx
0x1800016e3  retn
```
