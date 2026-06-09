# CRdpSettingsFileStream::DoOpenForWrite(ushort const *,int,int)

- ea: `0x1400a9bc0`
- end: `0x1400a9ea2`
- name: `?DoOpenForWrite@CRdpSettingsFileStream@@IEAAJPEBGHH@Z`
- size: `738`
- prototype: `__int64 __fastcall(CRdpSettingsFileStream *__hidden this, const unsigned __int16 *, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x1400aa620`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000d078`
- `0x14001e210`
- `0x1400a9bc0`
- `0x1400b3ef0`
- `0x140114010`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x1400a9d83`
- `KERNEL32!GetFileAttributesW` at `0x1400a9d83`
- `KERNEL32!CreateFileW` at `0x1400a9e50`
- `KERNEL32!CreateFileW` at `0x1400a9e50`
- `KERNEL32!GetLastError` at `0x1400a9db1`
- `KERNEL32!GetLastError` at `0x1400a9e60`
- `KERNEL32!GetLastError` at `0x1400a9db1`
- `KERNEL32!GetLastError` at `0x1400a9e60`

## pseudocode

```c
__int64 __fastcall CRdpSettingsFileStream::DoOpenForWrite(
        CRdpSettingsFileStream *this,
        const unsigned __int16 *a2,
        int a3,
        int a4)
{
  int v7; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v9; // edx
  const char *v10; // rcx
  const WCHAR *v11; // r14
  void *v12; // rax
  unsigned int v13; // eax
  unsigned int v14; // eax
  DWORD dwFlagsAndAttributes; // eax
  PVOID *v16; // rax
  DWORD LastError; // ebx
  unsigned int v18; // eax
  unsigned int v19; // eax
  HANDLE FileW; // rax
  signed int v21; // eax

  if ( a2 )
  {
    v7 = (*(__int64 (__fastcall **)(CRdpSettingsFileStream *))(*(_QWORD *)this + 96LL))(this);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 16;
        v10 = "Unable to initialize file name from moniker!";
LABEL_7:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v9,
          (unsigned int)WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)v10,
          v7);
        return (unsigned int)v7;
      }
      return (unsigned int)v7;
    }
    v11 = (const WCHAR *)((char *)this + 108);
  }
  else
  {
    v11 = (const WCHAR *)((char *)this + 108);
    if ( !*((_WORD *)this + 54) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids, v14);
      }
      return (unsigned int)-2147024773;
    }
    v7 = (*(__int64 (__fastcall **)(CRdpSettingsFileStream *))(*(_QWORD *)this + 64LL))(this);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 18;
        v10 = "Failed to close file stream!";
        goto LABEL_7;
      }
      return (unsigned int)v7;
    }
  }
  if ( !*((_QWORD *)this + 11) )
  {
    v12 = MIDL_user_allocate(0x800u);
    *((_QWORD *)this + 11) = v12;
    if ( !v12 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids, v13);
      }
      return (unsigned int)-2147024882;
    }
    *((_DWORD *)this + 24) = 2048;
  }
  dwFlagsAndAttributes = GetFileAttributesW(v11);
  if ( dwFlagsAndAttributes == -1 )
  {
    v16 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids,
          v18,
          LastError);
        v16 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 && *((_BYTE *)v16 + 25) >= 3u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          (unsigned int)WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids,
          v19,
          (__int64)v11);
      }
    }
    dwFlagsAndAttributes = 128;
  }
  FileW = CreateFileW(v11, 0x40000000u, a4 != 0 ? 3 : 1, 0, 2u, dwFlagsAndAttributes, 0);
  *((_QWORD *)this + 10) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v21 = GetLastError();
    v7 = v21;
    if ( v21 > 0 )
      return (unsigned __int16)v21 | 0x80070000;
  }
  else
  {
    *((_DWORD *)this + 19) = 1;
    *((_DWORD *)this + 158) = a3;
    *((_DWORD *)this + 159) = 1;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400a9bc0  push    rbx
0x1400a9bc2  push    rbp
0x1400a9bc3  push    rsi
0x1400a9bc4  push    rdi
0x1400a9bc5  push    r12
0x1400a9bc7  push    r13
0x1400a9bc9  push    r14
0x1400a9bcb  push    r15
0x1400a9bcd  sub     rsp, 48h
0x1400a9bd1  xor     r13d, r13d
0x1400a9bd4  mov     r12d, r9d
0x1400a9bd7  mov     r15d, r8d
0x1400a9bda  mov     rsi, rcx
0x1400a9bdd  test    rdx, rdx
0x1400a9be0  jz      loc_1400A9CCF
0x1400a9be6  mov     rax, [rcx]
0x1400a9be9  mov     rax, [rax+60h]
0x1400a9bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a9bf2  mov     edi, eax
0x1400a9bf4  test    eax, eax
0x1400a9bf6  jns     short loc_1400A9C5B
0x1400a9bf8  mov     rax, cs:WPP_GLOBAL_Control
0x1400a9bff  lea     rbp, WPP_GLOBAL_Control
0x1400a9c06  cmp     rax, rbp
0x1400a9c09  jz      loc_1400A9E8F
0x1400a9c0f  test    byte ptr [rax+1Ch], 8
0x1400a9c13  jz      loc_1400A9E8F
0x1400a9c19  cmp     byte ptr [rax+19h], 2
0x1400a9c1d  jb      loc_1400A9E8F
0x1400a9c23  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a9c28  lea     edx, [r13+10h]
0x1400a9c2c  lea     rcx, aUnableToInitia_0; "Unable to initialize file name from mon"...
0x1400a9c33  mov     [rsp+88h+dwFlagsAndAttributes], edi
0x1400a9c37  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400a9c3e  mov     qword ptr [rsp+88h+dwCreationDisposition], rcx
0x1400a9c43  mov     r9d, eax
0x1400a9c46  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9c4d  mov     rcx, [rcx+10h]
0x1400a9c51  call    WPP_SF_DsD
0x1400a9c56  jmp     loc_1400A9E8F
0x1400a9c5b  lea     r14, [rsi+6Ch]
0x1400a9c5f  cmp     [rsi+58h], r13
0x1400a9c63  jnz     loc_1400A9D80
0x1400a9c69  mov     ebx, 800h
0x1400a9c6e  mov     ecx, ebx; size
0x1400a9c70  call    MIDL_user_allocate
0x1400a9c75  mov     [rsi+58h], rax
0x1400a9c79  test    rax, rax
0x1400a9c7c  jnz     loc_1400A9D7D
0x1400a9c82  mov     rax, cs:WPP_GLOBAL_Control
0x1400a9c89  lea     rbp, WPP_GLOBAL_Control
0x1400a9c90  cmp     rax, rbp
0x1400a9c93  jz      short loc_1400A9CC5
0x1400a9c95  test    byte ptr [rax+1Ch], 1
0x1400a9c99  jz      short loc_1400A9CC5
0x1400a9c9b  cmp     byte ptr [rax+19h], 2
0x1400a9c9f  jb      short loc_1400A9CC5
0x1400a9ca1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a9ca6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9cad  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400a9cb4  mov     edx, 13h
0x1400a9cb9  mov     r9d, eax
0x1400a9cbc  mov     rcx, [rcx+10h]
0x1400a9cc0  call    WPP_SF_d
0x1400a9cc5  mov     edi, 8007000Eh
0x1400a9cca  jmp     loc_1400A9E8F
0x1400a9ccf  lea     r14, [rcx+6Ch]
0x1400a9cd3  cmp     [r14], r13w
0x1400a9cd7  jnz     short loc_1400A9D26
0x1400a9cd9  mov     rax, cs:WPP_GLOBAL_Control
0x1400a9ce0  lea     rbp, WPP_GLOBAL_Control
0x1400a9ce7  cmp     rax, rbp
0x1400a9cea  jz      short loc_1400A9D1C
0x1400a9cec  test    byte ptr [rax+1Ch], 1
0x1400a9cf0  jz      short loc_1400A9D1C
0x1400a9cf2  cmp     byte ptr [rax+19h], 2
0x1400a9cf6  jb      short loc_1400A9D1C
0x1400a9cf8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a9cfd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9d04  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400a9d0b  mov     edx, 11h
0x1400a9d10  mov     r9d, eax
0x1400a9d13  mov     rcx, [rcx+10h]
0x1400a9d17  call    WPP_SF_d
0x1400a9d1c  mov     edi, 8007007Bh
0x1400a9d21  jmp     loc_1400A9E8F
0x1400a9d26  mov     rax, [rcx]
0x1400a9d29  mov     rax, [rax+40h]
0x1400a9d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a9d32  mov     edi, eax
0x1400a9d34  test    eax, eax
0x1400a9d36  jns     loc_1400A9C5F
0x1400a9d3c  mov     rax, cs:WPP_GLOBAL_Control
0x1400a9d43  lea     rbp, WPP_GLOBAL_Control
0x1400a9d4a  cmp     rax, rbp
0x1400a9d4d  jz      loc_1400A9E8F
0x1400a9d53  test    byte ptr [rax+1Ch], 8
0x1400a9d57  jz      loc_1400A9E8F
0x1400a9d5d  cmp     byte ptr [rax+19h], 2
0x1400a9d61  jb      loc_1400A9E8F
0x1400a9d67  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a9d6c  mov     edx, 12h
0x1400a9d71  lea     rcx, aFailedToCloseF; "Failed to close file stream!"
0x1400a9d78  jmp     loc_1400A9C33
0x1400a9d7d  mov     [rsi+60h], ebx
0x1400a9d80  mov     rcx, r14; lpFileName
0x1400a9d83  call    cs:__imp_GetFileAttributesW
0x1400a9d89  cmp     eax, 0FFFFFFFFh
0x1400a9d8c  jnz     loc_1400A9E27
0x1400a9d92  mov     rax, cs:WPP_GLOBAL_Control
0x1400a9d99  lea     rbp, WPP_GLOBAL_Control
0x1400a9da0  cmp     rax, rbp
0x1400a9da3  jz      short loc_1400A9E22
0x1400a9da5  test    byte ptr [rax+1Ch], 1
0x1400a9da9  jz      short loc_1400A9DE8
0x1400a9dab  cmp     byte ptr [rax+19h], 2
0x1400a9daf  jb      short loc_1400A9DE8
0x1400a9db1  call    cs:__imp_GetLastError
0x1400a9db7  mov     ebx, eax
0x1400a9db9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a9dbe  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9dc5  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400a9dcc  mov     edx, 14h
0x1400a9dd1  mov     [rsp+88h+dwCreationDisposition], ebx
0x1400a9dd5  mov     r9d, eax
0x1400a9dd8  mov     rcx, [rcx+10h]
0x1400a9ddc  call    WPP_SF_Dd
0x1400a9de1  mov     rax, cs:WPP_GLOBAL_Control
0x1400a9de8  cmp     rax, rbp
0x1400a9deb  jz      short loc_1400A9E22
0x1400a9ded  test    byte ptr [rax+1Ch], 1
0x1400a9df1  jz      short loc_1400A9E22
0x1400a9df3  cmp     byte ptr [rax+19h], 3
0x1400a9df7  jb      short loc_1400A9E22
0x1400a9df9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a9dfe  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a9e05  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400a9e0c  mov     edx, 15h
0x1400a9e11  mov     qword ptr [rsp+88h+dwCreationDisposition], r14
0x1400a9e16  mov     r9d, eax
0x1400a9e19  mov     rcx, [rcx+10h]
0x1400a9e1d  call    WPP_SF_DS
0x1400a9e22  mov     eax, 80h
0x1400a9e27  mov     [rsp+88h+hTemplateFile], r13; hTemplateFile
0x1400a9e2c  neg     r12d
0x1400a9e2f  mov     [rsp+88h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x1400a9e33  mov     edx, 40000000h; dwDesiredAccess
0x1400a9e38  sbb     r8d, r8d
0x1400a9e3b  mov     [rsp+88h+dwCreationDisposition], 2; dwCreationDisposition
0x1400a9e43  and     r8d, 2
0x1400a9e47  xor     r9d, r9d; lpSecurityAttributes
0x1400a9e4a  inc     r8d; dwShareMode
0x1400a9e4d  mov     rcx, r14; lpFileName
0x1400a9e50  call    cs:__imp_CreateFileW
0x1400a9e56  mov     [rsi+50h], rax
0x1400a9e5a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400a9e5e  jnz     short loc_1400A9E77
0x1400a9e60  call    cs:__imp_GetLastError
0x1400a9e66  mov     edi, eax
0x1400a9e68  test    eax, eax
0x1400a9e6a  jle     short loc_1400A9E8F
0x1400a9e6c  movzx   edi, ax
0x1400a9e6f  or      edi, 80070000h
0x1400a9e75  jmp     short loc_1400A9E8F
0x1400a9e77  mov     dword ptr [rsi+4Ch], 1
0x1400a9e7e  mov     [rsi+278h], r15d
0x1400a9e85  mov     dword ptr [rsi+27Ch], 1
0x1400a9e8f  mov     eax, edi
0x1400a9e91  add     rsp, 48h
0x1400a9e95  pop     r15
0x1400a9e97  pop     r14
0x1400a9e99  pop     r13
0x1400a9e9b  pop     r12
0x1400a9e9d  pop     rdi
0x1400a9e9e  pop     rsi
0x1400a9e9f  pop     rbp
0x1400a9ea0  pop     rbx
0x1400a9ea1  retn
```
