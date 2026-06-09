# SspTelemetry::ClientImageInfo::ClientImageInfo(_LSA_SECPKG_FUNCTION_TABLE *)

- ea: `0x1800398c0`
- end: `0x180039ac2`
- name: `??0ClientImageInfo@SspTelemetry@@QEAA@PEAU_LSA_SECPKG_FUNCTION_TABLE@@@Z`
- size: `514`
- prototype: `__int64 __fastcall(SspTelemetry::ClientImageInfo *__hidden this, struct _LSA_SECPKG_FUNCTION_TABLE *)`
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009c60`
- `0x18002c9b8`
- `0x18004855c`
- `0x180048690`
- `0x18008d00c`
- `0x18008d6c4`
- `0x18008d898`
- `0x18008da84`
- `0x1800d56f4`

## callees

- `0x1800398c0`
- `0x180070680`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800399f7`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800399f7`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x180039a84`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x180039a84`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180039a0c`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180039a5c`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180039a6e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180039a0c`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180039a5c`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180039a6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039a27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039a27`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180039983`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180039983`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800399bc`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800399bc`

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
  DWORD dwSize[4]; // [rsp+50h] [rbp-258h] BYREF
  WCHAR ExeName[264]; // [rsp+60h] [rbp-248h] BYREF

  *(_QWORD *)dwSize = this;
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
    if ( *((_DWORD *)this + 2) == dword_180146C70 )
    {
      _o_wcsncpy_s(v3, 256, &Filename, -1);
LABEL_12:
      _o_wcsncpy_s(v4, 256, &Filename, -1);
      _o_wcsncat_s(v4, 256, &Ext, -1);
      *((_DWORD *)this + 392) = *((_DWORD *)this + 2);
      return this;
    }
    if ( _InterlockedCompareExchange16(&word_180146A60, 1, 0) != 1 )
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
            _o_wcsncpy_s(v3, 256, &Filename, -1);
          }
        }
        CloseHandle(v6);
      }
      dword_180146C70 = *((_DWORD *)this + 2);
      word_180146A60 = 0;
      goto LABEL_12;
    }
  }
  return this;
}

