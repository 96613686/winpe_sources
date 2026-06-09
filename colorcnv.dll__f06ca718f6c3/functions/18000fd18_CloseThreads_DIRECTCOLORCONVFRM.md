# CloseThreads(DIRECTCOLORCONVFRM *)

- ea: `0x18000fd18`
- end: `0x18000fe7e`
- name: `?CloseThreads@@YAXPEAUDIRECTCOLORCONVFRM@@@Z`
- size: `358`
- prototype: `void __fastcall(struct DIRECTCOLORCONVFRM *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001005c`

## callees

- `0x18000fd18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000fd5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000fd75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000fd5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000fd75`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000fd9a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000fd9a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fe77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fe2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fe46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fe53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fe60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fe2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fe46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fe53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fe60`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000fdac`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000fdc9`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000fdef`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000fe0c`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000fdac`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000fdc9`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000fdef`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x18000fe0c`

## pseudocode

```c
void __fastcall CloseThreads(struct DIRECTCOLORCONVFRM *a1)
{
  unsigned int v1; // eax
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  __int64 i; // rdi

  v1 = *((_DWORD *)a1 + 3660);
  *((_DWORD *)a1 + 3678) = 0;
  *((_DWORD *)a1 + 3659) = 1;
  if ( v1 >= 2 )
  {
    _InterlockedAdd((volatile signed __int32 *)a1 + 3661, v1);
    ReleaseSemaphore(*((HANDLE *)a1 + 1836), *((_DWORD *)a1 + 3660), 0);
    ReleaseSemaphore(*((HANDLE *)a1 + 1837), *((_DWORD *)a1 + 3660), 0);
    WaitForMultipleObjectsEx(*((_DWORD *)a1 + 3660), (const HANDLE *)a1 + 1832, 1, 0xFFFFFFFF, 0);
    v3 = (void *)*((_QWORD *)a1 + 1904);
    if ( v3 )
      AvRevertMmThreadCharacteristics(v3);
    v4 = (void *)*((_QWORD *)a1 + 1905);
    *((_QWORD *)a1 + 1904) = 0;
    if ( v4 )
      AvRevertMmThreadCharacteristics(v4);
    *((_QWORD *)a1 + 1905) = 0;
    if ( *((_DWORD *)a1 + 3660) == 4 )
    {
      v5 = (void *)*((_QWORD *)a1 + 1906);
      if ( v5 )
        AvRevertMmThreadCharacteristics(v5);
      v6 = (void *)*((_QWORD *)a1 + 1907);
      *((_QWORD *)a1 + 1906) = 0;
      if ( v6 )
        AvRevertMmThreadCharacteristics(v6);
      *((_QWORD *)a1 + 1907) = 0;
    }
    for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 3660); i = (unsigned int)(i + 1) )
      CloseHandle(*((HANDLE *)a1 + i + 1832));
    CloseHandle(*((HANDLE *)a1 + 1836));
    CloseHandle(*((HANDLE *)a1 + 1837));
    CloseHandle(*((HANDLE *)a1 + 1838));
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)a1 + 384);
}

```

## disassembly

```asm
0x18000fd18  mov     [rsp+arg_0], rbx
0x18000fd1d  push    rdi
0x18000fd1e  sub     rsp, 30h
0x18000fd22  mov     eax, [rcx+3930h]
0x18000fd28  mov     rbx, rcx
0x18000fd2b  mov     dword ptr [rcx+3978h], 0
0x18000fd35  mov     dword ptr [rcx+392Ch], 1
0x18000fd3f  cmp     eax, 2
0x18000fd42  jb      loc_18000FE66
0x18000fd48  lock add [rcx+3934h], eax
0x18000fd4f  mov     edx, [rcx+3930h]; lReleaseCount
0x18000fd55  xor     r8d, r8d; lpPreviousCount
0x18000fd58  mov     rcx, [rcx+3960h]; hSemaphore
0x18000fd5f  call    cs:__imp_ReleaseSemaphore
0x18000fd65  mov     edx, [rbx+3930h]; lReleaseCount
0x18000fd6b  xor     r8d, r8d; lpPreviousCount
0x18000fd6e  mov     rcx, [rbx+3968h]; hSemaphore
0x18000fd75  call    cs:__imp_ReleaseSemaphore
0x18000fd7b  mov     ecx, [rbx+3930h]; nCount
0x18000fd81  lea     rdx, [rbx+3940h]; lpHandles
0x18000fd88  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000fd8c  mov     [rsp+38h+bAlertable], 0; bAlertable
0x18000fd94  mov     r8d, 1; bWaitAll
0x18000fd9a  call    cs:__imp_WaitForMultipleObjectsEx
0x18000fda0  mov     rcx, [rbx+3B80h]; AvrtHandle
0x18000fda7  test    rcx, rcx
0x18000fdaa  jz      short loc_18000FDB2
0x18000fdac  call    cs:__imp_AvRevertMmThreadCharacteristics
0x18000fdb2  mov     rcx, [rbx+3B88h]; AvrtHandle
0x18000fdb9  mov     qword ptr [rbx+3B80h], 0
0x18000fdc4  test    rcx, rcx
0x18000fdc7  jz      short loc_18000FDCF
0x18000fdc9  call    cs:__imp_AvRevertMmThreadCharacteristics
0x18000fdcf  mov     qword ptr [rbx+3B88h], 0
0x18000fdda  cmp     dword ptr [rbx+3930h], 4
0x18000fde1  jnz     short loc_18000FE1D
0x18000fde3  mov     rcx, [rbx+3B90h]; AvrtHandle
0x18000fdea  test    rcx, rcx
0x18000fded  jz      short loc_18000FDF5
0x18000fdef  call    cs:__imp_AvRevertMmThreadCharacteristics
0x18000fdf5  mov     rcx, [rbx+3B98h]; AvrtHandle
0x18000fdfc  mov     qword ptr [rbx+3B90h], 0
0x18000fe07  test    rcx, rcx
0x18000fe0a  jz      short loc_18000FE12
0x18000fe0c  call    cs:__imp_AvRevertMmThreadCharacteristics
0x18000fe12  mov     qword ptr [rbx+3B98h], 0
0x18000fe1d  xor     edi, edi
0x18000fe1f  cmp     [rbx+3930h], edi
0x18000fe25  jbe     short loc_18000FE3F
0x18000fe27  mov     rcx, [rbx+rdi*8+3940h]; hObject
0x18000fe2f  call    cs:__imp_CloseHandle
0x18000fe35  inc     edi
0x18000fe37  cmp     edi, [rbx+3930h]
0x18000fe3d  jb      short loc_18000FE27
0x18000fe3f  mov     rcx, [rbx+3960h]; hObject
0x18000fe46  call    cs:__imp_CloseHandle
0x18000fe4c  mov     rcx, [rbx+3968h]; hObject
0x18000fe53  call    cs:__imp_CloseHandle
0x18000fe59  mov     rcx, [rbx+3970h]; hObject
0x18000fe60  call    cs:__imp_CloseHandle
0x18000fe66  lea     rcx, [rbx+3C00h]
0x18000fe6d  mov     rbx, [rsp+38h+arg_0]
0x18000fe72  add     rsp, 30h
0x18000fe76  pop     rdi
0x18000fe77  jmp     cs:__imp_DeleteCriticalSection
```
