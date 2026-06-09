# ImpersonateForCertAccess(ushort const *)

- ea: `0x18001d97c`
- end: `0x18001da90`
- name: `?ImpersonateForCertAccess@@YAJPEBG@Z`
- size: `276`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18001d3fc`

## callees

- `0x1800022e0`
- `0x18001d97c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001da3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001da5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001da3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001da5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001da4d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001da6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001da4d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001da6a`
- `dmEnrollEngine!GetEnrollmentSID` at `0x18001da13`
- `dmEnrollEngine!GetEnrollmentSID` at `0x18001da13`
- `dmEnrollEngine!GetEnrollmentCertStore` at `0x18001d9d9`
- `dmEnrollEngine!GetEnrollmentCertStore` at `0x18001d9d9`
- `DMCmnUtils!DmImpersonate` at `0x18001da23`
- `DMCmnUtils!DmImpersonate` at `0x18001da23`
- `DMCmnUtils!InvStrCmpIW` at `0x18001d9f8`
- `DMCmnUtils!InvStrCmpIW` at `0x18001d9f8`
- `RPCRT4!UuidFromStringW` at `0x18001d9b7`
- `RPCRT4!UuidFromStringW` at `0x18001d9b7`

## pseudocode

```c
__int64 __fastcall ImpersonateForCertAccess(unsigned __int16 *a1)
{
  int EnrollmentCertStore; // ebx
  void *v2; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rdi
  HANDLE v5; // rax
  LPVOID lpMem; // [rsp+20h] [rbp-40h] BYREF
  LPVOID v8; // [rsp+28h] [rbp-38h] BYREF
  UUID v9; // [rsp+30h] [rbp-30h] BYREF
  UUID Uuid; // [rsp+40h] [rbp-20h] BYREF

  lpMem = 0;
  v8 = 0;
  Uuid = 0;
  if ( UuidFromStringW(a1, &Uuid) )
  {
    EnrollmentCertStore = -2147024809;
  }
  else
  {
    v9 = Uuid;
    EnrollmentCertStore = GetEnrollmentCertStore(&v9, &v8);
    if ( EnrollmentCertStore >= 0 )
    {
      if ( v8 )
      {
        if ( !InvStrCmpIW((const unsigned __int16 *)v8, L"User") )
        {
          v9 = Uuid;
          EnrollmentCertStore = GetEnrollmentSID(&v9, &lpMem);
          if ( EnrollmentCertStore >= 0 )
          {
            EnrollmentCertStore = DmImpersonate((const unsigned __int16 *)lpMem);
            if ( EnrollmentCertStore >= 0 )
              byte_18002B844 = 1;
          }
        }
      }
    }
  }
  v2 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  v4 = v8;
  if ( v8 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
  }
  return (unsigned int)EnrollmentCertStore;
}

```

## disassembly

```asm
0x18001d97c  mov     [rsp-8+arg_8], rbx
0x18001d981  mov     [rsp-8+arg_10], rdi
0x18001d986  push    rbp
0x18001d987  mov     rbp, rsp
0x18001d98a  sub     rsp, 60h
0x18001d98e  mov     rax, cs:__security_cookie
0x18001d995  xor     rax, rsp
0x18001d998  mov     [rbp+var_10], rax
0x18001d99c  xorps   xmm0, xmm0
0x18001d99f  mov     [rbp+lpMem], 0
0x18001d9a7  lea     rdx, [rbp+Uuid]; Uuid
0x18001d9ab  mov     [rbp+var_38], 0
0x18001d9b3  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x18001d9b7  call    cs:__imp_UuidFromStringW
0x18001d9bd  test    eax, eax
0x18001d9bf  jz      short loc_18001D9C8
0x18001d9c1  mov     ebx, 80070057h
0x18001d9c6  jmp     short loc_18001DA36
0x18001d9c8  movaps  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x18001d9cc  lea     rdx, [rbp+var_38]
0x18001d9d0  lea     rcx, [rbp+var_30]
0x18001d9d4  movdqa  [rbp+var_30], xmm0
0x18001d9d9  call    cs:__imp_GetEnrollmentCertStore
0x18001d9df  mov     ebx, eax
0x18001d9e1  test    eax, eax
0x18001d9e3  js      short loc_18001DA36
0x18001d9e5  mov     rdi, [rbp+var_38]
0x18001d9e9  test    rdi, rdi
0x18001d9ec  jz      short loc_18001DA36
0x18001d9ee  lea     rdx, aUser; "User"
0x18001d9f5  mov     rcx, rdi
0x18001d9f8  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x18001d9fe  test    eax, eax
0x18001da00  jnz     short loc_18001DA36
0x18001da02  movaps  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x18001da06  lea     rdx, [rbp+lpMem]
0x18001da0a  lea     rcx, [rbp+var_30]
0x18001da0e  movdqa  [rbp+var_30], xmm0
0x18001da13  call    cs:__imp_GetEnrollmentSID
0x18001da19  mov     ebx, eax
0x18001da1b  test    eax, eax
0x18001da1d  js      short loc_18001DA36
0x18001da1f  mov     rcx, [rbp+lpMem]
0x18001da23  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x18001da29  mov     ebx, eax
0x18001da2b  test    eax, eax
0x18001da2d  js      short loc_18001DA36
0x18001da2f  mov     cs:byte_18002B844, 1
0x18001da36  mov     rdi, [rbp+lpMem]
0x18001da3a  test    rdi, rdi
0x18001da3d  jz      short loc_18001DA53
0x18001da3f  call    cs:__imp_GetProcessHeap
0x18001da45  mov     r8, rdi; lpMem
0x18001da48  xor     edx, edx; dwFlags
0x18001da4a  mov     rcx, rax; hHeap
0x18001da4d  call    cs:__imp_HeapFree
0x18001da53  mov     rdi, [rbp+var_38]
0x18001da57  test    rdi, rdi
0x18001da5a  jz      short loc_18001DA70
0x18001da5c  call    cs:__imp_GetProcessHeap
0x18001da62  mov     r8, rdi; lpMem
0x18001da65  xor     edx, edx; dwFlags
0x18001da67  mov     rcx, rax; hHeap
0x18001da6a  call    cs:__imp_HeapFree
0x18001da70  mov     eax, ebx
0x18001da72  mov     rcx, [rbp+var_10]
0x18001da76  xor     rcx, rsp; StackCookie
0x18001da79  call    __security_check_cookie
0x18001da7e  lea     r11, [rsp+60h+var_s0]
0x18001da83  mov     rbx, [r11+18h]
0x18001da87  mov     rdi, [r11+20h]
0x18001da8b  mov     rsp, r11
0x18001da8e  pop     rbp
0x18001da8f  retn
```
