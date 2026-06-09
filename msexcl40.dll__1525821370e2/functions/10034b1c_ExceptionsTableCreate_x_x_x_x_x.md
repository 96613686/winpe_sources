# ExceptionsTableCreate(x,x,x,x,x)

- ea: `0x10034b1c`
- end: `0x10034bc4`
- name: `_ExceptionsTableCreate@20`
- size: `168`
- prototype: `int __stdcall(int, wchar_t *FullPath, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callers

- `0x10027e33`

## callees

- `0x1002580a`
- `0x1002a7de`
- `0x10034b1c`
- `0x10034bca`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x10034b67`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x10034b67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10034b75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10034b75`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x10034b94`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x10034b94`

## pseudocode

```c
int __fastcall ExceptionsTableCreate(int a1, int a2, int a3, wchar_t *FullPath, int *a5)
{
  int v7; // eax
  int v8; // esi
  DWORD CurrentProcessId; // eax
  int v11; // eax
  int v12; // esi

  if ( a1 != -1 )
  {
    v7 = MemAllocate(1848);
    v8 = v7;
    if ( !v7 )
      return -1011;
    *(_DWORD *)(v7 + 24) = a3;
    *(_DWORD *)v7 = a1;
    *(_DWORD *)(v7 + 4) = a2;
    __wsplitpath_s(FullPath, 0, 0, 0, 0, (wchar_t *)(v7 + 28), 0x82u, 0, 0);
    *a5 = v8;
    CurrentProcessId = GetCurrentProcessId();
    v11 = ISAMDBFindTask(CurrentProcessId);
    if ( v11 )
    {
      v12 = JetSetSystemParameter(v11 + 32, a1, 67, pfnExceptionsTableAdd, 0);
      if ( !v12 )
        return v12;
    }
    else
    {
      v12 = -1029;
    }
    ExceptionsTableClose(*a5);
    return v12;
  }
  *a5 = 0;
  return 0;
}

```

## disassembly

```asm
0x10034b1c  mov     edi, edi
0x10034b1e  push    ebp
0x10034b1f  mov     ebp, esp
0x10034b21  push    ebx
0x10034b22  push    esi
0x10034b23  push    edi
0x10034b24  mov     edi, ecx
0x10034b26  mov     ebx, edx
0x10034b28  cmp     edi, 0FFFFFFFFh
0x10034b2b  jz      loc_10034BB2
0x10034b31  mov     ecx, 738h
0x10034b36  call    _MemAllocate@4; MemAllocate(x)
0x10034b3b  mov     esi, eax
0x10034b3d  test    esi, esi
0x10034b3f  jnz     short loc_10034B48
0x10034b41  mov     eax, 0FFFFFC0Dh
0x10034b46  jmp     short loc_10034BBD
0x10034b48  mov     eax, [ebp+arg_0]
0x10034b4b  xor     ecx, ecx
0x10034b4d  push    ecx; ExtCount
0x10034b4e  push    ecx; Ext
0x10034b4f  push    82h; FilenameCount
0x10034b54  mov     [esi+18h], eax
0x10034b57  lea     eax, [esi+1Ch]
0x10034b5a  push    eax; Filename
0x10034b5b  push    ecx; DirCount
0x10034b5c  push    ecx; Dir
0x10034b5d  push    ecx; DriveCount
0x10034b5e  push    ecx; Drive
0x10034b5f  push    [ebp+FullPath]; FullPath
0x10034b62  mov     [esi], edi
0x10034b64  mov     [esi+4], ebx
0x10034b67  call    ds:__imp___wsplitpath_s
0x10034b6d  mov     ebx, [ebp+arg_8]
0x10034b70  add     esp, 24h
0x10034b73  mov     [ebx], esi
0x10034b75  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x10034b7b  mov     ecx, eax
0x10034b7d  call    _ISAMDBFindTask@4; ISAMDBFindTask(x)
0x10034b82  test    eax, eax
0x10034b84  jz      short loc_10034BA2
0x10034b86  push    0
0x10034b88  push    offset _pfnExceptionsTableAdd@16; pfnExceptionsTableAdd(x,x,x,x)
0x10034b8d  push    43h ; 'C'
0x10034b8f  push    edi
0x10034b90  add     eax, 20h ; ' '
0x10034b93  push    eax
0x10034b94  call    ds:__imp__JetSetSystemParameter@20; JetSetSystemParameter(x,x,x,x,x)
0x10034b9a  mov     esi, eax
0x10034b9c  test    esi, esi
0x10034b9e  jz      short loc_10034BAE
0x10034ba0  jmp     short loc_10034BA7
0x10034ba2  mov     esi, 0FFFFFBFBh
0x10034ba7  mov     ecx, [ebx]
0x10034ba9  call    _ExceptionsTableClose@4; ExceptionsTableClose(x)
0x10034bae  mov     eax, esi
0x10034bb0  jmp     short loc_10034BBD
0x10034bb2  mov     eax, [ebp+arg_8]
0x10034bb5  mov     dword ptr [eax], 0
0x10034bbb  xor     eax, eax
0x10034bbd  pop     edi
0x10034bbe  pop     esi
0x10034bbf  pop     ebx
0x10034bc0  pop     ebp
0x10034bc1  retn    0Ch
```
