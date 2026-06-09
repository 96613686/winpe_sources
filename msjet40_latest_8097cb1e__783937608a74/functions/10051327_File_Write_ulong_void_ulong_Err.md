# File::Write(ulong,void *,ulong,Err &)

- ea: `0x10051327`
- end: `0x10051454`
- name: `?Write@File@@QAEXKPAXKAAVErr@@@Z`
- size: `301`
- prototype: `void __thiscall(File *__hidden this, LONG lDistanceToMove, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, struct Err *)`
- caller_count: `6`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x100550c1`
- `0x10056a81`
- `0x10056f68`
- `0x1006bb81`
- `0x1007690e`
- `0x1007727a`

## callees

- `0x10051327`
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

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10051437`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10051437`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100513e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100513e7`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x100513f6`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x100513f6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x10051367`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1005140f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x10051367`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1005140f`

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
  _DWORD v10[5]; // [esp+24h] [ebp-24h] BYREF
  DWORD NumberOfBytesWritten; // [esp+38h] [ebp-10h] BYREF
  int v12; // [esp+44h] [ebp-4h]

  if ( *((char *)this + 20) < 0 )
    goto LABEL_14;
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
      && WriteFile(*(HANDLE *)this, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
    {
      if ( NumberOfBytesWritten != nNumberOfBytesToWrite )
        Err::SetError(a5, -1808, v8);
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
0x10051327  push    2Ch
0x10051329  mov     eax, offset loc_101252CD
0x1005132e  call    __EH_prolog3
0x10051333  mov     edi, ecx
0x10051335  test    byte ptr [edi+14h], 80h
0x10051339  mov     esi, [ebp+arg_C]
0x1005133c  jnz     loc_100513E3
0x10051342  mov     eax, [ebp+lDistanceToMove]
0x10051345  mov     ebx, [ebp+nNumberOfBytesToWrite]
0x10051348  mov     dword ptr [ebp+Overlapped.8], eax
0x1005134b  lea     eax, [ebp+Overlapped]
0x1005134e  push    eax; lpOverlapped
0x1005134f  lea     eax, [ebp+NumberOfBytesWritten]
0x10051352  mov     dword ptr [ebp+Overlapped.8+4], 0
0x10051359  push    eax; lpNumberOfBytesWritten
0x1005135a  push    ebx; nNumberOfBytesToWrite
0x1005135b  push    [ebp+lpBuffer]; lpBuffer
0x1005135e  mov     [ebp+Overlapped.hEvent], 0
0x10051365  push    dword ptr [edi]; hFile
0x10051367  call    ds:__imp__WriteFile@20; WriteFile(x,x,x,x,x)
0x1005136d  test    eax, eax
0x1005136f  jnz     short loc_100513CB
0x10051371  mov     [ebp+var_24], 1
0x10051378  mov     [ebp+var_4], eax
0x1005137b  lea     eax, [ebp+var_24]
0x1005137e  push    eax
0x1005137f  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x10051384  mov     ebx, [ebp+var_24]
0x10051387  test    bl, 1
0x1005138a  jnz     short loc_1005139E
0x1005138c  cmp     [ebp+var_20], 0FFFFFC15h
0x10051393  jnz     short loc_1005139E
0x10051395  or      dword ptr [edi+14h], 80h
0x1005139c  jmp     short loc_100513B2
0x1005139e  test    bl, 8
0x100513a1  jz      short loc_100513B2
0x100513a3  cmp     ebx, [esi]
0x100513a5  jle     short loc_100513B2
0x100513a7  lea     eax, [ebp+var_24]
0x100513aa  mov     ecx, esi
0x100513ac  push    eax
0x100513ad  call    ??4Err@@QAEAAV0@ABV0@@Z; Err::operator=(Err const &)
0x100513b2  mov     [ebp+var_4], 0FFFFFFFFh
0x100513b9  test    ebx, 0FFFFFFFEh
0x100513bf  jz      short loc_100513DD
0x100513c1  lea     ecx, [ebp+var_24]; this
0x100513c4  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x100513c9  jmp     short loc_100513DD
0x100513cb  cmp     [ebp+NumberOfBytesWritten], ebx
0x100513ce  jz      short loc_100513DD
0x100513d0  push    ecx
0x100513d1  push    0FFFFF8F0h
0x100513d6  mov     ecx, esi
0x100513d8  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x100513dd  test    byte ptr [edi+14h], 80h
0x100513e1  jz      short loc_1005143D
0x100513e3  lea     ebx, [edi+18h]
0x100513e6  push    ebx; lpCriticalSection
0x100513e7  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100513ed  push    0; dwMoveMethod
0x100513ef  push    0; lpDistanceToMoveHigh
0x100513f1  push    [ebp+lDistanceToMove]; lDistanceToMove
0x100513f4  push    dword ptr [edi]; hFile
0x100513f6  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x100513fc  cmp     eax, 0FFFFFFFFh
0x100513ff  jz      short loc_10051419
0x10051401  push    0; lpOverlapped
0x10051403  lea     eax, [ebp+NumberOfBytesWritten]
0x10051406  push    eax; lpNumberOfBytesWritten
0x10051407  push    [ebp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x1005140a  push    [ebp+lpBuffer]; lpBuffer
0x1005140d  push    dword ptr [edi]; hFile
0x1005140f  call    ds:__imp__WriteFile@20; WriteFile(x,x,x,x,x)
0x10051415  test    eax, eax
0x10051417  jnz     short loc_10051421
0x10051419  push    esi
0x1005141a  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x1005141f  jmp     short loc_10051436
0x10051421  mov     eax, [ebp+nNumberOfBytesToWrite]
0x10051424  cmp     [ebp+NumberOfBytesWritten], eax
0x10051427  jz      short loc_10051436
0x10051429  push    ecx
0x1005142a  push    0FFFFF8F0h
0x1005142f  mov     ecx, esi
0x10051431  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10051436  push    ebx; lpCriticalSection
0x10051437  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1005143d  test    byte ptr [esi], 8
0x10051440  jz      short loc_1005144C
0x10051442  push    0; unsigned __int16 *
0x10051444  push    esi; struct Err *
0x10051445  mov     ecx, edi; this
0x10051447  call    ?SetExtErrInfo@File@@AAEXAAVErr@@PAG@Z; File::SetExtErrInfo(Err &,ushort *)
0x1005144c  call    __EH_epilog3
0x10051451  retn    10h
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
