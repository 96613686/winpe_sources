# ImpersonateForCertAccess(ushort const *)

- ea: `0x18002438c`
- end: `0x1800244a0`
- name: `?ImpersonateForCertAccess@@YAJPEBG@Z`
- size: `276`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180023e0c`

## callees

- `0x1800039f0`
- `0x18002438c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002445d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002447a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002445d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002447a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002444f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002446c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002444f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002446c`
- `dmEnrollEngine!GetEnrollmentSID` at `0x180024423`
- `dmEnrollEngine!GetEnrollmentSID` at `0x180024423`
- `dmEnrollEngine!GetEnrollmentCertStore` at `0x1800243e9`
- `dmEnrollEngine!GetEnrollmentCertStore` at `0x1800243e9`
- `RPCRT4!UuidFromStringW` at `0x1800243c7`
- `RPCRT4!UuidFromStringW` at `0x1800243c7`
- `DMCmnUtils!InvStrCmpIW` at `0x180024408`
- `DMCmnUtils!InvStrCmpIW` at `0x180024408`
- `DMCmnUtils!DmImpersonate` at `0x180024433`
- `DMCmnUtils!DmImpersonate` at `0x180024433`

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
              byte_180051144 = 1;
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
0x18002438c  mov     [rsp-8+arg_8], rbx
0x180024391  mov     [rsp-8+arg_10], rdi
0x180024396  push    rbp
0x180024397  mov     rbp, rsp
0x18002439a  sub     rsp, 60h
0x18002439e  mov     rax, cs:__security_cookie
0x1800243a5  xor     rax, rsp
0x1800243a8  mov     [rbp+var_10], rax
0x1800243ac  xorps   xmm0, xmm0
0x1800243af  mov     [rbp+lpMem], 0
0x1800243b7  lea     rdx, [rbp+Uuid]; Uuid
0x1800243bb  mov     [rbp+var_38], 0
0x1800243c3  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x1800243c7  call    cs:__imp_UuidFromStringW
0x1800243cd  test    eax, eax
0x1800243cf  jz      short loc_1800243D8
0x1800243d1  mov     ebx, 80070057h
0x1800243d6  jmp     short loc_180024446
0x1800243d8  movaps  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x1800243dc  lea     rdx, [rbp+var_38]
0x1800243e0  lea     rcx, [rbp+var_30]
0x1800243e4  movdqa  [rbp+var_30], xmm0
0x1800243e9  call    cs:__imp_GetEnrollmentCertStore
0x1800243ef  mov     ebx, eax
0x1800243f1  test    eax, eax
0x1800243f3  js      short loc_180024446
0x1800243f5  mov     rdi, [rbp+var_38]
0x1800243f9  test    rdi, rdi
0x1800243fc  jz      short loc_180024446
0x1800243fe  lea     rdx, aUser_0; "User"
0x180024405  mov     rcx, rdi
0x180024408  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x18002440e  test    eax, eax
0x180024410  jnz     short loc_180024446
0x180024412  movaps  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x180024416  lea     rdx, [rbp+lpMem]
0x18002441a  lea     rcx, [rbp+var_30]
0x18002441e  movdqa  [rbp+var_30], xmm0
0x180024423  call    cs:__imp_GetEnrollmentSID
0x180024429  mov     ebx, eax
0x18002442b  test    eax, eax
0x18002442d  js      short loc_180024446
0x18002442f  mov     rcx, [rbp+lpMem]
0x180024433  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x180024439  mov     ebx, eax
0x18002443b  test    eax, eax
0x18002443d  js      short loc_180024446
0x18002443f  mov     cs:byte_180051144, 1
0x180024446  mov     rdi, [rbp+lpMem]
0x18002444a  test    rdi, rdi
0x18002444d  jz      short loc_180024463
0x18002444f  call    cs:__imp_GetProcessHeap
0x180024455  mov     r8, rdi; lpMem
0x180024458  xor     edx, edx; dwFlags
0x18002445a  mov     rcx, rax; hHeap
0x18002445d  call    cs:__imp_HeapFree
0x180024463  mov     rdi, [rbp+var_38]
0x180024467  test    rdi, rdi
0x18002446a  jz      short loc_180024480
0x18002446c  call    cs:__imp_GetProcessHeap
0x180024472  mov     r8, rdi; lpMem
0x180024475  xor     edx, edx; dwFlags
0x180024477  mov     rcx, rax; hHeap
0x18002447a  call    cs:__imp_HeapFree
0x180024480  mov     eax, ebx
0x180024482  mov     rcx, [rbp+var_10]
0x180024486  xor     rcx, rsp; StackCookie
0x180024489  call    __security_check_cookie
0x18002448e  lea     r11, [rsp+60h+var_s0]
0x180024493  mov     rbx, [r11+18h]
0x180024497  mov     rdi, [r11+20h]
0x18002449b  mov     rsp, r11
0x18002449e  pop     rbp
0x18002449f  retn
```
