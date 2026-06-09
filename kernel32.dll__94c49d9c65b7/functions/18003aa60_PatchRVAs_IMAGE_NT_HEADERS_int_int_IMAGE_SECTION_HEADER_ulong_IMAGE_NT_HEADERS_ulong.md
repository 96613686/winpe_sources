# PatchRVAs<_IMAGE_NT_HEADERS>(int,int,_IMAGE_SECTION_HEADER *,ulong,_IMAGE_NT_HEADERS *,ulong)

- ea: `0x18003aa60`
- end: `0x18003accf`
- name: `??$PatchRVAs@U_IMAGE_NT_HEADERS@@@@YAJHHPEAU_IMAGE_SECTION_HEADER@@KPEAU_IMAGE_NT_HEADERS@@K@Z`
- size: `623`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x180048b68`

## callees

- `0x1800313d0`
- `0x1800373e8`
- `0x18003aa60`
- `0x180054f0c`
- `0x18007a840`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003ab31`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003ac4e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003ab31`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003ac4e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003ab0a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003ab54`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003abf6`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003ac07`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003ab0a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003ab54`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003abf6`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003ac07`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003ab7b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003ac2f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003ab7b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003ac2f`

## pseudocode

```c
__int64 __fastcall PatchRVAs<_IMAGE_NT_HEADERS>(HFILE a1, HFILE a2, __int64 a3, int a4, __int64 a5, int a6)
{
  __int64 result; // rax
  HFILE v7; // r13d
  int v8; // edi
  void *v9; // r12
  int v10; // edi
  unsigned int v11; // ebx
  unsigned int v12; // r14d
  int i; // r15d
  __int64 j; // rdx
  unsigned int v15; // r9d
  LONG v16; // ebx
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-59h] BYREF
  int v18; // [rsp+34h] [rbp-55h] BYREF
  int v19; // [rsp+38h] [rbp-51h]
  HFILE v20; // [rsp+3Ch] [rbp-4Dh]
  __int64 v21; // [rsp+40h] [rbp-49h]
  __int128 Buffer; // [rsp+48h] [rbp-41h] BYREF
  unsigned int v23; // [rsp+58h] [rbp-31h]
  unsigned __int8 v24[16]; // [rsp+60h] [rbp-29h] BYREF
  __int128 v25; // [rsp+70h] [rbp-19h]
  __int64 v26; // [rsp+80h] [rbp-9h]

  result = 0;
  v19 = a4;
  v21 = a3;
  v7 = a2;
  v20 = a2;
  v8 = *(_DWORD *)(a5 + 84);
  v9 = (void *)a1;
  v18 = 0;
  *(_OWORD *)v24 = 0;
  v26 = 0;
  v25 = 0;
  v23 = 0;
  Buffer = 0;
  v10 = v8 - a6;
  if ( v10 )
  {
    v11 = *(_DWORD *)(a5 + 120);
    if ( v11 && v11 < *(_DWORD *)(a5 + 84) )
    {
      llseek(a1, v11 - v10, 0);
      MuRead((int)v9, v24, 0x28u);
      *(_DWORD *)&v24[12] += v10;
      HIDWORD(v25) += v10;
      LODWORD(v26) = v10 + v26;
      HIDWORD(v26) += v10;
      llseek(v7, v11, 0);
      MuWrite(v7, v24, 0x28u);
    }
    v12 = *(_DWORD *)(a5 + 128);
    if ( v12 && v12 < *(_DWORD *)(a5 + 84) )
    {
      for ( i = 0; ; ++i )
      {
        SetFilePointer(v9, v12 + 20 * i - v10, 0, 0);
        NumberOfBytesRead = 0;
        ReadFile(v9, &Buffer, 0x14u, &NumberOfBytesRead, 0);
        if ( !v23 )
          break;
        HIDWORD(Buffer) += v10;
        SetFilePointer((HANDLE)v7, 20 * i + v12, 0, 0);
        NumberOfBytesRead = 0;
        WriteFile((HANDLE)v7, &Buffer, 0x14u, &NumberOfBytesRead, 0);
        for ( j = 0; ; j = (unsigned int)(j + 1) )
        {
          if ( (unsigned int)j >= *(unsigned __int16 *)(a5 + 6) )
            return 13;
          v15 = *(_DWORD *)(v21 + 40 * j + 12);
          if ( v23 >= v15 && v23 < v15 + *(_DWORD *)(v21 + 40 * j + 16) )
            break;
        }
        v16 = v23 + *(_DWORD *)(v21 + 40 * j + 20) - v15;
        SetFilePointer(v9, v16 - v19, 0, 0);
        SetFilePointer((HANDLE)v7, v16, 0, 0);
        while ( 1 )
        {
          NumberOfBytesRead = 0;
          ReadFile(v9, &v18, 4u, &NumberOfBytesRead, 0);
          if ( !v18 )
            break;
          NumberOfBytesRead = 0;
          v18 += v10;
          WriteFile((HANDLE)v7, &v18, 4u, &NumberOfBytesRead, 0);
        }
        v7 = v20;
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18003aa60  push    rbp
0x18003aa62  push    rbx
0x18003aa63  push    rsi
0x18003aa64  push    rdi
0x18003aa65  push    r12
0x18003aa67  push    r13
0x18003aa69  push    r14
0x18003aa6b  push    r15
0x18003aa6d  lea     rbp, [rsp-0Fh]
0x18003aa72  sub     rsp, 98h
0x18003aa79  mov     rax, cs:__security_cookie
0x18003aa80  xor     rax, rsp
0x18003aa83  mov     [rbp+47h+var_48], rax
0x18003aa87  mov     rsi, [rbp+47h+arg_20]
0x18003aa8b  xor     eax, eax
0x18003aa8d  xorps   xmm0, xmm0
0x18003aa90  mov     [rbp+47h+var_98], r9d
0x18003aa94  mov     [rbp+47h+var_90], r8
0x18003aa98  mov     r13d, edx
0x18003aa9b  mov     [rbp+47h+var_94], edx
0x18003aa9e  mov     edi, [rsi+54h]
0x18003aaa1  movsxd  r12, ecx
0x18003aaa4  mov     [rbp+47h+var_9C], 0
0x18003aaab  movups  xmmword ptr [rbp+47h+var_70], xmm0
0x18003aaaf  mov     [rbp+47h+var_50], rax
0x18003aab3  movups  [rbp+47h+var_60], xmm0
0x18003aab7  mov     [rbp+47h+var_78], eax
0x18003aaba  movups  [rbp+47h+Buffer], xmm0
0x18003aabe  sub     edi, [rbp+47h+arg_28]
0x18003aac1  jz      loc_18003AB9A
0x18003aac7  mov     ebx, [rsi+78h]
0x18003aaca  test    ebx, ebx
0x18003aacc  jnz     loc_18003AC6E
0x18003aad2  mov     r14d, [rsi+80h]
0x18003aad9  test    r14d, r14d
0x18003aadc  jz      loc_18003ACC8
0x18003aae2  cmp     r14d, [rsi+54h]
0x18003aae6  jnb     loc_18003ACC8
0x18003aaec  xor     r15d, r15d
0x18003aaef  lea     eax, [r15+r15*4]
0x18003aaf3  xor     r9d, r9d; dwMoveMethod
0x18003aaf6  lea     ebx, ds:0[rax*4]
0x18003aafd  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003ab00  mov     edx, ebx
0x18003ab02  mov     rcx, r12; hFile
0x18003ab05  sub     edx, edi
0x18003ab07  add     edx, r14d; lDistanceToMove
0x18003ab0a  call    cs:__imp_SetFilePointer
0x18003ab10  lea     r9, [rbp+47h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003ab14  mov     [rbp+47h+NumberOfBytesRead], 0
0x18003ab1b  mov     r8d, 14h; nNumberOfBytesToRead
0x18003ab21  mov     [rsp+0D0h+lpOverlapped], 0; lpOverlapped
0x18003ab2a  lea     rdx, [rbp+47h+Buffer]; lpBuffer
0x18003ab2e  mov     rcx, r12; hFile
0x18003ab31  call    cs:__imp_ReadFile
0x18003ab37  cmp     [rbp+47h+var_78], 0
0x18003ab3b  jz      loc_18003ACC8
0x18003ab41  add     dword ptr [rbp+47h+Buffer+0Ch], edi
0x18003ab44  lea     edx, [rbx+r14]; lDistanceToMove
0x18003ab48  movsxd  r13, r13d
0x18003ab4b  xor     r9d, r9d; dwMoveMethod
0x18003ab4e  mov     rcx, r13; hFile
0x18003ab51  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003ab54  call    cs:__imp_SetFilePointer
0x18003ab5a  lea     r9, [rbp+47h+NumberOfBytesRead]; lpNumberOfBytesWritten
0x18003ab5e  mov     [rbp+47h+NumberOfBytesRead], 0
0x18003ab65  mov     r8d, 14h; nNumberOfBytesToWrite
0x18003ab6b  mov     [rsp+0D0h+lpOverlapped], 0; lpOverlapped
0x18003ab74  lea     rdx, [rbp+47h+Buffer]; lpBuffer
0x18003ab78  mov     rcx, r13; hFile
0x18003ab7b  call    cs:__imp_WriteFile
0x18003ab81  mov     r10d, [rbp+47h+var_78]
0x18003ab85  xor     edx, edx
0x18003ab87  movzx   r11d, word ptr [rsi+6]
0x18003ab8c  mov     rbx, [rbp+47h+var_90]
0x18003ab90  cmp     edx, r11d
0x18003ab93  jb      short loc_18003ABBA
0x18003ab95  mov     eax, 0Dh
0x18003ab9a  mov     rcx, [rbp+47h+var_48]
0x18003ab9e  xor     rcx, rsp; StackCookie
0x18003aba1  call    __security_check_cookie
0x18003aba6  add     rsp, 98h
0x18003abad  pop     r15
0x18003abaf  pop     r14
0x18003abb1  pop     r13
0x18003abb3  pop     r12
0x18003abb5  pop     rdi
0x18003abb6  pop     rsi
0x18003abb7  pop     rbx
0x18003abb8  pop     rbp
0x18003abb9  retn
0x18003abba  lea     r8, [rdx+rdx*4]
0x18003abbe  mov     r9d, [rbx+r8*8+0Ch]
0x18003abc3  cmp     r10d, r9d
0x18003abc6  jb      loc_18003AC67
0x18003abcc  mov     ecx, [rbx+r8*8+10h]
0x18003abd1  add     ecx, r9d
0x18003abd4  cmp     r10d, ecx
0x18003abd7  jnb     loc_18003AC67
0x18003abdd  mov     ebx, [rbx+r8*8+14h]
0x18003abe2  sub     ebx, r9d
0x18003abe5  add     ebx, r10d
0x18003abe8  mov     edx, ebx
0x18003abea  xor     r9d, r9d; dwMoveMethod
0x18003abed  sub     edx, [rbp+47h+var_98]; lDistanceToMove
0x18003abf0  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003abf3  mov     rcx, r12; hFile
0x18003abf6  call    cs:__imp_SetFilePointer
0x18003abfc  xor     r9d, r9d; dwMoveMethod
0x18003abff  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003ac02  mov     edx, ebx; lDistanceToMove
0x18003ac04  mov     rcx, r13; hFile
0x18003ac07  call    cs:__imp_SetFilePointer
0x18003ac0d  xor     ebx, ebx
0x18003ac0f  jmp     short loc_18003AC35
0x18003ac11  add     eax, edi
0x18003ac13  mov     [rbp+47h+NumberOfBytesRead], ebx
0x18003ac16  lea     r9, [rbp+47h+NumberOfBytesRead]; lpNumberOfBytesWritten
0x18003ac1a  mov     [rbp+47h+var_9C], eax
0x18003ac1d  mov     r8d, 4; nNumberOfBytesToWrite
0x18003ac23  mov     [rsp+0D0h+lpOverlapped], rbx; lpOverlapped
0x18003ac28  lea     rdx, [rbp+47h+var_9C]; lpBuffer
0x18003ac2c  mov     rcx, r13; hFile
0x18003ac2f  call    cs:__imp_WriteFile
0x18003ac35  lea     r9, [rbp+47h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003ac39  mov     [rsp+0D0h+lpOverlapped], rbx; lpOverlapped
0x18003ac3e  mov     r8d, 4; nNumberOfBytesToRead
0x18003ac44  mov     [rbp+47h+NumberOfBytesRead], ebx
0x18003ac47  lea     rdx, [rbp+47h+var_9C]; lpBuffer
0x18003ac4b  mov     rcx, r12; hFile
0x18003ac4e  call    cs:__imp_ReadFile
0x18003ac54  mov     eax, [rbp+47h+var_9C]
0x18003ac57  test    eax, eax
0x18003ac59  jnz     short loc_18003AC11
0x18003ac5b  mov     r13d, [rbp+47h+var_94]
0x18003ac5f  inc     r15d
0x18003ac62  jmp     loc_18003AAEF
0x18003ac67  inc     edx
0x18003ac69  jmp     loc_18003AB90
0x18003ac6e  cmp     ebx, [rsi+54h]
0x18003ac71  jnb     loc_18003AAD2
0x18003ac77  mov     edx, ebx
0x18003ac79  xor     r8d, r8d; iOrigin
0x18003ac7c  sub     edx, edi; lOffset
0x18003ac7e  mov     ecx, r12d; hFile
0x18003ac81  call    _llseek
0x18003ac86  mov     r14d, 28h ; '('
0x18003ac8c  lea     rdx, [rbp+47h+var_70]; unsigned __int8 *
0x18003ac90  mov     r8d, r14d; unsigned int
0x18003ac93  mov     ecx, r12d; int
0x18003ac96  call    ?MuRead@@YAKHPEAEK@Z; MuRead(int,uchar *,ulong)
0x18003ac9b  add     dword ptr [rbp+47h+var_70+0Ch], edi
0x18003ac9e  xor     r8d, r8d; iOrigin
0x18003aca1  add     dword ptr [rbp+47h+var_60+0Ch], edi
0x18003aca4  mov     edx, ebx; lOffset
0x18003aca6  add     dword ptr [rbp+47h+var_50], edi
0x18003aca9  mov     ecx, r13d; hFile
0x18003acac  add     dword ptr [rbp+47h+var_50+4], edi
0x18003acaf  call    _llseek
0x18003acb4  mov     r8d, r14d; unsigned int
0x18003acb7  lea     rdx, [rbp+47h+var_70]; void *
0x18003acbb  mov     ecx, r13d; int
0x18003acbe  call    ?MuWrite@@YAKHPEBXK@Z; MuWrite(int,void const *,ulong)
0x18003acc3  jmp     loc_18003AAD2
0x18003acc8  xor     eax, eax
0x18003acca  jmp     loc_18003AB9A
```
