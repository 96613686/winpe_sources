# File::Write(ulong,void *,ulong,Err &)

- ea: `0x10051197`
- end: `0x100512c4`
- name: `?Write@File@@QAEXKPAXKAAVErr@@@Z`
- size: `301`
- prototype: `void __thiscall(File *__hidden this, LONG lDistanceToMove, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, struct Err *)`
- caller_count: `6`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x10054f31`
- `0x100568f1`
- `0x10056dd8`
- `0x1006b9f1`
- `0x1007677e`
- `0x100770ea`

## callees

- `0x10051197`
- `0x100515bd`
- `0x100610f0`
- `0x10074b2c`
- `0x10074b5f`
- `0x10074bb1`
- `0x10122f60`
- `0x10123e98`
- `0x10123f5f`
- `0x10123f8e`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100512a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100512a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10051257`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10051257`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x10051266`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x10051266`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x100511d7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1005127f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x100511d7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1005127f`

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
0x10051197  push    2Ch
0x10051199  mov     eax, offset loc_1012511D
0x1005119e  call    __EH_prolog3
0x100511a3  mov     edi, ecx
0x100511a5  test    byte ptr [edi+14h], 80h
0x100511a9  mov     esi, [ebp+arg_C]
0x100511ac  jnz     loc_10051253
0x100511b2  mov     eax, [ebp+lDistanceToMove]
0x100511b5  mov     ebx, [ebp+nNumberOfBytesToWrite]
0x100511b8  mov     dword ptr [ebp+Overlapped.8], eax
0x100511bb  lea     eax, [ebp+Overlapped]
0x100511be  push    eax; lpOverlapped
0x100511bf  lea     eax, [ebp+NumberOfBytesWritten]
0x100511c2  mov     dword ptr [ebp+Overlapped.8+4], 0
0x100511c9  push    eax; lpNumberOfBytesWritten
0x100511ca  push    ebx; nNumberOfBytesToWrite
0x100511cb  push    [ebp+lpBuffer]; lpBuffer
0x100511ce  mov     [ebp+Overlapped.hEvent], 0
0x100511d5  push    dword ptr [edi]; hFile
0x100511d7  call    ds:__imp__WriteFile@20; WriteFile(x,x,x,x,x)
0x100511dd  test    eax, eax
0x100511df  jnz     short loc_1005123B
0x100511e1  mov     [ebp+var_24], 1
0x100511e8  mov     [ebp+var_4], eax
0x100511eb  lea     eax, [ebp+var_24]
0x100511ee  push    eax
0x100511ef  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x100511f4  mov     ebx, [ebp+var_24]
0x100511f7  test    bl, 1
0x100511fa  jnz     short loc_1005120E
0x100511fc  cmp     [ebp+var_20], 0FFFFFC15h
0x10051203  jnz     short loc_1005120E
0x10051205  or      dword ptr [edi+14h], 80h
0x1005120c  jmp     short loc_10051222
0x1005120e  test    bl, 8
0x10051211  jz      short loc_10051222
0x10051213  cmp     ebx, [esi]
0x10051215  jle     short loc_10051222
0x10051217  lea     eax, [ebp+var_24]
0x1005121a  mov     ecx, esi
0x1005121c  push    eax
0x1005121d  call    ??4Err@@QAEAAV0@ABV0@@Z; Err::operator=(Err const &)
0x10051222  mov     [ebp+var_4], 0FFFFFFFFh
0x10051229  test    ebx, 0FFFFFFFEh
0x1005122f  jz      short loc_1005124D
0x10051231  lea     ecx, [ebp+var_24]; this
0x10051234  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x10051239  jmp     short loc_1005124D
0x1005123b  cmp     [ebp+NumberOfBytesWritten], ebx
0x1005123e  jz      short loc_1005124D
0x10051240  push    ecx
0x10051241  push    0FFFFF8F0h
0x10051246  mov     ecx, esi
0x10051248  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1005124d  test    byte ptr [edi+14h], 80h
0x10051251  jz      short loc_100512AD
0x10051253  lea     ebx, [edi+18h]
0x10051256  push    ebx; lpCriticalSection
0x10051257  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1005125d  push    0; dwMoveMethod
0x1005125f  push    0; lpDistanceToMoveHigh
0x10051261  push    [ebp+lDistanceToMove]; lDistanceToMove
0x10051264  push    dword ptr [edi]; hFile
0x10051266  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x1005126c  cmp     eax, 0FFFFFFFFh
0x1005126f  jz      short loc_10051289
0x10051271  push    0; lpOverlapped
0x10051273  lea     eax, [ebp+NumberOfBytesWritten]
0x10051276  push    eax; lpNumberOfBytesWritten
0x10051277  push    [ebp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x1005127a  push    [ebp+lpBuffer]; lpBuffer
0x1005127d  push    dword ptr [edi]; hFile
0x1005127f  call    ds:__imp__WriteFile@20; WriteFile(x,x,x,x,x)
0x10051285  test    eax, eax
0x10051287  jnz     short loc_10051291
0x10051289  push    esi
0x1005128a  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x1005128f  jmp     short loc_100512A6
0x10051291  mov     eax, [ebp+nNumberOfBytesToWrite]
0x10051294  cmp     [ebp+NumberOfBytesWritten], eax
0x10051297  jz      short loc_100512A6
0x10051299  push    ecx
0x1005129a  push    0FFFFF8F0h
0x1005129f  mov     ecx, esi
0x100512a1  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x100512a6  push    ebx; lpCriticalSection
0x100512a7  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100512ad  test    byte ptr [esi], 8
0x100512b0  jz      short loc_100512BC
0x100512b2  push    0; unsigned __int16 *
0x100512b4  push    esi; struct Err *
0x100512b5  mov     ecx, edi; this
0x100512b7  call    ?SetExtErrInfo@File@@AAEXAAVErr@@PAG@Z; File::SetExtErrInfo(Err &,ushort *)
0x100512bc  call    __EH_epilog3
0x100512c1  retn    10h
0x1012511d  nop
0x1012511e  nop
0x1012511f  mov     edx, [esp-4+lpBuffer]
0x10125123  lea     eax, [edx+0Ch]
0x10125126  mov     ecx, [edx-3Ch]
0x10125129  xor     ecx, eax; StackCookie
0x1012512b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10125130  mov     eax, offset stru_10127C9C
0x10125135  jmp     ___CxxFrameHandler3
```
