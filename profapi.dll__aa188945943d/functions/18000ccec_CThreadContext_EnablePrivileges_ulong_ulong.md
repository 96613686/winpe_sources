# CThreadContext::EnablePrivileges(ulong *,ulong)

- ea: `0x18000ccec`
- end: `0x18000ce35`
- name: `?EnablePrivileges@CThreadContext@@QEAAJPEAKK@Z`
- size: `329`
- prototype: `__int64 __fastcall(CThreadContext *this, unsigned int *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000a2d8`

## callees

- `0x1800061a4`
- `0x180007c60`
- `0x18000a6a0`
- `0x18000a750`
- `0x18000a7a0`
- `0x18000ccec`
- `0x180016960`
- `0x180016a24`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x18000cdd1`
- `ntdll!RtlAdjustPrivilege` at `0x18000cdd1`

## pseudocode

```c
__int64 __fastcall CThreadContext::EnablePrivileges(CThreadContext *this, unsigned int *a2, int a3)
{
  void **v3; // rdi
  int v6; // ebx
  _DWORD **v7; // r14
  _DWORD *v8; // rcx
  int v9; // eax
  CThreadContext *v10; // rcx
  __int64 v11; // rdi
  ULONG v12; // ecx
  NTSTATUS v13; // eax
  SIZE_T dwBytes; // [rsp+50h] [rbp+8h] BYREF
  int OldValue; // [rsp+60h] [rbp+18h] BYREF

  OldValue = a3;
  dwBytes = 0;
  v3 = (void **)((char *)this + 32);
  *((_QWORD *)this + 4) = 0;
  if ( !is_mul_ok(1u, 4u) )
    return (unsigned int)-2147024362;
  v6 = ResultFromHeapAlloc(4u, v3);
  if ( v6 >= 0 )
  {
    v7 = (_DWORD **)((char *)this + 40);
    dwBytes = 0;
    *((_QWORD *)this + 5) = 0;
    v6 = ULongLongMult(1u, 4u, &dwBytes);
    if ( v6 < 0 || (v6 = ResultFromHeapAlloc(dwBytes, (void **)this + 5), v6 < 0) )
    {
      ResultFromHeapFree(*v3);
      *v3 = 0;
      return (unsigned int)v6;
    }
    v8 = *v3;
    v9 = *a2;
    *((_DWORD *)this + 6) = 1;
    *v8 = v9;
    **v7 = 0;
    v6 = CThreadContext::ImpersonateSelf(this);
    if ( v6 >= 0 )
    {
      v11 = 0;
      do
      {
        if ( !(unsigned int)CThreadContext::PrivilegeEnabled(v10, a2[v11]) )
        {
          v12 = a2[v11];
          LOBYTE(OldValue) = 0;
          v13 = RtlAdjustPrivilege(v12, 1u, 1u, (PBOOLEAN)&OldValue);
          v6 = ResultFromWin32FromStatus(v13);
          if ( v6 < 0 )
          {
            CThreadContext::RevertPrivileges(this);
            return (unsigned int)v6;
          }
          if ( !(_BYTE)OldValue )
            (*v7)[v11] = 1;
        }
        v11 = (unsigned int)(v11 + 1);
      }
      while ( !(_DWORD)v11 );
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000ccec  mov     rax, rsp
0x18000ccef  mov     [rax+10h], rbx
0x18000ccf3  mov     [rax+20h], rbp
0x18000ccf7  mov     [rax+18h], r8d
0x18000ccfb  push    rsi
0x18000ccfc  push    rdi
0x18000ccfd  push    r13
0x18000ccff  push    r14
0x18000cd01  push    r15
0x18000cd03  sub     rsp, 20h
0x18000cd07  mov     ebp, 4
0x18000cd0c  mov     qword ptr [rax+8], 0
0x18000cd14  mov     eax, ebp
0x18000cd16  lea     rdi, [rcx+20h]
0x18000cd1a  mov     r15, rdx
0x18000cd1d  mov     qword ptr [rdi], 0
0x18000cd24  mov     rsi, rcx
0x18000cd27  lea     r13d, [rbp-3]
0x18000cd2b  mul     r13
0x18000cd2e  test    rdx, rdx
0x18000cd31  jnz     loc_18000CE17
0x18000cd37  mov     rdx, rdi; void **
0x18000cd3a  mov     rcx, rax; dwBytes
0x18000cd3d  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x18000cd42  mov     ebx, eax
0x18000cd44  test    eax, eax
0x18000cd46  js      loc_18000CE1C
0x18000cd4c  lea     r14, [rsi+28h]
0x18000cd50  mov     [rsp+48h+dwBytes], 0
0x18000cd59  lea     r8, [rsp+48h+dwBytes]; unsigned __int64 *
0x18000cd5e  mov     qword ptr [r14], 0
0x18000cd65  mov     edx, ebp; unsigned __int64
0x18000cd67  mov     ecx, r13d; unsigned __int64
0x18000cd6a  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000cd6f  mov     ebx, eax
0x18000cd71  test    eax, eax
0x18000cd73  js      loc_18000CE06
0x18000cd79  mov     rcx, [rsp+48h+dwBytes]; dwBytes
0x18000cd7e  mov     rdx, r14; void **
0x18000cd81  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x18000cd86  mov     ebx, eax
0x18000cd88  test    eax, eax
0x18000cd8a  js      short loc_18000CE06
0x18000cd8c  mov     rcx, [rdi]
0x18000cd8f  mov     eax, [r15]
0x18000cd92  mov     [rsi+18h], r13d
0x18000cd96  mov     [rcx], eax
0x18000cd98  mov     rcx, rsi; this
0x18000cd9b  mov     rax, [r14]
0x18000cd9e  mov     dword ptr [rax], 0
0x18000cda4  call    ?ImpersonateSelf@CThreadContext@@QEAAJXZ; CThreadContext::ImpersonateSelf(void)
0x18000cda9  mov     ebx, eax
0x18000cdab  test    eax, eax
0x18000cdad  js      short loc_18000CE1C
0x18000cdaf  xor     edi, edi
0x18000cdb1  mov     edx, [r15+rdi*4]; unsigned int
0x18000cdb5  call    ?PrivilegeEnabled@CThreadContext@@QEAAHK@Z; CThreadContext::PrivilegeEnabled(ulong)
0x18000cdba  test    eax, eax
0x18000cdbc  jnz     short loc_18000CDF2
0x18000cdbe  mov     ecx, [r15+rdi*4]; Privilege
0x18000cdc2  lea     r9, [rsp+48h+OldValue]; OldValue
0x18000cdc7  mov     r8b, r13b; ForThread
0x18000cdca  mov     byte ptr [rsp+48h+OldValue], al
0x18000cdce  mov     dl, r13b; NewValue
0x18000cdd1  call    cs:__imp_RtlAdjustPrivilege
0x18000cdd7  mov     ecx, eax; int
0x18000cdd9  call    ?ResultFromWin32FromStatus@@YAJJ@Z; ResultFromWin32FromStatus(long)
0x18000cdde  mov     ebx, eax
0x18000cde0  test    eax, eax
0x18000cde2  js      short loc_18000CDFC
0x18000cde4  cmp     byte ptr [rsp+48h+OldValue], 0
0x18000cde9  jnz     short loc_18000CDF2
0x18000cdeb  mov     rax, [r14]
0x18000cdee  mov     [rax+rdi*4], r13d
0x18000cdf2  add     edi, r13d
0x18000cdf5  cmp     edi, r13d
0x18000cdf8  jb      short loc_18000CDB1
0x18000cdfa  jmp     short loc_18000CE1C
0x18000cdfc  mov     rcx, rsi; this
0x18000cdff  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x18000ce04  jmp     short loc_18000CE1C
0x18000ce06  mov     rcx, [rdi]; lpMem
0x18000ce09  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18000ce0e  mov     qword ptr [rdi], 0
0x18000ce15  jmp     short loc_18000CE1C
0x18000ce17  mov     ebx, 80070216h
0x18000ce1c  mov     rbp, [rsp+48h+arg_18]
0x18000ce21  mov     eax, ebx
0x18000ce23  mov     rbx, [rsp+48h+arg_8]
0x18000ce28  add     rsp, 20h
0x18000ce2c  pop     r15
0x18000ce2e  pop     r14
0x18000ce30  pop     r13
0x18000ce32  pop     rdi
0x18000ce33  pop     rsi
0x18000ce34  retn
```
