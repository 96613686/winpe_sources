# File::Write(ulong,void *,ulong,Err &)

- ea: `0x1002e740`
- end: `0x1002e8b7`
- name: `?Write@File@@QAEXKPAXKAAVErr@@@Z`
- size: `375`
- prototype: `void __thiscall(File *__hidden this, LONG lDistanceToMove, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, struct Err *)`
- caller_count: `6`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x100223b0`
- `0x10023bb0`
- `0x10023fc0`
- `0x10024070`
- `0x10042760`
- `0x10042e50`

## callees

- `0x10025e60`
- `0x10025ee0`
- `0x1002e740`
- `0x1002ed90`
- `0x1004eda0`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1002e836`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1002e836`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1002e88e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1002e88e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1002e79e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1002e866`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1002e79e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1002e866`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1002e845`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1002e845`

## pseudocode

```c
void __thiscall File::Write(
        File *this,
        unsigned int lDistanceToMove,
        LPCVOID lpBuffer,
        DWORD nNumberOfBytesToWrite,
        struct Err *a5)
{
  struct Err *v6; // ecx
  int v7; // ebx
  struct Err *v8; // ecx
  struct _OVERLAPPED Overlapped; // [esp+10h] [ebp-38h] BYREF
  _DWORD v10[3]; // [esp+24h] [ebp-24h] BYREF
  void *Block; // [esp+30h] [ebp-18h]
  void *v12; // [esp+34h] [ebp-14h]
  DWORD NumberOfBytesWritten; // [esp+38h] [ebp-10h] BYREF
  int v14; // [esp+44h] [ebp-4h]

  if ( *((char *)this + 16) < 0 )
    goto LABEL_17;
  Overlapped.8 = (union _OVERLAPPED::$742A73540840F318F86F9CEE3D494648)lDistanceToMove;
  Overlapped.hEvent = 0;
  if ( WriteFile(*(HANDLE *)this, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, &Overlapped) )
  {
    if ( NumberOfBytesWritten != nNumberOfBytesToWrite )
      Err::SetError(a5, -1808, v6);
  }
  else
  {
    v10[0] = 1;
    v14 = 0;
    System::ErrGetLastError(v6);
    v7 = v10[0];
    if ( (v10[0] & 1) != 0 || v10[1] != -1003 )
    {
      if ( (v10[0] & 8) != 0 && v10[0] > *(_DWORD *)a5 )
        Err::operator=(v10);
    }
    else
    {
      *((_DWORD *)this + 4) |= 0x80u;
    }
    v14 = -1;
    if ( (v7 & 0xFFFFFFFE) != 0 )
    {
      if ( Block )
        operator delete[](Block);
      if ( v12 )
        operator delete[](v12);
    }
  }
  if ( *((char *)this + 16) < 0 )
  {
LABEL_17:
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 20));
    if ( SetFilePointer(*(HANDLE *)this, lDistanceToMove, 0, 0) == -1
      || !WriteFile(*(HANDLE *)this, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
    {
      System::ErrGetLastError(v8);
    }
    else if ( NumberOfBytesWritten != nNumberOfBytesToWrite )
    {
      Err::SetError(a5, -1808, v8);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 20));
  }
  if ( (*(_BYTE *)a5 & 8) != 0 )
    File::SetExtErrInfo(this, a5, 0);
}

