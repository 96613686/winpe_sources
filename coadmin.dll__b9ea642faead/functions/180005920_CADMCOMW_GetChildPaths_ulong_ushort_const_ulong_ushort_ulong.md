# CADMCOMW::GetChildPaths(ulong,ushort const *,ulong,ushort *,ulong *)

- ea: `0x180005920`
- end: `0x180005a0b`
- name: `?GetChildPaths@CADMCOMW@@UEAAJKPEBGKPEAGPEAK@Z`
- size: `235`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned int, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005920`
- `0x18000716c`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::GetChildPaths(
        CADMCOMW *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned int *a6)
{
  int v9; // ecx
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v13; // [rsp+60h] [rbp-18h] BYREF
  int v14; // [rsp+64h] [rbp-14h] BYREF
  int v15; // [rsp+68h] [rbp-10h] BYREF

  v13 = 0;
  v15 = 0;
  v14 = 0;
  v9 = CADMCOMW::LookupAndAccessCheck(this, a2, &v13, (__int64)a3, 3u, 0, 0, (__int64)&v15, 0, &v14, 0);
  if ( v9 >= 0 )
  {
    v10 = *((_QWORD *)this + 101);
    if ( v10 && v14 == 1 )
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, _QWORD, unsigned __int16 *, unsigned int *))(*(_QWORD *)v10 + 96LL))(
              v10,
              v13,
              a3,
              a4,
              a5,
              a6);
    else
      v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, _QWORD, unsigned __int16 *, unsigned int *))(**((_QWORD **)this + 4) + 504LL))(
              *((_QWORD *)this + 4),
              v13,
              a3,
              a4,
              a5,
              a6);
    v9 = v11;
    if ( v11 >= 0 )
      return 0;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180005920  mov     r11, rsp
0x180005923  mov     [r11+8], rbx
0x180005927  mov     [r11+10h], rsi
0x18000592b  push    rdi
0x18000592c  sub     rsp, 70h
0x180005930  mov     qword ptr [r11-28h], 0
0x180005938  lea     rax, [r11-14h]
0x18000593c  mov     [r11-30h], rax
0x180005940  mov     esi, r9d
0x180005943  mov     qword ptr [r11-38h], 0
0x18000594b  lea     rax, [r11-10h]
0x18000594f  mov     [r11-40h], rax
0x180005953  mov     rdi, r8
0x180005956  mov     qword ptr [r11-48h], 0
0x18000595e  mov     r9, r8
0x180005961  mov     dword ptr [rsp+78h+var_50], 0
0x180005969  lea     r8, [r11-18h]
0x18000596d  mov     dword ptr [rsp+78h+var_58], 3
0x180005975  mov     rbx, rcx
0x180005978  mov     [rsp+78h+var_18], 0
0x180005980  mov     [rsp+78h+var_10], 0
0x180005988  mov     [rsp+78h+var_14], 0
0x180005990  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x180005995  mov     ecx, eax
0x180005997  test    eax, eax
0x180005999  js      short loc_1800059F7
0x18000599b  mov     rcx, [rbx+328h]
0x1800059a2  test    rcx, rcx
0x1800059a5  jz      short loc_1800059B7
0x1800059a7  cmp     [rsp+78h+var_14], 1
0x1800059ac  jnz     short loc_1800059B7
0x1800059ae  mov     rax, [rcx]
0x1800059b1  mov     rax, [rax+60h]
0x1800059b5  jmp     short loc_1800059C5
0x1800059b7  mov     rcx, [rbx+20h]
0x1800059bb  mov     rax, [rcx]
0x1800059be  mov     rax, [rax+1F8h]
0x1800059c5  mov     rdx, [rsp+78h+arg_28]
0x1800059cd  mov     r9d, esi
0x1800059d0  mov     [rsp+78h+var_50], rdx
0x1800059d5  mov     r8, rdi
0x1800059d8  mov     rdx, [rsp+78h+arg_20]
0x1800059e0  mov     [rsp+78h+var_58], rdx
0x1800059e5  mov     edx, [rsp+78h+var_18]
0x1800059e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059ee  mov     ecx, eax
0x1800059f0  xor     eax, eax
0x1800059f2  test    ecx, ecx
0x1800059f4  cmovns  ecx, eax
0x1800059f7  lea     r11, [rsp+78h+var_8]
0x1800059fc  mov     eax, ecx
0x1800059fe  mov     rbx, [r11+10h]
0x180005a02  mov     rsi, [r11+18h]
0x180005a06  mov     rsp, r11
0x180005a09  pop     rdi
0x180005a0a  retn
```
