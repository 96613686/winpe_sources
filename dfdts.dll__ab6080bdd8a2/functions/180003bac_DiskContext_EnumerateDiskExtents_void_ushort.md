# DiskContext::EnumerateDiskExtents(void *,ushort *)

- ea: `0x180003bac`
- end: `0x180003e36`
- name: `?EnumerateDiskExtents@DiskContext@@AEAAKPEAXPEAG@Z`
- size: `650`
- prototype: `__int64 __fastcall(DiskContext *this, char *hDevice, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004d68`

## callees

- `0x180002c90`
- `0x180003984`
- `0x180003bac`
- `0x18000495c`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x180003c39`
- `KERNEL32!DeviceIoControl` at `0x180003d0a`
- `KERNEL32!DeviceIoControl` at `0x180003c39`
- `KERNEL32!DeviceIoControl` at `0x180003d0a`
- `KERNEL32!HeapAlloc` at `0x180003bfa`
- `KERNEL32!HeapAlloc` at `0x180003cc4`
- `KERNEL32!HeapAlloc` at `0x180003bfa`
- `KERNEL32!HeapAlloc` at `0x180003cc4`
- `KERNEL32!GetProcessHeap` at `0x180003be6`
- `KERNEL32!GetProcessHeap` at `0x180003c9f`
- `KERNEL32!GetProcessHeap` at `0x180003cb3`
- `KERNEL32!GetProcessHeap` at `0x180003e08`
- `KERNEL32!GetProcessHeap` at `0x180003be6`
- `KERNEL32!GetProcessHeap` at `0x180003c9f`
- `KERNEL32!GetProcessHeap` at `0x180003cb3`
- `KERNEL32!GetProcessHeap` at `0x180003e08`
- `KERNEL32!HeapFree` at `0x180003cad`
- `KERNEL32!HeapFree` at `0x180003e16`
- `KERNEL32!HeapFree` at `0x180003cad`
- `KERNEL32!HeapFree` at `0x180003e16`
- `KERNEL32!GetLastError` at `0x180003c47`
- `KERNEL32!GetLastError` at `0x180003d14`
- `KERNEL32!GetLastError` at `0x180003c47`
- `KERNEL32!GetLastError` at `0x180003d14`

## pseudocode

```c
__int64 __fastcall DiskContext::EnumerateDiskExtents(DiskContext *this, char *hDevice, unsigned __int16 *a3)
{
  HANDLE ProcessHeap; // rax
  unsigned int *lpOutBuffer; // rbx
  DWORD LastError; // eax
  unsigned int v9; // edi
  unsigned int v10; // r14d
  unsigned int v11; // r12d
  HANDLE v12; // rax
  HANDLE v13; // rax
  DWORD v14; // eax
  _QWORD *v15; // rcx
  int v16; // edx
  __int64 v17; // r15
  unsigned int v18; // eax
  HANDLE v19; // rax
  DWORD BytesReturned; // [rsp+98h] [rbp+10h] BYREF

  BytesReturned = 0;
  if ( (unsigned __int64)(hDevice - 1) > 0xFFFFFFFFFFFFFFFDuLL || !a3 )
    return 87;
  ProcessHeap = GetProcessHeap();
  lpOutBuffer = (unsigned int *)HeapAlloc(ProcessHeap, 8u, 0x20u);
  if ( !lpOutBuffer )
    return 14;
  if ( DeviceIoControl(hDevice, 0x560000u, 0, 0, lpOutBuffer, 0x20u, &BytesReturned, 0) )
  {
    v9 = 0;
    if ( lpOutBuffer[2] == *((_DWORD *)this + 156) )
    {
      v18 = DiskContext::SetVolumeLetters(this, a3);
      v9 = v18;
      if ( v18 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            37,
            (unsigned int)&WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids,
            (_DWORD)a3,
            v18);
      }
    }
    goto LABEL_32;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError != 122 && LastError != 234 )
    goto LABEL_33;
  v10 = *lpOutBuffer;
  v11 = 24 * *lpOutBuffer + 32;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids, v11);
  v12 = GetProcessHeap();
  HeapFree(v12, 0, lpOutBuffer);
  v13 = GetProcessHeap();
  lpOutBuffer = (unsigned int *)HeapAlloc(v13, 8u, v11);
  if ( lpOutBuffer )
  {
    if ( !DeviceIoControl(hDevice, 0x560000u, 0, 0, lpOutBuffer, 24 * v10 + 32, &BytesReturned, 0) )
    {
      v14 = GetLastError();
      v9 = v14;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_33;
      v16 = 35;
      goto LABEL_16;
    }
    if ( v10 > *lpOutBuffer )
      v10 = *lpOutBuffer;
    v17 = 0;
    if ( v10 )
    {
      while ( 1 )
      {
        if ( lpOutBuffer[6 * v17 + 2] == *((_DWORD *)this + 156) )
        {
          v14 = DiskContext::SetVolumeLetters(this, a3);
          v9 = v14;
          if ( v14 )
            break;
        }
        v17 = (unsigned int)(v17 + 1);
        if ( (unsigned int)v17 >= v10 )
          goto LABEL_32;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_33;
      v16 = 36;
LABEL_16:
      WPP_SF_Sd(v15[2], v16, (unsigned int)&WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids, (_DWORD)a3, v14);
      goto LABEL_33;
    }
LABEL_32:
    if ( !lpOutBuffer )
      return v9;
LABEL_33:
    v19 = GetProcessHeap();
    HeapFree(v19, 0, lpOutBuffer);
    return v9;
  }
  return 14;
}

