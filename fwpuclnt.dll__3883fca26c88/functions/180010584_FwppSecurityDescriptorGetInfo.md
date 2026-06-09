# FwppSecurityDescriptorGetInfo

- ea: `0x180010584`
- end: `0x1800106dc`
- name: `FwppSecurityDescriptorGetInfo`
- size: `344`
- prototype: `__int64 __usercall@<rax>(PSECURITY_DESCRIPTOR SecurityDescriptor@<rcx>, PACL *Dacl, PACL *Sacl)`
- caller_count: `15`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002d90`
- `0x180013fd0`
- `0x1800146f0`
- `0x180014d20`
- `0x180015a50`
- `0x180016940`
- `0x180017860`
- `0x180017d20`
- `0x1800183b0`
- `0x180018a90`
- `0x180019480`
- `0x180019910`
- `0x18001a670`
- `0x18001ba90`
- `0x18001ee40`

## callees

- `0x180007e38`
- `0x180010584`
- `0x180011500`
- `0x180012bd0`

## import_xrefs

- `ntdll!RtlGetSaclSecurityDescriptor` at `0x18001067f`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x18001067f`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18001063b`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18001063b`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x180010607`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x180010607`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x1800105d5`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x1800105d5`

## string_xrefs

- `0x1800105e5`: `RtlGetOwnerSecurityDescriptor`
- `0x180010617`: `RtlGetGroupSecurityDescriptor`
- `0x18001064b`: `RtlGetDaclSecurityDescriptor`
- `0x18001068f`: `RtlGetSaclSecurityDescriptor`
- `0x1800106a6`: `FwppSecurityDescriptorGetInfo`

## pseudocode

```c
__int64 __fastcall FwppSecurityDescriptorGetInfo(
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        char a2,
        PSID *a3,
        PSID *a4,
        PACL *Dacl,
        PACL *Sacl)
{
  NTSTATUS OwnerSecurityDescriptor; // eax
  __int64 v10; // rcx
  const char *v11; // rdx
  __int64 v12; // rbx
  __int64 v13; // rax
  unsigned __int8 OwnerDefaulted; // [rsp+20h] [rbp-38h] BYREF
  unsigned __int8 DaclPresent[7]; // [rsp+21h] [rbp-37h] BYREF

  OwnerDefaulted = 0;
  DaclPresent[0] = 0;
  if ( (a2 & 1) != 0 )
  {
    if ( a3 )
    {
      OwnerSecurityDescriptor = RtlGetOwnerSecurityDescriptor(SecurityDescriptor, a3, &OwnerDefaulted);
      if ( OwnerSecurityDescriptor < 0 )
      {
        v11 = "RtlGetOwnerSecurityDescriptor";
        goto LABEL_19;
      }
    }
  }
  if ( (a2 & 2) != 0 )
  {
    if ( a4 )
    {
      OwnerSecurityDescriptor = RtlGetGroupSecurityDescriptor(SecurityDescriptor, a4, &OwnerDefaulted);
      if ( OwnerSecurityDescriptor < 0 )
      {
        v11 = "RtlGetGroupSecurityDescriptor";
        goto LABEL_19;
      }
    }
  }
  if ( (a2 & 4) != 0 && Dacl )
  {
    OwnerSecurityDescriptor = RtlGetDaclSecurityDescriptor(SecurityDescriptor, DaclPresent, Dacl, &OwnerDefaulted);
    if ( OwnerSecurityDescriptor < 0 )
    {
      v11 = "RtlGetDaclSecurityDescriptor";
      goto LABEL_19;
    }
    if ( !DaclPresent[0] )
      *Dacl = 0;
  }
  v12 = 0;
  if ( (a2 & 8) == 0 || !Sacl )
    return v12;
  OwnerSecurityDescriptor = RtlGetSaclSecurityDescriptor(SecurityDescriptor, DaclPresent, Sacl, &OwnerDefaulted);
  if ( OwnerSecurityDescriptor < 0 )
  {
    v11 = "RtlGetSaclSecurityDescriptor";
LABEL_19:
    v13 = WfpReportSysErrorAsNtStatus(v10, v11, (unsigned int)OwnerSecurityDescriptor);
    v12 = v13;
    if ( v13 )
      WfpReportError(v13, "FwppSecurityDescriptorGetInfo");
    return v12;
  }
  if ( !DaclPresent[0] )
    *Sacl = 0;
  return v12;
}

```

## disassembly

