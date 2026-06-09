# CreateDirectoryW(ushort const *)

- ea: `0x1400407b0`
- end: `0x1400409b1`
- name: `?CreateDirectoryW@@YAJPEBG@Z`
- size: `513`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400414b4`
- `0x1400418a4`
- `0x140042bf8`

## callees

- `0x140020420`
- `0x1400407b0`
- `0x140040a40`
- `0x140041020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14004092c`
- `KERNEL32!GetLastError` at `0x14004092c`
- `KERNEL32!HeapAlloc` at `0x140040805`
- `KERNEL32!HeapAlloc` at `0x140040805`
- `KERNEL32!HeapFree` at `0x14004097d`
- `KERNEL32!HeapFree` at `0x14004097d`
- `KERNEL32!GetProcessHeap` at `0x1400407ee`
- `KERNEL32!GetProcessHeap` at `0x140040969`
- `KERNEL32!GetProcessHeap` at `0x1400407ee`
- `KERNEL32!GetProcessHeap` at `0x140040969`
- `KERNEL32!LocalFree` at `0x140040997`
- `KERNEL32!LocalFree` at `0x140040997`
- `KERNEL32!CreateDirectoryW` at `0x14004091c`
- `KERNEL32!CreateDirectoryW` at `0x14004091c`
- `msvcrt!wcschr` at `0x1400408b2`
- `msvcrt!wcschr` at `0x1400408ca`
- `msvcrt!wcschr` at `0x1400408fd`
- `msvcrt!wcschr` at `0x1400408b2`
- `msvcrt!wcschr` at `0x1400408ca`
- `msvcrt!wcschr` at `0x1400408fd`

## string_xrefs

- `0x14004081e`: `CreateDirectoryW`
- `0x14004085d`: `CreateDirectoryW`

## pseudocode

```c
__int64 __fastcall CreateDirectoryW(LPCWSTR lpSrc)
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
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+30h] [rbp-48h] BYREF

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
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateDirectoryW", 982, -2147024882);
        goto LABEL_30;
      }
      v6 = CreateSecurityDescriptor(&SecurityAttributes);
      v5 = v6;
      if ( v6 >= 0 )
      {
        v6 = ExpandVariables(v4, 0x400u, lpSrc);
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
                  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateDirectoryW", 1026, v5);
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
            SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateDirectoryW", 1009, -2147024735);
          }
          goto LABEL_28;
        }
        v7 = 991;
      }
      else
      {
        v7 = 985;
      }
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateDirectoryW", v7, v6);
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
0x1400407b0  push    rbx
0x1400407b2  push    rbp
0x1400407b3  push    rsi
0x1400407b4  push    rdi
0x1400407b5  push    r14
0x1400407b7  sub     rsp, 50h
0x1400407bb  xor     ebp, ebp
0x1400407bd  xorps   xmm0, xmm0
0x1400407c0  mov     rsi, rcx
0x1400407c3  mov     qword ptr [rsp+78h+SecurityAttributes.nLength], rbp
0x1400407c8  movdqu  xmmword ptr [rsp+78h+SecurityAttributes.lpSecurityDescriptor], xmm0
0x1400407ce  cmp     bp, [rcx]
0x1400407d1  jz      loc_14004098B
0x1400407d7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400407db  inc     rax
0x1400407de  cmp     [rcx+rax*2], bp
0x1400407e2  jnz     short loc_1400407DB
0x1400407e4  cmp     rax, 4
0x1400407e8  jb      loc_14004098B
0x1400407ee  call    cs:__imp_GetProcessHeap
0x1400407f5  nop     dword ptr [rax+rax+00h]
0x1400407fa  xor     edx, edx; dwFlags
0x1400407fc  mov     r8d, 800h; dwBytes
0x140040802  mov     rcx, rax; hHeap
0x140040805  call    cs:__imp_HeapAlloc
0x14004080c  nop     dword ptr [rax+rax+00h]
0x140040811  mov     rdi, rax
0x140040814  test    rax, rax
0x140040817  jnz     short loc_140040843
0x140040819  mov     ebx, 8007000Eh
0x14004081e  lea     r8, aCreatedirector; "CreateDirectoryW"
0x140040825  mov     r9d, 3D6h
0x14004082b  mov     [rsp+78h+var_58], ebx
0x14004082f  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140040836  lea     ecx, [rax+1]; Level
0x140040839  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14004083e  jmp     loc_14004098D
0x140040843  lea     rcx, [rsp+78h+SecurityAttributes]; struct _SECURITY_ATTRIBUTES *
0x140040848  call    ?CreateSecurityDescriptor@@YAJPEAU_SECURITY_ATTRIBUTES@@@Z; CreateSecurityDescriptor(_SECURITY_ATTRIBUTES *)
0x14004084d  mov     ebx, eax
0x14004084f  test    eax, eax
0x140040851  jns     short loc_14004087A
0x140040853  mov     r9d, 3D9h
0x140040859  mov     [rsp+78h+var_58], eax
0x14004085d  lea     r8, aCreatedirector; "CreateDirectoryW"
0x140040864  mov     ecx, 1; Level
0x140040869  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140040870  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140040875  jmp     loc_140040969
0x14004087a  mov     r8, rsi; lpSrc
0x14004087d  mov     edx, 400h; unsigned __int64
0x140040882  mov     rcx, rdi; unsigned __int16 *
0x140040885  call    ?ExpandVariables@@YAJPEAG_KPEBG@Z; ExpandVariables(ushort *,unsigned __int64,ushort const *)
0x14004088a  mov     ebx, eax
0x14004088c  test    eax, eax
0x14004088e  jns     short loc_140040898
0x140040890  mov     r9d, 3DFh
0x140040896  jmp     short loc_140040859
0x140040898  mov     r14d, 5Ch ; '\'
0x14004089e  cmp     r14w, [rdi]
0x1400408a2  jnz     short loc_1400408F2
0x1400408a4  cmp     r14w, [rdi+2]
0x1400408a9  jnz     short loc_1400408F2
0x1400408ab  mov     edx, r14d; Ch
0x1400408ae  lea     rcx, [rdi+4]; Str
0x1400408b2  call    cs:__imp_wcschr
0x1400408b9  nop     dword ptr [rax+rax+00h]
0x1400408be  test    rax, rax
0x1400408c1  jz      short loc_1400408DE
0x1400408c3  mov     edx, r14d; Ch
0x1400408c6  lea     rcx, [rax+2]; Str
0x1400408ca  call    cs:__imp_wcschr
0x1400408d1  nop     dword ptr [rax+rax+00h]
0x1400408d6  mov     rsi, rax
0x1400408d9  test    rax, rax
0x1400408dc  jnz     short loc_1400408F6
0x1400408de  mov     ebx, 800700A1h
0x1400408e3  mov     r9d, 3F1h
0x1400408e9  mov     [rsp+78h+var_58], ebx
0x1400408ed  jmp     loc_14004085D
0x1400408f2  lea     rsi, [rdi+4]
0x1400408f6  mov     edx, r14d; Ch
0x1400408f9  lea     rcx, [rsi+2]; Str
0x1400408fd  call    cs:__imp_wcschr
0x140040904  nop     dword ptr [rax+rax+00h]
0x140040909  mov     rsi, rax
0x14004090c  test    rax, rax
0x14004090f  jz      short loc_140040967
0x140040911  lea     rdx, [rsp+78h+SecurityAttributes]; lpSecurityAttributes
0x140040916  mov     [rax], bp
0x140040919  mov     rcx, rdi; lpPathName
0x14004091c  call    cs:__imp_CreateDirectoryW
0x140040923  nop     dword ptr [rax+rax+00h]
0x140040928  test    eax, eax
0x14004092a  jnz     short loc_140040952
0x14004092c  call    cs:__imp_GetLastError
0x140040933  nop     dword ptr [rax+rax+00h]
0x140040938  mov     ebx, eax
0x14004093a  test    eax, eax
0x14004093c  jle     short loc_140040947
0x14004093e  movzx   ebx, ax
0x140040941  or      ebx, 80070000h
0x140040947  test    ebx, ebx
0x140040949  jns     short loc_140040952
0x14004094b  cmp     bx, 0B7h
0x140040950  jnz     short loc_140040958
0x140040952  mov     [rsi], r14w
0x140040956  jmp     short loc_1400408F6
0x140040958  mov     [rsp+78h+var_58], ebx
0x14004095c  mov     r9d, 402h
0x140040962  jmp     loc_14004085D
0x140040967  mov     ebx, ebp
0x140040969  call    cs:__imp_GetProcessHeap
0x140040970  nop     dword ptr [rax+rax+00h]
0x140040975  mov     r8, rdi; lpMem
0x140040978  xor     edx, edx; dwFlags
0x14004097a  mov     rcx, rax; hHeap
0x14004097d  call    cs:__imp_HeapFree
0x140040984  nop     dword ptr [rax+rax+00h]
0x140040989  jmp     short loc_14004098D
0x14004098b  mov     ebx, ebp
0x14004098d  mov     rcx, [rsp+78h+SecurityAttributes.lpSecurityDescriptor]; hMem
0x140040992  test    rcx, rcx
0x140040995  jz      short loc_1400409A3
0x140040997  call    cs:__imp_LocalFree
0x14004099e  nop     dword ptr [rax+rax+00h]
0x1400409a3  mov     eax, ebx
0x1400409a5  add     rsp, 50h
0x1400409a9  pop     r14
0x1400409ab  pop     rdi
0x1400409ac  pop     rsi
0x1400409ad  pop     rbp
0x1400409ae  pop     rbx
0x1400409af  retn
```
