# SampCheckIfChangePasswordAllowed(void *,void *,uchar *)

- ea: `0x1803e33e4`
- end: `0x1803e362a`
- name: `?SampCheckIfChangePasswordAllowed@@YAJPEAX0PEAE@Z`
- size: `582`
- prototype: `int(void *, void *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1803e49ac`
- `0x1803e63d0`

## callees

- `0x1803e33e4`
- `0x1803e4108`
- `0x1803e4410`
- `0x1803e4440`
- `0x1803e6924`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x1803e344d`
- `ntdll!RtlEqualSid` at `0x1803e3465`
- `ntdll!RtlEqualSid` at `0x1803e3481`
- `ntdll!RtlEqualSid` at `0x1803e34d5`
- `ntdll!RtlEqualSid` at `0x1803e34ed`
- `ntdll!RtlEqualSid` at `0x1803e3509`
- `ntdll!RtlEqualSid` at `0x1803e353c`
- `ntdll!RtlEqualSid` at `0x1803e3554`
- `ntdll!RtlEqualSid` at `0x1803e3570`
- `ntdll!RtlEqualSid` at `0x1803e35c0`
- `ntdll!RtlEqualSid` at `0x1803e35d8`
- `ntdll!RtlEqualSid` at `0x1803e35f4`
- `ntdll!RtlEqualSid` at `0x1803e344d`
- `ntdll!RtlEqualSid` at `0x1803e3465`
- `ntdll!RtlEqualSid` at `0x1803e3481`
- `ntdll!RtlEqualSid` at `0x1803e34d5`
- `ntdll!RtlEqualSid` at `0x1803e34ed`
- `ntdll!RtlEqualSid` at `0x1803e3509`
- `ntdll!RtlEqualSid` at `0x1803e353c`
- `ntdll!RtlEqualSid` at `0x1803e3554`
- `ntdll!RtlEqualSid` at `0x1803e3570`
- `ntdll!RtlEqualSid` at `0x1803e35c0`
- `ntdll!RtlEqualSid` at `0x1803e35d8`
- `ntdll!RtlEqualSid` at `0x1803e35f4`

## pseudocode

```c
__int64 __fastcall SampCheckIfChangePasswordAllowed(void *a1, void *a2, unsigned __int8 *a3)
{
  __int64 Dacl; // rax
  __int64 v6; // rbp
  unsigned int v7; // r15d
  unsigned int i; // edi
  _BYTE *AcePrivate; // rax
  _BYTE *v10; // rbx
  void *v11; // rax
  void *v12; // rax
  void *v13; // rax
  _QWORD *v14; // rdx
  __int64 v15; // rax
  void *v16; // rax
  void *v17; // rax
  void *v18; // rax
  void *v19; // rax
  void *v20; // rax
  void *v21; // rax
  _QWORD *v22; // rdx
  __int64 v23; // rax
  void *v24; // rax
  void *v25; // rax
  void *v26; // rax

  *a3 = 0;
  Dacl = GetDacl(a1);
  v6 = Dacl;
  if ( Dacl )
  {
    v7 = *(unsigned __int16 *)(Dacl + 4);
    for ( i = 0; i < v7; ++i )
    {
      AcePrivate = (_BYTE *)GetAcePrivate(v6, i);
      v10 = AcePrivate;
      if ( AcePrivate )
      {
        if ( *AcePrivate == 5 )
        {
          v11 = (void *)SidFromAce(AcePrivate);
          if ( RtlEqualSid(SampPrincipalSelfSid, v11)
            || (v12 = (void *)SidFromAce(v10), RtlEqualSid(a2, v12))
            || (v13 = (void *)SidFromAce(v10), RtlEqualSid(SampWorldSid, v13)) )
          {
            v14 = (_QWORD *)((unsigned __int64)(v10 + 12) & -(__int64)((*((_DWORD *)v10 + 2) & 1) != 0));
            if ( v14 )
            {
              v15 = *v14 - *(_QWORD *)&GUID_CONTROL_UserChangePassword.Data1;
              if ( *v14 == *(_QWORD *)&GUID_CONTROL_UserChangePassword.Data1 )
                v15 = *(_QWORD *)(((unsigned __int64)(v10 + 12) & -(__int64)((*((_DWORD *)v10 + 2) & 1) != 0)) + 8)
                    - *(_QWORD *)GUID_CONTROL_UserChangePassword.Data4;
              if ( !v15 )
                goto LABEL_32;
            }
          }
        }
        if ( !*v10 )
        {
          v16 = (void *)SidFromAce(v10);
          if ( RtlEqualSid(SampPrincipalSelfSid, v16)
            || (v17 = (void *)SidFromAce(v10), RtlEqualSid(a2, v17))
            || (v18 = (void *)SidFromAce(v10), RtlEqualSid(SampWorldSid, v18)) )
          {
            if ( (AccessMaskFromAce(v10) & 0x100) != 0 )
            {
LABEL_32:
              *a3 = 1;
              return 0;
            }
          }
        }
        if ( *v10 == 6 )
        {
          v19 = (void *)SidFromAce(v10);
          if ( RtlEqualSid(SampPrincipalSelfSid, v19)
            || (v20 = (void *)SidFromAce(v10), RtlEqualSid(a2, v20))
            || (v21 = (void *)SidFromAce(v10), RtlEqualSid(SampWorldSid, v21)) )
          {
            v22 = (_QWORD *)((unsigned __int64)(v10 + 12) & -(__int64)((*((_DWORD *)v10 + 2) & 1) != 0));
            if ( v22 )
            {
              v23 = *v22 - *(_QWORD *)&GUID_CONTROL_UserChangePassword.Data1;
              if ( *v22 == *(_QWORD *)&GUID_CONTROL_UserChangePassword.Data1 )
                v23 = *(_QWORD *)(((unsigned __int64)(v10 + 12) & -(__int64)((*((_DWORD *)v10 + 2) & 1) != 0)) + 8)
                    - *(_QWORD *)GUID_CONTROL_UserChangePassword.Data4;
              if ( !v23 )
                goto LABEL_33;
            }
          }
        }
        if ( *v10 == 1 )
        {
          v24 = (void *)SidFromAce(v10);
          if ( RtlEqualSid(SampPrincipalSelfSid, v24)
            || (v25 = (void *)SidFromAce(v10), RtlEqualSid(a2, v25))
            || (v26 = (void *)SidFromAce(v10), RtlEqualSid(SampWorldSid, v26)) )
          {
            if ( (AccessMaskFromAce(v10) & 0x100) != 0 )
            {
LABEL_33:
              *a3 = 0;
              return 0;
            }
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1803e33e4  push    rbx
0x1803e33e6  push    rbp
0x1803e33e7  push    rsi
0x1803e33e8  push    rdi
0x1803e33e9  push    r14
0x1803e33eb  push    r15
0x1803e33ed  sub     rsp, 28h
0x1803e33f1  mov     rsi, r8
0x1803e33f4  mov     byte ptr [r8], 0
0x1803e33f8  mov     r14, rdx
0x1803e33fb  call    GetDacl
0x1803e3400  mov     rbp, rax
0x1803e3403  test    rax, rax
0x1803e3406  jz      loc_1803E361B
0x1803e340c  movzx   r15d, word ptr [rax+4]
0x1803e3411  xor     edi, edi
0x1803e3413  cmp     edi, r15d
0x1803e3416  jnb     loc_1803E361B
0x1803e341c  mov     edx, edi
0x1803e341e  mov     rcx, rbp
0x1803e3421  call    GetAcePrivate
0x1803e3426  mov     rbx, rax
0x1803e3429  test    rax, rax
0x1803e342c  jz      loc_1803E360C
0x1803e3432  cmp     byte ptr [rax], 5
0x1803e3435  jnz     loc_1803E34BE
0x1803e343b  mov     rcx, rax
0x1803e343e  call    SidFromAce
0x1803e3443  mov     rcx, cs:SampPrincipalSelfSid; Sid1
0x1803e344a  mov     rdx, rax; Sid2
0x1803e344d  call    cs:__imp_RtlEqualSid
0x1803e3453  test    al, al
0x1803e3455  jnz     short loc_1803E348B
0x1803e3457  mov     rcx, rbx
0x1803e345a  call    SidFromAce
0x1803e345f  mov     rdx, rax; Sid2
0x1803e3462  mov     rcx, r14; Sid1
0x1803e3465  call    cs:__imp_RtlEqualSid
0x1803e346b  test    al, al
0x1803e346d  jnz     short loc_1803E348B
0x1803e346f  mov     rcx, rbx
0x1803e3472  call    SidFromAce
0x1803e3477  mov     rcx, cs:SampWorldSid; Sid1
0x1803e347e  mov     rdx, rax; Sid2
0x1803e3481  call    cs:__imp_RtlEqualSid
0x1803e3487  test    al, al
0x1803e3489  jz      short loc_1803E34BE
0x1803e348b  mov     eax, [rbx+8]
0x1803e348e  lea     rcx, [rbx+0Ch]
0x1803e3492  and     al, 1
0x1803e3494  neg     al
0x1803e3496  sbb     rdx, rdx
0x1803e3499  and     rdx, rcx
0x1803e349c  jz      short loc_1803E34BE
0x1803e349e  mov     rax, [rdx]
0x1803e34a1  sub     rax, qword ptr cs:GUID_CONTROL_UserChangePassword.Data1
0x1803e34a8  jnz     short loc_1803E34B5
0x1803e34aa  mov     rax, [rdx+8]
0x1803e34ae  sub     rax, qword ptr cs:GUID_CONTROL_UserChangePassword.Data4
0x1803e34b5  test    rax, rax
0x1803e34b8  jz      loc_1803E3613
0x1803e34be  cmp     byte ptr [rbx], 0
0x1803e34c1  jnz     short loc_1803E3525
0x1803e34c3  mov     rcx, rbx
0x1803e34c6  call    SidFromAce
0x1803e34cb  mov     rcx, cs:SampPrincipalSelfSid; Sid1
0x1803e34d2  mov     rdx, rax; Sid2
0x1803e34d5  call    cs:__imp_RtlEqualSid
0x1803e34db  test    al, al
0x1803e34dd  jnz     short loc_1803E3513
0x1803e34df  mov     rcx, rbx
0x1803e34e2  call    SidFromAce
0x1803e34e7  mov     rdx, rax; Sid2
0x1803e34ea  mov     rcx, r14; Sid1
0x1803e34ed  call    cs:__imp_RtlEqualSid
0x1803e34f3  test    al, al
0x1803e34f5  jnz     short loc_1803E3513
0x1803e34f7  mov     rcx, rbx
0x1803e34fa  call    SidFromAce
0x1803e34ff  mov     rcx, cs:SampWorldSid; Sid1
0x1803e3506  mov     rdx, rax; Sid2
0x1803e3509  call    cs:__imp_RtlEqualSid
0x1803e350f  test    al, al
0x1803e3511  jz      short loc_1803E3525
0x1803e3513  mov     rcx, rbx
0x1803e3516  call    AccessMaskFromAce
0x1803e351b  bt      eax, 8
0x1803e351f  jb      loc_1803E3613
0x1803e3525  cmp     byte ptr [rbx], 6
0x1803e3528  jnz     short loc_1803E35A9
0x1803e352a  mov     rcx, rbx
0x1803e352d  call    SidFromAce
0x1803e3532  mov     rcx, cs:SampPrincipalSelfSid; Sid1
0x1803e3539  mov     rdx, rax; Sid2
0x1803e353c  call    cs:__imp_RtlEqualSid
0x1803e3542  test    al, al
0x1803e3544  jnz     short loc_1803E357A
0x1803e3546  mov     rcx, rbx
0x1803e3549  call    SidFromAce
0x1803e354e  mov     rdx, rax; Sid2
0x1803e3551  mov     rcx, r14; Sid1
0x1803e3554  call    cs:__imp_RtlEqualSid
0x1803e355a  test    al, al
0x1803e355c  jnz     short loc_1803E357A
0x1803e355e  mov     rcx, rbx
0x1803e3561  call    SidFromAce
0x1803e3566  mov     rcx, cs:SampWorldSid; Sid1
0x1803e356d  mov     rdx, rax; Sid2
0x1803e3570  call    cs:__imp_RtlEqualSid
0x1803e3576  test    al, al
0x1803e3578  jz      short loc_1803E35A9
0x1803e357a  mov     eax, [rbx+8]
0x1803e357d  lea     rcx, [rbx+0Ch]
0x1803e3581  and     al, 1
0x1803e3583  neg     al
0x1803e3585  sbb     rdx, rdx
0x1803e3588  and     rdx, rcx
0x1803e358b  jz      short loc_1803E35A9
0x1803e358d  mov     rax, [rdx]
0x1803e3590  sub     rax, qword ptr cs:GUID_CONTROL_UserChangePassword.Data1
0x1803e3597  jnz     short loc_1803E35A4
0x1803e3599  mov     rax, [rdx+8]
0x1803e359d  sub     rax, qword ptr cs:GUID_CONTROL_UserChangePassword.Data4
0x1803e35a4  test    rax, rax
0x1803e35a7  jz      short loc_1803E3618
0x1803e35a9  cmp     byte ptr [rbx], 1
0x1803e35ac  jnz     short loc_1803E360C
0x1803e35ae  mov     rcx, rbx
0x1803e35b1  call    SidFromAce
0x1803e35b6  mov     rcx, cs:SampPrincipalSelfSid; Sid1
0x1803e35bd  mov     rdx, rax; Sid2
0x1803e35c0  call    cs:__imp_RtlEqualSid
0x1803e35c6  test    al, al
0x1803e35c8  jnz     short loc_1803E35FE
0x1803e35ca  mov     rcx, rbx
0x1803e35cd  call    SidFromAce
0x1803e35d2  mov     rdx, rax; Sid2
0x1803e35d5  mov     rcx, r14; Sid1
0x1803e35d8  call    cs:__imp_RtlEqualSid
0x1803e35de  test    al, al
0x1803e35e0  jnz     short loc_1803E35FE
0x1803e35e2  mov     rcx, rbx
0x1803e35e5  call    SidFromAce
0x1803e35ea  mov     rcx, cs:SampWorldSid; Sid1
0x1803e35f1  mov     rdx, rax; Sid2
0x1803e35f4  call    cs:__imp_RtlEqualSid
0x1803e35fa  test    al, al
0x1803e35fc  jz      short loc_1803E360C
0x1803e35fe  mov     rcx, rbx
0x1803e3601  call    AccessMaskFromAce
0x1803e3606  bt      eax, 8
0x1803e360a  jb      short loc_1803E3618
0x1803e360c  inc     edi
0x1803e360e  jmp     loc_1803E3413
0x1803e3613  mov     byte ptr [rsi], 1
0x1803e3616  jmp     short loc_1803E361B
0x1803e3618  mov     byte ptr [rsi], 0
0x1803e361b  xor     eax, eax
0x1803e361d  add     rsp, 28h
0x1803e3621  pop     r15
0x1803e3623  pop     r14
0x1803e3625  pop     rdi
0x1803e3626  pop     rsi
0x1803e3627  pop     rbp
0x1803e3628  pop     rbx
0x1803e3629  retn
```
