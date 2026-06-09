# CreateSecurityDescriptorForUser(ushort const *,int,void * *)

- ea: `0x180013094`
- end: `0x18001315c`
- name: `?CreateSecurityDescriptorForUser@@YAJPEBGHPEAPEAX@Z`
- size: `200`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, LPCWSTR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012ea4`

## callees

- `0x1800045d0`
- `0x18000a074`
- `0x18000f61c`
- `0x18000f9c8`
- `0x180013094`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001312a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001312a`

## pseudocode

```c
__int64 __fastcall CreateSecurityDescriptorForUser(const unsigned __int16 *a1, int a2, LPCWSTR *a3)
{
  const wchar_t *v3; // rdi
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rsi
  int v9; // ebx
  const unsigned __int16 *v10; // r8
  WCHAR *v11; // rdi
  BOOL v12; // eax
  LPCWSTR StringSecurityDescriptor; // [rsp+70h] [rbp+18h] BYREF

  *a3 = 0;
  v3 = L"D:PAI(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)(A;OICI;FA;;;%s)(A;;0x00100020;;;S-1-15-3-65536-599108337-2355189375-1353122"
        "160-3480128286-3345335107-485756383-4087318168-230526575)";
  if ( !a2 )
    v3 = L"D:PAI(A;OICI;FA;;;SY)(A;OICI;FA;;;%s)(A;;0x00100020;;;S-1-15-3-65536-599108337-2355189375-1353122160-3480128286"
          "-3345335107-485756383-4087318168-230526575)";
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( a1[v7] );
  do
    ++v6;
  while ( v3[v6] );
  v8 = v7 + v6;
  StringSecurityDescriptor = 0;
  v9 = ResultFromHeapAllocArray<unsigned short>(v7 + v6 + 1, &StringSecurityDescriptor);
  if ( v9 >= 0 )
  {
    v10 = v3;
    v11 = (WCHAR *)StringSecurityDescriptor;
    v9 = StringCchPrintfW((unsigned __int16 *)StringSecurityDescriptor, v8 + 1, v10, a1);
    if ( v9 >= 0 )
    {
      StringSecurityDescriptor = 0;
      v12 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
              v11,
              1u,
              (PSECURITY_DESCRIPTOR *)&StringSecurityDescriptor,
              0);
      v9 = ResultFromWin32Bool(v12);
      if ( v9 >= 0 )
        *a3 = StringSecurityDescriptor;
    }
    ResultFromHeapFree(v11);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180013094  push    rbx
0x180013096  push    rbp
0x180013097  push    rsi
0x180013098  push    rdi
0x180013099  push    r14
0x18001309b  push    r15
0x18001309d  sub     rsp, 28h
0x1800130a1  xor     r15d, r15d
0x1800130a4  lea     rax, aDPaiAOiciFaSyA_0; "D:PAI(A;OICI;FA;;;SY)(A;OICI;FA;;;%s)(A"...
0x1800130ab  test    edx, edx
0x1800130ad  mov     [r8], r15
0x1800130b0  lea     rdi, aDPaiAOiciFaSyA; "D:PAI(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)(A"...
0x1800130b7  mov     r14, r8
0x1800130ba  cmovz   rdi, rax
0x1800130be  mov     rbp, rcx
0x1800130c1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800130c5  mov     rdx, rax
0x1800130c8  inc     rdx
0x1800130cb  cmp     [rcx+rdx*2], r15w
0x1800130d0  jnz     short loc_1800130C8
0x1800130d2  inc     rax
0x1800130d5  cmp     [rdi+rax*2], r15w
0x1800130da  jnz     short loc_1800130D2
0x1800130dc  lea     rsi, [rdx+rax]
0x1800130e0  mov     [rsp+58h+StringSecurityDescriptor], r15
0x1800130e5  lea     rcx, [rsi+1]
0x1800130e9  lea     rdx, [rsp+58h+StringSecurityDescriptor]
0x1800130ee  call    ??$ResultFromHeapAllocArray@G@@YAJ_KPEAPEAG@Z; ResultFromHeapAllocArray<ushort>(unsigned __int64,ushort * *)
0x1800130f3  mov     ebx, eax
0x1800130f5  test    eax, eax
0x1800130f7  js      short loc_18001314D
0x1800130f9  mov     r8, rdi; unsigned __int16 *
0x1800130fc  lea     rdx, [rsi+1]; unsigned __int64
0x180013100  mov     rdi, [rsp+58h+StringSecurityDescriptor]
0x180013105  mov     r9, rbp
0x180013108  mov     rcx, rdi; unsigned __int16 *
0x18001310b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013110  mov     ebx, eax
0x180013112  test    eax, eax
0x180013114  js      short loc_180013145
0x180013116  xor     r9d, r9d; SecurityDescriptorSize
0x180013119  mov     [rsp+58h+StringSecurityDescriptor], r15
0x18001311e  lea     r8, [rsp+58h+StringSecurityDescriptor]; SecurityDescriptor
0x180013123  mov     rcx, rdi; StringSecurityDescriptor
0x180013126  lea     edx, [r9+1]; StringSDRevision
0x18001312a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180013130  mov     ecx, eax; int
0x180013132  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180013137  mov     ebx, eax
0x180013139  test    eax, eax
0x18001313b  js      short loc_180013145
0x18001313d  mov     rax, [rsp+58h+StringSecurityDescriptor]
0x180013142  mov     [r14], rax
0x180013145  mov     rcx, rdi; lpMem
0x180013148  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18001314d  mov     eax, ebx
0x18001314f  add     rsp, 28h
0x180013153  pop     r15
0x180013155  pop     r14
0x180013157  pop     rdi
0x180013158  pop     rsi
0x180013159  pop     rbp
0x18001315a  pop     rbx
0x18001315b  retn
```
