# DBGetAdministratorAndAdministratorsDNT

- ea: `0x1801d283c`
- end: `0x1801d2a73`
- name: `DBGetAdministratorAndAdministratorsDNT`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800895e4`

## callees

- `0x18001e090`
- `0x180021aa3`
- `0x180172ffc`
- `0x1801d0ea0`
- `0x1801d24f0`
- `0x1801d283c`
- `0x1801d614c`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x1801d2914`
- `ntdll!RtlSubAuthoritySid` at `0x1801d2992`
- `ntdll!RtlSubAuthoritySid` at `0x1801d2914`
- `ntdll!RtlSubAuthoritySid` at `0x1801d2992`
- `ntdll!RtlSubAuthorityCountSid` at `0x1801d2901`
- `ntdll!RtlSubAuthorityCountSid` at `0x1801d297f`
- `ntdll!RtlSubAuthorityCountSid` at `0x1801d2901`
- `ntdll!RtlSubAuthorityCountSid` at `0x1801d297f`
- `ntdll!RtlValidSid` at `0x1801d28c5`
- `ntdll!RtlValidSid` at `0x1801d2943`
- `ntdll!RtlValidSid` at `0x1801d28c5`
- `ntdll!RtlValidSid` at `0x1801d2943`
- `ntdll!RtlLengthSid` at `0x1801d28de`
- `ntdll!RtlLengthSid` at `0x1801d292e`
- `ntdll!RtlLengthSid` at `0x1801d295c`
- `ntdll!RtlLengthSid` at `0x1801d29a7`
- `ntdll!RtlLengthSid` at `0x1801d29b9`
- `ntdll!RtlLengthSid` at `0x1801d29e3`
- `ntdll!RtlLengthSid` at `0x1801d28de`
- `ntdll!RtlLengthSid` at `0x1801d292e`
- `ntdll!RtlLengthSid` at `0x1801d295c`
- `ntdll!RtlLengthSid` at `0x1801d29a7`
- `ntdll!RtlLengthSid` at `0x1801d29b9`
- `ntdll!RtlLengthSid` at `0x1801d29e3`

## pseudocode

