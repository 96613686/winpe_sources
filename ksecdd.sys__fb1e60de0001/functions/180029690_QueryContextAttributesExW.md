# QueryContextAttributesExW

- ea: `0x180029690`
- end: `0x1800297e3`
- name: `QueryContextAttributesExW`
- size: `339`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, unsigned int ulAttribute, void *pBuffer, unsigned int cbBuffer)`
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
- `0x180029690`
- `0x1800297f0`

## pseudocode

```c
SECURITY_STATUS __stdcall QueryContextAttributesExW(
        PCtxtHandle phContext,
        unsigned int ulAttribute,
        void *pBuffer,
        unsigned int cbBuffer)
{
  __int64 v5; // rdi
  __int64 v8; // rbx
  unsigned int v9; // ecx
  ULONG_PTR dwLower; // r10
  __int64 v11; // rax
  unsigned int v12; // edx
  __int64 v13; // r8
  __int64 i; // rax
  SECURITY_STATUS ContextAttributes; // ebx
  struct _KSECDDLSASTATE *v17; // rax
  char v18; // [rsp+50h] [rbp+8h] BYREF

  v5 = ulAttribute;
  KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v18);
  if ( phContext && pBuffer )
  {
    if ( KsecddLsaStateRef::IsValid((KsecddLsaStateRef *)&v18) )
    {
      v8 = KsecddLsaStateRef::operator _KSECDDLSASTATE *(&v18);
      if ( *(_QWORD *)(v8 + 456) )
      {
        if ( (unsigned int)v5 < 0x16 )
          v9 = *((_DWORD *)&KsecQuerySizes + v5);
        else
          v9 = 0;
        memset(pBuffer, 0, v9);
        dwLower = phContext->dwLower;
        if ( phContext->dwLower >= *(unsigned int *)(v8 + 464) )
        {
          ContextAttributes = -2146893055;
        }
        else
        {
          v11 = *(_QWORD *)(v8 + 528);
          v12 = *(_DWORD *)(v11 + 16 * dwLower);
          if ( v12 )
          {
            v13 = *(_QWORD *)(v11 + 16 * dwLower + 8);
            for ( i = 0; (unsigned int)i < v12; i = (unsigned int)(i + 1) )
            {
              if ( *(_DWORD *)(v13 + 4 * i) == (_DWORD)v5 )
              {
                v17 = (struct _KSECDDLSASTATE *)KsecddLsaStateRef::operator _KSECDDLSASTATE *(&v18);
                ContextAttributes = ThunkedQueryContextAttributes(v17, phContext, v5, pBuffer, cbBuffer);
                goto LABEL_12;
              }
            }
          }
          ContextAttributes = KernelPackageCallValidatorWorkers::CallValidator<long (*_SECPKG_KERNEL_FUNCTION_TABLE::*)(unsigned __int64,unsigned long,void *),72>::InvokeById(
                                phContext->dwLower,
                                phContext->dwUpper,
                                (unsigned int)v5,
                                pBuffer);
        }
LABEL_12:
        KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v18);
        return ContextAttributes;
      }
      else
      {
        KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v18);
        return -1073741823;
      }
    }
    else
    {
      KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v18);
      return -1073741058;
    }
  }
  else
  {
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v18);
    return -2146893055;
  }
}

