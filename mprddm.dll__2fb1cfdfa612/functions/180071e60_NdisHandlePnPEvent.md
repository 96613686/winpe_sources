# NdisHandlePnPEvent

- ea: `0x180071e60`
- end: `0x1800720c0`
- name: `NdisHandlePnPEvent`
- size: `608`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18006b610`
- `0x18006be30`

## callees

- `0x180071e60`
- `0x1800720c8`
- `0x18008c5f2`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180072094`
- `KERNEL32!LocalFree` at `0x180072094`
- `KERNEL32!DeviceIoControl` at `0x18007206d`
- `KERNEL32!DeviceIoControl` at `0x18007206d`
- `KERNEL32!SetLastError` at `0x1800720a3`
- `KERNEL32!SetLastError` at `0x1800720a3`
- `KERNEL32!CreateFileW` at `0x180072035`
- `KERNEL32!CreateFileW` at `0x180072035`
- `KERNEL32!CloseHandle` at `0x180072081`
- `KERNEL32!CloseHandle` at `0x180072081`
- `KERNEL32!GetLastError` at `0x180072076`
- `KERNEL32!GetLastError` at `0x180072089`
- `KERNEL32!GetLastError` at `0x180072076`
- `KERNEL32!GetLastError` at `0x180072089`
- `KERNEL32!LocalAlloc` at `0x180071f92`
- `KERNEL32!LocalAlloc` at `0x180071f92`

## pseudocode

```c
__int64 __fastcall NdisHandlePnPEvent(
        DWORD a1,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  unsigned int v8; // r13d
  int v9; // eax
  unsigned int v10; // ecx
  __int64 v11; // rax
  int v12; // eax
  unsigned int v13; // edx
  __int64 v14; // rax
  __int64 v15; // r12
  unsigned __int16 *v16; // rbx
  int v17; // eax
  unsigned int v18; // r8d
  __int64 v19; // rcx
  unsigned int v20; // ecx
  DWORD v21; // ebp
  _OWORD *v22; // rax
  _QWORD *v23; // rdi
  DWORD LastError; // ebx
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int64 v28; // rax
  HANDLE FileW; // rsi
  _OWORD v31[2]; // [rsp+40h] [rbp-98h] BYREF
  __int128 v32; // [rsp+60h] [rbp-78h]
  __int128 v33; // [rsp+70h] [rbp-68h]
  DWORD BytesReturned; // [rsp+E0h] [rbp+8h] BYREF

  BytesReturned = a1;
  memset_0(v31, 0, 0x48u);
  v8 = 0;
  BytesReturned = 0;
  if ( a2 > 0xF )
    goto LABEL_32;
  v9 = 53230;
  if ( !_bittest(&v9, a2) )
    goto LABEL_32;
  *(_QWORD *)&v32 = 72;
  if ( !a3 )
  {
    v11 = 0;
    v10 = 74;
    goto LABEL_7;
  }
  v10 = *a3 + 74;
  if ( v10 < 0x48 )
  {
LABEL_32:
    LastError = 87;
    goto LABEL_33;
  }
  v11 = *a3;
LABEL_7:
  if ( v10 < (unsigned __int64)(v11 + 2) )
    goto LABEL_32;
  *(_QWORD *)&v33 = v10;
  v12 = a4 ? *a4 : 0;
  v13 = v10 + v12 + 2;
  if ( v13 < v10 )
    goto LABEL_32;
  v14 = a4 ? *a4 : 0LL;
  v15 = v13;
  if ( v13 < (unsigned __int64)(v14 + 2) )
    goto LABEL_32;
  v16 = a5;
  v17 = a5 ? *a5 : 0;
  v18 = v13 + v17 + 2;
  if ( v18 < v13 )
    goto LABEL_32;
  v19 = a5 ? *a5 : 0LL;
  if ( v18 < (unsigned __int64)(v19 + 2) )
    goto LABEL_32;
  v20 = v18 + (-v18 & 7);
  *((_QWORD *)&v31[0] + 1) = v20;
  v21 = v20 + 1;
  if ( v20 + 1 < v20 || v20 == -1 )
    goto LABEL_32;
  v22 = LocalAlloc(0x40u, v21);
  v23 = v22;
  if ( v22 )
  {
    v25 = v31[1];
    *v22 = v31[0];
    v26 = v32;
    v22[1] = v25;
    v27 = v33;
    v22[2] = v26;
    v22[3] = v27;
    *((_QWORD *)v22 + 8) = v15;
    *(_DWORD *)v22 = 2;
    *((_DWORD *)v22 + 1) = a2;
    NdispUnicodeStringToVar(v22, a3, (char *)v22 + 24);
    NdispUnicodeStringToVar(v23, a4, v23 + 5);
    NdispUnicodeStringToVar(v23, v16, v23 + 7);
    v28 = v23[1];
    *((_DWORD *)v23 + 4) = 0;
    *((_BYTE *)v23 + v28) = 0;
    FileW = CreateFileW(L"\\\\.\\NDIS", 0xC0000000, 0, 0, 3u, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
    }
    else
    {
      v8 = DeviceIoControl(FileW, 0x170008u, v23, v21, 0, 0, &BytesReturned, 0);
      LastError = GetLastError();
      CloseHandle(FileW);
    }
    LocalFree(v23);
  }
  else
  {
    LastError = 8;
  }
LABEL_33:
  SetLastError(LastError);
  return v8;
}

```

