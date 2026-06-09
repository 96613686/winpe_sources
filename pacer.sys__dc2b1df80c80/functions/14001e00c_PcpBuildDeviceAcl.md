# PcpBuildDeviceAcl

- ea: `0x14001e00c`
- end: `0x14001e231`
- name: `PcpBuildDeviceAcl`
- size: `549`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x14001e4dc`

## callees

- `0x14000eb54`
- `0x14001df3c`
- `0x14001e00c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001e1b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e209`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e1b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e209`
- `ntoskrnl!ExAllocatePool2` at `0x14001e0d3`
- `ntoskrnl!ExAllocatePool2` at `0x14001e0d3`
- `ntoskrnl!SeExports` at `0x14001e060`
- `ntoskrnl!RtlCreateAcl` at `0x14001e0fc`
- `ntoskrnl!RtlCreateAcl` at `0x14001e0fc`
- `ntoskrnl!RtlLengthSid` at `0x14001e082`
- `ntoskrnl!RtlLengthSid` at `0x14001e093`
- `ntoskrnl!RtlLengthSid` at `0x14001e0a4`
- `ntoskrnl!RtlLengthSid` at `0x14001e0b5`
- `ntoskrnl!RtlLengthSid` at `0x14001e082`
- `ntoskrnl!RtlLengthSid` at `0x14001e093`
- `ntoskrnl!RtlLengthSid` at `0x14001e0a4`
- `ntoskrnl!RtlLengthSid` at `0x14001e0b5`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14001e12b`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14001e155`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14001e179`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14001e19d`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14001e12b`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14001e155`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14001e179`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14001e19d`

## pseudocode

