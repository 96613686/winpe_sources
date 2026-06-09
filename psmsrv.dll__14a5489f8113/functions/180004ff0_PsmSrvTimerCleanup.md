# PsmSrvTimerCleanup

- ea: `0x180004ff0`
- end: `0x180005168`
- name: `PsmSrvTimerCleanup`
- size: `376`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180004ff0`
- `0x1800065a0`
- `0x180006f5c`
- `0x180009b40`
- `0x18000a750`
- `0x18001622c`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180005024`
- `ntdll!RtlLengthSid` at `0x180005024`
- `ntdll!RtlValidSid` at `0x180005035`
- `ntdll!RtlValidSid` at `0x180005035`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800050b1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800050b1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800050e7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800050e7`

## pseudocode

```c
__int64 __fastcall PsmSrvTimerCleanup(
        __int64 a1,
        unsigned int a2,
        void *a3,
        int a4,
        int a5,
        int a6,
        __int64 a7,
        int a8,
        __int64 a9)
{
  __int64 v11; // rax
  __int64 v12; // rdi
  _QWORD *v13; // rbx
  _QWORD *v14; // rax
  _QWORD *v15; // rcx
  unsigned int v16; // ebx
  __int64 v18; // [rsp+50h] [rbp-18h] BYREF
  __int64 *v19; // [rsp+58h] [rbp-10h] BYREF

  v18 = 0;
  v19 = 0;
  if ( a2 >= 2 && RtlLengthSid(a3) == a2 && RtlValidSid(a3) )
  {
    v11 = PsmpResourceAwareTimerFind((_DWORD)a3, a4, a5, a6, a7, a8, a9, (__int64)&v18, (__int64)&v19);
    v12 = v18;
    v13 = (_QWORD *)v11;
    if ( v11 )
    {
      RtlAcquireSRWLockExclusive(v18 + 328);
      v14 = (_QWORD *)*v13;
      if ( (_QWORD *)*v13 != v13 )
      {
        if ( (_QWORD *)v14[1] != v13 || (v15 = (_QWORD *)v13[1], (_QWORD *)*v15 != v13) )
          __fastfail(3u);
        *v15 = v14;
        v14[1] = v15;
        v13[1] = v13;
        *v13 = v13;
        PsmpResourceAwareTimerDereference(v13);
      }
      RtlReleaseSRWLockExclusive(v12 + 328);
      PsmpResourceAwareTimerDereference(v13);
      v16 = 0;
    }
    else
    {
      v16 = -1073741275;
    }
    if ( v19 )
      PsmpDereferenceHostContext(v19, 0);
    if ( v12 )
      PsmpDereferenceApplicationEx(v12, 0);
  }
  else
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids);
    return (unsigned int)-1073741811;
  }
  return v16;
}

```

## disassembly

```asm
0x180004ff0  mov     rax, rsp
0x180004ff3  mov     [rax+8], rbx
0x180004ff7  mov     [rax+10h], rsi
0x180004ffb  push    rdi
0x180004ffc  sub     rsp, 60h
0x180005000  mov     qword ptr [rax-18h], 0
0x180005008  mov     esi, r9d
0x18000500b  mov     qword ptr [rax-10h], 0
0x180005013  mov     rbx, r8
0x180005016  mov     edi, edx
0x180005018  cmp     edx, 2
0x18000501b  jb      loc_180005129
0x180005021  mov     rcx, rbx; Sid
0x180005024  call    cs:__imp_RtlLengthSid
0x18000502a  cmp     eax, edi
0x18000502c  jnz     loc_180005129
0x180005032  mov     rcx, rbx; Sid
0x180005035  call    cs:__imp_RtlValidSid
0x18000503b  test    al, al
0x18000503d  jz      loc_180005129
0x180005043  mov     r9d, [rsp+68h+arg_28]
0x18000504b  lea     rax, [rsp+68h+var_10]
0x180005050  mov     r8, [rsp+68h+arg_20]
0x180005058  mov     edx, esi
0x18000505a  mov     [rsp+68h+var_28], rax
0x18000505f  mov     rcx, rbx
0x180005062  lea     rax, [rsp+68h+var_18]
0x180005067  mov     [rsp+68h+var_30], rax
0x18000506c  mov     rax, [rsp+68h+arg_40]
0x180005074  mov     [rsp+68h+var_38], rax
0x180005079  mov     eax, [rsp+68h+arg_38]
0x180005080  mov     [rsp+68h+var_40], eax
0x180005084  mov     rax, [rsp+68h+arg_30]
0x18000508c  mov     [rsp+68h+var_48], rax
0x180005091  call    PsmpResourceAwareTimerFind
0x180005096  mov     rdi, [rsp+68h+var_18]
0x18000509b  mov     rbx, rax
0x18000509e  test    rax, rax
0x1800050a1  jz      loc_180005144
0x1800050a7  lea     rsi, [rdi+148h]
0x1800050ae  mov     rcx, rsi
0x1800050b1  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800050b7  mov     rax, [rbx]
0x1800050ba  cmp     rax, rbx
0x1800050bd  jz      short loc_1800050E4
0x1800050bf  cmp     [rax+8], rbx
0x1800050c3  jnz     short loc_18000513D
0x1800050c5  mov     rcx, [rbx+8]
0x1800050c9  cmp     [rcx], rbx
0x1800050cc  jnz     short loc_18000513D
0x1800050ce  mov     [rcx], rax
0x1800050d1  mov     [rax+8], rcx
0x1800050d5  mov     rcx, rbx; P
0x1800050d8  mov     [rbx+8], rbx
0x1800050dc  mov     [rbx], rbx
0x1800050df  call    PsmpResourceAwareTimerDereference
0x1800050e4  mov     rcx, rsi
0x1800050e7  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800050ed  mov     rcx, rbx; P
0x1800050f0  call    PsmpResourceAwareTimerDereference
0x1800050f5  xor     ebx, ebx
0x1800050f7  mov     rcx, [rsp+68h+var_10]
0x1800050fc  test    rcx, rcx
0x1800050ff  jz      short loc_180005108
0x180005101  xor     edx, edx
0x180005103  call    PsmpDereferenceHostContext
0x180005108  test    rdi, rdi
0x18000510b  jz      short loc_180005117
0x18000510d  xor     edx, edx
0x18000510f  mov     rcx, rdi
0x180005112  call    PsmpDereferenceApplicationEx
0x180005117  mov     rsi, [rsp+68h+arg_8]
0x18000511c  mov     eax, ebx
0x18000511e  mov     rbx, [rsp+68h+arg_0]
0x180005123  add     rsp, 60h
0x180005127  pop     rdi
0x180005128  retn
0x180005129  mov     rcx, cs:WPP_GLOBAL_Control
0x180005130  test    byte ptr [rcx+1Ch], 2
0x180005134  jnz     short loc_18000514B
0x180005136  mov     ebx, 0C000000Dh
0x18000513b  jmp     short loc_180005117
0x18000513d  mov     ecx, 3
0x180005142  int     29h; Win8: RtlFailFast(ecx)
0x180005144  mov     ebx, 0C0000225h
0x180005149  jmp     short loc_1800050F7
0x18000514b  cmp     byte ptr [rcx+19h], 2
0x18000514f  jb      short loc_180005136
0x180005151  mov     rcx, [rcx+10h]
0x180005155  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18000515c  mov     edx, 30h ; '0'
0x180005161  call    WPP_SF_
0x180005166  jmp     short loc_180005136
```
