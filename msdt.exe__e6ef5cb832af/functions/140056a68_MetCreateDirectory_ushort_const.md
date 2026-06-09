# MetCreateDirectory(ushort const *)

- ea: `0x140056a68`
- end: `0x140056c69`
- name: `?MetCreateDirectory@@YAJPEBG@Z`
- size: `513`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140056714`

## callees

- `0x140020420`
- `0x140056a68`
- `0x140056cf8`
- `0x140056dcc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140056be4`
- `KERNEL32!GetLastError` at `0x140056be4`
- `KERNEL32!HeapAlloc` at `0x140056abd`
- `KERNEL32!HeapAlloc` at `0x140056abd`
- `KERNEL32!HeapFree` at `0x140056c35`
- `KERNEL32!HeapFree` at `0x140056c35`
- `KERNEL32!GetProcessHeap` at `0x140056aa6`
- `KERNEL32!GetProcessHeap` at `0x140056c21`
- `KERNEL32!GetProcessHeap` at `0x140056aa6`
- `KERNEL32!GetProcessHeap` at `0x140056c21`
- `KERNEL32!LocalFree` at `0x140056c4f`
- `KERNEL32!LocalFree` at `0x140056c4f`
- `KERNEL32!CreateDirectoryW` at `0x140056bd4`
- `KERNEL32!CreateDirectoryW` at `0x140056bd4`
- `msvcrt!wcschr` at `0x140056b6a`
- `msvcrt!wcschr` at `0x140056b82`
- `msvcrt!wcschr` at `0x140056bb5`
- `msvcrt!wcschr` at `0x140056b6a`
- `msvcrt!wcschr` at `0x140056b82`
- `msvcrt!wcschr` at `0x140056bb5`

## string_xrefs

- `0x140056ad6`: `MetCreateDirectory`
- `0x140056b15`: `MetCreateDirectory`

## pseudocode

```c
__int64 __fastcall MetCreateDirectory(LPCWSTR lpSrc)
{
  unsigned __int64 v2; // rax
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v4; // rdi
  signed int v5; // ebx
  int v6; // eax
  int v7; // r9d
  wchar_t *v8; // rax
  wchar_t *v9; // rsi
  wchar_t *v10; // rax
  signed int LastError; // eax
  HANDLE v12; // rax
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+30h] [rbp-48h] BYREF

  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( *lpSrc )
  {
    v2 = -1;
    do
      ++v2;
    while ( lpSrc[v2] );
    if ( v2 >= 4 )
    {
      ProcessHeap = GetProcessHeap();
      v4 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x800u);
      if ( !v4 )
      {
        v5 = -2147024882;
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetCreateDirectory", 576, -2147024882);
        goto LABEL_30;
      }
      v6 = MetCreateSecurityDescriptor(&SecurityAttributes);
      v5 = v6;
      if ( v6 >= 0 )
      {
        v6 = MetExpandVariables(v4, 0x400u, lpSrc);
        v5 = v6;
        if ( v6 >= 0 )
        {
          if ( *v4 != 92 || v4[1] != 92 )
          {
            v9 = v4 + 2;
            goto LABEL_19;
          }
          v8 = wcschr(v4 + 2, 0x5Cu);
          if ( v8 && (v9 = wcschr(v8 + 1, 0x5Cu)) != 0 )
          {
LABEL_19:
            while ( 1 )
            {
              v10 = wcschr(v9 + 1, 0x5Cu);
              v9 = v10;
              if ( !v10 )
                break;
              *v10 = 0;
              if ( !CreateDirectoryW(v4, &SecurityAttributes) )
              {
                LastError = GetLastError();
                v5 = LastError;
                if ( LastError > 0 )
                  v5 = (unsigned __int16)LastError | 0x80070000;
                if ( v5 < 0 && (_WORD)v5 != 183 )
                {
                  SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetCreateDirectory", 620, v5);
                  goto LABEL_28;
                }
              }
              *v9 = 92;
            }
            v5 = 0;
          }
          else
          {
            v5 = -2147024735;
            SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetCreateDirectory", 603, -2147024735);
          }
          goto LABEL_28;
        }
        v7 = 585;
      }
      else
      {
        v7 = 579;
      }
      SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetCreateDirectory", v7, v6);
LABEL_28:
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v4);
      goto LABEL_30;
    }
  }
  v5 = 0;
