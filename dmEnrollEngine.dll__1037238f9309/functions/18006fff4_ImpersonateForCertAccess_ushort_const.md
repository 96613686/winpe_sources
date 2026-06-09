# ImpersonateForCertAccess(ushort const *)

- ea: `0x18006fff4`
- end: `0x18007010c`
- name: `?ImpersonateForCertAccess@@YAJPEBG@Z`
- size: `280`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18002d48c`
- `0x18004f260`

## callees

- `0x180019e8c`
- `0x18002e1a0`
- `0x18006fff4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800700d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800700ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800700d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800700ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800700c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800700de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800700c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800700de`
- `RPCRT4!UuidFromStringW` at `0x18007002a`
- `RPCRT4!UuidFromStringW` at `0x18007002a`
- `DMCmnUtils!DmImpersonate` at `0x1800700a8`
- `DMCmnUtils!DmImpersonate` at `0x1800700a8`
- `DMCmnUtils!InvStrCmpIW` at `0x180070077`
- `DMCmnUtils!InvStrCmpIW` at `0x180070077`

## pseudocode

```c
__int64 __fastcall ImpersonateForCertAccess(unsigned __int16 *a1)
{
  int EnrollmentString; // ebx
  HANDLE ProcessHeap; // rax
  HANDLE v3; // rax
  unsigned __int16 *v5; // [rsp+20h] [rbp-40h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-38h] BYREF
  struct _GUID v7; // [rsp+30h] [rbp-30h] BYREF
  UUID Uuid; // [rsp+40h] [rbp-20h] BYREF

  lpMem = 0;
  v5 = 0;
  Uuid = 0;
  if ( UuidFromStringW(a1, &Uuid) )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v7 = Uuid;
    EnrollmentString = EEDBManager::GetEnrollmentString(&v7, L"SslCertStore", &v5);
    if ( EnrollmentString >= 0 )
    {
      if ( !v5 )
        return (unsigned int)EnrollmentString;
      if ( !InvStrCmpIW(v5, L"User") )
      {
        v7 = Uuid;
        EnrollmentString = EEDBManager::GetEnrollmentString(&v7, L"SID", (unsigned __int16 **)&lpMem);
        if ( EnrollmentString >= 0 )
        {
          EnrollmentString = DmImpersonate((const unsigned __int16 *)lpMem);
          if ( EnrollmentString >= 0 )
            byte_1800B0724 = 1;
        }
        if ( lpMem )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, lpMem);
        }
      }
    }
    if ( v5 )
    {
      v3 = GetProcessHeap();
      HeapFree(v3, 0, v5);
    }
  }
  return (unsigned int)EnrollmentString;
}

```

## disassembly

```asm
0x18006fff4  mov     [rsp-8+arg_8], rbx
0x18006fff9  push    rbp
0x18006fffa  mov     rbp, rsp
0x18006fffd  sub     rsp, 60h
0x180070001  mov     rax, cs:__security_cookie
0x180070008  xor     rax, rsp
0x18007000b  mov     [rbp+var_10], rax
0x18007000f  xorps   xmm0, xmm0
0x180070012  mov     [rbp+lpMem], 0
0x18007001a  lea     rdx, [rbp+Uuid]; Uuid
0x18007001e  mov     [rbp+var_40], 0
0x180070026  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x18007002a  call    cs:__imp_UuidFromStringW
0x180070030  test    eax, eax
0x180070032  jz      short loc_18007003E
0x180070034  mov     ebx, 80070057h
0x180070039  jmp     loc_1800700F3
0x18007003e  movaps  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x180070042  lea     r8, [rbp+var_40]; unsigned __int16 **
0x180070046  lea     rdx, aSslcertstore; "SslCertStore"
0x18007004d  movdqa  xmmword ptr [rbp+var_30.Data1], xmm0
0x180070052  lea     rcx, [rbp+var_30]; struct _GUID
0x180070056  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x18007005b  mov     ebx, eax
0x18007005d  test    eax, eax
0x18007005f  js      short loc_1800700D7
0x180070061  cmp     [rbp+var_40], 0
0x180070066  jz      loc_1800700F3
0x18007006c  mov     rcx, [rbp+var_40]
0x180070070  lea     rdx, aUser; "User"
0x180070077  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x18007007d  test    eax, eax
0x18007007f  jnz     short loc_1800700D7
0x180070081  movaps  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x180070085  lea     r8, [rbp+lpMem]; unsigned __int16 **
0x180070089  lea     rdx, aSid; "SID"
0x180070090  movdqa  xmmword ptr [rbp+var_30.Data1], xmm0
0x180070095  lea     rcx, [rbp+var_30]; struct _GUID
0x180070099  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x18007009e  mov     ebx, eax
0x1800700a0  test    eax, eax
0x1800700a2  js      short loc_1800700BB
0x1800700a4  mov     rcx, [rbp+lpMem]
0x1800700a8  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x1800700ae  mov     ebx, eax
0x1800700b0  test    eax, eax
0x1800700b2  js      short loc_1800700BB
0x1800700b4  mov     cs:byte_1800B0724, 1
0x1800700bb  cmp     [rbp+lpMem], 0
0x1800700c0  jz      short loc_1800700D7
0x1800700c2  call    cs:__imp_GetProcessHeap
0x1800700c8  mov     r8, [rbp+lpMem]; lpMem
0x1800700cc  xor     edx, edx; dwFlags
0x1800700ce  mov     rcx, rax; hHeap
0x1800700d1  call    cs:__imp_HeapFree
0x1800700d7  cmp     [rbp+var_40], 0
0x1800700dc  jz      short loc_1800700F3
0x1800700de  call    cs:__imp_GetProcessHeap
0x1800700e4  mov     r8, [rbp+var_40]; lpMem
0x1800700e8  xor     edx, edx; dwFlags
0x1800700ea  mov     rcx, rax; hHeap
0x1800700ed  call    cs:__imp_HeapFree
0x1800700f3  mov     eax, ebx
0x1800700f5  mov     rcx, [rbp+var_10]
0x1800700f9  xor     rcx, rsp; StackCookie
0x1800700fc  call    __security_check_cookie
0x180070101  mov     rbx, [rsp+60h+arg_8]
0x180070106  add     rsp, 60h
0x18007010a  pop     rbp
0x18007010b  retn
```
