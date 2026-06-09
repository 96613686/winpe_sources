# PiDevCfgConfigureDeviceKeys

- ea: `0x1409b7ee8`
- end: `0x1409b80c6`
- name: `PiDevCfgConfigureDeviceKeys`
- size: `478`
- prototype: ``
- caller_count: `6`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140770808`
- `0x1409b85fc`
- `0x1409bb3bc`
- `0x1409bc518`
- `0x140a864bc`
- `0x140ad2658`

## callees

- `0x1404dc378`
- `0x1405e5528`
- `0x1406dd5c0`
- `0x1406dd620`
- `0x1409b733c`
- `0x1409b7bf4`
- `0x1409b7ee8`
- `0x1409b80cc`
- `0x1409b815c`
- `0x1409bc674`
- `0x140acff3c`
- `0x140bb19f0`

## string_xrefs

- `0x140b64cba`: `ConfigFlags`
- `0x140b64c75`: `ClassConfigured`

## pseudocode

```c
__int64 __fastcall PiDevCfgConfigureDeviceKeys(__int64 a1, __int64 a2, void *a3, int a4, _DWORD *a5, _DWORD *a6)
{
  int v9; // r12d
  int inited; // edi
  unsigned int *v12; // rcx
  unsigned int *v13; // rcx
  unsigned int *v14; // rcx
  __int64 v15; // [rsp+40h] [rbp-69h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp-61h] BYREF
  __int128 v17; // [rsp+50h] [rbp-59h] BYREF
  _OWORD v18[2]; // [rsp+60h] [rbp-49h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-29h] BYREF

  KeyHandle = 0;
  v15 = 0;
  v9 = a1;
  v17 = 0;
  memset(v18, 0, sizeof(v18));
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  inited = PiDevCfgInitResolveContext(a1, a3, (__int64)v18);
  if ( inited >= 0 )
  {
    inited = PiDevCfgEnumDeviceKeys(
               v9,
               a2,
               (_DWORD)a3,
               a4,
               1,
               (__int64)PiDevCfgConfigureDeviceKeyCallback,
               (__int64)v18);
    if ( inited >= 0 )
    {
      if ( (a4 & 8) == 0
        || (inited = PiDevCfgConfigureDeviceInterfaces(*(_QWORD *)(a2 + 8), a3, (__int64)v18), inited >= 0) )
      {
        if ( (a4 & 0x10) == 0 || (inited = PiDevCfgConfigureSoftwareDevices(*(_QWORD *)(a2 + 16), a3), inited >= 0) )
        {
          if ( (a4 & 0x200) == 0 || (inited = PiDevCfgConfigureDeviceFilters(*(_QWORD *)(a2 + 16), a3), inited >= 0) )
          {
            LODWORD(v17) = 917516;
            *((_QWORD *)&v17 + 1) = L"Status";
            *(_QWORD *)&ObjectAttributes.Length = 48;
            ObjectAttributes.ObjectName = (PUNICODE_STRING)&v17;
            *(_QWORD *)&ObjectAttributes.Attributes = 576;
            KeyHandle = 0;
            ObjectAttributes.RootDirectory = a3;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
            {
              if ( a6 )
              {
                if ( (int)PiDevCfgQueryResolveValue((__int64)v18, KeyHandle, L"Reboot", &v15) >= 0 )
                {
                  if ( (unsigned __int8)PnpValidateRegistryDword(v15) && *(unsigned int *)((char *)v12 + v12[2]) )
                    *a6 |= 0x40u;
                  ExFreePoolWithTag(v12, 0);
                }
                if ( (int)PiDevCfgQueryResolveValue((__int64)v18, KeyHandle, L"ClassConfigured", &v15) >= 0 )
                {
                  if ( (unsigned __int8)PnpValidateRegistryDword(v15) && *(unsigned int *)((char *)v13 + v13[2]) )
                    *a6 |= 2u;
                  ExFreePoolWithTag(v13, 0);
                }
              }
              if ( a5 && (int)PiDevCfgQueryResolveValue((__int64)v18, KeyHandle, L"ConfigFlags", &v15) >= 0 )
              {
                if ( (unsigned __int8)PnpValidateRegistryDword(v15) )
                  *a5 |= *(unsigned int *)((char *)v14 + v14[2]);
                ExFreePoolWithTag(v14, 0);
              }
            }
          }
        }
      }
    }
  }
  PiDevCfgFreeResolveContext(v18);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1409b7ee8  push    rbp
0x1409b7eea  push    rbx
0x1409b7eeb  push    rsi
0x1409b7eec  push    rdi
0x1409b7eed  push    r12
0x1409b7eef  push    r13
0x1409b7ef1  push    r14
0x1409b7ef3  push    r15
0x1409b7ef5  lea     rbp, [rsp-0Fh]
0x1409b7efa  sub     rsp, 0B8h
0x1409b7f01  mov     rsi, [rbp+47h+arg_20]
0x1409b7f05  xor     eax, eax
0x1409b7f07  mov     [rbp+47h+KeyHandle], rax
0x1409b7f0b  xorps   xmm1, xmm1
0x1409b7f0e  mov     [rbp+47h+var_B0], rax
0x1409b7f12  xorps   xmm0, xmm0
0x1409b7f15  mov     r15d, r9d
0x1409b7f18  mov     r14, r8
0x1409b7f1b  mov     r13, rdx
0x1409b7f1e  mov     r12, rcx
0x1409b7f21  movups  [rbp+47h+var_A0], xmm0
0x1409b7f25  movups  [rbp+47h+var_90], xmm1
0x1409b7f29  movups  [rbp+47h+var_80], xmm1
0x1409b7f2d  test    rsi, rsi
0x1409b7f30  jz      short loc_1409B7F34
0x1409b7f32  mov     [rsi], eax
0x1409b7f34  mov     rbx, [rbp+47h+arg_28]
0x1409b7f38  test    rbx, rbx
0x1409b7f3b  jz      short loc_1409B7F3F
0x1409b7f3d  mov     [rbx], eax
0x1409b7f3f  lea     r8, [rbp+47h+var_90]
0x1409b7f43  mov     rdx, r14
0x1409b7f46  call    PiDevCfgInitResolveContext
0x1409b7f4b  mov     edi, eax
0x1409b7f4d  test    eax, eax
0x1409b7f4f  js      short loc_1409B7F85
0x1409b7f51  lea     rax, [rbp+47h+var_90]
0x1409b7f55  mov     r9d, r15d
0x1409b7f58  mov     [rsp+0F0h+var_C0], rax
0x1409b7f5d  mov     r8, r14
0x1409b7f60  lea     rax, PiDevCfgConfigureDeviceKeyCallback
0x1409b7f67  mov     rdx, r13
0x1409b7f6a  mov     [rsp+0F0h+var_C8], rax
0x1409b7f6f  mov     rcx, r12
0x1409b7f72  mov     [rsp+0F0h+var_D0], 1
0x1409b7f77  call    PiDevCfgEnumDeviceKeys
0x1409b7f7c  xor     r12d, r12d
0x1409b7f7f  mov     edi, eax
0x1409b7f81  test    eax, eax
0x1409b7f83  jns     short loc_1409B7FB2
0x1409b7f85  lea     rcx, [rbp+47h+var_90]
0x1409b7f89  call    PiDevCfgFreeResolveContext
0x1409b7f8e  mov     rcx, [rbp+47h+KeyHandle]; Handle
0x1409b7f92  test    rcx, rcx
0x1409b7f95  jnz     loc_1409B80BC
0x1409b7f9b  mov     eax, edi
0x1409b7f9d  add     rsp, 0B8h
0x1409b7fa4  pop     r15
0x1409b7fa6  pop     r14
0x1409b7fa8  pop     r13
0x1409b7faa  pop     r12
0x1409b7fac  pop     rdi
0x1409b7fad  pop     rsi
0x1409b7fae  pop     rbx
0x1409b7faf  pop     rbp
0x1409b7fb0  retn
0x1409b7fb2  test    r15b, 8
0x1409b7fb6  jnz     loc_1409B8082
0x1409b7fbc  test    r15b, 10h
0x1409b7fc0  jz      short loc_1409B7FD4
0x1409b7fc2  mov     rcx, [r13+10h]
0x1409b7fc6  mov     rdx, r14
0x1409b7fc9  call    PiDevCfgConfigureSoftwareDevices
0x1409b7fce  mov     edi, eax
0x1409b7fd0  test    eax, eax
0x1409b7fd2  js      short loc_1409B7F85
0x1409b7fd4  bt      r15d, 9
0x1409b7fd9  jb      loc_1409B80A1
0x1409b7fdf  lea     rax, aStatus; "Status"
0x1409b7fe6  mov     dword ptr [rbp+47h+var_A0], 0E000Ch
0x1409b7fed  mov     qword ptr [rbp+47h+var_A0+8], rax
0x1409b7ff1  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x1409b7ff5  lea     rax, [rbp+47h+var_A0]
0x1409b7ff9  mov     qword ptr [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x1409b8001  xorps   xmm0, xmm0
0x1409b8004  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x1409b8008  mov     edx, 20019h; DesiredAccess
0x1409b800d  mov     qword ptr [rbp+47h+ObjectAttributes.Attributes], 240h
0x1409b8015  lea     rcx, [rbp+47h+KeyHandle]; KeyHandle
0x1409b8019  mov     [rbp+47h+KeyHandle], r12
0x1409b801d  mov     [rbp+47h+ObjectAttributes.RootDirectory], r14
0x1409b8021  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x1409b8026  call    ZwOpenKey
0x1409b802b  test    eax, eax
0x1409b802d  js      loc_1409B7F85
0x1409b8033  test    rbx, rbx
0x1409b8036  jz      loc_140B64CA9
0x1409b803c  mov     rdx, [rbp+47h+KeyHandle]
0x1409b8040  lea     r9, [rbp+47h+var_B0]
0x1409b8044  lea     r8, aReboot; "Reboot"
0x1409b804b  lea     rcx, [rbp+47h+var_90]
0x1409b804f  call    PiDevCfgQueryResolveValue
0x1409b8054  test    eax, eax
0x1409b8056  js      loc_140B64C6D
0x1409b805c  mov     rcx, [rbp+47h+var_B0]
0x1409b8060  call    PnpValidateRegistryDword
0x1409b8065  test    al, al
0x1409b8067  jz      loc_140B64C66
0x1409b806d  mov     eax, [rcx+8]
0x1409b8070  cmp     [rax+rcx], r12d
0x1409b8074  jz      loc_140B64C66
0x1409b807a  or      dword ptr [rbx], 40h
0x1409b807d  jmp     loc_140B64C66
0x1409b8082  mov     rcx, [r13+8]
0x1409b8086  lea     r8, [rbp+47h+var_90]
0x1409b808a  mov     rdx, r14
0x1409b808d  call    PiDevCfgConfigureDeviceInterfaces
0x1409b8092  mov     edi, eax
0x1409b8094  test    eax, eax
0x1409b8096  jns     loc_1409B7FBC
0x1409b809c  jmp     loc_1409B7F85
0x1409b80a1  mov     rcx, [r13+10h]
0x1409b80a5  mov     rdx, r14
0x1409b80a8  call    PiDevCfgConfigureDeviceFilters
0x1409b80ad  mov     edi, eax
0x1409b80af  test    eax, eax
0x1409b80b1  js      loc_1409B7F85
0x1409b80b7  jmp     loc_1409B7FDF
0x1409b80bc  call    ZwClose
0x1409b80c1  jmp     loc_1409B7F9B
0x140b64c66  xor     edx, edx; Tag
0x140b64c68  call    ExFreePoolWithTag
0x140b64c6d  mov     rdx, [rbp+47h+KeyHandle]
0x140b64c71  lea     r9, [rbp+47h+var_B0]
0x140b64c75  lea     r8, aClassconfigure; "ClassConfigured"
0x140b64c7c  lea     rcx, [rbp+47h+var_90]
0x140b64c80  call    PiDevCfgQueryResolveValue
0x140b64c85  test    eax, eax
0x140b64c87  js      short loc_140B64CA9
0x140b64c89  mov     rcx, [rbp+47h+var_B0]
0x140b64c8d  call    PnpValidateRegistryDword
0x140b64c92  test    al, al
0x140b64c94  jz      short loc_140B64CA2
0x140b64c96  mov     eax, [rcx+8]
0x140b64c99  cmp     [rax+rcx], r12d
0x140b64c9d  jz      short loc_140B64CA2
0x140b64c9f  or      dword ptr [rbx], 2
0x140b64ca2  xor     edx, edx; Tag
0x140b64ca4  call    ExFreePoolWithTag
0x140b64ca9  test    rsi, rsi
0x140b64cac  jz      loc_1409B7F85
0x140b64cb2  mov     rdx, [rbp+47h+KeyHandle]
0x140b64cb6  lea     r9, [rbp+47h+var_B0]
0x140b64cba  lea     r8, aConfigflags; "ConfigFlags"
0x140b64cc1  lea     rcx, [rbp+47h+var_90]
0x140b64cc5  call    PiDevCfgQueryResolveValue
0x140b64cca  test    eax, eax
0x140b64ccc  js      loc_1409B7F85
0x140b64cd2  mov     rcx, [rbp+47h+var_B0]
0x140b64cd6  call    PnpValidateRegistryDword
0x140b64cdb  test    al, al
0x140b64cdd  jz      short loc_140B64CE7
0x140b64cdf  mov     eax, [rcx+8]
0x140b64ce2  mov     edx, [rax+rcx]
0x140b64ce5  or      [rsi], edx
0x140b64ce7  xor     edx, edx; Tag
0x140b64ce9  call    ExFreePoolWithTag
0x140b64cee  nop
0x140b64cef  jmp     loc_1409B7F85
```
