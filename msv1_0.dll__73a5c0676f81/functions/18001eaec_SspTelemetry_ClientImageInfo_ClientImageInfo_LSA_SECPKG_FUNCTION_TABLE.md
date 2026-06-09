# SspTelemetry::ClientImageInfo::ClientImageInfo(_LSA_SECPKG_FUNCTION_TABLE *)

- ea: `0x18001eaec`
- end: `0x18001ecee`
- name: `??0ClientImageInfo@SspTelemetry@@QEAA@PEAU_LSA_SECPKG_FUNCTION_TABLE@@@Z`
- size: `514`
- prototype: `__int64 __fastcall(SspTelemetry::ClientImageInfo *__hidden this, struct _LSA_SECPKG_FUNCTION_TABLE *)`
- caller_count: `13`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009b00`
- `0x180011fc4`
- `0x180024c00`
- `0x18002d4cc`
- `0x180051944`
- `0x180052cb4`
- `0x180052f18`
- `0x1800530ac`
- `0x1800532a0`
- `0x1800581a8`
- `0x1800587c8`
- `0x180059760`
- `0x180068748`

## callees

- `0x18001eaec`
- `0x18002fb50`
- `0x18006d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18001ec23`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18001ec23`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x18001ecb0`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x18001ecb0`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001ec38`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001ec88`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001ec9a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001ec38`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001ec88`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001ec9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ec53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ec53`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001ebaf`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001ebaf`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18001ebe8`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18001ebe8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
SspTelemetry::ClientImageInfo *__fastcall SspTelemetry::ClientImageInfo::ClientImageInfo(
        SspTelemetry::ClientImageInfo *this,
        struct _LSA_SECPKG_FUNCTION_TABLE *a2)
{
  char *v3; // r15
  char *v4; // r12
  HANDLE v5; // rax
  void *v6; // r14
  DWORD dwSize[4]; // [rsp+50h] [rbp-268h] BYREF
  SspTelemetry::ClientImageInfo *v9; // [rsp+60h] [rbp-258h]
  WCHAR ExeName[264]; // [rsp+70h] [rbp-248h] BYREF

  v9 = this;
  *(_OWORD *)((char *)this + 1576) = 0;
  *(_OWORD *)((char *)this + 1592) = 0;
  *((_QWORD *)this + 201) = 0;
  v3 = (char *)this + 32;
  *((_WORD *)this + 16) = 0;
  v4 = (char *)this + 544;
  *((_WORD *)this + 272) = 0;
  *((_DWORD *)this + 392) = 0;
  if ( ((int (*)(void))a2->GetClientInfo)() >= 0 )
  {
    if ( *((_DWORD *)this + 2) == dword_18008A3E0 )
    {
      _o_wcsncpy_s(v3, 256);
LABEL_12:
      _o_wcsncpy_s(v4, 256);
      _o_wcsncat_s(v4, 256, &Ext, -1);
      *((_DWORD *)this + 392) = *((_DWORD *)this + 2);
      return this;
    }
    if ( _InterlockedCompareExchange16(&word_18008A5F0, 1, 0) != 1 )
    {
      Filename = 0;
      Ext = 0;
      v5 = OpenProcess(0x1000u, 0, *((_DWORD *)this + 2));
      v6 = v5;
      if ( v5 )
      {
        dwSize[0] = 260;
        if ( QueryFullProcessImageNameW(v5, 0, ExeName, dwSize) )
        {
          if ( _wsplitpath_s(ExeName, 0, 0, 0, 0, &Filename, 0x100u, &Ext, 0x100u) )
          {
            Filename = 0;
            Ext = 0;
          }
          else
          {
            _o_wcsncpy_s(v3, 256);
          }
        }
        CloseHandle(v6);
      }
      dword_18008A3E0 = *((_DWORD *)this + 2);
      word_18008A5F0 = 0;
      goto LABEL_12;
    }
  }
  return this;
}

