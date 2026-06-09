# SspiAcceptSecurityContextAsync

- ea: `0x180024130`
- end: `0x180024322`
- name: `SspiAcceptSecurityContextAsync`
- size: `498`
- prototype: `SECURITY_STATUS __stdcall(SspiAsyncContext *AsyncContext, PCredHandle phCredential, PCtxtHandle phContext, PSecBufferDesc pInput, unsigned int fContextReq, unsigned int TargetDataRep, PCtxtHandle phNewContext, PSecBufferDesc pOutput, unsigned int *pfContextAttr, PTimeStamp ptsExpiry)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800017c4`
- `0x1800108a0`
- `0x180024130`
- `0x180024330`

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
    result = MapKernelContextHandle(phContext, &v18, phContext, pInput);
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
0x180024130  push    rbx
0x180024132  push    rbp
0x180024133  push    rsi
0x180024134  push    rdi
0x180024135  push    r12
0x180024137  push    r14
0x180024139  push    r15
0x18002413b  sub     rsp, 90h
0x180024142  mov     rax, cs:__security_cookie
0x180024149  xor     rax, rsp
0x18002414c  mov     [rsp+0C8h+var_78], rax
0x180024151  mov     r14, [rsp+0C8h+phNewContext]
0x180024159  mov     r12, r9
0x18002415c  mov     r15, [rsp+0C8h+pOutput]
0x180024164  mov     rbp, rdx
0x180024167  mov     rsi, [rsp+0C8h+pfContextAttr]
0x18002416f  mov     rbx, rcx
0x180024172  mov     rdi, [rsp+0C8h+ptsExpiry]
0x18002417a  test    rcx, rcx
0x18002417d  jz      loc_1800242FB
0x180024183  cmp     dword ptr [rcx+14h], 90368h
0x18002418a  jz      loc_1800242FB
0x180024190  mov     [rsp+0C8h+var_40], r13
0x180024198  xor     r13d, r13d
0x18002419b  mov     [rsi], r13d
0x18002419e  test    rdi, rdi
0x1800241a1  jnz     loc_180024309
0x1800241a7  mov     qword ptr [rsp+0C8h+var_A8], r13
0x1800241ac  mov     qword ptr [rsp+0C8h+var_A8+8], r13
0x1800241b1  mov     qword ptr [rsp+0C8h+var_88], r13
0x1800241b6  mov     qword ptr [rsp+0C8h+var_88+8], r13
0x1800241bb  mov     qword ptr [rsp+0C8h+var_98], r13
0x1800241c0  mov     qword ptr [rsp+0C8h+var_98+8], r13
0x1800241c5  test    r8, r8
0x1800241c8  jz      loc_1800242E1
0x1800241ce  test    r14, r14
0x1800241d1  jz      loc_1800242EA
0x1800241d7  movaps  [rsp+0C8h+var_68], xmm7
0x1800241dc  test    rbp, rbp
0x1800241df  jz      short loc_1800241E9
0x1800241e1  movups  xmm0, xmmword ptr [rdx]
0x1800241e4  movups  [rsp+0C8h+var_98], xmm0
0x1800241e9  movaps  [rsp+0C8h+var_58], xmm6
0x1800241ee  movups  xmm7, xmmword ptr [r14]
0x1800241f2  test    r8, r8
0x1800241f5  jz      loc_1800242F1
0x1800241fb  movups  xmm6, xmmword ptr [r8]
0x1800241ff  lea     rdx, [rsp+0C8h+var_88]
0x180024204  mov     rcx, r8
0x180024207  call    MapKernelContextHandle
0x18002420c  test    eax, eax
0x18002420e  js      loc_1800242AF
0x180024214  test    rbp, rbp
0x180024217  jz      loc_180024313
0x18002421d  cmp     dword ptr [r15+4], 12h
0x180024222  ja      loc_180024302
0x180024228  movups  xmm1, [rsp+0C8h+var_88]
0x18002422d  mov     dword ptr [rbx+14h], 90368h
0x180024234  lea     rax, ProcessSecurityContextMarshalParams
0x18002423b  movups  xmm0, [rsp+0C8h+var_98]
0x180024240  mov     [rbx+0E0h], rax
0x180024247  mov     edx, 2
0x18002424c  lea     rax, ProcessSecurityContextUnMarshalResponse
0x180024253  mov     [rbx+20h], rbx
0x180024257  mov     [rbx+0E8h], rax
0x18002425e  mov     rcx, rbx
0x180024261  mov     eax, [rsp+0C8h+fContextReq]
0x180024268  mov     [rbx+58h], eax
0x18002426b  mov     eax, [rsp+0C8h+TargetDataRep]
0x180024272  mov     [rbx+5Ch], eax
0x180024275  movups  xmmword ptr [rbx+28h], xmm0
0x180024279  mov     [rbx+48h], r13
0x18002427d  movups  xmmword ptr [rbx+38h], xmm1
0x180024281  mov     [rbx+50h], r12
0x180024285  mov     [rbx+60h], r14
0x180024289  mov     [rbx+68h], r15
0x18002428d  mov     [rbx+70h], rsi
0x180024291  mov     [rbx+78h], rdi
0x180024295  movups  xmmword ptr [rbx+80h], xmm1
0x18002429c  movups  xmmword ptr [rbx+90h], xmm6
0x1800242a3  movups  xmmword ptr [rbx+0A0h], xmm7
0x1800242aa  call    CallAsyncFunction
0x1800242af  movaps  xmm6, [rsp+0C8h+var_58]
0x1800242b4  movaps  xmm7, [rsp+0C8h+var_68]
0x1800242b9  mov     r13, [rsp+0C8h+var_40]
0x1800242c1  mov     rcx, [rsp+0C8h+var_78]
0x1800242c6  xor     rcx, rsp; StackCookie
0x1800242c9  call    __security_check_cookie
0x1800242ce  add     rsp, 90h
0x1800242d5  pop     r15
0x1800242d7  pop     r14
0x1800242d9  pop     r12
0x1800242db  pop     rdi
0x1800242dc  pop     rsi
0x1800242dd  pop     rbp
0x1800242de  pop     rbx
0x1800242df  retn
0x1800242e1  test    rbp, rbp
0x1800242e4  jnz     loc_1800241CE
0x1800242ea  mov     eax, 80090301h
0x1800242ef  jmp     short loc_1800242B9
0x1800242f1  movups  xmm6, [rsp+0C8h+var_A8]
0x1800242f6  jmp     loc_18002421D
0x1800242fb  mov     eax, 8009035Dh
0x180024300  jmp     short loc_1800242C1
0x180024302  mov     eax, 8009035Dh
0x180024307  jmp     short loc_1800242AF
0x180024309  xor     eax, eax
0x18002430b  mov     [rdi], rax
0x18002430e  jmp     loc_1800241A7
0x180024313  mov     rax, qword ptr [rsp+0C8h+var_88]
0x180024318  mov     qword ptr [rsp+0C8h+var_98], rax
0x18002431d  jmp     loc_18002421D
```