```

## disassembly

```asm
0x1002e740  mov     edi, edi
0x1002e742  push    ebp
0x1002e743  mov     ebp, esp
0x1002e745  push    0FFFFFFFFh
0x1002e747  push    offset ?Write@File@@QAEXKPAXKAAVErr@@@Z_SEH
0x1002e74c  mov     eax, large fs:0
0x1002e752  push    eax
0x1002e753  sub     esp, 2Ch
0x1002e756  push    ebx
0x1002e757  push    esi
0x1002e758  push    edi
0x1002e759  mov     eax, ___security_cookie
0x1002e75e  xor     eax, ebp
0x1002e760  push    eax
0x1002e761  lea     eax, [ebp+var_C]
0x1002e764  mov     large fs:0, eax
0x1002e76a  mov     edi, ecx
0x1002e76c  test    byte ptr [edi+10h], 80h
0x1002e770  mov     esi, [ebp+arg_C]
0x1002e773  jnz     loc_1002E832
0x1002e779  mov     eax, [ebp+lDistanceToMove]
0x1002e77c  mov     ebx, [ebp+nNumberOfBytesToWrite]
0x1002e77f  mov     dword ptr [ebp+Overlapped.8], eax
0x1002e782  lea     eax, [ebp+Overlapped]
0x1002e785  push    eax; lpOverlapped
0x1002e786  lea     eax, [ebp+NumberOfBytesWritten]
0x1002e789  mov     dword ptr [ebp+Overlapped.8+4], 0
0x1002e790  push    eax; lpNumberOfBytesWritten
0x1002e791  push    ebx; nNumberOfBytesToWrite
0x1002e792  push    [ebp+lpBuffer]; lpBuffer
0x1002e795  mov     [ebp+Overlapped.hEvent], 0
0x1002e79c  push    dword ptr [edi]; hFile
0x1002e79e  call    ds:__imp__WriteFile@20; WriteFile(x,x,x,x,x)
0x1002e7a4  test    eax, eax
0x1002e7a6  jnz     short loc_1002E81A
0x1002e7a8  mov     [ebp+var_24], 1
0x1002e7af  mov     [ebp+var_4], eax
0x1002e7b2  lea     eax, [ebp+var_24]
0x1002e7b5  push    eax
0x1002e7b6  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x1002e7bb  mov     ebx, [ebp+var_24]
0x1002e7be  test    bl, 1
0x1002e7c1  jnz     short loc_1002E7D5
0x1002e7c3  cmp     [ebp+var_20], 0FFFFFC15h
0x1002e7ca  jnz     short loc_1002E7D5
0x1002e7cc  or      dword ptr [edi+10h], 80h
0x1002e7d3  jmp     short loc_1002E7E9
0x1002e7d5  test    bl, 8
0x1002e7d8  jz      short loc_1002E7E9
0x1002e7da  cmp     ebx, [esi]
0x1002e7dc  jle     short loc_1002E7E9
0x1002e7de  lea     eax, [ebp+var_24]
0x1002e7e1  mov     ecx, esi
0x1002e7e3  push    eax
0x1002e7e4  call    ??4Err@@QAEAAV0@ABV0@@Z; Err::operator=(Err const &)
0x1002e7e9  mov     [ebp+var_4], 0FFFFFFFFh
0x1002e7f0  test    ebx, 0FFFFFFFEh
0x1002e7f6  jz      short loc_1002E82C
0x1002e7f8  mov     eax, [ebp+Block]
0x1002e7fb  test    eax, eax
0x1002e7fd  jz      short loc_1002E808
0x1002e7ff  push    eax; Block
0x1002e800  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002e805  add     esp, 4
0x1002e808  mov     eax, [ebp+var_14]
0x1002e80b  test    eax, eax
0x1002e80d  jz      short loc_1002E82C
0x1002e80f  push    eax; Block
0x1002e810  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002e815  add     esp, 4
0x1002e818  jmp     short loc_1002E82C
0x1002e81a  cmp     [ebp+NumberOfBytesWritten], ebx
0x1002e81d  jz      short loc_1002E82C
0x1002e81f  push    ecx
0x1002e820  push    0FFFFF8F0h
0x1002e825  mov     ecx, esi
0x1002e827  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1002e82c  test    byte ptr [edi+10h], 80h
0x1002e830  jz      short loc_1002E894
0x1002e832  lea     ebx, [edi+14h]
0x1002e835  push    ebx; lpCriticalSection
0x1002e836  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1002e83c  push    0; dwMoveMethod
0x1002e83e  push    0; lpDistanceToMoveHigh
0x1002e840  push    [ebp+lDistanceToMove]; lDistanceToMove
0x1002e843  push    dword ptr [edi]; hFile
0x1002e845  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x1002e84b  cmp     eax, 0FFFFFFFFh
0x1002e84e  jnz     short loc_1002E858
0x1002e850  push    esi
0x1002e851  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x1002e856  jmp     short loc_1002E88D
0x1002e858  push    0; lpOverlapped
0x1002e85a  lea     eax, [ebp+NumberOfBytesWritten]
0x1002e85d  push    eax; lpNumberOfBytesWritten
0x1002e85e  push    [ebp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x1002e861  push    [ebp+lpBuffer]; lpBuffer
0x1002e864  push    dword ptr [edi]; hFile
0x1002e866  call    ds:__imp__WriteFile@20; WriteFile(x,x,x,x,x)
0x1002e86c  test    eax, eax
0x1002e86e  jnz     short loc_1002E878
0x1002e870  push    esi
0x1002e871  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x1002e876  jmp     short loc_1002E88D
0x1002e878  mov     eax, [ebp+nNumberOfBytesToWrite]
0x1002e87b  cmp     [ebp+NumberOfBytesWritten], eax
0x1002e87e  jz      short loc_1002E88D
0x1002e880  push    ecx
0x1002e881  push    0FFFFF8F0h
0x1002e886  mov     ecx, esi
0x1002e888  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1002e88d  push    ebx; lpCriticalSection
0x1002e88e  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1002e894  test    byte ptr [esi], 8
0x1002e897  jz      short loc_1002E8A3
0x1002e899  push    0; unsigned __int16 *
0x1002e89b  push    esi; struct Err *
0x1002e89c  mov     ecx, edi; this
0x1002e89e  call    ?SetExtErrInfo@File@@AAEXAAVErr@@PBG@Z; File::SetExtErrInfo(Err &,ushort const *)
0x1002e8a3  mov     ecx, [ebp+var_C]
0x1002e8a6  mov     large fs:0, ecx
0x1002e8ad  pop     ecx
0x1002e8ae  pop     edi
0x1002e8af  pop     esi
0x1002e8b0  pop     ebx
0x1002e8b1  mov     esp, ebp
0x1002e8b3  pop     ebp
0x1002e8b4  retn    10h
0x100607ed  nop
0x100607ee  nop
0x100607ef  mov     edx, [esp-4+lpBuffer]
0x100607f3  lea     eax, [edx+0Ch]
0x100607f6  mov     ecx, [edx-3Ch]
0x100607f9  xor     ecx, eax; StackCookie
0x100607fb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10060800  mov     eax, offset stru_100635EC
0x10060805  jmp     ___CxxFrameHandler3
```
