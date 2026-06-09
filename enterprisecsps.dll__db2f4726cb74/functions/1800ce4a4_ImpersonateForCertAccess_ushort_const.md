# ImpersonateForCertAccess(ushort const *)

- ea: `0x1800ce4a4`
- end: `0x1800ce5f2`
- name: `?ImpersonateForCertAccess@@YAJPEBG@Z`
- size: `334`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800cddfc`

## callees

- `0x180008de0`
- `0x1800ce4a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ce59c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ce5c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ce59c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ce5c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ce588`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ce5b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ce588`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ce5b1`
- `RPCRT4!UuidFromStringW` at `0x1800ce4df`
- `RPCRT4!UuidFromStringW` at `0x1800ce4df`
- `DMCmnUtils!DmImpersonate` at `0x1800ce566`
- `DMCmnUtils!DmImpersonate` at `0x1800ce566`
- `DMCmnUtils!InvStrCmpIW` at `0x1800ce52f`
- `DMCmnUtils!InvStrCmpIW` at `0x1800ce52f`
- `dmEnrollEngine!GetEnrollmentCertStore` at `0x1800ce50a`
- `dmEnrollEngine!GetEnrollmentCertStore` at `0x1800ce50a`
- `dmEnrollEngine!GetEnrollmentSID` at `0x1800ce550`
- `dmEnrollEngine!GetEnrollmentSID` at `0x1800ce550`

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
              byte_180157D64 = 1;
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
0x1800ce4a4  mov     [rsp-8+arg_8], rbx
0x1800ce4a9  mov     [rsp-8+arg_10], rdi
0x1800ce4ae  push    rbp
0x1800ce4af  mov     rbp, rsp
0x1800ce4b2  sub     rsp, 60h
0x1800ce4b6  mov     rax, cs:__security_cookie
0x1800ce4bd  xor     rax, rsp
0x1800ce4c0  mov     [rbp+var_10], rax
0x1800ce4c4  xorps   xmm0, xmm0
0x1800ce4c7  mov     [rbp+lpMem], 0
0x1800ce4cf  lea     rdx, [rbp+Uuid]; Uuid
0x1800ce4d3  mov     [rbp+var_38], 0
0x1800ce4db  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x1800ce4df  call    cs:__imp_UuidFromStringW
0x1800ce4e6  nop     dword ptr [rax+rax+00h]
0x1800ce4eb  test    eax, eax
0x1800ce4ed  jz      short loc_1800CE4F9
0x1800ce4ef  mov     ebx, 80070057h
0x1800ce4f4  jmp     loc_1800CE57F
0x1800ce4f9  movaps  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x1800ce4fd  lea     rdx, [rbp+var_38]
0x1800ce501  lea     rcx, [rbp+var_30]
0x1800ce505  movdqa  [rbp+var_30], xmm0
0x1800ce50a  call    cs:__imp_GetEnrollmentCertStore
0x1800ce511  nop     dword ptr [rax+rax+00h]
0x1800ce516  mov     ebx, eax
0x1800ce518  test    eax, eax
0x1800ce51a  js      short loc_1800CE57F
0x1800ce51c  mov     rdi, [rbp+var_38]
0x1800ce520  test    rdi, rdi
0x1800ce523  jz      short loc_1800CE57F
0x1800ce525  lea     rdx, aUser_0; "User"
0x1800ce52c  mov     rcx, rdi
0x1800ce52f  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x1800ce536  nop     dword ptr [rax+rax+00h]
0x1800ce53b  test    eax, eax
0x1800ce53d  jnz     short loc_1800CE57F
0x1800ce53f  movaps  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x1800ce543  lea     rdx, [rbp+lpMem]
0x1800ce547  lea     rcx, [rbp+var_30]
0x1800ce54b  movdqa  [rbp+var_30], xmm0
0x1800ce550  call    cs:__imp_GetEnrollmentSID
0x1800ce557  nop     dword ptr [rax+rax+00h]
0x1800ce55c  mov     ebx, eax
0x1800ce55e  test    eax, eax
0x1800ce560  js      short loc_1800CE57F
0x1800ce562  mov     rcx, [rbp+lpMem]
0x1800ce566  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x1800ce56d  nop     dword ptr [rax+rax+00h]
0x1800ce572  mov     ebx, eax
0x1800ce574  test    eax, eax
0x1800ce576  js      short loc_1800CE57F
0x1800ce578  mov     cs:byte_180157D64, 1
0x1800ce57f  mov     rdi, [rbp+lpMem]
0x1800ce583  test    rdi, rdi
0x1800ce586  jz      short loc_1800CE5A8
0x1800ce588  call    cs:__imp_GetProcessHeap
0x1800ce58f  nop     dword ptr [rax+rax+00h]
0x1800ce594  mov     r8, rdi; lpMem
0x1800ce597  xor     edx, edx; dwFlags
0x1800ce599  mov     rcx, rax; hHeap
0x1800ce59c  call    cs:__imp_HeapFree
0x1800ce5a3  nop     dword ptr [rax+rax+00h]
0x1800ce5a8  mov     rdi, [rbp+var_38]
0x1800ce5ac  test    rdi, rdi
0x1800ce5af  jz      short loc_1800CE5D1
0x1800ce5b1  call    cs:__imp_GetProcessHeap
0x1800ce5b8  nop     dword ptr [rax+rax+00h]
0x1800ce5bd  mov     r8, rdi; lpMem
0x1800ce5c0  xor     edx, edx; dwFlags
0x1800ce5c2  mov     rcx, rax; hHeap
0x1800ce5c5  call    cs:__imp_HeapFree
0x1800ce5cc  nop     dword ptr [rax+rax+00h]
0x1800ce5d1  mov     eax, ebx
0x1800ce5d3  mov     rcx, [rbp+var_10]
0x1800ce5d7  xor     rcx, rsp; StackCookie
0x1800ce5da  call    __security_check_cookie
0x1800ce5df  lea     r11, [rsp+60h+var_s0]
0x1800ce5e4  mov     rbx, [r11+18h]
0x1800ce5e8  mov     rdi, [r11+20h]
0x1800ce5ec  mov     rsp, r11
0x1800ce5ef  pop     rbp
0x1800ce5f0  retn
```
