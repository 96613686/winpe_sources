# CRdpSettingsFileStream::DoOpenForWrite(ushort const *,int,int)

- ea: `0x1400a7a50`
- end: `0x1400a7d32`
- name: `?DoOpenForWrite@CRdpSettingsFileStream@@IEAAJPEBGHH@Z`
- size: `738`
- prototype: `__int64 __fastcall(CRdpSettingsFileStream *__hidden this, const unsigned __int16 *, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x1400a84b0`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000d078`
- `0x14001e210`
- `0x1400a7a50`
- `0x1400b1d80`
- `0x140112010`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x1400a7c13`
- `KERNEL32!GetFileAttributesW` at `0x1400a7c13`
- `KERNEL32!CreateFileW` at `0x1400a7ce0`
- `KERNEL32!CreateFileW` at `0x1400a7ce0`
- `KERNEL32!GetLastError` at `0x1400a7c41`
- `KERNEL32!GetLastError` at `0x1400a7cf0`
- `KERNEL32!GetLastError` at `0x1400a7c41`
- `KERNEL32!GetLastError` at `0x1400a7cf0`

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
0x1400a7a50  push    rbx
0x1400a7a52  push    rbp
0x1400a7a53  push    rsi
0x1400a7a54  push    rdi
0x1400a7a55  push    r12
0x1400a7a57  push    r13
0x1400a7a59  push    r14
0x1400a7a5b  push    r15
0x1400a7a5d  sub     rsp, 48h
0x1400a7a61  xor     r13d, r13d
0x1400a7a64  mov     r12d, r9d
0x1400a7a67  mov     r15d, r8d
0x1400a7a6a  mov     rsi, rcx
0x1400a7a6d  test    rdx, rdx
0x1400a7a70  jz      loc_1400A7B5F
0x1400a7a76  mov     rax, [rcx]
0x1400a7a79  mov     rax, [rax+60h]
0x1400a7a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a7a82  mov     edi, eax
0x1400a7a84  test    eax, eax
0x1400a7a86  jns     short loc_1400A7AEB
0x1400a7a88  mov     rax, cs:WPP_GLOBAL_Control
0x1400a7a8f  lea     rbp, WPP_GLOBAL_Control
0x1400a7a96  cmp     rax, rbp
0x1400a7a99  jz      loc_1400A7D1F
0x1400a7a9f  test    byte ptr [rax+1Ch], 8
0x1400a7aa3  jz      loc_1400A7D1F
0x1400a7aa9  cmp     byte ptr [rax+19h], 2
0x1400a7aad  jb      loc_1400A7D1F
0x1400a7ab3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a7ab8  lea     edx, [r13+10h]
0x1400a7abc  lea     rcx, aUnableToInitia_0; "Unable to initialize file name from mon"...
0x1400a7ac3  mov     [rsp+88h+dwFlagsAndAttributes], edi
0x1400a7ac7  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400a7ace  mov     qword ptr [rsp+88h+dwCreationDisposition], rcx
0x1400a7ad3  mov     r9d, eax
0x1400a7ad6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7add  mov     rcx, [rcx+10h]
0x1400a7ae1  call    WPP_SF_DsD
0x1400a7ae6  jmp     loc_1400A7D1F
0x1400a7aeb  lea     r14, [rsi+6Ch]
0x1400a7aef  cmp     [rsi+58h], r13
0x1400a7af3  jnz     loc_1400A7C10
0x1400a7af9  mov     ebx, 800h
0x1400a7afe  mov     ecx, ebx; size
0x1400a7b00  call    MIDL_user_allocate
0x1400a7b05  mov     [rsi+58h], rax
0x1400a7b09  test    rax, rax
0x1400a7b0c  jnz     loc_1400A7C0D
0x1400a7b12  mov     rax, cs:WPP_GLOBAL_Control
0x1400a7b19  lea     rbp, WPP_GLOBAL_Control
0x1400a7b20  cmp     rax, rbp
0x1400a7b23  jz      short loc_1400A7B55
0x1400a7b25  test    byte ptr [rax+1Ch], 1
0x1400a7b29  jz      short loc_1400A7B55
0x1400a7b2b  cmp     byte ptr [rax+19h], 2
0x1400a7b2f  jb      short loc_1400A7B55
0x1400a7b31  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a7b36  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7b3d  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400a7b44  mov     edx, 13h
0x1400a7b49  mov     r9d, eax
0x1400a7b4c  mov     rcx, [rcx+10h]
0x1400a7b50  call    WPP_SF_d
0x1400a7b55  mov     edi, 8007000Eh
0x1400a7b5a  jmp     loc_1400A7D1F
0x1400a7b5f  lea     r14, [rcx+6Ch]
0x1400a7b63  cmp     [r14], r13w
0x1400a7b67  jnz     short loc_1400A7BB6
0x1400a7b69  mov     rax, cs:WPP_GLOBAL_Control
0x1400a7b70  lea     rbp, WPP_GLOBAL_Control
0x1400a7b77  cmp     rax, rbp
0x1400a7b7a  jz      short loc_1400A7BAC
0x1400a7b7c  test    byte ptr [rax+1Ch], 1
0x1400a7b80  jz      short loc_1400A7BAC
0x1400a7b82  cmp     byte ptr [rax+19h], 2
0x1400a7b86  jb      short loc_1400A7BAC
0x1400a7b88  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a7b8d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7b94  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400a7b9b  mov     edx, 11h
0x1400a7ba0  mov     r9d, eax
0x1400a7ba3  mov     rcx, [rcx+10h]
0x1400a7ba7  call    WPP_SF_d
0x1400a7bac  mov     edi, 8007007Bh
0x1400a7bb1  jmp     loc_1400A7D1F
0x1400a7bb6  mov     rax, [rcx]
0x1400a7bb9  mov     rax, [rax+40h]
0x1400a7bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a7bc2  mov     edi, eax
0x1400a7bc4  test    eax, eax
0x1400a7bc6  jns     loc_1400A7AEF
0x1400a7bcc  mov     rax, cs:WPP_GLOBAL_Control
0x1400a7bd3  lea     rbp, WPP_GLOBAL_Control
0x1400a7bda  cmp     rax, rbp
0x1400a7bdd  jz      loc_1400A7D1F
0x1400a7be3  test    byte ptr [rax+1Ch], 8
0x1400a7be7  jz      loc_1400A7D1F
0x1400a7bed  cmp     byte ptr [rax+19h], 2
0x1400a7bf1  jb      loc_1400A7D1F
0x1400a7bf7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a7bfc  mov     edx, 12h
0x1400a7c01  lea     rcx, aFailedToCloseF; "Failed to close file stream!"
0x1400a7c08  jmp     loc_1400A7AC3
0x1400a7c0d  mov     [rsi+60h], ebx
0x1400a7c10  mov     rcx, r14; lpFileName
0x1400a7c13  call    cs:__imp_GetFileAttributesW
0x1400a7c19  cmp     eax, 0FFFFFFFFh
0x1400a7c1c  jnz     loc_1400A7CB7
0x1400a7c22  mov     rax, cs:WPP_GLOBAL_Control
0x1400a7c29  lea     rbp, WPP_GLOBAL_Control
0x1400a7c30  cmp     rax, rbp
0x1400a7c33  jz      short loc_1400A7CB2
0x1400a7c35  test    byte ptr [rax+1Ch], 1
0x1400a7c39  jz      short loc_1400A7C78
0x1400a7c3b  cmp     byte ptr [rax+19h], 2
0x1400a7c3f  jb      short loc_1400A7C78
0x1400a7c41  call    cs:__imp_GetLastError
0x1400a7c47  mov     ebx, eax
0x1400a7c49  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a7c4e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7c55  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400a7c5c  mov     edx, 14h
0x1400a7c61  mov     [rsp+88h+dwCreationDisposition], ebx
0x1400a7c65  mov     r9d, eax
0x1400a7c68  mov     rcx, [rcx+10h]
0x1400a7c6c  call    WPP_SF_Dd
0x1400a7c71  mov     rax, cs:WPP_GLOBAL_Control
0x1400a7c78  cmp     rax, rbp
0x1400a7c7b  jz      short loc_1400A7CB2
0x1400a7c7d  test    byte ptr [rax+1Ch], 1
0x1400a7c81  jz      short loc_1400A7CB2
0x1400a7c83  cmp     byte ptr [rax+19h], 3
0x1400a7c87  jb      short loc_1400A7CB2
0x1400a7c89  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a7c8e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7c95  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x1400a7c9c  mov     edx, 15h
0x1400a7ca1  mov     qword ptr [rsp+88h+dwCreationDisposition], r14
0x1400a7ca6  mov     r9d, eax
0x1400a7ca9  mov     rcx, [rcx+10h]
0x1400a7cad  call    WPP_SF_DS
0x1400a7cb2  mov     eax, 80h
0x1400a7cb7  mov     [rsp+88h+hTemplateFile], r13; hTemplateFile
0x1400a7cbc  neg     r12d
0x1400a7cbf  mov     [rsp+88h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x1400a7cc3  mov     edx, 40000000h; dwDesiredAccess
0x1400a7cc8  sbb     r8d, r8d
0x1400a7ccb  mov     [rsp+88h+dwCreationDisposition], 2; dwCreationDisposition
0x1400a7cd3  and     r8d, 2
0x1400a7cd7  xor     r9d, r9d; lpSecurityAttributes
0x1400a7cda  inc     r8d; dwShareMode
0x1400a7cdd  mov     rcx, r14; lpFileName
0x1400a7ce0  call    cs:__imp_CreateFileW
0x1400a7ce6  mov     [rsi+50h], rax
0x1400a7cea  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400a7cee  jnz     short loc_1400A7D07
0x1400a7cf0  call    cs:__imp_GetLastError
0x1400a7cf6  mov     edi, eax
0x1400a7cf8  test    eax, eax
0x1400a7cfa  jle     short loc_1400A7D1F
0x1400a7cfc  movzx   edi, ax
0x1400a7cff  or      edi, 80070000h
0x1400a7d05  jmp     short loc_1400A7D1F
0x1400a7d07  mov     dword ptr [rsi+4Ch], 1
0x1400a7d0e  mov     [rsi+278h], r15d
0x1400a7d15  mov     dword ptr [rsi+27Ch], 1
0x1400a7d1f  mov     eax, edi
0x1400a7d21  add     rsp, 48h
0x1400a7d25  pop     r15
0x1400a7d27  pop     r14
0x1400a7d29  pop     r13
0x1400a7d2b  pop     r12
0x1400a7d2d  pop     rdi
0x1400a7d2e  pop     rsi
0x1400a7d2f  pop     rbp
0x1400a7d30  pop     rbx
0x1400a7d31  retn
```
