# SecObtainFileHashUsingUserToken

- ea: `0x140022300`
- end: `0x1400223a1`
- name: `SecObtainFileHashUsingUserToken`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140022468`

## callees

- `0x140011650`
- `0x140021b8c`
- `0x140022300`

## import_xrefs

- `ntoskrnl!SeTokenObjectType` at `0x140022324`
- `ntoskrnl!ObfDereferenceObject` at `0x14002237d`
- `ntoskrnl!ObfDereferenceObject` at `0x14002237d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002234f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002234f`

## pseudocode

```c
__int64 __fastcall SecObtainFileHashUsingUserToken(__int64 a1, void *a2, __int64 a3)
{
  int v5; // ebx
  PVOID Object; // [rsp+30h] [rbp-28h] BYREF

  Object = 0;
  v5 = ObReferenceObjectByHandle(a2, 0xCu, (POBJECT_TYPE)SeTokenObjectType, 1, &Object, 0);
  if ( v5 >= 0 )
    v5 = SecImpersonateAndObtainFileHash(a1, Object, a3);
  if ( Object )
    ObfDereferenceObject(Object);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140022300  mov     r11, rsp
0x140022303  push    rbx
0x140022304  push    rsi
0x140022305  push    rdi
0x140022306  sub     rsp, 40h
0x14002230a  mov     rax, cs:__security_cookie
0x140022311  xor     rax, rsp
0x140022314  mov     [rsp+58h+var_20], rax
0x140022319  mov     rsi, r8
0x14002231c  mov     qword ptr [r11-30h], 0
0x140022324  mov     r8, cs:__imp_SeTokenObjectType
0x14002232b  mov     rdi, rcx
0x14002232e  lea     rcx, [r11-28h]
0x140022332  mov     qword ptr [r11-28h], 0
0x14002233a  mov     rax, rdx
0x14002233d  mov     [r11-38h], rcx
0x140022341  mov     r9b, 1; AccessMode
0x140022344  mov     edx, 0Ch; DesiredAccess
0x140022349  mov     r8, [r8]; ObjectType
0x14002234c  mov     rcx, rax; Handle
0x14002234f  call    cs:__imp_ObReferenceObjectByHandle
0x140022356  nop     dword ptr [rax+rax+00h]
0x14002235b  mov     ebx, eax
0x14002235d  test    eax, eax
0x14002235f  js      short loc_140022373
0x140022361  mov     rdx, [rsp+58h+Object]
0x140022366  mov     r8, rsi
0x140022369  mov     rcx, rdi
0x14002236c  call    SecImpersonateAndObtainFileHash
0x140022371  mov     ebx, eax
0x140022373  mov     rcx, [rsp+58h+Object]; Object
0x140022378  test    rcx, rcx
0x14002237b  jz      short loc_140022389
0x14002237d  call    cs:__imp_ObfDereferenceObject
0x140022384  nop     dword ptr [rax+rax+00h]
0x140022389  mov     eax, ebx
0x14002238b  mov     rcx, [rsp+58h+var_20]
0x140022390  xor     rcx, rsp; StackCookie
0x140022393  call    __security_check_cookie
0x140022398  add     rsp, 40h
0x14002239c  pop     rdi
0x14002239d  pop     rsi
0x14002239e  pop     rbx
0x14002239f  retn
```
