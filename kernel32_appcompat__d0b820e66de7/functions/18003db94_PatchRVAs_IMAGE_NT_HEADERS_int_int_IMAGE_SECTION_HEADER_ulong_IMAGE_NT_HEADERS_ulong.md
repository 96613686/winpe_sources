# PatchRVAs<_IMAGE_NT_HEADERS>(int,int,_IMAGE_SECTION_HEADER *,ulong,_IMAGE_NT_HEADERS *,ulong)

- ea: `0x18003db94`
- end: `0x18003de34`
- name: `??$PatchRVAs@U_IMAGE_NT_HEADERS@@@@YAJHHPEAU_IMAGE_SECTION_HEADER@@KPEAU_IMAGE_NT_HEADERS@@K@Z`
- size: `672`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x18004d0dc`

## callees

- `0x180033330`
- `0x1800398a4`
- `0x18003db94`
- `0x18005987c`
- `0x1800827c0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003dc6b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003ddad`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003dc6b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003ddad`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003dc3e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003dc94`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003dd43`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003dd5a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003dc3e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003dc94`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003dd43`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003dd5a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003dcc1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003dd88`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003dcc1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003dd88`

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
0x18003db94  push    rbp
0x18003db96  push    rbx
0x18003db97  push    rsi
0x18003db98  push    rdi
0x18003db99  push    r12
0x18003db9b  push    r13
0x18003db9d  push    r14
0x18003db9f  push    r15
0x18003dba1  lea     rbp, [rsp-0Fh]
0x18003dba6  sub     rsp, 98h
0x18003dbad  mov     rax, cs:__security_cookie
0x18003dbb4  xor     rax, rsp
0x18003dbb7  mov     [rbp+47h+var_48], rax
0x18003dbbb  mov     rsi, [rbp+47h+arg_20]
0x18003dbbf  xor     eax, eax
0x18003dbc1  xorps   xmm0, xmm0
0x18003dbc4  mov     [rbp+47h+var_98], r9d
0x18003dbc8  mov     [rbp+47h+var_90], r8
0x18003dbcc  mov     r13d, edx
0x18003dbcf  mov     [rbp+47h+var_94], edx
0x18003dbd2  mov     edi, [rsi+54h]
0x18003dbd5  movsxd  r12, ecx
0x18003dbd8  mov     [rbp+47h+var_9C], 0
0x18003dbdf  movups  xmmword ptr [rbp+47h+var_70], xmm0
0x18003dbe3  mov     [rbp+47h+var_50], rax
0x18003dbe7  movups  [rbp+47h+var_60], xmm0
0x18003dbeb  mov     [rbp+47h+var_78], eax
0x18003dbee  movups  [rbp+47h+Buffer], xmm0
0x18003dbf2  sub     edi, [rbp+47h+arg_28]
0x18003dbf5  jz      loc_18003DCE6
0x18003dbfb  mov     ebx, [rsi+78h]
0x18003dbfe  test    ebx, ebx
0x18003dc00  jnz     loc_18003DDD3
0x18003dc06  mov     r14d, [rsi+80h]
0x18003dc0d  test    r14d, r14d
0x18003dc10  jz      loc_18003DE2D
0x18003dc16  cmp     r14d, [rsi+54h]
0x18003dc1a  jnb     loc_18003DE2D
0x18003dc20  xor     r15d, r15d
0x18003dc23  lea     eax, [r15+r15*4]
0x18003dc27  xor     r9d, r9d; dwMoveMethod
0x18003dc2a  lea     ebx, ds:0[rax*4]
0x18003dc31  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003dc34  mov     edx, ebx
0x18003dc36  mov     rcx, r12; hFile
0x18003dc39  sub     edx, edi
0x18003dc3b  add     edx, r14d; lDistanceToMove
0x18003dc3e  call    cs:__imp_SetFilePointer
0x18003dc45  nop     dword ptr [rax+rax+00h]
0x18003dc4a  lea     r9, [rbp+47h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003dc4e  mov     [rbp+47h+NumberOfBytesRead], 0
0x18003dc55  mov     r8d, 14h; nNumberOfBytesToRead
0x18003dc5b  mov     [rsp+0D0h+lpOverlapped], 0; lpOverlapped
0x18003dc64  lea     rdx, [rbp+47h+Buffer]; lpBuffer
0x18003dc68  mov     rcx, r12; hFile
0x18003dc6b  call    cs:__imp_ReadFile
0x18003dc72  nop     dword ptr [rax+rax+00h]
0x18003dc77  cmp     [rbp+47h+var_78], 0
0x18003dc7b  jz      loc_18003DE2D
0x18003dc81  add     dword ptr [rbp+47h+Buffer+0Ch], edi
0x18003dc84  lea     edx, [rbx+r14]; lDistanceToMove
0x18003dc88  movsxd  r13, r13d
0x18003dc8b  xor     r9d, r9d; dwMoveMethod
0x18003dc8e  mov     rcx, r13; hFile
0x18003dc91  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003dc94  call    cs:__imp_SetFilePointer
0x18003dc9b  nop     dword ptr [rax+rax+00h]
0x18003dca0  lea     r9, [rbp+47h+NumberOfBytesRead]; lpNumberOfBytesWritten
0x18003dca4  mov     [rbp+47h+NumberOfBytesRead], 0
0x18003dcab  mov     r8d, 14h; nNumberOfBytesToWrite
0x18003dcb1  mov     [rsp+0D0h+lpOverlapped], 0; lpOverlapped
0x18003dcba  lea     rdx, [rbp+47h+Buffer]; lpBuffer
0x18003dcbe  mov     rcx, r13; hFile
0x18003dcc1  call    cs:__imp_WriteFile
0x18003dcc8  nop     dword ptr [rax+rax+00h]
0x18003dccd  mov     r10d, [rbp+47h+var_78]
0x18003dcd1  xor     edx, edx
0x18003dcd3  movzx   r11d, word ptr [rsi+6]
0x18003dcd8  mov     rbx, [rbp+47h+var_90]
0x18003dcdc  cmp     edx, r11d
0x18003dcdf  jb      short loc_18003DD07
0x18003dce1  mov     eax, 0Dh
0x18003dce6  mov     rcx, [rbp+47h+var_48]
0x18003dcea  xor     rcx, rsp; StackCookie
0x18003dced  call    __security_check_cookie
0x18003dcf2  add     rsp, 98h
0x18003dcf9  pop     r15
0x18003dcfb  pop     r14
0x18003dcfd  pop     r13
0x18003dcff  pop     r12
0x18003dd01  pop     rdi
0x18003dd02  pop     rsi
0x18003dd03  pop     rbx
0x18003dd04  pop     rbp
0x18003dd05  retn
0x18003dd07  lea     r8, [rdx+rdx*4]
0x18003dd0b  mov     r9d, [rbx+r8*8+0Ch]
0x18003dd10  cmp     r10d, r9d
0x18003dd13  jb      loc_18003DDCC
0x18003dd19  mov     ecx, [rbx+r8*8+10h]
0x18003dd1e  add     ecx, r9d
0x18003dd21  cmp     r10d, ecx
0x18003dd24  jnb     loc_18003DDCC
0x18003dd2a  mov     ebx, [rbx+r8*8+14h]
0x18003dd2f  sub     ebx, r9d
0x18003dd32  add     ebx, r10d
0x18003dd35  mov     edx, ebx
0x18003dd37  xor     r9d, r9d; dwMoveMethod
0x18003dd3a  sub     edx, [rbp+47h+var_98]; lDistanceToMove
0x18003dd3d  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003dd40  mov     rcx, r12; hFile
0x18003dd43  call    cs:__imp_SetFilePointer
0x18003dd4a  nop     dword ptr [rax+rax+00h]
0x18003dd4f  xor     r9d, r9d; dwMoveMethod
0x18003dd52  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003dd55  mov     edx, ebx; lDistanceToMove
0x18003dd57  mov     rcx, r13; hFile
0x18003dd5a  call    cs:__imp_SetFilePointer
0x18003dd61  nop     dword ptr [rax+rax+00h]
0x18003dd66  xor     ebx, ebx
0x18003dd68  jmp     short loc_18003DD94
0x18003dd6a  add     eax, edi
0x18003dd6c  mov     [rbp+47h+NumberOfBytesRead], ebx
0x18003dd6f  lea     r9, [rbp+47h+NumberOfBytesRead]; lpNumberOfBytesWritten
0x18003dd73  mov     [rbp+47h+var_9C], eax
0x18003dd76  mov     r8d, 4; nNumberOfBytesToWrite
0x18003dd7c  mov     [rsp+0D0h+lpOverlapped], rbx; lpOverlapped
0x18003dd81  lea     rdx, [rbp+47h+var_9C]; lpBuffer
0x18003dd85  mov     rcx, r13; hFile
0x18003dd88  call    cs:__imp_WriteFile
0x18003dd8f  nop     dword ptr [rax+rax+00h]
0x18003dd94  lea     r9, [rbp+47h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003dd98  mov     [rsp+0D0h+lpOverlapped], rbx; lpOverlapped
0x18003dd9d  mov     r8d, 4; nNumberOfBytesToRead
0x18003dda3  mov     [rbp+47h+NumberOfBytesRead], ebx
0x18003dda6  lea     rdx, [rbp+47h+var_9C]; lpBuffer
0x18003ddaa  mov     rcx, r12; hFile
0x18003ddad  call    cs:__imp_ReadFile
0x18003ddb4  nop     dword ptr [rax+rax+00h]
0x18003ddb9  mov     eax, [rbp+47h+var_9C]
0x18003ddbc  test    eax, eax
0x18003ddbe  jnz     short loc_18003DD6A
0x18003ddc0  mov     r13d, [rbp+47h+var_94]
0x18003ddc4  inc     r15d
0x18003ddc7  jmp     loc_18003DC23
0x18003ddcc  inc     edx
0x18003ddce  jmp     loc_18003DCDC
0x18003ddd3  cmp     ebx, [rsi+54h]
0x18003ddd6  jnb     loc_18003DC06
0x18003dddc  mov     edx, ebx
0x18003ddde  xor     r8d, r8d; iOrigin
0x18003dde1  sub     edx, edi; lOffset
0x18003dde3  mov     ecx, r12d; hFile
0x18003dde6  call    _llseek
0x18003ddeb  mov     r14d, 28h ; '('
0x18003ddf1  lea     rdx, [rbp+47h+var_70]; unsigned __int8 *
0x18003ddf5  mov     r8d, r14d; unsigned int
0x18003ddf8  mov     ecx, r12d; int
0x18003ddfb  call    ?MuRead@@YAKHPEAEK@Z; MuRead(int,uchar *,ulong)
0x18003de00  add     dword ptr [rbp+47h+var_70+0Ch], edi
0x18003de03  xor     r8d, r8d; iOrigin
0x18003de06  add     dword ptr [rbp+47h+var_60+0Ch], edi
0x18003de09  mov     edx, ebx; lOffset
0x18003de0b  add     dword ptr [rbp+47h+var_50], edi
0x18003de0e  mov     ecx, r13d; hFile
0x18003de11  add     dword ptr [rbp+47h+var_50+4], edi
0x18003de14  call    _llseek
0x18003de19  mov     r8d, r14d; unsigned int
0x18003de1c  lea     rdx, [rbp+47h+var_70]; void *
0x18003de20  mov     ecx, r13d; int
0x18003de23  call    ?MuWrite@@YAKHPEBXK@Z; MuWrite(int,void const *,ulong)
0x18003de28  jmp     loc_18003DC06
0x18003de2d  xor     eax, eax
0x18003de2f  jmp     loc_18003DCE6
```
