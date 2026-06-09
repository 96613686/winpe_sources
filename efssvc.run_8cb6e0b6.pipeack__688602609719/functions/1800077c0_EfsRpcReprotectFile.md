# EfsRpcReprotectFile

- ea: `0x1800077c0`
- end: `0x1800078d7`
- name: `EfsRpcReprotectFile`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800037b8`
- `0x180003864`
- `0x180003a24`
- `0x1800077c0`
- `0x18000d192`

## import_xrefs

- `EFSCORE!EfsDllGetLocalFileName` at `0x180007841`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180007841`
- `EFSCORE!EfsDllFreeHeap` at `0x1800078a7`
- `EFSCORE!EfsDllFreeHeap` at `0x1800078a7`
- `EFSCORE!EfsDllReprotectFile` at `0x18000786b`
- `EFSCORE!EfsDllReprotectFile` at `0x18000786b`

## pseudocode

```c
__int64 __fastcall EfsRpcReprotectFile(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // ebx
  int v6; // eax
  int v7; // ecx
  int v8; // esi
  int LocalFileName; // eax
  int v10; // ecx
  int v11; // eax
  int v12; // ecx
  _BYTE v14[136]; // [rsp+30h] [rbp-88h] BYREF
  __int16 v15; // [rsp+C8h] [rbp+10h] BYREF
  __int64 v16; // [rsp+D8h] [rbp+20h] BYREF

  memset_0(v14, 0, 0x70u);
  v15 = 0;
  v16 = 0;
  if ( a2 && a3 )
  {
    v6 = EdpBeginLocalOnlyRpcCall((__int64)v14);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v8 = 1;
      LocalFileName = EfsDllGetLocalFileName(a2, 1, &v16, &v15);
      if ( LocalFileName )
      {
        fnEfsLogTrace1(v10, (unsigned int)EFS_API_ERROR, LocalFileName, 6, 44);
      }
      else
      {
        v11 = EfsDllReprotectFile(v14, v16, a3);
        v5 = v11;
        if ( v11 < 0 )
          fnEfsLogTrace1(v12, (unsigned int)EFS_API_ERROR, v11, 6, 51);
      }
    }
    else
    {
      v8 = 0;
      fnEfsLogTrace1(v7, (unsigned int)EFS_API_ERROR, v6, 6, 33);
    }
    if ( v16 )
      EfsDllFreeHeap(v16);
    if ( v8 )
      EdpCleanupLocalOnlyRpcCall(v14);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v5;
}

```

## disassembly

```asm
0x1800077c0  mov     [rsp+arg_0], rbx
0x1800077c5  push    rbp
0x1800077c6  push    rsi
0x1800077c7  push    rdi
0x1800077c8  sub     rsp, 0A0h
0x1800077cf  mov     rbp, rdx
0x1800077d2  lea     rcx, [rsp+0B8h+var_88]; void *
0x1800077d7  xor     edx, edx; Val
0x1800077d9  mov     rdi, r8
0x1800077dc  lea     r8d, [rdx+70h]; Size
0x1800077e0  call    memset_0
0x1800077e5  xor     eax, eax
0x1800077e7  mov     [rsp+0B8h+arg_8], ax
0x1800077ef  mov     [rsp+0B8h+arg_18], rax
0x1800077f7  test    rbp, rbp
0x1800077fa  jnz     short loc_180007806
0x1800077fc  mov     ebx, 80070057h
0x180007801  jmp     loc_1800078C1
0x180007806  test    rdi, rdi
0x180007809  jz      short loc_1800077FC
0x18000780b  lea     rcx, [rsp+0B8h+var_88]
0x180007810  call    EdpBeginLocalOnlyRpcCall
0x180007815  mov     ebx, eax
0x180007817  test    eax, eax
0x180007819  jns     short loc_180007827
0x18000781b  xor     esi, esi
0x18000781d  mov     [rsp+0B8h+var_98], 1221h
0x180007825  jmp     short loc_180007885
0x180007827  mov     esi, 1
0x18000782c  lea     r9, [rsp+0B8h+arg_8]
0x180007834  mov     edx, esi
0x180007836  lea     r8, [rsp+0B8h+arg_18]
0x18000783e  mov     rcx, rbp
0x180007841  call    cs:__imp_EfsDllGetLocalFileName
0x180007848  nop     dword ptr [rax+rax+00h]
0x18000784d  test    eax, eax
0x18000784f  jz      short loc_18000785B
0x180007851  mov     [rsp+0B8h+var_98], 122Ch
0x180007859  jmp     short loc_180007885
0x18000785b  mov     rdx, [rsp+0B8h+arg_18]
0x180007863  lea     rcx, [rsp+0B8h+var_88]
0x180007868  mov     r8, rdi
0x18000786b  call    cs:__imp_EfsDllReprotectFile
0x180007872  nop     dword ptr [rax+rax+00h]
0x180007877  mov     ebx, eax
0x180007879  test    eax, eax
0x18000787b  jns     short loc_18000789A
0x18000787d  mov     [rsp+0B8h+var_98], 1233h
0x180007885  mov     r9d, 6
0x18000788b  lea     rdx, EFS_API_ERROR
0x180007892  mov     r8d, eax
0x180007895  call    fnEfsLogTrace1
0x18000789a  mov     rcx, [rsp+0B8h+arg_18]
0x1800078a2  test    rcx, rcx
0x1800078a5  jz      short loc_1800078B3
0x1800078a7  call    cs:__imp_EfsDllFreeHeap
0x1800078ae  nop     dword ptr [rax+rax+00h]
0x1800078b3  test    esi, esi
0x1800078b5  jz      short loc_1800078C1
0x1800078b7  lea     rcx, [rsp+0B8h+var_88]
0x1800078bc  call    EdpCleanupLocalOnlyRpcCall
0x1800078c1  mov     eax, ebx
0x1800078c3  mov     rbx, [rsp+0B8h+arg_0]
0x1800078cb  add     rsp, 0A0h
0x1800078d2  pop     rdi
0x1800078d3  pop     rsi
0x1800078d4  pop     rbp
0x1800078d5  retn
```
