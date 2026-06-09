# CDRMStore::CreateSidAndSecurityDescriptor(void)

- ea: `0x180035184`
- end: `0x18003528b`
- name: `?CreateSidAndSecurityDescriptor@CDRMStore@@AEAAJXZ`
- size: `263`
- prototype: `__int64 __fastcall(CDRMStore *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180036fc8`

## callees

- `0x180001244`
- `0x180001284`
- `0x180017358`
- `0x180035184`
- `0x18004cedc`
- `0x18005bd72`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003525f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003525f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180035255`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180035255`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800351a1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800351b3`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800351a1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800351b3`

## pseudocode

```c
__int64 __fastcall CDRMStore::CreateSidAndSecurityDescriptor(CDRMStore *this)
{
  LPWSTR *v1; // rsi
  unsigned __int16 *v3; // rbp
  void *v4; // rcx
  signed int v5; // ebx
  __int64 v6; // rax
  unsigned __int64 v7; // rbx
  unsigned __int16 *v8; // rax
  signed int LastError; // eax

  v1 = (LPWSTR *)((char *)this + 48);
  v3 = 0;
  LocalFree(*((HLOCAL *)this + 6));
  v4 = (void *)*((_QWORD *)this + 4);
  *v1 = 0;
  if ( v4 )
    LocalFree(v4);
  *(_OWORD *)((char *)this + 24) = 0;
  *((_QWORD *)this + 5) = 0;
  v5 = UDGetProcessUserSIDStringW(v1);
  if ( v5 >= 0 )
  {
    v6 = -1;
    do
      ++v6;
    while ( (*v1)[v6] );
    v7 = v6 + 51;
    v8 = (unsigned __int16 *)operator new(saturated_mul(v6 + 51, 2u));
    v3 = v8;
    if ( v8 )
    {
      memset_0(v8, 0, 2 * v7);
      v5 = StringCchPrintfW(v3, v7, L"D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OICI;GA;;;%s)", *v1);
      if ( v5 >= 0 )
      {
        *((_DWORD *)this + 6) = 24;
        *((_DWORD *)this + 10) = 0;
        if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v3, 1u, (PSECURITY_DESCRIPTOR *)this + 4, 0) )
        {
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError > 0 )
            v5 = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
    else
    {
      v5 = -2147024882;
    }
  }
  operator delete(v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180035184  push    rbx
0x180035186  push    rbp
0x180035187  push    rsi
0x180035188  push    rdi
0x180035189  push    r14
0x18003518b  push    r15
0x18003518d  sub     rsp, 28h
0x180035191  lea     rsi, [rcx+30h]
0x180035195  mov     rdi, rcx
0x180035198  mov     rcx, [rsi]; hMem
0x18003519b  xor     r15d, r15d
0x18003519e  mov     ebp, r15d
0x1800351a1  call    cs:__imp_LocalFree
0x1800351a7  mov     rcx, [rdi+20h]; hMem
0x1800351ab  mov     [rsi], r15
0x1800351ae  test    rcx, rcx
0x1800351b1  jz      short loc_1800351B9
0x1800351b3  call    cs:__imp_LocalFree
0x1800351b9  xorps   xmm0, xmm0
0x1800351bc  xor     eax, eax
0x1800351be  movups  xmmword ptr [rdi+18h], xmm0
0x1800351c2  mov     rcx, rsi; StringSid
0x1800351c5  mov     [rdi+28h], rax
0x1800351c9  call    ?UDGetProcessUserSIDStringW@@YAJPEAPEAG@Z; UDGetProcessUserSIDStringW(ushort * *)
0x1800351ce  mov     ebx, eax
0x1800351d0  test    eax, eax
0x1800351d2  js      loc_180035274
0x1800351d8  mov     rcx, [rsi]
0x1800351db  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800351df  mov     rax, r8
0x1800351e2  inc     rax
0x1800351e5  cmp     [rcx+rax*2], r15w
0x1800351ea  jnz     short loc_1800351E2
0x1800351ec  lea     rbx, [rax+33h]
0x1800351f0  mov     eax, 2
0x1800351f5  mul     rbx
0x1800351f8  cmovb   rax, r8
0x1800351fc  mov     rcx, rax; Size
0x1800351ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035204  mov     rbp, rax
0x180035207  test    rax, rax
0x18003520a  jnz     short loc_180035213
0x18003520c  mov     ebx, 8007000Eh
0x180035211  jmp     short loc_180035274
0x180035213  lea     r8, [rbx+rbx]; Size
0x180035217  xor     edx, edx; Val
0x180035219  mov     rcx, rbp; void *
0x18003521c  call    memset_0
0x180035221  mov     r9, [rsi]
0x180035224  lea     r8, aDAOiciGaBaAOic; "D:(A;OICI;GA;;;BA)(A;OICI;GA;;;SY)(A;OI"...
0x18003522b  mov     rdx, rbx; unsigned __int64
0x18003522e  mov     rcx, rbp; unsigned __int16 *
0x180035231  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180035236  mov     ebx, eax
0x180035238  test    eax, eax
0x18003523a  js      short loc_180035274
0x18003523c  xor     r9d, r9d; SecurityDescriptorSize
0x18003523f  mov     dword ptr [rdi+18h], 18h
0x180035246  lea     r8, [rdi+20h]; SecurityDescriptor
0x18003524a  mov     [rdi+28h], r15d
0x18003524e  mov     rcx, rbp; StringSecurityDescriptor
0x180035251  lea     edx, [r9+1]; StringSDRevision
0x180035255  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18003525b  test    eax, eax
0x18003525d  jnz     short loc_180035274
0x18003525f  call    cs:__imp_GetLastError
0x180035265  mov     ebx, eax
0x180035267  test    eax, eax
0x180035269  jle     short loc_180035274
0x18003526b  movzx   ebx, ax
0x18003526e  or      ebx, 80070000h
0x180035274  mov     rcx, rbp; Block
0x180035277  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003527c  mov     eax, ebx
0x18003527e  add     rsp, 28h
0x180035282  pop     r15
0x180035284  pop     r14
0x180035286  pop     rdi
0x180035287  pop     rsi
0x180035288  pop     rbp
0x180035289  pop     rbx
0x18003528a  retn
```
