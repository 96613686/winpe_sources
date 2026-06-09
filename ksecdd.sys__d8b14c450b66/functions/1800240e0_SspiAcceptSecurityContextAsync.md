# SspiAcceptSecurityContextAsync

- ea: `0x1800240e0`
- end: `0x1800242d2`
- name: `SspiAcceptSecurityContextAsync`
- size: `498`
- prototype: `SECURITY_STATUS __stdcall(SspiAsyncContext *AsyncContext, PCredHandle phCredential, PCtxtHandle phContext, PSecBufferDesc pInput, unsigned int fContextReq, unsigned int TargetDataRep, PCtxtHandle phNewContext, PSecBufferDesc pOutput, unsigned int *pfContextAttr, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800017c4`
- `0x180010840`
- `0x1800240e0`
- `0x1800242e0`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiAcceptSecurityContextAsync(
        SspiAsyncContext *AsyncContext,
        PCredHandle phCredential,
        PCtxtHandle phContext,
        PSecBufferDesc pInput,
        unsigned int fContextReq,
        unsigned int TargetDataRep,
        PCtxtHandle phNewContext,
        PSecBufferDesc pOutput,
        unsigned int *pfContextAttr,
        PTimeStamp ptsExpiry)
{
  struct _SecHandle v13; // xmm7
  struct _SecHandle v14; // xmm6
  SECURITY_STATUS result; // eax
  __int128 v16; // xmm1
  struct _SecHandle v17; // [rsp+30h] [rbp-98h]
  __int128 v18; // [rsp+40h] [rbp-88h] BYREF

  if ( !AsyncContext || *((_DWORD *)AsyncContext + 5) == 590696 )
    return -2146892963;
  *pfContextAttr = 0;
  if ( ptsExpiry )
    ptsExpiry->QuadPart = 0;
  v18 = 0u;
  v17 = (struct _SecHandle)0LL;
  if ( !phContext && !phCredential || !phNewContext )
    return -2146893055;
  if ( phCredential )
    v17 = *phCredential;
  v13 = *phNewContext;
  if ( phContext )
  {
    v14 = *phContext;
    result = MapKernelContextHandle(phContext, &v18);
    if ( result < 0 )
      return result;
    if ( !phCredential )
      v17.dwLower = v18;
  }
  else
  {
    v14 = (struct _SecHandle)0LL;
  }
  if ( pOutput->cBuffers > 0x12 )
    return -2146892963;
  v16 = v18;
  *((_DWORD *)AsyncContext + 5) = 590696;
  *((_QWORD *)AsyncContext + 28) = ProcessSecurityContextMarshalParams;
  *((_QWORD *)AsyncContext + 4) = AsyncContext;
  *((_QWORD *)AsyncContext + 29) = ProcessSecurityContextUnMarshalResponse;
  *((_DWORD *)AsyncContext + 22) = fContextReq;
  *((_DWORD *)AsyncContext + 23) = TargetDataRep;
  *(struct _SecHandle *)((char *)AsyncContext + 40) = v17;
  *((_QWORD *)AsyncContext + 9) = 0;
  *(_OWORD *)((char *)AsyncContext + 56) = v16;
  *((_QWORD *)AsyncContext + 10) = pInput;
  *((_QWORD *)AsyncContext + 12) = phNewContext;
  *((_QWORD *)AsyncContext + 13) = pOutput;
  *((_QWORD *)AsyncContext + 14) = pfContextAttr;
  *((_QWORD *)AsyncContext + 15) = ptsExpiry;
  *((_OWORD *)AsyncContext + 8) = v16;
  *((struct _SecHandle *)AsyncContext + 9) = v14;
  *((struct _SecHandle *)AsyncContext + 10) = v13;
  return CallAsyncFunction((__int64)AsyncContext, 2);
}

