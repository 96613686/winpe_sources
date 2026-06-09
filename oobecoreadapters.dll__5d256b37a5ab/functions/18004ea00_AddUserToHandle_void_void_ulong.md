# AddUserToHandle(void *,void *,ulong)

- ea: `0x18004ea00`
- end: `0x18004ebfe`
- name: `?AddUserToHandle@@YAJPEAX0K@Z`
- size: `510`
- prototype: `__int64 __fastcall(HANDLE Handle, void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004ec04`

## callees

- `0x180005a9c`
- `0x1800076d4`
- `0x18004ea00`
- `0x18004eda4`
- `0x18005318c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ea6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004eb5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ebb0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ebd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ea6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004eb5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ebb0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ebd1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004ea79`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004ea79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004eb69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ebbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ebdf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004eb69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ebbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ebdf`
- `ntdll!NtQuerySecurityObject` at `0x18004ea33`
- `ntdll!NtQuerySecurityObject` at `0x18004eabf`
- `ntdll!NtQuerySecurityObject` at `0x18004ea33`
- `ntdll!NtQuerySecurityObject` at `0x18004eabf`
- `ntdll!NtSetSecurityObject` at `0x18004eb83`
- `ntdll!NtSetSecurityObject` at `0x18004eb83`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18004eae8`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18004eae8`

## string_xrefs

- `0x18004ea48`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x18004ea8b`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x18004eafb`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x18004eb3a`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x18004eb91`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

## pseudocode

```c
int __fastcall AddUserToHandle(HANDLE Handle, void *a2, ACCESS_MASK a3)
{
  NTSTATUS v6; // eax
  ULONG v8; // ebx
  HANDLE ProcessHeap; // rax
  void *v10; // rsi
  int v11; // ebx
  NTSTATUS v12; // eax
  __int64 v13; // rdx
  int v14; // eax
  void *v15; // rdi
  HANDLE v16; // rax
  NTSTATUS v17; // eax
  int v18; // eax
  void *v19; // rbx
  int v20; // edi
  HANDLE v21; // rax
  void *v22; // rbx
  HANDLE v23; // rax
  int LengthNeeded; // [rsp+20h] [rbp-48h]
  int LengthNeededa; // [rsp+20h] [rbp-48h]
  int LengthNeededb; // [rsp+20h] [rbp-48h]
  ULONG Length; // [rsp+30h] [rbp-38h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+38h] [rbp-30h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]
  bool v31; // [rsp+B8h] [rbp+50h] BYREF

  Length = 0;
  v6 = NtQuerySecurityObject(Handle, 4u, 0, 0, &Length);
  if ( v6 == -1073741789 )
  {
    v8 = Length;
    ProcessHeap = GetProcessHeap();
    v10 = HeapAlloc(ProcessHeap, 0, v8);
    if ( !v10 )
    {
      v11 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
        (const char *)0x8007000ELL,
        LengthNeeded);
      return v11;
    }
    v12 = NtQuerySecurityObject(Handle, 4u, v10, Length, &Length);
    if ( v12 >= 0 )
    {
      lpMem = 0;
      memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
      v12 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      if ( v12 >= 0 )
      {
        v31 = 0;
        v14 = BuildUserSD(v10, a2, a3, &v31, SecurityDescriptor);
        v11 = v14;
        if ( v14 >= 0 )
        {
          if ( v31 || (v17 = NtSetSecurityObject(Handle, 4u, SecurityDescriptor), v17 >= 0) )
          {
            v22 = lpMem;
            if ( lpMem )
            {
              v23 = GetProcessHeap();
              HeapFree(v23, 0, v22);
            }
            v11 = 0;
          }
          else
          {
            v18 = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x79,
                    (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
                    (const char *)(unsigned int)v17,
                    LengthNeededb);
            v19 = lpMem;
            v20 = v18;
            if ( lpMem )
            {
              v21 = GetProcessHeap();
              HeapFree(v21, 0, v19);
            }
            v11 = v20;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x72,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
            (const char *)(unsigned int)v14,
            LengthNeededb);
          v15 = lpMem;
          if ( lpMem )
          {
            v16 = GetProcessHeap();
            HeapFree(v16, 0, v15);
          }
        }
        goto LABEL_23;
      }
      v13 = 108;
    }
    else
    {
      v13 = 105;
    }
    v11 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v13,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
            (const char *)(unsigned int)v12,
            LengthNeededa);
