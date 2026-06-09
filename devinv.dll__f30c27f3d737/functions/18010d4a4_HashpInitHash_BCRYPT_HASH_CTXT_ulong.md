# HashpInitHash(BCRYPT_HASH_CTXT *,ulong *)

- ea: `0x18010d4a4`
- end: `0x18010d54a`
- name: `?HashpInitHash@@YAJPEAUBCRYPT_HASH_CTXT@@PEAK@Z`
- size: `166`
- prototype: `__int64 __fastcall(struct BCRYPT_HASH_CTXT *, unsigned int *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18010d238`
- `0x18010d2b4`
- `0x18010d3d4`

## callees

- `0x18010d4a4`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x18010d52c`
- `bcrypt!BCryptDestroyHash` at `0x18010d52c`
- `bcrypt!BCryptGetProperty` at `0x18010d51d`
- `bcrypt!BCryptGetProperty` at `0x18010d51d`
- `bcrypt!BCryptCreateHash` at `0x18010d4e7`
- `bcrypt!BCryptCreateHash` at `0x18010d4e7`

## pseudocode

```c
NTSTATUS __fastcall HashpInitHash(struct BCRYPT_HASH_CTXT *a1, unsigned int *a2)
{
  BCRYPT_HANDLE *v2; // rdi
  NTSTATUS result; // eax
  unsigned int *v6; // r14
  NTSTATUS Property; // esi
  ULONG pcbResult; // [rsp+70h] [rbp+8h] BYREF

  v2 = (BCRYPT_HANDLE *)((char *)a1 + 8);
  pcbResult = 0;
  result = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)a1, (BCRYPT_HASH_HANDLE *)a1 + 1, (PUCHAR)a1 + 16, 0x200u, 0, 0, 0);
  if ( result >= 0 )
  {
    v6 = (unsigned int *)((char *)a1 + 528);
    Property = BCryptGetProperty(*v2, L"HashDigestLength", (PUCHAR)a1 + 528, 4u, &pcbResult, 0);
    if ( Property >= 0 )
    {
      if ( a2 )
        *a2 = *v6;
    }
    else
    {
      BCryptDestroyHash(*v2);
    }
    return Property;
  }
  return result;
}

```

## disassembly

```asm
0x18010d4a4  mov     rax, rsp
0x18010d4a7  push    rbx
0x18010d4a8  push    rsi
0x18010d4a9  push    rdi
0x18010d4aa  push    r14
0x18010d4ac  sub     rsp, 48h
0x18010d4b0  lea     rdi, [rcx+8]
0x18010d4b4  mov     dword ptr [rax-38h], 0
0x18010d4bb  mov     rbx, rdx
0x18010d4be  mov     dword ptr [rax-40h], 0
0x18010d4c5  mov     rsi, rcx
0x18010d4c8  mov     dword ptr [rax+8], 0
0x18010d4cf  lea     r8, [rcx+10h]; pbHashObject
0x18010d4d3  mov     qword ptr [rax-48h], 0
0x18010d4db  mov     rcx, [rcx]; hAlgorithm
0x18010d4de  mov     rdx, rdi; phHash
0x18010d4e1  mov     r9d, 200h; cbHashObject
0x18010d4e7  call    cs:__imp_BCryptCreateHash
0x18010d4ed  test    eax, eax
0x18010d4ef  js      short loc_18010D540
0x18010d4f1  mov     rcx, [rdi]; hObject
0x18010d4f4  lea     rax, [rsp+68h+arg_0]
0x18010d4f9  lea     r14, [rsi+210h]
0x18010d500  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18010d508  mov     r8, r14; pbOutput
0x18010d50b  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18010d510  mov     r9d, 4; cbOutput
0x18010d516  lea     rdx, pszProperty; "HashDigestLength"
0x18010d51d  call    cs:__imp_BCryptGetProperty
0x18010d523  mov     esi, eax
0x18010d525  test    eax, eax
0x18010d527  jns     short loc_18010D534
0x18010d529  mov     rcx, [rdi]; hHash
0x18010d52c  call    cs:__imp_BCryptDestroyHash
0x18010d532  jmp     short loc_18010D53E
0x18010d534  test    rbx, rbx
0x18010d537  jz      short loc_18010D53E
0x18010d539  mov     eax, [r14]
0x18010d53c  mov     [rbx], eax
0x18010d53e  mov     eax, esi
0x18010d540  add     rsp, 48h
0x18010d544  pop     r14
0x18010d546  pop     rdi
0x18010d547  pop     rsi
0x18010d548  pop     rbx
0x18010d549  retn
```
