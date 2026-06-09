# CreateLocalManagementEnrollment(void)

- ea: `0x1800063cc`
- end: `0x180006481`
- name: `?CreateLocalManagementEnrollment@@YAJXZ`
- size: `181`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005c00`

## callees

- `0x180001660`
- `0x1800063cc`
- `0x180007010`

## import_xrefs

- `dmEnrollEngine!EnrollEngineInitialize` at `0x1800063fc`
- `dmEnrollEngine!EnrollEngineInitialize` at `0x1800063fc`
- `dmEnrollEngine!__imp_SetProviderID` at `0x180006446`
- `dmEnrollEngine!__imp_SetProviderID` at `0x180006446`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 CreateLocalManagementEnrollment(void)
{
  int v0; // ebx
  __int64 v2; // [rsp+20h] [rbp-48h] BYREF
  __int128 v3; // [rsp+30h] [rbp-38h] BYREF
  __int128 v4; // [rsp+40h] [rbp-28h] BYREF

  v2 = 0;
  v4 = 0;
  v0 = EnrollEngineInitialize(1, 0, &v2);
  if ( v0 >= 0 )
  {
    v0 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v2 + 64LL))(v2, 20, &v4);
    if ( v0 >= 0 )
    {
      v3 = v4;
      v0 = SetProviderID(&v3, L"Local_Management");
    }
  }
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 112LL))(v2);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1800063cc  push    rbx
0x1800063ce  sub     rsp, 60h
0x1800063d2  mov     rax, cs:__security_cookie
0x1800063d9  xor     rax, rsp
0x1800063dc  mov     [rsp+68h+var_18], rax
0x1800063e1  mov     [rsp+68h+var_48], 0
0x1800063ea  xorps   xmm0, xmm0
0x1800063ed  movups  [rsp+68h+var_28], xmm0
0x1800063f2  lea     r8, [rsp+68h+var_48]
0x1800063f7  xor     edx, edx
0x1800063f9  lea     ecx, [rdx+1]
0x1800063fc  call    cs:__imp_EnrollEngineInitialize
0x180006403  nop     dword ptr [rax+rax+00h]
0x180006408  mov     ebx, eax
0x18000640a  test    eax, eax
0x18000640c  js      short loc_180006454
0x18000640e  mov     rcx, [rsp+68h+var_48]
0x180006413  mov     rax, [rcx]
0x180006416  lea     r8, [rsp+68h+var_28]
0x18000641b  mov     edx, 14h
0x180006420  mov     rax, [rax+40h]
0x180006424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006429  mov     ebx, eax
0x18000642b  test    eax, eax
0x18000642d  js      short loc_180006454
0x18000642f  movaps  xmm0, [rsp+68h+var_28]
0x180006434  movdqa  [rsp+68h+var_38], xmm0
0x18000643a  lea     rdx, aLocalManagemen; "Local_Management"
0x180006441  lea     rcx, [rsp+68h+var_38]
0x180006446  call    cs:__imp_SetProviderID
0x18000644d  nop     dword ptr [rax+rax+00h]
0x180006452  mov     ebx, eax
0x180006454  mov     rcx, [rsp+68h+var_48]
0x180006459  test    rcx, rcx
0x18000645c  jz      short loc_18000646B
0x18000645e  mov     rax, [rcx]
0x180006461  mov     rax, [rax+70h]
0x180006465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000646a  nop
0x18000646b  mov     eax, ebx
0x18000646d  mov     rcx, [rsp+68h+var_18]
0x180006472  xor     rcx, rsp; StackCookie
0x180006475  call    __security_check_cookie
0x18000647a  add     rsp, 60h
0x18000647e  pop     rbx
0x18000647f  retn
```
