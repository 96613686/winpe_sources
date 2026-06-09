# MRxSmb2PreProcessOpen

- ea: `0x140010370`
- end: `0x1400104b4`
- name: `MRxSmb2PreProcessOpen`
- size: `324`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140010370`
- `0x14002a51c`
- `0x140037120`

## import_xrefs

- `ntoskrnl!SeAccessCheck` at `0x140039ebd`
- `ntoskrnl!SeAccessCheck` at `0x140039ebd`
- `rdbss!RxFcbScavengeRelatedFobxs` at `0x1400104a2`
- `rdbss!RxFcbScavengeRelatedFobxs` at `0x1400104a2`

## pseudocode

```c
__int64 __fastcall MRxSmb2PreProcessOpen(__int64 a1)
{
  __int64 v1; // rax
  __int64 v3; // rsi
  __int64 v4; // rbp
  __int64 v5; // rax
  __int64 v6; // rcx
  int v7; // edi
  void *v9; // rcx
  _QWORD *v10; // rdi
  _QWORD *v11; // rax
  _QWORD *v12; // rdx
  _QWORD *v13; // rax
  _QWORD *v14; // rbx
  __int64 v15; // r8
  int AccessStatus; // [rsp+50h] [rbp-48h] BYREF
  DWORD GrantedAccess; // [rsp+54h] [rbp-44h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+58h] [rbp-40h] BYREF

  v1 = *(_QWORD *)(a1 + 656);
  v3 = *(_QWORD *)(a1 + 56);
  AccessStatus = -1073741790;
  GrantedAccess = 0;
  v4 = *(_QWORD *)(v1 + 40);
  GenericMapping.GenericRead = 1179785;
  GenericMapping.GenericWrite = 1179926;
  GenericMapping.GenericExecute = 1179808;
  v5 = *(_QWORD *)(v4 + 416);
  GenericMapping.GenericAll = 2032127;
  v6 = *(_QWORD *)(v5 + 128);
  if ( v6
    && (v9 = *(void **)(v6 + 56)) != 0
    && !SeAccessCheck(
          v9,
          (PSECURITY_SUBJECT_CONTEXT)(*(_QWORD *)(*(_QWORD *)(a1 + 544) + 8LL) + 32LL),
          0,
          1u,
          0,
          0,
          &GenericMapping,
          *(_BYTE *)(a1 + 36),
          &GrantedAccess,
          &AccessStatus) )
  {
    v7 = AccessStatus;
  }
  else
  {
    v7 = 0;
  }
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qdqd(
        WPP_GLOBAL_Control->AttachedDevice,
        *(_QWORD *)(v4 + 416),
        (unsigned int)*(char *)(a1 + 36),
        a1,
        *(char *)(a1 + 36),
        *(_QWORD *)(v4 + 416),
        v7);
    }
    return (unsigned int)v7;
  }
  else
  {
    if ( *(_WORD *)v3 == 0xEC21 && *(int *)(v3 + 196) > 0 )
    {
      v10 = (_QWORD *)(v3 + 264);
      v11 = (_QWORD *)(v3 + 264);
      while ( 1 )
      {
        v11 = (_QWORD *)*v11;
        if ( v11 == v10 )
          break;
        v12 = v11 - 17;
        if ( *((_WORD *)v11 - 68) != 0xEBAA )
        {
          if ( v11 != (_QWORD *)136 )
          {
            do
            {
              v13 = v12 + 17;
              while ( 1 )
              {
                v13 = (_QWORD *)*v13;
                if ( v13 == v10 )
                  break;
                v14 = v13 - 17;
                if ( *((_WORD *)v13 - 68) != 0xEBAA )
                  goto LABEL_16;
              }
              v14 = 0;
LABEL_16:
              if ( (v12[9] & 8) != 0 )
              {
                v15 = v12[6];
                if ( v15 )
                {
                  if ( *(_DWORD *)(v15 + 44) != *(_DWORD *)(*(_QWORD *)(v12[5] + 40LL) + 264LL) )
                  {
                    LOBYTE(v15) = 1;
                    RxFcbScavengeRelatedFobxs(v3, v12, v15);
                  }
                }
              }
              v12 = v14;
            }
            while ( v14 );
          }
          return 0;
        }
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x140010370  push    rbx
0x140010372  push    rbp
0x140010373  push    rsi
0x140010374  push    rdi
0x140010375  sub     rsp, 78h
0x140010379  mov     rax, cs:__security_cookie
0x140010380  xor     rax, rsp
0x140010383  mov     [rsp+98h+var_30], rax
0x140010388  mov     rax, [rcx+290h]
0x14001038f  mov     rbx, rcx
0x140010392  mov     rsi, [rcx+38h]
0x140010396  mov     [rsp+98h+var_48], 0C0000022h
0x14001039e  mov     [rsp+98h+var_44], 0
0x1400103a6  mov     rbp, [rax+28h]
0x1400103aa  mov     [rsp+98h+var_40.GenericRead], 120089h
0x1400103b2  mov     [rsp+98h+var_40.GenericWrite], 120116h
0x1400103ba  mov     [rsp+98h+var_40.GenericExecute], 1200A0h
0x1400103c2  mov     rax, [rbp+1A0h]
0x1400103c9  mov     [rsp+98h+var_40.GenericAll], 1F01FFh
0x1400103d1  mov     rcx, [rax+80h]
0x1400103d8  test    rcx, rcx
0x1400103db  jnz     short loc_14001040A
0x1400103dd  xor     edi, edi
0x1400103df  test    edi, edi
0x1400103e1  js      loc_140039EDA
0x1400103e7  mov     eax, 0EC21h
0x1400103ec  cmp     [rsi], ax
0x1400103ef  jz      short loc_140010418
0x1400103f1  xor     eax, eax
0x1400103f3  mov     rcx, [rsp+98h+var_30]
0x1400103f8  xor     rcx, rsp; StackCookie
0x1400103fb  call    __security_check_cookie
0x140010400  add     rsp, 78h
0x140010404  pop     rdi
0x140010405  pop     rsi
0x140010406  pop     rbp
0x140010407  pop     rbx
0x140010408  retn
0x14001040a  mov     rcx, [rcx+38h]; SecurityDescriptor
0x14001040e  test    rcx, rcx
0x140010411  jz      short loc_1400103DD
0x140010413  jmp     loc_140039E6E
0x140010418  cmp     dword ptr [rsi+0C4h], 0
0x14001041f  jle     short loc_1400103F1
0x140010421  lea     rdi, [rsi+108h]
0x140010428  mov     ebp, 0EBAAh
0x14001042d  mov     rax, rdi
0x140010430  mov     rax, [rax]
0x140010433  cmp     rax, rdi
0x140010436  jz      short loc_1400103F1
0x140010438  lea     rdx, [rax-88h]
0x14001043f  cmp     [rdx], bp
0x140010442  jz      short loc_140010430
0x140010444  test    rdx, rdx
0x140010447  jz      short loc_1400103F1
0x140010449  nop     dword ptr [rax+00000000h]
0x140010450  lea     rax, [rdx+88h]
0x140010457  mov     rax, [rax]
0x14001045a  cmp     rax, rdi
0x14001045d  jz      short loc_1400104B0
0x14001045f  lea     rbx, [rax-88h]
0x140010466  cmp     [rbx], bp
0x140010469  jz      short loc_140010457
0x14001046b  mov     eax, [rdx+48h]
0x14001046e  test    al, 8
0x140010470  jnz     short loc_14001047F
0x140010472  mov     rdx, rbx
0x140010475  test    rbx, rbx
0x140010478  jnz     short loc_140010450
0x14001047a  jmp     loc_1400103F1
0x14001047f  mov     r8, [rdx+30h]
0x140010483  test    r8, r8
0x140010486  jz      short loc_140010472
0x140010488  mov     rax, [rdx+28h]
0x14001048c  mov     rcx, [rax+28h]
0x140010490  mov     eax, [rcx+108h]
0x140010496  cmp     [r8+2Ch], eax
0x14001049a  jz      short loc_140010472
0x14001049c  mov     r8b, 1
0x14001049f  mov     rcx, rsi
0x1400104a2  call    cs:__imp_RxFcbScavengeRelatedFobxs
0x1400104a9  nop     dword ptr [rax+rax+00h]
0x1400104ae  jmp     short loc_140010472
0x1400104b0  xor     ebx, ebx
0x1400104b2  jmp     short loc_14001046B
0x140039e6e  mov     rax, [rbx+220h]
0x140039e75  mov     r9d, 1; DesiredAccess
0x140039e7b  xor     r8d, r8d; SubjectContextLocked
0x140039e7e  mov     rdx, [rax+8]
0x140039e82  lea     rax, [rsp+98h+var_48]
0x140039e87  mov     [rsp+98h+AccessStatus], rax; AccessStatus
0x140039e8c  add     rdx, 20h ; ' '; SubjectSecurityContext
0x140039e90  lea     rax, [rsp+98h+var_44]
0x140039e95  mov     [rsp+98h+GrantedAccess], rax; GrantedAccess
0x140039e9a  movzx   eax, byte ptr [rbx+24h]
0x140039e9e  mov     [rsp+98h+AccessMode], al; AccessMode
0x140039ea2  lea     rax, [rsp+98h+var_40]
0x140039ea7  mov     [rsp+98h+GenericMapping], rax; GenericMapping
0x140039eac  mov     [rsp+98h+Privileges], 0; Privileges
0x140039eb5  mov     [rsp+98h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x140039ebd  call    cs:__imp_SeAccessCheck
0x140039ec4  nop     dword ptr [rax+rax+00h]
0x140039ec9  test    al, al
0x140039ecb  jnz     loc_1400103DD
0x140039ed1  mov     edi, [rsp+98h+var_48]
0x140039ed5  jmp     loc_1400103DF
0x140039eda  mov     rcx, cs:WPP_GLOBAL_Control
0x140039ee1  lea     rax, WPP_GLOBAL_Control
0x140039ee8  cmp     rcx, rax
0x140039eeb  jz      short loc_140039F20
0x140039eed  mov     eax, [rcx+2Ch]
0x140039ef0  test    al, 1
0x140039ef2  jz      short loc_140039F20
0x140039ef4  cmp     byte ptr [rcx+29h], 1
0x140039ef8  jb      short loc_140039F20
0x140039efa  mov     rdx, [rbp+1A0h]
0x140039f01  mov     r9, rbx
0x140039f04  movsx   r8d, byte ptr [rbx+24h]
0x140039f09  mov     rcx, [rcx+18h]
0x140039f0d  mov     dword ptr [rsp+98h+GenericMapping], edi
0x140039f11  mov     [rsp+98h+Privileges], rdx
0x140039f16  mov     [rsp+98h+PreviouslyGrantedAccess], r8d
0x140039f1b  call    WPP_SF_qdqd
0x140039f20  mov     eax, edi
0x140039f22  jmp     loc_1400103F3
```