```

## disassembly

```asm
0x1800398c0  mov     [rsp+arg_10], rbx
0x1800398c5  mov     [rsp+arg_18], rbp
0x1800398ca  push    rsi
0x1800398cb  push    rdi
0x1800398cc  push    r12
0x1800398ce  push    r14
0x1800398d0  push    r15
0x1800398d2  sub     rsp, 280h
0x1800398d9  mov     rax, cs:__security_cookie
0x1800398e0  xor     rax, rsp
0x1800398e3  mov     [rsp+2A8h+var_38], rax
0x1800398eb  mov     rbx, rcx
0x1800398ee  mov     qword ptr [rsp+2A8h+dwSize], rcx
0x1800398f3  xorps   xmm0, xmm0
0x1800398f6  movups  xmmword ptr [rcx+628h], xmm0
0x1800398fd  xorps   xmm1, xmm1
0x180039900  movups  xmmword ptr [rcx+638h], xmm1
0x180039907  mov     qword ptr [rcx+648h], 0
0x180039912  lea     r15, [rcx+20h]
0x180039916  xor     eax, eax
0x180039918  mov     [r15], ax
0x18003991c  lea     r12, [rcx+220h]
0x180039923  mov     [r12], ax
0x180039928  mov     [rcx+620h], eax
0x18003992e  mov     rax, [rdx+80h]
0x180039935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003993a  test    eax, eax
0x18003993c  js      loc_180039A93
0x180039942  mov     eax, cs:dword_180146C70
0x180039948  cmp     [rbx+8], eax
0x18003994b  jz      loc_180039A41
0x180039951  xor     eax, eax
0x180039953  lea     ecx, [rax+1]
0x180039956  lock cmpxchg cs:word_180146A60, cx
0x18003995f  cmp     ax, cx
0x180039962  jz      loc_180039A93
0x180039968  xor     eax, eax
0x18003996a  mov     cs:Filename, ax
0x180039971  mov     cs:Ext, ax
0x180039978  mov     r8d, [rbx+8]; dwProcessId
0x18003997c  xor     edx, edx; bInheritHandle
0x18003997e  mov     ecx, 1000h; dwDesiredAccess
0x180039983  call    cs:__imp_OpenProcess
0x180039989  mov     r14, rax
0x18003998c  mov     edi, 100h
0x180039991  lea     rsi, Filename
0x180039998  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18003999c  test    rax, rax
0x18003999f  jz      loc_180039A2D
0x1800399a5  mov     [rsp+2A8h+dwSize], 104h
0x1800399ad  lea     r9, [rsp+2A8h+dwSize]; lpdwSize
0x1800399b2  lea     r8, [rsp+2A8h+ExeName]; lpExeName
0x1800399b7  xor     edx, edx; dwFlags
0x1800399b9  mov     rcx, rax; hProcess
0x1800399bc  call    cs:__imp_QueryFullProcessImageNameW
0x1800399c2  test    eax, eax
0x1800399c4  jz      short loc_180039A24
0x1800399c6  mov     [rsp+2A8h+ExtCount], rdi; ExtCount
0x1800399cb  lea     rax, Ext
0x1800399d2  mov     [rsp+2A8h+Ext], rax; Ext
0x1800399d7  mov     [rsp+2A8h+FilenameCount], rdi; FilenameCount
0x1800399dc  mov     [rsp+2A8h+Filename], rsi; Filename
0x1800399e1  mov     [rsp+2A8h+DirCount], 0; DirCount
0x1800399ea  xor     r9d, r9d; Dir
0x1800399ed  xor     r8d, r8d; DriveCount
0x1800399f0  xor     edx, edx; Drive
0x1800399f2  lea     rcx, [rsp+2A8h+ExeName]; FullPath
0x1800399f7  call    cs:__imp__wsplitpath_s
0x1800399fd  test    eax, eax
0x1800399ff  jnz     short loc_180039A14
0x180039a01  mov     r9, rbp
0x180039a04  mov     r8, rsi
0x180039a07  mov     edx, edi
0x180039a09  mov     rcx, r15
0x180039a0c  call    cs:__imp__o_wcsncpy_s
0x180039a12  jmp     short loc_180039A24
0x180039a14  xor     eax, eax
0x180039a16  mov     cs:Filename, ax
0x180039a1d  mov     cs:Ext, ax
0x180039a24  mov     rcx, r14; hObject
0x180039a27  call    cs:__imp_CloseHandle
0x180039a2d  mov     eax, [rbx+8]
0x180039a30  mov     cs:dword_180146C70, eax
0x180039a36  xor     eax, eax
0x180039a38  xchg    ax, cs:word_180146A60
0x180039a3f  jmp     short loc_180039A62
0x180039a41  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180039a45  mov     r9, rbp
0x180039a48  lea     rsi, Filename
0x180039a4f  mov     r8, rsi
0x180039a52  mov     edi, 100h
0x180039a57  mov     edx, edi
0x180039a59  mov     rcx, r15
0x180039a5c  call    cs:__imp__o_wcsncpy_s
0x180039a62  mov     r9, rbp
0x180039a65  mov     r8, rsi
0x180039a68  mov     rdx, rdi
0x180039a6b  mov     rcx, r12
0x180039a6e  call    cs:__imp__o_wcsncpy_s
0x180039a74  mov     r9, rbp
0x180039a77  lea     r8, Ext
0x180039a7e  mov     rdx, rdi
0x180039a81  mov     rcx, r12
0x180039a84  call    cs:__imp__o_wcsncat_s
0x180039a8a  mov     ecx, [rbx+8]
0x180039a8d  mov     [rbx+620h], ecx
0x180039a93  mov     rax, rbx
0x180039a96  mov     rcx, [rsp+2A8h+var_38]
0x180039a9e  xor     rcx, rsp; StackCookie
0x180039aa1  call    __security_check_cookie
0x180039aa6  lea     r11, [rsp+2A8h+var_28]
0x180039aae  mov     rbx, [r11+40h]
0x180039ab2  mov     rbp, [r11+48h]
0x180039ab6  mov     rsp, r11
0x180039ab9  pop     r15
0x180039abb  pop     r14
0x180039abd  pop     r12
0x180039abf  pop     rdi
0x180039ac0  pop     rsi
0x180039ac1  retn
```
