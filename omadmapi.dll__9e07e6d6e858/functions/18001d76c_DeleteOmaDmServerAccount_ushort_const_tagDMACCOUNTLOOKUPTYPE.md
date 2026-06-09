# DeleteOmaDmServerAccount(ushort const *,tagDMACCOUNTLOOKUPTYPE)

- ea: `0x18001d76c`
- end: `0x18001d7e9`
- name: `?DeleteOmaDmServerAccount@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@@Z`
- size: `125`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015df0`
- `0x180016160`

## callees

- `0x18000f47c`
- `0x180016700`
- `0x18001d76c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d7d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d7d4`
- `DMCmnUtils!CopyString` at `0x18001d798`
- `DMCmnUtils!CopyString` at `0x18001d798`

## pseudocode

```c
__int64 __fastcall DeleteOmaDmServerAccount(__int16 *a1, int a2)
{
  int AccountIDFromLookupID; // ebx
  HLOCAL hMem; // [rsp+30h] [rbp+8h] BYREF

  hMem = 0;
  if ( !a1 )
    goto LABEL_2;
  if ( !a2 )
  {
    AccountIDFromLookupID = OmaDmGetAccountIDFromLookupID(a1, 0, (unsigned __int16 **)&hMem);
LABEL_8:
    if ( AccountIDFromLookupID < 0 )
      goto LABEL_10;
LABEL_9:
    AccountIDFromLookupID = OmaDmDeleteSecurityAccount((const unsigned __int16 *)hMem, 1u);
    goto LABEL_10;
  }
  if ( a2 == 1 )
  {
    AccountIDFromLookupID = CopyString((const unsigned __int16 *)a1, 0xFFFFFFFF, (unsigned __int16 **)&hMem);
    if ( AccountIDFromLookupID >= 0 )
      goto LABEL_9;
    goto LABEL_8;
  }
LABEL_2:
  AccountIDFromLookupID = -2147024809;
LABEL_10:
  LocalFree(hMem);
  return (unsigned int)AccountIDFromLookupID;
}

```

## disassembly

```asm
0x18001d76c  push    rbx
0x18001d76e  sub     rsp, 20h
0x18001d772  mov     [rsp+28h+hMem], 0
0x18001d77b  test    rcx, rcx
0x18001d77e  jnz     short loc_18001D787
0x18001d780  mov     ebx, 80070057h
0x18001d785  jmp     short loc_18001D7CF
0x18001d787  test    edx, edx
0x18001d789  jz      short loc_18001D7AC
0x18001d78b  cmp     edx, 1
0x18001d78e  jnz     short loc_18001D780
0x18001d790  lea     r8, [rsp+28h+hMem]
0x18001d795  or      edx, 0FFFFFFFFh
0x18001d798  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18001d79f  nop     dword ptr [rax+rax+00h]
0x18001d7a4  mov     ebx, eax
0x18001d7a6  test    eax, eax
0x18001d7a8  js      short loc_18001D7BA
0x18001d7aa  jmp     short loc_18001D7BE
0x18001d7ac  lea     r8, [rsp+28h+hMem]
0x18001d7b1  xor     edx, edx
0x18001d7b3  call    ?OmaDmGetAccountIDFromLookupID@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@PEAPEAG@Z; OmaDmGetAccountIDFromLookupID(ushort const *,tagDMACCOUNTLOOKUPTYPE,ushort * *)
0x18001d7b8  mov     ebx, eax
0x18001d7ba  test    ebx, ebx
0x18001d7bc  js      short loc_18001D7CF
0x18001d7be  mov     rcx, [rsp+28h+hMem]
0x18001d7c3  mov     edx, 1
0x18001d7c8  call    OmaDmDeleteSecurityAccount
0x18001d7cd  mov     ebx, eax
0x18001d7cf  mov     rcx, [rsp+28h+hMem]; hMem
0x18001d7d4  call    cs:__imp_LocalFree
0x18001d7db  nop     dword ptr [rax+rax+00h]
0x18001d7e0  mov     eax, ebx
0x18001d7e2  add     rsp, 20h
0x18001d7e6  pop     rbx
0x18001d7e7  retn
```
