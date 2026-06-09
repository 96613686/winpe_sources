# sub_140C67BAC

- ea: `0x140c67bac`
- end: `0x140c67f31`
- name: `sub_140C67BAC`
- size: `901`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update`

## callers

- `0x140c616dc`

## callees

- `0x1405de5e8`
- `0x1406d9d70`
- `0x1406daa70`
- `0x1406f4880`
- `0x140730784`
- `0x14076b240`
- `0x14077540c`
- `0x14077635c`
- `0x1408bae00`
- `0x1408c77b0`
- `0x14095e740`
- `0x140974ae8`
- `0x140a81728`
- `0x140a8baa0`
- `0x140aa3338`
- `0x140c67bac`

## string_xrefs

- `0x140c67d6a`: `DeviceInstallMode`
- `0x140c67db1`: `DriverUpdatesPending`
- `0x140c67ccd`: `DeviceInstall`

## pseudocode

```c
__int64 sub_140C67BAC()
{
  char v0; // r14
  int v1; // ecx
  int v2; // esi
  __int64 v3; // rdx
  __int64 v4; // rcx
  int v5; // edi
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rcx
  int v14; // [rsp+20h] [rbp-E0h]
  int v15; // [rsp+28h] [rbp-D8h]
  char v16; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v17[3]; // [rsp+61h] [rbp-9Fh] BYREF
  int v18; // [rsp+64h] [rbp-9Ch] BYREF
  int v19; // [rsp+68h] [rbp-98h] BYREF
  int v20; // [rsp+6Ch] [rbp-94h] BYREF
  int v21; // [rsp+70h] [rbp-90h] BYREF
  int v22; // [rsp+74h] [rbp-8Ch] BYREF
  int v23; // [rsp+78h] [rbp-88h] BYREF
  HANDLE Handle; // [rsp+80h] [rbp-80h] BYREF
  HANDLE v25; // [rsp+88h] [rbp-78h] BYREF
  __int128 v26; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v27; // [rsp+A0h] [rbp-60h] BYREF
  int v28; // [rsp+A8h] [rbp-58h]
  int *v29; // [rsp+B0h] [rbp-50h]
  int v30; // [rsp+B8h] [rbp-48h]
  int v31; // [rsp+C0h] [rbp-40h]
  __int64 *v32; // [rsp+C8h] [rbp-38h]
  int v33; // [rsp+D0h] [rbp-30h]
  int *v34; // [rsp+D8h] [rbp-28h]
  int v35; // [rsp+E0h] [rbp-20h]
  int v36; // [rsp+E8h] [rbp-18h]
  __int64 *v37; // [rsp+F0h] [rbp-10h]
  int v38; // [rsp+F8h] [rbp-8h]
  char *v39; // [rsp+100h] [rbp+0h]
  int v40; // [rsp+108h] [rbp+8h]
  int v41; // [rsp+110h] [rbp+10h]

  v19 = 0;
  v21 = 0;
  v16 = 0;
  v0 = 0;
  v17[0] = 0;
  v26 = 0;
  v25 = 0;
  Handle = 0;
  v20 = 0;
  memset_0(&v27, 0, 0x78u);
  v28 = 7;
  v27 = qword_140028960;
  v30 = 4;
  v29 = &v19;
  v32 = qword_1400290F8;
  v33 = 7;
  v34 = &v21;
  v35 = 4;
  v39 = &v16;
  v37 = qword_140028AC0;
  v38 = 17;
  v40 = 1;
  v2 = sub_140A81728(v1, (unsigned int)L"SYSTEM", 7, 0, (__int64)&v27, 3);
  if ( v2 >= 0 )
  {
    if ( v31 >= 0 )
    {
      if ( (v19 & 3) == 0 )
        v19 = 0;
    }
    else
    {
      v19 = 3;
    }
    if ( v36 < 0 )
      v21 = 0;
    if ( v41 < 0 )
      v16 = 0;
    LODWORD(v26) = 1835034;
    *((_QWORD *)&v26 + 1) = L"DeviceInstall";
    LOBYTE(v14) = 0;
    if ( (int)sub_140974AE8(&v26, 131097, &v25, 0, v14) >= 0 )
    {
      v5 = 1;
      v6 = 0;
      v22 = 1;
      v23 = 0;
      if ( (int)sub_1408BAE00(*(__int64 *)&qword_140E4C568, (char *)v25, L"Parameters", 0, 0x20019u, &Handle) >= 0 )
      {
        if ( (unsigned __int8)RtlIsStateSeparationEnabled(v8, v7) )
        {
          v18 = 4;
          if ( (int)sub_14095E740(v9, Handle, L"DeviceInstallMode", &v20, &v22, &v18) < 0
            || v20 != 4
            || (v5 = v22, v18 != 4) )
          {
            v5 = 0;
          }
        }
        v18 = 4;
        if ( (int)sub_14095E740(v9, Handle, L"DriverUpdatesPending", &v20, &v23, &v18) >= 0 && v20 == 4 && v18 == 4 )
          v6 = v23;
        ZwClose(Handle);
      }
      ZwClose(v25);
      if ( v5 )
      {
        dword_140FDA02C |= 2u;
        if ( v6 )
          sub_140730784();
      }
    }
    *(_DWORD *)((char *)&NlsMbCodePageTag + 7) = v19;
    dword_140FDA0AC = v21;
    if ( (dword_140FBC980 & 0x10) != 0 )
      v10 = dword_140FBC980 & 1;
    else
      v10 = sub_1405DE5E8();
    if ( v10 )
    {
      LOBYTE(v4) = 1;
      sub_14076B240(v4, &xmmword_140FDA2B0);
    }
    if ( *(_DWORD *)((char *)&NlsMbCodePageTag + 7) )
    {
      if ( (dword_140FDA0AC & 0x20) != 0 || (dword_140FDA02C & 2) == 0 )
      {
        v11 = sub_14077635C(0, v17);
        v0 = v17[0];
        if ( v11 >= 0 )
        {
          if ( v17[0] )
            dword_140FDA02C |= 1u;
        }
      }
      if ( v16 == -1 )
        dword_140FDA02C |= 1u;
    }
    if ( (dword_140FDA02C & 1) != 0 )
    {
      if ( !(unsigned __int8)RtlIsStateSeparationEnabled(v4, v3) || (v2 = sub_14077540C(), v2 >= 0) )
      {
        v2 = sub_1408C77B0(1, sub_140769D50);
        if ( v2 >= 0 )
        {
          if ( v16 == -1 )
            sub_140AA3338(qword_140E4C568, 0, (unsigned int)L"SYSTEM", 7, 0, v15, (__int64)qword_140028AC0, 0, 0, 0, 0);
          if ( v0 )
          {
            LOBYTE(v12) = 1;
            sub_14077635C(v12, 0);
          }
        }
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140c67bac  push    rbp
0x140c67bae  push    rbx
0x140c67baf  push    rsi
0x140c67bb0  push    rdi
0x140c67bb1  push    r13
0x140c67bb3  push    r14
0x140c67bb5  push    r15
0x140c67bb7  lea     rbp, [rsp-30h]
0x140c67bbc  sub     rsp, 130h
0x140c67bc3  mov     rax, cs:__security_cookie
0x140c67bca  xor     rax, rsp
0x140c67bcd  mov     [rbp+60h+var_40], rax
0x140c67bd1  xor     r15d, r15d
0x140c67bd4  lea     rcx, [rbp+60h+var_C0]; void *
0x140c67bd8  xorps   xmm0, xmm0
0x140c67bdb  mov     [rsp+160h+var_F8], r15d
0x140c67be0  xor     edx, edx; Val
0x140c67be2  mov     [rsp+160h+var_F0], r15d
0x140c67be7  mov     [rsp+160h+var_100], r15b
0x140c67bec  mov     r14b, r15b
0x140c67bef  lea     r8d, [r15+78h]; Size
0x140c67bf3  mov     [rsp+160h+var_FF], r15b
0x140c67bf8  movups  [rbp+60h+var_D0], xmm0
0x140c67bfc  mov     [rbp+60h+var_D8], r15
0x140c67c00  mov     [rbp+60h+Handle], r15
0x140c67c04  mov     [rsp+160h+var_F4], r15d
0x140c67c09  call    memset_0
0x140c67c0e  lea     rax, qword_140028960
0x140c67c15  mov     [rbp+60h+var_B8], 7
0x140c67c1c  mov     [rbp+60h+var_C0], rax
0x140c67c20  lea     r13d, [r15+4]
0x140c67c24  lea     rax, [rsp+160h+var_F8]
0x140c67c29  mov     [rbp+60h+var_A8], r13d
0x140c67c2d  mov     [rbp+60h+var_B0], rax
0x140c67c31  lea     ebx, [r15+3]
0x140c67c35  lea     rax, qword_1400290F8
0x140c67c3c  mov     dword ptr [rsp+160h+var_138], ebx
0x140c67c40  mov     [rbp+60h+var_98], rax
0x140c67c44  lea     rdi, qword_140028AC0
0x140c67c4b  lea     rax, [rsp+160h+var_F0]
0x140c67c50  mov     [rbp+60h+var_90], 7
0x140c67c57  mov     [rbp+60h+var_88], rax
0x140c67c5b  lea     r8d, [r15+7]
0x140c67c5f  lea     rax, [rsp+160h+var_100]
0x140c67c64  mov     [rbp+60h+var_80], r13d
0x140c67c68  mov     [rbp+60h+var_60], rax
0x140c67c6c  lea     rdx, aSystem_3; "SYSTEM"
0x140c67c73  lea     rax, [rbp+60h+var_C0]
0x140c67c77  mov     [rbp+60h+var_70], rdi
0x140c67c7b  xor     r9d, r9d
0x140c67c7e  mov     [rsp+160h+var_140], rax
0x140c67c83  mov     [rbp+60h+var_68], 11h
0x140c67c8a  mov     [rbp+60h+var_58], 1
0x140c67c91  call    sub_140A81728
0x140c67c96  mov     esi, eax
0x140c67c98  test    eax, eax
0x140c67c9a  js      loc_140C67F10
0x140c67ca0  cmp     [rbp+60h+var_A0], r15d
0x140c67ca4  jge     short loc_140C67CAC
0x140c67ca6  mov     [rsp+160h+var_F8], ebx
0x140c67caa  jmp     short loc_140C67CB7
0x140c67cac  test    byte ptr [rsp+160h+var_F8], bl
0x140c67cb0  jnz     short loc_140C67CB7
0x140c67cb2  mov     [rsp+160h+var_F8], r15d
0x140c67cb7  cmp     [rbp+60h+var_78], r15d
0x140c67cbb  jge     short loc_140C67CC2
0x140c67cbd  mov     [rsp+160h+var_F0], r15d
0x140c67cc2  cmp     [rbp+60h+var_50], r15d
0x140c67cc6  jge     short loc_140C67CCD
0x140c67cc8  mov     [rsp+160h+var_100], r15b
0x140c67ccd  lea     rax, aDeviceinstall; "DeviceInstall"
0x140c67cd4  mov     dword ptr [rbp+60h+var_D0], 1C001Ah
0x140c67cdb  xor     r9d, r9d
0x140c67cde  mov     qword ptr [rbp+60h+var_D0+8], rax
0x140c67ce2  lea     r8, [rbp+60h+var_D8]
0x140c67ce6  mov     byte ptr [rsp+160h+var_140], r15b
0x140c67ceb  mov     edx, 20019h
0x140c67cf0  lea     rcx, [rbp+60h+var_D0]
0x140c67cf4  call    sub_140974AE8
0x140c67cf9  test    eax, eax
0x140c67cfb  js      loc_140C67E05
0x140c67d01  mov     rdx, [rbp+60h+var_D8]
0x140c67d05  lea     rax, [rbp+60h+Handle]
0x140c67d09  mov     rcx, cs:qword_140E4C568
0x140c67d10  lea     r8, aParameters_0; "Parameters"
0x140c67d17  mov     [rsp+160h+var_138], rax
0x140c67d1c  mov     edi, 1
0x140c67d21  mov     ebx, r15d
0x140c67d24  mov     dword ptr [rsp+160h+var_140], 20019h
0x140c67d2c  xor     r9d, r9d
0x140c67d2f  mov     [rsp+160h+var_EC], edi
0x140c67d33  mov     [rsp+160h+var_E8], ebx
0x140c67d37  call    sub_1408BAE00
0x140c67d3c  test    eax, eax
0x140c67d3e  js      loc_140C67DE1
0x140c67d44  call    RtlIsStateSeparationEnabled
0x140c67d49  test    al, al
0x140c67d4b  jz      short loc_140C67D94
0x140c67d4d  mov     rdx, [rbp+60h+Handle]
0x140c67d51  lea     rax, [rsp+160h+var_FC]
0x140c67d56  mov     [rsp+160h+var_138], rax
0x140c67d5b  lea     r9, [rsp+160h+var_F4]
0x140c67d60  lea     rax, [rsp+160h+var_EC]
0x140c67d65  mov     [rsp+160h+var_FC], r13d
0x140c67d6a  lea     r8, aDeviceinstallm; "DeviceInstallMode"
0x140c67d71  mov     [rsp+160h+var_140], rax
0x140c67d76  call    sub_14095E740
0x140c67d7b  test    eax, eax
0x140c67d7d  js      short loc_140C67D91
0x140c67d7f  cmp     [rsp+160h+var_F4], r13d
0x140c67d84  jnz     short loc_140C67D91
0x140c67d86  mov     edi, [rsp+160h+var_EC]
0x140c67d8a  cmp     [rsp+160h+var_FC], r13d
0x140c67d8f  jz      short loc_140C67D94
0x140c67d91  mov     edi, r15d
0x140c67d94  mov     rdx, [rbp+60h+Handle]
0x140c67d98  lea     rax, [rsp+160h+var_FC]
0x140c67d9d  mov     [rsp+160h+var_138], rax
0x140c67da2  lea     r9, [rsp+160h+var_F4]
0x140c67da7  lea     rax, [rsp+160h+var_E8]
0x140c67dac  mov     [rsp+160h+var_FC], r13d
0x140c67db1  lea     r8, aDriverupdatesp; "DriverUpdatesPending"
0x140c67db8  mov     [rsp+160h+var_140], rax
0x140c67dbd  call    sub_14095E740
0x140c67dc2  test    eax, eax
0x140c67dc4  js      short loc_140C67DD8
0x140c67dc6  cmp     [rsp+160h+var_F4], r13d
0x140c67dcb  jnz     short loc_140C67DD8
0x140c67dcd  cmp     [rsp+160h+var_FC], r13d
0x140c67dd2  jnz     short loc_140C67DD8
0x140c67dd4  mov     ebx, [rsp+160h+var_E8]
0x140c67dd8  mov     rcx, [rbp+60h+Handle]; Handle
0x140c67ddc  call    ZwClose
0x140c67de1  mov     rcx, [rbp+60h+var_D8]; Handle
0x140c67de5  call    ZwClose
0x140c67dea  test    edi, edi
0x140c67dec  jz      short loc_140C67DFE
0x140c67dee  or      cs:dword_140FDA02C, 2
0x140c67df5  test    ebx, ebx
0x140c67df7  jz      short loc_140C67DFE
0x140c67df9  call    sub_140730784
0x140c67dfe  lea     rdi, qword_140028AC0
0x140c67e05  mov     eax, [rsp+160h+var_F8]
0x140c67e09  mov     dword ptr cs:NlsMbCodePageTag+7, eax
0x140c67e0f  mov     eax, [rsp+160h+var_F0]
0x140c67e13  mov     cs:dword_140FDA0AC, eax
0x140c67e19  mov     eax, cs:dword_140FBC980
0x140c67e1f  test    al, 10h
0x140c67e21  jz      short loc_140C67E28
0x140c67e23  and     eax, 1
0x140c67e26  jmp     short loc_140C67E2D
0x140c67e28  call    sub_1405DE5E8
0x140c67e2d  test    eax, eax
0x140c67e2f  jz      short loc_140C67E3F
0x140c67e31  lea     rdx, xmmword_140FDA2B0
0x140c67e38  mov     cl, 1
0x140c67e3a  call    sub_14076B240
0x140c67e3f  cmp     dword ptr cs:NlsMbCodePageTag+7, r15d
0x140c67e46  jz      short loc_140C67E8B
0x140c67e48  mov     eax, cs:dword_140FDA0AC
0x140c67e4e  test    al, 20h
0x140c67e50  jnz     short loc_140C67E5C
0x140c67e52  mov     eax, cs:dword_140FDA02C
0x140c67e58  test    al, 2
0x140c67e5a  jnz     short loc_140C67E7D
0x140c67e5c  lea     rdx, [rsp+160h+var_FF]
0x140c67e61  xor     ecx, ecx
0x140c67e63  call    sub_14077635C
0x140c67e68  mov     r14b, [rsp+160h+var_FF]
0x140c67e6d  test    eax, eax
0x140c67e6f  js      short loc_140C67E7D
0x140c67e71  test    r14b, r14b
0x140c67e74  jz      short loc_140C67E7D
0x140c67e76  or      cs:dword_140FDA02C, 1
0x140c67e7d  cmp     [rsp+160h+var_100], 0FFh
0x140c67e82  jnz     short loc_140C67E8B
0x140c67e84  or      cs:dword_140FDA02C, 1
0x140c67e8b  mov     eax, cs:dword_140FDA02C
0x140c67e91  test    al, 1
0x140c67e93  jz      short loc_140C67F10
0x140c67e95  call    RtlIsStateSeparationEnabled
0x140c67e9a  test    al, al
0x140c67e9c  jz      short loc_140C67EA9
0x140c67e9e  call    sub_14077540C
0x140c67ea3  mov     esi, eax
0x140c67ea5  test    eax, eax
0x140c67ea7  js      short loc_140C67F10
0x140c67ea9  xor     r8d, r8d
0x140c67eac  lea     rdx, sub_140769D50
0x140c67eb3  lea     ecx, [r8+1]
0x140c67eb7  call    sub_1408C77B0
0x140c67ebc  mov     esi, eax
0x140c67ebe  test    eax, eax
0x140c67ec0  js      short loc_140C67F10
0x140c67ec2  cmp     [rsp+160h+var_100], 0FFh
0x140c67ec7  jnz     short loc_140C67F02
0x140c67ec9  mov     rcx, cs:qword_140E4C568
0x140c67ed0  lea     r8, aSystem_3; "SYSTEM"
0x140c67ed7  mov     [rsp+160h+var_110], r15d
0x140c67edc  mov     r9d, 7
0x140c67ee2  mov     [rsp+160h+var_118], r15d
0x140c67ee7  xor     edx, edx
0x140c67ee9  mov     [rsp+160h+var_120], r15
0x140c67eee  mov     [rsp+160h+var_128], r15d
0x140c67ef3  mov     [rsp+160h+var_130], rdi
0x140c67ef8  mov     [rsp+160h+var_140], r15
0x140c67efd  call    sub_140AA3338
0x140c67f02  test    r14b, r14b
0x140c67f05  jz      short loc_140C67F10
0x140c67f07  xor     edx, edx
0x140c67f09  mov     cl, 1
0x140c67f0b  call    sub_14077635C
0x140c67f10  mov     eax, esi
0x140c67f12  mov     rcx, [rbp+60h+var_40]
0x140c67f16  xor     rcx, rsp; StackCookie
0x140c67f19  call    __security_check_cookie
0x140c67f1e  add     rsp, 130h
0x140c67f25  pop     r15
0x140c67f27  pop     r14
0x140c67f29  pop     r13
0x140c67f2b  pop     rdi
0x140c67f2c  pop     rsi
0x140c67f2d  pop     rbx
0x140c67f2e  pop     rbp
0x140c67f2f  retn
```