```

## disassembly

```asm
0x1800240e0  push    rbx
0x1800240e2  push    rbp
0x1800240e3  push    rsi
0x1800240e4  push    rdi
0x1800240e5  push    r12
0x1800240e7  push    r14
0x1800240e9  push    r15
0x1800240eb  sub     rsp, 90h
0x1800240f2  mov     rax, cs:__security_cookie
0x1800240f9  xor     rax, rsp
0x1800240fc  mov     [rsp+0C8h+var_78], rax
0x180024101  mov     r14, [rsp+0C8h+phNewContext]
0x180024109  mov     r12, r9
0x18002410c  mov     r15, [rsp+0C8h+pOutput]
0x180024114  mov     rbp, rdx
0x180024117  mov     rsi, [rsp+0C8h+pfContextAttr]
0x18002411f  mov     rbx, rcx
0x180024122  mov     rdi, [rsp+0C8h+ptsExpiry]
0x18002412a  test    rcx, rcx
0x18002412d  jz      loc_1800242AB
0x180024133  cmp     dword ptr [rcx+14h], 90368h
0x18002413a  jz      loc_1800242AB
0x180024140  mov     [rsp+0C8h+var_40], r13
0x180024148  xor     r13d, r13d
0x18002414b  mov     [rsi], r13d
0x18002414e  test    rdi, rdi
0x180024151  jnz     loc_1800242B9
0x180024157  mov     qword ptr [rsp+0C8h+var_A8], r13
0x18002415c  mov     qword ptr [rsp+0C8h+var_A8+8], r13
0x180024161  mov     qword ptr [rsp+0C8h+var_88], r13
0x180024166  mov     qword ptr [rsp+0C8h+var_88+8], r13
0x18002416b  mov     qword ptr [rsp+0C8h+var_98], r13
0x180024170  mov     qword ptr [rsp+0C8h+var_98+8], r13
0x180024175  test    r8, r8
0x180024178  jz      loc_180024291
0x18002417e  test    r14, r14
0x180024181  jz      loc_18002429A
0x180024187  movaps  [rsp+0C8h+var_68], xmm7
0x18002418c  test    rbp, rbp
0x18002418f  jz      short loc_180024199
0x180024191  movups  xmm0, xmmword ptr [rdx]
0x180024194  movups  [rsp+0C8h+var_98], xmm0
0x180024199  movaps  [rsp+0C8h+var_58], xmm6
0x18002419e  movups  xmm7, xmmword ptr [r14]
0x1800241a2  test    r8, r8
0x1800241a5  jz      loc_1800242A1
0x1800241ab  movups  xmm6, xmmword ptr [r8]
0x1800241af  lea     rdx, [rsp+0C8h+var_88]
0x1800241b4  mov     rcx, r8
0x1800241b7  call    MapKernelContextHandle
0x1800241bc  test    eax, eax
0x1800241be  js      loc_18002425F
0x1800241c4  test    rbp, rbp
0x1800241c7  jz      loc_1800242C3
0x1800241cd  cmp     dword ptr [r15+4], 12h
0x1800241d2  ja      loc_1800242B2
0x1800241d8  movups  xmm1, [rsp+0C8h+var_88]
0x1800241dd  mov     dword ptr [rbx+14h], 90368h
0x1800241e4  lea     rax, ProcessSecurityContextMarshalParams
0x1800241eb  movups  xmm0, [rsp+0C8h+var_98]
0x1800241f0  mov     [rbx+0E0h], rax
0x1800241f7  mov     edx, 2
0x1800241fc  lea     rax, ProcessSecurityContextUnMarshalResponse
0x180024203  mov     [rbx+20h], rbx
0x180024207  mov     [rbx+0E8h], rax
0x18002420e  mov     rcx, rbx
0x180024211  mov     eax, [rsp+0C8h+fContextReq]
0x180024218  mov     [rbx+58h], eax
0x18002421b  mov     eax, [rsp+0C8h+TargetDataRep]
0x180024222  mov     [rbx+5Ch], eax
0x180024225  movups  xmmword ptr [rbx+28h], xmm0
0x180024229  mov     [rbx+48h], r13
0x18002422d  movups  xmmword ptr [rbx+38h], xmm1
0x180024231  mov     [rbx+50h], r12
0x180024235  mov     [rbx+60h], r14
0x180024239  mov     [rbx+68h], r15
0x18002423d  mov     [rbx+70h], rsi
0x180024241  mov     [rbx+78h], rdi
0x180024245  movups  xmmword ptr [rbx+80h], xmm1
0x18002424c  movups  xmmword ptr [rbx+90h], xmm6
0x180024253  movups  xmmword ptr [rbx+0A0h], xmm7
0x18002425a  call    CallAsyncFunction
0x18002425f  movaps  xmm6, [rsp+0C8h+var_58]
0x180024264  movaps  xmm7, [rsp+0C8h+var_68]
0x180024269  mov     r13, [rsp+0C8h+var_40]
0x180024271  mov     rcx, [rsp+0C8h+var_78]
0x180024276  xor     rcx, rsp; StackCookie
0x180024279  call    __security_check_cookie
0x18002427e  add     rsp, 90h
0x180024285  pop     r15
0x180024287  pop     r14
0x180024289  pop     r12
0x18002428b  pop     rdi
0x18002428c  pop     rsi
0x18002428d  pop     rbp
0x18002428e  pop     rbx
0x18002428f  retn
0x180024291  test    rbp, rbp
0x180024294  jnz     loc_18002417E
0x18002429a  mov     eax, 80090301h
0x18002429f  jmp     short loc_180024269
0x1800242a1  movups  xmm6, [rsp+0C8h+var_A8]
0x1800242a6  jmp     loc_1800241CD
0x1800242ab  mov     eax, 8009035Dh
0x1800242b0  jmp     short loc_180024271
0x1800242b2  mov     eax, 8009035Dh
0x1800242b7  jmp     short loc_18002425F
0x1800242b9  xor     eax, eax
0x1800242bb  mov     [rdi], rax
0x1800242be  jmp     loc_180024157
0x1800242c3  mov     rax, qword ptr [rsp+0C8h+var_88]
0x1800242c8  mov     qword ptr [rsp+0C8h+var_98], rax
0x1800242cd  jmp     loc_1800241CD
```
