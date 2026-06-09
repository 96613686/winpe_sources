# CClfsMarshallingContext::ReserveLogSpace(__int64 const &)

- ea: `0x1800135a4`
- end: `0x180013698`
- name: `?ReserveLogSpace@CClfsMarshallingContext@@QEAAKAEB_J@Z`
- size: `244`
- prototype: `unsigned int __fastcall(CClfsMarshallingContext *__hidden this, const __int64 *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ddd8`
- `0x18000e160`
- `0x18000e8e4`

## callees

- `0x180009090`
- `0x18000e750`
- `0x18001031c`
- `0x1800135a4`

## pseudocode

```c
__int64 __fastcall CClfsMarshallingContext::ReserveLogSpace(void **this, __int64 *a2)
{
  __int64 result; // rax
  struct CLogIocb *v5; // rdi
  unsigned int appended; // ebx
  DWORD v7; // [rsp+40h] [rbp-58h]
  __int64 v8; // [rsp+80h] [rbp-18h] BYREF
  __int64 v9; // [rsp+88h] [rbp-10h] BYREF
  struct CLogIocb *v10; // [rsp+B0h] [rbp+18h] BYREF
  union _CLS_LSN v11; // [rsp+B8h] [rbp+20h] BYREF

  v11 = CLFS_LSN_NULL;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  result = CClfsMarshallingContext::AllocateIocbNaked((CClfsMarshallingContext *)this, &v10);
  if ( !(_DWORD)result )
  {
    v5 = v10;
    appended = NtReserveAndAppendLogInternal(
                 this[6],
                 0,
                 0,
                 a2,
                 &v9,
                 &v8,
                 0,
                 0,
                 v7,
                 &v11,
                 0,
                 0,
                 0,
                 *((_QWORD *)v10 + 7),
                 0,
                 0);
    CClfsMarshallingContext::FreeIocbNaked((CClfsMarshallingContext *)this, v5);
    return appended;
  }
  return result;
}

```

## disassembly

```asm
0x1800135a4  mov     r11, rsp
0x1800135a7  mov     [r11+8], rbx
0x1800135ab  mov     [r11+10h], rsi
0x1800135af  push    rdi
0x1800135b0  sub     rsp, 90h
0x1800135b7  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x1800135be  mov     rbx, rdx
0x1800135c1  lea     rdx, [r11+18h]; struct CLogIocb **
0x1800135c5  mov     [r11+20h], rax
0x1800135c9  mov     rsi, rcx
0x1800135cc  mov     qword ptr [r11-18h], 0
0x1800135d4  mov     qword ptr [r11-10h], 0
0x1800135dc  mov     qword ptr [r11+18h], 0
0x1800135e4  call    ?AllocateIocbNaked@CClfsMarshallingContext@@AEAAKPEAPEAVCLogIocb@@@Z; CClfsMarshallingContext::AllocateIocbNaked(CLogIocb * *)
0x1800135e9  test    eax, eax
0x1800135eb  jnz     loc_180013682
0x1800135f1  mov     rdi, [rsp+98h+arg_10]
0x1800135f9  mov     r9, rbx; __int64 *
0x1800135fc  mov     rcx, [rsi+30h]; void *
0x180013600  xor     r8d, r8d; unsigned int
0x180013603  mov     [rsp+98h+var_20], 0; struct _OVERLAPPED *
0x18001360c  xor     edx, edx; void *
0x18001360e  mov     [rsp+98h+var_28], al; char
0x180013612  mov     rax, [rdi+38h]
0x180013616  mov     [rsp+98h+var_30], rax; void *
0x18001361b  lea     rax, [rsp+98h+arg_18]
0x180013623  mov     [rsp+98h+var_38], 0; unsigned int *
0x18001362c  mov     [rsp+98h+var_40], 0; struct _CLS_INFORMATION *
0x180013635  mov     [rsp+98h+var_48], 0; union _CLS_LSN *
0x18001363e  mov     [rsp+98h+var_50], rax; union _CLS_LSN *
0x180013643  lea     rax, [rsp+98h+var_18]
0x18001364b  mov     [rsp+98h+var_60], 0; union _CLS_LSN *
0x180013654  mov     [rsp+98h+var_68], 0; unsigned int
0x18001365c  mov     [rsp+98h+var_70], rax; __int64 *
0x180013661  lea     rax, [rsp+98h+var_10]
0x180013669  mov     [rsp+98h+var_78], rax; __int64 *
0x18001366e  call    ?NtReserveAndAppendLogInternal@@YAKPEAX0KPEA_J1QEA_JKPEAT_CLS_LSN@@PEAK33PEAU_CLS_INFORMATION@@40EPEAU_OVERLAPPED@@@Z; NtReserveAndAppendLogInternal(void *,void *,ulong,__int64 *,__int64 *,__int64 * const,ulong,_CLS_LSN *,ulong *,_CLS_LSN *,_CLS_LSN *,_CLS_INFORMATION *,ulong *,void *,uchar,_OVERLAPPED *)
0x180013673  mov     rdx, rdi; struct CLogIocb *
0x180013676  mov     rcx, rsi; this
0x180013679  mov     ebx, eax
0x18001367b  call    ?FreeIocbNaked@CClfsMarshallingContext@@AEAAXPEAVCLogIocb@@@Z; CClfsMarshallingContext::FreeIocbNaked(CLogIocb *)
0x180013680  mov     eax, ebx
0x180013682  lea     r11, [rsp+98h+var_8]
0x18001368a  mov     rbx, [r11+10h]
0x18001368e  mov     rsi, [r11+18h]
0x180013692  mov     rsp, r11
0x180013695  pop     rdi
0x180013696  retn
```
