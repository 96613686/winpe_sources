# PutFileData

- ea: `0x10020f50`
- end: `0x10021054`
- name: `PutFileData`
- size: `260`
- prototype: `int __stdcall(DWORD NumberOfBytesWritten, int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x100209c0`
- `0x10022400`

## callees

- `0x1000b070`
- `0x1000b200`
- `0x10020f50`
- `0x10029520`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x1002100b`
- `KERNEL32!SetFilePointer` at `0x1002100b`
- `KERNEL32!WriteFile` at `0x10020fca`
- `KERNEL32!WriteFile` at `0x10020fea`
- `KERNEL32!WriteFile` at `0x10020fac`
- `KERNEL32!WriteFile` at `0x10020fd7`

## pseudocode

```c
int __stdcall PutFileData(HANDLE *NumberOfBytesWritten, int a2, int a3)
{
  HANDLE *v3; // edi
  HANDLE *v4; // ebp
  CHAR *v5; // ebx
  int v7; // esi
  BOOL (__stdcall *v8)(HANDLE, LPCVOID, DWORD, LPDWORD, LPOVERLAPPED); // eax
  DWORD v9; // eax
  HANDLE v10; // [esp-14h] [ebp-24h]
  DWORD nNumberOfBytesToWrite; // [esp+Ch] [ebp-4h] BYREF

  v3 = NumberOfBytesWritten;
  v4 = NumberOfBytesWritten + 2059;
  nNumberOfBytesToWrite = 8 * (_DWORD)NumberOfBytesWritten[2059];
  v5 = (CHAR *)MemAllocate(nNumberOfBytesToWrite);
  if ( !v5 )
    return -1011;
  v7 = TextConvertFromUnicode(a2, v3[2057], v4, v5, (int)&nNumberOfBytesToWrite);
  if ( v7 < 0 )
    goto LABEL_15;
  v8 = WriteFile;
  if ( a2 == 1200 && a3 )
  {
    if ( !WriteFile(*v3, &dword_10002A30, 2u, (LPDWORD)&NumberOfBytesWritten, 0) || NumberOfBytesWritten != (HANDLE *)2 )
      goto LABEL_14;
    v8 = WriteFile;
  }
  if ( !v8(*v3, v5, nNumberOfBytesToWrite, (LPDWORD)&NumberOfBytesWritten, 0)
    || NumberOfBytesWritten != (HANDLE *)nNumberOfBytesToWrite )
  {
LABEL_14:
    v7 = -1022;
LABEL_15:
    MemFree(v5);
    return v7;
  }
  v10 = *v3;
  v3[2081] = *v4;
  v9 = SetFilePointer(v10, 0, 0, 1u);
  if ( v9 == -1 )
  {
    MemFree(v5);
    return -1;
  }
  else
  {
    v3[2080] = (HANDLE)v9;
    MemFree(v5);
    return v7;
  }
}

