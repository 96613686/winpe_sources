# CMasterClock::Init(void)

- ea: `0x18000ae14`
- end: `0x18000aefa`
- name: `?Init@CMasterClock@@QEAAJXZ`
- size: `230`
- prototype: `__int64 __fastcall(CMasterClock *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x1800138f0`

## callees

- `0x18000ae14`
- `0x18000b274`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x18000ae9e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x18000ae9e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000aed3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000aed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae5a`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000ae84`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000ae84`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x18000ae47`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x18000ae47`

## pseudocode

```c
__int64 __fastcall CMasterClock::Init(CMasterClock *this)
{
  HANDLE FileMappingA; // rax
  DWORD LastError; // edi
  LPVOID v4; // rax
  HANDLE MutexA; // rax

  FileMappingA = CreateFileMappingA((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x14u, "DirectMusicMasterClock");
  *((_QWORD *)this + 12) = FileMappingA;
  if ( !FileMappingA )
    return 2147942414LL;
  LastError = GetLastError();
  v4 = MapViewOfFile(*((HANDLE *)this + 12), 2u, 0, 0, 0);
  *((_QWORD *)this + 14) = v4;
  if ( !v4 )
    return 2147942414LL;
  MutexA = CreateMutexA(0, LastError != 183, "DirectMusicMasterClockMutex");
  *((_QWORD *)this + 13) = MutexA;
  if ( !MutexA )
    return 2147942414LL;
  if ( LastError != 183 )
  {
    *(GUID *)*((_QWORD *)this + 14) = GUID_SysClock;
    *(_DWORD *)(*((_QWORD *)this + 14) + 16LL) = 0;
    ReleaseMutex(*((HANDLE *)this + 13));
  }
  CMasterClock::UpdateClockList(this);
  return 0;
}

```

## disassembly

```asm
0x18000ae14  mov     [rsp+arg_0], rbx
0x18000ae19  mov     [rsp+arg_8], rsi
0x18000ae1e  push    rdi
0x18000ae1f  sub     rsp, 30h
0x18000ae23  xor     r9d, r9d; dwMaximumSizeHigh
0x18000ae26  lea     rax, Name; "DirectMusicMasterClock"
0x18000ae2d  mov     rbx, rcx
0x18000ae30  mov     [rsp+38h+lpName], rax; lpName
0x18000ae35  xor     edx, edx; lpFileMappingAttributes
0x18000ae37  mov     [rsp+38h+dwMaximumSizeLow], 14h; dwMaximumSizeLow
0x18000ae3f  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18000ae43  lea     r8d, [r9+4]; flProtect
0x18000ae47  call    cs:__imp_CreateFileMappingA
0x18000ae4d  mov     [rbx+60h], rax
0x18000ae51  test    rax, rax
0x18000ae54  jz      loc_18000AEE5
0x18000ae5a  call    cs:__imp_GetLastError
0x18000ae60  mov     rcx, [rbx+60h]; hFileMappingObject
0x18000ae64  xor     esi, esi
0x18000ae66  cmp     eax, 0B7h
0x18000ae6b  mov     qword ptr [rsp+38h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18000ae74  mov     edi, eax
0x18000ae76  setnz   sil
0x18000ae7a  xor     r9d, r9d; dwFileOffsetLow
0x18000ae7d  xor     r8d, r8d; dwFileOffsetHigh
0x18000ae80  lea     edx, [r9+2]; dwDesiredAccess
0x18000ae84  call    cs:__imp_MapViewOfFile
0x18000ae8a  mov     [rbx+70h], rax
0x18000ae8e  test    rax, rax
0x18000ae91  jz      short loc_18000AEE5
0x18000ae93  lea     r8, aDirectmusicmas_0; "DirectMusicMasterClockMutex"
0x18000ae9a  mov     edx, esi; bInitialOwner
0x18000ae9c  xor     ecx, ecx; lpMutexAttributes
0x18000ae9e  call    cs:__imp_CreateMutexA
0x18000aea4  mov     [rbx+68h], rax
0x18000aea8  test    rax, rax
0x18000aeab  jz      short loc_18000AEE5
0x18000aead  cmp     edi, 0B7h
0x18000aeb3  jz      short loc_18000AED9
0x18000aeb5  mov     rax, [rbx+70h]
0x18000aeb9  movups  xmm0, xmmword ptr cs:GUID_SysClock.Data1
0x18000aec0  movdqu  xmmword ptr [rax], xmm0
0x18000aec4  mov     rax, [rbx+70h]
0x18000aec8  mov     dword ptr [rax+10h], 0
0x18000aecf  mov     rcx, [rbx+68h]; hMutex
0x18000aed3  call    cs:__imp_ReleaseMutex
0x18000aed9  mov     rcx, rbx; this
0x18000aedc  call    ?UpdateClockList@CMasterClock@@AEAAJXZ; CMasterClock::UpdateClockList(void)
0x18000aee1  xor     eax, eax
0x18000aee3  jmp     short loc_18000AEEA
0x18000aee5  mov     eax, 8007000Eh
0x18000aeea  mov     rbx, [rsp+38h+arg_0]
0x18000aeef  mov     rsi, [rsp+38h+arg_8]
0x18000aef4  add     rsp, 30h
0x18000aef8  pop     rdi
0x18000aef9  retn
```
