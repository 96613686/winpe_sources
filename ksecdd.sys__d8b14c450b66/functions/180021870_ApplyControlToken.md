# ApplyControlToken

- ea: `0x180021870`
- end: `0x1800218d5`
- name: `ApplyControlToken`
- size: `101`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, PSecBufferDesc pInput)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800017c4`
- `0x18000ad04`
- `0x180010840`
- `0x180021870`

## pseudocode

```c
SECURITY_STATUS __stdcall ApplyControlToken(PCtxtHandle phContext, PSecBufferDesc pInput)
{
  SECURITY_STATUS result; // eax
  _QWORD v4[2]; // [rsp+20h] [rbp-28h] BYREF

  v4[0] = 0;
  v4[1] = 0;
  if ( !phContext )
    return -2146893055;
  result = MapKernelContextHandle(phContext, v4);
  if ( result >= 0 )
    return (unsigned int)SspipApplyControlToken(v4, (__int64)pInput).Pointer;
  return result;
}

```

## disassembly

```asm
0x180021870  push    rbx
0x180021872  sub     rsp, 40h
0x180021876  mov     rax, cs:__security_cookie
0x18002187d  xor     rax, rsp
0x180021880  mov     [rsp+48h+var_18], rax
0x180021885  mov     [rsp+48h+var_28], 0
0x18002188e  mov     rbx, rdx
0x180021891  mov     [rsp+48h+var_20], 0
0x18002189a  test    rcx, rcx
0x18002189d  jnz     short loc_1800218A6
0x18002189f  mov     eax, 80090301h
0x1800218a4  jmp     short loc_1800218C1
0x1800218a6  lea     rdx, [rsp+48h+var_28]
0x1800218ab  call    MapKernelContextHandle
0x1800218b0  test    eax, eax
0x1800218b2  js      short loc_1800218C1
0x1800218b4  mov     rdx, rbx
0x1800218b7  lea     rcx, [rsp+48h+var_28]
0x1800218bc  call    SspipApplyControlToken
0x1800218c1  mov     rcx, [rsp+48h+var_18]
0x1800218c6  xor     rcx, rsp; StackCookie
0x1800218c9  call    __security_check_cookie
0x1800218ce  add     rsp, 40h
0x1800218d2  pop     rbx
0x1800218d3  retn
```
