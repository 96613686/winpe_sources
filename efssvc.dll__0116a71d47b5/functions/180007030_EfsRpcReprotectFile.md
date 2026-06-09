# EfsRpcReprotectFile

- ea: `0x180007030`
- end: `0x180007134`
- name: `EfsRpcReprotectFile`
- size: `260`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180003604`
- `0x1800036a0`
- `0x180003828`
- `0x180007030`
- `0x18000c392`

## import_xrefs

- `EFSCORE!EfsDllGetLocalFileName` at `0x1800070b1`
- `EFSCORE!EfsDllGetLocalFileName` at `0x1800070b1`
- `EFSCORE!EfsDllFreeHeap` at `0x18000710b`
- `EFSCORE!EfsDllFreeHeap` at `0x18000710b`
- `EFSCORE!EfsDllReprotectFile` at `0x1800070d5`
- `EFSCORE!EfsDllReprotectFile` at `0x1800070d5`

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
      EdpCleanupLocalOnlyRpcCall((__int64)v14);
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
0x180007030  mov     [rsp+arg_0], rbx
0x180007035  push    rbp
0x180007036  push    rsi
0x180007037  push    rdi
0x180007038  sub     rsp, 0A0h
0x18000703f  mov     rbp, rdx
0x180007042  lea     rcx, [rsp+0B8h+var_88]; void *
0x180007047  xor     edx, edx; Val
0x180007049  mov     rdi, r8
0x18000704c  lea     r8d, [rdx+70h]; Size
0x180007050  call    memset_0
0x180007055  xor     eax, eax
0x180007057  mov     [rsp+0B8h+arg_8], ax
0x18000705f  mov     [rsp+0B8h+arg_18], rax
0x180007067  test    rbp, rbp
0x18000706a  jnz     short loc_180007076
0x18000706c  mov     ebx, 80070057h
0x180007071  jmp     loc_18000711F
0x180007076  test    rdi, rdi
0x180007079  jz      short loc_18000706C
0x18000707b  lea     rcx, [rsp+0B8h+var_88]
0x180007080  call    EdpBeginLocalOnlyRpcCall
0x180007085  mov     ebx, eax
0x180007087  test    eax, eax
0x180007089  jns     short loc_180007097
0x18000708b  xor     esi, esi
0x18000708d  mov     [rsp+0B8h+var_98], 1221h
0x180007095  jmp     short loc_1800070E9
0x180007097  mov     esi, 1
0x18000709c  lea     r9, [rsp+0B8h+arg_8]
0x1800070a4  mov     edx, esi
0x1800070a6  lea     r8, [rsp+0B8h+arg_18]
0x1800070ae  mov     rcx, rbp
0x1800070b1  call    cs:__imp_EfsDllGetLocalFileName
0x1800070b7  test    eax, eax
0x1800070b9  jz      short loc_1800070C5
0x1800070bb  mov     [rsp+0B8h+var_98], 122Ch
0x1800070c3  jmp     short loc_1800070E9
0x1800070c5  mov     rdx, [rsp+0B8h+arg_18]
0x1800070cd  lea     rcx, [rsp+0B8h+var_88]
0x1800070d2  mov     r8, rdi
0x1800070d5  call    cs:__imp_EfsDllReprotectFile
0x1800070db  mov     ebx, eax
0x1800070dd  test    eax, eax
0x1800070df  jns     short loc_1800070FE
0x1800070e1  mov     [rsp+0B8h+var_98], 1233h
0x1800070e9  mov     r9d, 6
0x1800070ef  lea     rdx, EFS_API_ERROR
0x1800070f6  mov     r8d, eax
0x1800070f9  call    fnEfsLogTrace1
0x1800070fe  mov     rcx, [rsp+0B8h+arg_18]
0x180007106  test    rcx, rcx
0x180007109  jz      short loc_180007111
0x18000710b  call    cs:__imp_EfsDllFreeHeap
0x180007111  test    esi, esi
0x180007113  jz      short loc_18000711F
0x180007115  lea     rcx, [rsp+0B8h+var_88]
0x18000711a  call    EdpCleanupLocalOnlyRpcCall
0x18000711f  mov     eax, ebx
0x180007121  mov     rbx, [rsp+0B8h+arg_0]
0x180007129  add     rsp, 0A0h
0x180007130  pop     rdi
0x180007131  pop     rsi
0x180007132  pop     rbp
0x180007133  retn
```
