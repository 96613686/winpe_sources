# CreateSecurityDescriptorForUser(ushort const *,int,void * *)

- ea: `0x18000cba8`
- end: `0x18000cc5f`
- name: `?CreateSecurityDescriptorForUser@@YAJPEBGHPEAPEAX@Z`
- size: `183`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, LPCWSTR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000caa0`

## callees

- `0x180003330`
- `0x1800063e0`
- `0x180007c60`
- `0x18000a6d0`
- `0x18000cba8`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000cc27`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000cc27`

## pseudocode

```c
__int64 __fastcall CreateSecurityDescriptorForUser(const unsigned __int16 *a1, __int64 a2, LPCWSTR *a3)
{
  __int64 v4; // rax
  unsigned __int64 v6; // rbp
  int v7; // ebx
  const unsigned __int16 *v8; // r9
  WCHAR *v9; // rdi
  BOOL v10; // eax
  LPCWSTR StringSecurityDescriptor; // [rsp+50h] [rbp+18h] BYREF

  *a3 = 0;
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  v6 = v4 + 171;
  StringSecurityDescriptor = 0;
  v7 = ResultFromHeapAllocArray<unsigned short>(v4 + 171, &StringSecurityDescriptor);
  if ( v7 >= 0 )
  {
    v8 = a1;
    v9 = (WCHAR *)StringSecurityDescriptor;
    v7 = StringCchPrintfW(
           (unsigned __int16 *)StringSecurityDescriptor,
           v6,
           L"D:PAI(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)(A;OICI;FA;;;%s)(A;;0x00100020;;;S-1-15-3-65536-599108337-2355189375-135"
            "3122160-3480128286-3345335107-485756383-4087318168-230526575)",
           v8);
    if ( v7 >= 0 )
    {
      StringSecurityDescriptor = 0;
      v10 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
              v9,
              1u,
              (PSECURITY_DESCRIPTOR *)&StringSecurityDescriptor,
              0);
      v7 = ResultFromWin32Bool(v10);
      if ( v7 >= 0 )
        *a3 = StringSecurityDescriptor;
    }
    ResultFromHeapFree(v9);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000cba8  mov     [rsp+arg_0], rbx
0x18000cbad  mov     [rsp+arg_8], rbp
0x18000cbb2  push    rsi
0x18000cbb3  push    rdi
0x18000cbb4  push    r14
0x18000cbb6  sub     rsp, 20h
0x18000cbba  xor     r14d, r14d
0x18000cbbd  mov     rsi, r8
0x18000cbc0  mov     [r8], r14
0x18000cbc3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000cbc7  mov     rdi, rcx
0x18000cbca  inc     rax
0x18000cbcd  cmp     [rcx+rax*2], r14w
0x18000cbd2  jnz     short loc_18000CBCA
0x18000cbd4  lea     rbp, [rax+0ABh]
0x18000cbdb  mov     [rsp+38h+StringSecurityDescriptor], r14
0x18000cbe0  mov     rcx, rbp
0x18000cbe3  lea     rdx, [rsp+38h+StringSecurityDescriptor]
0x18000cbe8  call    ??$ResultFromHeapAllocArray@G@@YAJ_KPEAPEAG@Z; ResultFromHeapAllocArray<ushort>(unsigned __int64,ushort * *)
0x18000cbed  mov     ebx, eax
0x18000cbef  test    eax, eax
0x18000cbf1  js      short loc_18000CC4A
0x18000cbf3  mov     r9, rdi
0x18000cbf6  lea     r8, aDPaiAOiciFaSyA; "D:PAI(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)(A"...
0x18000cbfd  mov     rdi, [rsp+38h+StringSecurityDescriptor]
0x18000cc02  mov     rdx, rbp; unsigned __int64
0x18000cc05  mov     rcx, rdi; unsigned __int16 *
0x18000cc08  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000cc0d  mov     ebx, eax
0x18000cc0f  test    eax, eax
0x18000cc11  js      short loc_18000CC42
0x18000cc13  xor     r9d, r9d; SecurityDescriptorSize
0x18000cc16  mov     [rsp+38h+StringSecurityDescriptor], r14
0x18000cc1b  lea     r8, [rsp+38h+StringSecurityDescriptor]; SecurityDescriptor
0x18000cc20  mov     rcx, rdi; StringSecurityDescriptor
0x18000cc23  lea     edx, [r9+1]; StringSDRevision
0x18000cc27  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000cc2d  mov     ecx, eax; int
0x18000cc2f  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18000cc34  mov     ebx, eax
0x18000cc36  test    eax, eax
0x18000cc38  js      short loc_18000CC42
0x18000cc3a  mov     rax, [rsp+38h+StringSecurityDescriptor]
0x18000cc3f  mov     [rsi], rax
0x18000cc42  mov     rcx, rdi; lpMem
0x18000cc45  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18000cc4a  mov     rbp, [rsp+38h+arg_8]
0x18000cc4f  mov     eax, ebx
0x18000cc51  mov     rbx, [rsp+38h+arg_0]
0x18000cc56  add     rsp, 20h
0x18000cc5a  pop     r14
0x18000cc5c  pop     rdi
0x18000cc5d  pop     rsi
0x18000cc5e  retn
```
