# OpenAdminBaseKey(ushort *,ushort *,ulong,IMSAdminBaseW * *,ulong *)

- ea: `0x180003de8`
- end: `0x180003ef3`
- name: `?OpenAdminBaseKey@@YAJPEAG0KPEAPEAUIMSAdminBaseW@@PEAK@Z`
- size: `267`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned int, struct IMSAdminBaseW **, unsigned int *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180005800`
- `0x180007814`
- `0x18000a030`
- `0x18000c8d8`
- `0x18000d210`

## callees

- `0x180003ab8`
- `0x180003de8`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall OpenAdminBaseKey(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned int a3,
        struct IMSAdminBaseW **a4,
        unsigned int *a5)
{
  struct IMSAdminBaseW *v5; // rdi
  int v10; // eax
  int inited; // ebx
  struct IMSAdminBaseW *v13; // [rsp+40h] [rbp-48h] BYREF
  unsigned int v14; // [rsp+A8h] [rbp+20h] BYREF

  v5 = *a4;
  v14 = 0;
  v10 = ((__int64 (__fastcall *)(struct IMSAdminBaseW *, _QWORD, unsigned __int16 *, _QWORD, int, unsigned int *))v5->lpVtbl->OpenKey)(
          v5,
          0,
          a2,
          a3,
          30000,
          &v14);
  inited = v10;
  if ( v10 >= 0
    || ((unsigned __int16)v10 == 1722 || (unsigned int)(unsigned __int16)v10 - 1725 <= 2 || v10 == -2147417848)
    && (v13 = v5, inited = InitAdminBase(a1, &v13), inited >= 0)
    && (v5 = v13,
        *a4 = v13,
        inited = ((__int64 (__fastcall *)(struct IMSAdminBaseW *, _QWORD, unsigned __int16 *, _QWORD, int, unsigned int *))v5->lpVtbl->OpenKey)(
                   v5,
                   0,
                   a2,
                   a3,
                   30000,
                   &v14),
        inited >= 0) )
  {
    *a5 = v14;
  }
  else if ( v14 )
  {
    ((void (__fastcall *)(struct IMSAdminBaseW *))v5->lpVtbl->CloseKey)(v5);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180003de8  mov     r11, rsp
0x180003deb  push    rbx
0x180003dec  push    rbp
0x180003ded  push    rsi
0x180003dee  push    rdi
0x180003def  push    r14
0x180003df1  push    r15
0x180003df3  sub     rsp, 58h
0x180003df7  mov     rdi, [r9]
0x180003dfa  mov     rsi, rcx
0x180003dfd  lea     rcx, [r11+20h]
0x180003e01  mov     dword ptr [r11+20h], 0
0x180003e09  mov     [r11-60h], rcx
0x180003e0d  mov     r14, r9
0x180003e10  mov     ebp, r8d
0x180003e13  mov     [rsp+88h+var_68], 7530h
0x180003e1b  mov     rax, [rdi]
0x180003e1e  mov     r9d, r8d
0x180003e21  mov     r15, rdx
0x180003e24  mov     r8, rdx
0x180003e27  xor     edx, edx
0x180003e29  mov     rcx, rdi
0x180003e2c  mov     rax, [rax+88h]
0x180003e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e38  mov     ebx, eax
0x180003e3a  test    eax, eax
0x180003e3c  jns     loc_180003ED3
0x180003e42  movzx   ecx, ax
0x180003e45  cmp     ecx, 6BAh
0x180003e4b  jz      short loc_180003E5F
0x180003e4d  add     ecx, 0FFFFF943h
0x180003e53  cmp     ecx, 2
0x180003e56  jbe     short loc_180003E5F
0x180003e58  cmp     eax, 80010108h
0x180003e5d  jnz     short loc_180003EB4
0x180003e5f  lea     rdx, [rsp+88h+var_48]; struct IMSAdminBaseW **
0x180003e64  mov     [rsp+88h+var_48], rdi
0x180003e69  mov     rcx, rsi; unsigned __int16 *
0x180003e6c  call    ?InitAdminBase@@YAJPEAGPEAPEAUIMSAdminBaseW@@@Z; InitAdminBase(ushort *,IMSAdminBaseW * *)
0x180003e71  mov     ebx, eax
0x180003e73  test    eax, eax
0x180003e75  js      short loc_180003EB4
0x180003e77  mov     rdi, [rsp+88h+var_48]
0x180003e7c  mov     [r14], rdi
0x180003e7f  lea     rcx, [rsp+88h+arg_18]
0x180003e87  mov     rax, [rdi]
0x180003e8a  mov     r9d, ebp
0x180003e8d  mov     [rsp+88h+var_60], rcx
0x180003e92  mov     r8, r15
0x180003e95  xor     edx, edx
0x180003e97  mov     [rsp+88h+var_68], 7530h
0x180003e9f  mov     rcx, rdi
0x180003ea2  mov     rax, [rax+88h]
0x180003ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eae  mov     ebx, eax
0x180003eb0  test    eax, eax
0x180003eb2  jns     short loc_180003ED3
0x180003eb4  mov     edx, [rsp+88h+arg_18]
0x180003ebb  test    edx, edx
0x180003ebd  jz      short loc_180003EE4
0x180003ebf  mov     rax, [rdi]
0x180003ec2  mov     rcx, rdi
0x180003ec5  mov     rax, [rax+90h]
0x180003ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ed1  jmp     short loc_180003EE4
0x180003ed3  mov     rcx, [rsp+88h+arg_20]
0x180003edb  mov     eax, [rsp+88h+arg_18]
0x180003ee2  mov     [rcx], eax
0x180003ee4  mov     eax, ebx
0x180003ee6  add     rsp, 58h
0x180003eea  pop     r15
0x180003eec  pop     r14
0x180003eee  pop     rdi
0x180003eef  pop     rsi
0x180003ef0  pop     rbp
0x180003ef1  pop     rbx
0x180003ef2  retn
```
