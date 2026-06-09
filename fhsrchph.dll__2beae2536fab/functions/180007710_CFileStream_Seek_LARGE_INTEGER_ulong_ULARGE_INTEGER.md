# CFileStream::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)

- ea: `0x180007710`
- end: `0x18000779c`
- name: `?Seek@CFileStream@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z`
- size: `140`
- prototype: `signed int __fastcall(CFileStream *this, union _LARGE_INTEGER, int, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180007710`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x18000775c`
- `KERNEL32!SetFilePointer` at `0x18000775c`
- `KERNEL32!GetLastError` at `0x180007769`
- `KERNEL32!GetLastError` at `0x180007769`

## pseudocode

```c
signed int __fastcall CFileStream::Seek(CFileStream *this, union _LARGE_INTEGER a2, int a3, union _ULARGE_INTEGER *a4)
{
  int v5; // r8d
  signed int result; // eax
  DWORD v7; // r9d
  void *v8; // rcx
  DWORD v9; // edi
  bool v10; // sf
  LONG DistanceToMoveHigh; // [rsp+40h] [rbp+18h] BYREF

  if ( a3 )
  {
    v5 = a3 - 1;
    if ( v5 )
    {
      if ( v5 != 1 )
        return -2147024809;
      v7 = 2;
    }
    else
    {
      v7 = 1;
    }
  }
  else
  {
    v7 = 0;
  }
  v8 = (void *)*((_QWORD *)this + 3);
  DistanceToMoveHigh = a2.HighPart;
  v9 = SetFilePointer(v8, a2.LowPart, &DistanceToMoveHigh, v7);
  if ( v9 != -1 )
  {
    result = 0;
LABEL_14:
    if ( a4 )
    {
      a4->HighPart = DistanceToMoveHigh;
      a4->LowPart = v9;
    }
    return result;
  }
  result = GetLastError();
  v10 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v10 = result < 0;
  }
  if ( !v10 )
    goto LABEL_14;
  return result;
}

```

## disassembly

```asm
0x180007710  mov     [rsp+arg_0], rbx
0x180007715  push    rdi
0x180007716  sub     rsp, 20h
0x18000771a  mov     rbx, r9
0x18000771d  test    r8d, r8d
0x180007720  jz      short loc_180007745
0x180007722  sub     r8d, 1
0x180007726  jz      short loc_18000773D
0x180007728  cmp     r8d, 1
0x18000772c  jz      short loc_180007735
0x18000772e  mov     eax, 80070057h
0x180007733  jmp     short loc_180007791
0x180007735  mov     r9d, 2
0x18000773b  jmp     short loc_180007748
0x18000773d  mov     r9d, 1
0x180007743  jmp     short loc_180007748
0x180007745  xor     r9d, r9d; dwMoveMethod
0x180007748  mov     rcx, [rcx+18h]; hFile
0x18000774c  lea     r8, [rsp+28h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x180007751  mov     rax, rdx
0x180007754  shr     rax, 20h
0x180007758  mov     [rsp+28h+DistanceToMoveHigh], eax
0x18000775c  call    cs:__imp_SetFilePointer
0x180007762  mov     edi, eax
0x180007764  cmp     eax, 0FFFFFFFFh
0x180007767  jnz     short loc_180007781
0x180007769  call    cs:__imp_GetLastError
0x18000776f  test    eax, eax
0x180007771  jle     short loc_18000777D
0x180007773  movzx   eax, ax
0x180007776  or      eax, 80070000h
0x18000777b  test    eax, eax
0x18000777d  js      short loc_180007791
0x18000777f  jmp     short loc_180007783
0x180007781  xor     eax, eax
0x180007783  test    rbx, rbx
0x180007786  jz      short loc_180007791
0x180007788  mov     ecx, [rsp+28h+DistanceToMoveHigh]
0x18000778c  mov     [rbx+4], ecx
0x18000778f  mov     [rbx], edi
0x180007791  mov     rbx, [rsp+28h+arg_0]
0x180007796  add     rsp, 20h
0x18000779a  pop     rdi
0x18000779b  retn
```
