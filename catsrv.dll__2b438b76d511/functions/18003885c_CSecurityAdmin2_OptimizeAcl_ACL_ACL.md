# CSecurityAdmin2::OptimizeAcl(_ACL *,_ACL * *)

- ea: `0x18003885c`
- end: `0x18003896a`
- name: `?OptimizeAcl@CSecurityAdmin2@@QEAAJPEAU_ACL@@PEAPEAU2@@Z`
- size: `270`
- prototype: `__int64 __fastcall(CSecurityAdmin2 *__hidden this, struct _ACL *, struct _ACL **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003496c`
- `0x180036dc4`

## callees

- `0x18003885c`
- `0x180055502`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038933`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18003890b`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18003890b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003892d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003892d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038878`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038878`

## pseudocode

```c
signed int __fastcall CSecurityAdmin2::OptimizeAcl(CSecurityAdmin2 *this, struct _ACL *a2, struct _ACL **a3)
{
  struct _ACL *v4; // rax
  struct _ACL *v5; // rbx
  signed int result; // eax
  struct _ACL *v7; // rdi
  unsigned int v8; // r13d
  __int16 v9; // r12
  struct _ACL *v10; // r14
  unsigned int i; // r15d
  WORD AclSize; // si

  v4 = (struct _ACL *)CoTaskMemAlloc(a2->AclSize);
  v5 = v4;
  if ( !v4 )
    return -2147024882;
  *(_WORD *)&v4->AclRevision = 2;
  v7 = a2 + 1;
  v4->AclSize = a2->AclSize;
  *(_DWORD *)&v4->AceCount = 0;
  v8 = 0;
  v9 = 8;
  while ( 2 )
  {
    if ( v8 >= a2->AceCount )
    {
      v5->AclSize = v9;
      *a3 = v5;
      return 0;
    }
    else
    {
      v10 = v5 + 1;
      for ( i = 0; i < v5->AceCount; ++i )
      {
        AclSize = v7->AclSize;
        if ( AclSize == v10->AclSize && !memcmp_0(v7, v10, v7->AclSize) )
          goto LABEL_12;
        v10 = (struct _ACL *)((char *)v10 + v10->AclSize);
      }
      if ( AddAce(v5, 2u, 0xFFFFFFFF, v7, v7->AclSize) )
      {
        v9 += v7->AclSize;
        AclSize = v7->AclSize;
LABEL_12:
        v7 = (struct _ACL *)((char *)v7 + AclSize);
        ++v8;
        continue;
      }
      CoTaskMemFree(v5);
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
    return result;
  }
}

```

## disassembly

```asm
0x18003885c  mov     [rsp+arg_10], r8
0x180038861  push    rbx
0x180038862  push    rbp
0x180038863  push    rsi
0x180038864  push    rdi
0x180038865  push    r12
0x180038867  push    r13
0x180038869  push    r14
0x18003886b  push    r15
0x18003886d  sub     rsp, 38h
0x180038871  movzx   ecx, word ptr [rdx+2]; cb
0x180038875  mov     rbp, rdx
0x180038878  call    cs:__imp_CoTaskMemAlloc
0x18003887e  mov     rbx, rax
0x180038881  test    rax, rax
0x180038884  jnz     short loc_180038890
0x180038886  mov     eax, 8007000Eh
0x18003888b  jmp     loc_180038959
0x180038890  mov     word ptr [rax], 2
0x180038895  lea     rdi, [rbp+8]
0x180038899  movzx   eax, word ptr [rbp+2]
0x18003889d  mov     [rbx+2], ax
0x1800388a1  xor     eax, eax
0x1800388a3  mov     [rbx+4], eax
0x1800388a6  xor     r13d, r13d
0x1800388a9  lea     r12d, [rax+8]
0x1800388ad  movzx   eax, word ptr [rbp+4]
0x1800388b1  cmp     r13d, eax
0x1800388b4  jnb     loc_180038947
0x1800388ba  lea     r14, [rbx+8]
0x1800388be  xor     r15d, r15d
0x1800388c1  movzx   eax, word ptr [rbx+4]
0x1800388c5  cmp     r15d, eax
0x1800388c8  jnb     short loc_1800388F4
0x1800388ca  movzx   esi, word ptr [rdi+2]
0x1800388ce  cmp     si, [r14+2]
0x1800388d3  jnz     short loc_1800388E7
0x1800388d5  mov     r8d, esi; Size
0x1800388d8  mov     rdx, r14; Buf2
0x1800388db  mov     rcx, rdi; Buf1
0x1800388de  call    memcmp_0
0x1800388e3  test    eax, eax
0x1800388e5  jz      short loc_18003891F
0x1800388e7  movzx   eax, word ptr [r14+2]
0x1800388ec  add     r14, rax
0x1800388ef  inc     r15d
0x1800388f2  jmp     short loc_1800388C1
0x1800388f4  movzx   eax, word ptr [rdi+2]
0x1800388f8  mov     r9, rdi; pAceList
0x1800388fb  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x1800388ff  mov     [rsp+78h+nAceListLength], eax; nAceListLength
0x180038903  mov     edx, 2; dwAceRevision
0x180038908  mov     rcx, rbx; pAcl
0x18003890b  call    cs:__imp_AddAce
0x180038911  test    eax, eax
0x180038913  jz      short loc_18003892A
0x180038915  movzx   eax, word ptr [rdi+2]
0x180038919  add     r12d, eax
0x18003891c  movzx   esi, ax
0x18003891f  movzx   eax, si
0x180038922  add     rdi, rax
0x180038925  inc     r13d
0x180038928  jmp     short loc_1800388AD
0x18003892a  mov     rcx, rbx; pv
0x18003892d  call    cs:__imp_CoTaskMemFree
0x180038933  call    cs:__imp_GetLastError
0x180038939  test    eax, eax
0x18003893b  jle     short loc_180038959
0x18003893d  movzx   eax, ax
0x180038940  or      eax, 80070000h
0x180038945  jmp     short loc_180038959
0x180038947  mov     rax, [rsp+78h+arg_10]
0x18003894f  mov     [rbx+2], r12w
0x180038954  mov     [rax], rbx
0x180038957  xor     eax, eax
0x180038959  add     rsp, 38h
0x18003895d  pop     r15
0x18003895f  pop     r14
0x180038961  pop     r13
0x180038963  pop     r12
0x180038965  pop     rdi
0x180038966  pop     rsi
0x180038967  pop     rbp
0x180038968  pop     rbx
0x180038969  retn
```
