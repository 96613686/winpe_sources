# QueryContextAttributesW

- ea: `0x180029570`
- end: `0x180029689`
- name: `QueryContextAttributesW`
- size: `281`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, unsigned int ulAttribute, void *pBuffer)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001c00`
- `0x180001cf0`
- `0x180001f90`
- `0x180002820`
- `0x180004c74`
- `0x180010d00`
- `0x180029570`
- `0x1800297f0`

## pseudocode

```c
SECURITY_STATUS __stdcall QueryContextAttributesW(PCtxtHandle phContext, unsigned int ulAttribute, void *pBuffer)
{
  __int64 v4; // rdi
  __int64 v6; // rbx
  unsigned int v7; // ecx
  ULONG_PTR dwLower; // r10
  __int64 v9; // rax
  unsigned int v10; // edx
  __int64 i; // rcx
  SECURITY_STATUS ContextAttributes; // ebx
  struct _KSECDDLSASTATE *v14; // rax
  char v15; // [rsp+60h] [rbp+8h] BYREF

  v4 = ulAttribute;
  KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v15);
  if ( !phContext || !pBuffer )
    goto LABEL_18;
  if ( !KsecddLsaStateRef::IsValid((KsecddLsaStateRef *)&v15) )
  {
    ContextAttributes = -1073741058;
    goto LABEL_12;
  }
  v6 = KsecddLsaStateRef::operator _KSECDDLSASTATE *(&v15);
  if ( !*(_QWORD *)(v6 + 456) )
  {
    ContextAttributes = -1073741823;
    goto LABEL_12;
  }
  v7 = (unsigned int)v4 < 0x16 ? *((_DWORD *)&KsecQuerySizes + v4) : 0;
  memset(pBuffer, 0, v7);
  dwLower = phContext->dwLower;
  if ( phContext->dwLower >= *(unsigned int *)(v6 + 464) )
  {
LABEL_18:
    ContextAttributes = -2146893055;
    goto LABEL_12;
  }
  v9 = *(_QWORD *)(v6 + 528);
  v10 = *(_DWORD *)(v9 + 16 * dwLower);
  if ( v10 )
  {
    for ( i = 0; (unsigned int)i < v10; i = (unsigned int)(i + 1) )
    {
      if ( *(_DWORD *)(*(_QWORD *)(v9 + 16 * dwLower + 8) + 4 * i) == (_DWORD)v4 )
      {
        v14 = (struct _KSECDDLSASTATE *)KsecddLsaStateRef::operator _KSECDDLSASTATE *(&v15);
        ContextAttributes = ThunkedQueryContextAttributes(v14, phContext, v4, pBuffer, 0);
        goto LABEL_12;
      }
    }
  }
  ContextAttributes = KernelPackageCallValidatorWorkers::CallValidator<long (*_SECPKG_KERNEL_FUNCTION_TABLE::*)(unsigned __int64,unsigned long,void *),72>::InvokeById(
                        phContext->dwLower,
                        phContext->dwUpper,
                        (unsigned int)v4,
                        pBuffer);
LABEL_12:
  KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v15);
  return ContextAttributes;
}

