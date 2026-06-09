# BfeFwpConditionValueValidate

- ea: `0x1400ad330`
- end: `0x1400ad5dd`
- name: `BfeFwpConditionValueValidate`
- size: `685`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400ad238`
- `0x1400ad290`

## callees

- `0x140009520`
- `0x140009e00`
- `0x14003c580`
- `0x140050ce0`
- `0x14006a9a8`
- `0x14006b7e8`
- `0x1400aa658`
- `0x1400ad030`
- `0x1400ad330`
- `0x1400ad5f0`
- `0x1400ad648`
- `0x1400ad6a0`
- `0x1400ad700`

## import_xrefs

- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x1400ad3a8`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x1400ad3a8`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1400ad3ce`
- `ntoskrnl!RtlGetSaclSecurityDescriptor` at `0x1400ad3ce`

## string_xrefs

- `0x1400ad471`: `RtlValidRelativeSecurityDescriptor`
- `0x1400ad5c9`: `RtlGetSaclSecurityDescriptor`
- `0x1400ad3f7`: `BfeRelativeSecurityDescriptorValidate`
- `0x1400ad489`: `BfeRelativeSecurityDescriptorValidate`

## pseudocode

```c
__int64 __fastcall BfeFwpConditionValueValidate(__int64 a1)
{
  int v1; // edx
  __int64 v2; // rbx
  __int64 v3; // rdi
  __int64 v5; // rcx
  __int64 v6; // rax
  ULONG v7; // edx
  void *v8; // rbx
  __int64 v9; // rcx
  NTSTATUS SaclSecurityDescriptor; // eax
  __int64 v11; // rcx
  __int64 v12; // rax
  int v13; // edx
  __int64 v14; // r8
  __int64 v15; // rax
  unsigned __int8 SaclPresent; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int8 SaclDefaulted; // [rsp+48h] [rbp+10h] BYREF
  PACL Sacl; // [rsp+50h] [rbp+18h] BYREF

  v1 = *(_DWORD *)a1;
  v2 = 0;
  v3 = a1;
  if ( *(_DWORD *)a1 != 9 )
  {
    if ( v1 == 14 )
    {
      a1 = *(_QWORD *)(a1 + 8);
      if ( a1 )
      {
        v2 = BfeFwpByteBlobValidate();
        if ( !v2 )
        {
          v6 = *(_QWORD *)(v3 + 8);
          v7 = *(_DWORD *)v6;
          if ( *(_DWORD *)v6 )
          {
            v8 = *(void **)(v6 + 8);
            SaclPresent = 0;
            SaclDefaulted = 0;
            Sacl = 0;
            if ( RtlValidRelativeSecurityDescriptor(v8, v7, 0) )
            {
              SaclSecurityDescriptor = RtlGetSaclSecurityDescriptor(v8, &SaclPresent, &Sacl, &SaclDefaulted);
              if ( SaclSecurityDescriptor < 0 )
              {
                v12 = WfpReportSysErrorAsNtStatus(
                        v11,
                        "RtlGetSaclSecurityDescriptor",
                        (unsigned int)SaclSecurityDescriptor,
                        1);
              }
              else
              {
                v2 = 0;
                if ( !SaclPresent || !Sacl )
                  goto LABEL_20;
                v12 = WfpReportAppErrorAsWinError(v11, "BfeRelativeSecurityDescriptorValidate", 50);
              }
            }
            else
            {
              v12 = WfpReportSysErrorAsWinError(v9, "RtlValidRelativeSecurityDescriptor", 1338);
            }
            v2 = v12;
            if ( !v12 )
              return v2;
            WfpReportError(v12, "BfeRelativeSecurityDescriptorValidate");
LABEL_20:
            if ( !v2 )
              return v2;
            goto LABEL_16;
          }
          v15 = WfpReportAppErrorAsWinError(v5, "BfeFwpConditionValueValidate", 1338);
LABEL_19:
          v2 = v15;
          goto LABEL_20;
        }
LABEL_16:
        WfpReportError(v2, "BfeFwpConditionValueValidate");
        return v2;
      }
    }
    else if ( v1 <= 256 )
    {
      if ( v1 != 256 )
      {
        switch ( *(_DWORD *)a1 )
        {
          case 0:
          case 1:
          case 2:
          case 3:
          case 5:
          case 6:
          case 7:
            return v2;
          case 4:
          case 8:
          case 0xA:
          case 0xB:
          case 0x12:
            if ( !*(_QWORD *)(a1 + 8) )
              goto LABEL_17;
            return v2;
          case 0xC:
          case 0x10:
            a1 = *(_QWORD *)(a1 + 8);
            if ( !a1 )
              goto LABEL_17;
            v2 = BfeFwpByteBlobValidate();
            if ( !v2 )
              return v2;
            goto LABEL_16;
          case 0xD:
            a1 = *(_QWORD *)(a1 + 8);
            if ( !a1 )
              goto LABEL_17;
            v2 = BfeSidValidate();
            if ( !v2 )
              return v2;
            goto LABEL_16;
          case 0xF:
            a1 = *(_QWORD *)(a1 + 8);
            if ( !a1 )
              goto LABEL_17;
            v2 = BfeFwpTokenInformationValidate();
            if ( !v2 )
              return v2;
            goto LABEL_16;
          case 0x11:
            a1 = *(_QWORD *)(a1 + 8);
            if ( !a1 )
              goto LABEL_17;
            v2 = BfeWstrValidate();
            if ( !v2 )
              return v2;
            goto LABEL_16;
          default:
            goto LABEL_48;
        }
      }
      a1 = *(_QWORD *)(a1 + 8);
      if ( a1 )
      {
        v2 = BfeFwpV4AddrAndMaskValidate();
        if ( !v2 )
          return v2;
        goto LABEL_16;
      }
    }
    else
    {
      v13 = v1 - 257;
      if ( v13 )
      {
        if ( v13 != 1 )
        {
LABEL_48:
          v14 = 3223453725LL;
          goto LABEL_18;
        }
        a1 = *(_QWORD *)(a1 + 8);
        if ( a1 )
        {
          v2 = BfeFwpRangeValidate();
          if ( !v2 )
            return v2;
          goto LABEL_16;
        }
      }
      else
      {
        a1 = *(_QWORD *)(a1 + 8);
        if ( a1 )
        {
          v2 = BfeFwpV6AddrAndMaskValidate();
          if ( !v2 )
            return v2;
          goto LABEL_16;
        }
      }
    }
LABEL_17:
    v14 = 3223453724LL;
LABEL_18:
    v15 = WfpReportAppErrorAsNtStatus(a1, "BfeFwpConditionValueValidate", v14);
    goto LABEL_19;
  }
  return v2;
}

```

