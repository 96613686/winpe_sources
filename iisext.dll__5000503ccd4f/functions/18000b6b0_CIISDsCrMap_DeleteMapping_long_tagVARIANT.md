# CIISDsCrMap::DeleteMapping(long,tagVARIANT)

- ea: `0x18000b6b0`
- end: `0x18000b7a1`
- name: `?DeleteMapping@CIISDsCrMap@@UEAAJJUtagVARIANT@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(CIISDsCrMap *__hidden this, int, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000a8e0`
- `0x18000b6b0`
- `0x18000b7a8`
- `0x18000cba0`
- `0x18000d210`
- `0x1800111e0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISDsCrMap::DeleteMapping(CIISDsCrMap *this, int a2, struct tagVARIANT *a3)
{
  IRecordInfo *pRecInfo; // xmm1_8
  int v8; // edi
  IRecordInfo *v9; // xmm1_8
  struct tagVARIANT v10; // [rsp+20h] [rbp-258h] BYREF
  unsigned __int16 v11[264]; // [rsp+40h] [rbp-238h] BYREF

  if ( (unsigned int)(a2 - 1) > 3 )
    return 2147942487LL;
  if ( *((_DWORD *)this + 35) )
  {
    pRecInfo = a3->pRecInfo;
    *(_OWORD *)&v10.vt = *(_OWORD *)&a3->vt;
    v10.pRecInfo = pRecInfo;
    return CIISDsCrMap::DeleteMappingIIS6(this, a2, &v10);
  }
  else
  {
    v8 = CIISDsCrMap::OpenMd(this, L"Cert11");
    if ( v8 >= 0 )
    {
      v9 = a3->pRecInfo;
      *(_OWORD *)&v10.vt = *(_OWORD *)&a3->vt;
      v10.pRecInfo = v9;
      v8 = CIISDsCrMap::Locate(this, a2, &v10, v11);
      if ( v8 >= 0 )
        v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *))(**((_QWORD **)this + 7) + 32LL))(
               *((_QWORD *)this + 7),
               *((unsigned int *)this + 16),
               v11);
      CIISDsCrMap::CloseMd(this, 1);
    }
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x18000b6b0  mov     [rsp+arg_8], rbx
0x18000b6b5  push    rbp
0x18000b6b6  push    rsi
0x18000b6b7  push    rdi
0x18000b6b8  sub     rsp, 260h
0x18000b6bf  mov     rax, cs:__security_cookie
0x18000b6c6  xor     rax, rsp
0x18000b6c9  mov     [rsp+278h+var_28], rax
0x18000b6d1  lea     eax, [rdx-1]
0x18000b6d4  mov     rsi, r8
0x18000b6d7  mov     ebp, edx
0x18000b6d9  mov     rbx, rcx
0x18000b6dc  cmp     eax, 3
0x18000b6df  ja      loc_18000B779
0x18000b6e5  cmp     dword ptr [rcx+8Ch], 0
0x18000b6ec  jz      short loc_18000B70F
0x18000b6ee  movups  xmm0, xmmword ptr [r8]
0x18000b6f2  movsd   xmm1, qword ptr [r8+10h]
0x18000b6f8  lea     r8, [rsp+278h+var_258]; struct tagVARIANT
0x18000b6fd  movaps  xmmword ptr [rsp+278h+var_258], xmm0
0x18000b702  movsd   qword ptr [rsp+278h+var_258+10h], xmm1
0x18000b708  call    ?DeleteMappingIIS6@CIISDsCrMap@@AEAAJJUtagVARIANT@@@Z; CIISDsCrMap::DeleteMappingIIS6(long,tagVARIANT)
0x18000b70d  jmp     short loc_18000B77E
0x18000b70f  lea     rdx, aCert11; "Cert11"
0x18000b716  call    ?OpenMd@CIISDsCrMap@@QEAAJPEAGK@Z; CIISDsCrMap::OpenMd(ushort *,ulong)
0x18000b71b  mov     edi, eax
0x18000b71d  test    eax, eax
0x18000b71f  js      short loc_18000B775
0x18000b721  movups  xmm0, xmmword ptr [rsi]
0x18000b724  lea     r9, [rsp+278h+var_238]; unsigned __int16 *
0x18000b729  mov     edx, ebp; int
0x18000b72b  movsd   xmm1, qword ptr [rsi+10h]
0x18000b730  lea     r8, [rsp+278h+var_258]; struct tagVARIANT
0x18000b735  mov     rcx, rbx; this
0x18000b738  movaps  xmmword ptr [rsp+278h+var_258], xmm0
0x18000b73d  movsd   qword ptr [rsp+278h+var_258+10h], xmm1
0x18000b743  call    ?Locate@CIISDsCrMap@@QEAAJJUtagVARIANT@@PEAG@Z; CIISDsCrMap::Locate(long,tagVARIANT,ushort *)
0x18000b748  mov     edi, eax
0x18000b74a  test    eax, eax
0x18000b74c  js      short loc_18000B768
0x18000b74e  mov     rcx, [rbx+38h]
0x18000b752  lea     r8, [rsp+278h+var_238]
0x18000b757  mov     edx, [rbx+40h]
0x18000b75a  mov     rax, [rcx]
0x18000b75d  mov     rax, [rax+20h]
0x18000b761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b766  mov     edi, eax
0x18000b768  mov     edx, 1; int
0x18000b76d  mov     rcx, rbx; this
0x18000b770  call    ?CloseMd@CIISDsCrMap@@QEAAJH@Z; CIISDsCrMap::CloseMd(int)
0x18000b775  mov     eax, edi
0x18000b777  jmp     short loc_18000B77E
0x18000b779  mov     eax, 80070057h
0x18000b77e  mov     rcx, [rsp+278h+var_28]
0x18000b786  xor     rcx, rsp; StackCookie
0x18000b789  call    __security_check_cookie
0x18000b78e  mov     rbx, [rsp+278h+arg_8]
0x18000b796  add     rsp, 260h
0x18000b79d  pop     rdi
0x18000b79e  pop     rsi
0x18000b79f  pop     rbp
0x18000b7a0  retn
```
