# CDataObj_CreateInstance

- ea: `0x180002e5c`
- end: `0x180002f0b`
- name: `CDataObj_CreateInstance`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003400`

## callees

- `0x180002e5c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002e78`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002e78`
- `USER32!RegisterClipboardFormatA` at `0x180002ebb`
- `USER32!RegisterClipboardFormatA` at `0x180002ece`
- `USER32!RegisterClipboardFormatA` at `0x180002ee1`
- `USER32!RegisterClipboardFormatA` at `0x180002ebb`
- `USER32!RegisterClipboardFormatA` at `0x180002ece`
- `USER32!RegisterClipboardFormatA` at `0x180002ee1`

## string_xrefs

- `0x180002ed4`: `FileGroupDescriptor`
- `0x180002ec1`: `FileGroupDescriptorW`

## pseudocode

```c
__int64 __fastcall CDataObj_CreateInstance(int a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  _DWORD *v9; // rax
  bool v10; // zf

  v9 = LocalAlloc(0x40u, 0x28u);
  if ( v9 )
  {
    v10 = g_cfFileContents == 0;
    *(_QWORD *)v9 = c_CDataObjVtbl;
    v9[2] = 1;
    v9[3] = a1;
    *((_QWORD *)v9 + 2) = a2;
    *((_QWORD *)v9 + 3) = a3;
    *((_QWORD *)v9 + 4) = a4;
    *a5 = v9;
    if ( v10 )
    {
      g_cfFileContents = RegisterClipboardFormatA("FileContents");
      g_cfFileGroupDescriptorW = RegisterClipboardFormatA("FileGroupDescriptorW");
      g_cfFileGroupDescriptorA = RegisterClipboardFormatA("FileGroupDescriptor");
    }
    return 0;
  }
  else
  {
    *a5 = 0;
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180002e5c  push    rbx
0x180002e5e  push    rbp
0x180002e5f  push    rsi
0x180002e60  push    rdi
0x180002e61  sub     rsp, 28h
0x180002e65  mov     rsi, rdx
0x180002e68  mov     ebp, ecx
0x180002e6a  mov     edx, 28h ; '('; uBytes
0x180002e6f  mov     rbx, r9
0x180002e72  mov     rdi, r8
0x180002e75  lea     ecx, [rdx+18h]; uFlags
0x180002e78  call    cs:__imp_LocalAlloc
0x180002e7e  test    rax, rax
0x180002e81  jz      short loc_180002EF1
0x180002e83  cmp     cs:g_cfFileContents, 0
0x180002e8a  lea     rcx, c_CDataObjVtbl
0x180002e91  mov     [rax], rcx
0x180002e94  mov     rcx, [rsp+48h+arg_20]
0x180002e99  mov     dword ptr [rax+8], 1
0x180002ea0  mov     [rax+0Ch], ebp
0x180002ea3  mov     [rax+10h], rsi
0x180002ea7  mov     [rax+18h], rdi
0x180002eab  mov     [rax+20h], rbx
0x180002eaf  mov     [rcx], rax
0x180002eb2  jnz     short loc_180002EED
0x180002eb4  lea     rcx, c_szFileContents; "FileContents"
0x180002ebb  call    cs:__imp_RegisterClipboardFormatA
0x180002ec1  lea     rcx, c_szFileGroupDescriptorW; "FileGroupDescriptorW"
0x180002ec8  mov     cs:g_cfFileContents, eax
0x180002ece  call    cs:__imp_RegisterClipboardFormatA
0x180002ed4  lea     rcx, c_szFileGroupDescriptorA; "FileGroupDescriptor"
0x180002edb  mov     cs:g_cfFileGroupDescriptorW, eax
0x180002ee1  call    cs:__imp_RegisterClipboardFormatA
0x180002ee7  mov     cs:g_cfFileGroupDescriptorA, eax
0x180002eed  xor     eax, eax
0x180002eef  jmp     short loc_180002F02
0x180002ef1  mov     rax, [rsp+48h+arg_20]
0x180002ef6  mov     qword ptr [rax], 0
0x180002efd  mov     eax, 8007000Eh
0x180002f02  add     rsp, 28h
0x180002f06  pop     rdi
0x180002f07  pop     rsi
0x180002f08  pop     rbp
0x180002f09  pop     rbx
0x180002f0a  retn
```
