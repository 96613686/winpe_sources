# UL_AND_WORKER_MANAGER::EnumerateWorkerProcesses(ulong *,__MIDL_IW3Control_0004 * *,ushort * * *)

- ea: `0x180010e14`
- end: `0x18001105d`
- name: `?EnumerateWorkerProcesses@UL_AND_WORKER_MANAGER@@QEAAJPEAKPEAPEAU__MIDL_IW3Control_0004@@PEAPEAPEAG@Z`
- size: `585`
- prototype: `__int64 __fastcall(UL_AND_WORKER_MANAGER *__hidden this, unsigned int *, struct __MIDL_IW3Control_0004 **, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800322cc`

## callees

- `0x180010e14`
- `0x180012a40`
- `0x1800236ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010e77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010ea1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010f27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010e77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010ea1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010f27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011017`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011025`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001103c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011055`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011017`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011025`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001103c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011055`
- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180010ec5`
- `iisutil!?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180010ec5`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180010e4d`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180010e6b`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180010e95`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180010fc7`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180010e4d`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180010e6b`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180010e95`
- `iisutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x180010fc7`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180010ed2`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180010f88`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180010ed2`
- `iisutil!??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z` at `0x180010f88`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180010edc`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180010f92`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180010fac`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180010fbe`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180011000`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18001100c`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180010edc`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180010f92`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180010fac`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180010fbe`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x180011000`
- `iisutil!??1CLKRHashTable_Iterator@@QEAA@XZ` at `0x18001100c`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180010f7b`
- `iisutil!?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ` at `0x180010f7b`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x180010fa0`
- `iisutil!??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z` at `0x180010fa0`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x180010f6e`
- `iisutil!?Increment@CLKRHashTable_Iterator@@QEAA_NXZ` at `0x180010f6e`

## pseudocode

