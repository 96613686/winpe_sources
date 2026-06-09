# File::Read(ulong,void *,ulong,Err &)

- ea: `0x1002e5c0`
- end: `0x1002e737`
- name: `?Read@File@@QAEXKPAXKAAVErr@@@Z`
- size: `375`
- prototype: `void __thiscall(File *__hidden this, LONG lDistanceToMove, void *lpBuffer, DWORD nNumberOfBytesToRead, struct Err *)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x10020080`
- `0x100228f0`
- `0x10023420`
- `0x10041e80`
- `0x10042760`

## callees

- `0x10025e60`
- `0x10025ee0`
- `0x1002e5c0`
- `0x1002ed90`
- `0x1004eda0`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1002e6b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1002e6b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1002e70e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1002e70e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1002e61e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1002e6e6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1002e61e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1002e6e6`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1002e6c5`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1002e6c5`

## pseudocode

```c
void __thiscall File::Read(
        File *this,
        unsigned int lDistanceToMove,
        void *lpBuffer,
        DWORD nNumberOfBytesToRead,
        struct Err *a5)
{
  struct Err *v6; // ecx
  int v7; // ebx
  struct Err *v8; // ecx
  _OVERLAPPED Overlapped; // [esp+10h] [ebp-38h] BYREF
  _DWORD v10[3]; // [esp+24h] [ebp-24h] BYREF
  void *Block; // [esp+30h] [ebp-18h]
  void *v12; // [esp+34h] [ebp-14h]
  DWORD NumberOfBytesRead; // [esp+38h] [ebp-10h] BYREF
  int v14; // [esp+44h] [ebp-4h]

  if ( *((char *)this + 16) < 0 )
    goto LABEL_17;
  Overlapped.8 = (union _OVERLAPPED::$742A73540840F318F86F9CEE3D494648)lDistanceToMove;
  Overlapped.hEvent = 0;
  if ( ReadFile(*(HANDLE *)this, lpBuffer, nNumberOfBytesToRead, &NumberOfBytesRead, &Overlapped) )
  {
    if ( NumberOfBytesRead != nNumberOfBytesToRead )
      Err::SetError(a5, -1018, v6);
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
      || !ReadFile(*(HANDLE *)this, lpBuffer, nNumberOfBytesToRead, &NumberOfBytesRead, 0) )
    {
      System::ErrGetLastError(v8);
    }
    else if ( NumberOfBytesRead != nNumberOfBytesToRead )
    {
      Err::SetError(a5, -1018, v8);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 20));
  }
  if ( (*(_BYTE *)a5 & 8) != 0 )
    File::SetExtErrInfo(this, a5, 0);
}