LABEL_23:
    MemoryFree(v10);
    return v11;
  }
  if ( v6 >= 0 )
    return 0;
  else
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x62,
             (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
             (const char *)(unsigned int)v6,
             LengthNeeded);
}

```

## disassembly

```asm
0x18004ea00  push    rbp
0x18004ea02  push    rbx
0x18004ea03  push    rsi
0x18004ea04  push    rdi
0x18004ea05  push    r14
0x18004ea07  push    r15
0x18004ea09  mov     rbp, rsp
0x18004ea0c  sub     rsp, 68h
0x18004ea10  xor     r9d, r9d; Length
0x18004ea13  mov     [rbp+Length], 0
0x18004ea1a  mov     r14d, r8d
0x18004ea1d  lea     rax, [rbp+Length]
0x18004ea21  mov     r15, rdx
0x18004ea24  mov     qword ptr [rsp+68h+LengthNeeded], rax; int
0x18004ea29  xor     r8d, r8d; SecurityDescriptor
0x18004ea2c  mov     rdi, rcx
0x18004ea2f  lea     edx, [r9+4]; SecurityInformation
0x18004ea33  call    cs:__imp_NtQuerySecurityObject
0x18004ea39  cmp     eax, 0C0000023h
0x18004ea3e  jz      short loc_18004EA68
0x18004ea40  test    eax, eax
0x18004ea42  jns     short loc_18004EA61
0x18004ea44  mov     rcx, [rbp+30h]; this
0x18004ea48  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18004ea4f  mov     r9d, eax; char *
0x18004ea52  mov     edx, 62h ; 'b'; void *
0x18004ea57  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004ea5c  jmp     loc_18004EBF1
0x18004ea61  xor     eax, eax
0x18004ea63  jmp     loc_18004EBF1
0x18004ea68  mov     ebx, [rbp+Length]
0x18004ea6b  call    cs:__imp_GetProcessHeap
0x18004ea71  mov     r8d, ebx; dwBytes
0x18004ea74  xor     edx, edx; dwFlags
0x18004ea76  mov     rcx, rax; hHeap
0x18004ea79  call    cs:__imp_HeapAlloc
0x18004ea7f  mov     rsi, rax
0x18004ea82  test    rax, rax
0x18004ea85  jnz     short loc_18004EAA7
0x18004ea87  mov     rcx, [rbp+30h]; this
0x18004ea8b  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18004ea92  mov     ebx, 8007000Eh
0x18004ea97  lea     edx, [rax+66h]; void *
0x18004ea9a  mov     r9d, ebx; char *
0x18004ea9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eaa2  jmp     loc_18004EBEF
0x18004eaa7  mov     r9d, [rbp+Length]; Length
0x18004eaab  lea     rax, [rbp+Length]
0x18004eaaf  mov     r8, rsi; SecurityDescriptor
0x18004eab2  mov     qword ptr [rsp+68h+LengthNeeded], rax; int
0x18004eab7  mov     edx, 4; SecurityInformation
0x18004eabc  mov     rcx, rdi; Handle
0x18004eabf  call    cs:__imp_NtQuerySecurityObject
0x18004eac5  test    eax, eax
0x18004eac7  jns     short loc_18004EAD0
0x18004eac9  mov     edx, 69h ; 'i'
0x18004eace  jmp     short loc_18004EAF7
0x18004ead0  xor     eax, eax
0x18004ead2  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18004ead6  xorps   xmm0, xmm0
0x18004ead9  mov     [rbp+lpMem], rax
0x18004eadd  movups  [rbp+SecurityDescriptor], xmm0
0x18004eae1  lea     edx, [rax+1]; Revision
0x18004eae4  movups  [rbp+var_20], xmm0
0x18004eae8  call    cs:__imp_RtlCreateSecurityDescriptor
0x18004eaee  test    eax, eax
0x18004eaf0  jns     short loc_18004EB11
0x18004eaf2  mov     edx, 6Ch ; 'l'; void *
0x18004eaf7  mov     rcx, [rbp+30h]; this
0x18004eafb  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18004eb02  mov     r9d, eax; char *
0x18004eb05  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004eb0a  mov     ebx, eax
0x18004eb0c  jmp     loc_18004EBE7
0x18004eb11  lea     rax, [rbp+SecurityDescriptor]
0x18004eb15  mov     [rbp+arg_18], 0
0x18004eb19  lea     r9, [rbp+arg_18]; bool *
0x18004eb1d  mov     qword ptr [rsp+68h+LengthNeeded], rax; int
0x18004eb22  mov     r8d, r14d; unsigned int
0x18004eb25  mov     rdx, r15; void *
0x18004eb28  mov     rcx, rsi; void *
0x18004eb2b  call    ?BuildUserSD@@YAJPEAX0KPEA_N0@Z; BuildUserSD(void *,void *,ulong,bool *,void *)
0x18004eb30  mov     ebx, eax
0x18004eb32  test    eax, eax
0x18004eb34  jns     short loc_18004EB71
0x18004eb36  mov     rcx, [rbp+30h]; this
0x18004eb3a  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18004eb41  mov     r9d, eax; char *
0x18004eb44  mov     edx, 72h ; 'r'; void *
0x18004eb49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eb4e  mov     rdi, [rbp+lpMem]
0x18004eb52  test    rdi, rdi
0x18004eb55  jz      loc_18004EBE7
0x18004eb5b  call    cs:__imp_GetProcessHeap
0x18004eb61  mov     r8, rdi; lpMem
0x18004eb64  xor     edx, edx; dwFlags
0x18004eb66  mov     rcx, rax; hHeap
0x18004eb69  call    cs:__imp_HeapFree
0x18004eb6f  jmp     short loc_18004EBE7
0x18004eb71  cmp     [rbp+arg_18], 0
0x18004eb75  jnz     short loc_18004EBC8
0x18004eb77  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18004eb7b  mov     edx, 4; SecurityInformation
0x18004eb80  mov     rcx, rdi; Handle
0x18004eb83  call    cs:__imp_NtSetSecurityObject
0x18004eb89  test    eax, eax
0x18004eb8b  jns     short loc_18004EBC8
0x18004eb8d  mov     rcx, [rbp+30h]; this
0x18004eb91  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x18004eb98  mov     r9d, eax; char *
0x18004eb9b  mov     edx, 79h ; 'y'; void *
0x18004eba0  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004eba5  mov     rbx, [rbp+lpMem]
0x18004eba9  mov     edi, eax
0x18004ebab  test    rbx, rbx
0x18004ebae  jz      short loc_18004EBC4
0x18004ebb0  call    cs:__imp_GetProcessHeap
0x18004ebb6  mov     r8, rbx; lpMem
0x18004ebb9  xor     edx, edx; dwFlags
0x18004ebbb  mov     rcx, rax; hHeap
0x18004ebbe  call    cs:__imp_HeapFree
0x18004ebc4  mov     ebx, edi
0x18004ebc6  jmp     short loc_18004EBE7
0x18004ebc8  mov     rbx, [rbp+lpMem]
0x18004ebcc  test    rbx, rbx
0x18004ebcf  jz      short loc_18004EBE5
0x18004ebd1  call    cs:__imp_GetProcessHeap
0x18004ebd7  mov     r8, rbx; lpMem
0x18004ebda  xor     edx, edx; dwFlags
0x18004ebdc  mov     rcx, rax; hHeap
0x18004ebdf  call    cs:__imp_HeapFree
0x18004ebe5  xor     ebx, ebx
0x18004ebe7  mov     rcx, rsi; void *
0x18004ebea  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18004ebef  mov     eax, ebx
0x18004ebf1  add     rsp, 68h
0x18004ebf5  pop     r15
0x18004ebf7  pop     r14
0x18004ebf9  pop     rdi
0x18004ebfa  pop     rsi
0x18004ebfb  pop     rbx
0x18004ebfc  pop     rbp
0x18004ebfd  retn
```
