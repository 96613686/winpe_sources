# CEnhancedStorageSilo::SendCommand(uchar,uchar *,ulong,uchar *,ulong *)

- ea: `0x1800082b0`
- end: `0x1800084c6`
- name: `?SendCommand@CEnhancedStorageSilo@@UEAAJEPEAEK0PEAK@Z`
- size: `534`
- prototype: `__int64 __fastcall(CEnhancedStorageSilo *this, __int64, unsigned __int8 *, unsigned int, unsigned __int8 *lpOutBuffer, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000124c`
- `0x180001258`
- `0x180003ce0`
- `0x180003df0`
- `0x180003ed0`
- `0x1800082b0`
- `0x180008538`
- `0x18000c4b6`
- `0x18000c4f0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180008400`
- `KERNEL32!CreateFileW` at `0x180008400`
- `KERNEL32!GetLastError` at `0x18000840f`
- `KERNEL32!GetLastError` at `0x180008459`
- `KERNEL32!GetLastError` at `0x18000840f`
- `KERNEL32!GetLastError` at `0x180008459`
- `KERNEL32!DeviceIoControl` at `0x18000844f`
- `KERNEL32!DeviceIoControl` at `0x18000844f`
- `KERNEL32!CloseHandle` at `0x180008488`
- `KERNEL32!CloseHandle` at `0x180008488`

## string_xrefs

- `0x18000834a`: `CEnhancedStorageSilo::SendCommand`
- `0x18000837a`: `pbCommandBuffer`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageSilo::SendCommand(
        CEnhancedStorageSilo *this,
        __int64 a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 *lpOutBuffer,
        unsigned int *a6)
{
  size_t v7; // rsi
  char v8; // r13
  unsigned int v9; // ebx
  DWORD v10; // r14d
  char *v11; // rdi
  HANDLE FileW; // rsi
  signed int LastError; // eax
  signed int v14; // eax
  int v16; // [rsp+50h] [rbp-B0h] BYREF
  DWORD BytesReturned; // [rsp+54h] [rbp-ACh] BYREF
  CEnhancedStorageSilo *v18; // [rsp+58h] [rbp-A8h]
  _BYTE v19[272]; // [rsp+60h] [rbp-A0h] BYREF

  v7 = a4;
  v8 = a2;
  v18 = this;
  v16 = 0;
  BytesReturned = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_Dqdqqd(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, (unsigned __int8)a2, a3, a4, lpOutBuffer, a6, *a6);
  CESTTrackFn::CESTTrackFn((CESTTrackFn *)v19, "CEnhancedStorageSilo::SendCommand", &v16);
  if ( a3 )
  {
    v10 = v7 + 12;
    v11 = (char *)operator new[]((unsigned int)(v7 + 12));
    if ( v11 )
    {
      *v11 = *((_BYTE *)v18 + 72);
      v11[1] = v8;
      *((_DWORD *)v11 + 1) = v7;
      memcpy_0(v11 + 8, a3, v7);
      FileW = CreateFileW(*((LPCWSTR *)v18 + 8), 0x80000000, 3u, 0, 3u, 0, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v16 = LastError;
      }
      else
      {
        if ( DeviceIoControl(FileW, 0x2D140Cu, v11, v10, lpOutBuffer, *a6, &BytesReturned, 0) )
        {
          if ( BytesReturned <= *a6 )
            *a6 = BytesReturned;
          else
            v16 = -2147024888;
        }
        else
        {
          v14 = GetLastError();
          if ( v14 > 0 )
            v14 = (unsigned __int16)v14 | 0x80070000;
          v16 = v14;
        }
        CloseHandle(FileW);
      }
      operator delete[](v11);
      v9 = v16;
    }
    else
    {
      v9 = -2147024882;
      v16 = -2147024882;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids,
        "pbCommandBuffer");
    v9 = -2147024809;
  }
  CESTTrackFn::~CESTTrackFn((CESTTrackFn *)v19);
  return v9;
}

