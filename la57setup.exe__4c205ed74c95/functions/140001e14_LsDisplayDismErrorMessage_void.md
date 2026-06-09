# LsDisplayDismErrorMessage(void)

- ea: `0x140001e14`
- end: `0x140001e71`
- name: `?LsDisplayDismErrorMessage@@YAXXZ`
- size: `93`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140001ca4`

## callees

- `0x140001e14`
- `0x140001f34`
- `0x140001fc4`

## import_xrefs

- `DismApi!DismGetLastErrorMessage` at `0x140001e2f`
- `DismApi!DismGetLastErrorMessage` at `0x140001e2f`
- `DismApi!DismDelete` at `0x140001e5a`
- `DismApi!DismDelete` at `0x140001e5a`

## pseudocode

```c
void LsDisplayDismErrorMessage(void)
{
  LPCWCH *v0; // [rsp+30h] [rbp+8h] BYREF

  v0 = 0;
  if ( LsiDismState )
  {
    if ( (int)DismGetLastErrorMessage(&v0) >= 0 && v0 && *v0 )
    {
      LsDisplayString(*v0, 1);
      DismDelete(v0);
    }
    else
    {
      LsDisplayMessage(0xC1001007);
    }
  }
}

```

## disassembly

```asm
0x140001e14  sub     rsp, 28h
0x140001e18  cmp     cs:?LsiDismState@@3W4_LSI_DISM_STATE@@A, 0; _LSI_DISM_STATE LsiDismState
0x140001e1f  mov     [rsp+28h+arg_0], 0
0x140001e28  jz      short loc_140001E6C
0x140001e2a  lea     rcx, [rsp+28h+arg_0]
0x140001e2f  call    cs:__imp_DismGetLastErrorMessage
0x140001e35  test    eax, eax
0x140001e37  js      short loc_140001E62
0x140001e39  mov     rax, [rsp+28h+arg_0]
0x140001e3e  test    rax, rax
0x140001e41  jz      short loc_140001E62
0x140001e43  mov     rcx, [rax]; lpWideCharStr
0x140001e46  test    rcx, rcx
0x140001e49  jz      short loc_140001E62
0x140001e4b  mov     edx, 1; int
0x140001e50  call    ?LsDisplayString@@YAXPEBGH@Z; LsDisplayString(ushort const *,int)
0x140001e55  mov     rcx, [rsp+28h+arg_0]
0x140001e5a  call    cs:__imp_DismDelete
0x140001e60  jmp     short loc_140001E6C
0x140001e62  mov     ecx, 0C1001007h; dwMessageId
0x140001e67  call    ?LsDisplayMessage@@YAXKZZ; LsDisplayMessage(ulong,...)
0x140001e6c  add     rsp, 28h
0x140001e70  retn
```
