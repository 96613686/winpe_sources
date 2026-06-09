# CopyFileW(void *,void *,__int64)

- ea: `0x18003ec98`
- end: `0x18003edbb`
- name: `?CopyFileW@@YAJPEAX0_J@Z`
- size: `291`
- prototype: `__int64 __fastcall(HANDLE hFile, HANDLE, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003f624`
- `0x18003ffd4`

## callees

- `0x1800012b8`
- `0x18003ec98`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003ecc1`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003ecc1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003ed55`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003ed55`
- `wbemcomn!GetMemLogObject` at `0x18003ed60`
- `wbemcomn!GetMemLogObject` at `0x18003ed60`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ed6b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ed6b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003ed09`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003ed09`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003ed32`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003ed32`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CopyFileW(HANDLE hFile, HANDLE a2, __int64 a3)
{
  __int64 v3; // rdi
  int v6; // ebx
  void *v7; // rbp
  DWORD v8; // esi
  CMemoryLog *MemLogObject; // rax
  DWORD NumberOfBytesRead; // [rsp+70h] [rbp+18h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+78h] [rbp+20h] BYREF

  v3 = a3;
  v6 = 0;
  if ( a3 > 0 )
  {
    v7 = CWin32DefaultArena::WbemMemAlloc(0x3E800u);
    if ( !v7 )
    {
      v6 = -2147217402;
LABEL_16:
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v6);
      goto LABEL_17;
    }
    NumberOfBytesWritten = 0;
    NumberOfBytesRead = 0;
    while ( v3 > 0 )
    {
      v8 = 256000;
      if ( v3 < 256000 )
        v8 = v3;
      if ( !ReadFile(hFile, v7, v8, &NumberOfBytesRead, 0)
        || NumberOfBytesRead != v8
        || !NumberOfBytesRead
        || !WriteFile(a2, v7, v8, &NumberOfBytesWritten, 0)
        || NumberOfBytesWritten != NumberOfBytesRead )
      {
        v6 = -2147217407;
        break;
      }
      v3 -= v8;
    }
    CWin32DefaultArena::WbemMemFree(v7);
    if ( v6 < 0 )
      goto LABEL_16;
  }
LABEL_17:
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids, (unsigned int)v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003ec98  mov     [rsp+arg_0], rbx
0x18003ec9d  push    rbp
0x18003ec9e  push    rsi
0x18003ec9f  push    rdi
0x18003eca0  push    r14
0x18003eca2  push    r15
0x18003eca4  sub     rsp, 30h
0x18003eca8  mov     rdi, r8
0x18003ecab  mov     r14, rdx
0x18003ecae  mov     r15, rcx
0x18003ecb1  xor     ebx, ebx
0x18003ecb3  test    r8, r8
0x18003ecb6  jle     loc_18003ED71
0x18003ecbc  mov     ecx, 3E800h
0x18003ecc1  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003ecc7  mov     rbp, rax
0x18003ecca  test    rax, rax
0x18003eccd  jnz     short loc_18003ECD9
0x18003eccf  mov     ebx, 80041006h
0x18003ecd4  jmp     loc_18003ED60
0x18003ecd9  mov     [rsp+58h+NumberOfBytesWritten], ebx
0x18003ecdd  mov     [rsp+58h+NumberOfBytesRead], ebx
0x18003ece1  test    rdi, rdi
0x18003ece4  jle     short loc_18003ED52
0x18003ece6  cmp     rdi, 3E800h
0x18003eced  mov     esi, 3E800h
0x18003ecf2  jge     short loc_18003ECF6
0x18003ecf4  mov     esi, edi
0x18003ecf6  mov     [rsp+58h+lpOverlapped], rbx; lpOverlapped
0x18003ecfb  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003ed00  mov     r8d, esi; nNumberOfBytesToRead
0x18003ed03  mov     rdx, rbp; lpBuffer
0x18003ed06  mov     rcx, r15; hFile
0x18003ed09  call    cs:__imp_ReadFile
0x18003ed0f  test    eax, eax
0x18003ed11  jz      short loc_18003ED4D
0x18003ed13  mov     eax, [rsp+58h+NumberOfBytesRead]
0x18003ed17  cmp     eax, esi
0x18003ed19  jnz     short loc_18003ED4D
0x18003ed1b  test    eax, eax
0x18003ed1d  jz      short loc_18003ED4D
0x18003ed1f  mov     [rsp+58h+lpOverlapped], rbx; lpOverlapped
0x18003ed24  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003ed29  mov     r8d, esi; nNumberOfBytesToWrite
0x18003ed2c  mov     rdx, rbp; lpBuffer
0x18003ed2f  mov     rcx, r14; hFile
0x18003ed32  call    cs:__imp_WriteFile
0x18003ed38  test    eax, eax
0x18003ed3a  jz      short loc_18003ED4D
0x18003ed3c  mov     eax, [rsp+58h+NumberOfBytesRead]
0x18003ed40  cmp     [rsp+58h+NumberOfBytesWritten], eax
0x18003ed44  jnz     short loc_18003ED4D
0x18003ed46  mov     eax, esi
0x18003ed48  sub     rdi, rax
0x18003ed4b  jmp     short loc_18003ECE1
0x18003ed4d  mov     ebx, 80041001h
0x18003ed52  mov     rcx, rbp
0x18003ed55  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003ed5b  nop
0x18003ed5c  test    ebx, ebx
0x18003ed5e  jns     short loc_18003ED71
0x18003ed60  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003ed66  mov     edx, ebx
0x18003ed68  mov     rcx, rax
0x18003ed6b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003ed71  lea     rax, WPP_GLOBAL_Control
0x18003ed78  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ed7f  cmp     rcx, rax
0x18003ed82  jz      short loc_18003EDA8
0x18003ed84  test    byte ptr [rcx+1Ch], 1
0x18003ed88  jz      short loc_18003EDA8
0x18003ed8a  cmp     byte ptr [rcx+19h], 2
0x18003ed8e  jb      short loc_18003EDA8
0x18003ed90  mov     edx, 0Ah
0x18003ed95  mov     r9d, ebx
0x18003ed98  lea     r8, WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids
0x18003ed9f  mov     rcx, [rcx+10h]
0x18003eda3  call    WPP_SF_d
0x18003eda8  mov     eax, ebx
0x18003edaa  mov     rbx, [rsp+58h+arg_0]
0x18003edaf  add     rsp, 30h
0x18003edb3  pop     r15
0x18003edb5  pop     r14
0x18003edb7  pop     rdi
0x18003edb8  pop     rsi
0x18003edb9  pop     rbp
0x18003edba  retn
```