```c
BOOLEAN DBGetAdministratorAndAdministratorsDNT()
{
  BOOLEAN result; // al
  ULONG v1; // eax
  PUCHAR v2; // rax
  ULONG v3; // edx
  ULONG v4; // eax
  PUCHAR v5; // rax
  ULONG v6; // edx
  ULONG v7; // eax
  __int64 v8; // rbx
  __int64 v9; // [rsp+20h] [rbp-A8h] BYREF
  _OWORD v10[4]; // [rsp+28h] [rbp-A0h] BYREF
  _OWORD v11[4]; // [rsp+68h] [rbp-60h] BYREF
  _DWORD Src[4]; // [rsp+A8h] [rbp-20h] BYREF

  Src[0] = 513;
  Src[1] = 83886080;
  Src[2] = 32;
  Src[3] = 544;
  result = 0;
  memset(v10, 0, 60);
  memset(v11, 0, 60);
  v9 = 0;
  if ( !*(_DWORD *)gfADAM )
  {
    result = RtlValidSid((char *)qword_18052B2C0 + 24);
    if ( result )
    {
      v1 = RtlLengthSid((char *)qword_18052B2C0 + 24);
      memcpy_0((char *)&v10[1] + 8, (char *)qword_18052B2C0 + 24, v1);
      v2 = RtlSubAuthorityCountSid((char *)&v10[1] + 8);
      v3 = *v2;
      *v2 = v3 + 1;
      *RtlSubAuthoritySid((char *)&v10[1] + 8, v3) = 500;
      LODWORD(v10[0]) = 58;
      DWORD1(v10[0]) = RtlLengthSid((char *)&v10[1] + 8);
      result = RtlValidSid((char *)qword_18052B2C0 + 24);
      if ( result )
      {
        v4 = RtlLengthSid((char *)qword_18052B2C0 + 24);
        memcpy_0((char *)&v10[1] + 8, (char *)qword_18052B2C0 + 24, v4);
        v5 = RtlSubAuthorityCountSid((char *)&v10[1] + 8);
        v6 = *v5;
        *v5 = v6 + 1;
        *RtlSubAuthoritySid((char *)&v10[1] + 8, v6) = 500;
        LODWORD(v10[0]) = 58;
        DWORD1(v10[0]) = RtlLengthSid((char *)&v10[1] + 8);
        v7 = RtlLengthSid(Src);
        memcpy_0((char *)&v11[1] + 8, Src, v7);
        LODWORD(v11[0]) = 58;
        DWORD1(v11[0]) = RtlLengthSid((char *)&v11[1] + 8);
        DBOpen2(1, &v9);
        v8 = v9;
        if ( !(unsigned int)DBFindObjectWithSidInNc(v9, v10, (unsigned int)dword_18052B2C8) )
        {
          dntAdministrator = *(_DWORD *)(v8 + 24);
          if ( !(unsigned int)DBFindObjectWithSidInNc(v8, v11, (unsigned int)dword_18052B2C8) )
          {
            dntAdministrators = *(_DWORD *)(v8 + 24);
            AdminDNTsAreValid = 1;
          }
        }
        return DBClose(v8, 1);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1801d283c  mov     r11, rsp
0x1801d283f  push    rbx
0x1801d2840  sub     rsp, 0C0h
0x1801d2847  mov     rax, cs:__security_cookie
0x1801d284e  xor     rax, rsp
0x1801d2851  mov     [rsp+0C8h+var_10], rax
0x1801d2859  mov     dword ptr [r11-20h], 201h
0x1801d2861  mov     dword ptr [r11-1Ch], 5000000h
0x1801d2869  mov     dword ptr [r11-18h], 20h ; ' '
0x1801d2871  mov     dword ptr [r11-14h], 220h
0x1801d2879  xorps   xmm0, xmm0
0x1801d287c  xor     eax, eax
0x1801d287e  movups  [rsp+0C8h+var_A0], xmm0
0x1801d2883  movups  [rsp+0C8h+Sid], xmm0
0x1801d2888  movups  xmmword ptr [rsp+0C8h+var_80], xmm0
0x1801d288d  movups  xmmword ptr [rsp+0C8h+var_80+0Ch], xmm0
0x1801d2892  xorps   xmm1, xmm1
0x1801d2895  movups  [rsp+0C8h+var_60], xmm1
0x1801d289a  movups  [rsp+0C8h+var_50], xmm1
0x1801d289f  movups  xmmword ptr [r11-40h], xmm1
0x1801d28a4  movups  xmmword ptr [r11-34h], xmm1
0x1801d28a9  mov     [rsp+0C8h+var_A8], rax
0x1801d28ae  cmp     cs:gfADAM, eax
0x1801d28b4  jnz     loc_1801D2A5A
0x1801d28ba  mov     rcx, cs:qword_18052B2C0
0x1801d28c1  add     rcx, 18h; Sid
0x1801d28c5  call    cs:__imp_RtlValidSid
0x1801d28cb  test    al, al
0x1801d28cd  jz      loc_1801D2A58
0x1801d28d3  mov     rcx, cs:qword_18052B2C0
0x1801d28da  add     rcx, 18h; Sid
0x1801d28de  call    cs:__imp_RtlLengthSid
0x1801d28e4  mov     r8d, eax; Size
0x1801d28e7  mov     rdx, cs:qword_18052B2C0
0x1801d28ee  add     rdx, 18h; Src
0x1801d28f2  lea     rcx, [rsp+0C8h+Sid+8]; void *
0x1801d28f7  call    memcpy_0
0x1801d28fc  lea     rcx, [rsp+0C8h+Sid+8]; Sid
0x1801d2901  call    cs:__imp_RtlSubAuthorityCountSid
0x1801d2907  movzx   edx, byte ptr [rax]; SubAuthority
0x1801d290a  lea     ecx, [rdx+1]
0x1801d290d  mov     [rax], cl
0x1801d290f  lea     rcx, [rsp+0C8h+Sid+8]; Sid
0x1801d2914  call    cs:__imp_RtlSubAuthoritySid
0x1801d291a  mov     dword ptr [rax], 1F4h
0x1801d2920  mov     ebx, 3Ah ; ':'
0x1801d2925  mov     dword ptr [rsp+0C8h+var_A0], ebx
0x1801d2929  lea     rcx, [rsp+0C8h+Sid+8]; Sid
0x1801d292e  call    cs:__imp_RtlLengthSid
0x1801d2934  mov     dword ptr [rsp+0C8h+var_A0+4], eax
0x1801d2938  mov     rcx, cs:qword_18052B2C0
0x1801d293f  add     rcx, 18h; Sid
0x1801d2943  call    cs:__imp_RtlValidSid
0x1801d2949  test    al, al
0x1801d294b  jz      loc_1801D2A58
0x1801d2951  mov     rcx, cs:qword_18052B2C0
0x1801d2958  add     rcx, 18h; Sid
0x1801d295c  call    cs:__imp_RtlLengthSid
0x1801d2962  mov     r8d, eax; Size
0x1801d2965  mov     rdx, cs:qword_18052B2C0
0x1801d296c  add     rdx, 18h; Src
0x1801d2970  lea     rcx, [rsp+0C8h+Sid+8]; void *
0x1801d2975  call    memcpy_0
0x1801d297a  lea     rcx, [rsp+0C8h+Sid+8]; Sid
0x1801d297f  call    cs:__imp_RtlSubAuthorityCountSid
0x1801d2985  movzx   edx, byte ptr [rax]; SubAuthority
0x1801d2988  lea     ecx, [rdx+1]
0x1801d298b  mov     [rax], cl
0x1801d298d  lea     rcx, [rsp+0C8h+Sid+8]; Sid
0x1801d2992  call    cs:__imp_RtlSubAuthoritySid
0x1801d2998  mov     dword ptr [rax], 1F4h
0x1801d299e  mov     dword ptr [rsp+0C8h+var_A0], ebx
0x1801d29a2  lea     rcx, [rsp+0C8h+Sid+8]; Sid
0x1801d29a7  call    cs:__imp_RtlLengthSid
0x1801d29ad  mov     dword ptr [rsp+0C8h+var_A0+4], eax
0x1801d29b1  lea     rcx, [rsp+0C8h+Src]; Sid
0x1801d29b9  call    cs:__imp_RtlLengthSid
0x1801d29bf  mov     r8d, eax; Size
0x1801d29c2  lea     rdx, [rsp+0C8h+Src]; Src
0x1801d29ca  lea     rcx, [rsp+0C8h+var_50+8]; void *
0x1801d29d2  call    memcpy_0
0x1801d29d7  mov     dword ptr [rsp+0C8h+var_60], ebx
0x1801d29db  lea     rcx, [rsp+0C8h+var_50+8]; Sid
0x1801d29e3  call    cs:__imp_RtlLengthSid
0x1801d29e9  mov     dword ptr [rsp+0C8h+var_60+4], eax
0x1801d29ed  lea     rdx, [rsp+0C8h+var_A8]
0x1801d29f2  lea     ecx, [rbx-39h]
0x1801d29f5  call    DBOpen2
0x1801d29fa  mov     r8d, cs:dword_18052B2C8
0x1801d2a01  lea     rdx, [rsp+0C8h+var_A0]
0x1801d2a06  mov     rbx, [rsp+0C8h+var_A8]
0x1801d2a0b  mov     rcx, rbx
0x1801d2a0e  call    DBFindObjectWithSidInNc
0x1801d2a13  test    eax, eax
0x1801d2a15  jnz     short loc_1801D2A4B
0x1801d2a17  mov     eax, [rbx+18h]
0x1801d2a1a  mov     cs:dntAdministrator, eax
0x1801d2a20  mov     r8d, cs:dword_18052B2C8
0x1801d2a27  lea     rdx, [rsp+0C8h+var_60]
0x1801d2a2c  mov     rcx, rbx
0x1801d2a2f  call    DBFindObjectWithSidInNc
0x1801d2a34  test    eax, eax
0x1801d2a36  jnz     short loc_1801D2A4B
0x1801d2a38  mov     eax, [rbx+18h]
0x1801d2a3b  mov     cs:dntAdministrators, eax
0x1801d2a41  mov     cs:AdminDNTsAreValid, 1
0x1801d2a4b  mov     edx, 1
0x1801d2a50  mov     rcx, rbx
0x1801d2a53  call    DBClose
0x1801d2a58  jmp     short $+2
0x1801d2a5a  mov     rcx, [rsp+0C8h+var_10]
0x1801d2a62  xor     rcx, rsp; StackCookie
0x1801d2a65  call    __security_check_cookie
0x1801d2a6a  add     rsp, 0C0h
0x1801d2a71  pop     rbx
0x1801d2a72  retn
0x180466d2c  push    rbp
0x180466d2e  sub     rsp, 20h
0x180466d32  mov     rbp, rdx
0x180466d35  mov     edx, 1
0x180466d3a  mov     rcx, [rbp+20h]
0x180466d3e  call    DBClose
0x180466d43  nop
0x180466d44  add     rsp, 20h
0x180466d48  pop     rbp
0x180466d49  retn
0x180466d4b  push    rbp
0x180466d4d  sub     rsp, 20h
0x180466d51  mov     rbp, rdx
0x180466d54  mov     rdx, [rcx]
0x180466d57  mov     edx, [rdx]
0x180466d59  mov     r8d, 2051C9Eh
0x180466d5f  call    DoHandleAllExceptions
0x180466d64  nop
0x180466d65  add     rsp, 20h
0x180466d69  pop     rbp
0x180466d6a  retn
```
