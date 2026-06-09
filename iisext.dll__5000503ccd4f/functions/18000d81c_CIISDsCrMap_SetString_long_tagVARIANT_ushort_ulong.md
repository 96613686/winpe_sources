# CIISDsCrMap::SetString(long,tagVARIANT,ushort *,ulong)

- ea: `0x18000d81c`
- end: `0x18000d927`
- name: `?SetString@CIISDsCrMap@@QEAAJJUtagVARIANT@@PEAGK@Z`
- size: `267`
- prototype: `__int64 __usercall@<rax>(CIISDsCrMap *__hidden this@<rcx>, int@<edx>, struct tagVARIANT *__struct_ptr@<r8>, unsigned __int16 *@<r9>, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x18000d460`
- `0x18000d750`
- `0x18000d7c0`

## callees

- `0x18000a8e0`
- `0x18000c55c`
- `0x18000cba0`
- `0x18000d210`
- `0x18000d6d8`
- `0x18000d81c`
- `0x1800111e0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000d901`
- `KERNEL32!LocalFree` at `0x18000d901`

## pseudocode

```c
__int64 __fastcall CIISDsCrMap::SetString(
        CIISDsCrMap *this,
        int a2,
        struct tagVARIANT *a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  __int64 result; // rax
  int v9; // eax
  unsigned __int8 *v10; // rdi
  int v11; // ebx
  IRecordInfo *pRecInfo; // xmm1_8
  unsigned int v13; // [rsp+30h] [rbp-278h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-270h] BYREF
  struct tagVARIANT v15; // [rsp+40h] [rbp-268h] BYREF
  unsigned __int16 v16[264]; // [rsp+60h] [rbp-248h] BYREF

  hMem = 0;
  v13 = 0;
  result = GetStringFromBSTR(a4, (char **)&hMem, &v13, 1);
  if ( (int)result >= 0 )
  {
    v9 = CIISDsCrMap::OpenMd(this, L"Cert11");
    v10 = (unsigned __int8 *)hMem;
    v11 = v9;
    if ( v9 >= 0 )
    {
      pRecInfo = a3->pRecInfo;
      *(_OWORD *)&v15.vt = *(_OWORD *)&a3->vt;
      v15.pRecInfo = pRecInfo;
      v11 = CIISDsCrMap::Locate(this, a2, &v15, v16);
      if ( v11 >= 0 )
        v11 = CIISDsCrMap::SetMdData(this, v16, a5, 2, v13, v10);
      CIISDsCrMap::CloseMd(this, 1);
    }
    if ( v10 )
      LocalFree(v10);
    return (unsigned int)v11;
  }
  return result;
}

```

## disassembly

```asm
0x18000d81c  push    rbx
0x18000d81e  push    rbp
0x18000d81f  push    rsi
0x18000d820  push    rdi
0x18000d821  push    r14
0x18000d823  sub     rsp, 280h
0x18000d82a  mov     rax, cs:__security_cookie
0x18000d831  xor     rax, rsp
0x18000d834  mov     [rsp+2A8h+var_38], rax
0x18000d83c  mov     rax, r9
0x18000d83f  mov     [rsp+2A8h+hMem], 0
0x18000d848  mov     rbp, r8
0x18000d84b  mov     [rsp+2A8h+var_278], 0
0x18000d853  mov     r14d, edx
0x18000d856  lea     r8, [rsp+2A8h+var_278]; unsigned int *
0x18000d85b  mov     rsi, rcx
0x18000d85e  lea     rdx, [rsp+2A8h+hMem]; char **
0x18000d863  mov     rcx, rax; lpWideCharStr
0x18000d866  mov     r9d, 1; int
0x18000d86c  call    ?GetStringFromBSTR@@YAJPEAGPEAPEADPEAKH@Z; GetStringFromBSTR(ushort *,char * *,ulong *,int)
0x18000d871  test    eax, eax
0x18000d873  js      loc_18000D909
0x18000d879  lea     rdx, aCert11; "Cert11"
0x18000d880  mov     rcx, rsi; this
0x18000d883  call    ?OpenMd@CIISDsCrMap@@QEAAJPEAGK@Z; CIISDsCrMap::OpenMd(ushort *,ulong)
0x18000d888  mov     rdi, [rsp+2A8h+hMem]
0x18000d88d  mov     ebx, eax
0x18000d88f  test    eax, eax
0x18000d891  js      short loc_18000D8F9
0x18000d893  movaps  xmm0, xmmword ptr [rbp+0]
0x18000d897  lea     r9, [rsp+2A8h+var_248]; unsigned __int16 *
0x18000d89c  movsd   xmm1, qword ptr [rbp+10h]
0x18000d8a1  lea     r8, [rsp+2A8h+var_268]; struct tagVARIANT
0x18000d8a6  mov     edx, r14d; int
0x18000d8a9  movaps  xmmword ptr [rsp+2A8h+var_268], xmm0
0x18000d8ae  mov     rcx, rsi; this
0x18000d8b1  movsd   qword ptr [rsp+2A8h+var_268+10h], xmm1
0x18000d8b7  call    ?Locate@CIISDsCrMap@@QEAAJJUtagVARIANT@@PEAG@Z; CIISDsCrMap::Locate(long,tagVARIANT,ushort *)
0x18000d8bc  mov     ebx, eax
0x18000d8be  test    eax, eax
0x18000d8c0  js      short loc_18000D8EC
0x18000d8c2  mov     eax, [rsp+2A8h+var_278]
0x18000d8c6  lea     rdx, [rsp+2A8h+var_248]; unsigned __int16 *
0x18000d8cb  mov     r8d, [rsp+2A8h+arg_20]; unsigned int
0x18000d8d3  mov     r9d, 2; unsigned int
0x18000d8d9  mov     [rsp+2A8h+var_280], rdi; unsigned __int8 *
0x18000d8de  mov     rcx, rsi; this
0x18000d8e1  mov     [rsp+2A8h+var_288], eax; unsigned int
0x18000d8e5  call    ?SetMdData@CIISDsCrMap@@QEAAJPEAGKKKPEAE@Z; CIISDsCrMap::SetMdData(ushort *,ulong,ulong,ulong,uchar *)
0x18000d8ea  mov     ebx, eax
0x18000d8ec  mov     edx, 1; int
0x18000d8f1  mov     rcx, rsi; this
0x18000d8f4  call    ?CloseMd@CIISDsCrMap@@QEAAJH@Z; CIISDsCrMap::CloseMd(int)
0x18000d8f9  test    rdi, rdi
0x18000d8fc  jz      short loc_18000D907
0x18000d8fe  mov     rcx, rdi; hMem
0x18000d901  call    cs:__imp_LocalFree
0x18000d907  mov     eax, ebx
0x18000d909  mov     rcx, [rsp+2A8h+var_38]
0x18000d911  xor     rcx, rsp; StackCookie
0x18000d914  call    __security_check_cookie
0x18000d919  add     rsp, 280h
0x18000d920  pop     r14
0x18000d922  pop     rdi
0x18000d923  pop     rsi
0x18000d924  pop     rbp
0x18000d925  pop     rbx
0x18000d926  retn
```