```c
unsigned int __fastcall UL_AND_WORKER_MANAGER::EnumerateWorkerProcesses(
        UL_AND_WORKER_MANAGER *this,
        unsigned int *a2,
        struct __MIDL_IW3Control_0004 **a3,
        unsigned __int16 ***a4)
{
  CLKRHashTable *v4; // r12
  unsigned int result; // eax
  unsigned int v9; // eax
  struct __MIDL_IW3Control_0004 *v10; // r13
  int ProcessInfo; // edi
  unsigned int v12; // r15d
  unsigned int v13; // eax
  unsigned __int16 **v14; // r14
  const struct CLKRHashTable_Iterator *v15; // rax
  WORKER_PROCESS *v16; // rbx
  SIZE_T v17; // rdi
  unsigned __int16 *v18; // rax
  unsigned __int16 *v19; // rbx
  __int64 v20; // rax
  const struct CLKRHashTable_Iterator *v21; // rax
  char v22; // bl
  __int64 i; // r12
  _BYTE v24[16]; // [rsp+28h] [rbp-69h] BYREF
  __int64 v25; // [rsp+38h] [rbp-59h]
  __int16 v26; // [rsp+44h] [rbp-4Dh]
  _BYTE v27[40]; // [rsp+50h] [rbp-41h] BYREF
  _BYTE v28[112]; // [rsp+78h] [rbp-19h] BYREF
  __int64 v29; // [rsp+F8h] [rbp+67h]

  v4 = (UL_AND_WORKER_MANAGER *)((char *)this + 336);
  result = CLKRHashTable::Size((UL_AND_WORKER_MANAGER *)((char *)this + 336));
  if ( result )
  {
    v9 = CLKRHashTable::Size(v4);
    v10 = (struct __MIDL_IW3Control_0004 *)CoTaskMemAlloc(84LL * v9);
    if ( !v10 )
      return -2147024882;
    v12 = 0;
    v13 = CLKRHashTable::Size(v4);
    v14 = (unsigned __int16 **)CoTaskMemAlloc(8LL * v13);
    if ( v14 )
    {
      ProcessInfo = 0;
      v15 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::Begin(v4, v28);
      CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v24, v15);
      CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v28);
      while ( 1 )
      {
        v21 = (const struct CLKRHashTable_Iterator *)CLKRHashTable::End(v4, v28);
        CLKRHashTable_Iterator::CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v27, v21);
        CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v28);
        v22 = CLKRHashTable_Iterator::operator!=(v24, v27);
        CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v27);
        if ( !v22 )
        {
          CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v24);
          *a2 = CLKRHashTable::Size(v4);
          *a3 = v10;
          *a4 = v14;
          return ProcessInfo;
        }
        v16 = *(WORKER_PROCESS **)(v25 + 8LL * v26 + 24);
        ProcessInfo = WORKER_PROCESS::GetProcessInfo(v16, (struct __MIDL_IW3Control_0004 *)((char *)v10 + 84 * v12));
        if ( ProcessInfo < 0 )
          break;
        v29 = *((_QWORD *)v16 + 7);
        v17 = (unsigned int)(2 * *(_DWORD *)(v29 + 72) + 2);
        v18 = (unsigned __int16 *)CoTaskMemAlloc(v17);
        v19 = v18;
        if ( !v18 )
        {
          ProcessInfo = -2147024882;
LABEL_16:
          CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v24);
          goto LABEL_19;
        }
        ProcessInfo = StringCchCopyNW(
                        v18,
                        v17 >> 1,
                        *(const unsigned __int16 **)(v29 + 56),
                        (unsigned int)(*(_DWORD *)(v29 + 72) + 1));
        if ( ProcessInfo < 0 )
          goto LABEL_16;
        v20 = v12++;
        v14[v20] = v19;
        CLKRHashTable_Iterator::Increment((CLKRHashTable_Iterator *)v24);
      }
      CLKRHashTable_Iterator::~CLKRHashTable_Iterator((CLKRHashTable_Iterator *)v24);
    }
    else
    {
      ProcessInfo = -2147024882;
    }
    v19 = 0;
LABEL_19:
    CoTaskMemFree(v10);
    if ( v19 )
      CoTaskMemFree(v19);
    if ( v14 )
    {
      for ( i = 0; (unsigned int)i < v12; i = (unsigned int)(i + 1) )
      {
        CoTaskMemFree(v14[i]);
        v14[i] = 0;
      }
      CoTaskMemFree(v14);
    }
    return ProcessInfo;
  }
  else
  {
    *a2 = 0;
    *a3 = 0;
    *a4 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180010e14  mov     rax, rsp
0x180010e17  mov     [rax+20h], r9
0x180010e1b  mov     [rax+18h], r8
0x180010e1f  mov     [rax+10h], rdx
0x180010e23  push    rbp
0x180010e24  push    rbx
0x180010e25  push    rsi
0x180010e26  push    rdi
0x180010e27  push    r12
0x180010e29  push    r13
0x180010e2b  push    r14
0x180010e2d  push    r15
0x180010e2f  lea     rbp, [rax-5Fh]
0x180010e33  sub     rsp, 0A8h
0x180010e3a  lea     r12, [rcx+150h]
0x180010e41  mov     rbx, r9
0x180010e44  mov     rcx, r12
0x180010e47  mov     rdi, r8
0x180010e4a  mov     rsi, rdx
0x180010e4d  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x180010e53  xor     r14d, r14d
0x180010e56  test    eax, eax
0x180010e58  jnz     short loc_180010E68
0x180010e5a  mov     [rsi], r14d
0x180010e5d  mov     [rdi], r14
0x180010e60  mov     [rbx], r14
0x180010e63  jmp     loc_180010FE3
0x180010e68  mov     rcx, r12
0x180010e6b  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x180010e71  mov     eax, eax
0x180010e73  imul    rcx, rax, 54h ; 'T'; cb
0x180010e77  call    cs:__imp_CoTaskMemAlloc
0x180010e7d  mov     r13, rax
0x180010e80  test    rax, rax
0x180010e83  jnz     short loc_180010E8F
0x180010e85  mov     edi, 8007000Eh
0x180010e8a  jmp     loc_180010FE1
0x180010e8f  mov     rcx, r12
0x180010e92  mov     r15d, r14d
0x180010e95  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x180010e9b  mov     ecx, eax
0x180010e9d  shl     rcx, 3; cb
0x180010ea1  call    cs:__imp_CoTaskMemAlloc
0x180010ea7  mov     r14, rax
0x180010eaa  mov     rsi, rax
0x180010ead  test    rax, rax
0x180010eb0  jnz     short loc_180010EBC
0x180010eb2  mov     edi, 8007000Eh
0x180010eb7  jmp     loc_180011012
0x180010ebc  lea     rdx, [rbp+57h+var_70]
0x180010ec0  mov     rcx, r12
0x180010ec3  xor     edi, edi
0x180010ec5  call    cs:__imp_?Begin@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::Begin(void)
0x180010ecb  mov     rdx, rax
0x180010ece  lea     rcx, [rbp+57h+var_C0]
0x180010ed2  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x180010ed8  lea     rcx, [rbp+57h+var_70]
0x180010edc  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180010ee2  jmp     loc_180010F74
0x180010ee7  movsx   rcx, [rbp+57h+var_A4]
0x180010eec  mov     rax, [rbp+57h+var_B0]
0x180010ef0  mov     rbx, [rax+rcx*8+18h]
0x180010ef5  mov     eax, r15d
0x180010ef8  mov     rcx, rbx; this
0x180010efb  imul    rdx, rax, 54h ; 'T'
0x180010eff  add     rdx, r13; struct __MIDL_IW3Control_0004 *
0x180010f02  call    ?GetProcessInfo@WORKER_PROCESS@@QEAAJPEAU__MIDL_IW3Control_0004@@@Z; WORKER_PROCESS::GetProcessInfo(__MIDL_IW3Control_0004 *)
0x180010f07  mov     edi, eax
0x180010f09  test    eax, eax
0x180010f0b  js      loc_180011008
0x180010f11  mov     rax, [rbx+38h]
0x180010f15  mov     [rbp+57h+arg_0], rax
0x180010f19  mov     eax, [rax+48h]
0x180010f1c  lea     eax, ds:2[rax*2]
0x180010f23  mov     ecx, eax; cb
0x180010f25  mov     edi, eax
0x180010f27  call    cs:__imp_CoTaskMemAlloc
0x180010f2d  mov     rbx, rax
0x180010f30  test    rax, rax
0x180010f33  jz      loc_180010FF7
0x180010f39  mov     r8, [rbp+57h+arg_0]
0x180010f3d  mov     rcx, rax; unsigned __int16 *
0x180010f40  shr     rdi, 1
0x180010f43  mov     rdx, rdi; unsigned __int64
0x180010f46  mov     r9d, [r8+48h]
0x180010f4a  mov     r8, [r8+38h]; unsigned __int16 *
0x180010f4e  inc     r9d; unsigned __int64
0x180010f51  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180010f56  lea     rcx, [rbp+57h+var_C0]
0x180010f5a  mov     edi, eax
0x180010f5c  test    eax, eax
0x180010f5e  js      loc_180011000
0x180010f64  mov     eax, r15d
0x180010f67  inc     r15d
0x180010f6a  mov     [r14+rax*8], rbx
0x180010f6e  call    cs:__imp_?Increment@CLKRHashTable_Iterator@@QEAA_NXZ; CLKRHashTable_Iterator::Increment(void)
0x180010f74  lea     rdx, [rbp+57h+var_70]
0x180010f78  mov     rcx, r12
0x180010f7b  call    cs:__imp_?End@CLKRHashTable@@QEAA?AVCLKRHashTable_Iterator@@XZ; CLKRHashTable::End(void)
0x180010f81  mov     rdx, rax
0x180010f84  lea     rcx, [rbp+57h+var_98]
0x180010f88  call    cs:__imp_??0CLKRHashTable_Iterator@@QEAA@AEBV0@@Z; CLKRHashTable_Iterator::CLKRHashTable_Iterator(CLKRHashTable_Iterator const &)
0x180010f8e  lea     rcx, [rbp+57h+var_70]
0x180010f92  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180010f98  lea     rdx, [rbp+57h+var_98]
0x180010f9c  lea     rcx, [rbp+57h+var_C0]
0x180010fa0  call    cs:__imp_??9CLKRHashTable_Iterator@@QEBA_NAEBV0@@Z; CLKRHashTable_Iterator::operator!=(CLKRHashTable_Iterator const &)
0x180010fa6  lea     rcx, [rbp+57h+var_98]
0x180010faa  mov     bl, al
0x180010fac  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180010fb2  test    bl, bl
0x180010fb4  jnz     loc_180010EE7
0x180010fba  lea     rcx, [rbp+57h+var_C0]
0x180010fbe  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180010fc4  mov     rcx, r12
0x180010fc7  call    cs:__imp_?Size@CLKRHashTable@@QEBAKXZ; CLKRHashTable::Size(void)
0x180010fcd  mov     rcx, [rbp+57h+arg_8]
0x180010fd1  mov     [rcx], eax
0x180010fd3  mov     rax, [rbp+57h+arg_10]
0x180010fd7  mov     [rax], r13
0x180010fda  mov     rax, [rbp+57h+arg_18]
0x180010fde  mov     [rax], r14
0x180010fe1  mov     eax, edi
0x180010fe3  add     rsp, 0A8h
0x180010fea  pop     r15
0x180010fec  pop     r14
0x180010fee  pop     r13
0x180010ff0  pop     r12
0x180010ff2  pop     rdi
0x180010ff3  pop     rsi
0x180010ff4  pop     rbx
0x180010ff5  pop     rbp
0x180010ff6  retn
0x180010ff7  mov     edi, 8007000Eh
0x180010ffc  lea     rcx, [rbp+57h+var_C0]
0x180011000  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180011006  jmp     short loc_180011014
0x180011008  lea     rcx, [rbp+57h+var_C0]
0x18001100c  call    cs:__imp_??1CLKRHashTable_Iterator@@QEAA@XZ; CLKRHashTable_Iterator::~CLKRHashTable_Iterator(void)
0x180011012  xor     ebx, ebx
0x180011014  mov     rcx, r13; pv
0x180011017  call    cs:__imp_CoTaskMemFree
0x18001101d  test    rbx, rbx
0x180011020  jz      short loc_18001102B
0x180011022  mov     rcx, rbx; pv
0x180011025  call    cs:__imp_CoTaskMemFree
0x18001102b  test    r14, r14
0x18001102e  jz      short loc_180010FE1
0x180011030  xor     r12d, r12d
0x180011033  test    r15d, r15d
0x180011036  jz      short loc_180011052
0x180011038  mov     rcx, [rsi+r12*8]; pv
0x18001103c  call    cs:__imp_CoTaskMemFree
0x180011042  mov     qword ptr [rsi+r12*8], 0
0x18001104a  inc     r12d
0x18001104d  cmp     r12d, r15d
0x180011050  jb      short loc_180011038
0x180011052  mov     rcx, r14; pv
0x180011055  call    cs:__imp_CoTaskMemFree
0x18001105b  jmp     short loc_180010FE1
```
