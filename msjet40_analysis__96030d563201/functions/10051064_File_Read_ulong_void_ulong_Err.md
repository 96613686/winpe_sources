# File::Read(ulong,void *,ulong,Err &)

- ea: `0x10051064`
- end: `0x10051191`
- name: `?Read@File@@QAEXKPAXKAAVErr@@@Z`
- size: `301`
- prototype: `void __thiscall(File *__hidden this, LONG lDistanceToMove, void *lpBuffer, DWORD nNumberOfBytesToRead, struct Err *)`
- caller_count: `9`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1004946a`
- `0x10053680`
- `0x10055db3`
- `0x10055fc1`
- `0x10056489`
- `0x10056caa`
- `0x10075b07`
- `0x1007677e`
- `0x10076dec`

## callees

- `0x10051064`
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

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10051174`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10051174`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10051124`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10051124`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x10051133`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x10051133`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x100510a4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1005114c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x100510a4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1005114c`

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
0x10051064  push    2Ch
0x10051066  mov     eax, offset loc_1012511D
0x1005106b  call    __EH_prolog3
0x10051070  mov     edi, ecx
0x10051072  test    byte ptr [edi+14h], 80h
0x10051076  mov     esi, [ebp+arg_C]
0x10051079  jnz     loc_10051120
0x1005107f  mov     eax, [ebp+lDistanceToMove]
0x10051082  mov     ebx, [ebp+nNumberOfBytesToRead]
0x10051085  mov     dword ptr [ebp+Overlapped.8], eax
0x10051088  lea     eax, [ebp+Overlapped]
0x1005108b  push    eax; lpOverlapped
0x1005108c  lea     eax, [ebp+NumberOfBytesRead]
0x1005108f  mov     dword ptr [ebp+Overlapped.8+4], 0
0x10051096  push    eax; lpNumberOfBytesRead
0x10051097  push    ebx; nNumberOfBytesToRead
0x10051098  push    [ebp+lpBuffer]; lpBuffer
0x1005109b  mov     [ebp+Overlapped.hEvent], 0
0x100510a2  push    dword ptr [edi]; hFile
0x100510a4  call    ds:__imp__ReadFile@20; ReadFile(x,x,x,x,x)
0x100510aa  test    eax, eax
0x100510ac  jnz     short loc_10051108
0x100510ae  mov     [ebp+var_24], 1
0x100510b5  mov     [ebp+var_4], eax
0x100510b8  lea     eax, [ebp+var_24]
0x100510bb  push    eax
0x100510bc  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x100510c1  mov     ebx, [ebp+var_24]
0x100510c4  test    bl, 1
0x100510c7  jnz     short loc_100510DB
0x100510c9  cmp     [ebp+var_20], 0FFFFFC15h
0x100510d0  jnz     short loc_100510DB
0x100510d2  or      dword ptr [edi+14h], 80h
0x100510d9  jmp     short loc_100510EF
0x100510db  test    bl, 8
0x100510de  jz      short loc_100510EF
0x100510e0  cmp     ebx, [esi]
0x100510e2  jle     short loc_100510EF
0x100510e4  lea     eax, [ebp+var_24]
0x100510e7  mov     ecx, esi
0x100510e9  push    eax
0x100510ea  call    ??4Err@@QAEAAV0@ABV0@@Z; Err::operator=(Err const &)
0x100510ef  mov     [ebp+var_4], 0FFFFFFFFh
0x100510f6  test    ebx, 0FFFFFFFEh
0x100510fc  jz      short loc_1005111A
0x100510fe  lea     ecx, [ebp+var_24]; this
0x10051101  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x10051106  jmp     short loc_1005111A
0x10051108  cmp     [ebp+NumberOfBytesRead], ebx
0x1005110b  jz      short loc_1005111A
0x1005110d  push    ecx
0x1005110e  push    0FFFFFC06h
0x10051113  mov     ecx, esi
0x10051115  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1005111a  test    byte ptr [edi+14h], 80h
0x1005111e  jz      short loc_1005117A
0x10051120  lea     ebx, [edi+18h]
0x10051123  push    ebx; lpCriticalSection
0x10051124  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1005112a  push    0; dwMoveMethod
0x1005112c  push    0; lpDistanceToMoveHigh
0x1005112e  push    [ebp+lDistanceToMove]; lDistanceToMove
0x10051131  push    dword ptr [edi]; hFile
0x10051133  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x10051139  cmp     eax, 0FFFFFFFFh
0x1005113c  jz      short loc_10051156
0x1005113e  push    0; lpOverlapped
0x10051140  lea     eax, [ebp+NumberOfBytesRead]
0x10051143  push    eax; lpNumberOfBytesRead
0x10051144  push    [ebp+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x10051147  push    [ebp+lpBuffer]; lpBuffer
0x1005114a  push    dword ptr [edi]; hFile
0x1005114c  call    ds:__imp__ReadFile@20; ReadFile(x,x,x,x,x)
0x10051152  test    eax, eax
0x10051154  jnz     short loc_1005115E
0x10051156  push    esi
0x10051157  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x1005115c  jmp     short loc_10051173
0x1005115e  mov     eax, [ebp+nNumberOfBytesToRead]
0x10051161  cmp     [ebp+NumberOfBytesRead], eax
0x10051164  jz      short loc_10051173
0x10051166  push    ecx
0x10051167  push    0FFFFFC06h
0x1005116c  mov     ecx, esi
0x1005116e  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10051173  push    ebx; lpCriticalSection
0x10051174  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1005117a  test    byte ptr [esi], 8
0x1005117d  jz      short loc_10051189
0x1005117f  push    0; unsigned __int16 *
0x10051181  push    esi; struct Err *
0x10051182  mov     ecx, edi; this
0x10051184  call    ?SetExtErrInfo@File@@AAEXAAVErr@@PAG@Z; File::SetExtErrInfo(Err &,ushort *)
0x10051189  call    __EH_epilog3
0x1005118e  retn    10h
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
