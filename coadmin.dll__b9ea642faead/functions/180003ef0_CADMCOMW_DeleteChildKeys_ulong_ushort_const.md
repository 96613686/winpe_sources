# CADMCOMW::DeleteChildKeys(ulong,ushort const *)

- ea: `0x180003ef0`
- end: `0x180003fc0`
- name: `?DeleteChildKeys@CADMCOMW@@UEAAJKPEBG@Z`
- size: `208`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000238c`
- `0x180003ef0`
- `0x18000716c`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::DeleteChildKeys(CADMCOMW *this, unsigned int a2, unsigned __int16 *a3)
{
  signed int v6; // ebx
  int v8; // [rsp+60h] [rbp-28h] BYREF
  __int64 v9; // [rsp+68h] [rbp-20h] BYREF
  unsigned int v10; // [rsp+A8h] [rbp+20h] BYREF

  v10 = 0;
  v8 = 0;
  v6 = CADMCOMW::LookupAndAccessCheck(this, a2, &v10, (__int64)a3, 0, 2, 0, 0, &v9, 0, (__int64)&v8);
  if ( v6 >= 0 )
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *))(**((_QWORD **)this + 4) + 88LL))(
           *((_QWORD *)this + 4),
           v10,
           a3);
  if ( v8 )
    CADMCOMW::AuditAccess(this, 0x1196u, v6, a2, a3, 0, 0, 0, 0, 0, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180003ef0  mov     r11, rsp
0x180003ef3  mov     [r11+8], rbx
0x180003ef7  mov     [r11+10h], rbp
0x180003efb  push    rsi
0x180003efc  push    rdi
0x180003efd  push    r14
0x180003eff  sub     rsp, 70h
0x180003f03  xor     r14d, r14d
0x180003f06  lea     rax, [r11-28h]
0x180003f0a  mov     [r11-38h], rax
0x180003f0e  mov     rdi, r8
0x180003f11  mov     [r11-40h], r14
0x180003f15  lea     rax, [r11-20h]
0x180003f19  mov     [r11-48h], rax
0x180003f1d  mov     r9, r8
0x180003f20  mov     [r11-50h], r14
0x180003f24  lea     r8, [r11+20h]
0x180003f28  mov     [r11-58h], r14
0x180003f2c  mov     ebp, edx
0x180003f2e  mov     [rsp+88h+var_60], 2
0x180003f36  mov     rsi, rcx
0x180003f39  mov     [r11-68h], r14d
0x180003f3d  mov     [r11+20h], r14d
0x180003f41  mov     [r11-28h], r14d
0x180003f45  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x180003f4a  mov     ebx, eax
0x180003f4c  test    eax, eax
0x180003f4e  js      short loc_180003F6C
0x180003f50  mov     rcx, [rsi+20h]
0x180003f54  mov     r8, rdi
0x180003f57  mov     edx, [rsp+88h+arg_18]
0x180003f5e  mov     rax, [rcx]
0x180003f61  mov     rax, [rax+58h]
0x180003f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f6a  mov     ebx, eax
0x180003f6c  cmp     [rsp+88h+var_28], r14d
0x180003f71  jz      short loc_180003FA9
0x180003f73  mov     [rsp+88h+var_38], r14; unsigned __int16 *
0x180003f78  mov     r9d, ebp; unsigned int
0x180003f7b  mov     [rsp+88h+var_40], r14; struct _METADATA_RECORD *
0x180003f80  mov     r8d, ebx; int
0x180003f83  mov     [rsp+88h+var_48], r14; struct _METADATA_RECORD *
0x180003f88  mov     edx, 1196h; unsigned int
0x180003f8d  mov     [rsp+88h+var_50], r14d; unsigned int
0x180003f92  mov     rcx, rsi; this
0x180003f95  mov     [rsp+88h+var_58], r14; unsigned __int16 *
0x180003f9a  mov     [rsp+88h+var_60], r14d; unsigned int
0x180003f9f  mov     [rsp+88h+var_68], rdi; unsigned __int16 *
0x180003fa4  call    ?AuditAccess@CADMCOMW@@AEAAJKJKPEBGK0KPEAU_METADATA_RECORD@@10@Z; CADMCOMW::AuditAccess(ulong,long,ulong,ushort const *,ulong,ushort const *,ulong,_METADATA_RECORD *,_METADATA_RECORD *,ushort const *)
0x180003fa9  lea     r11, [rsp+88h+var_18]
0x180003fae  mov     eax, ebx
0x180003fb0  mov     rbx, [r11+20h]
0x180003fb4  mov     rbp, [r11+28h]
0x180003fb8  mov     rsp, r11
0x180003fbb  pop     r14
0x180003fbd  pop     rdi
0x180003fbe  pop     rsi
0x180003fbf  retn
```
