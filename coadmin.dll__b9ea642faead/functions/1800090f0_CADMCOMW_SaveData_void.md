# CADMCOMW::SaveData(void)

- ea: `0x1800090f0`
- end: `0x1800091f3`
- name: `?SaveData@CADMCOMW@@UEAAJXZ`
- size: `259`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000716c`
- `0x1800090f0`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::SaveData(CADMCOMW *this)
{
  int v2; // ebx
  __int64 v3; // rcx
  unsigned int v5; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v6; // [rsp+80h] [rbp+18h] BYREF

  v5 = 0;
  v6 = 0;
  v2 = CADMCOMW::LookupAndAccessCheck(this, 0, &v6, (__int64)&byte_1800127D8, 1u, 0, 0, 0, 0, 0, 0);
  if ( v2 >= 0 )
  {
    v3 = *((_QWORD *)this + 101);
    if ( !v3 || (v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 192LL))(v3), v2 >= 0) )
    {
      v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, int, unsigned int *))(**((_QWORD **)this + 4)
                                                                                           + 280LL))(
             *((_QWORD *)this + 4),
             0,
             0,
             1,
             5000,
             &v5);
      if ( v2 >= 0 )
        v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 4) + 304LL))(*((_QWORD *)this + 4), v5);
    }
  }
  if ( v5 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 288LL))(*((_QWORD *)this + 4));
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800090f0  mov     rax, rsp
0x1800090f3  mov     [rax+8], rbx
0x1800090f7  push    rdi
0x1800090f8  sub     rsp, 60h
0x1800090fc  mov     qword ptr [rax-18h], 0
0x180009104  lea     r9, byte_1800127D8
0x18000910b  mov     qword ptr [rax-20h], 0
0x180009113  lea     r8, [rax+18h]
0x180009117  mov     qword ptr [rax-28h], 0
0x18000911f  xor     edx, edx
0x180009121  mov     qword ptr [rax-30h], 0
0x180009129  mov     rdi, rcx
0x18000912c  mov     qword ptr [rax-38h], 0
0x180009134  mov     dword ptr [rax-40h], 0
0x18000913b  mov     dword ptr [rax-48h], 1
0x180009142  mov     dword ptr [rax+10h], 0
0x180009149  mov     dword ptr [rax+18h], 0
0x180009150  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x180009155  mov     ebx, eax
0x180009157  test    eax, eax
0x180009159  js      short loc_1800091CB
0x18000915b  mov     rcx, [rdi+328h]
0x180009162  test    rcx, rcx
0x180009165  jz      short loc_18000917C
0x180009167  mov     rax, [rcx]
0x18000916a  mov     rax, [rax+0C0h]
0x180009171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009176  mov     ebx, eax
0x180009178  test    eax, eax
0x18000917a  js      short loc_1800091CB
0x18000917c  mov     rcx, [rdi+20h]
0x180009180  lea     rdx, [rsp+68h+arg_8]
0x180009185  mov     [rsp+68h+var_40], rdx
0x18000918a  mov     r9d, 1
0x180009190  xor     r8d, r8d
0x180009193  mov     [rsp+68h+var_48], 1388h
0x18000919b  xor     edx, edx
0x18000919d  mov     rax, [rcx]
0x1800091a0  mov     rax, [rax+118h]
0x1800091a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091ac  mov     ebx, eax
0x1800091ae  test    eax, eax
0x1800091b0  js      short loc_1800091CB
0x1800091b2  mov     rcx, [rdi+20h]
0x1800091b6  mov     edx, [rsp+68h+arg_8]
0x1800091ba  mov     rax, [rcx]
0x1800091bd  mov     rax, [rax+130h]
0x1800091c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091c9  mov     ebx, eax
0x1800091cb  mov     edx, [rsp+68h+arg_8]
0x1800091cf  test    edx, edx
0x1800091d1  jz      short loc_1800091E6
0x1800091d3  mov     rcx, [rdi+20h]
0x1800091d7  mov     rax, [rcx]
0x1800091da  mov     rax, [rax+120h]
0x1800091e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091e6  mov     eax, ebx
0x1800091e8  mov     rbx, [rsp+68h+arg_0]
0x1800091ed  add     rsp, 60h
0x1800091f1  pop     rdi
0x1800091f2  retn
```