```asm
0x180010584  push    rbx
0x180010586  push    rbp
0x180010587  push    rsi
0x180010588  push    rdi
0x180010589  push    r14
0x18001058b  sub     rsp, 30h
0x18001058f  mov     rax, cs:__security_cookie
0x180010596  xor     rax, rsp
0x180010599  mov     [rsp+58h+var_30], rax
0x18001059e  mov     rbx, [rsp+58h+Dacl]
0x1800105a6  mov     r14, r9
0x1800105a9  mov     rsi, [rsp+58h+Sacl]
0x1800105b1  mov     rax, r8
0x1800105b4  mov     [rsp+58h+OwnerDefaulted], 0
0x1800105b9  mov     edi, edx
0x1800105bb  mov     [rsp+58h+DaclPresent], 0
0x1800105c0  mov     rbp, rcx
0x1800105c3  test    dl, 1
0x1800105c6  jz      short loc_1800105F1
0x1800105c8  test    rax, rax
0x1800105cb  jz      short loc_1800105F1
0x1800105cd  lea     r8, [rsp+58h+OwnerDefaulted]; OwnerDefaulted
0x1800105d2  mov     rdx, rax; Owner
0x1800105d5  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1800105dc  nop     dword ptr [rax+rax+00h]
0x1800105e1  test    eax, eax
0x1800105e3  jns     short loc_1800105F1
0x1800105e5  lea     rdx, aRtlgetownersec; "RtlGetOwnerSecurityDescriptor"
0x1800105ec  jmp     loc_180010696
0x1800105f1  test    dil, 2
0x1800105f5  jz      short loc_180010620
0x1800105f7  test    r14, r14
0x1800105fa  jz      short loc_180010620
0x1800105fc  lea     r8, [rsp+58h+OwnerDefaulted]; GroupDefaulted
0x180010601  mov     rdx, r14; Group
0x180010604  mov     rcx, rbp; SecurityDescriptor
0x180010607  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x18001060e  nop     dword ptr [rax+rax+00h]
0x180010613  test    eax, eax
0x180010615  jns     short loc_180010620
0x180010617  lea     rdx, aRtlgetgroupsec; "RtlGetGroupSecurityDescriptor"
0x18001061e  jmp     short loc_180010696
0x180010620  test    dil, 4
0x180010624  jz      short loc_180010662
0x180010626  test    rbx, rbx
0x180010629  jz      short loc_180010662
0x18001062b  lea     r9, [rsp+58h+OwnerDefaulted]; DaclDefaulted
0x180010630  mov     r8, rbx; Dacl
0x180010633  lea     rdx, [rsp+58h+DaclPresent]; DaclPresent
0x180010638  mov     rcx, rbp; SecurityDescriptor
0x18001063b  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x180010642  nop     dword ptr [rax+rax+00h]
0x180010647  test    eax, eax
0x180010649  jns     short loc_180010654
0x18001064b  lea     rdx, aRtlgetdaclsecu; "RtlGetDaclSecurityDescriptor"
0x180010652  jmp     short loc_180010696
0x180010654  cmp     [rsp+58h+DaclPresent], 0
0x180010659  jnz     short loc_180010662
0x18001065b  mov     qword ptr [rbx], 0
0x180010662  xor     ebx, ebx
0x180010664  test    dil, 8
0x180010668  jz      short loc_1800106C0
0x18001066a  test    rsi, rsi
0x18001066d  jz      short loc_1800106C0
0x18001066f  lea     r9, [rsp+58h+OwnerDefaulted]; SaclDefaulted
0x180010674  mov     r8, rsi; Sacl
0x180010677  lea     rdx, [rsp+58h+DaclPresent]; SaclPresent
0x18001067c  mov     rcx, rbp; SecurityDescriptor
0x18001067f  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x180010686  nop     dword ptr [rax+rax+00h]
0x18001068b  test    eax, eax
0x18001068d  jns     short loc_1800106B7
0x18001068f  lea     rdx, aRtlgetsaclsecu; "RtlGetSaclSecurityDescriptor"
0x180010696  mov     r8d, eax
0x180010699  call    WfpReportSysErrorAsNtStatus
0x18001069e  mov     rbx, rax
0x1800106a1  test    rax, rax
0x1800106a4  jz      short loc_1800106C0
0x1800106a6  lea     rdx, aFwppsecurityde; "FwppSecurityDescriptorGetInfo"
0x1800106ad  mov     rcx, rax
0x1800106b0  call    WfpReportError
0x1800106b5  jmp     short loc_1800106C0
0x1800106b7  cmp     [rsp+58h+DaclPresent], bl
0x1800106bb  jnz     short loc_1800106C0
0x1800106bd  mov     [rsi], rbx
0x1800106c0  mov     rax, rbx
0x1800106c3  mov     rcx, [rsp+58h+var_30]
0x1800106c8  xor     rcx, rsp; StackCookie
0x1800106cb  call    __security_check_cookie
0x1800106d0  add     rsp, 30h
0x1800106d4  pop     r14
0x1800106d6  pop     rdi
0x1800106d7  pop     rsi
0x1800106d8  pop     rbp
0x1800106d9  pop     rbx
0x1800106da  retn
```