```

## disassembly

```asm
0x180003bac  mov     rax, rsp
0x180003baf  push    rbx
0x180003bb0  push    rbp
0x180003bb1  push    rsi
0x180003bb2  push    rdi
0x180003bb3  push    r12
0x180003bb5  push    r13
0x180003bb7  push    r14
0x180003bb9  push    r15
0x180003bbb  sub     rsp, 48h
0x180003bbf  mov     dword ptr [rax+10h], 0
0x180003bc6  mov     rsi, r8
0x180003bc9  lea     rax, [rdx-1]
0x180003bcd  mov     r15, rdx
0x180003bd0  mov     r13, rcx
0x180003bd3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003bd7  ja      loc_180003E1E
0x180003bdd  test    r8, r8
0x180003be0  jz      loc_180003E1E
0x180003be6  call    cs:__imp_GetProcessHeap
0x180003bec  mov     edi, 20h ; ' '
0x180003bf1  mov     rcx, rax; hHeap
0x180003bf4  mov     r8d, edi; dwBytes
0x180003bf7  lea     edx, [rdi-18h]; dwFlags
0x180003bfa  call    cs:__imp_HeapAlloc
0x180003c00  mov     rbx, rax
0x180003c03  test    rax, rax
0x180003c06  jz      loc_180003CD2
0x180003c0c  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x180003c15  lea     rax, [rsp+88h+BytesReturned]
0x180003c1d  mov     [rsp+88h+lpBytesReturned], rax; lpBytesReturned
0x180003c22  xor     r9d, r9d; nInBufferSize
0x180003c25  mov     [rsp+88h+nOutBufferSize], edi; nOutBufferSize
0x180003c29  xor     r8d, r8d; lpInBuffer
0x180003c2c  mov     edx, 560000h; dwIoControlCode
0x180003c31  mov     [rsp+88h+lpOutBuffer], rbx; lpOutBuffer
0x180003c36  mov     rcx, r15; hDevice
0x180003c39  call    cs:__imp_DeviceIoControl
0x180003c3f  test    eax, eax
0x180003c41  jnz     loc_180003DAF
0x180003c47  call    cs:__imp_GetLastError
0x180003c4d  mov     edi, eax
0x180003c4f  cmp     eax, 7Ah ; 'z'
0x180003c52  jz      short loc_180003C5F
0x180003c54  cmp     eax, 0EAh
0x180003c59  jnz     loc_180003E08
0x180003c5f  mov     r14d, [rbx]
0x180003c62  lea     ecx, [r14+r14*2]
0x180003c66  lea     r12d, ds:20h[rcx*8]
0x180003c6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c75  lea     rbp, WPP_GLOBAL_Control
0x180003c7c  cmp     rcx, rbp
0x180003c7f  jz      short loc_180003C9F
0x180003c81  test    byte ptr [rcx+1Ch], 4
0x180003c85  jz      short loc_180003C9F
0x180003c87  mov     rcx, [rcx+10h]
0x180003c8b  lea     r8, WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids
0x180003c92  mov     edx, 22h ; '"'
0x180003c97  mov     r9d, r12d
0x180003c9a  call    WPP_SF_d
0x180003c9f  call    cs:__imp_GetProcessHeap
0x180003ca5  mov     r8, rbx; lpMem
0x180003ca8  xor     edx, edx; dwFlags
0x180003caa  mov     rcx, rax; hHeap
0x180003cad  call    cs:__imp_HeapFree
0x180003cb3  call    cs:__imp_GetProcessHeap
0x180003cb9  mov     r8d, r12d; dwBytes
0x180003cbc  mov     edx, 8; dwFlags
0x180003cc1  mov     rcx, rax; hHeap
0x180003cc4  call    cs:__imp_HeapAlloc
0x180003cca  mov     rbx, rax
0x180003ccd  test    rax, rax
0x180003cd0  jnz     short loc_180003CDC
0x180003cd2  mov     edi, 0Eh
0x180003cd7  jmp     loc_180003E23
0x180003cdc  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x180003ce5  lea     rax, [rsp+88h+BytesReturned]
0x180003ced  mov     [rsp+88h+lpBytesReturned], rax; lpBytesReturned
0x180003cf2  xor     r9d, r9d; nInBufferSize
0x180003cf5  mov     [rsp+88h+nOutBufferSize], r12d; nOutBufferSize
0x180003cfa  xor     r8d, r8d; lpInBuffer
0x180003cfd  mov     edx, 560000h; dwIoControlCode
0x180003d02  mov     [rsp+88h+lpOutBuffer], rbx; lpOutBuffer
0x180003d07  mov     rcx, r15; hDevice
0x180003d0a  call    cs:__imp_DeviceIoControl
0x180003d10  test    eax, eax
0x180003d12  jnz     short loc_180003D57
0x180003d14  call    cs:__imp_GetLastError
0x180003d1a  mov     edi, eax
0x180003d1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d23  cmp     rcx, rbp
0x180003d26  jz      loc_180003E08
0x180003d2c  test    byte ptr [rcx+1Ch], 1
0x180003d30  jz      loc_180003E08
0x180003d36  mov     edx, 23h ; '#'
0x180003d3b  mov     rcx, [rcx+10h]
0x180003d3f  lea     r8, WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids
0x180003d46  mov     r9, rsi
0x180003d49  mov     dword ptr [rsp+88h+lpOutBuffer], eax
0x180003d4d  call    WPP_SF_Sd
0x180003d52  jmp     loc_180003E08
0x180003d57  cmp     r14d, [rbx]
0x180003d5a  cmova   r14d, [rbx]
0x180003d5e  xor     r15d, r15d
0x180003d61  test    r14d, r14d
0x180003d64  jz      loc_180003E03
0x180003d6a  mov     eax, [r13+270h]
0x180003d71  lea     rcx, [r15+r15*2]
0x180003d75  cmp     [rbx+rcx*8+8], eax
0x180003d79  jnz     short loc_180003D8C
0x180003d7b  mov     rdx, rsi; unsigned __int16 *
0x180003d7e  mov     rcx, r13; this
0x180003d81  call    ?SetVolumeLetters@DiskContext@@AEAAKPEAG@Z; DiskContext::SetVolumeLetters(ushort *)
0x180003d86  mov     edi, eax
0x180003d88  test    eax, eax
0x180003d8a  jnz     short loc_180003D96
0x180003d8c  inc     r15d
0x180003d8f  cmp     r15d, r14d
0x180003d92  jb      short loc_180003D6A
0x180003d94  jmp     short loc_180003E03
0x180003d96  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d9d  cmp     rcx, rbp
0x180003da0  jz      short loc_180003E08
0x180003da2  test    byte ptr [rcx+1Ch], 1
0x180003da6  jz      short loc_180003E08
0x180003da8  mov     edx, 24h ; '$'
0x180003dad  jmp     short loc_180003D3B
0x180003daf  mov     eax, [r13+270h]
0x180003db6  xor     edi, edi
0x180003db8  cmp     [rbx+8], eax
0x180003dbb  jnz     short loc_180003E03
0x180003dbd  mov     rdx, rsi; unsigned __int16 *
0x180003dc0  mov     rcx, r13; this
0x180003dc3  call    ?SetVolumeLetters@DiskContext@@AEAAKPEAG@Z; DiskContext::SetVolumeLetters(ushort *)
0x180003dc8  mov     edi, eax
0x180003dca  test    eax, eax
0x180003dcc  jz      short loc_180003E03
0x180003dce  mov     rcx, cs:WPP_GLOBAL_Control
0x180003dd5  lea     rbp, WPP_GLOBAL_Control
0x180003ddc  cmp     rcx, rbp
0x180003ddf  jz      short loc_180003E03
0x180003de1  test    byte ptr [rcx+1Ch], 1
0x180003de5  jz      short loc_180003E03
0x180003de7  mov     rcx, [rcx+10h]
0x180003deb  lea     r8, WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids
0x180003df2  mov     edx, 25h ; '%'
0x180003df7  mov     dword ptr [rsp+88h+lpOutBuffer], eax
0x180003dfb  mov     r9, rsi
0x180003dfe  call    WPP_SF_Sd
0x180003e03  test    rbx, rbx
0x180003e06  jz      short loc_180003E23
0x180003e08  call    cs:__imp_GetProcessHeap
0x180003e0e  mov     r8, rbx; lpMem
0x180003e11  xor     edx, edx; dwFlags
0x180003e13  mov     rcx, rax; hHeap
0x180003e16  call    cs:__imp_HeapFree
0x180003e1c  jmp     short loc_180003E23
0x180003e1e  mov     edi, 57h ; 'W'
0x180003e23  mov     eax, edi
0x180003e25  add     rsp, 48h
0x180003e29  pop     r15
0x180003e2b  pop     r14
0x180003e2d  pop     r13
0x180003e2f  pop     r12
0x180003e31  pop     rdi
0x180003e32  pop     rsi
0x180003e33  pop     rbp
0x180003e34  pop     rbx
0x180003e35  retn
```
