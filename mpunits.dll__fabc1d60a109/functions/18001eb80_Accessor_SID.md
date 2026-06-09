# Accessor_SID

- ea: `0x18001eb80`
- end: `0x18001ec42`
- name: `Accessor_SID`
- size: `194`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001eb80`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18001ec1b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18001ec1b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001ebc5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001ebc5`

## pseudocode

```c
__int64 __fastcall Accessor_SID(__int64 a1, __int64 a2, _QWORD *a3, _DWORD *a4)
{
  void *v8; // rax
  __int64 v9; // rdi
  __int64 v10; // rbx
  LPWSTR v11; // r8
  _WORD *v12; // rbx
  _WORD *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  _WORD *v16; // rcx
  __int64 result; // rax
  LPWSTR StringSid; // [rsp+40h] [rbp+8h] BYREF

  v8 = (void *)(*(__int64 (**)(void))a2)();
  StringSid = 0;
  if ( !v8 )
    return 13;
  v9 = *(_QWORD *)(a1 + 248);
  v10 = *(_QWORD *)(a2 + 64);
  if ( !ConvertSidToStringSidW(v8, &StringSid) )
    return 13;
  v11 = StringSid;
  v12 = (_WORD *)(v9 + v10);
  v13 = v12;
  v14 = 2147483646;
  v15 = 185;
  do
  {
    if ( !v14 )
      break;
    if ( !*v11 )
      break;
    *v13++ = *v11++;
    --v14;
    --v15;
  }
  while ( v15 );
  v16 = v13 - 1;
  if ( v15 )
    v16 = v13;
  *v16 = 0;
  LocalFree(StringSid);
  *a3 = v12;
  result = 0;
  *a4 = 0;
  return result;
}

```

## disassembly

```asm
0x18001eb80  mov     [rsp+arg_8], rbx
0x18001eb85  mov     [rsp+arg_10], rbp
0x18001eb8a  push    rsi
0x18001eb8b  push    rdi
0x18001eb8c  push    r14
0x18001eb8e  sub     rsp, 20h
0x18001eb92  mov     rax, [rdx]
0x18001eb95  mov     rsi, r9
0x18001eb98  mov     r14, r8
0x18001eb9b  mov     rbx, rdx
0x18001eb9e  mov     rdi, rcx
0x18001eba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eba6  xor     ebp, ebp
0x18001eba8  mov     [rsp+38h+StringSid], rbp
0x18001ebad  test    rax, rax
0x18001ebb0  jz      short loc_18001EC2A
0x18001ebb2  mov     rdi, [rdi+0F8h]
0x18001ebb9  lea     rdx, [rsp+38h+StringSid]; StringSid
0x18001ebbe  mov     rbx, [rbx+40h]
0x18001ebc2  mov     rcx, rax; Sid
0x18001ebc5  call    cs:__imp_ConvertSidToStringSidW
0x18001ebcb  test    eax, eax
0x18001ebcd  jz      short loc_18001EC2A
0x18001ebcf  mov     r8, [rsp+38h+StringSid]
0x18001ebd4  add     rbx, rdi
0x18001ebd7  mov     rax, rbx
0x18001ebda  mov     ecx, 7FFFFFFEh
0x18001ebdf  mov     edx, 0B9h
0x18001ebe4  test    rcx, rcx
0x18001ebe7  jz      short loc_18001EC08
0x18001ebe9  movzx   r9d, word ptr [r8]
0x18001ebed  test    r9w, r9w
0x18001ebf1  jz      short loc_18001EC08
0x18001ebf3  mov     [rax], r9w
0x18001ebf7  add     r8, 2
0x18001ebfb  add     rax, 2
0x18001ebff  dec     rcx
0x18001ec02  sub     rdx, 1
0x18001ec06  jnz     short loc_18001EBE4
0x18001ec08  test    rdx, rdx
0x18001ec0b  lea     rcx, [rax-2]
0x18001ec0f  cmovnz  rcx, rax
0x18001ec13  mov     [rcx], bp
0x18001ec16  mov     rcx, [rsp+38h+StringSid]; hMem
0x18001ec1b  call    cs:__imp_LocalFree
0x18001ec21  mov     [r14], rbx
0x18001ec24  xor     eax, eax
0x18001ec26  mov     [rsi], ebp
0x18001ec28  jmp     short loc_18001EC2F
0x18001ec2a  mov     eax, 0Dh
0x18001ec2f  mov     rbx, [rsp+38h+arg_8]
0x18001ec34  mov     rbp, [rsp+38h+arg_10]
0x18001ec39  add     rsp, 20h
0x18001ec3d  pop     r14
0x18001ec3f  pop     rdi
0x18001ec40  pop     rsi
0x18001ec41  retn
```
