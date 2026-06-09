# KsIsCurrentProcessFrameServer

- ea: `0x180050db0`
- end: `0x180051084`
- name: `KsIsCurrentProcessFrameServer`
- size: `724`
- prototype: `char()`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180044ee0`
- `0x1800503f4`

## callees

- `0x180019bd0`
- `0x18001a000`
- `0x180050db0`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x180050de1`
- `ntoskrnl!ExGetPreviousMode` at `0x180050de1`
- `ntoskrnl!RtlInitializeSid` at `0x180050ea9`
- `ntoskrnl!RtlInitializeSid` at `0x180050ec7`
- `ntoskrnl!RtlInitializeSid` at `0x180050ea9`
- `ntoskrnl!RtlInitializeSid` at `0x180050ec7`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050ee0`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050ef7`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050f11`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050f2b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050f49`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050f62`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050f79`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050f90`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050fa9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050fc2`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050fda`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050ff3`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050ee0`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050ef7`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050f11`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050f2b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050f49`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050f62`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050f79`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050f90`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050fa9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050fc2`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050fda`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050ff3`
- `ntoskrnl!RtlCheckTokenMembership` at `0x18005100e`
- `ntoskrnl!RtlCheckTokenMembership` at `0x180051027`
- `ntoskrnl!RtlCheckTokenMembership` at `0x18005100e`
- `ntoskrnl!RtlCheckTokenMembership` at `0x180051027`
- `ntoskrnl!RtlLengthRequiredSid` at `0x180050dfd`
- `ntoskrnl!RtlLengthRequiredSid` at `0x180050e47`
- `ntoskrnl!RtlLengthRequiredSid` at `0x180050dfd`
- `ntoskrnl!RtlLengthRequiredSid` at `0x180050e47`
- `ntoskrnl!ExFreePoolWithTag` at `0x180051038`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005104e`
- `ntoskrnl!ExFreePoolWithTag` at `0x180051038`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005104e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180050e18`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180050e63`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180050e18`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180050e63`

## pseudocode

```c
char KsIsCurrentProcessFrameServer()
{
  char v0; // si
  ULONG v1; // ebx
  PVOID PoolWithTag; // rax
  void *v3; // rdi
  ULONG v4; // r14d
  PVOID v5; // rax
  void *v6; // rbx
  char v8; // [rsp+20h] [rbp-20h] BYREF
  _BYTE v9[3]; // [rsp+21h] [rbp-1Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+24h] [rbp-1Ch] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v8 = 0;
  v9[0] = 0;
  v0 = 1;
  if ( ExGetPreviousMode() )
  {
    v1 = RtlLengthRequiredSid(6u);
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, v1, 0x7363534Bu);
    v3 = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
      memset(PoolWithTag, 0, v1);
    v4 = RtlLengthRequiredSid(6u);
    v5 = ExAllocatePoolWithTag((POOL_TYPE)1025, v4, 0x7363534Bu);
    v6 = v5;
    if ( !ExPoolZeroingNativelySupported && v5 )
      memset(v5, 0, v4);
    if ( v3 )
    {
      if ( v6 )
      {
        if ( RtlInitializeSid(v3, &IdentifierAuthority, 6u) >= 0 && RtlInitializeSid(v6, &IdentifierAuthority, 6u) >= 0 )
        {
          *RtlSubAuthoritySid(v3, 0) = 80;
          *RtlSubAuthoritySid(v3, 1u) = -379073292;
          *RtlSubAuthoritySid(v3, 2u) = 2104103821;
          *RtlSubAuthoritySid(v3, 3u) = -1247697674;
          *RtlSubAuthoritySid(v3, 4u) = 1811662266;
          *RtlSubAuthoritySid(v3, 5u) = 774708259;
          *RtlSubAuthoritySid(v6, 0) = 80;
          *RtlSubAuthoritySid(v6, 1u) = -1558133237;
          *RtlSubAuthoritySid(v6, 2u) = 149274525;
          *RtlSubAuthoritySid(v6, 3u) = -1546006515;
          *RtlSubAuthoritySid(v6, 4u) = -428641286;
          *RtlSubAuthoritySid(v6, 5u) = -954125960;
          if ( (int)RtlCheckTokenMembership(0, v3, &v8) >= 0 )
            RtlCheckTokenMembership(0, v6, v9);
        }
      }
      ExFreePoolWithTag(v3, 0);
    }
    if ( v6 )
      ExFreePoolWithTag(v6, 0);
  }
  if ( !v8 && !v9[0] )
    return 0;
  return v0;
}