## disassembly

```asm
0x180071e60  mov     [rsp+BytesReturned], ecx
0x180071e64  push    rbx
0x180071e65  push    rbp
0x180071e66  push    rsi
0x180071e67  push    rdi
0x180071e68  push    r12
0x180071e6a  push    r13
0x180071e6c  push    r14
0x180071e6e  push    r15
0x180071e70  sub     rsp, 98h
0x180071e77  mov     r14, r8
0x180071e7a  lea     rcx, [rsp+0D8h+var_98]; void *
0x180071e7f  mov     r15d, edx
0x180071e82  mov     ebx, 48h ; 'H'
0x180071e87  mov     r8d, ebx; Size
0x180071e8a  xor     edx, edx; Val
0x180071e8c  mov     rsi, r9
0x180071e8f  call    memset_0
0x180071e94  xor     r13d, r13d
0x180071e97  mov     [rsp+0D8h+BytesReturned], r13d
0x180071e9f  cmp     r15d, 0Fh
0x180071ea3  ja      loc_18007209C
0x180071ea9  mov     eax, 0CFEEh
0x180071eae  bt      eax, r15d
0x180071eb2  jnb     loc_18007209C
0x180071eb8  mov     qword ptr [rsp+0D8h+var_78], rbx
0x180071ebd  test    r14, r14
0x180071ec0  jz      short loc_180071ED7
0x180071ec2  movzx   ecx, word ptr [r14]
0x180071ec6  add     ecx, 4Ah ; 'J'
0x180071ec9  cmp     ecx, ebx
0x180071ecb  jb      loc_18007209C
0x180071ed1  movzx   eax, word ptr [r14]
0x180071ed5  jmp     short loc_180071EDC
0x180071ed7  xor     eax, eax
0x180071ed9  lea     ecx, [rax+4Ah]
0x180071edc  mov     edx, ecx
0x180071ede  add     rax, 2
0x180071ee2  cmp     rdx, rax
0x180071ee5  jb      loc_18007209C
0x180071eeb  mov     qword ptr [rsp+0D8h+var_68], rdx
0x180071ef0  test    rsi, rsi
0x180071ef3  jnz     short loc_180071EF9
0x180071ef5  xor     eax, eax
0x180071ef7  jmp     short loc_180071EFC
0x180071ef9  movzx   eax, word ptr [rsi]
0x180071efc  lea     edx, [rax+2]
0x180071eff  add     edx, ecx
0x180071f01  cmp     edx, ecx
0x180071f03  jb      loc_18007209C
0x180071f09  test    rsi, rsi
0x180071f0c  jnz     short loc_180071F12
0x180071f0e  xor     eax, eax
0x180071f10  jmp     short loc_180071F15
0x180071f12  movzx   eax, word ptr [rsi]
0x180071f15  mov     r12d, edx
0x180071f18  add     rax, 2
0x180071f1c  cmp     r12, rax
0x180071f1f  jb      loc_18007209C
0x180071f25  mov     rbx, [rsp+0D8h+arg_20]
0x180071f2d  test    rbx, rbx
0x180071f30  jnz     short loc_180071F36
0x180071f32  xor     eax, eax
0x180071f34  jmp     short loc_180071F39
0x180071f36  movzx   eax, word ptr [rbx]
0x180071f39  lea     r8d, [rax+2]
0x180071f3d  add     r8d, edx
0x180071f40  cmp     r8d, edx
0x180071f43  jb      loc_18007209C
0x180071f49  test    rbx, rbx
0x180071f4c  jnz     short loc_180071F52
0x180071f4e  xor     ecx, ecx
0x180071f50  jmp     short loc_180071F55
0x180071f52  movzx   ecx, word ptr [rbx]
0x180071f55  add     rcx, 2
0x180071f59  mov     eax, r8d
0x180071f5c  cmp     rax, rcx
0x180071f5f  jb      loc_18007209C
0x180071f65  mov     ecx, r8d
0x180071f68  neg     ecx
0x180071f6a  and     ecx, 7
0x180071f6d  add     ecx, r8d
0x180071f70  mov     eax, ecx
0x180071f72  mov     qword ptr [rsp+0D8h+var_98+8], rax
0x180071f77  lea     ebp, [rcx+1]
0x180071f7a  cmp     ebp, ecx
0x180071f7c  jb      loc_18007209C
0x180071f82  cmp     ebp, 1
0x180071f85  jb      loc_18007209C
0x180071f8b  mov     edx, ebp; uBytes
0x180071f8d  mov     ecx, 40h ; '@'; uFlags
0x180071f92  call    cs:__imp_LocalAlloc
0x180071f98  mov     rdi, rax
0x180071f9b  test    rax, rax
0x180071f9e  jnz     short loc_180071FA8
0x180071fa0  lea     ebx, [rax+8]
0x180071fa3  jmp     loc_1800720A1
0x180071fa8  movaps  xmm0, [rsp+0D8h+var_98]
0x180071fad  lea     r8, [rax+18h]
0x180071fb1  movaps  xmm1, [rsp+0D8h+var_88]
0x180071fb6  mov     rdx, r14
0x180071fb9  movups  xmmword ptr [rax], xmm0
0x180071fbc  mov     rcx, rdi
0x180071fbf  movaps  xmm0, [rsp+0D8h+var_78]
0x180071fc4  movups  xmmword ptr [rax+10h], xmm1
0x180071fc8  movaps  xmm1, [rsp+0D8h+var_68]
0x180071fcd  movups  xmmword ptr [rax+20h], xmm0
0x180071fd1  movups  xmmword ptr [rax+30h], xmm1
0x180071fd5  mov     [rax+40h], r12
0x180071fd9  mov     dword ptr [rax], 2
0x180071fdf  mov     [rax+4], r15d
0x180071fe3  call    NdispUnicodeStringToVar
0x180071fe8  lea     r8, [rdi+28h]
0x180071fec  mov     rdx, rsi
0x180071fef  mov     rcx, rdi
0x180071ff2  call    NdispUnicodeStringToVar
0x180071ff7  lea     r8, [rdi+38h]
0x180071ffb  mov     rdx, rbx
0x180071ffe  mov     rcx, rdi
0x180072001  call    NdispUnicodeStringToVar
0x180072006  mov     rax, [rdi+8]
0x18007200a  lea     rcx, aNdis_0; "\\\\.\\NDIS"
0x180072011  xor     ebx, ebx
0x180072013  xor     r9d, r9d; lpSecurityAttributes
0x180072016  mov     [rsp+0D8h+hTemplateFile], rbx; hTemplateFile
0x18007201b  xor     r8d, r8d; dwShareMode
0x18007201e  mov     [rdi+10h], ebx
0x180072021  mov     edx, 0C0000000h; dwDesiredAccess
0x180072026  mov     [rsp+0D8h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18007202a  mov     [rdi+rax], bl
0x18007202d  mov     [rsp+0D8h+dwCreationDisposition], 3; dwCreationDisposition
0x180072035  call    cs:__imp_CreateFileW
0x18007203b  mov     rsi, rax
0x18007203e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180072042  jz      short loc_180072089
0x180072044  mov     [rsp+0D8h+lpOverlapped], rbx; lpOverlapped
0x180072049  lea     rax, [rsp+0D8h+BytesReturned]
0x180072051  mov     [rsp+0D8h+hTemplateFile], rax; lpBytesReturned
0x180072056  mov     r9d, ebp; nInBufferSize
0x180072059  mov     [rsp+0D8h+dwFlagsAndAttributes], ebx; nOutBufferSize
0x18007205d  mov     r8, rdi; lpInBuffer
0x180072060  mov     edx, 170008h; dwIoControlCode
0x180072065  mov     qword ptr [rsp+0D8h+dwCreationDisposition], rbx; lpOutBuffer
0x18007206a  mov     rcx, rsi; hDevice
0x18007206d  call    cs:__imp_DeviceIoControl
0x180072073  mov     r13d, eax
0x180072076  call    cs:__imp_GetLastError
0x18007207c  mov     rcx, rsi; hObject
0x18007207f  mov     ebx, eax
0x180072081  call    cs:__imp_CloseHandle
0x180072087  jmp     short loc_180072091
0x180072089  call    cs:__imp_GetLastError
0x18007208f  mov     ebx, eax
0x180072091  mov     rcx, rdi; hMem
0x180072094  call    cs:__imp_LocalFree
0x18007209a  jmp     short loc_1800720A1
0x18007209c  mov     ebx, 57h ; 'W'
0x1800720a1  mov     ecx, ebx; dwErrCode
0x1800720a3  call    cs:__imp_SetLastError
0x1800720a9  mov     eax, r13d
0x1800720ac  add     rsp, 98h
0x1800720b3  pop     r15
0x1800720b5  pop     r14
0x1800720b7  pop     r13
0x1800720b9  pop     r12
0x1800720bb  pop     rdi
0x1800720bc  pop     rsi
0x1800720bd  pop     rbp
0x1800720be  pop     rbx
0x1800720bf  retn
```