```

## disassembly

```asm
0x180029690  mov     [rsp+arg_8], rbx
0x180029695  mov     [rsp+arg_10], rbp
0x18002969a  push    rsi
0x18002969b  push    rdi
0x18002969c  push    r14
0x18002969e  sub     rsp, 30h
0x1800296a2  mov     r14, rcx
0x1800296a5  mov     edi, edx
0x1800296a7  lea     rcx, [rsp+48h+arg_0]; this
0x1800296ac  mov     ebp, r9d
0x1800296af  mov     rsi, r8
0x1800296b2  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x1800296b7  test    r14, r14
0x1800296ba  jz      loc_1800297CF
0x1800296c0  test    rsi, rsi
0x1800296c3  jz      loc_1800297CF
0x1800296c9  lea     rcx, [rsp+48h+arg_0]; this
0x1800296ce  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x1800296d3  lea     rcx, [rsp+48h+arg_0]; this
0x1800296d8  test    al, al
0x1800296da  jz      loc_180029799
0x1800296e0  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x1800296e5  mov     rbx, rax
0x1800296e8  cmp     qword ptr [rax+1C8h], 0
0x1800296f0  jz      loc_180029788
0x1800296f6  cmp     edi, 16h
0x1800296f9  jb      short loc_180029779
0x1800296fb  xor     ecx, ecx
0x1800296fd  mov     r8d, ecx; Size
0x180029700  xor     edx, edx; Val
0x180029702  mov     rcx, rsi; void *
0x180029705  call    memset
0x18002970a  mov     r10, [r14]
0x18002970d  mov     eax, [rbx+1D0h]
0x180029713  cmp     r10, rax
0x180029716  jnb     loc_1800297A5
0x18002971c  mov     rax, [rbx+210h]
0x180029723  mov     rcx, r10
0x180029726  add     rcx, rcx
0x180029729  mov     edx, [rax+rcx*8]
0x18002972c  test    edx, edx
0x18002972e  jz      short loc_18002973B
0x180029730  mov     r8, [rax+rcx*8+8]
0x180029735  xor     eax, eax
0x180029737  cmp     eax, edx
0x180029739  jb      short loc_18002976F
0x18002973b  mov     rdx, [r14+8]
0x18002973f  mov     r9, rsi
0x180029742  mov     r8d, edi
0x180029745  mov     rcx, r10
0x180029748  call    ?InvokeById@?$CallValidator@PEQ_SECPKG_KERNEL_FUNCTION_TABLE@@P6AJ_KKPEAX@Z$0EI@@KernelPackageCallValidatorWorkers@@SAJ_K0KPEAX@Z; KernelPackageCallValidatorWorkers::CallValidator<long (*_SECPKG_KERNEL_FUNCTION_TABLE::*)(unsigned __int64,ulong,void *),72>::InvokeById(unsigned __int64,unsigned __int64,ulong,void *)
0x18002974d  mov     ebx, eax
0x18002974f  lea     rcx, [rsp+48h+arg_0]; this
0x180029754  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180029759  mov     eax, ebx
0x18002975b  mov     rbx, [rsp+48h+arg_8]
0x180029760  mov     rbp, [rsp+48h+arg_10]
0x180029765  add     rsp, 30h
0x180029769  pop     r14
0x18002976b  pop     rdi
0x18002976c  pop     rsi
0x18002976d  retn
0x18002976f  cmp     [r8+rax*4], edi
0x180029773  jz      short loc_1800297AC
0x180029775  inc     eax
0x180029777  jmp     short loc_180029737
0x180029779  lea     rcx, ?KsecQuerySizes@@3PAKA; ulong near * KsecQuerySizes
0x180029780  mov     ecx, [rcx+rdi*4]
0x180029783  jmp     loc_1800296FD
0x180029788  lea     rcx, [rsp+48h+arg_0]; this
0x18002978d  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180029792  mov     eax, 0C0000001h
0x180029797  jmp     short loc_18002975B
0x180029799  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18002979e  mov     eax, 0C00002FEh
0x1800297a3  jmp     short loc_18002975B
0x1800297a5  mov     ebx, 80090301h
0x1800297aa  jmp     short loc_18002974F
0x1800297ac  lea     rcx, [rsp+48h+arg_0]
0x1800297b1  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x1800297b6  mov     rcx, rax; struct _KSECDDLSASTATE *
0x1800297b9  mov     [rsp+48h+var_28], ebp; unsigned int
0x1800297bd  mov     r9, rsi; void *
0x1800297c0  mov     r8d, edi; unsigned int
0x1800297c3  mov     rdx, r14; struct _SecHandle *
0x1800297c6  call    ?ThunkedQueryContextAttributes@@YAJPEAU_KSECDDLSASTATE@@PEAU_SecHandle@@KPEAXK@Z; ThunkedQueryContextAttributes(_KSECDDLSASTATE *,_SecHandle *,ulong,void *,ulong)
0x1800297cb  mov     ebx, eax
0x1800297cd  jmp     short loc_18002974F
0x1800297cf  lea     rcx, [rsp+48h+arg_0]; this
0x1800297d4  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x1800297d9  mov     eax, 80090301h
0x1800297de  jmp     loc_18002975B
```
