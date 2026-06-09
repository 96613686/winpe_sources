# GetTokenIl(void *)

- ea: `0x180045ad8`
- end: `0x180045b28`
- name: `?GetTokenIl@@YAKPEAX@Z`
- size: `80`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012f98`
- `0x180045dbc`

## callees

- `0x18001ce64`
- `0x180045ad8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045b15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045b15`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180045b05`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180045b05`

## pseudocode

```c
__int64 __fastcall GetTokenIl(void *a1, DWORD a2)
{
  DWORD v2; // edi
  int TokenInformation; // eax
  HLOCAL v4; // rbx
  HLOCAL hMem; // [rsp+38h] [rbp+10h] BYREF

  hMem = 0;
  v2 = 0;
  TokenInformation = AccGetTokenInformation(a1, a2, &hMem);
  v4 = hMem;
  if ( TokenInformation >= 0 )
    v2 = *GetSidSubAuthority(*(PSID *)hMem, 0);
  if ( v4 )
    LocalFree(v4);
  return v2;
}

```

## disassembly

```asm
0x180045ad8  mov     [rsp+arg_0], rbx
0x180045add  push    rdi
0x180045ade  sub     rsp, 20h
0x180045ae2  lea     r8, [rsp+28h+hMem]; void **
0x180045ae7  mov     [rsp+28h+hMem], 0
0x180045af0  xor     edi, edi
0x180045af2  call    ?AccGetTokenInformation@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z; AccGetTokenInformation(void *,_TOKEN_INFORMATION_CLASS,void * *)
0x180045af7  mov     rbx, [rsp+28h+hMem]
0x180045afc  test    eax, eax
0x180045afe  js      short loc_180045B0D
0x180045b00  mov     rcx, [rbx]; pSid
0x180045b03  xor     edx, edx; nSubAuthority
0x180045b05  call    cs:__imp_GetSidSubAuthority
0x180045b0b  mov     edi, [rax]
0x180045b0d  test    rbx, rbx
0x180045b10  jz      short loc_180045B1B
0x180045b12  mov     rcx, rbx; hMem
0x180045b15  call    cs:__imp_LocalFree
0x180045b1b  mov     rbx, [rsp+28h+arg_0]
0x180045b20  mov     eax, edi
0x180045b22  add     rsp, 20h
0x180045b26  pop     rdi
0x180045b27  retn
```
