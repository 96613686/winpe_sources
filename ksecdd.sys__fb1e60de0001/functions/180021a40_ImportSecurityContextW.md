# ImportSecurityContextW

- ea: `0x180021a40`
- end: `0x180021b60`
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
- `0x180010980`
- `0x180021a40`

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
0x180021a40  push    rbp
0x180021a42  push    rbx
0x180021a43  push    rsi
0x180021a44  push    rdi
0x180021a45  push    r14
0x180021a47  mov     rbp, rsp
0x180021a4a  sub     rsp, 50h
0x180021a4e  mov     rsi, rcx
0x180021a51  mov     [rbp+var_28], 0
0x180021a59  lea     rcx, [rbp+var_30]; this
0x180021a5d  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFFh
0x180021a65  mov     rdi, r9
0x180021a68  mov     [rbp+var_10], 0
0x180021a70  mov     r14, r8
0x180021a73  mov     rbx, rdx
0x180021a76  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180021a7b  lea     rcx, [rbp+var_30]; this
0x180021a7f  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x180021a84  test    al, al
0x180021a86  jnz     short loc_180021A8F
0x180021a88  mov     ebx, 0C00002FEh
0x180021a8d  jmp     short loc_180021AD9
0x180021a8f  lea     rcx, [rbp+var_30]
0x180021a93  call    ??BKsecddLsaStateRef@@QEAAPEAU_KSECDDLSASTATE@@XZ; KsecddLsaStateRef::operator _KSECDDLSASTATE *(void)
0x180021a98  cmp     qword ptr [rax+1C8h], 0
0x180021aa0  jnz     short loc_180021AA9
0x180021aa2  mov     ebx, 0C0000001h
0x180021aa7  jmp     short loc_180021AD9
0x180021aa9  test    rbx, rbx
0x180021aac  jz      loc_180021B46
0x180021ab2  test    rdi, rdi
0x180021ab5  jz      loc_180021B46
0x180021abb  lea     r9, [rbp+var_10]
0x180021abf  mov     edx, 1
0x180021ac4  lea     r8, [rbp+var_28]
0x180021ac8  mov     rcx, rsi; String1
0x180021acb  call    KSecLocatePackageEx
0x180021ad0  test    eax, eax
0x180021ad2  jns     short loc_180021AE6
0x180021ad4  mov     ebx, 80090305h
0x180021ad9  lea     rcx, [rbp+var_30]; this
0x180021add  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180021ae2  mov     eax, ebx
0x180021ae4  jmp     short loc_180021B54
0x180021ae6  lea     rcx, [rbp+var_20]; this
0x180021aea  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180021aef  lea     rcx, [rbp+var_20]; this
0x180021af3  call    ?IsValid@KsecddLsaStateRef@@QEAA_NXZ; KsecddLsaStateRef::IsValid(void)
0x180021af8  test    al, al
0x180021afa  jnz     short loc_180021B03
0x180021afc  mov     ebx, 0C00002FEh
0x180021b01  jmp     short loc_180021B28
0x180021b03  mov     rax, [rbp+var_28]
0x180021b07  mov     rax, [rax+60h]
0x180021b0b  test    rax, rax
0x180021b0e  jnz     short loc_180021B17
0x180021b10  mov     ebx, 80090302h
0x180021b15  jmp     short loc_180021B28
0x180021b17  lea     r8, [rbp+var_18]
0x180021b1b  mov     rdx, r14
0x180021b1e  mov     rcx, rbx
0x180021b21  call    _guard_dispatch_icall
0x180021b26  mov     ebx, eax
0x180021b28  lea     rcx, [rbp+var_20]; this
0x180021b2c  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180021b31  test    ebx, ebx
0x180021b33  js      short loc_180021AD9
0x180021b35  mov     rcx, [rbp+var_18]
0x180021b39  mov     [rdi+8], rcx
0x180021b3d  mov     rcx, [rbp+var_10]
0x180021b41  mov     [rdi], rcx
0x180021b44  jmp     short loc_180021AD9
0x180021b46  lea     rcx, [rbp+var_30]; this
0x180021b4a  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180021b4f  mov     eax, 0C000000Dh
0x180021b54  add     rsp, 50h
0x180021b58  pop     r14
0x180021b5a  pop     rdi
0x180021b5b  pop     rsi
0x180021b5c  pop     rbx
0x180021b5d  pop     rbp
0x180021b5e  retn
```
