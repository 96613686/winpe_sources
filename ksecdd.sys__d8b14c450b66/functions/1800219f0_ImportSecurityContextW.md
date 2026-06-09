# ImportSecurityContextW

- ea: `0x1800219f0`
- end: `0x180021b10`
- name: `ImportSecurityContextW`
- size: `288`
- prototype: `SECURITY_STATUS __stdcall(PSECURITY_STRING pszPackage, PSecBuffer pPackedContext, void *Token, PCtxtHandle phContext)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800018f8`
- `0x180001c00`
- `0x180001cf0`
- `0x180001f90`
- `0x180002820`
- `0x180010920`
- `0x1800219f0`

## pseudocode

```c
SECURITY_STATUS __stdcall ImportSecurityContextW(
        PSECURITY_STRING pszPackage,
        PSecBuffer pPackedContext,
        void *Token,
        PCtxtHandle phContext)
{
  SECURITY_STATUS v8; // ebx
  __int64 (__fastcall *v10)(PSecBuffer, void *, ULONG_PTR *); // rax
  _BYTE v11[8]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v12; // [rsp+28h] [rbp-28h]
  _BYTE v13[8]; // [rsp+30h] [rbp-20h] BYREF
  ULONG_PTR v14; // [rsp+38h] [rbp-18h] BYREF
  ULONG_PTR v15; // [rsp+40h] [rbp-10h]

  v12 = 0;
  v14 = -1;
  v15 = 0;
  KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)v11);
  if ( !KsecddLsaStateRef::IsValid((KsecddLsaStateRef *)v11) )
  {
    v8 = -1073741058;
LABEL_9:
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)v11);
    return v8;
  }
  if ( !*(_QWORD *)(KsecddLsaStateRef::operator _KSECDDLSASTATE *(v11) + 456) )
  {
    v8 = -1073741823;
    goto LABEL_9;
  }
  if ( pPackedContext && phContext )
  {
    if ( (int)KSecLocatePackageEx(pszPackage) >= 0 )
    {
      KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)v13);
      if ( KsecddLsaStateRef::IsValid((KsecddLsaStateRef *)v13) )
      {
        v10 = *(__int64 (__fastcall **)(PSecBuffer, void *, ULONG_PTR *))(v12 + 96);
        if ( v10 )
          v8 = v10(pPackedContext, Token, &v14);
        else
          v8 = -2146893054;
      }
      else
      {
        v8 = -1073741058;
      }
      KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)v13);
      if ( v8 >= 0 )
      {
        phContext->dwUpper = v14;
        phContext->dwLower = v15;
      }
    }
    else
    {
      v8 = -2146893051;
    }
    goto LABEL_9;
  }
  KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)v11);
  return -1073741811;
}

```

## disassembly

```asm
0x1800219f0  push    rbp
0x1800219f2  push    rbx
0x1800219f3  push    rsi
0x1800219f4  push    rdi
0x1800219f5  push    r14
0x1800219f7  mov     rbp, rsp
0x1800219fa  sub     rsp, 50h
0x1800219fe  mov     rsi, rcx
0x180021a01  mov     [rbp+var_28], 0
0x180021a09  lea     rcx, [rbp+var_30]; this
0x180021a0d  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFFh
0x180021a15  mov     rdi, r9
0x180021a18  mov     [rbp+var_10], 0
0x180021a20  mov     r14, r8
0x180021a23  mov     rbx, rdx
0x180021a26  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180021a2b  lea     rcx, [rbp+var_30]; this
0x180021a2f  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x180021a34  test    al, al
0x180021a36  jnz     short loc_180021A3F
0x180021a38  mov     ebx, 0C00002FEh
0x180021a3d  jmp     short loc_180021A89
0x180021a3f  lea     rcx, [rbp+var_30]
0x180021a43  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x180021a48  cmp     qword ptr [rax+1C8h], 0
0x180021a50  jnz     short loc_180021A59
0x180021a52  mov     ebx, 0C0000001h
0x180021a57  jmp     short loc_180021A89
0x180021a59  test    rbx, rbx
0x180021a5c  jz      loc_180021AF6
0x180021a62  test    rdi, rdi
0x180021a65  jz      loc_180021AF6
0x180021a6b  lea     r9, [rbp+var_10]
0x180021a6f  mov     edx, 1
0x180021a74  lea     r8, [rbp+var_28]
0x180021a78  mov     rcx, rsi; String1
0x180021a7b  call    KSecLocatePackageEx
0x180021a80  test    eax, eax
0x180021a82  jns     short loc_180021A96
0x180021a84  mov     ebx, 80090305h
0x180021a89  lea     rcx, [rbp+var_30]; this
0x180021a8d  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180021a92  mov     eax, ebx
0x180021a94  jmp     short loc_180021B04
0x180021a96  lea     rcx, [rbp+var_20]; this
0x180021a9a  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180021a9f  lea     rcx, [rbp+var_20]; this
0x180021aa3  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x180021aa8  test    al, al
0x180021aaa  jnz     short loc_180021AB3
0x180021aac  mov     ebx, 0C00002FEh
0x180021ab1  jmp     short loc_180021AD8
0x180021ab3  mov     rax, [rbp+var_28]
0x180021ab7  mov     rax, [rax+60h]
0x180021abb  test    rax, rax
0x180021abe  jnz     short loc_180021AC7
0x180021ac0  mov     ebx, 80090302h
0x180021ac5  jmp     short loc_180021AD8
0x180021ac7  lea     r8, [rbp+var_18]
0x180021acb  mov     rdx, r14
0x180021ace  mov     rcx, rbx
0x180021ad1  call    _guard_dispatch_icall
0x180021ad6  mov     ebx, eax
0x180021ad8  lea     rcx, [rbp+var_20]; this
0x180021adc  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180021ae1  test    ebx, ebx
0x180021ae3  js      short loc_180021A89
0x180021ae5  mov     rcx, [rbp+var_18]
0x180021ae9  mov     [rdi+8], rcx
0x180021aed  mov     rcx, [rbp+var_10]
0x180021af1  mov     [rdi], rcx
0x180021af4  jmp     short loc_180021A89
0x180021af6  lea     rcx, [rbp+var_30]; this
0x180021afa  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180021aff  mov     eax, 0C000000Dh
0x180021b04  add     rsp, 50h
0x180021b08  pop     r14
0x180021b0a  pop     rdi
0x180021b0b  pop     rsi
0x180021b0c  pop     rbx
0x180021b0d  pop     rbp
0x180021b0e  retn
```