LABEL_30:
  if ( SecurityAttributes.lpSecurityDescriptor )
    LocalFree(SecurityAttributes.lpSecurityDescriptor);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140056a68  push    rbx
0x140056a6a  push    rbp
0x140056a6b  push    rsi
0x140056a6c  push    rdi
0x140056a6d  push    r14
0x140056a6f  sub     rsp, 50h
0x140056a73  xor     ebp, ebp
0x140056a75  xorps   xmm0, xmm0
0x140056a78  mov     rsi, rcx
0x140056a7b  mov     qword ptr [rsp+78h+SecurityAttributes.nLength], rbp
0x140056a80  movdqu  xmmword ptr [rsp+78h+SecurityAttributes.lpSecurityDescriptor], xmm0
0x140056a86  cmp     bp, [rcx]
0x140056a89  jz      loc_140056C43
0x140056a8f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140056a93  inc     rax
0x140056a96  cmp     [rcx+rax*2], bp
0x140056a9a  jnz     short loc_140056A93
0x140056a9c  cmp     rax, 4
0x140056aa0  jb      loc_140056C43
0x140056aa6  call    cs:__imp_GetProcessHeap
0x140056aad  nop     dword ptr [rax+rax+00h]
0x140056ab2  xor     edx, edx; dwFlags
0x140056ab4  mov     r8d, 800h; dwBytes
0x140056aba  mov     rcx, rax; hHeap
0x140056abd  call    cs:__imp_HeapAlloc
0x140056ac4  nop     dword ptr [rax+rax+00h]
0x140056ac9  mov     rdi, rax
0x140056acc  test    rax, rax
0x140056acf  jnz     short loc_140056AFB
0x140056ad1  mov     ebx, 8007000Eh
0x140056ad6  lea     r8, aMetcreatedirec; "MetCreateDirectory"
0x140056add  mov     r9d, 240h
0x140056ae3  mov     [rsp+78h+var_58], ebx
0x140056ae7  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x140056aee  lea     ecx, [rax+1]; Level
0x140056af1  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140056af6  jmp     loc_140056C45
0x140056afb  lea     rcx, [rsp+78h+SecurityAttributes]; struct _SECURITY_ATTRIBUTES *
0x140056b00  call    ?MetCreateSecurityDescriptor@@YAJPEAU_SECURITY_ATTRIBUTES@@@Z; MetCreateSecurityDescriptor(_SECURITY_ATTRIBUTES *)
0x140056b05  mov     ebx, eax
0x140056b07  test    eax, eax
0x140056b09  jns     short loc_140056B32
0x140056b0b  mov     r9d, 243h
0x140056b11  mov     [rsp+78h+var_58], eax
0x140056b15  lea     r8, aMetcreatedirec; "MetCreateDirectory"
0x140056b1c  mov     ecx, 1; Level
0x140056b21  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x140056b28  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140056b2d  jmp     loc_140056C21
0x140056b32  mov     r8, rsi; lpSrc
0x140056b35  mov     edx, 400h; unsigned __int64
0x140056b3a  mov     rcx, rdi; unsigned __int16 *
0x140056b3d  call    ?MetExpandVariables@@YAJPEAG_KPEBG@Z; MetExpandVariables(ushort *,unsigned __int64,ushort const *)
0x140056b42  mov     ebx, eax
0x140056b44  test    eax, eax
0x140056b46  jns     short loc_140056B50
0x140056b48  mov     r9d, 249h
0x140056b4e  jmp     short loc_140056B11
0x140056b50  mov     r14d, 5Ch ; '\'
0x140056b56  cmp     r14w, [rdi]
0x140056b5a  jnz     short loc_140056BAA
0x140056b5c  cmp     r14w, [rdi+2]
0x140056b61  jnz     short loc_140056BAA
0x140056b63  mov     edx, r14d; Ch
0x140056b66  lea     rcx, [rdi+4]; Str
0x140056b6a  call    cs:__imp_wcschr
0x140056b71  nop     dword ptr [rax+rax+00h]
0x140056b76  test    rax, rax
0x140056b79  jz      short loc_140056B96
0x140056b7b  mov     edx, r14d; Ch
0x140056b7e  lea     rcx, [rax+2]; Str
0x140056b82  call    cs:__imp_wcschr
0x140056b89  nop     dword ptr [rax+rax+00h]
0x140056b8e  mov     rsi, rax
0x140056b91  test    rax, rax
0x140056b94  jnz     short loc_140056BAE
0x140056b96  mov     ebx, 800700A1h
0x140056b9b  mov     r9d, 25Bh
0x140056ba1  mov     [rsp+78h+var_58], ebx
0x140056ba5  jmp     loc_140056B15
0x140056baa  lea     rsi, [rdi+4]
0x140056bae  mov     edx, r14d; Ch
0x140056bb1  lea     rcx, [rsi+2]; Str
0x140056bb5  call    cs:__imp_wcschr
0x140056bbc  nop     dword ptr [rax+rax+00h]
0x140056bc1  mov     rsi, rax
0x140056bc4  test    rax, rax
0x140056bc7  jz      short loc_140056C1F
0x140056bc9  lea     rdx, [rsp+78h+SecurityAttributes]; lpSecurityAttributes
0x140056bce  mov     [rax], bp
0x140056bd1  mov     rcx, rdi; lpPathName
0x140056bd4  call    cs:__imp_CreateDirectoryW
0x140056bdb  nop     dword ptr [rax+rax+00h]
0x140056be0  test    eax, eax
0x140056be2  jnz     short loc_140056C0A
0x140056be4  call    cs:__imp_GetLastError
0x140056beb  nop     dword ptr [rax+rax+00h]
0x140056bf0  mov     ebx, eax
0x140056bf2  test    eax, eax
0x140056bf4  jle     short loc_140056BFF
0x140056bf6  movzx   ebx, ax
0x140056bf9  or      ebx, 80070000h
0x140056bff  test    ebx, ebx
0x140056c01  jns     short loc_140056C0A
0x140056c03  cmp     bx, 0B7h
0x140056c08  jnz     short loc_140056C10
0x140056c0a  mov     [rsi], r14w
0x140056c0e  jmp     short loc_140056BAE
0x140056c10  mov     [rsp+78h+var_58], ebx
0x140056c14  mov     r9d, 26Ch
0x140056c1a  jmp     loc_140056B15
0x140056c1f  mov     ebx, ebp
0x140056c21  call    cs:__imp_GetProcessHeap
0x140056c28  nop     dword ptr [rax+rax+00h]
0x140056c2d  mov     r8, rdi; lpMem
0x140056c30  xor     edx, edx; dwFlags
0x140056c32  mov     rcx, rax; hHeap
0x140056c35  call    cs:__imp_HeapFree
0x140056c3c  nop     dword ptr [rax+rax+00h]
0x140056c41  jmp     short loc_140056C45
0x140056c43  mov     ebx, ebp
0x140056c45  mov     rcx, [rsp+78h+SecurityAttributes.lpSecurityDescriptor]; hMem
0x140056c4a  test    rcx, rcx
0x140056c4d  jz      short loc_140056C5B
0x140056c4f  call    cs:__imp_LocalFree
0x140056c56  nop     dword ptr [rax+rax+00h]
0x140056c5b  mov     eax, ebx
0x140056c5d  add     rsp, 50h
0x140056c61  pop     r14
0x140056c63  pop     rdi
0x140056c64  pop     rsi
0x140056c65  pop     rbp
0x140056c66  pop     rbx
0x140056c67  retn
```
