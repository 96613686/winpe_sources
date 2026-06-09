# NdisHandlePnPEvent

- ea: `0x180075758`
- end: `0x1800759f7`
- name: `NdisHandlePnPEvent`
- size: `671`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18006e10c`
- `0x18006e9f0`

## callees

- `0x180075758`
- `0x180075a00`
- `0x180092a92`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800759b2`
- `KERNEL32!LocalFree` at `0x1800759b2`
- `KERNEL32!DeviceIoControl` at `0x180075974`
- `KERNEL32!DeviceIoControl` at `0x180075974`
- `KERNEL32!SetLastError` at `0x1800759c7`
- `KERNEL32!SetLastError` at `0x1800759c7`
- `KERNEL32!CreateFileW` at `0x18007593a`
- `KERNEL32!CreateFileW` at `0x18007593a`
- `KERNEL32!CloseHandle` at `0x180075993`
- `KERNEL32!CloseHandle` at `0x180075993`
- `KERNEL32!GetLastError` at `0x180075982`
- `KERNEL32!GetLastError` at `0x1800759a1`
- `KERNEL32!GetLastError` at `0x180075982`
- `KERNEL32!GetLastError` at `0x1800759a1`
- `KERNEL32!LocalAlloc` at `0x180075890`
- `KERNEL32!LocalAlloc` at `0x180075890`

## pseudocode

```c
__int64 __fastcall NdisHandlePnPEvent(
        DWORD a1,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  unsigned int v8; // edi
  int v9; // eax
  unsigned int v10; // ecx
  __int64 v11; // rax
  int v12; // eax
  unsigned int v13; // r8d
  __int64 v14; // rax
  unsigned __int16 *v15; // rbx
  int v16; // eax
  unsigned int v17; // edx
  __int64 v18; // rcx
  unsigned int v19; // edx
  DWORD v20; // r15d
  _OWORD *v21; // rax
  _QWORD *v22; // rsi
  DWORD LastError; // ebx
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int64 v27; // rax
  HANDLE FileW; // r14
  _OWORD v30[2]; // [rsp+48h] [rbp-31h] BYREF
  __int128 v31; // [rsp+68h] [rbp-11h]
  __int128 v32; // [rsp+78h] [rbp-1h]
  __int64 v33; // [rsp+88h] [rbp+Fh]
  DWORD BytesReturned; // [rsp+C8h] [rbp+4Fh] BYREF

  BytesReturned = a1;
  memset_0(v30, 0, 0x48u);
  v8 = 0;
  BytesReturned = 0;
  if ( a2 > 0xF )
    goto LABEL_28;
  v9 = 53230;
  if ( !_bittest(&v9, a2) )
    goto LABEL_28;
  *(_QWORD *)&v31 = 72;
  if ( a3 )
  {
    v10 = *a3 + 74;
    if ( v10 >= 0x48 )
    {
      v11 = *a3;
      goto LABEL_7;
    }
LABEL_28:
    LastError = 87;
    goto LABEL_29;
  }
  v10 = 74;
  v11 = 0;
LABEL_7:
  if ( v10 < (unsigned __int64)(v11 + 2) )
    goto LABEL_28;
  *(_QWORD *)&v32 = v10;
  v12 = 0;
  if ( a4 )
    v12 = *a4;
  v13 = v10 + v12 + 2;
  if ( v13 < v10 )
    goto LABEL_28;
  v14 = 0;
  if ( a4 )
    v14 = *a4;
  if ( v13 < (unsigned __int64)(v14 + 2) )
    goto LABEL_28;
  v15 = a5;
  v16 = 0;
  v33 = v13;
  if ( a5 )
    v16 = *a5;
  v17 = v13 + v16 + 2;
  if ( v17 < v13 )
    goto LABEL_28;
  v18 = 0;
  if ( a5 )
    v18 = *a5;
  if ( v17 < (unsigned __int64)(v18 + 2) )
    goto LABEL_28;
  v19 = (-v17 & 7) + v17;
  *((_QWORD *)&v30[0] + 1) = v19;
  v20 = v19 + 1;
  if ( v19 + 1 < v19 || v19 == -1 )
    goto LABEL_28;
  v21 = LocalAlloc(0x40u, v20);
  v22 = v21;
  if ( v21 )
  {
    v24 = v30[1];
    *v21 = v30[0];
    v25 = v31;
    v21[1] = v24;
    v26 = v32;
    v21[2] = v25;
    *(_QWORD *)&v25 = v33;
    v21[3] = v26;
    *((_QWORD *)v21 + 8) = v25;
    *(_DWORD *)v21 = 2;
    *((_DWORD *)v21 + 1) = a2;
    NdispUnicodeStringToVar(v21, a3, (char *)v21 + 24);
    NdispUnicodeStringToVar(v22, a4, v22 + 5);
    NdispUnicodeStringToVar(v22, v15, v22 + 7);
    v27 = v22[1];
    *((_DWORD *)v22 + 4) = 0;
    *((_BYTE *)v22 + v27) = 0;
    FileW = CreateFileW(L"\\\\.\\NDIS", 0xC0000000, 0, 0, 3u, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
    }
    else
    {
      v8 = DeviceIoControl(FileW, 0x170008u, v22, v20, 0, 0, &BytesReturned, 0);
      LastError = GetLastError();
      CloseHandle(FileW);
    }
    LocalFree(v22);
  }
  else
  {
    LastError = 8;
  }
LABEL_29:
  SetLastError(LastError);
  return v8;
}

```

