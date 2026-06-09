# CSecurityAdmin2::OptimizeAcl(_ACL *,_ACL * *)

- ea: `0x18002ae90`
- end: `0x18002af9f`
- name: `?OptimizeAcl@CSecurityAdmin2@@QEAAJPEAU_ACL@@PEAPEAU2@@Z`
- size: `271`
- prototype: `__int64 __fastcall(CSecurityAdmin2 *__hidden this, struct _ACL *, struct _ACL **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180009574`
- `0x1800293c8`

## callees

- `0x18002ae90`
- `0x180055822`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002af61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002af61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002aeac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002aeac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af68`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18002af3f`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18002af3f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall CSecurityAdmin2::OptimizeAcl(CSecurityAdmin2 *this, struct _ACL *a2, struct _ACL **a3)
{
  struct _ACL *v4; // rax
  struct _ACL *v5; // rbx
  signed int result; // eax
  struct _ACL *v7; // rdi
  __int16 v8; // r12
  unsigned int v9; // r13d
  struct _ACL *v10; // r14
  unsigned int i; // r15d
  WORD AclSize; // si

  v4 = (struct _ACL *)CoTaskMemAlloc(a2->AclSize);
  v5 = v4;
  if ( !v4 )
    return -2147024882;
  *(_WORD *)&v4->AclRevision = 2;
  v4->AclSize = a2->AclSize;
  *(_DWORD *)&v4->AceCount = 0;
  v7 = a2 + 1;
  v8 = 8;
  v9 = 0;
  while ( 2 )
  {
    if ( v9 >= a2->AceCount )
    {
      v5->AclSize = v8;
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
        v8 += v7->AclSize;
        AclSize = v7->AclSize;
LABEL_12:
        v7 = (struct _ACL *)((char *)v7 + AclSize);
        ++v9;
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
0x18002ae90  mov     [rsp+arg_10], r8
0x18002ae95  push    rbx
0x18002ae96  push    rbp
0x18002ae97  push    rsi
0x18002ae98  push    rdi
0x18002ae99  push    r12
0x18002ae9b  push    r13
0x18002ae9d  push    r14
0x18002ae9f  push    r15
0x18002aea1  sub     rsp, 38h
0x18002aea5  mov     rbp, rdx
0x18002aea8  movzx   ecx, word ptr [rdx+2]; cb
0x18002aeac  call    cs:__imp_CoTaskMemAlloc
0x18002aeb2  mov     rbx, rax
0x18002aeb5  test    rax, rax
0x18002aeb8  jnz     short loc_18002AEC4
0x18002aeba  mov     eax, 8007000Eh
0x18002aebf  jmp     loc_18002AF8E
0x18002aec4  mov     word ptr [rax], 2
0x18002aec9  movzx   eax, word ptr [rbp+2]
0x18002aecd  mov     [rbx+2], ax
0x18002aed1  xor     eax, eax
0x18002aed3  mov     [rbx+4], eax
0x18002aed6  lea     rdi, [rbp+8]
0x18002aeda  lea     r12d, [rax+8]
0x18002aede  xor     r13d, r13d
0x18002aee1  movzx   eax, word ptr [rbp+4]
0x18002aee5  cmp     r13d, eax
0x18002aee8  jnb     loc_18002AF7C
0x18002aeee  lea     r14, [rbx+8]
0x18002aef2  xor     r15d, r15d
0x18002aef5  movzx   eax, word ptr [rbx+4]
0x18002aef9  cmp     r15d, eax
0x18002aefc  jnb     short loc_18002AF28
0x18002aefe  movzx   esi, word ptr [rdi+2]
0x18002af02  cmp     si, [r14+2]
0x18002af07  jnz     short loc_18002AF1B
0x18002af09  mov     r8d, esi; Size
0x18002af0c  mov     rdx, r14; Buf2
0x18002af0f  mov     rcx, rdi; Buf1
0x18002af12  call    memcmp_0
0x18002af17  test    eax, eax
0x18002af19  jz      short loc_18002AF53
0x18002af1b  movzx   eax, word ptr [r14+2]
0x18002af20  add     r14, rax
0x18002af23  inc     r15d
0x18002af26  jmp     short loc_18002AEF5
0x18002af28  movzx   eax, word ptr [rdi+2]
0x18002af2c  mov     [rsp+78h+nAceListLength], eax; nAceListLength
0x18002af30  mov     r9, rdi; pAceList
0x18002af33  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x18002af37  mov     edx, 2; dwAceRevision
0x18002af3c  mov     rcx, rbx; pAcl
0x18002af3f  call    cs:__imp_AddAce
0x18002af45  test    eax, eax
0x18002af47  jz      short loc_18002AF5E
0x18002af49  movzx   eax, word ptr [rdi+2]
0x18002af4d  add     r12d, eax
0x18002af50  movzx   esi, ax
0x18002af53  movzx   eax, si
0x18002af56  add     rdi, rax
0x18002af59  inc     r13d
0x18002af5c  jmp     short loc_18002AEE1
0x18002af5e  mov     rcx, rbx; pv
0x18002af61  call    cs:__imp_CoTaskMemFree
0x18002af67  nop
0x18002af68  call    cs:__imp_GetLastError
0x18002af6e  test    eax, eax
0x18002af70  jle     short loc_18002AF8E
0x18002af72  movzx   eax, ax
0x18002af75  or      eax, 80070000h
0x18002af7a  jmp     short loc_18002AF8E
0x18002af7c  mov     [rbx+2], r12w
0x18002af81  mov     rax, [rsp+78h+arg_10]
0x18002af89  mov     [rax], rbx
0x18002af8c  xor     eax, eax
0x18002af8e  add     rsp, 38h
0x18002af92  pop     r15
0x18002af94  pop     r14
0x18002af96  pop     r13
0x18002af98  pop     r12
0x18002af9a  pop     rdi
0x18002af9b  pop     rsi
0x18002af9c  pop     rbp
0x18002af9d  pop     rbx
0x18002af9e  retn
```