```c
__int64 __fastcall PcpBuildDeviceAcl(struct _ACL **a1, int a2, int a3, int a4)
{
  int v5; // eax
  PSID v6; // rsi
  NTSTATUS Acl; // ebx
  PSID SeLocalServiceSid; // r12
  PSID SeAliasAdminsSid; // rbp
  PSID SeLocalSystemSid; // r15
  ULONG v11; // ebx
  ULONG v12; // ebx
  ULONG v13; // ebx
  ULONG v14; // ebx
  struct _ACL *Pool2; // rax
  struct _ACL *v16; // rdi
  int v18; // [rsp+98h] [rbp+10h] BYREF
  __int16 v19; // [rsp+9Ch] [rbp+14h]
  PSID Sid; // [rsp+A0h] [rbp+18h]

  Sid = 0;
  v18 = 0;
  v19 = 1280;
  v5 = PcpAllocateAndInitializeSid((unsigned int)&v18, a2, a3, a4);
  v6 = Sid;
  Acl = v5;
  if ( v5 >= 0 )
  {
    SeLocalServiceSid = SeExports->SeLocalServiceSid;
    SeAliasAdminsSid = SeExports->SeAliasAdminsSid;
    SeLocalSystemSid = SeExports->SeLocalSystemSid;
    v11 = RtlLengthSid(SeLocalServiceSid);
    v12 = RtlLengthSid(v6) + v11;
    v13 = RtlLengthSid(SeAliasAdminsSid) + v12;
    v14 = RtlLengthSid(SeLocalSystemSid) + 40 + v13;
    Pool2 = (struct _ACL *)ExAllocatePool2(64, v14, 1701274448);
    v16 = Pool2;
    if ( Pool2 )
    {
      Acl = RtlCreateAcl(Pool2, v14, 2u);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAccessAllowedAceEx(v16, 2u, 3u, 0x10000000u, SeAliasAdminsSid);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAceEx(v16, 2u, 3u, 0x10000000u, SeLocalSystemSid);
          if ( Acl >= 0 )
          {
            Acl = RtlAddAccessAllowedAceEx(v16, 2u, 3u, 0x10000000u, SeLocalServiceSid);
            if ( Acl >= 0 )
            {
              Acl = RtlAddAccessAllowedAceEx(v16, 2u, 3u, 0x10000000u, v6);
              if ( Acl >= 0 )
              {
                *a1 = v16;
                goto LABEL_15;
              }
            }
          }
        }
      }
      ExFreePoolWithTag(v16, 0);
    }
    else
    {
      Acl = -1073741670;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_0a0383b750aa364b280d5887b3b80ddf_Traceguids, (unsigned int)Acl);
  }
LABEL_15:
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x14001e00c  mov     r11, rsp
0x14001e00f  mov     [r11+8], rbx
0x14001e013  mov     [r11+20h], rbp
0x14001e017  push    rsi
0x14001e018  push    rdi
0x14001e019  push    r12
0x14001e01b  push    r14
0x14001e01d  push    r15
0x14001e01f  sub     rsp, 60h
0x14001e023  mov     r14, rcx
0x14001e026  mov     qword ptr [r11+18h], 0
0x14001e02e  lea     rax, [r11+18h]
0x14001e032  mov     dword ptr [r11+10h], 0
0x14001e03a  lea     rcx, [r11+10h]
0x14001e03e  mov     [r11-38h], rax
0x14001e042  mov     word ptr [r11+14h], 500h
0x14001e049  call    PcpAllocateAndInitializeSid
0x14001e04e  mov     rsi, [rsp+88h+Sid]
0x14001e056  mov     ebx, eax
0x14001e058  test    eax, eax
0x14001e05a  js      loc_14001E1C5
0x14001e060  mov     rax, cs:__imp_SeExports
0x14001e067  mov     rcx, [rax]
0x14001e06a  mov     r12, [rcx+180h]
0x14001e071  mov     rbp, [rcx+110h]
0x14001e078  mov     r15, [rcx+108h]
0x14001e07f  mov     rcx, r12; Sid
0x14001e082  call    cs:__imp_RtlLengthSid
0x14001e089  nop     dword ptr [rax+rax+00h]
0x14001e08e  mov     rcx, rsi; Sid
0x14001e091  mov     ebx, eax
0x14001e093  call    cs:__imp_RtlLengthSid
0x14001e09a  nop     dword ptr [rax+rax+00h]
0x14001e09f  mov     rcx, rbp; Sid
0x14001e0a2  add     ebx, eax
0x14001e0a4  call    cs:__imp_RtlLengthSid
0x14001e0ab  nop     dword ptr [rax+rax+00h]
0x14001e0b0  mov     rcx, r15; Sid
0x14001e0b3  add     ebx, eax
0x14001e0b5  call    cs:__imp_RtlLengthSid
0x14001e0bc  nop     dword ptr [rax+rax+00h]
0x14001e0c1  mov     ecx, 40h ; '@'
0x14001e0c6  mov     r8d, 65676350h
0x14001e0cc  add     eax, 28h ; '('
0x14001e0cf  add     ebx, eax
0x14001e0d1  mov     edx, ebx
0x14001e0d3  call    cs:__imp_ExAllocatePool2
0x14001e0da  nop     dword ptr [rax+rax+00h]
0x14001e0df  mov     rdi, rax
0x14001e0e2  test    rax, rax
0x14001e0e5  jnz     short loc_14001E0F1
0x14001e0e7  mov     ebx, 0C000009Ah
0x14001e0ec  jmp     loc_14001E1C5
0x14001e0f1  mov     r8d, 2; AclRevision
0x14001e0f7  mov     edx, ebx; AclLength
0x14001e0f9  mov     rcx, rdi; Acl
0x14001e0fc  call    cs:__imp_RtlCreateAcl
0x14001e103  nop     dword ptr [rax+rax+00h]
0x14001e108  mov     ebx, eax
0x14001e10a  test    eax, eax
0x14001e10c  js      loc_14001E1B4
0x14001e112  mov     edx, 2; AceRevision
0x14001e117  mov     [rsp+88h+var_68], rbp; Sid
0x14001e11c  mov     ebp, 10000000h
0x14001e121  mov     rcx, rdi; Acl
0x14001e124  mov     r9d, ebp; AccessMask
0x14001e127  lea     r8d, [rdx+1]; AceFlags
0x14001e12b  call    cs:__imp_RtlAddAccessAllowedAceEx
0x14001e132  nop     dword ptr [rax+rax+00h]
0x14001e137  mov     ebx, eax
0x14001e139  test    eax, eax
0x14001e13b  js      short loc_14001E1B4
0x14001e13d  mov     [rsp+88h+var_68], r15; Sid
0x14001e142  mov     r9d, ebp; AccessMask
0x14001e145  mov     r15d, 3
0x14001e14b  mov     rcx, rdi; Acl
0x14001e14e  mov     r8d, r15d; AceFlags
0x14001e151  lea     edx, [r15-1]; AceRevision
0x14001e155  call    cs:__imp_RtlAddAccessAllowedAceEx
0x14001e15c  nop     dword ptr [rax+rax+00h]
0x14001e161  mov     ebx, eax
0x14001e163  test    eax, eax
0x14001e165  js      short loc_14001E1B4
0x14001e167  mov     r9d, ebp; AccessMask
0x14001e16a  mov     [rsp+88h+var_68], r12; Sid
0x14001e16f  mov     r8d, r15d; AceFlags
0x14001e172  lea     edx, [r15-1]; AceRevision
0x14001e176  mov     rcx, rdi; Acl
0x14001e179  call    cs:__imp_RtlAddAccessAllowedAceEx
0x14001e180  nop     dword ptr [rax+rax+00h]
0x14001e185  mov     ebx, eax
0x14001e187  test    eax, eax
0x14001e189  js      short loc_14001E1B4
0x14001e18b  mov     r9d, ebp; AccessMask
0x14001e18e  mov     [rsp+88h+var_68], rsi; Sid
0x14001e193  mov     r8d, r15d; AceFlags
0x14001e196  lea     edx, [r15-1]; AceRevision
0x14001e19a  mov     rcx, rdi; Acl
0x14001e19d  call    cs:__imp_RtlAddAccessAllowedAceEx
0x14001e1a4  nop     dword ptr [rax+rax+00h]
0x14001e1a9  mov     ebx, eax
0x14001e1ab  test    eax, eax
0x14001e1ad  js      short loc_14001E1B4
0x14001e1af  mov     [r14], rdi
0x14001e1b2  jmp     short loc_14001E1FF
0x14001e1b4  xor     edx, edx; Tag
0x14001e1b6  mov     rcx, rdi; P
0x14001e1b9  call    cs:__imp_ExFreePoolWithTag
0x14001e1c0  nop     dword ptr [rax+rax+00h]
0x14001e1c5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e1cc  lea     rax, WPP_GLOBAL_Control
0x14001e1d3  cmp     rcx, rax
0x14001e1d6  jz      short loc_14001E1FF
0x14001e1d8  cmp     byte ptr [rcx+29h], 2
0x14001e1dc  jb      short loc_14001E1FF
0x14001e1de  test    dword ptr [rcx+2Ch], 800h
0x14001e1e5  jz      short loc_14001E1FF
0x14001e1e7  mov     rcx, [rcx+18h]
0x14001e1eb  lea     r8, WPP_0a0383b750aa364b280d5887b3b80ddf_Traceguids
0x14001e1f2  mov     edx, 0Bh
0x14001e1f7  mov     r9d, ebx
0x14001e1fa  call    WPP_SF_D
0x14001e1ff  test    rsi, rsi
0x14001e202  jz      short loc_14001E215
0x14001e204  xor     edx, edx; Tag
0x14001e206  mov     rcx, rsi; P
0x14001e209  call    cs:__imp_ExFreePoolWithTag
0x14001e210  nop     dword ptr [rax+rax+00h]
0x14001e215  lea     r11, [rsp+88h+var_28]
0x14001e21a  mov     eax, ebx
0x14001e21c  mov     rbx, [r11+30h]
0x14001e220  mov     rbp, [r11+48h]
0x14001e224  mov     rsp, r11
0x14001e227  pop     r15
0x14001e229  pop     r14
0x14001e22b  pop     r12
0x14001e22d  pop     rdi
0x14001e22e  pop     rsi
0x14001e22f  retn
```