```

## disassembly

```asm
0x180050db0  push    rbp
0x180050db2  push    rbx
0x180050db3  push    rsi
0x180050db4  push    rdi
0x180050db5  push    r14
0x180050db7  mov     rbp, rsp
0x180050dba  sub     rsp, 40h
0x180050dbe  mov     rax, cs:__security_cookie
0x180050dc5  xor     rax, rsp
0x180050dc8  mov     [rbp+var_10], rax
0x180050dcc  mov     dword ptr [rbp+IdentifierAuthority.Value], 0
0x180050dd3  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x180050dd9  mov     [rbp+var_20], 0
0x180050ddd  mov     [rbp+var_1F], 0
0x180050de1  call    cs:__imp_ExGetPreviousMode
0x180050de8  nop     dword ptr [rax+rax+00h]
0x180050ded  mov     esi, 1
0x180050df2  test    al, al
0x180050df4  jz      loc_18005105A
0x180050dfa  lea     ecx, [rsi+5]; SubAuthorityCount
0x180050dfd  call    cs:__imp_RtlLengthRequiredSid
0x180050e04  nop     dword ptr [rax+rax+00h]
0x180050e09  mov     edx, eax; NumberOfBytes
0x180050e0b  mov     r8d, 7363534Bh; Tag
0x180050e11  mov     ecx, 401h; PoolType
0x180050e16  mov     ebx, eax
0x180050e18  call    cs:__imp_ExAllocatePoolWithTag
0x180050e1f  nop     dword ptr [rax+rax+00h]
0x180050e24  cmp     cs:ExPoolZeroingNativelySupported, 0
0x180050e2b  mov     rdi, rax
0x180050e2e  jnz     short loc_180050E42
0x180050e30  test    rax, rax
0x180050e33  jz      short loc_180050E42
0x180050e35  mov     r8d, ebx; Size
0x180050e38  xor     edx, edx; Val
0x180050e3a  mov     rcx, rax; void *
0x180050e3d  call    memset
0x180050e42  mov     ecx, 6; SubAuthorityCount
0x180050e47  call    cs:__imp_RtlLengthRequiredSid
0x180050e4e  nop     dword ptr [rax+rax+00h]
0x180050e53  mov     edx, eax; NumberOfBytes
0x180050e55  mov     r8d, 7363534Bh; Tag
0x180050e5b  mov     ecx, 401h; PoolType
0x180050e60  mov     r14d, eax
0x180050e63  call    cs:__imp_ExAllocatePoolWithTag
0x180050e6a  nop     dword ptr [rax+rax+00h]
0x180050e6f  cmp     cs:ExPoolZeroingNativelySupported, 0
0x180050e76  mov     rbx, rax
0x180050e79  jnz     short loc_180050E8D
0x180050e7b  test    rax, rax
0x180050e7e  jz      short loc_180050E8D
0x180050e80  mov     r8d, r14d; Size
0x180050e83  xor     edx, edx; Val
0x180050e85  mov     rcx, rax; void *
0x180050e88  call    memset
0x180050e8d  test    rdi, rdi
0x180050e90  jz      loc_180051044
0x180050e96  test    rbx, rbx
0x180050e99  jz      loc_180051033
0x180050e9f  mov     r8b, 6; SubAuthorityCount
0x180050ea2  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x180050ea6  mov     rcx, rdi; Sid
0x180050ea9  call    cs:__imp_RtlInitializeSid
0x180050eb0  nop     dword ptr [rax+rax+00h]
0x180050eb5  test    eax, eax
0x180050eb7  js      loc_180051033
0x180050ebd  mov     r8b, 6; SubAuthorityCount
0x180050ec0  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x180050ec4  mov     rcx, rbx; Sid
0x180050ec7  call    cs:__imp_RtlInitializeSid
0x180050ece  nop     dword ptr [rax+rax+00h]
0x180050ed3  test    eax, eax
0x180050ed5  js      loc_180051033
0x180050edb  xor     edx, edx; SubAuthority
0x180050edd  mov     rcx, rdi; Sid
0x180050ee0  call    cs:__imp_RtlSubAuthoritySid
0x180050ee7  nop     dword ptr [rax+rax+00h]
0x180050eec  mov     edx, esi; SubAuthority
0x180050eee  mov     rcx, rdi; Sid
0x180050ef1  mov     dword ptr [rax], 50h ; 'P'
0x180050ef7  call    cs:__imp_RtlSubAuthoritySid
0x180050efe  nop     dword ptr [rax+rax+00h]
0x180050f03  mov     edx, 2; SubAuthority
0x180050f08  mov     rcx, rdi; Sid
0x180050f0b  mov     dword ptr [rax], 0E967CCF4h
0x180050f11  call    cs:__imp_RtlSubAuthoritySid
0x180050f18  nop     dword ptr [rax+rax+00h]
0x180050f1d  mov     edx, 3; SubAuthority
0x180050f22  mov     rcx, rdi; Sid
0x180050f25  mov     dword ptr [rax], 7D6A138Dh
0x180050f2b  call    cs:__imp_RtlSubAuthoritySid
0x180050f32  nop     dword ptr [rax+rax+00h]
0x180050f37  mov     r14d, 4
0x180050f3d  mov     rcx, rdi; Sid
0x180050f40  mov     edx, r14d; SubAuthority
0x180050f43  mov     dword ptr [rax], 0B5A1A4F6h
0x180050f49  call    cs:__imp_RtlSubAuthoritySid
0x180050f50  nop     dword ptr [rax+rax+00h]
0x180050f55  lea     edx, [r14+1]; SubAuthority
0x180050f59  mov     rcx, rdi; Sid
0x180050f5c  mov     dword ptr [rax], 6BFBC5BAh
0x180050f62  call    cs:__imp_RtlSubAuthoritySid
0x180050f69  nop     dword ptr [rax+rax+00h]
0x180050f6e  xor     edx, edx; SubAuthority
0x180050f70  mov     rcx, rbx; Sid
0x180050f73  mov     dword ptr [rax], 2E2D1C23h
0x180050f79  call    cs:__imp_RtlSubAuthoritySid
0x180050f80  nop     dword ptr [rax+rax+00h]
0x180050f85  mov     edx, esi; SubAuthority
0x180050f87  mov     rcx, rbx; Sid
0x180050f8a  mov     dword ptr [rax], 50h ; 'P'
0x180050f90  call    cs:__imp_RtlSubAuthoritySid
0x180050f97  nop     dword ptr [rax+rax+00h]
0x180050f9c  lea     edx, [r14-2]; SubAuthority
0x180050fa0  mov     rcx, rbx; Sid
0x180050fa3  mov     dword ptr [rax], 0A320C60Bh
0x180050fa9  call    cs:__imp_RtlSubAuthoritySid
0x180050fb0  nop     dword ptr [rax+rax+00h]
0x180050fb5  lea     edx, [r14-1]; SubAuthority
0x180050fb9  mov     rcx, rbx; Sid
0x180050fbc  mov     dword ptr [rax], 8E5BF9Dh
0x180050fc2  call    cs:__imp_RtlSubAuthoritySid
0x180050fc9  nop     dword ptr [rax+rax+00h]
0x180050fce  mov     edx, r14d; SubAuthority
0x180050fd1  mov     rcx, rbx; Sid
0x180050fd4  mov     dword ptr [rax], 0A3D9D00Dh
0x180050fda  call    cs:__imp_RtlSubAuthoritySid
0x180050fe1  nop     dword ptr [rax+rax+00h]
0x180050fe6  lea     edx, [r14+1]; SubAuthority
0x180050fea  mov     rcx, rbx; Sid
0x180050fed  mov     dword ptr [rax], 0E67373FAh
0x180050ff3  call    cs:__imp_RtlSubAuthoritySid
0x180050ffa  nop     dword ptr [rax+rax+00h]
0x180050fff  lea     r8, [rbp+var_20]
0x180051003  mov     rdx, rdi
0x180051006  xor     ecx, ecx
0x180051008  mov     dword ptr [rax], 0C7213178h
0x18005100e  call    cs:__imp_RtlCheckTokenMembership
0x180051015  nop     dword ptr [rax+rax+00h]
0x18005101a  test    eax, eax
0x18005101c  js      short loc_180051033
0x18005101e  lea     r8, [rbp+var_1F]
0x180051022  mov     rdx, rbx
0x180051025  xor     ecx, ecx
0x180051027  call    cs:__imp_RtlCheckTokenMembership
0x18005102e  nop     dword ptr [rax+rax+00h]
0x180051033  xor     edx, edx; Tag
0x180051035  mov     rcx, rdi; P
0x180051038  call    cs:__imp_ExFreePoolWithTag
0x18005103f  nop     dword ptr [rax+rax+00h]
0x180051044  test    rbx, rbx
0x180051047  jz      short loc_18005105A
0x180051049  xor     edx, edx; Tag
0x18005104b  mov     rcx, rbx; P
0x18005104e  call    cs:__imp_ExFreePoolWithTag
0x180051055  nop     dword ptr [rax+rax+00h]
0x18005105a  cmp     [rbp+var_20], 0
0x18005105e  jnz     short loc_180051069
0x180051060  cmp     [rbp+var_1F], 0
0x180051064  jnz     short loc_180051069
0x180051066  xor     sil, sil
0x180051069  mov     al, sil
0x18005106c  mov     rcx, [rbp+var_10]
0x180051070  xor     rcx, rsp; StackCookie
0x180051073  call    __security_check_cookie
0x180051078  add     rsp, 40h
0x18005107c  pop     r14
0x18005107e  pop     rdi
0x18005107f  pop     rsi
0x180051080  pop     rbx
0x180051081  pop     rbp
0x180051082  retn
```
