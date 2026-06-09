# File::Read(ulong,void *,ulong,Err &)

- ea: `0x100511f4`
- end: `0x10051321`
- name: `?Read@File@@QAEXKPAXKAAVErr@@@Z`
- size: `301`
- prototype: `void __thiscall(File *__hidden this, LONG lDistanceToMove, void *lpBuffer, DWORD nNumberOfBytesToRead, struct Err *)`
- caller_count: `9`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x100495ea`
- `0x10053810`
- `0x10055f43`
- `0x10056151`
- `0x10056619`
- `0x10056e3a`
- `0x10075c97`
- `0x1007690e`
- `0x10076f7c`

## callees

- `0x100511f4`
- `0x1005174d`
- `0x10061284`
- `0x10074cbc`
- `0x10074cef`
- `0x10074d41`
- `0x10123110`
- `0x10124048`
- `0x1012410f`
- `0x1012413e`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10051304`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10051304`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100512b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100512b4`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x100512c3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x100512c3`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x10051234`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x100512dc`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x10051234`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x100512dc`

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
  _DWORD v10[5]; // [esp+24h] [ebp-24h] BYREF
  DWORD NumberOfBytesRead; // [esp+38h] [ebp-10h] BYREF
  int v12; // [esp+44h] [ebp-4h]

  if ( *((char *)this + 20) < 0 )
    goto LABEL_14;
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
    v12 = 0;
    System::ErrGetLastError(v6);
    v7 = v10[0];
    if ( (v10[0] & 1) != 0 || v10[1] != -1003 )
    {
      if ( (v10[0] & 8) != 0 && v10[0] > *(_DWORD *)a5 )
        Err::operator=(v10);
    }
    else
    {
      *((_DWORD *)this + 5) |= 0x80u;
    }
    v12 = -1;
    if ( (v7 & 0xFFFFFFFE) != 0 )
      Err::Delete((Err *)v10);
  }
  if ( *((char *)this + 20) < 0 )
  {
LABEL_14:
    EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
    if ( SetFilePointer(*(HANDLE *)this, lDistanceToMove, 0, 0) != -1
      && ReadFile(*(HANDLE *)this, lpBuffer, nNumberOfBytesToRead, &NumberOfBytesRead, 0) )
    {
      if ( NumberOfBytesRead != nNumberOfBytesToRead )
        Err::SetError(a5, -1018, v8);
    }
    else
    {
      System::ErrGetLastError(v8);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  }
  if ( (*(_BYTE *)a5 & 8) != 0 )
    File::SetExtErrInfo(this, a5, 0);
}

```

## disassembly

