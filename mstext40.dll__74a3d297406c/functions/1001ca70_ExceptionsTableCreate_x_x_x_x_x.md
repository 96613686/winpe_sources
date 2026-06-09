# ExceptionsTableCreate(x,x,x,x,x)

- ea: `0x1001ca70`
- end: `0x1001caf5`
- name: `_ExceptionsTableCreate@20`
- size: `133`
- prototype: `int __stdcall(int, int, int, wchar_t *FullPath, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x100108e0`

## callees

- `0x1000b070`
- `0x1000c2f0`
- `0x1001ca20`
- `0x1001ca70`
- `0x1001cb00`

## pseudocode

```c
int __stdcall ExceptionsTableCreate(int a1, int a2, int a3, wchar_t *FullPath, int *a5)
{
  int v5; // eax
  int v6; // esi
  int v8; // esi

  if ( a1 == -1 )
  {
    *a5 = 0;
    return 0;
  }
  else
  {
    v5 = MemAllocate(0x738u);
    v6 = v5;
    if ( v5 )
    {
      *(_DWORD *)(v5 + 4) = a2;
      *(_DWORD *)(v5 + 24) = a3;
      *(_DWORD *)v5 = a1;
      SplitPath(FullPath, 0, 0, 0, 0, (wchar_t *)(v5 + 28), 0x82u, 0, 0);
      *a5 = v6;
      v8 = ExceptionsTableRegister(a1);
      if ( v8 )
        ExceptionsTableClose(*a5);
      return v8;
    }
    else
    {
      return -1011;
    }
  }
}

```

## disassembly

```asm
0x1001ca70  push    edi
0x1001ca71  mov     edi, [esp+4+arg_0]
0x1001ca75  cmp     edi, 0FFFFFFFFh
0x1001ca78  jz      short loc_1001CAE5
0x1001ca7a  push    esi
0x1001ca7b  push    738h; Size
0x1001ca80  call    _MemAllocate@4; MemAllocate(x)
0x1001ca85  mov     esi, eax
0x1001ca87  test    esi, esi
0x1001ca89  jnz     short loc_1001CA95
0x1001ca8b  pop     esi
0x1001ca8c  mov     eax, 0FFFFFC0Dh
0x1001ca91  pop     edi
0x1001ca92  retn    14h
0x1001ca95  mov     eax, [esp+8+arg_4]
0x1001ca99  push    ebx
0x1001ca9a  push    0; ExtCount
0x1001ca9c  push    0; Ext
0x1001ca9e  push    82h; FilenameCount
0x1001caa3  mov     [esi+4], eax
0x1001caa6  mov     eax, [esp+18h+arg_8]
0x1001caaa  mov     [esi+18h], eax
0x1001caad  lea     eax, [esi+1Ch]
0x1001cab0  push    eax; Filename
0x1001cab1  push    0; DirCount
0x1001cab3  push    0; Dir
0x1001cab5  push    0; DriveCount
0x1001cab7  push    0; Drive
0x1001cab9  push    [esp+2Ch+FullPath]; FullPath
0x1001cabd  mov     [esi], edi
0x1001cabf  call    _SplitPath@36; SplitPath(x,x,x,x,x,x,x,x,x)
0x1001cac4  mov     ebx, [esp+0Ch+arg_10]
0x1001cac8  push    edi
0x1001cac9  mov     [ebx], esi
0x1001cacb  call    ExceptionsTableRegister
0x1001cad0  mov     esi, eax
0x1001cad2  test    esi, esi
0x1001cad4  jz      short loc_1001CADD
0x1001cad6  push    dword ptr [ebx]
0x1001cad8  call    _ExceptionsTableClose@4; ExceptionsTableClose(x)
0x1001cadd  pop     ebx
0x1001cade  mov     eax, esi
0x1001cae0  pop     esi
0x1001cae1  pop     edi
0x1001cae2  retn    14h
0x1001cae5  mov     eax, [esp+4+arg_10]
0x1001cae9  pop     edi
0x1001caea  mov     dword ptr [eax], 0
0x1001caf0  xor     eax, eax
0x1001caf2  retn    14h
```
