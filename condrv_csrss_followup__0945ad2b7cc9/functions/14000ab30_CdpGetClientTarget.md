# CdpGetClientTarget

- ea: `0x14000ab30`
- end: `0x14000ac47`
- name: `CdpGetClientTarget`
- size: `279`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140008230`
- `0x14000c5c0`

## callees

- `0x14000ab30`
- `0x14000ac50`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000abfc`
- `ntoskrnl!ObfDereferenceObject` at `0x14000abfc`
- `ntoskrnl!IoGetRequestorProcess` at `0x14000ab5f`
- `ntoskrnl!IoGetRequestorProcess` at `0x14000ab5f`

## pseudocode

```c
__int64 __fastcall CdpGetClientTarget(__int64 a1, IRP *a2, _QWORD *a3)
{
  int v3; // eax
  PVOID v4; // r9
  PEPROCESS RequestorProcess; // rax
  __int64 result; // rax
  _QWORD *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  _QWORD *v12; // [rsp+30h] [rbp+8h] BYREF
  PVOID Object; // [rsp+48h] [rbp+20h] BYREF

  v3 = *(_DWORD *)(a1 + 32);
  v4 = 0;
  v12 = 0;
  Object = 0;
  if ( (v3 & 1) != 0 )
  {
    v9 = *(_QWORD **)(*(_QWORD *)(a1 + 8) + 224LL);
    if ( !v9 )
      return 3221225480LL;
    goto LABEL_5;
  }
  RequestorProcess = IoGetRequestorProcess(a2);
  if ( !RequestorProcess )
    return 3221225483LL;
  result = CdGetProcessConnection(&Object, (__int64 *)&v12, 0, RequestorProcess);
  if ( (int)result >= 0 )
  {
    v9 = v12;
    v4 = Object;
LABEL_5:
    v10 = *(_QWORD *)(a1 + 8);
    if ( !v10 || v10 == v9[3] )
    {
      a3[2] = v9[3];
      *a3 = v9[5];
      v11 = *(_DWORD *)(a1 + 32);
      a3[3] = v4;
      if ( (v11 & 2) != 0 )
      {
        a3[1] = *(_QWORD *)(a1 + 16);
        return 0;
      }
      else if ( *(_DWORD *)(a1 + 16) == 1 )
      {
        a3[1] = v9[6];
        return 0;
      }
      else
      {
        a3[1] = v9[7];
        return 0;
      }
    }
    else
    {
      if ( (*(_DWORD *)(a1 + 32) & 1) == 0 )
        ObfDereferenceObject(v4);
      return 3221225480LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000ab30  mov     [rsp+arg_8], rbx
0x14000ab35  push    rdi
0x14000ab36  sub     rsp, 20h
0x14000ab3a  mov     eax, [rcx+20h]
0x14000ab3d  xor     r9d, r9d
0x14000ab40  mov     [rsp+28h+arg_0], 0
0x14000ab49  mov     rdi, r8
0x14000ab4c  mov     [rsp+28h+Object], r9
0x14000ab51  mov     rbx, rcx
0x14000ab54  test    al, 1
0x14000ab56  jnz     loc_14000AC0F
0x14000ab5c  mov     rcx, rdx; Irp
0x14000ab5f  call    cs:__imp_IoGetRequestorProcess
0x14000ab66  nop     dword ptr [rax+rax+00h]
0x14000ab6b  test    rax, rax
0x14000ab6e  jz      loc_14000AC40
0x14000ab74  mov     r9, rax
0x14000ab77  lea     rdx, [rsp+28h+arg_0]
0x14000ab7c  xor     r8d, r8d
0x14000ab7f  lea     rcx, [rsp+28h+Object]
0x14000ab84  call    CdGetProcessConnection
0x14000ab89  test    eax, eax
0x14000ab8b  js      short loc_14000ABCA
0x14000ab8d  mov     rcx, [rsp+28h+arg_0]
0x14000ab92  mov     r9, [rsp+28h+Object]
0x14000ab97  mov     rax, [rbx+8]
0x14000ab9b  test    rax, rax
0x14000ab9e  jnz     short loc_14000ABEC
0x14000aba0  mov     rax, [rcx+18h]
0x14000aba4  mov     [rdi+10h], rax
0x14000aba8  mov     rax, [rcx+28h]
0x14000abac  mov     [rdi], rax
0x14000abaf  mov     eax, [rbx+20h]
0x14000abb2  mov     [rdi+18h], r9
0x14000abb6  test    al, 2
0x14000abb8  jnz     short loc_14000ABD6
0x14000abba  cmp     dword ptr [rbx+10h], 1
0x14000abbe  jz      short loc_14000AC2A
0x14000abc0  mov     rax, [rcx+38h]
0x14000abc4  mov     [rdi+8], rax
0x14000abc8  xor     eax, eax
0x14000abca  mov     rbx, [rsp+28h+arg_8]
0x14000abcf  add     rsp, 20h
0x14000abd3  pop     rdi
0x14000abd4  retn
0x14000abd6  mov     rax, [rbx+10h]
0x14000abda  mov     [rdi+8], rax
0x14000abde  xor     eax, eax
0x14000abe0  mov     rbx, [rsp+28h+arg_8]
0x14000abe5  add     rsp, 20h
0x14000abe9  pop     rdi
0x14000abea  retn
0x14000abec  cmp     rax, [rcx+18h]
0x14000abf0  jz      short loc_14000ABA0
0x14000abf2  mov     eax, [rbx+20h]
0x14000abf5  test    al, 1
0x14000abf7  jnz     short loc_14000AC08
0x14000abf9  mov     rcx, r9; Object
0x14000abfc  call    cs:__imp_ObfDereferenceObject
0x14000ac03  nop     dword ptr [rax+rax+00h]
0x14000ac08  mov     eax, 0C0000008h
0x14000ac0d  jmp     short loc_14000ABCA
0x14000ac0f  mov     rax, [rcx+8]
0x14000ac13  mov     rcx, [rax+0E0h]
0x14000ac1a  test    rcx, rcx
0x14000ac1d  jnz     loc_14000AB97
0x14000ac23  mov     eax, 0C0000008h
0x14000ac28  jmp     short loc_14000ABCA
0x14000ac2a  mov     rax, [rcx+30h]
0x14000ac2e  mov     [rdi+8], rax
0x14000ac32  xor     eax, eax
0x14000ac34  mov     rbx, [rsp+28h+arg_8]
0x14000ac39  add     rsp, 20h
0x14000ac3d  pop     rdi
0x14000ac3e  retn
0x14000ac40  mov     eax, 0C000000Bh
0x14000ac45  jmp     short loc_14000ABCA
```