```asm
0x100511f4  push    2Ch
0x100511f6  mov     eax, offset loc_101252CD
0x100511fb  call    __EH_prolog3
0x10051200  mov     edi, ecx
0x10051202  test    byte ptr [edi+14h], 80h
0x10051206  mov     esi, [ebp+arg_C]
0x10051209  jnz     loc_100512B0
0x1005120f  mov     eax, [ebp+lDistanceToMove]
0x10051212  mov     ebx, [ebp+nNumberOfBytesToRead]
0x10051215  mov     dword ptr [ebp+Overlapped.8], eax
0x10051218  lea     eax, [ebp+Overlapped]
0x1005121b  push    eax; lpOverlapped
0x1005121c  lea     eax, [ebp+NumberOfBytesRead]
0x1005121f  mov     dword ptr [ebp+Overlapped.8+4], 0
0x10051226  push    eax; lpNumberOfBytesRead
0x10051227  push    ebx; nNumberOfBytesToRead
0x10051228  push    [ebp+lpBuffer]; lpBuffer
0x1005122b  mov     [ebp+Overlapped.hEvent], 0
0x10051232  push    dword ptr [edi]; hFile
0x10051234  call    ds:__imp__ReadFile@20; ReadFile(x,x,x,x,x)
0x1005123a  test    eax, eax
0x1005123c  jnz     short loc_10051298
0x1005123e  mov     [ebp+var_24], 1
0x10051245  mov     [ebp+var_4], eax
0x10051248  lea     eax, [ebp+var_24]
0x1005124b  push    eax
0x1005124c  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x10051251  mov     ebx, [ebp+var_24]
0x10051254  test    bl, 1
0x10051257  jnz     short loc_1005126B
0x10051259  cmp     [ebp+var_20], 0FFFFFC15h
0x10051260  jnz     short loc_1005126B
0x10051262  or      dword ptr [edi+14h], 80h
0x10051269  jmp     short loc_1005127F
0x1005126b  test    bl, 8
0x1005126e  jz      short loc_1005127F
0x10051270  cmp     ebx, [esi]
0x10051272  jle     short loc_1005127F
0x10051274  lea     eax, [ebp+var_24]
0x10051277  mov     ecx, esi
0x10051279  push    eax
0x1005127a  call    ??4Err@@QAEAAV0@ABV0@@Z; Err::operator=(Err const &)
0x1005127f  mov     [ebp+var_4], 0FFFFFFFFh
0x10051286  test    ebx, 0FFFFFFFEh
0x1005128c  jz      short loc_100512AA
0x1005128e  lea     ecx, [ebp+var_24]; this
0x10051291  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x10051296  jmp     short loc_100512AA
0x10051298  cmp     [ebp+NumberOfBytesRead], ebx
0x1005129b  jz      short loc_100512AA
0x1005129d  push    ecx
0x1005129e  push    0FFFFFC06h
0x100512a3  mov     ecx, esi
0x100512a5  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x100512aa  test    byte ptr [edi+14h], 80h
0x100512ae  jz      short loc_1005130A
0x100512b0  lea     ebx, [edi+18h]
0x100512b3  push    ebx; lpCriticalSection
0x100512b4  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100512ba  push    0; dwMoveMethod
0x100512bc  push    0; lpDistanceToMoveHigh
0x100512be  push    [ebp+lDistanceToMove]; lDistanceToMove
0x100512c1  push    dword ptr [edi]; hFile
0x100512c3  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x100512c9  cmp     eax, 0FFFFFFFFh
0x100512cc  jz      short loc_100512E6
0x100512ce  push    0; lpOverlapped
0x100512d0  lea     eax, [ebp+NumberOfBytesRead]
0x100512d3  push    eax; lpNumberOfBytesRead
0x100512d4  push    [ebp+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x100512d7  push    [ebp+lpBuffer]; lpBuffer
0x100512da  push    dword ptr [edi]; hFile
0x100512dc  call    ds:__imp__ReadFile@20; ReadFile(x,x,x,x,x)
0x100512e2  test    eax, eax
0x100512e4  jnz     short loc_100512EE
0x100512e6  push    esi
0x100512e7  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x100512ec  jmp     short loc_10051303
0x100512ee  mov     eax, [ebp+nNumberOfBytesToRead]
0x100512f1  cmp     [ebp+NumberOfBytesRead], eax
0x100512f4  jz      short loc_10051303
0x100512f6  push    ecx
0x100512f7  push    0FFFFFC06h
0x100512fc  mov     ecx, esi
0x100512fe  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10051303  push    ebx; lpCriticalSection
0x10051304  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1005130a  test    byte ptr [esi], 8
0x1005130d  jz      short loc_10051319
0x1005130f  push    0; unsigned __int16 *
0x10051311  push    esi; struct Err *
0x10051312  mov     ecx, edi; this
0x10051314  call    ?SetExtErrInfo@File@@AAEXAAVErr@@PAG@Z; File::SetExtErrInfo(Err &,ushort *)
0x10051319  call    __EH_epilog3
0x1005131e  retn    10h
0x101252cd  nop
0x101252ce  nop
0x101252cf  mov     edx, [esp-4+lpBuffer]
0x101252d3  lea     eax, [edx+0Ch]
0x101252d6  mov     ecx, [edx-3Ch]
0x101252d9  xor     ecx, eax; StackCookie
0x101252db  call    @__security_check_cookie@4; __security_check_cookie(x)
0x101252e0  mov     eax, offset stru_10127E4C
0x101252e5  jmp     ___CxxFrameHandler3
```