```

## disassembly

```asm
0x1800082b0  push    rbp
0x1800082b2  push    rbx
0x1800082b3  push    rsi
0x1800082b4  push    rdi
0x1800082b5  push    r12
0x1800082b7  push    r13
0x1800082b9  push    r14
0x1800082bb  push    r15
0x1800082bd  lea     rbp, [rsp-88h]
0x1800082c5  sub     rsp, 188h
0x1800082cc  mov     rax, cs:__security_cookie
0x1800082d3  xor     rax, rsp
0x1800082d6  mov     [rbp+0C0h+var_50], rax
0x1800082da  mov     r12, [rbp+0C0h+lpOutBuffer]
0x1800082e1  mov     r15, r8
0x1800082e4  mov     rbx, [rbp+0C0h+arg_28]
0x1800082eb  mov     esi, r9d
0x1800082ee  movzx   r13d, dl
0x1800082f2  mov     [rsp+1C0h+var_168], rcx
0x1800082f7  mov     [rsp+1C0h+var_170], 0
0x1800082ff  mov     [rsp+1C0h+BytesReturned], 0
0x180008307  mov     rcx, cs:WPP_GLOBAL_Control
0x18000830e  lea     rdi, WPP_GLOBAL_Control
0x180008315  cmp     rcx, rdi
0x180008318  jz      short loc_180008345
0x18000831a  test    byte ptr [rcx+1Ch], 10h
0x18000831e  jz      short loc_180008345
0x180008320  mov     eax, [rbx]
0x180008322  mov     r9d, r13d
0x180008325  mov     rcx, [rcx+10h]
0x180008329  mov     [rsp+1C0h+var_180], eax
0x18000832d  mov     [rsp+1C0h+lpOverlapped], rbx
0x180008332  mov     [rsp+1C0h+hTemplateFile], r12
0x180008337  mov     [rsp+1C0h+dwFlagsAndAttributes], esi
0x18000833b  mov     qword ptr [rsp+1C0h+dwCreationDisposition], r8
0x180008340  call    WPP_SF_Dqdqqd
0x180008345  lea     r8, [rsp+1C0h+var_170]; int *
0x18000834a  lea     rdx, aCenhancedstora_18; "CEnhancedStorageSilo::SendCommand"
0x180008351  lea     rcx, [rsp+1C0h+var_160]; this
0x180008356  call    ??0CESTTrackFn@@QEAA@PEBDPEAJ@Z; CESTTrackFn::CESTTrackFn(char const *,long *)
0x18000835b  test    r15, r15
0x18000835e  jnz     short loc_180008397
0x180008360  mov     rcx, cs:WPP_GLOBAL_Control
0x180008367  cmp     rcx, rdi
0x18000836a  jz      short loc_18000838D
0x18000836c  test    byte ptr [rcx+1Ch], 2
0x180008370  jz      short loc_18000838D
0x180008372  mov     rcx, [rcx+10h]
0x180008376  lea     edx, [r15+32h]
0x18000837a  lea     r9, aPbcommandbuffe; "pbCommandBuffer"
0x180008381  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x180008388  call    WPP_SF_s
0x18000838d  mov     ebx, 80070057h
0x180008392  jmp     loc_18000849A
0x180008397  lea     r14d, [rsi+0Ch]
0x18000839b  mov     ecx, r14d; unsigned __int64
0x18000839e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800083a3  mov     rdi, rax
0x1800083a6  test    rax, rax
0x1800083a9  jnz     short loc_1800083B9
0x1800083ab  mov     ebx, 8007000Eh
0x1800083b0  mov     [rsp+1C0h+var_170], ebx
0x1800083b4  jmp     loc_18000849A
0x1800083b9  mov     rax, [rsp+1C0h+var_168]
0x1800083be  lea     rcx, [rdi+8]; void *
0x1800083c2  mov     r8, rsi; Size
0x1800083c5  mov     rdx, r15; Src
0x1800083c8  mov     al, [rax+48h]
0x1800083cb  mov     [rdi], al
0x1800083cd  mov     [rdi+1], r13b
0x1800083d1  mov     [rdi+4], esi
0x1800083d4  call    memcpy_0
0x1800083d9  mov     rax, [rsp+1C0h+var_168]
0x1800083de  xor     r15d, r15d
0x1800083e1  mov     [rsp+1C0h+hTemplateFile], r15; hTemplateFile
0x1800083e6  xor     r9d, r9d; lpSecurityAttributes
0x1800083e9  mov     [rsp+1C0h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x1800083ee  mov     edx, 80000000h; dwDesiredAccess
0x1800083f3  mov     rcx, [rax+40h]; lpFileName
0x1800083f7  lea     r8d, [r15+3]; dwShareMode
0x1800083fb  mov     [rsp+1C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x180008400  call    cs:__imp_CreateFileW
0x180008406  mov     rsi, rax
0x180008409  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000840d  jnz     short loc_180008427
0x18000840f  call    cs:__imp_GetLastError
0x180008415  test    eax, eax
0x180008417  jle     short loc_180008421
0x180008419  movzx   eax, ax
0x18000841c  or      eax, 80070000h
0x180008421  mov     [rsp+1C0h+var_170], eax
0x180008425  jmp     short loc_18000848E
0x180008427  lea     rax, [rsp+1C0h+BytesReturned]
0x18000842c  mov     [rsp+1C0h+lpOverlapped], r15; lpOverlapped
0x180008431  mov     [rsp+1C0h+hTemplateFile], rax; lpBytesReturned
0x180008436  mov     r9d, r14d; nInBufferSize
0x180008439  mov     eax, [rbx]
0x18000843b  mov     r8, rdi; lpInBuffer
0x18000843e  mov     [rsp+1C0h+dwFlagsAndAttributes], eax; nOutBufferSize
0x180008442  mov     edx, 2D140Ch; dwIoControlCode
0x180008447  mov     rcx, rsi; hDevice
0x18000844a  mov     qword ptr [rsp+1C0h+dwCreationDisposition], r12; lpOutBuffer
0x18000844f  call    cs:__imp_DeviceIoControl
0x180008455  test    eax, eax
0x180008457  jnz     short loc_180008471
0x180008459  call    cs:__imp_GetLastError
0x18000845f  test    eax, eax
0x180008461  jle     short loc_18000846B
0x180008463  movzx   eax, ax
0x180008466  or      eax, 80070000h
0x18000846b  mov     [rsp+1C0h+var_170], eax
0x18000846f  jmp     short loc_180008485
0x180008471  mov     eax, [rsp+1C0h+BytesReturned]
0x180008475  cmp     eax, [rbx]
0x180008477  jbe     short loc_180008483
0x180008479  mov     [rsp+1C0h+var_170], 80070008h
0x180008481  jmp     short loc_180008485
0x180008483  mov     [rbx], eax
0x180008485  mov     rcx, rsi; hObject
0x180008488  call    cs:__imp_CloseHandle
0x18000848e  mov     rcx, rdi; Block
0x180008491  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180008496  mov     ebx, [rsp+1C0h+var_170]
0x18000849a  lea     rcx, [rsp+1C0h+var_160]; this
0x18000849f  call    ??1CESTTrackFn@@QEAA@XZ; CESTTrackFn::~CESTTrackFn(void)
0x1800084a4  mov     eax, ebx
0x1800084a6  mov     rcx, [rbp+0C0h+var_50]
0x1800084aa  xor     rcx, rsp; StackCookie
0x1800084ad  call    __security_check_cookie
0x1800084b2  add     rsp, 188h
0x1800084b9  pop     r15
0x1800084bb  pop     r14
0x1800084bd  pop     r13
0x1800084bf  pop     r12
0x1800084c1  pop     rdi
0x1800084c2  pop     rsi
0x1800084c3  pop     rbx
0x1800084c4  pop     rbp
0x1800084c5  retn
```
