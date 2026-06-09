# DecryptMessage

- ea: `0x180029c90`
- end: `0x180029d76`
- name: `DecryptMessage`
- size: `230`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, PSecBufferDesc pMessage, unsigned int MessageSeqNo, unsigned int *pfQOP)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001c00`
- `0x180001cf0`
- `0x180001f90`
- `0x180002820`
- `0x180010980`
- `0x180029c90`

## pseudocode

```c
SECURITY_STATUS __stdcall DecryptMessage(
        PCtxtHandle phContext,
        PSecBufferDesc pMessage,
        unsigned int MessageSeqNo,
        unsigned int *pfQOP)
{
  ULONG_PTR dwLower; // rbp
  ULONG_PTR dwUpper; // r14
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 (__fastcall *v11)(ULONG_PTR, PSecBufferDesc, _QWORD, unsigned int *); // rax
  SECURITY_STATUS v12; // ebx
  char v14; // [rsp+50h] [rbp+8h] BYREF

  if ( !phContext || !pMessage )
    return -2146893055;
  dwLower = phContext->dwLower;
  dwUpper = phContext->dwUpper;
  KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v14);
  if ( KsecddLsaStateRef::IsValid((KsecddLsaStateRef *)&v14) )
  {
    v9 = KsecddLsaStateRef::operator _KSECDDLSASTATE *(&v14);
    if ( *(_QWORD *)(v9 + 456) )
    {
      if ( dwLower < *(unsigned int *)(v9 + 464)
        && (_mm_lfence(), (v10 = *(_QWORD *)(*(_QWORD *)(v9 + 456) + 8 * dwLower)) != 0) )
      {
        v11 = *(__int64 (__fastcall **)(ULONG_PTR, PSecBufferDesc, _QWORD, unsigned int *))(v10 + 56);
        if ( v11 )
          v12 = v11(dwUpper, pMessage, MessageSeqNo, pfQOP);
        else
          v12 = -2146893054;
      }
      else
      {
        v12 = -2146893055;
      }
    }
    else
    {
      v12 = -1073741823;
    }
  }
  else
  {
    v12 = -1073741058;
  }
  KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v14);
  return v12;
}

```

## disassembly

```asm
0x180029c90  push    rbx
0x180029c92  push    rsi
0x180029c93  push    rdi
0x180029c94  sub     rsp, 30h
0x180029c98  mov     rdi, r9
0x180029c9b  mov     esi, r8d
0x180029c9e  mov     rbx, rdx
0x180029ca1  test    rcx, rcx
0x180029ca4  jz      loc_180029D4C
0x180029caa  test    rdx, rdx
0x180029cad  jz      loc_180029D4C
0x180029cb3  mov     [rsp+48h+arg_8], rbp
0x180029cb8  mov     rbp, [rcx]
0x180029cbb  mov     [rsp+48h+arg_10], r14
0x180029cc0  mov     r14, [rcx+8]
0x180029cc4  lea     rcx, [rsp+48h+arg_0]; this
0x180029cc9  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180029cce  lea     rcx, [rsp+48h+arg_0]; this
0x180029cd3  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x180029cd8  test    al, al
0x180029cda  jz      short loc_180029D5A
0x180029cdc  lea     rcx, [rsp+48h+arg_0]
0x180029ce1  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x180029ce6  mov     rcx, rax
0x180029ce9  cmp     qword ptr [rax+1C8h], 0
0x180029cf1  jz      short loc_180029D68
0x180029cf3  mov     eax, [rax+1D0h]
0x180029cf9  cmp     rbp, rax
0x180029cfc  jnb     short loc_180029D6F
0x180029cfe  lfence
0x180029d01  mov     rax, [rcx+1C8h]
0x180029d08  mov     rcx, [rax+rbp*8]
0x180029d0c  test    rcx, rcx
0x180029d0f  jz      short loc_180029D6F
0x180029d11  mov     rax, [rcx+38h]
0x180029d15  test    rax, rax
0x180029d18  jz      short loc_180029D61
0x180029d1a  mov     r9, rdi
0x180029d1d  mov     r8d, esi
0x180029d20  mov     rdx, rbx
0x180029d23  mov     rcx, r14
0x180029d26  call    _guard_dispatch_icall
0x180029d2b  mov     ebx, eax
0x180029d2d  lea     rcx, [rsp+48h+arg_0]; this
0x180029d32  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180029d37  mov     r14, [rsp+48h+arg_10]
0x180029d3c  mov     eax, ebx
0x180029d3e  mov     rbp, [rsp+48h+arg_8]
0x180029d43  add     rsp, 30h
0x180029d47  pop     rdi
0x180029d48  pop     rsi
0x180029d49  pop     rbx
0x180029d4a  retn
0x180029d4c  mov     eax, 80090301h
0x180029d51  add     rsp, 30h
0x180029d55  pop     rdi
0x180029d56  pop     rsi
0x180029d57  pop     rbx
0x180029d58  retn
0x180029d5a  mov     ebx, 0C00002FEh
0x180029d5f  jmp     short loc_180029D2D
0x180029d61  mov     ebx, 80090302h
0x180029d66  jmp     short loc_180029D2D
0x180029d68  mov     ebx, 0C0000001h
0x180029d6d  jmp     short loc_180029D2D
0x180029d6f  mov     ebx, 80090301h
0x180029d74  jmp     short loc_180029D2D
```
