# GetNewFile(CRATicket *,RECV_ENTRY *,long)

- ea: `0x140047b24`
- end: `0x140047d08`
- name: `?GetNewFile@@YAJPEAVCRATicket@@PEAURECV_ENTRY@@J@Z`
- size: `484`
- prototype: `__int64 __fastcall(struct CRATicket *, struct RECV_ENTRY *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140048d20`
- `0x140048e34`

## callees

- `0x140007fc4`
- `0x1400080fc`
- `0x140047b24`
- `0x14004ad80`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140047ca0`
- `KERNEL32!CreateFileW` at `0x140047ca0`
- `KERNEL32!GetSystemTime` at `0x140047b8f`
- `KERNEL32!GetSystemTime` at `0x140047b8f`
- `msvcrt!malloc` at `0x140047b68`
- `msvcrt!malloc` at `0x140047b68`
- `msvcrt!free` at `0x140047cc4`
- `msvcrt!free` at `0x140047cc4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetNewFile(struct CRATicket *a1, struct RECV_ENTRY *a2, unsigned int a3)
{
  void *v6; // rax
  signed int v7; // ebx
  unsigned __int16 *v8; // rcx
  unsigned __int16 *v9; // r9
  __int64 v10; // rax
  __int64 v11; // r8
  unsigned __int16 *v12; // rcx
  const WCHAR *v13; // rcx
  HANDLE FileW; // rax
  void *v15; // rcx
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v18[264]; // [rsp+70h] [rbp-90h] BYREF

  SystemTime = 0;
  v6 = malloc(0x20Au);
  *((_QWORD *)a2 + 2) = v6;
  if ( v6 )
  {
    GetSystemTime(&SystemTime);
    v8 = (unsigned __int16 *)*((_QWORD *)a1 + 65);
    v9 = v18;
    v10 = 2147483646;
    v11 = 261;
    do
    {
      if ( !v10 )
        break;
      if ( !*v8 )
        break;
      *v9++ = *v8++;
      --v10;
      --v11;
    }
    while ( v11 );
    v12 = v9 - 1;
    v7 = v11 == 0 ? 0x8007007A : 0;
    if ( v11 )
      v12 = v9;
    *v12 = 0;
    if ( v11 )
    {
      v7 = StringCchCatW(v18, 0x105u, L"\\ra_ftp_%d_%d_%d_%d_%d_%d_%d_%d");
      if ( v7 >= 0 )
      {
        v7 = StringCchPrintfW(
               *((unsigned __int16 **)a2 + 2),
               0x104u,
               v18,
               a3,
               SystemTime.wYear,
               SystemTime.wMonth,
               SystemTime.wDay,
               SystemTime.wHour,
               SystemTime.wMinute,
               SystemTime.wSecond,
               SystemTime.wMilliseconds);
        if ( v7 >= 0 )
        {
          v13 = (const WCHAR *)*((_QWORD *)a2 + 2);
          *((_QWORD *)a2 + 3) = 0;
          FileW = CreateFileW(v13, 0x40000000u, 0, 0, 2u, 0, 0);
          *((_QWORD *)a2 + 3) = FileW;
          if ( FileW != (HANDLE)-1LL )
            return (unsigned int)v7;
          v7 = -2147467259;
        }
      }
    }
  }
  else
  {
    v7 = -2147024882;
  }
  v15 = (void *)*((_QWORD *)a2 + 2);
  if ( v15 )
  {
    free(v15);
    *((_QWORD *)a2 + 2) = 0;
  }
  if ( *((_QWORD *)a2 + 3) )
    *((_QWORD *)a2 + 3) = 0;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140047b24  mov     [rsp-8+arg_0], rbx
0x140047b29  mov     [rsp-8+arg_18], rsi
0x140047b2e  push    rbp
0x140047b2f  push    rdi
0x140047b30  push    r14
0x140047b32  lea     rbp, [rsp-190h]
0x140047b3a  sub     rsp, 290h
0x140047b41  mov     rax, cs:__security_cookie
0x140047b48  xor     rax, rsp
0x140047b4b  mov     [rbp+1A0h+var_20], rax
0x140047b52  mov     rbx, rcx
0x140047b55  xorps   xmm0, xmm0
0x140047b58  mov     ecx, 20Ah; Size
0x140047b5d  mov     esi, r8d
0x140047b60  movups  xmmword ptr [rsp+2A0h+SystemTime.wYear], xmm0
0x140047b65  mov     rdi, rdx
0x140047b68  call    cs:__imp_malloc
0x140047b6f  nop     dword ptr [rax+rax+00h]
0x140047b74  xor     r14d, r14d
0x140047b77  mov     [rdi+10h], rax
0x140047b7b  test    rax, rax
0x140047b7e  jnz     short loc_140047B8A
0x140047b80  mov     ebx, 8007000Eh
0x140047b85  jmp     loc_140047CBB
0x140047b8a  lea     rcx, [rsp+2A0h+SystemTime]; lpSystemTime
0x140047b8f  call    cs:__imp_GetSystemTime
0x140047b96  nop     dword ptr [rax+rax+00h]
0x140047b9b  mov     rcx, [rbx+208h]
0x140047ba2  lea     r9, [rsp+2A0h+var_230]
0x140047ba7  mov     r10d, 105h
0x140047bad  mov     eax, 7FFFFFFEh
0x140047bb2  mov     r8d, r10d
0x140047bb5  test    rax, rax
0x140047bb8  jz      short loc_140047BD7
0x140047bba  movzx   edx, word ptr [rcx]
0x140047bbd  test    dx, dx
0x140047bc0  jz      short loc_140047BD7
0x140047bc2  mov     [r9], dx
0x140047bc6  add     rcx, 2
0x140047bca  add     r9, 2
0x140047bce  dec     rax
0x140047bd1  sub     r8, 1
0x140047bd5  jnz     short loc_140047BB5
0x140047bd7  mov     rax, r8
0x140047bda  lea     rcx, [r9-2]
0x140047bde  neg     rax
0x140047be1  sbb     ebx, ebx
0x140047be3  not     ebx
0x140047be5  and     ebx, 8007007Ah
0x140047beb  test    r8, r8
0x140047bee  cmovnz  rcx, r9
0x140047bf2  mov     [rcx], r14w
0x140047bf6  jz      loc_140047CBB
0x140047bfc  lea     r8, aRaFtpDDDDDDDD; "\\ra_ftp_%d_%d_%d_%d_%d_%d_%d_%d"
0x140047c03  mov     rdx, r10; unsigned __int64
0x140047c06  lea     rcx, [rsp+2A0h+var_230]; unsigned __int16 *
0x140047c0b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140047c10  mov     ebx, eax
0x140047c12  test    eax, eax
0x140047c14  js      loc_140047CBB
0x140047c1a  movzx   ecx, [rsp+2A0h+SystemTime.wSecond]
0x140047c1f  mov     r9d, esi
0x140047c22  movzx   edx, [rsp+2A0h+SystemTime.wMinute]
0x140047c27  movzx   r8d, [rsp+2A0h+SystemTime.wHour]
0x140047c2d  movzx   eax, [rsp+2A0h+SystemTime.wMilliseconds]
0x140047c32  movzx   r10d, [rsp+2A0h+SystemTime.wDay]
0x140047c38  movzx   r11d, [rsp+2A0h+SystemTime.wMonth]
0x140047c3e  movzx   ebx, [rsp+2A0h+SystemTime.wYear]
0x140047c43  mov     [rsp+2A0h+var_250], eax
0x140047c47  mov     [rsp+2A0h+var_258], ecx
0x140047c4b  mov     rcx, [rdi+10h]; unsigned __int16 *
0x140047c4f  mov     [rsp+2A0h+var_260], edx
0x140047c53  mov     edx, 104h; unsigned __int64
0x140047c58  mov     [rsp+2A0h+var_268], r8d
0x140047c5d  lea     r8, [rsp+2A0h+var_230]; unsigned __int16 *
0x140047c62  mov     dword ptr [rsp+2A0h+hTemplateFile], r10d
0x140047c67  mov     [rsp+2A0h+dwFlagsAndAttributes], r11d
0x140047c6c  mov     [rsp+2A0h+dwCreationDisposition], ebx
0x140047c70  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140047c75  mov     ebx, eax
0x140047c77  test    eax, eax
0x140047c79  js      short loc_140047CBB
0x140047c7b  mov     rcx, [rdi+10h]; lpFileName
0x140047c7f  xor     r9d, r9d; lpSecurityAttributes
0x140047c82  mov     [rsp+2A0h+hTemplateFile], r14; hTemplateFile
0x140047c87  xor     r8d, r8d; dwShareMode
0x140047c8a  mov     [rsp+2A0h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x140047c8f  mov     edx, 40000000h; dwDesiredAccess
0x140047c94  mov     [rsp+2A0h+dwCreationDisposition], 2; dwCreationDisposition
0x140047c9c  mov     [rdi+18h], r14
0x140047ca0  call    cs:__imp_CreateFileW
0x140047ca7  nop     dword ptr [rax+rax+00h]
0x140047cac  mov     [rdi+18h], rax
0x140047cb0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140047cb4  jnz     short loc_140047CDE
0x140047cb6  mov     ebx, 80004005h
0x140047cbb  mov     rcx, [rdi+10h]; Block
0x140047cbf  test    rcx, rcx
0x140047cc2  jz      short loc_140047CD4
0x140047cc4  call    cs:__imp_free
0x140047ccb  nop     dword ptr [rax+rax+00h]
0x140047cd0  mov     [rdi+10h], r14
0x140047cd4  cmp     [rdi+18h], r14
0x140047cd8  jz      short loc_140047CDE
0x140047cda  mov     [rdi+18h], r14
0x140047cde  mov     eax, ebx
0x140047ce0  mov     rcx, [rbp+1A0h+var_20]
0x140047ce7  xor     rcx, rsp; StackCookie
0x140047cea  call    __security_check_cookie
0x140047cef  lea     r11, [rsp+2A0h+var_10]
0x140047cf7  mov     rbx, [r11+20h]
0x140047cfb  mov     rsi, [r11+38h]
0x140047cff  mov     rsp, r11
0x140047d02  pop     r14
0x140047d04  pop     rdi
0x140047d05  pop     rbp
0x140047d06  retn
```
