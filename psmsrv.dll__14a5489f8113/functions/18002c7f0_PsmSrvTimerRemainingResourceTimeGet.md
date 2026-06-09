# PsmSrvTimerRemainingResourceTimeGet

- ea: `0x18002c7f0`
- end: `0x18002c945`
- name: `PsmSrvTimerRemainingResourceTimeGet`
- size: `341`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000532c`
- `0x1800065a0`
- `0x180006f5c`
- `0x180009b40`
- `0x18000a750`
- `0x18001622c`
- `0x18002c7f0`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18002c82c`
- `ntdll!RtlLengthSid` at `0x18002c82c`
- `ntdll!RtlValidSid` at `0x18002c83d`
- `ntdll!RtlValidSid` at `0x18002c83d`

## pseudocode

```c
__int64 __fastcall PsmSrvTimerRemainingResourceTimeGet(
        __int64 a1,
        unsigned int a2,
        void *a3,
        int a4,
        int a5,
        int a6,
        __int64 a7,
        int a8,
        __int64 a9,
        _QWORD *a10)
{
  __int64 v12; // rax
  __int64 v13; // rdi
  void *v14; // rsi
  int v15; // ebx
  __int64 v17; // [rsp+50h] [rbp-28h] BYREF
  __int64 v18; // [rsp+58h] [rbp-20h] BYREF
  __int64 *v19; // [rsp+60h] [rbp-18h] BYREF

  v18 = 0;
  v17 = 0;
  v19 = 0;
  if ( a2 >= 2 && RtlLengthSid(a3) == a2 && RtlValidSid(a3) )
  {
    v12 = PsmpResourceAwareTimerFind((_DWORD)a3, a4, a5, a6, a7, a8, a9, (__int64)&v17, (__int64)&v19);
    v13 = v17;
    v14 = (void *)v12;
    if ( v12 )
    {
      v15 = PsmpResourceAwareTimerRemainingTimeGet(v12, v17, &v18);
      if ( v15 >= 0 )
      {
        v15 = 0;
        *a10 = v18;
      }
      PsmpResourceAwareTimerDereference(v14);
    }
    else
    {
      v15 = -1073741275;
    }
    if ( v19 )
      PsmpDereferenceHostContext(v19, 0);
    if ( v13 )
      PsmpDereferenceApplicationEx(v13, 0);
  }
  else
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids);
    return (unsigned int)-1073741811;
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18002c7f0  mov     rax, rsp
0x18002c7f3  mov     [rax+8], rbx
0x18002c7f7  mov     [rax+10h], rsi
0x18002c7fb  push    rdi
0x18002c7fc  sub     rsp, 70h
0x18002c800  mov     qword ptr [rax-20h], 0
0x18002c808  mov     esi, r9d
0x18002c80b  mov     qword ptr [rax-28h], 0
0x18002c813  mov     rbx, r8
0x18002c816  mov     qword ptr [rax-18h], 0
0x18002c81e  mov     edi, edx
0x18002c820  cmp     edx, 2
0x18002c823  jb      loc_18002C904
0x18002c829  mov     rcx, rbx; Sid
0x18002c82c  call    cs:__imp_RtlLengthSid
0x18002c832  cmp     eax, edi
0x18002c834  jnz     loc_18002C904
0x18002c83a  mov     rcx, rbx; Sid
0x18002c83d  call    cs:__imp_RtlValidSid
0x18002c843  test    al, al
0x18002c845  jz      loc_18002C904
0x18002c84b  mov     r9d, [rsp+78h+arg_28]
0x18002c853  lea     rax, [rsp+78h+var_18]
0x18002c858  mov     r8, [rsp+78h+arg_20]
0x18002c860  mov     edx, esi
0x18002c862  mov     [rsp+78h+var_38], rax
0x18002c867  mov     rcx, rbx
0x18002c86a  lea     rax, [rsp+78h+var_28]
0x18002c86f  mov     [rsp+78h+var_40], rax
0x18002c874  mov     rax, [rsp+78h+arg_40]
0x18002c87c  mov     [rsp+78h+var_48], rax
0x18002c881  mov     eax, [rsp+78h+arg_38]
0x18002c888  mov     [rsp+78h+var_50], eax
0x18002c88c  mov     rax, [rsp+78h+arg_30]
0x18002c894  mov     [rsp+78h+var_58], rax
0x18002c899  call    PsmpResourceAwareTimerFind
0x18002c89e  mov     rdi, [rsp+78h+var_28]
0x18002c8a3  mov     rsi, rax
0x18002c8a6  test    rax, rax
0x18002c8a9  jnz     short loc_18002C8B2
0x18002c8ab  mov     ebx, 0C0000225h
0x18002c8b0  jmp     short loc_18002C8E2
0x18002c8b2  lea     r8, [rsp+78h+var_20]
0x18002c8b7  mov     rdx, rdi
0x18002c8ba  mov     rcx, rsi
0x18002c8bd  call    PsmpResourceAwareTimerRemainingTimeGet
0x18002c8c2  mov     ebx, eax
0x18002c8c4  test    eax, eax
0x18002c8c6  js      short loc_18002C8DA
0x18002c8c8  mov     rcx, [rsp+78h+arg_48]
0x18002c8d0  xor     ebx, ebx
0x18002c8d2  mov     rax, [rsp+78h+var_20]
0x18002c8d7  mov     [rcx], rax
0x18002c8da  mov     rcx, rsi; P
0x18002c8dd  call    PsmpResourceAwareTimerDereference
0x18002c8e2  mov     rcx, [rsp+78h+var_18]
0x18002c8e7  test    rcx, rcx
0x18002c8ea  jz      short loc_18002C8F3
0x18002c8ec  xor     edx, edx
0x18002c8ee  call    PsmpDereferenceHostContext
0x18002c8f3  test    rdi, rdi
0x18002c8f6  jz      short loc_18002C931
0x18002c8f8  xor     edx, edx
0x18002c8fa  mov     rcx, rdi
0x18002c8fd  call    PsmpDereferenceApplicationEx
0x18002c902  jmp     short loc_18002C931
0x18002c904  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c90b  test    byte ptr [rcx+1Ch], 2
0x18002c90f  jz      short loc_18002C92C
0x18002c911  cmp     byte ptr [rcx+19h], 2
0x18002c915  jb      short loc_18002C92C
0x18002c917  mov     rcx, [rcx+10h]
0x18002c91b  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002c922  mov     edx, 32h ; '2'
0x18002c927  call    WPP_SF_
0x18002c92c  mov     ebx, 0C000000Dh
0x18002c931  lea     r11, [rsp+78h+var_8]
0x18002c936  mov     eax, ebx
0x18002c938  mov     rbx, [r11+10h]
0x18002c93c  mov     rsi, [r11+18h]
0x18002c940  mov     rsp, r11
0x18002c943  pop     rdi
0x18002c944  retn
```
