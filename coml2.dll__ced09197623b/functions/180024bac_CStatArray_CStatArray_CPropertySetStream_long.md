# CStatArray::CStatArray(CPropertySetStream *,long *)

- ea: `0x180024bac`
- end: `0x180024c87`
- name: `??0CStatArray@@QEAA@PEAVCPropertySetStream@@PEAJ@Z`
- size: `219`
- prototype: `CStatArray *(CStatArray *__hidden this, struct CPropertySetStream *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024a20`

## callees

- `0x180024bac`
- `0x180024c90`
- `0x18003f834`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024c23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024c23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024be5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024be5`

## pseudocode

```c
CStatArray *__fastcall CStatArray::CStatArray(CStatArray *this, struct CPropertySetStream *a2, int *a3)
{
  unsigned int *v6; // rdi
  void *v7; // rcx
  int v8; // eax
  SIZE_T v9; // rcx
  struct tagSTATPROPSTG *v10; // rax
  int v11; // eax
  struct tagPROPSPEC *v13; // [rsp+20h] [rbp-28h]
  struct tagPROPSPEC *v14; // [rsp+20h] [rbp-28h]
  unsigned int v15; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v16; // [rsp+60h] [rbp+18h] BYREF

  *(_DWORD *)this = 1;
  *((_QWORD *)this + 1) = 0;
  v6 = (unsigned int *)((char *)this + 16);
  while ( 1 )
  {
    v7 = (void *)*((_QWORD *)this + 1);
    v15 = 0;
    *v6 = -1;
    CoTaskMemFree(v7);
    *((_QWORD *)this + 1) = 0;
    v8 = PrEnumerateProperties(a2, 1, &v15, v6, v13, 0);
    if ( v8 < 0 )
      break;
    v9 = 16LL * (*v6 + 1);
    v16 = *v6 + 1;
    v10 = (struct tagSTATPROPSTG *)CoTaskMemAlloc(v9);
    *((_QWORD *)this + 1) = v10;
    if ( !v10 )
    {
      v8 = -1073741670;
      break;
    }
    v15 = 0;
    v8 = PrEnumerateProperties(a2, 0, &v15, &v16, v14, v10);
    if ( v8 < 0 )
      break;
    if ( v16 == *v6 )
    {
      v11 = 0;
      goto LABEL_7;
    }
  }
  v11 = DfpNtStatusToHResult(v8);
LABEL_7:
  *a3 = v11;
  return this;
}

```

## disassembly

```asm
0x180024bac  mov     [rsp+arg_8], rbx
0x180024bb1  push    rbp
0x180024bb2  push    rsi
0x180024bb3  push    rdi
0x180024bb4  sub     rsp, 30h
0x180024bb8  mov     rsi, r8
0x180024bbb  mov     dword ptr [rcx], 1
0x180024bc1  mov     rbp, rdx
0x180024bc4  mov     qword ptr [rcx+8], 0
0x180024bcc  mov     rbx, rcx
0x180024bcf  lea     rdi, [rcx+10h]
0x180024bd3  mov     rcx, [rbx+8]; pv
0x180024bd7  mov     [rsp+48h+arg_0], 0
0x180024bdf  mov     dword ptr [rdi], 0FFFFFFFFh
0x180024be5  call    cs:__imp_CoTaskMemFree
0x180024beb  mov     r9, rdi; unsigned int *
0x180024bee  mov     qword ptr [rbx+8], 0
0x180024bf6  lea     r8, [rsp+48h+arg_0]; unsigned int *
0x180024bfb  mov     [rsp+48h+var_20], 0; struct tagSTATPROPSTG *
0x180024c04  mov     edx, 1; unsigned int
0x180024c09  mov     rcx, rbp; this
0x180024c0c  call    ?PrEnumerateProperties@@YAJPEAVCPropertySetStream@@KPEAK1QEAUtagPROPSPEC@@QEAUtagSTATPROPSTG@@@Z; PrEnumerateProperties(CPropertySetStream *,ulong,ulong *,ulong *,tagPROPSPEC * const,tagSTATPROPSTG * const)
0x180024c11  test    eax, eax
0x180024c13  js      short loc_180024C77
0x180024c15  mov     eax, [rdi]
0x180024c17  inc     eax
0x180024c19  mov     ecx, eax
0x180024c1b  shl     rcx, 4; cb
0x180024c1f  mov     [rsp+48h+arg_10], eax
0x180024c23  call    cs:__imp_CoTaskMemAlloc
0x180024c29  mov     [rbx+8], rax
0x180024c2d  test    rax, rax
0x180024c30  jz      short loc_180024C80
0x180024c32  lea     r9, [rsp+48h+arg_10]; unsigned int *
0x180024c37  mov     [rsp+48h+arg_0], 0
0x180024c3f  lea     r8, [rsp+48h+arg_0]; unsigned int *
0x180024c44  mov     [rsp+48h+var_20], rax; struct tagSTATPROPSTG *
0x180024c49  xor     edx, edx; unsigned int
0x180024c4b  mov     rcx, rbp; this
0x180024c4e  call    ?PrEnumerateProperties@@YAJPEAVCPropertySetStream@@KPEAK1QEAUtagPROPSPEC@@QEAUtagSTATPROPSTG@@@Z; PrEnumerateProperties(CPropertySetStream *,ulong,ulong *,ulong *,tagPROPSPEC * const,tagSTATPROPSTG * const)
0x180024c53  test    eax, eax
0x180024c55  js      short loc_180024C77
0x180024c57  mov     eax, [rdi]
0x180024c59  cmp     [rsp+48h+arg_10], eax
0x180024c5d  jnz     loc_180024BD3
0x180024c63  xor     eax, eax
0x180024c65  mov     [rsi], eax
0x180024c67  mov     rax, rbx
0x180024c6a  mov     rbx, [rsp+48h+arg_8]
0x180024c6f  add     rsp, 30h
0x180024c73  pop     rdi
0x180024c74  pop     rsi
0x180024c75  pop     rbp
0x180024c76  retn
0x180024c77  mov     ecx, eax; int
0x180024c79  call    ?DfpNtStatusToHResult@@YAJJ@Z; DfpNtStatusToHResult(long)
0x180024c7e  jmp     short loc_180024C65
0x180024c80  mov     eax, 0C000009Ah
0x180024c85  jmp     short loc_180024C77
```
