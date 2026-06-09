# QueryLocalManagementEnrollmentId(_GUID &)

- ea: `0x180006868`
- end: `0x180006930`
- name: `?QueryLocalManagementEnrollmentId@@YAJAEAU_GUID@@@Z`
- size: `200`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800058e0`
- `0x180005c00`
- `0x180005d20`

## callees

- `0x180006868`
- `0x180007010`

## import_xrefs

- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x180006892`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x180006892`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall QueryLocalManagementEnrollmentId(struct _GUID *a1)
{
  __int64 DatabaseManagerInstance; // rax
  int v3; // ebx
  __int64 v4; // rcx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = 0;
  v6 = 0;
  *a1 = GUID_NULL;
  DatabaseManagerInstance = GetDatabaseManagerInstance();
  v3 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)DatabaseManagerInstance + 16LL))(
         DatabaseManagerInstance,
         20,
         &v7);
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 24LL))(v7, &v6);
    if ( v3 >= 0 )
    {
      v4 = v6;
      if ( !v6 )
        goto LABEL_6;
      v3 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v6 + 24LL))(v6, a1);
    }
  }
  v4 = v6;
LABEL_6:
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180006868  mov     [rsp+arg_10], rbx
0x18000686d  push    rdi
0x18000686e  sub     rsp, 20h
0x180006872  mov     rdi, rcx
0x180006875  mov     [rsp+28h+arg_8], 0
0x18000687e  mov     [rsp+28h+arg_0], 0
0x180006887  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000688e  movdqu  xmmword ptr [rcx], xmm0
0x180006892  call    cs:__imp_GetDatabaseManagerInstance
0x180006899  nop     dword ptr [rax+rax+00h]
0x18000689e  mov     rcx, rax
0x1800068a1  mov     rdx, [rax]
0x1800068a4  mov     rax, [rdx+10h]
0x1800068a8  lea     r8, [rsp+28h+arg_8]
0x1800068ad  mov     edx, 14h
0x1800068b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068b7  mov     ebx, eax
0x1800068b9  test    eax, eax
0x1800068bb  js      short loc_1800068F4
0x1800068bd  mov     rcx, [rsp+28h+arg_8]
0x1800068c2  mov     rax, [rcx]
0x1800068c5  lea     rdx, [rsp+28h+arg_0]
0x1800068ca  mov     rax, [rax+18h]
0x1800068ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068d3  mov     ebx, eax
0x1800068d5  test    eax, eax
0x1800068d7  js      short loc_1800068F4
0x1800068d9  mov     rcx, [rsp+28h+arg_0]
0x1800068de  test    rcx, rcx
0x1800068e1  jz      short loc_1800068F9
0x1800068e3  mov     rax, [rcx]
0x1800068e6  mov     rdx, rdi
0x1800068e9  mov     rax, [rax+18h]
0x1800068ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068f2  mov     ebx, eax
0x1800068f4  mov     rcx, [rsp+28h+arg_0]
0x1800068f9  test    rcx, rcx
0x1800068fc  jz      short loc_18000690B
0x1800068fe  mov     rax, [rcx]
0x180006901  mov     rax, [rax+10h]
0x180006905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000690a  nop
0x18000690b  mov     rcx, [rsp+28h+arg_8]
0x180006910  test    rcx, rcx
0x180006913  jz      short loc_180006922
0x180006915  mov     rax, [rcx]
0x180006918  mov     rax, [rax+10h]
0x18000691c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006921  nop
0x180006922  mov     eax, ebx
0x180006924  mov     rbx, [rsp+28h+arg_10]
0x180006929  add     rsp, 20h
0x18000692d  pop     rdi
0x18000692e  retn
```
