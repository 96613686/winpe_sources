# CIISDsCrMap::DeleteMappingIIS6(long,tagVARIANT)

- ea: `0x18000b7a8`
- end: `0x18000b85c`
- name: `?DeleteMappingIIS6@CIISDsCrMap@@AEAAJJUtagVARIANT@@@Z`
- size: `180`
- prototype: `__int64 __fastcall(CIISDsCrMap *__hidden this, int, struct tagVARIANT *__struct_ptr)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000b6b0`

## callees

- `0x18000a8e0`
- `0x18000b7a8`
- `0x18000cba0`
- `0x18000d210`
- `0x1800111e0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISDsCrMap::DeleteMappingIIS6(CIISDsCrMap *this, int a2, struct tagVARIANT *a3)
{
  int v6; // ebx
  IRecordInfo *pRecInfo; // xmm1_8
  struct tagVARIANT v9; // [rsp+20h] [rbp-258h] BYREF
  unsigned __int16 v10[264]; // [rsp+40h] [rbp-238h] BYREF

  v6 = CIISDsCrMap::OpenMd(this, L"Cert11/Mappings");
  if ( v6 >= 0 )
  {
    pRecInfo = a3->pRecInfo;
    *(_OWORD *)&v9.vt = *(_OWORD *)&a3->vt;
    v9.pRecInfo = pRecInfo;
    v6 = CIISDsCrMap::Locate(this, a2, &v9, v10);
    if ( v6 >= 0 )
      v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *))(**((_QWORD **)this + 7) + 32LL))(
             *((_QWORD *)this + 7),
             *((unsigned int *)this + 16),
             v10);
    CIISDsCrMap::CloseMd(this, 1);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000b7a8  mov     [rsp+arg_8], rbx
0x18000b7ad  push    rbp
0x18000b7ae  push    rsi
0x18000b7af  push    rdi
0x18000b7b0  sub     rsp, 260h
0x18000b7b7  mov     rax, cs:__security_cookie
0x18000b7be  xor     rax, rsp
0x18000b7c1  mov     [rsp+278h+var_28], rax
0x18000b7c9  mov     ebp, edx
0x18000b7cb  mov     rsi, r8
0x18000b7ce  lea     rdx, aCert11Mappings; "Cert11/Mappings"
0x18000b7d5  mov     rdi, rcx
0x18000b7d8  call    ?OpenMd@CIISDsCrMap@@QEAAJPEAGK@Z; CIISDsCrMap::OpenMd(ushort *,ulong)
0x18000b7dd  mov     ebx, eax
0x18000b7df  test    eax, eax
0x18000b7e1  js      short loc_18000B837
0x18000b7e3  movaps  xmm0, xmmword ptr [rsi]
0x18000b7e6  lea     r9, [rsp+278h+var_238]; unsigned __int16 *
0x18000b7eb  movsd   xmm1, qword ptr [rsi+10h]
0x18000b7f0  lea     r8, [rsp+278h+var_258]; struct tagVARIANT
0x18000b7f5  mov     edx, ebp; int
0x18000b7f7  movaps  xmmword ptr [rsp+278h+var_258], xmm0
0x18000b7fc  mov     rcx, rdi; this
0x18000b7ff  movsd   qword ptr [rsp+278h+var_258+10h], xmm1
0x18000b805  call    ?Locate@CIISDsCrMap@@QEAAJJUtagVARIANT@@PEAG@Z; CIISDsCrMap::Locate(long,tagVARIANT,ushort *)
0x18000b80a  mov     ebx, eax
0x18000b80c  test    eax, eax
0x18000b80e  js      short loc_18000B82A
0x18000b810  mov     rcx, [rdi+38h]
0x18000b814  lea     r8, [rsp+278h+var_238]
0x18000b819  mov     edx, [rdi+40h]
0x18000b81c  mov     rax, [rcx]
0x18000b81f  mov     rax, [rax+20h]
0x18000b823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b828  mov     ebx, eax
0x18000b82a  mov     edx, 1; int
0x18000b82f  mov     rcx, rdi; this
0x18000b832  call    ?CloseMd@CIISDsCrMap@@QEAAJH@Z; CIISDsCrMap::CloseMd(int)
0x18000b837  mov     eax, ebx
0x18000b839  mov     rcx, [rsp+278h+var_28]
0x18000b841  xor     rcx, rsp; StackCookie
0x18000b844  call    __security_check_cookie
0x18000b849  mov     rbx, [rsp+278h+arg_8]
0x18000b851  add     rsp, 260h
0x18000b858  pop     rdi
0x18000b859  pop     rsi
0x18000b85a  pop     rbp
0x18000b85b  retn
```