```

## disassembly

```asm
0x18001eaec  mov     [rsp+arg_10], rbx
0x18001eaf1  mov     [rsp+arg_18], rbp
0x18001eaf6  push    rsi
0x18001eaf7  push    rdi
0x18001eaf8  push    r12
0x18001eafa  push    r14
0x18001eafc  push    r15
0x18001eafe  sub     rsp, 290h
0x18001eb05  mov     rax, cs:__security_cookie
0x18001eb0c  xor     rax, rsp
0x18001eb0f  mov     [rsp+2B8h+var_38], rax
0x18001eb17  mov     rbx, rcx
0x18001eb1a  mov     [rsp+2B8h+var_258], rcx
0x18001eb1f  xorps   xmm0, xmm0
0x18001eb22  movups  xmmword ptr [rcx+628h], xmm0
0x18001eb29  xorps   xmm1, xmm1
0x18001eb2c  movups  xmmword ptr [rcx+638h], xmm1
0x18001eb33  mov     qword ptr [rcx+648h], 0
0x18001eb3e  lea     r15, [rcx+20h]
0x18001eb42  xor     eax, eax
0x18001eb44  mov     [r15], ax
0x18001eb48  lea     r12, [rcx+220h]
0x18001eb4f  mov     [r12], ax
0x18001eb54  mov     [rcx+620h], eax
0x18001eb5a  mov     rax, [rdx+80h]
0x18001eb61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb66  test    eax, eax
0x18001eb68  js      loc_18001ECBF
0x18001eb6e  mov     eax, cs:dword_18008A3E0
0x18001eb74  cmp     [rbx+8], eax
0x18001eb77  jz      loc_18001EC6D
0x18001eb7d  xor     eax, eax
0x18001eb7f  lea     ecx, [rax+1]
0x18001eb82  lock cmpxchg cs:word_18008A5F0, cx
0x18001eb8b  cmp     ax, cx
0x18001eb8e  jz      loc_18001ECBF
0x18001eb94  xor     eax, eax
0x18001eb96  mov     cs:Filename, ax
0x18001eb9d  mov     cs:Ext, ax
0x18001eba4  mov     r8d, [rbx+8]; dwProcessId
0x18001eba8  xor     edx, edx; bInheritHandle
0x18001ebaa  mov     ecx, 1000h; dwDesiredAccess
0x18001ebaf  call    cs:__imp_OpenProcess
0x18001ebb5  mov     r14, rax
0x18001ebb8  mov     edi, 100h
0x18001ebbd  lea     rsi, Filename
0x18001ebc4  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18001ebc8  test    rax, rax
0x18001ebcb  jz      loc_18001EC59
0x18001ebd1  mov     [rsp+2B8h+dwSize], 104h
0x18001ebd9  lea     r9, [rsp+2B8h+dwSize]; lpdwSize
0x18001ebde  lea     r8, [rsp+2B8h+ExeName]; lpExeName
0x18001ebe3  xor     edx, edx; dwFlags
0x18001ebe5  mov     rcx, rax; hProcess
0x18001ebe8  call    cs:__imp_QueryFullProcessImageNameW
0x18001ebee  test    eax, eax
0x18001ebf0  jz      short loc_18001EC50
0x18001ebf2  mov     [rsp+2B8h+ExtCount], rdi; ExtCount
0x18001ebf7  lea     rax, Ext
0x18001ebfe  mov     [rsp+2B8h+Ext], rax; Ext
0x18001ec03  mov     [rsp+2B8h+FilenameCount], rdi; FilenameCount
0x18001ec08  mov     [rsp+2B8h+Filename], rsi; Filename
0x18001ec0d  mov     [rsp+2B8h+DirCount], 0; DirCount
0x18001ec16  xor     r9d, r9d; Dir
0x18001ec19  xor     r8d, r8d; DriveCount
0x18001ec1c  xor     edx, edx; Drive
0x18001ec1e  lea     rcx, [rsp+2B8h+ExeName]; FullPath
0x18001ec23  call    cs:__imp__wsplitpath_s
0x18001ec29  test    eax, eax
0x18001ec2b  jnz     short loc_18001EC40
0x18001ec2d  mov     r9, rbp
0x18001ec30  mov     r8, rsi
0x18001ec33  mov     edx, edi
0x18001ec35  mov     rcx, r15
0x18001ec38  call    cs:__imp__o_wcsncpy_s
0x18001ec3e  jmp     short loc_18001EC50
0x18001ec40  xor     eax, eax
0x18001ec42  mov     cs:Filename, ax
0x18001ec49  mov     cs:Ext, ax
0x18001ec50  mov     rcx, r14; hObject
0x18001ec53  call    cs:__imp_CloseHandle
0x18001ec59  mov     eax, [rbx+8]
0x18001ec5c  mov     cs:dword_18008A3E0, eax
0x18001ec62  xor     eax, eax
0x18001ec64  xchg    ax, cs:word_18008A5F0
0x18001ec6b  jmp     short loc_18001EC8E
0x18001ec6d  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18001ec71  mov     r9, rbp
0x18001ec74  lea     rsi, Filename
0x18001ec7b  mov     r8, rsi
0x18001ec7e  mov     edi, 100h
0x18001ec83  mov     edx, edi
0x18001ec85  mov     rcx, r15
0x18001ec88  call    cs:__imp__o_wcsncpy_s
0x18001ec8e  mov     r9, rbp
0x18001ec91  mov     r8, rsi
0x18001ec94  mov     rdx, rdi
0x18001ec97  mov     rcx, r12
0x18001ec9a  call    cs:__imp__o_wcsncpy_s
0x18001eca0  mov     r9, rbp
0x18001eca3  lea     r8, Ext
0x18001ecaa  mov     rdx, rdi
0x18001ecad  mov     rcx, r12
0x18001ecb0  call    cs:__imp__o_wcsncat_s
0x18001ecb6  mov     ecx, [rbx+8]
0x18001ecb9  mov     [rbx+620h], ecx
0x18001ecbf  mov     rax, rbx
0x18001ecc2  mov     rcx, [rsp+2B8h+var_38]
0x18001ecca  xor     rcx, rsp; StackCookie
0x18001eccd  call    __security_check_cookie
0x18001ecd2  lea     r11, [rsp+2B8h+var_28]
0x18001ecda  mov     rbx, [r11+40h]
0x18001ecde  mov     rbp, [r11+48h]
0x18001ece2  mov     rsp, r11
0x18001ece5  pop     r15
0x18001ece7  pop     r14
0x18001ece9  pop     r12
0x18001eceb  pop     rdi
0x18001ecec  pop     rsi
0x18001eced  retn
```
