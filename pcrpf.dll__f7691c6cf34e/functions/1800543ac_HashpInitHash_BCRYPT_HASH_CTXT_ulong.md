# HashpInitHash(BCRYPT_HASH_CTXT *,ulong *)

- ea: `0x1800543ac`
- end: `0x180054458`
- name: `?HashpInitHash@@YAJPEAUBCRYPT_HASH_CTXT@@PEAK@Z`
- size: `172`
- prototype: `NTSTATUS __fastcall(struct BCRYPT_HASH_CTXT *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180054234`
- `0x1800542a0`

## callees

- `0x1800543ac`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x1800543f0`
- `bcrypt!BCryptCreateHash` at `0x1800543f0`
- `bcrypt!BCryptGetProperty` at `0x180054429`
- `bcrypt!BCryptGetProperty` at `0x180054429`
- `bcrypt!BCryptDestroyHash` at `0x18005443e`
- `bcrypt!BCryptDestroyHash` at `0x18005443e`

## pseudocode

```c
NTSTATUS __fastcall HashpInitHash(struct BCRYPT_HASH_CTXT *a1, unsigned int *a2)
{
  BCRYPT_HANDLE *v2; // rbx
  NTSTATUS result; // eax
  NTSTATUS Property; // edi
  ULONG pcbResult; // [rsp+58h] [rbp+10h] BYREF
  int v7; // [rsp+5Ch] [rbp+14h]

  v7 = HIDWORD(a2);
  v2 = (BCRYPT_HANDLE *)((char *)a1 + 8);
  pcbResult = 0;
  result = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)a1, (BCRYPT_HASH_HANDLE *)a1 + 1, (PUCHAR)a1 + 16, 0x200u, 0, 0, 0);
  if ( result >= 0 )
  {
    Property = BCryptGetProperty(*v2, L"HashDigestLength", (PUCHAR)a1 + 528, 4u, &pcbResult, 0);
    if ( Property < 0 )
      BCryptDestroyHash(*v2);
    return Property;
  }
  return result;
}

```

## disassembly

```asm
0x1800543ac  mov     rax, rsp
0x1800543af  mov     [rax+8], rbx
0x1800543b3  mov     [rax+10h], rdx
0x1800543b7  push    rdi
0x1800543b8  sub     rsp, 40h
0x1800543bc  lea     rbx, [rcx+8]
0x1800543c0  mov     dword ptr [rax-18h], 0
0x1800543c7  mov     rdi, rcx
0x1800543ca  mov     dword ptr [rax-20h], 0
0x1800543d1  lea     r8, [rcx+10h]; pbHashObject
0x1800543d5  mov     dword ptr [rax+10h], 0
0x1800543dc  mov     rcx, [rcx]; hAlgorithm
0x1800543df  mov     rdx, rbx; phHash
0x1800543e2  mov     r9d, 200h; cbHashObject
0x1800543e8  mov     qword ptr [rax-28h], 0
0x1800543f0  call    cs:__imp_BCryptCreateHash
0x1800543f7  nop     dword ptr [rax+rax+00h]
0x1800543fc  test    eax, eax
0x1800543fe  js      short loc_18005444C
0x180054400  mov     rcx, [rbx]; hObject
0x180054403  lea     rax, [rsp+48h+arg_8]
0x180054408  lea     r8, [rdi+210h]; pbOutput
0x18005440f  mov     [rsp+48h+dwFlags], 0; dwFlags
0x180054417  mov     r9d, 4; cbOutput
0x18005441d  mov     [rsp+48h+pcbResult], rax; pcbResult
0x180054422  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180054429  call    cs:__imp_BCryptGetProperty
0x180054430  nop     dword ptr [rax+rax+00h]
0x180054435  mov     edi, eax
0x180054437  test    eax, eax
0x180054439  jns     short loc_18005444A
0x18005443b  mov     rcx, [rbx]; hHash
0x18005443e  call    cs:__imp_BCryptDestroyHash
0x180054445  nop     dword ptr [rax+rax+00h]
0x18005444a  mov     eax, edi
0x18005444c  mov     rbx, [rsp+48h+arg_0]
0x180054451  add     rsp, 40h
0x180054455  pop     rdi
0x180054456  retn
```