```

## disassembly

```asm
0x180029570  push    rbx
0x180029572  push    rsi
0x180029573  push    rdi
0x180029574  push    r14
0x180029576  sub     rsp, 38h
0x18002957a  mov     r14, rcx
0x18002957d  mov     edi, edx
0x18002957f  lea     rcx, [rsp+58h+arg_0]; this
0x180029584  mov     rsi, r8
0x180029587  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x18002958c  test    r14, r14
0x18002958f  jz      loc_18002965B
0x180029595  test    rsi, rsi
0x180029598  jz      loc_18002965B
0x18002959e  lea     rcx, [rsp+58h+arg_0]; this
0x1800295a3  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x1800295a8  test    al, al
0x1800295aa  jz      loc_180029654
0x1800295b0  lea     rcx, [rsp+58h+arg_0]
0x1800295b5  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x1800295ba  mov     rbx, rax
0x1800295bd  cmp     qword ptr [rax+1C8h], 0
0x1800295c5  jz      loc_18002964D
0x1800295cb  cmp     edi, 16h
0x1800295ce  jb      short loc_180029641
0x1800295d0  xor     ecx, ecx
0x1800295d2  mov     r8d, ecx; Size
0x1800295d5  xor     edx, edx; Val
0x1800295d7  mov     rcx, rsi; void *
0x1800295da  call    memset
0x1800295df  mov     r10, [r14]
0x1800295e2  mov     eax, [rbx+1D0h]
0x1800295e8  cmp     r10, rax
0x1800295eb  jnb     short loc_18002965B
0x1800295ed  mov     rax, [rbx+210h]
0x1800295f4  mov     rcx, r10
0x1800295f7  add     rcx, rcx
0x1800295fa  mov     edx, [rax+rcx*8]
0x1800295fd  test    edx, edx
0x1800295ff  jz      short loc_18002960C
0x180029601  mov     r8, [rax+rcx*8+8]
0x180029606  xor     ecx, ecx
0x180029608  cmp     ecx, edx
0x18002960a  jb      short loc_180029637
0x18002960c  mov     rdx, [r14+8]
0x180029610  mov     r9, rsi
0x180029613  mov     r8d, edi
0x180029616  mov     rcx, r10
0x180029619  call    ?InvokeById@?$CallValidator@PEQ_SECPKG_KERNEL_FUNCTION_TABLE@@P6AJ_KKPEAX@Z$0EI@@KernelPackageCallValidatorWorkers@@SAJ_K0KPEAX@Z; KernelPackageCallValidatorWorkers::CallValidator<long (*_SECPKG_KERNEL_FUNCTION_TABLE::*)(unsigned __int64,ulong,void *),72>::InvokeById(unsigned __int64,unsigned __int64,ulong,void *)
0x18002961e  mov     ebx, eax
0x180029620  lea     rcx, [rsp+58h+arg_0]; this
0x180029625  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18002962a  mov     eax, ebx
0x18002962c  add     rsp, 38h
0x180029630  pop     r14
0x180029632  pop     rdi
0x180029633  pop     rsi
0x180029634  pop     rbx
0x180029635  retn
0x180029637  cmp     [r8+rcx*4], edi
0x18002963b  jz      short loc_180029662
0x18002963d  inc     ecx
0x18002963f  jmp     short loc_180029608
0x180029641  lea     rcx, ?KsecQuerySizes@@3PAKA; ulong near * KsecQuerySizes
0x180029648  mov     ecx, [rcx+rdi*4]
0x18002964b  jmp     short loc_1800295D2
0x18002964d  mov     ebx, 0C0000001h
0x180029652  jmp     short loc_180029620
0x180029654  mov     ebx, 0C00002FEh
0x180029659  jmp     short loc_180029620
0x18002965b  mov     ebx, 80090301h
0x180029660  jmp     short loc_180029620
0x180029662  lea     rcx, [rsp+58h+arg_0]
0x180029667  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x18002966c  mov     rcx, rax; struct _KSECDDLSASTATE *
0x18002966f  mov     [rsp+58h+var_38], 0; unsigned int
0x180029677  mov     r9, rsi; void *
0x18002967a  mov     r8d, edi; unsigned int
0x18002967d  mov     rdx, r14; struct _SecHandle *
0x180029680  call    ?ThunkedQueryContextAttributes@@YAJPEAU_KSECDDLSASTATE@@PEAU_SecHandle@@KPEAXK@Z; ThunkedQueryContextAttributes(_KSECDDLSASTATE *,_SecHandle *,ulong,void *,ulong)
0x180029685  mov     ebx, eax
0x180029687  jmp     short loc_180029620
```
