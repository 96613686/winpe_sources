# PsmSrvTimerElapsedResourceTimeGet

- ea: `0x18002c640`
- end: `0x18002c7e6`
- name: `PsmSrvTimerElapsedResourceTimeGet`
- size: `422`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800065a0`
- `0x180006f5c`
- `0x180009b40`
- `0x18000a750`
- `0x18001622c`
- `0x18002478c`
- `0x18002c640`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18002c69d`
- `ntdll!RtlLengthSid` at `0x18002c69d`
- `ntdll!RtlValidSid` at `0x18002c6ae`
- `ntdll!RtlValidSid` at `0x18002c6ae`

## pseudocode

```c
__int64 __fastcall PsmSrvTimerElapsedResourceTimeGet(
        __int64 a1,
        unsigned int a2,
        void *a3,
        int a4,
        int a5,
        int a6,
        __int64 a7,
        int a8,
        __int64 a9,
        _QWORD *a10,
        _QWORD *a11,
        _QWORD *a12,
        _QWORD *a13,
        _QWORD *a14)
{
  __int64 v16; // rax
  __int64 v17; // rdi
  void *v18; // rsi
  int v19; // ebx
  __int64 v21; // [rsp+50h] [rbp-41h] BYREF
  __int64 v22; // [rsp+58h] [rbp-39h] BYREF
  __int64 v23; // [rsp+60h] [rbp-31h] BYREF
  __int64 v24; // [rsp+68h] [rbp-29h] BYREF
  __int64 v25; // [rsp+70h] [rbp-21h] BYREF
  __int64 v26; // [rsp+78h] [rbp-19h] BYREF
  __int64 *v27; // [rsp+80h] [rbp-11h] BYREF

  v24 = 0;
  v23 = 0;
  v26 = 0;
  v25 = 0;
  v22 = 0;
  v21 = 0;
  v27 = 0;
  if ( a2 >= 2 && RtlLengthSid(a3) == a2 && RtlValidSid(a3) )
  {
    v16 = PsmpResourceAwareTimerFind((_DWORD)a3, a4, a5, a6, a7, a8, a9, (__int64)&v21, (__int64)&v27);
    v17 = v21;
    v18 = (void *)v16;
    if ( v16 )
    {
      v19 = PsmpResourceAwareTimerElapsedResourceTimeGet(
              v16,
              v21,
              (unsigned int)&v22,
              (unsigned int)&v23,
              (__int64)&v24,
              (__int64)&v25,
              (__int64)&v26);
      if ( v19 >= 0 )
      {
        v19 = 0;
        *a10 = v22;
        *a11 = v23;
        *a12 = v24;
        *a13 = v25;
        *a14 = v26;
      }
      PsmpResourceAwareTimerDereference(v18);
    }
    else
    {
      v19 = -1073741275;
    }
    if ( v27 )
      PsmpDereferenceHostContext(v27, 0);
    if ( v17 )
      PsmpDereferenceApplicationEx(v17, 0);
  }
  else
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids);
    return (unsigned int)-1073741811;
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18002c640  push    rbp
0x18002c642  push    rbx
0x18002c643  push    rsi
0x18002c644  push    rdi
0x18002c645  lea     rbp, [rsp-7]
0x18002c64a  sub     rsp, 98h
0x18002c651  mov     [rbp+1Fh+var_48], 0
0x18002c659  mov     esi, r9d
0x18002c65c  mov     [rbp+1Fh+var_50], 0
0x18002c664  mov     rbx, r8
0x18002c667  mov     [rbp+1Fh+var_38], 0
0x18002c66f  mov     edi, edx
0x18002c671  mov     [rbp+1Fh+var_40], 0
0x18002c679  mov     [rbp+1Fh+var_58], 0
0x18002c681  mov     [rbp+1Fh+var_60], 0
0x18002c689  mov     [rbp+1Fh+var_30], 0
0x18002c691  cmp     edx, 2
0x18002c694  jb      loc_18002C7AB
0x18002c69a  mov     rcx, rbx; Sid
0x18002c69d  call    cs:__imp_RtlLengthSid
0x18002c6a3  cmp     eax, edi
0x18002c6a5  jnz     loc_18002C7AB
0x18002c6ab  mov     rcx, rbx; Sid
0x18002c6ae  call    cs:__imp_RtlValidSid
0x18002c6b4  test    al, al
0x18002c6b6  jz      loc_18002C7AB
0x18002c6bc  mov     r9d, [rbp+1Fh+arg_28]
0x18002c6c0  lea     rax, [rbp+1Fh+var_30]
0x18002c6c4  mov     r8, [rbp+1Fh+arg_20]
0x18002c6c8  mov     edx, esi
0x18002c6ca  mov     [rsp+0B0h+var_70], rax
0x18002c6cf  mov     rcx, rbx
0x18002c6d2  lea     rax, [rbp+1Fh+var_60]
0x18002c6d6  mov     [rsp+0B0h+var_78], rax
0x18002c6db  mov     rax, [rbp+1Fh+arg_40]
0x18002c6df  mov     [rsp+0B0h+var_80], rax
0x18002c6e4  mov     eax, [rbp+1Fh+arg_38]
0x18002c6e7  mov     dword ptr [rsp+0B0h+var_88], eax
0x18002c6eb  mov     rax, [rbp+1Fh+arg_30]
0x18002c6ef  mov     [rsp+0B0h+var_90], rax
0x18002c6f4  call    PsmpResourceAwareTimerFind
0x18002c6f9  mov     rdi, [rbp+1Fh+var_60]
0x18002c6fd  mov     rsi, rax
0x18002c700  test    rax, rax
0x18002c703  jnz     short loc_18002C70C
0x18002c705  mov     ebx, 0C0000225h
0x18002c70a  jmp     short loc_18002C78A
0x18002c70c  lea     rax, [rbp+1Fh+var_38]
0x18002c710  mov     rdx, rdi
0x18002c713  mov     [rsp+0B0h+var_80], rax
0x18002c718  lea     r9, [rbp+1Fh+var_50]
0x18002c71c  lea     rax, [rbp+1Fh+var_40]
0x18002c720  mov     rcx, rsi
0x18002c723  mov     [rsp+0B0h+var_88], rax
0x18002c728  lea     r8, [rbp+1Fh+var_58]
0x18002c72c  lea     rax, [rbp+1Fh+var_48]
0x18002c730  mov     [rsp+0B0h+var_90], rax
0x18002c735  call    PsmpResourceAwareTimerElapsedResourceTimeGet
0x18002c73a  mov     ebx, eax
0x18002c73c  test    eax, eax
0x18002c73e  js      short loc_18002C782
0x18002c740  mov     rcx, [rbp+1Fh+arg_48]
0x18002c744  xor     ebx, ebx
0x18002c746  mov     rax, [rbp+1Fh+var_58]
0x18002c74a  mov     [rcx], rax
0x18002c74d  mov     rcx, [rbp+1Fh+arg_50]
0x18002c751  mov     rax, [rbp+1Fh+var_50]
0x18002c755  mov     [rcx], rax
0x18002c758  mov     rcx, [rbp+1Fh+arg_58]
0x18002c75f  mov     rax, [rbp+1Fh+var_48]
0x18002c763  mov     [rcx], rax
0x18002c766  mov     rcx, [rbp+1Fh+arg_60]
0x18002c76d  mov     rax, [rbp+1Fh+var_40]
0x18002c771  mov     [rcx], rax
0x18002c774  mov     rcx, [rbp+1Fh+arg_68]
0x18002c77b  mov     rax, [rbp+1Fh+var_38]
0x18002c77f  mov     [rcx], rax
0x18002c782  mov     rcx, rsi; P
0x18002c785  call    PsmpResourceAwareTimerDereference
0x18002c78a  mov     rcx, [rbp+1Fh+var_30]
0x18002c78e  test    rcx, rcx
0x18002c791  jz      short loc_18002C79A
0x18002c793  xor     edx, edx
0x18002c795  call    PsmpDereferenceHostContext
0x18002c79a  test    rdi, rdi
0x18002c79d  jz      short loc_18002C7D8
0x18002c79f  xor     edx, edx
0x18002c7a1  mov     rcx, rdi
0x18002c7a4  call    PsmpDereferenceApplicationEx
0x18002c7a9  jmp     short loc_18002C7D8
0x18002c7ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c7b2  test    byte ptr [rcx+1Ch], 2
0x18002c7b6  jz      short loc_18002C7D3
0x18002c7b8  cmp     byte ptr [rcx+19h], 2
0x18002c7bc  jb      short loc_18002C7D3
0x18002c7be  mov     rcx, [rcx+10h]
0x18002c7c2  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002c7c9  mov     edx, 31h ; '1'
0x18002c7ce  call    WPP_SF_
0x18002c7d3  mov     ebx, 0C000000Dh
0x18002c7d8  mov     eax, ebx
0x18002c7da  add     rsp, 98h
0x18002c7e1  pop     rdi
0x18002c7e2  pop     rsi
0x18002c7e3  pop     rbx
0x18002c7e4  pop     rbp
0x18002c7e5  retn
```