## disassembly

```asm
0x180075758  mov     rax, rsp
0x18007575b  mov     [rax+10h], rbx
0x18007575f  mov     [rax+18h], rsi
0x180075763  mov     [rax+20h], rdi
0x180075767  mov     [rax+8], ecx
0x18007576a  push    rbp
0x18007576b  push    r12
0x18007576d  push    r13
0x18007576f  push    r14
0x180075771  push    r15
0x180075773  lea     rbp, [rax-47h]
0x180075777  sub     rsp, 90h
0x18007577e  mov     r12, r8
0x180075781  lea     rcx, [rbp+3Fh+var_70]; void *
0x180075785  mov     r13d, edx
0x180075788  mov     ebx, 48h ; 'H'
0x18007578d  mov     r8d, ebx; Size
0x180075790  xor     edx, edx; Val
0x180075792  mov     r14, r9
0x180075795  call    memset_0
0x18007579a  xor     edi, edi
0x18007579c  mov     [rbp+3Fh+BytesReturned], edi
0x18007579f  cmp     r13d, 0Fh
0x1800757a3  ja      loc_1800759C0
0x1800757a9  mov     eax, 0CFEEh
0x1800757ae  bt      eax, r13d
0x1800757b2  jnb     loc_1800759C0
0x1800757b8  mov     qword ptr [rbp+3Fh+var_50], rbx
0x1800757bc  test    r12, r12
0x1800757bf  jnz     short loc_1800757C8
0x1800757c1  lea     ecx, [rbx+2]
0x1800757c4  mov     eax, edi
0x1800757c6  jmp     short loc_1800757DD
0x1800757c8  movzx   ecx, word ptr [r12]
0x1800757cd  add     ecx, 4Ah ; 'J'
0x1800757d0  cmp     ecx, ebx
0x1800757d2  jb      loc_1800759C0
0x1800757d8  movzx   eax, word ptr [r12]
0x1800757dd  mov     edx, ecx
0x1800757df  add     rax, 2
0x1800757e3  cmp     rdx, rax
0x1800757e6  jb      loc_1800759C0
0x1800757ec  mov     qword ptr [rbp+3Fh+var_40], rdx
0x1800757f0  mov     eax, edi
0x1800757f2  test    r14, r14
0x1800757f5  jz      short loc_1800757FB
0x1800757f7  movzx   eax, word ptr [r14]
0x1800757fb  lea     r8d, [rax+2]
0x1800757ff  add     r8d, ecx
0x180075802  cmp     r8d, ecx
0x180075805  jb      loc_1800759C0
0x18007580b  mov     rax, rdi
0x18007580e  test    r14, r14
0x180075811  jz      short loc_180075817
0x180075813  movzx   eax, word ptr [r14]
0x180075817  mov     ecx, r8d
0x18007581a  add     rax, 2
0x18007581e  cmp     rcx, rax
0x180075821  jb      loc_1800759C0
0x180075827  mov     rbx, [rbp+3Fh+arg_20]
0x18007582b  mov     eax, edi
0x18007582d  mov     [rbp+3Fh+var_30], rcx
0x180075831  test    rbx, rbx
0x180075834  jz      short loc_180075839
0x180075836  movzx   eax, word ptr [rbx]
0x180075839  lea     edx, [rax+2]
0x18007583c  add     edx, r8d
0x18007583f  cmp     edx, r8d
0x180075842  jb      loc_1800759C0
0x180075848  mov     rcx, rdi
0x18007584b  test    rbx, rbx
0x18007584e  jz      short loc_180075853
0x180075850  movzx   ecx, word ptr [rbx]
0x180075853  add     rcx, 2
0x180075857  mov     eax, edx
0x180075859  cmp     rax, rcx
0x18007585c  jb      loc_1800759C0
0x180075862  mov     eax, edx
0x180075864  neg     eax
0x180075866  and     eax, 7
0x180075869  add     edx, eax
0x18007586b  mov     eax, edx
0x18007586d  mov     qword ptr [rbp+3Fh+var_70+8], rax
0x180075871  lea     r15d, [rdx+1]
0x180075875  cmp     r15d, edx
0x180075878  jb      loc_1800759C0
0x18007587e  cmp     r15d, 1
0x180075882  jb      loc_1800759C0
0x180075888  mov     edx, r15d; uBytes
0x18007588b  mov     ecx, 40h ; '@'; uFlags
0x180075890  call    cs:__imp_LocalAlloc
0x180075897  nop     dword ptr [rax+rax+00h]
0x18007589c  mov     rsi, rax
0x18007589f  test    rax, rax
0x1800758a2  jnz     short loc_1800758AC
0x1800758a4  lea     ebx, [rax+8]
0x1800758a7  jmp     loc_1800759C5
0x1800758ac  movaps  xmm0, [rbp+3Fh+var_70]
0x1800758b0  lea     r8, [rax+18h]
0x1800758b4  movaps  xmm1, [rbp+3Fh+var_60]
0x1800758b8  mov     rdx, r12
0x1800758bb  movups  xmmword ptr [rax], xmm0
0x1800758be  mov     rcx, rsi
0x1800758c1  movaps  xmm0, [rbp+3Fh+var_50]
0x1800758c5  movups  xmmword ptr [rax+10h], xmm1
0x1800758c9  movaps  xmm1, [rbp+3Fh+var_40]
0x1800758cd  movups  xmmword ptr [rax+20h], xmm0
0x1800758d1  movsd   xmm0, [rbp+3Fh+var_30]
0x1800758d6  movups  xmmword ptr [rax+30h], xmm1
0x1800758da  movsd   qword ptr [rax+40h], xmm0
0x1800758df  mov     dword ptr [rax], 2
0x1800758e5  mov     [rax+4], r13d
0x1800758e9  call    NdispUnicodeStringToVar
0x1800758ee  lea     r8, [rsi+28h]
0x1800758f2  mov     rdx, r14
0x1800758f5  mov     rcx, rsi
0x1800758f8  call    NdispUnicodeStringToVar
0x1800758fd  lea     r8, [rsi+38h]
0x180075901  mov     rdx, rbx
0x180075904  mov     rcx, rsi
0x180075907  call    NdispUnicodeStringToVar
0x18007590c  mov     rax, [rsi+8]
0x180075910  lea     rcx, aNdis_0; "\\\\.\\NDIS"
0x180075917  mov     [rsp+0B0h+hTemplateFile], rdi; hTemplateFile
0x18007591c  xor     r9d, r9d; lpSecurityAttributes
0x18007591f  mov     [rsi+10h], edi
0x180075922  xor     r8d, r8d; dwShareMode
0x180075925  mov     [rsp+0B0h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x180075929  mov     edx, 0C0000000h; dwDesiredAccess
0x18007592e  mov     [rsi+rax], dil
0x180075932  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18007593a  call    cs:__imp_CreateFileW
0x180075941  nop     dword ptr [rax+rax+00h]
0x180075946  mov     r14, rax
0x180075949  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007594d  jz      short loc_1800759A1
0x18007594f  mov     [rsp+0B0h+lpOverlapped], rdi; lpOverlapped
0x180075954  lea     rax, [rbp+3Fh+BytesReturned]
0x180075958  mov     [rsp+0B0h+hTemplateFile], rax; lpBytesReturned
0x18007595d  mov     r9d, r15d; nInBufferSize
0x180075960  mov     [rsp+0B0h+dwFlagsAndAttributes], edi; nOutBufferSize
0x180075964  mov     r8, rsi; lpInBuffer
0x180075967  mov     edx, 170008h; dwIoControlCode
0x18007596c  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rdi; lpOutBuffer
0x180075971  mov     rcx, r14; hDevice
0x180075974  call    cs:__imp_DeviceIoControl
0x18007597b  nop     dword ptr [rax+rax+00h]
0x180075980  mov     edi, eax
0x180075982  call    cs:__imp_GetLastError
0x180075989  nop     dword ptr [rax+rax+00h]
0x18007598e  mov     rcx, r14; hObject
0x180075991  mov     ebx, eax
0x180075993  call    cs:__imp_CloseHandle
0x18007599a  nop     dword ptr [rax+rax+00h]
0x18007599f  jmp     short loc_1800759AF
0x1800759a1  call    cs:__imp_GetLastError
0x1800759a8  nop     dword ptr [rax+rax+00h]
0x1800759ad  mov     ebx, eax
0x1800759af  mov     rcx, rsi; hMem
0x1800759b2  call    cs:__imp_LocalFree
0x1800759b9  nop     dword ptr [rax+rax+00h]
0x1800759be  jmp     short loc_1800759C5
0x1800759c0  mov     ebx, 57h ; 'W'
0x1800759c5  mov     ecx, ebx; dwErrCode
0x1800759c7  call    cs:__imp_SetLastError
0x1800759ce  nop     dword ptr [rax+rax+00h]
0x1800759d3  lea     r11, [rsp+0B0h+var_20]
0x1800759db  mov     eax, edi
0x1800759dd  mov     rbx, [r11+38h]
0x1800759e1  mov     rsi, [r11+40h]
0x1800759e5  mov     rdi, [r11+48h]
0x1800759e9  mov     rsp, r11
0x1800759ec  pop     r15
0x1800759ee  pop     r14
0x1800759f0  pop     r13
0x1800759f2  pop     r12
0x1800759f4  pop     rbp
0x1800759f5  retn
```
