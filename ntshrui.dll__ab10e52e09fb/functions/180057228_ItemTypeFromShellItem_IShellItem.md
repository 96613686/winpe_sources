# ItemTypeFromShellItem(IShellItem *)

- ea: `0x180057228`
- end: `0x1800572b6`
- name: `?ItemTypeFromShellItem@@YA?AW4_SHARE_ITEM_TYPE@@PEAUIShellItem@@@Z`
- size: `142`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180022734`
- `0x18005bb88`
- `0x1800683e8`

## callees

- `0x1800135f0`
- `0x180057228`
- `0x18005af54`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800572a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800572a3`
- `SHCORE!__imp_PathIsNetworkPathW` at `0x18005725b`
- `SHCORE!__imp_PathIsNetworkPathW` at `0x18005725b`
- `SHLWAPI!PathIsRootW` at `0x18005726a`
- `SHLWAPI!PathIsRootW` at `0x18005726a`

## pseudocode

```c
__int64 __fastcall ItemTypeFromShellItem(struct IShellItem *a1)
{
  unsigned int v1; // ebx
  int v4; // [rsp+38h] [rbp+10h] BYREF
  LPCWSTR pszPath; // [rsp+40h] [rbp+18h] BYREF

  v1 = 0;
  v4 = 0;
  pszPath = 0;
  if ( (int)GetPathAndAttributes(a1, 541065216, &pszPath, &v4) >= 0 )
  {
    if ( PathIsNetworkPathW(pszPath) || !PathIsRootW(pszPath) )
    {
      if ( v4 == 0x20000000 )
      {
        v1 = 1;
      }
      else if ( (unsigned int)_HasSharingHandler(a1) )
      {
        v1 = 3;
      }
    }
    else
    {
      v1 = 2;
    }
    CoTaskMemFree((LPVOID)pszPath);
  }
  return v1;
}

```

## disassembly

```asm
0x180057228  mov     rax, rsp
0x18005722b  mov     [rax+8], rbx
0x18005722f  push    rdi
0x180057230  sub     rsp, 20h
0x180057234  xor     ebx, ebx
0x180057236  lea     r9, [rax+10h]
0x18005723a  lea     r8, [rax+18h]
0x18005723e  mov     [rax+10h], ebx
0x180057241  mov     edx, 20400000h
0x180057246  mov     [rax+18h], rbx
0x18005724a  mov     rdi, rcx
0x18005724d  call    GetPathAndAttributes
0x180057252  test    eax, eax
0x180057254  js      short loc_1800572A9
0x180057256  mov     rcx, [rsp+28h+pszPath]; pszPath
0x18005725b  call    cs:__imp_PathIsNetworkPathW
0x180057261  test    eax, eax
0x180057263  jnz     short loc_18005727B
0x180057265  mov     rcx, [rsp+28h+pszPath]; pszPath
0x18005726a  call    cs:__imp_PathIsRootW
0x180057270  test    eax, eax
0x180057272  jz      short loc_18005727B
0x180057274  mov     ebx, 2
0x180057279  jmp     short loc_18005729E
0x18005727b  cmp     [rsp+28h+arg_8], 20000000h
0x180057283  jnz     short loc_18005728C
0x180057285  mov     ebx, 1
0x18005728a  jmp     short loc_18005729E
0x18005728c  mov     rcx, rdi; struct IShellItem *
0x18005728f  call    ?_HasSharingHandler@@YAHPEAUIShellItem@@@Z; _HasSharingHandler(IShellItem *)
0x180057294  test    eax, eax
0x180057296  mov     ecx, 3
0x18005729b  cmovnz  ebx, ecx
0x18005729e  mov     rcx, [rsp+28h+pszPath]; pv
0x1800572a3  call    cs:__imp_CoTaskMemFree
0x1800572a9  mov     eax, ebx
0x1800572ab  mov     rbx, [rsp+28h+arg_0]
0x1800572b0  add     rsp, 20h
0x1800572b4  pop     rdi
0x1800572b5  retn
```