## disassembly

```asm
0x1400ad330  mov     [rsp+arg_18], rbx
0x1400ad335  push    rdi
0x1400ad336  sub     rsp, 30h
0x1400ad33a  movsxd  rdx, dword ptr [rcx]
0x1400ad33d  xor     ebx, ebx
0x1400ad33f  mov     rdi, rcx
0x1400ad342  cmp     edx, 9
0x1400ad345  jnz     short loc_1400AD356
0x1400ad347  mov     rax, rbx; jumptable 00000001400AD4D4 cases 0-3,5-7
0x1400ad34a  mov     rbx, [rsp+38h+arg_18]
0x1400ad34f  add     rsp, 30h
0x1400ad353  pop     rdi
0x1400ad354  retn
0x1400ad356  cmp     edx, 0Eh
0x1400ad359  jnz     loc_1400AD405
0x1400ad35f  mov     rcx, [rcx+8]
0x1400ad363  test    rcx, rcx
0x1400ad366  jz      loc_1400AD44B
0x1400ad36c  call    BfeFwpByteBlobValidate
0x1400ad371  mov     rbx, rax
0x1400ad374  test    rax, rax
0x1400ad377  jnz     loc_1400AD437
0x1400ad37d  mov     rax, [rdi+8]
0x1400ad381  mov     edx, [rax]; SecurityDescriptorLength
0x1400ad383  test    edx, edx
0x1400ad385  jz      loc_1400AD5AC
0x1400ad38b  mov     rbx, [rax+8]
0x1400ad38f  xor     r8d, r8d; RequiredInformation
0x1400ad392  mov     rcx, rbx; SecurityDescriptorInput
0x1400ad395  mov     [rsp+38h+SaclPresent], 0
0x1400ad39a  mov     [rsp+38h+SaclDefaulted], 0
0x1400ad39f  mov     [rsp+38h+Sacl], 0
0x1400ad3a8  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x1400ad3af  nop     dword ptr [rax+rax+00h]
0x1400ad3b4  test    al, al
0x1400ad3b6  jz      loc_1400AD46B
0x1400ad3bc  lea     r9, [rsp+38h+SaclDefaulted]; SaclDefaulted
0x1400ad3c1  mov     rcx, rbx; SecurityDescriptor
0x1400ad3c4  lea     r8, [rsp+38h+Sacl]; Sacl
0x1400ad3c9  lea     rdx, [rsp+38h+SaclPresent]; SaclPresent
0x1400ad3ce  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x1400ad3d5  nop     dword ptr [rax+rax+00h]
0x1400ad3da  test    eax, eax
0x1400ad3dc  js      loc_1400AD5C3
0x1400ad3e2  xor     ebx, ebx
0x1400ad3e4  cmp     [rsp+38h+SaclPresent], bl
0x1400ad3e8  jz      short loc_1400AD460
0x1400ad3ea  cmp     [rsp+38h+Sacl], rbx
0x1400ad3ef  jz      short loc_1400AD460
0x1400ad3f1  mov     r8d, 32h ; '2'
0x1400ad3f7  lea     rdx, aBferelativesec; "BfeRelativeSecurityDescriptorValidate"
0x1400ad3fe  call    WfpReportAppErrorAsWinError
0x1400ad403  jmp     short loc_1400AD47D
0x1400ad405  cmp     edx, 100h
0x1400ad40b  jle     loc_1400AD49A
0x1400ad411  sub     edx, 101h
0x1400ad417  jnz     loc_1400AD4FD
0x1400ad41d  mov     rcx, [rcx+8]
0x1400ad421  test    rcx, rcx
0x1400ad424  jz      short loc_1400AD44B
0x1400ad426  call    BfeFwpV6AddrAndMaskValidate
0x1400ad42b  mov     rbx, rax
0x1400ad42e  test    rax, rax
0x1400ad431  jz      loc_1400AD347; jumptable 00000001400AD4D4 cases 0-3,5-7
0x1400ad437  lea     rdx, aBfefwpconditio; "BfeFwpConditionValueValidate"
0x1400ad43e  mov     rcx, rbx
0x1400ad441  call    WfpReportError
0x1400ad446  jmp     loc_1400AD347; jumptable 00000001400AD4D4 cases 0-3,5-7
0x1400ad44b  mov     r8d, 0C022001Ch
0x1400ad451  lea     rdx, aBfefwpconditio; "BfeFwpConditionValueValidate"
0x1400ad458  call    WfpReportAppErrorAsNtStatus
0x1400ad45d  mov     rbx, rax
0x1400ad460  test    rbx, rbx
0x1400ad463  jz      loc_1400AD347; jumptable 00000001400AD4D4 cases 0-3,5-7
0x1400ad469  jmp     short loc_1400AD437
0x1400ad46b  mov     r8d, 53Ah
0x1400ad471  lea     rdx, aRtlvalidrelati; "RtlValidRelativeSecurityDescriptor"
0x1400ad478  call    WfpReportSysErrorAsWinError
0x1400ad47d  mov     rbx, rax
0x1400ad480  test    rax, rax
0x1400ad483  jz      loc_1400AD347; jumptable 00000001400AD4D4 cases 0-3,5-7
0x1400ad489  lea     rdx, aBferelativesec; "BfeRelativeSecurityDescriptorValidate"
0x1400ad490  mov     rcx, rax
0x1400ad493  call    WfpReportError
0x1400ad498  jmp     short loc_1400AD460
0x1400ad49a  jnz     short loc_1400AD4B7
0x1400ad49c  mov     rcx, [rcx+8]
0x1400ad4a0  test    rcx, rcx
0x1400ad4a3  jz      short loc_1400AD44B
0x1400ad4a5  call    BfeFwpV4AddrAndMaskValidate
0x1400ad4aa  mov     rbx, rax
0x1400ad4ad  test    rax, rax
0x1400ad4b0  jnz     short loc_1400AD437
0x1400ad4b2  jmp     loc_1400AD347; jumptable 00000001400AD4D4 cases 0-3,5-7
0x1400ad4b7  cmp     edx, 12h; switch 19 cases
0x1400ad4ba  ja      def_1400AD4D4; jumptable 00000001400AD4D4 default case, cases 9,14
0x1400ad4c0  mov     rax, rdx
0x1400ad4c3  lea     rdx, cs:140000000h
0x1400ad4ca  mov     ecx, ds:(jpt_1400AD4D4 - 140000000h)[rdx+rax*4]
0x1400ad4d1  add     rcx, rdx
0x1400ad4d4  jmp     rcx; switch jump
0x1400ad4da  mov     rcx, [rdi+8]; jumptable 00000001400AD4D4 case 13
0x1400ad4de  test    rcx, rcx
0x1400ad4e1  jz      loc_1400AD44B
0x1400ad4e7  call    BfeSidValidate
0x1400ad4ec  mov     rbx, rax
0x1400ad4ef  test    rax, rax
0x1400ad4f2  jnz     loc_1400AD437
0x1400ad4f8  jmp     loc_1400AD347; jumptable 00000001400AD4D4 cases 0-3,5-7
0x1400ad4fd  cmp     edx, 1
0x1400ad500  jnz     def_1400AD4D4; jumptable 00000001400AD4D4 default case, cases 9,14
0x1400ad506  mov     rcx, [rcx+8]
0x1400ad50a  test    rcx, rcx
0x1400ad50d  jz      loc_1400AD44B
0x1400ad513  call    BfeFwpRangeValidate
0x1400ad518  mov     rbx, rax
0x1400ad51b  test    rax, rax
0x1400ad51e  jnz     loc_1400AD437
0x1400ad524  jmp     loc_1400AD347; jumptable 00000001400AD4D4 cases 0-3,5-7
0x1400ad529  cmp     [rdi+8], rbx; jumptable 00000001400AD4D4 cases 4,8,10,11,18
0x1400ad52d  jnz     loc_1400AD347; jumptable 00000001400AD4D4 cases 0-3,5-7
0x1400ad533  jmp     loc_1400AD44B
0x1400ad538  mov     rcx, [rdi+8]; jumptable 00000001400AD4D4 cases 12,16
0x1400ad53c  test    rcx, rcx
0x1400ad53f  jz      loc_1400AD44B
0x1400ad545  call    BfeFwpByteBlobValidate
0x1400ad54a  mov     rbx, rax
0x1400ad54d  test    rax, rax
0x1400ad550  jnz     loc_1400AD437
0x1400ad556  jmp     loc_1400AD347; jumptable 00000001400AD4D4 cases 0-3,5-7
0x1400ad55b  mov     rcx, [rdi+8]; jumptable 00000001400AD4D4 case 15
0x1400ad55f  test    rcx, rcx
0x1400ad562  jz      loc_1400AD44B
0x1400ad568  call    BfeFwpTokenInformationValidate
0x1400ad56d  mov     rbx, rax
0x1400ad570  test    rax, rax
0x1400ad573  jnz     loc_1400AD437
0x1400ad579  jmp     loc_1400AD347; jumptable 00000001400AD4D4 cases 0-3,5-7
0x1400ad57e  mov     rcx, [rdi+8]; jumptable 00000001400AD4D4 case 17
0x1400ad582  test    rcx, rcx
0x1400ad585  jz      loc_1400AD44B
0x1400ad58b  call    BfeWstrValidate
0x1400ad590  mov     rbx, rax
0x1400ad593  test    rax, rax
0x1400ad596  jnz     loc_1400AD437
0x1400ad59c  jmp     loc_1400AD347; jumptable 00000001400AD4D4 cases 0-3,5-7
0x1400ad5a1  mov     r8d, 0C022001Dh; jumptable 00000001400AD4D4 default case, cases 9,14
0x1400ad5a7  jmp     loc_1400AD451
0x1400ad5ac  mov     r8d, 53Ah
0x1400ad5b2  lea     rdx, aBfefwpconditio; "BfeFwpConditionValueValidate"
0x1400ad5b9  call    WfpReportAppErrorAsWinError
0x1400ad5be  jmp     loc_1400AD45D
0x1400ad5c3  mov     r9d, 1
0x1400ad5c9  lea     rdx, aRtlgetsaclsecu; "RtlGetSaclSecurityDescriptor"
0x1400ad5d0  mov     r8d, eax
0x1400ad5d3  call    WfpReportSysErrorAsNtStatus
0x1400ad5d8  jmp     loc_1400AD47D
```