```

## disassembly

```asm
0x1002e5c0  mov     edi, edi
0x1002e5c2  push    ebp
0x1002e5c3  mov     ebp, esp
0x1002e5c5  push    0FFFFFFFFh
0x1002e5c7  push    offset ?Write@File@@QAEXKPAXKAAVErr@@@Z_SEH
0x1002e5cc  mov     eax, large fs:0
0x1002e5d2  push    eax
0x1002e5d3  sub     esp, 2Ch
0x1002e5d6  push    ebx
0x1002e5d7  push    esi
0x1002e5d8  push    edi
0x1002e5d9  mov     eax, ___security_cookie
0x1002e5de  xor     eax, ebp
0x1002e5e0  push    eax
0x1002e5e1  lea     eax, [ebp+var_C]
0x1002e5e4  mov     large fs:0, eax
0x1002e5ea  mov     edi, ecx
0x1002e5ec  test    byte ptr [edi+10h], 80h
0x1002e5f0  mov     esi, [ebp+arg_C]
0x1002e5f3  jnz     loc_1002E6B2
0x1002e5f9  mov     eax, [ebp+lDistanceToMove]
0x1002e5fc  mov     ebx, [ebp+nNumberOfBytesToRead]
0x1002e5ff  mov     dword ptr [ebp+Overlapped.8], eax
0x1002e602  lea     eax, [ebp+Overlapped]
0x1002e605  push    eax; lpOverlapped
0x1002e606  lea     eax, [ebp+NumberOfBytesRead]
0x1002e609  mov     dword ptr [ebp+Overlapped.8+4], 0
0x1002e610  push    eax; lpNumberOfBytesRead
0x1002e611  push    ebx; nNumberOfBytesToRead
0x1002e612  push    [ebp+lpBuffer]; lpBuffer
0x1002e615  mov     [ebp+Overlapped.hEvent], 0
0x1002e61c  push    dword ptr [edi]; hFile
0x1002e61e  call    ds:__imp__ReadFile@20; ReadFile(x,x,x,x,x)
0x1002e624  test    eax, eax
0x1002e626  jnz     short loc_1002E69A
0x1002e628  mov     [ebp+var_24], 1
0x1002e62f  mov     [ebp+var_4], eax
0x1002e632  lea     eax, [ebp+var_24]
0x1002e635  push    eax
0x1002e636  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x1002e63b  mov     ebx, [ebp+var_24]
0x1002e63e  test    bl, 1
0x1002e641  jnz     short loc_1002E655
0x1002e643  cmp     [ebp+var_20], 0FFFFFC15h
0x1002e64a  jnz     short loc_1002E655
0x1002e64c  or      dword ptr [edi+10h], 80h
0x1002e653  jmp     short loc_1002E669
0x1002e655  test    bl, 8
0x1002e658  jz      short loc_1002E669
0x1002e65a  cmp     ebx, [esi]
0x1002e65c  jle     short loc_1002E669
0x1002e65e  lea     eax, [ebp+var_24]
0x1002e661  mov     ecx, esi
0x1002e663  push    eax
0x1002e664  call    ??4Err@@QAEAAV0@ABV0@@Z; Err::operator=(Err const &)
0x1002e669  mov     [ebp+var_4], 0FFFFFFFFh
0x1002e670  test    ebx, 0FFFFFFFEh
0x1002e676  jz      short loc_1002E6AC
0x1002e678  mov     eax, [ebp+Block]
0x1002e67b  test    eax, eax
0x1002e67d  jz      short loc_1002E688
0x1002e67f  push    eax; Block
0x1002e680  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002e685  add     esp, 4
0x1002e688  mov     eax, [ebp+var_14]
0x1002e68b  test    eax, eax
0x1002e68d  jz      short loc_1002E6AC
0x1002e68f  push    eax; Block
0x1002e690  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002e695  add     esp, 4
0x1002e698  jmp     short loc_1002E6AC
0x1002e69a  cmp     [ebp+NumberOfBytesRead], ebx
0x1002e69d  jz      short loc_1002E6AC
0x1002e69f  push    ecx
0x1002e6a0  push    0FFFFFC06h
0x1002e6a5  mov     ecx, esi
0x1002e6a7  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1002e6ac  test    byte ptr [edi+10h], 80h
0x1002e6b0  jz      short loc_1002E714
0x1002e6b2  lea     ebx, [edi+14h]
0x1002e6b5  push    ebx; lpCriticalSection
0x1002e6b6  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1002e6bc  push    0; dwMoveMethod
0x1002e6be  push    0; lpDistanceToMoveHigh
0x1002e6c0  push    [ebp+lDistanceToMove]; lDistanceToMove
0x1002e6c3  push    dword ptr [edi]; hFile
0x1002e6c5  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x1002e6cb  cmp     eax, 0FFFFFFFFh
0x1002e6ce  jnz     short loc_1002E6D8
0x1002e6d0  push    esi
0x1002e6d1  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x1002e6d6  jmp     short loc_1002E70D
0x1002e6d8  push    0; lpOverlapped
0x1002e6da  lea     eax, [ebp+NumberOfBytesRead]
0x1002e6dd  push    eax; lpNumberOfBytesRead
0x1002e6de  push    [ebp+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x1002e6e1  push    [ebp+lpBuffer]; lpBuffer
0x1002e6e4  push    dword ptr [edi]; hFile
0x1002e6e6  call    ds:__imp__ReadFile@20; ReadFile(x,x,x,x,x)
0x1002e6ec  test    eax, eax
0x1002e6ee  jnz     short loc_1002E6F8
0x1002e6f0  push    esi
0x1002e6f1  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x1002e6f6  jmp     short loc_1002E70D
0x1002e6f8  mov     eax, [ebp+nNumberOfBytesToRead]
0x1002e6fb  cmp     [ebp+NumberOfBytesRead], eax
0x1002e6fe  jz      short loc_1002E70D
0x1002e700  push    ecx
0x1002e701  push    0FFFFFC06h
0x1002e706  mov     ecx, esi
0x1002e708  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1002e70d  push    ebx; lpCriticalSection
0x1002e70e  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1002e714  test    byte ptr [esi], 8
0x1002e717  jz      short loc_1002E723
0x1002e719  push    0; unsigned __int16 *
0x1002e71b  push    esi; struct Err *
0x1002e71c  mov     ecx, edi; this
0x1002e71e  call    ?SetExtErrInfo@File@@AAEXAAVErr@@PBG@Z; File::SetExtErrInfo(Err &,ushort const *)
0x1002e723  mov     ecx, [ebp+var_C]
0x1002e726  mov     large fs:0, ecx
0x1002e72d  pop     ecx
0x1002e72e  pop     edi
0x1002e72f  pop     esi
0x1002e730  pop     ebx
0x1002e731  mov     esp, ebp
0x1002e733  pop     ebp
0x1002e734  retn    10h
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
