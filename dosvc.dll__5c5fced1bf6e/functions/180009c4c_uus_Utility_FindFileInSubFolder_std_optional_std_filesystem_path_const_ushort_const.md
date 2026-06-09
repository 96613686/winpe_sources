# uus::Utility::FindFileInSubFolder(std::optional<std::filesystem::path> const &,ushort const *)

- ea: `0x180009c4c`
- end: `0x180009cfa`
- name: `?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBV34@PEBG@Z`
- size: `174`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001170`

## callees

- `0x180001380`
- `0x18000342c`
- `0x180009c4c`

## pseudocode

```c
__int64 __fastcall uus::Utility::FindFileInSubFolder(__int64 a1, __int64 a2)
{
  _BYTE *FileInSubFolder; // rcx
  int v4; // edx
  int v5; // edi
  _BYTE v7[40]; // [rsp+28h] [rbp-60h] BYREF
  _BYTE v8[56]; // [rsp+50h] [rbp-38h] BYREF

  if ( *(_BYTE *)(a2 + 32) )
  {
    FileInSubFolder = (_BYTE *)uus::Utility::FindFileInSubFolder((__int64)v8, (_QWORD *)a2);
    v4 = 0;
    v5 = 1;
  }
  else
  {
    v5 = 0;
    v7[32] = 0;
    FileInSubFolder = v7;
    v4 = 2;
  }
  *(_BYTE *)(a1 + 32) = 0;
  if ( FileInSubFolder[32] )
  {
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_OWORD *)a1 = *(_OWORD *)FileInSubFolder;
    *(_OWORD *)(a1 + 16) = *((_OWORD *)FileInSubFolder + 1);
    *(_WORD *)FileInSubFolder = 0;
    *((_QWORD *)FileInSubFolder + 2) = 0;
    *((_QWORD *)FileInSubFolder + 3) = 7;
    *(_BYTE *)(a1 + 32) = 1;
  }
  if ( v4 )
    std::_Optional_destruct_base<std::filesystem::path,0>::~_Optional_destruct_base<std::filesystem::path,0>(v7);
  if ( v5 )
    std::_Optional_destruct_base<std::filesystem::path,0>::~_Optional_destruct_base<std::filesystem::path,0>(v8);
  return a1;
}

```

## disassembly

```asm
0x180009c4c  mov     [rsp+arg_0], rbx
0x180009c51  push    rdi
0x180009c52  sub     rsp, 80h
0x180009c59  cmp     byte ptr [rdx+20h], 0
0x180009c5d  mov     rbx, rcx
0x180009c60  jz      short loc_180009C78
0x180009c62  lea     rcx, [rsp+88h+var_38]
0x180009c67  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z; uus::Utility::FindFileInSubFolder(std::filesystem::path const &,ushort const *)
0x180009c6c  mov     rcx, rax
0x180009c6f  xor     edx, edx
0x180009c71  mov     edi, 1
0x180009c76  jmp     short loc_180009C87
0x180009c78  xor     edi, edi
0x180009c7a  mov     [rsp+88h+var_40], 0
0x180009c7f  lea     rcx, [rsp+88h+var_60]
0x180009c84  lea     edx, [rdi+2]
0x180009c87  mov     byte ptr [rbx+20h], 0
0x180009c8b  cmp     byte ptr [rcx+20h], 0
0x180009c8f  jz      short loc_180009CCA
0x180009c91  xorps   xmm0, xmm0
0x180009c94  xor     eax, eax
0x180009c96  movups  xmmword ptr [rbx], xmm0
0x180009c99  mov     qword ptr [rbx+10h], 0
0x180009ca1  mov     qword ptr [rbx+18h], 0
0x180009ca9  movups  xmm0, xmmword ptr [rcx]
0x180009cac  movups  xmmword ptr [rbx], xmm0
0x180009caf  movups  xmm1, xmmword ptr [rcx+10h]
0x180009cb3  movups  xmmword ptr [rbx+10h], xmm1
0x180009cb7  mov     [rcx], ax
0x180009cba  mov     [rcx+10h], rax
0x180009cbe  mov     qword ptr [rcx+18h], 7
0x180009cc6  mov     byte ptr [rbx+20h], 1
0x180009cca  test    edx, edx
0x180009ccc  jz      short loc_180009CD8
0x180009cce  lea     rcx, [rsp+88h+var_60]
0x180009cd3  call    ??1?$_Optional_destruct_base@Vpath@filesystem@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::filesystem::path,0>::~_Optional_destruct_base<std::filesystem::path,0>(void)
0x180009cd8  test    edi, edi
0x180009cda  jz      short loc_180009CE6
0x180009cdc  lea     rcx, [rsp+88h+var_38]
0x180009ce1  call    ??1?$_Optional_destruct_base@Vpath@filesystem@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::filesystem::path,0>::~_Optional_destruct_base<std::filesystem::path,0>(void)
0x180009ce6  mov     rax, rbx
0x180009ce9  mov     rbx, [rsp+88h+arg_0]
0x180009cf1  add     rsp, 80h
0x180009cf8  pop     rdi
0x180009cf9  retn
```
