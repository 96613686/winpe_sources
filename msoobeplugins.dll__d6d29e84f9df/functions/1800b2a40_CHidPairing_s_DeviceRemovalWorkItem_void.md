# CHidPairing::s_DeviceRemovalWorkItem(void *)

- ea: `0x1800b2a40`
- end: `0x1800b2b4f`
- name: `?s_DeviceRemovalWorkItem@CHidPairing@@CAKPEAX@Z`
- size: `271`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000ac48`
- `0x1800b175c`
- `0x1800b2a40`
- `0x1800b8834`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800b2a82`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800b2a82`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b2abc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b2abc`
- `USER32!KillTimer` at `0x1800b2b04`
- `USER32!KillTimer` at `0x1800b2b04`
- `deviceassociation!DafStartRemoveAssociation` at `0x1800b2aa6`
- `deviceassociation!DafStartRemoveAssociation` at `0x1800b2aa6`
- `deviceassociation!DafCloseAssociationContext` at `0x1800b2b0f`
- `deviceassociation!DafCloseAssociationContext` at `0x1800b2b0f`
- `deviceassociation!DafCreateAssociationContext` at `0x1800b2a6b`
- `deviceassociation!DafCreateAssociationContext` at `0x1800b2a6b`

## pseudocode

```c
__int64 __fastcall CHidPairing::s_DeviceRemovalWorkItem(PVOID Parameter)
{
  __int64 Error; // rbx
  __int64 v4; // [rsp+40h] [rbp+8h] BYREF

  v4 = 0;
  LODWORD(Error) = DafCreateAssociationContext(*((_QWORD *)Parameter + 14), 0, 0, 0, &v4);
  if ( (int)Error < 0 )
    goto LABEL_12;
  if ( ResetEvent(*((HANDLE *)Parameter + 43)) || (LODWORD(Error) = ResultFromKnownLastError(), (int)Error >= 0) )
  {
    LODWORD(Error) = DafStartRemoveAssociation(v4, CHidPairing::s_DafRemoveAssociationDataCallback, Parameter);
    if ( (int)Error >= 0 )
    {
      if ( !WaitForSingleObject(*((HANDLE *)Parameter + 43), 0xFFFFFFFF)
        || (Error = (unsigned int)ResultFromKnownLastError(),
            UnattendLogW(1, L"CHidPairing::s_DeviceRemovalWorkItem - WaitForSingleObject failed: hr=0x%08X", Error),
            (int)Error >= 0) )
      {
        if ( *((int *)Parameter + 101) >= 0 )
        {
          CHidPairing::_PostUnexpectedErrorMessage((CHidPairing *)Parameter, -2147418113);
          KillTimer(*((HWND *)Parameter + 9), 0x3E9u);
        }
      }
    }
  }
  if ( (int)DafCloseAssociationContext(v4) < 0 )
    UnattendLogW(2, L"CHidPairing::s_DeviceRemovalWorkItem - DafCloseAssociationContext failed");
  if ( (int)Error < 0 )
LABEL_12:
    UnattendLogW(
      1,
      L"CHidPairing::s_DeviceRemovalWorkItem - s_DeviceRemovalWorkItem failed: hr=0x%08X",
      (unsigned int)Error);
  return 0;
}

```

## disassembly

```asm
0x1800b2a40  mov     r11, rsp
0x1800b2a43  mov     [r11+10h], rbx
0x1800b2a47  push    rdi
0x1800b2a48  sub     rsp, 30h
0x1800b2a4c  mov     rdi, rcx
0x1800b2a4f  mov     qword ptr [r11+8], 0
0x1800b2a57  mov     rcx, [rcx+70h]
0x1800b2a5b  lea     rax, [r11+8]
0x1800b2a5f  xor     r9d, r9d
0x1800b2a62  mov     [r11-18h], rax
0x1800b2a66  xor     r8d, r8d
0x1800b2a69  xor     edx, edx
0x1800b2a6b  call    cs:__imp_DafCreateAssociationContext
0x1800b2a71  mov     ebx, eax
0x1800b2a73  test    eax, eax
0x1800b2a75  js      loc_1800B2B2E
0x1800b2a7b  mov     rcx, [rdi+158h]; hEvent
0x1800b2a82  call    cs:__imp_ResetEvent
0x1800b2a88  test    eax, eax
0x1800b2a8a  jnz     short loc_1800B2A97
0x1800b2a8c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800b2a91  mov     ebx, eax
0x1800b2a93  test    eax, eax
0x1800b2a95  js      short loc_1800B2B0A
0x1800b2a97  mov     rcx, [rsp+38h+arg_0]
0x1800b2a9c  lea     rdx, ?s_DafRemoveAssociationDataCallback@CHidPairing@@SAXPEAXJ@Z; CHidPairing::s_DafRemoveAssociationDataCallback(void *,long)
0x1800b2aa3  mov     r8, rdi
0x1800b2aa6  call    cs:__imp_DafStartRemoveAssociation
0x1800b2aac  mov     ebx, eax
0x1800b2aae  test    eax, eax
0x1800b2ab0  js      short loc_1800B2B0A
0x1800b2ab2  mov     rcx, [rdi+158h]; hHandle
0x1800b2ab9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b2abc  call    cs:__imp_WaitForSingleObject
0x1800b2ac2  test    eax, eax
0x1800b2ac4  jz      short loc_1800B2AE5
0x1800b2ac6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800b2acb  mov     r8d, eax
0x1800b2ace  lea     rdx, aChidpairingSDe_7; "CHidPairing::s_DeviceRemovalWorkItem - "...
0x1800b2ad5  mov     ecx, 1
0x1800b2ada  mov     ebx, eax
0x1800b2adc  call    UnattendLogW
0x1800b2ae1  test    ebx, ebx
0x1800b2ae3  js      short loc_1800B2B0A
0x1800b2ae5  cmp     dword ptr [rdi+194h], 0
0x1800b2aec  jl      short loc_1800B2B0A
0x1800b2aee  mov     edx, 8000FFFFh; int
0x1800b2af3  mov     rcx, rdi; this
0x1800b2af6  call    ?_PostUnexpectedErrorMessage@CHidPairing@@AEAAXJ@Z; CHidPairing::_PostUnexpectedErrorMessage(long)
0x1800b2afb  mov     rcx, [rdi+48h]; hWnd
0x1800b2aff  mov     edx, 3E9h; uIDEvent
0x1800b2b04  call    cs:__imp_KillTimer
0x1800b2b0a  mov     rcx, [rsp+38h+arg_0]
0x1800b2b0f  call    cs:__imp_DafCloseAssociationContext
0x1800b2b15  test    eax, eax
0x1800b2b17  jns     short loc_1800B2B2A
0x1800b2b19  lea     rdx, aChidpairingSDe_3; "CHidPairing::s_DeviceRemovalWorkItem - "...
0x1800b2b20  mov     ecx, 2
0x1800b2b25  call    UnattendLogW
0x1800b2b2a  test    ebx, ebx
0x1800b2b2c  jns     short loc_1800B2B42
0x1800b2b2e  mov     r8d, ebx
0x1800b2b31  lea     rdx, aChidpairingSDe_4; "CHidPairing::s_DeviceRemovalWorkItem - "...
0x1800b2b38  mov     ecx, 1
0x1800b2b3d  call    UnattendLogW
0x1800b2b42  mov     rbx, [rsp+38h+arg_8]
0x1800b2b47  xor     eax, eax
0x1800b2b49  add     rsp, 30h
0x1800b2b4d  pop     rdi
0x1800b2b4e  retn
```
