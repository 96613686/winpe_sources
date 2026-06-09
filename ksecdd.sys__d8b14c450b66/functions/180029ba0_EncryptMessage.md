# EncryptMessage

- ea: `0x180029ba0`
- end: `0x180029c7c`
- name: `EncryptMessage`
- size: `220`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, unsigned int fQOP, PSecBufferDesc pMessage, unsigned int MessageSeqNo)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001c00`
- `0x180001cf0`
- `0x180001f90`
- `0x180002820`
- `0x180010920`
- `0x180029ba0`

## pseudocode

```c
SECURITY_STATUS __stdcall EncryptMessage(
        PCtxtHandle phContext,
        unsigned int fQOP,
        PSecBufferDesc pMessage,
        unsigned int MessageSeqNo)
{
  ULONG_PTR dwLower; // rbp
  ULONG_PTR dwUpper; // r14
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 (__fastcall *v12)(ULONG_PTR, _QWORD, PSecBufferDesc, _QWORD); // rax
  SECURITY_STATUS v13; // ebx
  char v14; // [rsp+50h] [rbp+8h] BYREF

  if ( !phContext || !pMessage )
    return -2146893055;
  dwLower = phContext->dwLower;
  dwUpper = phContext->dwUpper;
  KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v14);
  if ( KsecddLsaStateRef::IsValid((KsecddLsaStateRef *)&v14) )
  {
    v10 = KsecddLsaStateRef::operator _KSECDDLSASTATE *(&v14);
    if ( *(_QWORD *)(v10 + 456) )
    {
      if ( dwLower < *(unsigned int *)(v10 + 464)
        && (_mm_lfence(), (v11 = *(_QWORD *)(*(_QWORD *)(v10 + 456) + 8 * dwLower)) != 0) )
      {
        v12 = *(__int64 (__fastcall **)(ULONG_PTR, _QWORD, PSecBufferDesc, _QWORD))(v11 + 48);
        if ( v12 )
          v13 = v12(dwUpper, fQOP, pMessage, MessageSeqNo);
        else
          v13 = -2146893054;
      }
      else
      {
        v13 = -2146893055;
      }
    }
    else
    {
      v13 = -1073741823;
    }
  }
  else
  {
    v13 = -1073741058;
  }
  KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v14);
  return v13;
}

```

## disassembly

```asm
0x180029ba0  push    rbx
0x180029ba2  push    rsi
0x180029ba3  push    rdi
0x180029ba4  sub     rsp, 30h
0x180029ba8  mov     edi, r9d
0x180029bab  mov     rbx, r8
0x180029bae  mov     esi, edx
0x180029bb0  test    rcx, rcx
0x180029bb3  jnz     short loc_180029BC3
0x180029bb5  mov     eax, 80090301h
0x180029bba  add     rsp, 30h
0x180029bbe  pop     rdi
0x180029bbf  pop     rsi
0x180029bc0  pop     rbx
0x180029bc1  retn
0x180029bc3  test    rbx, rbx
0x180029bc6  jz      short loc_180029BB5
0x180029bc8  mov     [rsp+48h+arg_8], rbp
0x180029bcd  mov     rbp, [rcx]
0x180029bd0  mov     [rsp+48h+arg_10], r14
0x180029bd5  mov     r14, [rcx+8]
0x180029bd9  lea     rcx, [rsp+48h+arg_0]; this
0x180029bde  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180029be3  lea     rcx, [rsp+48h+arg_0]; this
0x180029be8  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x180029bed  test    al, al
0x180029bef  jz      short loc_180029C67
0x180029bf1  lea     rcx, [rsp+48h+arg_0]
0x180029bf6  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x180029bfb  mov     rcx, rax
0x180029bfe  cmp     qword ptr [rax+1C8h], 0
0x180029c06  jz      short loc_180029C6E
0x180029c08  mov     eax, [rax+1D0h]
0x180029c0e  cmp     rbp, rax
0x180029c11  jnb     short loc_180029C75
0x180029c13  lfence
0x180029c16  mov     rax, [rcx+1C8h]
0x180029c1d  mov     rcx, [rax+rbp*8]
0x180029c21  test    rcx, rcx
0x180029c24  jz      short loc_180029C75
0x180029c26  mov     rax, [rcx+30h]
0x180029c2a  test    rax, rax
0x180029c2d  jz      short loc_180029C60
0x180029c2f  mov     r9d, edi
0x180029c32  mov     r8, rbx
0x180029c35  mov     edx, esi
0x180029c37  mov     rcx, r14
0x180029c3a  call    _guard_dispatch_icall
0x180029c3f  mov     ebx, eax
0x180029c41  lea     rcx, [rsp+48h+arg_0]; this
0x180029c46  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180029c4b  mov     r14, [rsp+48h+arg_10]
0x180029c50  mov     eax, ebx
0x180029c52  mov     rbp, [rsp+48h+arg_8]
0x180029c57  add     rsp, 30h
0x180029c5b  pop     rdi
0x180029c5c  pop     rsi
0x180029c5d  pop     rbx
0x180029c5e  retn
0x180029c60  mov     ebx, 80090302h
0x180029c65  jmp     short loc_180029C41
0x180029c67  mov     ebx, 0C00002FEh
0x180029c6c  jmp     short loc_180029C41
0x180029c6e  mov     ebx, 0C0000001h
0x180029c73  jmp     short loc_180029C41
0x180029c75  mov     ebx, 80090301h
0x180029c7a  jmp     short loc_180029C41
```