```

## disassembly

```asm
0x10020f50  push    ecx
0x10020f51  push    ebx
0x10020f52  push    ebp
0x10020f53  push    edi
0x10020f54  mov     edi, [esp+10h+NumberOfBytesWritten]
0x10020f58  mov     eax, [edi+202Ch]
0x10020f5e  lea     ebp, [edi+202Ch]
0x10020f64  shl     eax, 3
0x10020f67  push    eax; Size
0x10020f68  mov     [esp+14h+nNumberOfBytesToWrite], eax
0x10020f6c  call    _MemAllocate@4; MemAllocate(x)
0x10020f71  mov     ebx, eax
0x10020f73  test    ebx, ebx
0x10020f75  jnz     short loc_10020F83
0x10020f77  pop     edi
0x10020f78  pop     ebp
0x10020f79  mov     eax, 0FFFFFC0Dh
0x10020f7e  pop     ebx
0x10020f7f  pop     ecx
0x10020f80  retn    0Ch
0x10020f83  push    esi
0x10020f84  lea     eax, [esp+14h+nNumberOfBytesToWrite]
0x10020f88  push    eax; int
0x10020f89  push    ebx; lpMultiByteStr
0x10020f8a  push    ebp; int
0x10020f8b  push    dword ptr [edi+2024h]; Src
0x10020f91  push    [esp+24h+arg_4]; int
0x10020f95  call    _TextConvertFromUnicode@20; TextConvertFromUnicode(x,x,x,x,x)
0x10020f9a  mov     esi, eax
0x10020f9c  test    esi, esi
0x10020f9e  js      loc_10021044
0x10020fa4  cmp     [esp+14h+arg_4], 4B0h
0x10020fac  mov     eax, ds:__imp__WriteFile@20; WriteFile(x,x,x,x,x)
0x10020fb1  jnz     short loc_10020FDC
0x10020fb3  cmp     [esp+14h+arg_8], 0
0x10020fb8  jz      short loc_10020FDC
0x10020fba  push    0; lpOverlapped
0x10020fbc  lea     ecx, [esp+18h+NumberOfBytesWritten]
0x10020fc0  push    ecx; lpNumberOfBytesWritten
0x10020fc1  push    2; nNumberOfBytesToWrite
0x10020fc3  push    offset dword_10002A30; lpBuffer
0x10020fc8  push    dword ptr [edi]; hFile
0x10020fca  call    eax ; WriteFile(x,x,x,x,x); WriteFile(x,x,x,x,x)
0x10020fcc  test    eax, eax
0x10020fce  jz      short loc_1002103F
0x10020fd0  cmp     [esp+14h+NumberOfBytesWritten], 2
0x10020fd5  jnz     short loc_1002103F
0x10020fd7  mov     eax, ds:__imp__WriteFile@20; WriteFile(x,x,x,x,x)
0x10020fdc  push    0; lpOverlapped
0x10020fde  lea     ecx, [esp+18h+NumberOfBytesWritten]
0x10020fe2  push    ecx; lpNumberOfBytesWritten
0x10020fe3  push    [esp+1Ch+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x10020fe7  push    ebx; lpBuffer
0x10020fe8  push    dword ptr [edi]; hFile
0x10020fea  call    eax ; WriteFile(x,x,x,x,x); WriteFile(x,x,x,x,x)
0x10020fec  test    eax, eax
0x10020fee  jz      short loc_1002103F
0x10020ff0  mov     eax, [esp+14h+NumberOfBytesWritten]
0x10020ff4  cmp     eax, [esp+14h+nNumberOfBytesToWrite]
0x10020ff8  jnz     short loc_1002103F
0x10020ffa  mov     eax, [ebp+0]
0x10020ffd  push    1; dwMoveMethod
0x10020fff  push    0; lpDistanceToMoveHigh
0x10021001  push    0; lDistanceToMove
0x10021003  push    dword ptr [edi]; hFile
0x10021005  mov     [edi+2084h], eax
0x1002100b  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x10021011  cmp     eax, 0FFFFFFFFh
0x10021014  jz      short loc_1002102C
0x10021016  push    ebx
0x10021017  mov     [edi+2080h], eax
0x1002101d  call    _MemFree@4; MemFree(x)
0x10021022  mov     eax, esi
0x10021024  pop     esi
0x10021025  pop     edi
0x10021026  pop     ebp
0x10021027  pop     ebx
0x10021028  pop     ecx
0x10021029  retn    0Ch
0x1002102c  push    ebx
0x1002102d  or      esi, 0FFFFFFFFh
0x10021030  call    _MemFree@4; MemFree(x)
0x10021035  mov     eax, esi
0x10021037  pop     esi
0x10021038  pop     edi
0x10021039  pop     ebp
0x1002103a  pop     ebx
0x1002103b  pop     ecx
0x1002103c  retn    0Ch
0x1002103f  mov     esi, 0FFFFFC02h
0x10021044  push    ebx
0x10021045  call    _MemFree@4; MemFree(x)
0x1002104a  mov     eax, esi
0x1002104c  pop     esi
0x1002104d  pop     edi
0x1002104e  pop     ebp
0x1002104f  pop     ebx
0x10021050  pop     ecx
0x10021051  retn    0Ch
```
