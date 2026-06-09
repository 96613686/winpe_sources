# IsVirtualServiceAccount(ushort const *)

- ea: `0x180040510`
- end: `0x180040593`
- name: `?IsVirtualServiceAccount@@YAHPEBG@Z`
- size: `131`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003797c`

## callees

- `0x180040428`
- `0x180040510`
- `0x1800408fc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004057e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004057e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180040527`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180040527`

## pseudocode

```c
__int64 __fastcall IsVirtualServiceAccount(const unsigned __int16 *a1)
{
  unsigned int v2; // ebx
  PSID Sid; // [rsp+38h] [rbp+10h] BYREF

  Sid = 0;
  if ( ConvertStringSidToSidW(a1, &Sid) )
    v2 = IsVirtualServiceAccount(Sid);
  else
    v2 = StringIsPrefixed(a1, L"S-1-5-80") || StringIsPrefixed(a1, L"S-1-5-99");
  if ( Sid )
    LocalFree(Sid);
  return v2;
}

```

## disassembly

```asm
0x180040510  push    rbx
0x180040512  sub     rsp, 20h
0x180040516  lea     rdx, [rsp+28h+Sid]; Sid
0x18004051b  mov     [rsp+28h+Sid], 0
0x180040524  mov     rbx, rcx
0x180040527  call    cs:__imp_ConvertStringSidToSidW
0x18004052e  nop     dword ptr [rax+rax+00h]
0x180040533  test    eax, eax
0x180040535  jz      short loc_180040545
0x180040537  mov     rcx, [rsp+28h+Sid]; Sid
0x18004053c  call    ?IsVirtualServiceAccount@@YAHPEAX@Z; IsVirtualServiceAccount(void *)
0x180040541  mov     ebx, eax
0x180040543  jmp     short loc_180040574
0x180040545  lea     rdx, aS1580; "S-1-5-80"
0x18004054c  mov     rcx, rbx; unsigned __int16 *
0x18004054f  call    ?StringIsPrefixed@@YAHPEBG0@Z; StringIsPrefixed(ushort const *,ushort const *)
0x180040554  test    eax, eax
0x180040556  jnz     short loc_18004056F
0x180040558  lea     rdx, aS1599; "S-1-5-99"
0x18004055f  mov     rcx, rbx; unsigned __int16 *
0x180040562  call    ?StringIsPrefixed@@YAHPEBG0@Z; StringIsPrefixed(ushort const *,ushort const *)
0x180040567  test    eax, eax
0x180040569  jnz     short loc_18004056F
0x18004056b  xor     ebx, ebx
0x18004056d  jmp     short loc_180040574
0x18004056f  mov     ebx, 1
0x180040574  mov     rcx, [rsp+28h+Sid]; hMem
0x180040579  test    rcx, rcx
0x18004057c  jz      short loc_18004058A
0x18004057e  call    cs:__imp_LocalFree
0x180040585  nop     dword ptr [rax+rax+00h]
0x18004058a  mov     eax, ebx
0x18004058c  add     rsp, 20h
0x180040590  pop     rbx
0x180040591  retn
```
