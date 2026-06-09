# CreateDecoderForStream(IStream *,IImageDecoder * *,DecoderInitFlag)

- ea: `0x180038a74`
- end: `0x180038d8c`
- name: `?CreateDecoderForStream@@YAJPEAUIStream@@PEAPEAUIImageDecoder@@W4DecoderInitFlag@@@Z`
- size: `792`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18003a1d0`
- `0x18003cac0`
- `0x18003cf08`

## callees

- `0x1800067bc`
- `0x18001ec80`
- `0x180038a74`
- `0x180038d94`
- `0x180038e50`
- `0x1800fe680`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180038cd9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180038cd9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038d66`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038d66`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038aaf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038b95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038aaf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038b95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038ac7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038bd4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038ac7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038bd4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180038b7b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180038c9c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180038b7b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180038c9c`

## string_xrefs

- `0x180038d5c`: `CreateCodecInstance`

## pseudocode

```c
__int64 __fastcall CreateDecoderForStream(__int64 *a1, _QWORD *a2, unsigned int a3)
{
  __int64 v5; // rbx
  char *v6; // rdi
  int v7; // esi
  int v8; // ebp
  char *v9; // r15
  unsigned int v10; // r14d
  __int64 v11; // rax
  int v12; // ebp
  const WCHAR *v13; // r15
  INT_PTR (__stdcall *v14)(); // rbp
  struct CachedCodecInfo *DecoderWithHeader; // rbx
  FARPROC ProcAddress; // rax
  int v17; // ebx
  HMODULE Library; // rax
  __int64 v20; // [rsp+30h] [rbp-A8h] BYREF
  unsigned int v21; // [rsp+38h] [rbp-A0h] BYREF
  _QWORD *v22; // [rsp+40h] [rbp-98h]
  char v23; // [rsp+50h] [rbp-88h] BYREF

  v22 = a2;
  EnterCriticalSection(&ImagingCritSec::critSec);
  ReloadCachedCodecInfo();
  v5 = (unsigned int)dword_1801A50E4;
  LeaveCriticalSection(&ImagingCritSec::critSec);
  if ( !(_DWORD)v5 )
    return 2289762310LL;
  if ( (unsigned int)v5 > 0x40 )
  {
    v6 = (char *)GpMallocEx(v5, 0);
    if ( !v6 )
    {
      GpFree(0);
      return 2147942414LL;
    }
    v7 = 1;
  }
  else
  {
    v6 = &v23;
    v7 = 0;
  }
  v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD))(*a1 + 40))(a1, 0, 0, 0);
  if ( v8 >= 0 )
  {
    v9 = v6;
    v10 = 0;
    do
    {
      v11 = *a1;
      v21 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64 *, char *, _QWORD, unsigned int *))(v11 + 24))(
              a1,
              v9,
              (unsigned int)v5,
              &v21);
      v10 += v21;
      if ( v12 != -2147483638 )
        break;
      LODWORD(v5) = v5 - v21;
      v9 += v21;
      Sleep(0);
    }
    while ( (_DWORD)v5 );
    if ( !v10 )
    {
      v17 = -2147467259;
      if ( v12 < 0 )
        v17 = v12;
      goto LABEL_22;
    }
    while ( 1 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64))(*a1 + 40))(a1, -v10, 1);
      if ( v8 != -2147483638 )
        break;
      Sleep(0);
    }
    if ( v8 >= 0 )
    {
      v13 = 0;
      EnterCriticalSection(&ImagingCritSec::critSec);
      if ( (a3 & 2) != 0 && (DecoderWithHeader = FindDecoderWithHeader(v6, v10, 0x10000u)) != 0
        || (v14 = 0, (DecoderWithHeader = FindDecoderWithHeader(v6, v10, 0)) != 0) )
      {
        v14 = (INT_PTR (__stdcall *)())*((_QWORD *)DecoderWithHeader + 16);
        if ( !v14 )
          v13 = (const WCHAR *)*((_QWORD *)DecoderWithHeader + 5);
      }
      LeaveCriticalSection(&ImagingCritSec::critSec);
      if ( DecoderWithHeader )
      {
        v20 = 0;
        if ( v14 )
        {
          ProcAddress = v14;
        }
        else
        {
          Library = LoadLibraryExW(v13, 0, 0);
          if ( !Library || (ProcAddress = GetProcAddress(Library, "CreateCodecInstance")) == 0 )
          {
            v17 = -2005204983;
LABEL_19:
            if ( v17 >= 0 )
            {
              v17 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v20 + 24LL))(v20, a1, a3);
              if ( v17 < 0 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 32LL))(v20);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
              }
              else
              {
                *v22 = v20;
              }
            }
LABEL_22:
            if ( v7 )
              GpFree(v6);
            return (unsigned int)v17;
          }
        }
        v17 = ((__int64 (__fastcall *)(GUID *, __int64 *))ProcAddress)(&IID_IImageDecoder, &v20);
        goto LABEL_19;
      }
      if ( v7 )
        GpFree(v6);
      return 2289762310LL;
    }
  }
  if ( v7 )
    GpFree(v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180038a74  mov     [rsp+arg_18], rbx
0x180038a79  push    rbp
0x180038a7a  push    rsi
0x180038a7b  push    rdi
0x180038a7c  push    r12
0x180038a7e  push    r13
0x180038a80  push    r14
0x180038a82  push    r15
0x180038a84  sub     rsp, 0A0h
0x180038a8b  mov     rax, cs:__security_cookie
0x180038a92  xor     rax, rsp
0x180038a95  mov     [rsp+0D8h+var_48], rax
0x180038a9d  mov     r12, rcx
0x180038aa0  mov     [rsp+0D8h+var_98], rdx
0x180038aa5  lea     rcx, ?critSec@ImagingCritSec@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180038aac  mov     r13d, r8d
0x180038aaf  call    cs:__imp_EnterCriticalSection
0x180038ab5  call    ?ReloadCachedCodecInfo@@YAXXZ; ReloadCachedCodecInfo(void)
0x180038aba  mov     ebx, cs:dword_1801A50E4
0x180038ac0  lea     rcx, ?critSec@ImagingCritSec@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180038ac7  call    cs:__imp_LeaveCriticalSection
0x180038acd  test    ebx, ebx
0x180038acf  jz      loc_180038C8E
0x180038ad5  cmp     ebx, 40h ; '@'
0x180038ad8  ja      loc_180038D10
0x180038ade  lea     rdi, [rsp+0D8h+var_88]
0x180038ae3  xor     esi, esi
0x180038ae5  mov     rax, [r12]
0x180038ae9  xor     edx, edx
0x180038aeb  xor     r9d, r9d
0x180038aee  xor     r8d, r8d
0x180038af1  mov     rcx, r12
0x180038af4  mov     rax, [rax+28h]
0x180038af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038afd  mov     ebp, eax
0x180038aff  test    eax, eax
0x180038b01  js      loc_180038C7A
0x180038b07  mov     r15, rdi
0x180038b0a  xor     r14d, r14d
0x180038b0d  mov     rax, [r12]
0x180038b11  lea     r9, [rsp+0D8h+var_A0]
0x180038b16  mov     r8d, ebx
0x180038b19  mov     [rsp+0D8h+var_A0], 0
0x180038b21  mov     rdx, r15
0x180038b24  mov     rcx, r12
0x180038b27  mov     rax, [rax+18h]
0x180038b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b30  mov     ebp, eax
0x180038b32  mov     eax, [rsp+0D8h+var_A0]
0x180038b36  add     r14d, eax
0x180038b39  cmp     ebp, 8000000Ah
0x180038b3f  jz      loc_180038C95
0x180038b45  test    r14d, r14d
0x180038b48  jz      loc_180038C6E
0x180038b4e  mov     eax, r14d
0x180038b51  neg     eax
0x180038b53  movsxd  rbx, eax
0x180038b56  mov     rax, [r12]
0x180038b5a  xor     r9d, r9d
0x180038b5d  mov     rdx, rbx
0x180038b60  mov     rcx, r12
0x180038b63  mov     rax, [rax+28h]
0x180038b67  lea     r8d, [r9+1]
0x180038b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b70  mov     ebp, eax
0x180038b72  cmp     eax, 8000000Ah
0x180038b77  jnz     short loc_180038B83
0x180038b79  xor     ecx, ecx; dwMilliseconds
0x180038b7b  call    cs:__imp_Sleep
0x180038b81  jmp     short loc_180038B56
0x180038b83  test    ebp, ebp
0x180038b85  js      loc_180038C7A
0x180038b8b  lea     rcx, ?critSec@ImagingCritSec@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180038b92  xor     r15d, r15d
0x180038b95  call    cs:__imp_EnterCriticalSection
0x180038b9b  test    r13b, 2
0x180038b9f  jnz     loc_180038CEE
0x180038ba5  xor     r8d, r8d; unsigned int
0x180038ba8  mov     edx, r14d; unsigned int
0x180038bab  mov     rcx, rdi; void *
0x180038bae  xor     ebp, ebp
0x180038bb0  call    ?FindDecoderWithHeader@@YAPEAUCachedCodecInfo@@PEBXII@Z; FindDecoderWithHeader(void const *,uint,uint)
0x180038bb5  mov     rbx, rax
0x180038bb8  test    rax, rax
0x180038bbb  jz      short loc_180038BCD
0x180038bbd  mov     rbp, [rbx+80h]
0x180038bc4  test    rbp, rbp
0x180038bc7  jz      loc_180038D46
0x180038bcd  lea     rcx, ?critSec@ImagingCritSec@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180038bd4  call    cs:__imp_LeaveCriticalSection
0x180038bda  test    rbx, rbx
0x180038bdd  jz      loc_180038C86
0x180038be3  mov     [rsp+0D8h+var_A8], 0
0x180038bec  test    rbp, rbp
0x180038bef  jz      loc_180038CD1
0x180038bf5  mov     rax, rbp
0x180038bf8  lea     rcx, IID_IImageDecoder
0x180038bff  lea     rdx, [rsp+0D8h+var_A8]
0x180038c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c09  mov     ebx, eax
0x180038c0b  test    ebx, ebx
0x180038c0d  js      short loc_180038C39
0x180038c0f  mov     rcx, [rsp+0D8h+var_A8]
0x180038c14  mov     r8d, r13d
0x180038c17  mov     rdx, r12
0x180038c1a  mov     rax, [rcx]
0x180038c1d  mov     rax, [rax+18h]
0x180038c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c26  mov     rcx, [rsp+0D8h+var_A8]
0x180038c2b  mov     ebx, eax
0x180038c2d  test    eax, eax
0x180038c2f  js      short loc_180038CAF
0x180038c31  mov     rax, [rsp+0D8h+var_98]
0x180038c36  mov     [rax], rcx
0x180038c39  test    esi, esi
0x180038c3b  jnz     loc_180038D39
0x180038c41  mov     eax, ebx
0x180038c43  mov     rcx, [rsp+0D8h+var_48]
0x180038c4b  xor     rcx, rsp; StackCookie
0x180038c4e  call    __security_check_cookie
0x180038c53  mov     rbx, [rsp+0D8h+arg_18]
0x180038c5b  add     rsp, 0A0h
0x180038c62  pop     r15
0x180038c64  pop     r14
0x180038c66  pop     r13
0x180038c68  pop     r12
0x180038c6a  pop     rdi
0x180038c6b  pop     rsi
0x180038c6c  pop     rbp
0x180038c6d  retn
0x180038c6e  test    ebp, ebp
0x180038c70  mov     ebx, 80004005h
0x180038c75  cmovs   ebx, ebp
0x180038c78  jmp     short loc_180038C39
0x180038c7a  test    esi, esi
0x180038c7c  jnz     loc_180038D2C
0x180038c82  mov     eax, ebp
0x180038c84  jmp     short loc_180038C43
0x180038c86  test    esi, esi
0x180038c88  jnz     loc_180038D4F
0x180038c8e  mov     eax, 887B0006h
0x180038c93  jmp     short loc_180038C43
0x180038c95  xor     ecx, ecx; dwMilliseconds
0x180038c97  sub     ebx, eax
0x180038c99  add     r15, rax
0x180038c9c  call    cs:__imp_Sleep
0x180038ca2  test    ebx, ebx
0x180038ca4  jz      loc_180038B45
0x180038caa  jmp     loc_180038B0D
0x180038caf  mov     rax, [rcx]
0x180038cb2  mov     rax, [rax+20h]
0x180038cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038cbb  mov     rcx, [rsp+0D8h+var_A8]
0x180038cc0  mov     rax, [rcx]
0x180038cc3  mov     rax, [rax+10h]
0x180038cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ccc  jmp     loc_180038C39
0x180038cd1  xor     r8d, r8d; dwFlags
0x180038cd4  xor     edx, edx; hFile
0x180038cd6  mov     rcx, r15; lpLibFileName
0x180038cd9  call    cs:__imp_LoadLibraryExW
0x180038cdf  test    rax, rax
0x180038ce2  jnz     short loc_180038D5C
0x180038ce4  mov     ebx, 887B0009h
0x180038ce9  jmp     loc_180038C0B
0x180038cee  mov     r8d, 10000h; unsigned int
0x180038cf4  mov     edx, r14d; unsigned int
0x180038cf7  mov     rcx, rdi; void *
0x180038cfa  call    ?FindDecoderWithHeader@@YAPEAUCachedCodecInfo@@PEBXII@Z; FindDecoderWithHeader(void const *,uint,uint)
0x180038cff  mov     rbx, rax
0x180038d02  test    rax, rax
0x180038d05  jnz     loc_180038BBD
0x180038d0b  jmp     loc_180038BA5
0x180038d10  mov     rcx, rbx
0x180038d13  xor     edx, edx
0x180038d15  call    GpMallocEx
0x180038d1a  mov     rdi, rax
0x180038d1d  test    rax, rax
0x180038d20  jz      short loc_180038D7A
0x180038d22  mov     esi, 1
0x180038d27  jmp     loc_180038AE5
0x180038d2c  mov     rcx, rdi
0x180038d2f  call    GpFree
0x180038d34  jmp     loc_180038C82
0x180038d39  mov     rcx, rdi
0x180038d3c  call    GpFree
0x180038d41  jmp     loc_180038C41
0x180038d46  mov     r15, [rbx+28h]
0x180038d4a  jmp     loc_180038BCD
0x180038d4f  mov     rcx, rdi
0x180038d52  call    GpFree
0x180038d57  jmp     loc_180038C8E
0x180038d5c  lea     rdx, aCreatecodecins; "CreateCodecInstance"
0x180038d63  mov     rcx, rax; hModule
0x180038d66  call    cs:__imp_GetProcAddress
0x180038d6c  test    rax, rax
0x180038d6f  jnz     loc_180038BF8
0x180038d75  jmp     loc_180038CE4
0x180038d7a  mov     rcx, rax
0x180038d7d  call    GpFree
0x180038d82  mov     eax, 8007000Eh
0x180038d87  jmp     loc_180038C43
```
