# ApplyControlToken

- ea: `0x1800218c0`
- end: `0x180021925`
- name: `ApplyControlToken`
- size: `101`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, PSecBufferDesc pInput)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800017c4`
- `0x18000ad04`
- `0x1800108a0`
- `0x1800218c0`

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
0x1800218c0  push    rbx
0x1800218c2  sub     rsp, 40h
0x1800218c6  mov     rax, cs:__security_cookie
0x1800218cd  xor     rax, rsp
0x1800218d0  mov     [rsp+48h+var_18], rax
0x1800218d5  mov     [rsp+48h+var_28], 0
0x1800218de  mov     rbx, rdx
0x1800218e1  mov     [rsp+48h+var_20], 0
0x1800218ea  test    rcx, rcx
0x1800218ed  jnz     short loc_1800218F6
0x1800218ef  mov     eax, 80090301h
0x1800218f4  jmp     short loc_180021911
0x1800218f6  lea     rdx, [rsp+48h+var_28]
0x1800218fb  call    MapKernelContextHandle
0x180021900  test    eax, eax
0x180021902  js      short loc_180021911
0x180021904  mov     rdx, rbx
0x180021907  lea     rcx, [rsp+48h+var_28]
0x18002190c  call    SspipApplyControlToken
0x180021911  mov     rcx, [rsp+48h+var_18]
0x180021916  xor     rcx, rsp; StackCookie
0x180021919  call    __security_check_cookie
0x18002191e  add     rsp, 40h
0x180021922  pop     rbx
0x180021923  retn
```
